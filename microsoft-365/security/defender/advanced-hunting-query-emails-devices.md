---
title: 高度な検索機能を使用して、デバイス、電子メール、アプリ、および ID 間の脅威を検出する
description: デバイス、電子メール、アプリ、および ID をカバーする一般的な検索シナリオとサンプル クエリを調査します。
keywords: 高度なハンティング、Office365 データ、Windows デバイス、Office365 メールの正規化、電子メール、アプリ、ID、脅威ハンティング、サイバー脅威ハンティング、検索、クエリ、テレメトリ、Microsoft 365、Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 237d665f14a34d990ec514735ad5a2dbc9020d92
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58253225"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>デバイス、メール、アプリ、ID 全体の脅威を探す

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[高度なMicrosoft 365 Defender](advanced-hunting-overview.md)を使用すると、次の脅威を積極的に検索できます。
- Microsoft Defender for Endpoint によって管理されるデバイス
- ユーザーが処理するメールMicrosoft 365
- クラウド アプリのアクティビティ、認証イベント、およびドメイン コントローラーのアクティビティは、Microsoft Cloud App Security Microsoft Defender for Identity によって追跡されます。

このレベルの可視性により、電子メールや Web に届く高度な侵入、ローカル特権の昇格、特権ドメイン資格情報の取得、デバイス間の横方向への移動など、ネットワークのセクションを横断する脅威をすばやく探し出す可能性があります。 

このような高度な脅威を探す際にクエリを作成する方法を探る際に役立つ、さまざまな検索シナリオに基づく一般的な手法とサンプル クエリを次に示します。

## <a name="get-entity-info"></a>エンティティ情報の取得
これらのクエリを使用して、ユーザー アカウント、デバイス、ファイルに関する情報をすばやく取得する方法について説明します。 

### <a name="obtain-user-accounts-from-email-addresses"></a>メール アドレスからユーザー アカウントを取得する
[デバイスとメールを対象とする複数のテーブル](advanced-hunting-schema-tables.md)全体に対してクエリを作成する場合、送信者または受信者のメール アドレスからユーザー アカウント名を取得する必要があります。 通常、この操作は、電子メール アドレスのローカル ホストを使用して受信者または送信者 *のアドレスに* 対して実行できます。

以下のスニペットでは [、tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto 関数を使用して、列の受信者の電子メール アドレスの直前にローカル ホスト `@` を抽出します `RecipientEmailAddress` 。

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
次のクエリは、このスニペットを使用する方法を示しています。

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>IdentityInfo テーブルを結合する

IdentityInfo テーブルを結合または結合することで、アカウント名や他のアカウント情報 [を取得できます](advanced-hunting-identityinfo-table.md)。 次のクエリは [、EmailEvents](advanced-hunting-emailevents-table.md) テーブルからフィッシングとマルウェアの検出の一覧を取得し、その情報をテーブルに結合して、各受信者に関する詳細情報 `IdentityInfo` を取得します。 

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

### <a name="get-device-information"></a>デバイス情報の取得
高度 [な検索スキーマは、](advanced-hunting-schema-tables.md) さまざまなテーブルに広範なデバイス情報を提供します。 たとえば [、DeviceInfo テーブルは、](advanced-hunting-deviceinfo-table.md) 定期的に集計されるイベント データに基づいて、包括的なデバイス情報を提供します。 このクエリでは、このテーブルを使用して、潜在的に侵害されたユーザー ( ) が任意のデバイスにログオンしたのか確認し、それらのデバイスでトリガーされたアラート `DeviceInfo` `<account-name>` を一覧表示します。

>[!Tip]
> このクエリは `kind=inner` 、内部結合 [を指定するために](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)使用します。これにより、 の左側の値の重複排除が防止されます `DeviceId` 。

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


### <a name="get-file-event-information"></a>ファイル イベント情報の取得

ファイル関連イベントに関する情報を取得するには、次のクエリを使用します。 

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


### <a name="get-network-event-information"></a>ネットワーク イベント情報の取得

ネットワーク関連のイベントに関する情報を取得するには、次のクエリを使用します。

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

### <a name="get-device-agent-version-information"></a>デバイス エージェントのバージョン情報の取得

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

デバイスの状態を取得するには、次のクエリを使用します。 次の例では、クエリはデバイスがオンボードされているのか確認します。

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

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>正常に送信されていないメールを受信したユーザーのログオン アクティビティを一覧表示する
[ゼロ時間自動削除 (ZAP) は](../office-365-security/zero-hour-auto-purge.md) 、悪意のあるメールを受信した後にアドレス指定します。 ZAP が失敗した場合、悪意のあるコードが最終的にデバイスで実行され、アカウントが侵害されたままになる可能性があります。 このクエリは、ZAP によって正常にアドレス指定されていない電子メールの受信者によって行われたログオン アクティビティをチェックします。

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>資格情報の盗難の対象となるドメイン アカウントによるログオン試行の取得
このクエリは、最初にテーブル内のすべての資格情報アクセス通知を識別 `AlertInfo` します。 次に、テーブルを結合または結合し、対象となるアカウントの名前と、ドメインに参加しているアカウントのフィルターのみを `AlertEvidence` 解析します。 最後に、テーブルをチェックして、ドメインに参加している対象アカウントによってすべてのログオン `IdentityLogonEvents` アクティビティを取得します。

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
悪意のあるファイル () を送信する電子メール アドレスがわかっている場合は、このクエリを実行して、この送信者のファイルがデバイス `MaliciousSender@example.com` に存在するかどうかを判断できます。 たとえば、このクエリを使用して、マルウェア配布キャンペーンの影響を受けるデバイスを特定できます。

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
悪意のあるメールには多くの場合、PowerShell コマンドを実行して追加のペイロードを配信するドキュメントや特別に細工した添付ファイルが含まれます。 既知の悪意のある送信者 ( ) からのメールを認識している場合は、このクエリを使用して、送信者から電子メールを受信した後 30 分以内に発生した PowerShell アクティビティを一覧表示および確認 `MaliciousSender@example.com` できます。  

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
