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
ms.openlocfilehash: aacd0745ff507356035f8f460ed2b4307e9da6ed
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964875"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="27713-104">デバイス、メール、アプリ、ID 全体の脅威を探す</span><span class="sxs-lookup"><span data-stu-id="27713-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="27713-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="27713-105">**Applies to:**</span></span>
- <span data-ttu-id="27713-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27713-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="27713-107">[高度なMicrosoft 365 Defender](advanced-hunting-overview.md)を使用すると、次の脅威を積極的に検索できます。</span><span class="sxs-lookup"><span data-stu-id="27713-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="27713-108">Microsoft Defender for Endpoint によって管理されるデバイス</span><span class="sxs-lookup"><span data-stu-id="27713-108">Devices managed by Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="27713-109">ユーザーが処理するメールMicrosoft 365</span><span class="sxs-lookup"><span data-stu-id="27713-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="27713-110">クラウド アプリのアクティビティ、認証イベント、およびドメイン コントローラーのアクティビティは、Microsoft Cloud App Security Microsoft Defender for Identity によって追跡されます。</span><span class="sxs-lookup"><span data-stu-id="27713-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Microsoft Defender for Identity</span></span>

<span data-ttu-id="27713-111">このレベルの可視性により、電子メールや Web に届く高度な侵入、ローカル特権の昇格、特権ドメイン資格情報の取得、デバイス間の横方向への移動など、ネットワークのセクションを横断する脅威をすばやく探し出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27713-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="27713-112">このような高度な脅威を探す際にクエリを作成する方法を探る際に役立つ、さまざまな検索シナリオに基づく一般的な手法とサンプル クエリを次に示します。</span><span class="sxs-lookup"><span data-stu-id="27713-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="27713-113">エンティティ情報の取得</span><span class="sxs-lookup"><span data-stu-id="27713-113">Get entity info</span></span>
<span data-ttu-id="27713-114">これらのクエリを使用して、ユーザー アカウント、デバイス、ファイルに関する情報をすばやく取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="27713-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="27713-115">メール アドレスからユーザー アカウントを取得する</span><span class="sxs-lookup"><span data-stu-id="27713-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="27713-116">[デバイスとメールを対象とする複数のテーブル](advanced-hunting-schema-tables.md)全体に対してクエリを作成する場合、送信者または受信者のメール アドレスからユーザー アカウント名を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27713-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="27713-117">通常、この操作は、電子メール アドレスのローカル ホストを使用して受信者または送信者 *のアドレスに* 対して実行できます。</span><span class="sxs-lookup"><span data-stu-id="27713-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="27713-118">以下のスニペットでは [、tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto 関数を使用して、列の受信者の電子メール アドレスの直前にローカル ホスト `@` を抽出します `RecipientEmailAddress` 。</span><span class="sxs-lookup"><span data-stu-id="27713-118">In the snippet below, we use the [tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="27713-119">次のクエリは、このスニペットを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="27713-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="27713-120">IdentityInfo テーブルを結合する</span><span class="sxs-lookup"><span data-stu-id="27713-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="27713-121">IdentityInfo テーブルを結合または結合することで、アカウント名や他のアカウント情報 [を取得できます](advanced-hunting-identityinfo-table.md)。</span><span class="sxs-lookup"><span data-stu-id="27713-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="27713-122">次のクエリは [、EmailEvents](advanced-hunting-emailevents-table.md) テーブルからフィッシングとマルウェアの検出の一覧を取得し、その情報をテーブルに結合して、各受信者に関する詳細情報 `IdentityInfo` を取得します。</span><span class="sxs-lookup"><span data-stu-id="27713-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

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

### <a name="get-device-information"></a><span data-ttu-id="27713-123">デバイス情報の取得</span><span class="sxs-lookup"><span data-stu-id="27713-123">Get device information</span></span>
<span data-ttu-id="27713-124">高度 [な検索スキーマは、](advanced-hunting-schema-tables.md) さまざまなテーブルに広範なデバイス情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="27713-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="27713-125">たとえば [、DeviceInfo テーブルは、](advanced-hunting-deviceinfo-table.md) 定期的に集計されるイベント データに基づいて、包括的なデバイス情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="27713-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="27713-126">このクエリでは、このテーブルを使用して、潜在的に侵害されたユーザー ( ) が任意のデバイスにログオンしたのか確認し、それらのデバイスでトリガーされたアラート `DeviceInfo` `<account-name>` を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="27713-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="27713-127">このクエリは `kind=inner` 、内部結合 [を指定するために](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)使用します。これにより、 の左側の値の重複排除が防止されます `DeviceId` 。</span><span class="sxs-lookup"><span data-stu-id="27713-127">This query uses `kind=inner` to specify an [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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


### <a name="get-file-event-information"></a><span data-ttu-id="27713-128">ファイル イベント情報の取得</span><span class="sxs-lookup"><span data-stu-id="27713-128">Get file event information</span></span>

<span data-ttu-id="27713-129">ファイル関連イベントに関する情報を取得するには、次のクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="27713-129">Use the following query to get information on file related events.</span></span> 

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


### <a name="get-network-event-information"></a><span data-ttu-id="27713-130">ネットワーク イベント情報の取得</span><span class="sxs-lookup"><span data-stu-id="27713-130">Get network event information</span></span>

<span data-ttu-id="27713-131">ネットワーク関連のイベントに関する情報を取得するには、次のクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="27713-131">Use the following query to get information on network related events.</span></span>

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

### <a name="get-device-agent-version-information"></a><span data-ttu-id="27713-132">デバイス エージェントのバージョン情報の取得</span><span class="sxs-lookup"><span data-stu-id="27713-132">Get device agent version information</span></span>

<span data-ttu-id="27713-133">次のクエリを使用して、デバイスで実行されているエージェントのバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="27713-133">Use the following query to get the version of the agent running on a device.</span></span>

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


### <a name="example-query-for-macos-devices"></a><span data-ttu-id="27713-134">macOS デバイスのクエリの例</span><span class="sxs-lookup"><span data-stu-id="27713-134">Example query for macOS devices</span></span>

<span data-ttu-id="27713-135">次のクエリ例を使用して、Catalina より古いバージョンの macOS を実行しているすべてのデバイスを確認します。</span><span class="sxs-lookup"><span data-stu-id="27713-135">Use the following example query to see all devices running macOS with a version older than Catalina.</span></span>

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

### <a name="get-device-status-info"></a><span data-ttu-id="27713-136">デバイスの状態情報を取得する</span><span class="sxs-lookup"><span data-stu-id="27713-136">Get device status info</span></span>

<span data-ttu-id="27713-137">デバイスの状態を取得するには、次のクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="27713-137">Use the following query to get status of a device.</span></span> <span data-ttu-id="27713-138">次の例では、クエリはデバイスがオンボードされているのか確認します。</span><span class="sxs-lookup"><span data-stu-id="27713-138">In the following example, the query checks to see if the device is onboarded.</span></span>

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


## <a name="hunting-scenarios"></a><span data-ttu-id="27713-139">捜索のシナリオ</span><span class="sxs-lookup"><span data-stu-id="27713-139">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="27713-140">正常に送信されていないメールを受信したユーザーのログオン アクティビティを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="27713-140">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="27713-141">[ゼロ時間自動削除 (ZAP) は](../office-365-security/zero-hour-auto-purge.md) 、悪意のあるメールを受信した後にアドレス指定します。</span><span class="sxs-lookup"><span data-stu-id="27713-141">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="27713-142">ZAP が失敗した場合、悪意のあるコードが最終的にデバイスで実行され、アカウントが侵害されたままになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27713-142">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="27713-143">このクエリは、ZAP によって正常にアドレス指定されていない電子メールの受信者によって行われたログオン アクティビティをチェックします。</span><span class="sxs-lookup"><span data-stu-id="27713-143">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="27713-144">資格情報の盗難の対象となるドメイン アカウントによるログオン試行の取得</span><span class="sxs-lookup"><span data-stu-id="27713-144">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="27713-145">このクエリは、最初にテーブル内のすべての資格情報アクセス通知を識別 `AlertInfo` します。</span><span class="sxs-lookup"><span data-stu-id="27713-145">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="27713-146">次に、テーブルを結合または結合し、対象となるアカウントの名前と、ドメインに参加しているアカウントのフィルターのみを `AlertEvidence` 解析します。</span><span class="sxs-lookup"><span data-stu-id="27713-146">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="27713-147">最後に、テーブルをチェックして、ドメインに参加している対象アカウントによってすべてのログオン `IdentityLogonEvents` アクティビティを取得します。</span><span class="sxs-lookup"><span data-stu-id="27713-147">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="27713-148">既知の悪意のある送信者からのファイルがデバイスに存在するかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="27713-148">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="27713-149">悪意のあるファイル () を送信する電子メール アドレスがわかっている場合は、このクエリを実行して、この送信者のファイルがデバイス `MaliciousSender@example.com` に存在するかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="27713-149">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="27713-150">たとえば、このクエリを使用して、マルウェア配布キャンペーンの影響を受けるデバイスを特定できます。</span><span class="sxs-lookup"><span data-stu-id="27713-150">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="27713-151">悪意のあるメール受信後のログオン試行を確認する</span><span class="sxs-lookup"><span data-stu-id="27713-151">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="27713-152">このクエリは、既知の悪意のあるメールの受信後 30 分以内に受信者が実行したログオン試行のうち、最新のもの 10 件を見つけます。</span><span class="sxs-lookup"><span data-stu-id="27713-152">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="27713-153">このクエリを使用することで、メールの受信者のアカウントが侵害されたかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="27713-153">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="27713-154">既知の悪意のある送信者からのメール受信後の PowerShell アクティビティを確認する</span><span class="sxs-lookup"><span data-stu-id="27713-154">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="27713-155">悪意のあるメールには多くの場合、PowerShell コマンドを実行して追加のペイロードを配信するドキュメントや特別に細工した添付ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="27713-155">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="27713-156">既知の悪意のある送信者 ( ) からのメールを認識している場合は、このクエリを使用して、送信者から電子メールを受信した後 30 分以内に発生した PowerShell アクティビティを一覧表示および確認 `MaliciousSender@example.com` できます。</span><span class="sxs-lookup"><span data-stu-id="27713-156">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="27713-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="27713-157">Related topics</span></span>
- [<span data-ttu-id="27713-158">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="27713-158">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="27713-159">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="27713-159">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="27713-160">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="27713-160">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="27713-161">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="27713-161">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="27713-162">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="27713-162">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="27713-163">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="27713-163">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
