---
title: 高度な検索機能を使用して、デバイス、メール、アプリ、id 間の脅威を探します。
description: デバイス、メール、アプリ、および id をカバーする一般的な検索シナリオとサンプルクエリを調査します。
keywords: 高度な検索、Office365 データ、Windows デバイス、Office365 メール正規化、電子メール、アプリ、id、脅威の検索、サイバー脅威の検索、検索、クエリ、テレメトリ、Microsoft 365、Microsoft の脅威保護
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 9f5468ccb853bbbe126198a14f7b824d953a2738
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412636"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>デバイス、メール、アプリ、および id 間の脅威を探します。

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

Microsoft の脅威保護での[高度な](advanced-hunting-overview.md)検索では、次のような脅威を事前に確認できます。
- Microsoft Defender ATP で管理されているデバイス
- Microsoft 365 によって処理された電子メール
- Microsoft Cloud App Security と Azure ATP によって追跡される cloud app アクティビティ、認証イベント、およびドメインコントローラアクティビティ

この可視性レベルにより、電子メールや web で受信した高度な侵入を含む、ネットワークの一部を通過する脅威をすばやく確認できます。また、ローカルの権限を取得し、権限のあるドメインの資格情報を取得したり、デバイス間で laterally を移動したりすることができます。 

ここでは、このような高度な脅威を探すときにクエリを作成する方法を調査するのに役立つ、さまざまな検索シナリオに基づく一般的な手法とサンプルクエリを示します。

## <a name="get-entity-info"></a>エンティティ情報を取得する
ユーザーアカウント、デバイス、およびファイルに関する情報をすばやく取得する方法については、以下のクエリを使用してください。 

### <a name="obtain-user-accounts-from-email-addresses"></a>メール アドレスからユーザー アカウントを取得する
[デバイスとメールを対象とする複数のテーブル](advanced-hunting-schema-tables.md)全体に対してクエリを作成する場合、送信者または受信者のメール アドレスからユーザー アカウント名を取得する必要があります。 通常、この操作は、電子メールアドレスから *ローカルホスト* を使用して、受信者または送信者のアドレスに対して行うことができます。

次のスニペットでは、 [tostring ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) kusto 関数を使用して、 `@` 列の from 受信者の電子メールアドレスの前にローカルホストを抽出し `RecipientEmailAddress` ます。

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

### <a name="merge-the-identityinfo-table"></a>Id 情報テーブルをマージする

ユーザー [情報テーブル](advanced-hunting-identityinfo-table.md)を結合または結合することによって、アカウント名やその他のアカウント情報を取得できます。 次のクエリは、 [Emailevents テーブル](advanced-hunting-emailevents-table.md) からフィッシングとマルウェアの検出の一覧を取得し、その情報をテーブルに結合して `IdentityInfo` 各受信者に関する詳細情報を取得します。 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where MalwareFilterVerdict == 'Malware' or PhishFilterVerdict == 'Phish'
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, PhishFilterVerdict, MalwareFilterVerdict,
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a>デバイス情報を取得する
[高度な検索スキーマ](advanced-hunting-schema-tables.md)では、さまざまなテーブルに多様なデバイス情報が用意されています。 たとえば、 [DeviceInfo テーブル](advanced-hunting-deviceinfo-table.md) は、定期的に集計されたイベントデータに基づく包括的なデバイス情報を提供します。 このクエリは、テーブルを使用して、 `DeviceInfo` 侵害された可能性があるユーザー () がデバイスにログオンしているかどうかを確認し、 `<account-name>` それらのデバイスでトリガーされた通知を一覧表示します。

>[!Tip]
> このクエリは、を使用し `kind=inner` て [内部結合](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)を指定します。これにより、の左側の値の重複を防ぐことができ `DeviceId` ます。

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

## <a name="hunting-scenarios"></a>捜索のシナリオ

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Zapped できなかった電子メールを受信したユーザーのログオンアクティビティを一覧表示する
[ゼロ時間自動削除 (ZAP)](../office-365-security/zero-hour-auto-purge.md) は、受信後の悪意のある電子メールアドレスを解決します。 ZAP が失敗すると、悪意のあるコードがデバイス上で実行され、アカウントが侵害されたままになる可能性があります。 このクエリは、電子メールの受信者によって行われたログオンアクティビティが、ZAP によって正常にアドレス指定されなかったことをチェックします。

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>資格情報の盗用を対象としたドメインアカウントによるログオン試行の取得
このクエリは、まず、テーブル内のすべての資格情報アクセスアラートを識別 `AlertInfo` します。 次に、テーブルを結合または結合して、 `AlertEvidence` 対象となるアカウントの名前を解析し、ドメインに参加しているアカウントについてのみフィルター処理を行います。 最後に、テーブルをチェックして、 `IdentityLogonEvents` ドメインに参加している対象のアカウントによってすべてのログオンアクティビティを取得します。

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
悪意のあるファイルを送信する電子メールアドレスを知っていることを前提とし `MaliciousSender@example.com` て、このクエリを実行して、この送信者からのファイルがデバイス上に存在するかどうかを判断できます。 たとえば、このクエリを使用して、マルウェア配布キャンペーンの影響を受けたデバイスを特定することができます。

```kusto
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
//Get emails with attachments identified by a SHA-256
| where isnotempty(SHA256)
| join (
//Check devices for any activity involving the attachments
DeviceFileEvents
| project FileName, SHA256
) on SHA256
| project Timestamp, FileName , SHA256, DeviceName, DeviceId,  NetworkMessageId, SenderFromAddress, RecipientEmailAddress
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>悪意のあるメール受信後のログオン試行を確認する
このクエリは、既知の悪意のあるメールの受信後 30 分以内に受信者が実行したログオン試行のうち、最新のもの 10 件を見つけます。 このクエリを使用することで、メールの受信者のアカウントが侵害されたかどうかを確認できます。

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where MalwareFilterVerdict == "Malware"
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
悪意のあるメールには多くの場合、PowerShell コマンドを実行して追加のペイロードを配信するドキュメントや特別に細工した添付ファイルが含まれます。 既知の悪意のある送信者 () からのメールを認識している場合は `MaliciousSender@example.com` 、このクエリを使用して、送信者から電子メールを受信してから30分以内に発生した PowerShell アクティビティをリストして確認することができます。  

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
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
