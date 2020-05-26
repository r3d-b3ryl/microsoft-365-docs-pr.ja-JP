---
title: メッセージの暗号化を使用して組織の機密情報の種類のポリシーを作成する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: Office 365 メッセージの暗号化を使用して、組織の機密情報の種類のポリシーを作成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: da459ab5e92592f86bc32d7dd9d648de24b9a3ed
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352070"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a><span data-ttu-id="a0352-103">メッセージの暗号化を使用して組織の機密情報の種類のポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="a0352-103">Create a sensitive information type policy for your organization using Message Encryption</span></span>

<span data-ttu-id="a0352-104">Exchange メールフロールールまたはデータ損失防止 (DLP) のいずれかを使用して、Office 365 メッセージの暗号化を使用して機密情報の種類のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a0352-104">You can use either Exchange mail flow rules or Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="a0352-105">Exchange メールフロールールを作成するには、Exchange 管理センター (EAC) または PowerShell のどちらかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a0352-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="a0352-106">EAC でメールフロールールを使用してポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="a0352-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="a0352-107">Exchange 管理センター (EAC) にサインインし、[**メールフロー**] [ルール] に移動し  >  **Rules**ます。</span><span class="sxs-lookup"><span data-stu-id="a0352-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="a0352-108">[ルール] ページで、Office 365 メッセージの暗号化を適用するルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0352-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="a0352-109">特定のキーワードの存在や、メッセージまたは添付ファイル内の機密情報の種類などの条件に基づいてルールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a0352-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="a0352-110">PowerShell でメールフロールールを使用してポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="a0352-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="a0352-111">組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="a0352-111">Use a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="a0352-112">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0352-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="a0352-113">New-transportrule コマンドレットと新しいコマンドレットを使用して、ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0352-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

## <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="a0352-114">PowerShell を使用して作成されたメールフロールールの例</span><span class="sxs-lookup"><span data-stu-id="a0352-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="a0352-115">メールまたは添付ファイルに次の機密情報の種類が含まれている場合は、PowerShell で次のコマンドを実行して、組織外から送信されたメールを*暗号化専用*ポリシーで自動的に暗号化する Exchange メールフロールールを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0352-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="a0352-116">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="a0352-116">ABA routing number</span></span>
- <span data-ttu-id="a0352-117">クレジットカード番号</span><span class="sxs-lookup"><span data-stu-id="a0352-117">Credit card Number</span></span>
- <span data-ttu-id="a0352-118">医薬品執行機関 (DEA) 番号</span><span class="sxs-lookup"><span data-stu-id="a0352-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="a0352-119">米国/英国</span><span class="sxs-lookup"><span data-stu-id="a0352-119">U.S. / U.K.</span></span> <span data-ttu-id="a0352-120">passport number</span><span class="sxs-lookup"><span data-stu-id="a0352-120">passport number</span></span>
- <span data-ttu-id="a0352-121">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="a0352-121">U.S. bank account number</span></span>
- <span data-ttu-id="a0352-122">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="a0352-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="a0352-123">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="a0352-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="a0352-124">詳細については、「 [new-transportrule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule?view=exchange-ps) [」を参照して](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration?view=exchange-ps)ください。</span><span class="sxs-lookup"><span data-stu-id="a0352-124">For more information, see [Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration?view=exchange-ps) and [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule?view=exchange-ps).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="a0352-125">受信者が添付ファイルにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="a0352-125">How recipients access attachments</span></span>

<span data-ttu-id="a0352-126">Microsoft がメッセージを暗号化すると、受信者は暗号化された電子メールにアクセスして開くときに、添付ファイルに無制限でアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="a0352-126">After Microsoft encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="a0352-127">この変更を準備するには</span><span class="sxs-lookup"><span data-stu-id="a0352-127">To prepare for this change</span></span>

<span data-ttu-id="a0352-128">この変更に関して組織内のユーザーを準備するために、適用可能なエンドユーザードキュメントおよびトレーニング資料を更新することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a0352-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="a0352-129">必要に応じて、これらの Office 365 メッセージ暗号化リソースをユーザーと共有します。</span><span class="sxs-lookup"><span data-stu-id="a0352-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="a0352-130">Outlook for PC で暗号化されたメッセージを送信、表示、および返信する</span><span class="sxs-lookup"><span data-stu-id="a0352-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="a0352-131">Microsoft 365 Essentials Video: Office メッセージの暗号化</span><span class="sxs-lookup"><span data-stu-id="a0352-131">Microsoft 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="a0352-132">監査ログでのこれらの変更の表示</span><span class="sxs-lookup"><span data-stu-id="a0352-132">View these changes in the audit log</span></span>

<span data-ttu-id="a0352-133">Microsoft 365 は、このアクティビティを監査して、管理者が使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0352-133">Microsoft 365 audits this activity and makes it available to administrators.</span></span> <span data-ttu-id="a0352-134">この操作は ' New-transportrule ' であり、セキュリティ & コンプライアンスセンターでの監査ログの検索からのサンプルの監査エントリのスニペットは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a0352-134">The operation is 'New-TransportRule' and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="a0352-135">機密情報の種類のポリシーを無効にする、またはカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="a0352-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="a0352-136">Exchange メールフロールールを作成したら、exchange 管理センター (EAC) の**メールフロー**ルールに移動し、[送信機密メールを暗号化する (標準のルール)] ルールを無効にして、[ルールを無効にしたり、編集](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)したりすることができ  >  **Rules** *Encrypt outbound sensitive emails (out of box rule)* ます。</span><span class="sxs-lookup"><span data-stu-id="a0352-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule "*Encrypt outbound sensitive emails (out of box rule)*".</span></span>
