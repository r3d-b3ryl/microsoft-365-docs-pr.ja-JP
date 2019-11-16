---
title: Microsoft 365 Enterprise テスト環境の Azure AD Id 保護
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Azure AD Identity Protection を構成し、Microsoft 365 Enterprise テスト環境で現在のアカウントを分析します。
ms.openlocfilehash: bc98ebbdd45e06481e2d95687fb4eb8c986533a3
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673243"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="243dc-103">Microsoft 365 Enterprise テスト環境の Azure AD Id 保護</span><span class="sxs-lookup"><span data-stu-id="243dc-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="243dc-104">*このテストラボガイドは、Microsoft 365 エンタープライズテスト環境にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="243dc-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="243dc-105">Azure AD Id 保護を使用すると、組織の id に影響を及ぼす可能性のある脆弱性を検出し、自動化された応答を構成し、インシデントを調査できます。</span><span class="sxs-lookup"><span data-stu-id="243dc-105">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="243dc-106">この記事では、Azure AD Id 保護を有効にし、テスト環境アカウントの分析を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="243dc-106">This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="243dc-107">Microsoft 365 エンタープライズテスト環境で Azure AD Id 保護をセットアップするには、次の2つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="243dc-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="243dc-108">Microsoft 365 Enterprise のテスト環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="243dc-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="243dc-109">Azure AD Id 保護を有効にして使用します。</span><span class="sxs-lookup"><span data-stu-id="243dc-109">Enable and use Azure AD Identity Protection.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="243dc-111">[ここ](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="243dc-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="243dc-112">フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="243dc-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="243dc-113">最小限の要件で Azure AD Identity Protection を軽量な方法でテストする場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="243dc-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="243dc-114">シミュレートされたエンタープライズで Azure AD Identity Protection をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="243dc-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="243dc-115">Azure AD Identity Protection のテストでは、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="243dc-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="243dc-116">これは、Azure AD Id 保護をテストして、一般的な組織を表す環境で試してみることができるようにするためのオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="243dc-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="243dc-117">フェーズ 2: Azure AD Identity Protection を有効にして使用する</span><span class="sxs-lookup"><span data-stu-id="243dc-117">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="243dc-118">ブラウザーのプライベートインスタンスを開き、Microsoft 365 Enterprise テスト環境のグローバル管理[https://portal.azure.com](https://portal.azure.com)者アカウントを使用して Azure portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="243dc-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="243dc-119">Azure portal で、[**すべてのサービス > Marketplace**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="243dc-119">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="243dc-120">「 **AZURE AD Identity Protection** 」と入力し、それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="243dc-120">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="243dc-121">[スタート **] ブレードで**、[**設定**] の下の [**オン**] をクリックし、[**ダッシュボードに Pin**] をクリックしてから、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="243dc-121">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="243dc-122">Azure portal で、ダッシュボードの [ **AZURE AD Id 保護**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="243dc-122">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="243dc-123">**AZURE AD Identity Protection-概要**ブレードとダッシュボードが表示されているはずです。</span><span class="sxs-lookup"><span data-stu-id="243dc-123">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard.</span></span> <span data-ttu-id="243dc-124">[**脆弱性**] で、多要素認証が登録されていないユーザーアカウントの数が決まっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="243dc-124">Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration.</span></span> <span data-ttu-id="243dc-125">この数値は、以前に実行した Microsoft 365 Enterprise のテストラボガイドによって異なります。</span><span class="sxs-lookup"><span data-stu-id="243dc-125">This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="243dc-126">**調査**のカテゴリをクリックして、検出されたユーザーまたはイベントがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="243dc-126">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="243dc-127">テストと実験の詳細については、「[リスクイベントをシミュレート](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="243dc-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="243dc-128">Azure AD Id 保護を運用環境に展開するための情報とリンクについては、Id フェーズの「[資格情報が侵害](identity-secure-user-sign-ins.md#identity-ident-prot)されないように保護する」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="243dc-128">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="243dc-129">次の手順</span><span class="sxs-lookup"><span data-stu-id="243dc-129">Next step</span></span>

<span data-ttu-id="243dc-130">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="243dc-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="243dc-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="243dc-131">See also</span></span>

[<span data-ttu-id="243dc-132">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="243dc-132">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="243dc-133">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="243dc-133">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="243dc-134">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="243dc-134">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="243dc-135">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="243dc-135">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
