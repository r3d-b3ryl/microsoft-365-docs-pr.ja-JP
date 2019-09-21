---
title: 情報保護インフラストラクチャの終了条件
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 情報保護ベースのサービスとインフラストラクチャの条件を調べ、構成が Microsoft 365 Enterprise の要件を満たしていることを確認します。
ms.openlocfilehash: 02e972a80d4b42ae66193bbbc55d0f1e63be5ba6
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047240"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="96f8b-103">情報保護インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="96f8b-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="96f8b-104">情報保護インフラストラクチャが次の必須基準を満たすとともに、オプションの基準も考慮されていることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="96f8b-104">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="96f8b-105">必須: 組織のセキュリティおよび情報の保護レベルが定義されている</span><span class="sxs-lookup"><span data-stu-id="96f8b-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="96f8b-p101">組織に必要なセキュリティ レベルを計画し、決定している。これらのレベルでは、機密情報とそれに伴う必須データ セキュリティの最小限のセキュリティ レベルと強化するための追加のレベルが定義されます。</span><span class="sxs-lookup"><span data-stu-id="96f8b-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="96f8b-108">少なくとも 3 種類のセキュリティ レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="96f8b-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="96f8b-109">基準</span><span class="sxs-lookup"><span data-stu-id="96f8b-109">Baseline</span></span>
- <span data-ttu-id="96f8b-110">機密</span><span class="sxs-lookup"><span data-stu-id="96f8b-110">Sensitive</span></span>
- <span data-ttu-id="96f8b-111">高度な規制</span><span class="sxs-lookup"><span data-stu-id="96f8b-111">Highly regulated</span></span>

<span data-ttu-id="96f8b-112">必要に応じて、[手順 1](infoprotect-define-sec-infoprotect-levels.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="96f8b-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="96f8b-113">必須: Microsoft 365 のセキュリティ強化が構成済み</span><span class="sxs-lookup"><span data-stu-id="96f8b-113">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="96f8b-114">次の [Office 365 セキュリティの強化](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)の設定が構成されています:</span><span class="sxs-lookup"><span data-stu-id="96f8b-114">You've configured the following settings for [Office 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="96f8b-115">Microsoft 365 セキュリティセンターの脅威管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="96f8b-115">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="96f8b-116">その他の Exchange Online テナント レベルの設定</span><span class="sxs-lookup"><span data-stu-id="96f8b-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="96f8b-117">SharePoint Online 管理センターでのテナント全体の共有ポリシー</span><span class="sxs-lookup"><span data-stu-id="96f8b-117">Tenant-wide sharing policies in SharePoint Online admin center</span></span>
- <span data-ttu-id="96f8b-118">Azure Active Directory (Azure AD) の設定</span><span class="sxs-lookup"><span data-stu-id="96f8b-118">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="96f8b-119">[SharePoint、OneDrive、Microsoft Teams 用の Office 365 Advanced Threat Protection (ATP) を有効にする](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)ことも行いました。</span><span class="sxs-lookup"><span data-stu-id="96f8b-119">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="96f8b-120">必要に応じて、[手順 3](infoprotect-configure-increased-security-office-365.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="96f8b-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="96f8b-121">省略可能: 環境全体で分類方法が構成されている</span><span class="sxs-lookup"><span data-stu-id="96f8b-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="96f8b-122">法務/コンプライアンス チームと協力して、組織のデータのガバナンスとセキュリティ ポリシーの適切な分類方法とラベリング方法を策定しています。</span><span class="sxs-lookup"><span data-stu-id="96f8b-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data governance and security policies.</span></span> 

<span data-ttu-id="96f8b-123">これらのポリシーは、次の構成および展開に対応しています: </span><span class="sxs-lookup"><span data-stu-id="96f8b-123">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="96f8b-124">機密性の高いデータ タイプ</span><span class="sxs-lookup"><span data-stu-id="96f8b-124">Sensitive data types</span></span>
- <span data-ttu-id="96f8b-125">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="96f8b-125">Retention labels</span></span>
- <span data-ttu-id="96f8b-126">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="96f8b-126">Sensitivity labels</span></span>
- <span data-ttu-id="96f8b-127">Azure Information Protection のラベル</span><span class="sxs-lookup"><span data-stu-id="96f8b-127">Azure Information Protection labels</span></span>

<span data-ttu-id="96f8b-128">必要に応じて、[手順 2](infoprotect-configure-classification.md) がこの必須条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="96f8b-128">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="96f8b-129">オプション: 環境全体に Windows Information Protection が展開されている</span><span class="sxs-lookup"><span data-stu-id="96f8b-129">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="96f8b-130">登録されている Windows 10 Enterprise デバイスには、次の項目を定義する Intune ポリシーが展開および適用されています。</span><span class="sxs-lookup"><span data-stu-id="96f8b-130">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="96f8b-131">保護するアプリ。</span><span class="sxs-lookup"><span data-stu-id="96f8b-131">Which apps to protect.</span></span>
- <span data-ttu-id="96f8b-132">保護レベル。</span><span class="sxs-lookup"><span data-stu-id="96f8b-132">The level of protection.</span></span>
- <span data-ttu-id="96f8b-133">保護の範囲。</span><span class="sxs-lookup"><span data-stu-id="96f8b-133">Where the protection extends.</span></span>

<span data-ttu-id="96f8b-134">必要に応じて、[手順 4](infoprotect-deploy-windows-information-protection.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="96f8b-134">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="96f8b-135">オプション: Office 365 データ損失防止 (DLP) が展開されている</span><span class="sxs-lookup"><span data-stu-id="96f8b-135">Optional: Office 365 Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="96f8b-136">顧客やその他の種類の非公開データを保護し、業界や地域の規制や要件を順守するために組織が必要とする一連の DLP ポリシー (場所や規則、条件やアクションを含む) を分析し、テストしてから展開しました。</span><span class="sxs-lookup"><span data-stu-id="96f8b-136">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="96f8b-137">データ コンプライアンスとセキュリティ スタッフは、Office 365 のセキュリティとコンプライアンスのダッシュボードを使用して DLP インシデントを監視しています。</span><span class="sxs-lookup"><span data-stu-id="96f8b-137">Your data compliance and security staff are using the Office 365 Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="96f8b-138">必要に応じて、[手順 5](infoprotect-data-loss-prevention.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="96f8b-138">If needed, [Step 5](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a><span data-ttu-id="96f8b-139">省略可能: 電子メールの暗号化が構成されている</span><span class="sxs-lookup"><span data-stu-id="96f8b-139">Optional: Email encryption is configured</span></span>

<span data-ttu-id="96f8b-140">必要に応じて、組織に次の電子メールの暗号化を構成しています。</span><span class="sxs-lookup"><span data-stu-id="96f8b-140">You've configured the following email encryption as needed for your organization:</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="96f8b-141">**暗号化方法**</span><span class="sxs-lookup"><span data-stu-id="96f8b-141">**Encryption method**</span></span> | <span data-ttu-id="96f8b-142">**送信した電子メール関連**</span><span class="sxs-lookup"><span data-stu-id="96f8b-142">**For email sent**</span></span> |
| [<span data-ttu-id="96f8b-143">Office 365 Message Encryption (OME)</span><span class="sxs-lookup"><span data-stu-id="96f8b-143">Office 365 Message Encryption (OME)</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | <span data-ttu-id="96f8b-144">暗号化を使用する組織外</span><span class="sxs-lookup"><span data-stu-id="96f8b-144">Outside your organization with encryption</span></span> |
| [<span data-ttu-id="96f8b-145">Information Rights Management (IRM)</span><span class="sxs-lookup"><span data-stu-id="96f8b-145">Information Rights Management (IRM)</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | <span data-ttu-id="96f8b-146">暗号化とアクセス許可の両方とも</span><span class="sxs-lookup"><span data-stu-id="96f8b-146">With both encryption and permissions</span></span> |
| [<span data-ttu-id="96f8b-147">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span><span class="sxs-lookup"><span data-stu-id="96f8b-147">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | <span data-ttu-id="96f8b-148">公開キー暗号を使用する暗号化とデジタル署名の両方とも</span><span class="sxs-lookup"><span data-stu-id="96f8b-148">With both encryption and digital signatures using public key cryptography</span></span> |
|||

<span data-ttu-id="96f8b-149">必要な場合、[手順 6](infoprotect-email-encryption.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="96f8b-149">If needed, [Step 6](infoprotect-email-encryption.md) can help you meet this requirement.</span></span>

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="96f8b-150">省略可能: Office 365 での特権アクセス管理の構成。</span><span class="sxs-lookup"><span data-stu-id="96f8b-150">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="96f8b-151">[Office 365 での特権アクセス管理を設定する](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)トピックにある情報を使用して、特権アクセスを有効にし、組織内に 1 つまたは複数の特権アクセス ポリシーを作成しました。</span><span class="sxs-lookup"><span data-stu-id="96f8b-151">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="96f8b-152">これらのポリシーを構成して、機密データへのアクセスや重要な構成設定へのアクセスのために just-in-time アクセスが有効にされました。</span><span class="sxs-lookup"><span data-stu-id="96f8b-152">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="96f8b-153">必要に応じて、[手順 7](infoprotect-configure-privileged-access-management.md) がこの必須条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="96f8b-153">If needed, [Step 7](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="96f8b-154">結果と次の手順</span><span class="sxs-lookup"><span data-stu-id="96f8b-154">Results and next steps</span></span>

<span data-ttu-id="96f8b-155">Microsoft 365 Enterprise の情報保護インフラストラクチャでは、定義されたセキュリティ レベル、Office 365 のセキュリティ強化、機密データの種類とラベルを使用した分類、Windows 情報保護、データ損失防止、電子メールの暗号化、および特権アクセスの管理が使用されます。</span><span class="sxs-lookup"><span data-stu-id="96f8b-155">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, Windows Information Protection, Data Loss Prevention, and privileged access management.</span></span>

<span data-ttu-id="96f8b-156">Microsoft 365 Enterprise のエンド ツー エンドの展開に従っている場合、[ワークロードとシナリオ](deploy-workloads.md)で基盤インフラストラクチャのすべての機能と構成を活用することができます。</span><span class="sxs-lookup"><span data-stu-id="96f8b-156">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
