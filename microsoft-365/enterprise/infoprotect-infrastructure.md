---
title: 'フェーズ 6: 情報保護'
f1.keywords:
- NOCSH
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
description: Microsoft 365 Enterprise の情報保護インフラストラクチャの展開手順。
ms.openlocfilehash: 0e6fdf1a9c63200bfb57fc9f833515553c1609f4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631623"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="52ee7-103">フェーズ 6: 情報保護</span><span class="sxs-lookup"><span data-stu-id="52ee7-103">Phase 6: Information protection</span></span>

![フェーズ 6: 情報保護](../media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="52ee7-p101">情報保護は、機密情報を送信、保存、処理する方法を定義するポリシーとテクノロジの集合です。フェーズ 6 では、クラウドベースのワークロードとシナリオのデータの保護に役立つ Microsoft 365 Enterprise の情報保護の設定と機能について、順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="52ee7-p101">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information. In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads and scenarios.</span></span>

>[!Note]
><span data-ttu-id="52ee7-107">既に情報保護を展開している場合は、このフェーズの[終了条件](infoprotect-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="52ee7-107">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="52ee7-108">Microsoft 365 Enterprise の情報保護インフラストラクチャを計画および展開する</span><span class="sxs-lookup"><span data-stu-id="52ee7-108">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="52ee7-p102">法務/コンプライアンス チームと連携して、組織がコンプライアンス標準 (HIPPA、CJIS、GDPR など) に準拠する必要があるかどうかを判別することが重要です。また、セキュリティ グループと連携して、組織の情報保護の目標、およびセキュリティを強化する必要がある部門やグループの情報保護目標を決定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="52ee7-p102">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR. You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="52ee7-111">次に、以下の手順に従って Microsoft 365 Enterprise の情報保護を形成します。</span><span class="sxs-lookup"><span data-stu-id="52ee7-111">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![手順 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="52ee7-113">セキュリティおよび情報保護のレベルを定義する</span><span class="sxs-lookup"><span data-stu-id="52ee7-113">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![手順 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="52ee7-115">環境のデータ分類を構成する</span><span class="sxs-lookup"><span data-stu-id="52ee7-115">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![手順 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="52ee7-117">Microsoft 365 のセキュリティ強化を構成する</span><span class="sxs-lookup"><span data-stu-id="52ee7-117">Configure increased security for Microsoft 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![手順 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="52ee7-119">Windows 情報保護を構成する</span><span class="sxs-lookup"><span data-stu-id="52ee7-119">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|
|![手順 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="52ee7-121">データ損失防止 (DLP) を構成する</span><span class="sxs-lookup"><span data-stu-id="52ee7-121">Configure Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|
|![手順 6](../media/stepnumbers/Step6.png)|[<span data-ttu-id="52ee7-123">電子メールの暗号化を構成する</span><span class="sxs-lookup"><span data-stu-id="52ee7-123">Configure email encryption</span></span>](infoprotect-email-encryption.md)|
|![手順 7](../media/stepnumbers/Step7.png)|[<span data-ttu-id="52ee7-125">Office 365 の特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="52ee7-125">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
|||

<span data-ttu-id="52ee7-126">上記の手順が完了したら、このフェーズの[終了条件](infoprotect-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="52ee7-126">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="52ee7-127">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="52ee7-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="52ee7-128">Microsoft の IT エキスパートが [Azure Information Protection を使用してデータを保護](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="52ee7-128">Learn how IT experts at Microsoft use [Azure Information Protection and safeguard data](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="52ee7-129">Contoso 社での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="52ee7-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="52ee7-130">架空の典型的な多国籍企業である Contoso Corporation での、Microsoft 365 クラウド サービスによる[情報保護の実装](contoso-info-protect.md)方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="52ee7-130">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![Contoso 社](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="52ee7-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="52ee7-132">Next step</span></span>

|||
|:-------|:-----|
|![手順 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="52ee7-134">セキュリティおよび情報保護のレベルを定義する</span><span class="sxs-lookup"><span data-stu-id="52ee7-134">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

