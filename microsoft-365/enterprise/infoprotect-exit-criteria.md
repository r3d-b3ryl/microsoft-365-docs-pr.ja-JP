---
title: 情報保護インフラストラクチャの終了条件
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 情報保護ベースのサービスとインフラストラクチャの条件を調べ、構成が Microsoft 365 Enterprise の要件を満たしていることを確認します。
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869527"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="8f8d2-103">情報保護インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="8f8d2-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="8f8d2-104">基礎インフラストラクチャを完了する前に、情報保護インフラストラクチャが次の条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8f8d2-104">Before you are complete with your foundation infrastructure, make sure that your information protection infrastructure meets these conditions.</span></span> 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="8f8d2-105">必須: 組織のセキュリティおよび情報の保護レベルが定義されている</span><span class="sxs-lookup"><span data-stu-id="8f8d2-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="8f8d2-p101">組織に必要なセキュリティ レベルを計画し、決定している。これらのレベルでは、機密情報とそれに伴う必須データ セキュリティの最小限のセキュリティ レベルと強化するための追加のレベルが定義されます。</span><span class="sxs-lookup"><span data-stu-id="8f8d2-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="8f8d2-108">少なくとも 3 種類のセキュリティ レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="8f8d2-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="8f8d2-109">基準</span><span class="sxs-lookup"><span data-stu-id="8f8d2-109">Baseline</span></span>
- <span data-ttu-id="8f8d2-110">機密</span><span class="sxs-lookup"><span data-stu-id="8f8d2-110">Sensitive</span></span>
- <span data-ttu-id="8f8d2-111">高度な規制</span><span class="sxs-lookup"><span data-stu-id="8f8d2-111">Highly regulated</span></span>

<span data-ttu-id="8f8d2-112">必要に応じて、[手順 1](infoprotect-define-sec-infoprotect-levels.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8f8d2-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a><span data-ttu-id="8f8d2-113">必須: Office 365 のセキュリティ強化が構成されている</span><span class="sxs-lookup"><span data-stu-id="8f8d2-113">Required: Increased security for Office 365 is configured</span></span>

<span data-ttu-id="8f8d2-114">「[セキュリティ強化のために Office 365 テナントを構成する](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)」の内容に基づいて、セキュリティの強化のために次の設定を構成している。</span><span class="sxs-lookup"><span data-stu-id="8f8d2-114">You've configured the following settings for increased security based on the information in [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):</span></span>

- <span data-ttu-id="8f8d2-115">Office 365 セキュリティ/コンプライアンス センターの脅威管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="8f8d2-115">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="8f8d2-116">その他の Exchange Online テナント レベルの設定</span><span class="sxs-lookup"><span data-stu-id="8f8d2-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="8f8d2-117">SharePoint 管理センターでのテナント レベルでの共有ポリシー</span><span class="sxs-lookup"><span data-stu-id="8f8d2-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="8f8d2-118">Azure Active Directory の設定</span><span class="sxs-lookup"><span data-stu-id="8f8d2-118">Settings in Azure Active Directory</span></span>

<span data-ttu-id="8f8d2-119">[Office 365 Advanced Threat Protection (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton) も有効にしている。</span><span class="sxs-lookup"><span data-stu-id="8f8d2-119">You've also [enabled Office 365 Advanced Threat Protection (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="8f8d2-120">必要に応じて、[手順 3](infoprotect-configure-increased-security-office-365.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8f8d2-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="8f8d2-121">省略可能: 環境全体で分類方法が構成されている</span><span class="sxs-lookup"><span data-stu-id="8f8d2-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="8f8d2-122">法務/コンプライアンス チームと協力して、次のような、組織のデータの適切な分類方法とラベリング方法を策定している。</span><span class="sxs-lookup"><span data-stu-id="8f8d2-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data, which include the following:</span></span>

- <span data-ttu-id="8f8d2-123">機密性の高いデータ タイプ</span><span class="sxs-lookup"><span data-stu-id="8f8d2-123">Sensitive data types</span></span>
- <span data-ttu-id="8f8d2-124">Office 365 のラベル</span><span class="sxs-lookup"><span data-stu-id="8f8d2-124">Office 365 labels</span></span>
- <span data-ttu-id="8f8d2-125">Azure Information Protection のラベル</span><span class="sxs-lookup"><span data-stu-id="8f8d2-125">Azure Information Protection labels</span></span>

<span data-ttu-id="8f8d2-126">必要に応じて、[手順 2](infoprotect-configure-classification.md) がこの必須条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8f8d2-126">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="8f8d2-127">省略可能: Office 365 での特権アクセス管理の構成。</span><span class="sxs-lookup"><span data-stu-id="8f8d2-127">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="8f8d2-p102">お客様は、トピック「[Office 365 での特権アクセス管理の構成](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)」での説明を使用して、Office 365 をお使いの組織で特権アクセスの有効化と特権アクセスポリシーの作成を行いました。こうしたポリシーを構成し、機密データへのアクセスまたは重要な構成設定へのアクセスのためにジャスト イン タイムアクセスを有効化しました。</span><span class="sxs-lookup"><span data-stu-id="8f8d2-p102">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access  and create one or more privileged access policies in your Office 365 organization. You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="8f8d2-130">必要に応じて、[手順 4](infoprotect-configure-privileged-access-management.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8f8d2-130">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="next-step"></a><span data-ttu-id="8f8d2-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="8f8d2-131">Next Step</span></span>

<span data-ttu-id="8f8d2-132">これで、Microsoft Teams や Exchange Online など、Microsoft 365 Enterprise の基礎インフラストラクチャで稼働する[ワークロードとシナリオ](deploy-workloads.md)を展開する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="8f8d2-132">You're now ready to deploy [workloads and scenarios](deploy-workloads.md), such as Microsoft Teams and Exchange Online, that run on top of your Microsoft 365 Enterprise foundation infrastructure.</span></span>
