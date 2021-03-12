---
title: 365 Message Encryption を使用して機密情報Officeポリシーを作成する
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
description: 365 Message Encryption を使用して組織の機密情報の種類ポリシーをOfficeする方法について学習します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 22aec87b149c58b2537f6921fb7c37552ef72f98
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741380"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a><span data-ttu-id="3eba3-103">メッセージ暗号化を使用して組織の機密情報の種類ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="3eba3-103">Create a sensitive information type policy for your organization using Message Encryption</span></span>

<span data-ttu-id="3eba3-104">Exchange メール フロー ルールまたはデータ損失防止 (DLP) のいずれかを使用して、365 メッセージ暗号化を使用して機密情報の種類Office作成できます。</span><span class="sxs-lookup"><span data-stu-id="3eba3-104">You can use either Exchange mail flow rules or Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="3eba3-105">Exchange メール フロー ルールを作成するには、Exchange 管理センター (EAC) または PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3eba3-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="3eba3-106">EAC でメール フロー ルールを使用してポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="3eba3-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="3eba3-107">Exchange 管理センター (EAC) にサインインし、[メール フロールール]**に移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="3eba3-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="3eba3-108">[ルール] ページで、365 メッセージ暗号化にOfficeルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="3eba3-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="3eba3-109">メッセージまたは添付ファイルに特定のキーワードや機密情報の種類が存在するなどの条件に基づいてルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3eba3-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="3eba3-110">PowerShell でメール フロー ルールを使用してポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="3eba3-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="3eba3-111">組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="3eba3-111">Use a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="3eba3-112">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3eba3-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="3eba3-113">ポリシーを作成Set-IRMConfiguration、New-TransportRuleコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3eba3-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

## <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="3eba3-114">PowerShell で作成されたメール フロー ルールの例</span><span class="sxs-lookup"><span data-stu-id="3eba3-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="3eba3-115">PowerShell で次のコマンドを実行して Exchange メール フロー ルールを作成し、電子メールまたは添付ファイルに次の機密情報の種類が含まれている場合、組織外に送信された電子メールを暗号化専用オプションで自動的に暗号化します。</span><span class="sxs-lookup"><span data-stu-id="3eba3-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the encrypt-only option if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="3eba3-116">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="3eba3-116">ABA routing number</span></span>
- <span data-ttu-id="3eba3-117">クレジット カード番号</span><span class="sxs-lookup"><span data-stu-id="3eba3-117">Credit card Number</span></span>
- <span data-ttu-id="3eba3-118">麻薬取締局 (DEA) 番号</span><span class="sxs-lookup"><span data-stu-id="3eba3-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="3eba3-119">米国/英国</span><span class="sxs-lookup"><span data-stu-id="3eba3-119">U.S. / U.K.</span></span> <span data-ttu-id="3eba3-120">passport number</span><span class="sxs-lookup"><span data-stu-id="3eba3-120">passport number</span></span>
- <span data-ttu-id="3eba3-121">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="3eba3-121">U.S. bank account number</span></span>
- <span data-ttu-id="3eba3-122">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="3eba3-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="3eba3-123">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="3eba3-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="3eba3-124">詳細については [、「Set-IRMConfiguration」](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration) および [「New-TransportRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)。</span><span class="sxs-lookup"><span data-stu-id="3eba3-124">For more information, see [Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration) and [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="3eba3-125">受信者が添付ファイルにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="3eba3-125">How recipients access attachments</span></span>

<span data-ttu-id="3eba3-126">Microsoft がメッセージを暗号化すると、受信者は暗号化された電子メールにアクセスして開く際に、添付ファイルに無制限にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3eba3-126">After Microsoft encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="3eba3-127">この変更の準備をするには</span><span class="sxs-lookup"><span data-stu-id="3eba3-127">To prepare for this change</span></span>

<span data-ttu-id="3eba3-128">該当するエンドユーザー向けドキュメントとトレーニング資料を更新して、組織のユーザーをこの変更に備える必要があります。</span><span class="sxs-lookup"><span data-stu-id="3eba3-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="3eba3-129">必要に応Office 365 Message Encryption リソースをユーザーと共有します。</span><span class="sxs-lookup"><span data-stu-id="3eba3-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="3eba3-130">Outlook for PC で暗号化されたメッセージを送信、表示、返信する</span><span class="sxs-lookup"><span data-stu-id="3eba3-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="3eba3-131">Microsoft 365 Essentials ビデオ: Office暗号化</span><span class="sxs-lookup"><span data-stu-id="3eba3-131">Microsoft 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="3eba3-132">監査ログでこれらの変更を表示する</span><span class="sxs-lookup"><span data-stu-id="3eba3-132">View these changes in the audit log</span></span>

<span data-ttu-id="3eba3-133">Microsoft 365 は、このアクティビティを監査し、管理者が使用できます。</span><span class="sxs-lookup"><span data-stu-id="3eba3-133">Microsoft 365 audits this activity and makes it available to administrators.</span></span> <span data-ttu-id="3eba3-134">操作は 'New-TransportRule' であり、コンプライアンス センターのセキュリティ監査ログ検索のサンプル監査エントリ&以下に示します。</span><span class="sxs-lookup"><span data-stu-id="3eba3-134">The operation is 'New-TransportRule' and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="3eba3-135">機密情報の種類ポリシーを無効またはカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="3eba3-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="3eba3-136">Exchange メール フロー ルールを作成したら、Exchange [](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)管理センター   >   (EAC) の [メール フロー ルール] に移動してルールを無効にし、[送信機密メールの暗号化 (アウトボックス ルール) ] を無効にすることで、ルールを無効または *無効* にできます。</span><span class="sxs-lookup"><span data-stu-id="3eba3-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule "*Encrypt outbound sensitive emails (out of box rule)*".</span></span>
