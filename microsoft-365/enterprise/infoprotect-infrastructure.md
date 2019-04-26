---
title: 'フェーズ 6: 情報保護'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/01/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise の情報保護インフラストラクチャの展開手順。
ms.openlocfilehash: 821c32eea09cde87155d0ee1ccdd81077d051d38
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287647"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="54f35-103">フェーズ 6: 情報保護</span><span class="sxs-lookup"><span data-stu-id="54f35-103">Phase 6: Information protection</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="54f35-p101">情報保護は、機密情報を送信、保存、処理する方法を定義するポリシーとテクノロジの集合です。フェーズ 6 では、クラウドベースのワークロードとシナリオのデータの保護に役立つ Microsoft 365 Enterprise の情報保護の設定と機能について、順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="54f35-p101">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information. In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads and scenarios.</span></span>

>[!Note]
><span data-ttu-id="54f35-106">既に情報保護を展開している場合は、このフェーズの[終了条件](infoprotect-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="54f35-106">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="54f35-107">Microsoft 365 Enterprise の情報保護インフラストラクチャを計画および展開する</span><span class="sxs-lookup"><span data-stu-id="54f35-107">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="54f35-p102">法務/コンプライアンス チームと連携して、組織がコンプライアンス標準 (HIPPA、CJIS、GDPR など) に準拠する必要があるかどうかを判別することが重要です。また、セキュリティ グループと連携して、組織の情報保護の目標、およびセキュリティを強化する必要がある部門やグループの情報保護目標を決定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="54f35-p102">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR. You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="54f35-110">次に、以下の手順に従って Microsoft 365 Enterprise の情報保護を形成します。</span><span class="sxs-lookup"><span data-stu-id="54f35-110">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="54f35-111">セキュリティおよび情報保護のレベルを定義する</span><span class="sxs-lookup"><span data-stu-id="54f35-111">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="54f35-112">環境のデータ分類方法を構成する</span><span class="sxs-lookup"><span data-stu-id="54f35-112">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="54f35-113">Microsoft 365 のセキュリティ強化を構成する</span><span class="sxs-lookup"><span data-stu-id="54f35-113">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="54f35-114">Office 365 の特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="54f35-114">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|


<span data-ttu-id="54f35-115">上記の手順が完了したら、このフェーズの[終了条件](infoprotect-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="54f35-115">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="54f35-116">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="54f35-116">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="54f35-117">Microsoft の IT 専門家が、Office 365 Enterprise の情報保護機能を使用して、どのように情報を保護し、サイバー攻撃から防御しているかを説明します。</span><span class="sxs-lookup"><span data-stu-id="54f35-117">Learn how IT experts at Microsoft use the information protection capabilities of Microsoft 356 Enterprise to protect information and defend against cyber attacks:</span></span>

- [<span data-ttu-id="54f35-118">Azure Information Protection でクラウドのファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="54f35-118">Protecting files in the cloud with Azure Information Protection</span></span>](https://www.microsoft.com/itshowcase/Article/Content/924/Protecting-files-in-the-cloud-with-Azure-Information-Protection)
- [<span data-ttu-id="54f35-119">Microsoft は脅威からの保護、脅威の検出、脅威への対応に脅威インテリジェンスを使用する</span><span class="sxs-lookup"><span data-stu-id="54f35-119">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="54f35-120">Microsoft の Office 365 を使用したフィッシング阻止の試み</span><span class="sxs-lookup"><span data-stu-id="54f35-120">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="54f35-121">Contoso 社での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="54f35-121">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="54f35-122">架空の典型的な多国籍企業である Contoso Corporation での、Microsoft 365 クラウド サービスによる[情報保護の実装](contoso-info-protect.md)方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="54f35-122">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="54f35-123">次の手順</span><span class="sxs-lookup"><span data-stu-id="54f35-123">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="54f35-124">セキュリティおよび情報保護のレベルを定義する</span><span class="sxs-lookup"><span data-stu-id="54f35-124">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

