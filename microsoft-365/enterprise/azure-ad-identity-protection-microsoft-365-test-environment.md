---
title: Microsoft 365 Enterprise テスト環境の Azure AD Id 保護
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Azure AD Identity Protection を構成し、Microsoft 365 Enterprise テスト環境で現在のアカウントを分析します。
ms.openlocfilehash: c0d364eaef9cfd37531d9f9e1803db66739a7984
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802102"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="36530-103">Microsoft 365 Enterprise テスト環境の Azure AD Id 保護</span><span class="sxs-lookup"><span data-stu-id="36530-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="36530-104">*このテストラボ ガイドは、Microsoft 365 Enterprise テスト環境にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="36530-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="36530-105">Azure Active Directory (Azure AD) Id 保護を使用すると、組織の id に影響を及ぼす可能性のある脆弱性を検出し、自動化された応答を構成し、インシデントを調査できます。</span><span class="sxs-lookup"><span data-stu-id="36530-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="36530-106">この記事では、Azure AD Identity Protection を使用して、テスト環境アカウントの分析を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="36530-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="36530-107">Microsoft 365 エンタープライズテスト環境で Azure AD Id 保護をセットアップするには、次の2つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="36530-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="36530-108">Microsoft 365 Enterprise のテスト環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="36530-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="36530-109">Azure AD Identity Protection を使用します。</span><span class="sxs-lookup"><span data-stu-id="36530-109">Use Azure AD Identity Protection.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="36530-111">[ここ](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="36530-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="36530-112">フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="36530-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="36530-113">最小限の要件で Azure AD Identity Protection を軽量な方法でテストする場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="36530-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="36530-114">シミュレートされたエンタープライズで Azure AD Identity Protection をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="36530-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="36530-115">Azure AD Identity Protection のテストでは、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="36530-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="36530-116">これは、Azure AD Id 保護をテストして、一般的な組織を表す環境で試してみることができるようにするためのオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="36530-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="36530-117">フェーズ 2: Azure AD Identity Protection を使用する</span><span class="sxs-lookup"><span data-stu-id="36530-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="36530-118">ブラウザーのプライベートインスタンスを開き、Microsoft 365 Enterprise テスト環境のグローバル管理[https://portal.azure.com](https://portal.azure.com)者アカウントを使用して Azure portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="36530-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="36530-119">Azure portal で、検索ボックスに「 **id 保護**」と入力し、[ **Azure AD id 保護**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36530-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="36530-120">[ **Identity Protection-概要**] ブレードで、各レポートをクリックして、報告されているものを確認します。</span><span class="sxs-lookup"><span data-stu-id="36530-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="36530-121">[**通知**] の下で、[**リスクが検出された通知のユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36530-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="36530-122">[**リスクが検出されたユーザーのアラート**] ウィンドウで、[**中**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36530-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="36530-123">**メールが次のユーザーに送信さ**れる場合は、[**含める**] をクリックして、グローバル管理者アカウントが選択されているメンバーの一覧に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36530-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="36530-124">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36530-124">Click **Save**.</span></span>

<span data-ttu-id="36530-125">[**保護**] の下にあるさまざまなポリシーをクリックして、それらを構成する方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="36530-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="36530-126">ポリシーを作成してアクティブにした場合は、アクセスがブロックされている範囲を超えていないか、またはグローバル管理者であってもサインインできないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="36530-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="36530-127">テストと実験の詳細については、「[リスクイベントをシミュレート](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36530-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="36530-128">Azure AD Id 保護を運用環境に展開するための情報とリンクについては、Id フェーズの「[資格情報が侵害](identity-secure-user-sign-ins.md#identity-ident-prot)されないように保護する」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36530-128">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="36530-129">次の手順</span><span class="sxs-lookup"><span data-stu-id="36530-129">Next step</span></span>

<span data-ttu-id="36530-130">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="36530-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="36530-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="36530-131">See also</span></span>

[<span data-ttu-id="36530-132">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="36530-132">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="36530-133">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="36530-133">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="36530-134">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="36530-134">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="36530-135">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="36530-135">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
