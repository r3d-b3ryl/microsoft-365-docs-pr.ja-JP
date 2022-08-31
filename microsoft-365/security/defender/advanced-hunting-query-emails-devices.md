---
title: 高度な捜索を使用して、デバイス、電子メール、アプリ、ID 間で脅威を検出する
description: 一般的な捜索シナリオと、デバイス、電子メール、アプリ、ID を対象とするサンプル クエリを調査します。
keywords: 高度な捜索, Office365 データ, Windows デバイス, Office365 電子メール正規化, 電子メール, アプリ, ID, 脅威の捜索, サイバー脅威の捜索, 検索, クエリ, テレメトリ, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 740f9c5e683297f2a4d990cad5fdbc8c6295ed57
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481858"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>デバイス、メール、アプリ、ID 全体の脅威を探す

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defenderでの[高度な捜索](advanced-hunting-overview.md)では、次の複数の脅威をプロアクティブに検出できます。
- Microsoft Defender for Endpointによって管理されるデバイス
- Microsoft 365 によって処理された電子メール
- Microsoft Defender for Cloud AppsとMicrosoft Defender for Identityによって追跡されるクラウド アプリアクティビティ、認証イベント、ドメイン コントローラーアクティビティ

このレベルの可視性を使用すると、電子メールや Web に届く高度な侵入、ローカル特権の昇格、特権ドメイン資格情報の取得、デバイス間への横移動など、ネットワークのセクションを横断する脅威をすばやく検出できます。 

このような高度な脅威を探すときにクエリを構築する方法を調べるのに役立つ、さまざまなハンティング シナリオに基づく一般的な手法とサンプル クエリを次に示します。

## <a name="get-entity-info"></a>エンティティ情報を取得する
これらのクエリを使用して、ユーザー アカウント、デバイス、ファイルに関する情報をすばやく取得する方法について説明します。 

### <a name="obtain-user-accounts-from-email-addresses"></a>メール アドレスからユーザー アカウントを取得する
[デバイスとメールを対象とする複数のテーブル](advanced-hunting-schema-tables.md)全体に対してクエリを作成する場合、送信者または受信者のメール アドレスからユーザー アカウント名を取得する必要があります。 一般に、電子メール アドレスの *ローカル ホスト* を使用して、受信者または送信者のアドレスに対してこれを行うことができます。

次のスニペットでは、 [tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto 関数を使用して、列の受信者からの電子メール アドレスの直前に `@` ローカル ホストを抽出します `RecipientEmailAddress`。

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
次のクエリは、このスニペットの使用方法を示しています。

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>IdentityInfo テーブルをマージする

[IdentityInfo テーブル](advanced-hunting-identityinfo-table.md)をマージまたは結合することで、アカウント名とその他のアカウント情報を取得できます。 次のクエリでは、 [EmailEvents テーブル](advanced-hunting-emailevents-table.md) からフィッシングとマルウェアの検出の一覧を取得し、その情報をテーブルに `IdentityInfo` 結合して、各受信者に関する詳細情報を取得します。 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where ThreatTypes has "Malware" or ThreatTypes has "Phish"
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, ThreatTypes, 
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

この[短いビデオ](https://www.youtube.com/watch?v=8qZx7Pp5XgM)では、Kusto 照会言語を使用してテーブルを結合する方法について説明します。  

### <a name="get-device-information"></a>デバイス情報を取得する

[高度なハンティング スキーマ](advanced-hunting-schema-tables.md)は、さまざまなテーブルに広範なデバイス情報を提供します。 たとえば、 [DeviceInfo テーブル](advanced-hunting-deviceinfo-table.md) は、定期的に集計されるイベント データに基づいて包括的なデバイス情報を提供します。 このクエリでは、このテーブルを `DeviceInfo` 使用して、侵害された可能性のあるユーザー (`<account-name>`) が任意のデバイスにログオンしているかどうかを確認し、それらのデバイスでトリガーされたアラートを一覧表示します。

>[!Tip]
> このクエリは[、内部結合](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)を指定するために使用`kind=inner`します。これにより`DeviceId`、.

```kusto
DeviceInfo
//Query for devices that the potentially compromised account has logged onto
| where LoggedOnUsers contains '<account-name>'
| distinct DeviceId
//Crosscheck devices against alert records in AlertEvidence and AlertInfo tables
| join kind=inner AlertEvidence on DeviceId
| project AlertId
//List all alerts on devices that user has logged on to
| join AlertInfo on AlertId
| project AlertId, Timestamp, Title, Severity, Category 
```


### <a name="get-file-event-information"></a>ファイル イベント情報を取得する

次のクエリを使用して、ファイル関連のイベントに関する情報を取得します。 

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceFileEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


### <a name="get-network-event-information"></a>ネットワーク イベント情報を取得する

次のクエリを使用して、ネットワーク関連のイベントに関する情報を取得します。

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceNetworkEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```

### <a name="get-device-agent-version-information"></a>デバイス エージェントのバージョン情報を取得する

次のクエリを使用して、デバイスで実行されているエージェントのバージョンを取得します。

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceNetworkEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


### <a name="example-query-for-macos-devices"></a>macOS デバイスのクエリの例

次のクエリ例を使用して、Catalina より古いバージョンの macOS を実行しているすべてのデバイスを確認します。

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where OSPlatform == "macOS" and  OSVersion !contains "10.15" and OSVersion !contains "11."
| summarize by DeviceId
| join kind=inner (
    DeviceInfo
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```

### <a name="get-device-status-info"></a>デバイスの状態情報を取得する

次のクエリを使用して、デバイスの状態を取得します。 次の例では、デバイスがオンボードされているかどうかをクエリで確認します。

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where OnboardingStatus != "Onboarded"
| summarize by DeviceId
| join kind=inner (
    DeviceInfo
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


## <a name="hunting-scenarios"></a>捜索のシナリオ

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>正常に表示されなかった電子メールを受信したユーザーのログオン アクティビティを一覧表示する

[ゼロ時間自動消去 (ZAP)](../office-365-security/zero-hour-auto-purge.md) は、悪意のある電子メールを受信した後にアドレス指定します。 ZAP が失敗した場合、悪意のあるコードが最終的にデバイスで実行され、アカウントが侵害される可能性があります。 このクエリは、ZAP によって正常に対処されなかった電子メールの受信者によって行われたログオン アクティビティをチェックします。

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfully
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>資格情報の盗難の対象となるドメイン アカウントによるログオン試行を取得する

このクエリでは、まず、テーブル内のすべての資格情報アクセス アラートを `AlertInfo` 識別します。 その後、テーブルを `AlertEvidence` マージまたは結合します。このテーブルは、対象のアカウントの名前を解析し、ドメイン参加アカウントのフィルターのみを対象にします。 最後に、テーブルを `IdentityLogonEvents` チェックして、ドメインに参加している対象アカウントによってすべてのログオン アクティビティを取得します。

```kusto
AlertInfo
| where Timestamp > ago(30d)
//Get all credential access alerts
| where Category == "CredentialAccess"
//Get more info from AlertEvidence table to get the SID of the target accounts
| join AlertEvidence on AlertId
| extend IsJoined=(parse_json(AdditionalFields).Account.IsDomainJoined)
| extend TargetAccountSid=tostring(parse_json(AdditionalFields).Account.Sid)
//Filter for domain-joined accounts only
| where IsJoined has "true"
//Merge with IdentityLogonEvents to get all logon attempts by the potentially compromised target accounts
| join kind=inner IdentityLogonEvents on $left.TargetAccountSid == $right.AccountSid
//Show only pertinent info, such as account name, the app or service, protocol, the accessed device, and type of logon
| project AccountDisplayName, TargetAccountSid, Application, Protocol, DeviceName, LogonType
```

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>既知の悪意のある送信者からのファイルがデバイスに存在するかどうかを確認する

悪意のあるファイルを送信している電子メール アドレスがわかっている場合は`MaliciousSender@example.com`、このクエリを実行して、この送信者のファイルがデバイスに存在するかどうかを判断できます。 たとえば、このクエリを使用して、マルウェア配布キャンペーンの影響を受けるデバイスを特定できます。

```kusto
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
//Get emails with attachments identified by a SHA-256
| where isnotempty(SHA256)
| join (
//Check devices for any activity involving the attachments
DeviceFileEvents
| project FileName, SHA256, DeviceName, DeviceId
) on SHA256
| project Timestamp, FileName , SHA256, DeviceName, DeviceId,  NetworkMessageId, SenderFromAddress, RecipientEmailAddress
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>悪意のあるメール受信後のログオン試行を確認する

このクエリは、既知の悪意のあるメールの受信後 30 分以内に受信者が実行したログオン試行のうち、最新のもの 10 件を見つけます。 このクエリを使用することで、メールの受信者のアカウントが侵害されたかどうかを確認できます。

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where ThreatTypes has "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmails
| join (
//Merge malicious emails with logon events to find logons by recipients
IdentityLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
//Check only logons within 30 minutes of receipt of an email
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>既知の悪意のある送信者からのメール受信後の PowerShell アクティビティを確認する

悪意のあるメールには多くの場合、PowerShell コマンドを実行して追加のペイロードを配信するドキュメントや特別に細工した添付ファイルが含まれます。 既知の悪意のある送信者 () からのメールが認識されている場合は、このクエリを使用して、送信者`MaliciousSender@example.com`から電子メールを受信した後 30 分以内に発生した PowerShell アクティビティを一覧表示して確認できます。  

```kusto
//Define new table for emails from specific sender
let EmailsFromBadSender=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
//Merge emails from sender with process-related events on devices
EmailsFromBadSender
| join (
DeviceProcessEvents
//Look for PowerShell activity
| where FileName =~ "powershell.exe"
//Add line below to check only events initiated by Outlook
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
//Check only PowerShell activities within 30 minutes of receipt of an email
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>関連項目

- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
