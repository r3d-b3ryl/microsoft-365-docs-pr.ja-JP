---
title: Microsoft 365 for enterprise テスト環境の Azure AD Id 保護
f1.keywords:
- NOCSH
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
description: Azure AD Identity Protection を構成し、Microsoft 365 for enterprise テスト環境で現在のアカウントを分析します。
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487710"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="6a138-103">Microsoft 365 for enterprise テスト環境の Azure AD Id 保護</span><span class="sxs-lookup"><span data-stu-id="6a138-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="6a138-104">*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="6a138-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="6a138-105">Azure Active Directory (Azure AD) Id 保護を使用して、組織の id に影響する可能性のある潜在的な脆弱性を検出したり、自動化された応答を構成したり、インシデントを調査したりできます。</span><span class="sxs-lookup"><span data-stu-id="6a138-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="6a138-106">この記事では、Azure AD Identity Protection を使用して、テスト環境アカウントの分析を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a138-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="6a138-107">Microsoft 365 のエンタープライズテスト環境で Azure AD Id 保護をセットアップするには、次の2つのフェーズが必要です。</span><span class="sxs-lookup"><span data-stu-id="6a138-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="6a138-108">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="6a138-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="6a138-109">フェーズ 2: Azure AD Identity Protection を使用する</span><span class="sxs-lookup"><span data-stu-id="6a138-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="6a138-111">Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a138-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="6a138-112">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="6a138-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="6a138-113">最小要件での軽量な方法で Azure AD Identity Protection のみをテストする場合は、「 [軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="6a138-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6a138-114">シミュレートされたエンタープライズで Azure AD Identity Protection をテストする場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a138-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a138-115">Azure AD Identity Protection をテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6a138-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="6a138-116">これは、Azure AD Id 保護をテストして、一般的な組織を表す環境で試してみることができるようにするためのオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="6a138-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="6a138-117">フェーズ 2: Azure AD Identity Protection を使用する</span><span class="sxs-lookup"><span data-stu-id="6a138-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="6a138-118">ブラウザーのプライベートインスタンスを開き、 [https://portal.azure.com](https://portal.azure.com) Microsoft 365 for enterprise テスト環境のグローバル管理者アカウントを使用して、Azure portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="6a138-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="6a138-119">Azure portal で、検索ボックスに「 **id 保護** 」と入力し、[ **Azure AD id 保護**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a138-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="6a138-120">[ **Identity Protection-概要** ] ブレードで、各レポートを選択してレポートの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="6a138-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="6a138-121">[ **通知**] の下で、[ **リスクが検出されたアラート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a138-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="6a138-122">[ **リスクが検出されたユーザーのアラート** ] ウィンドウで、[ **中**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a138-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="6a138-123">**メールが次のユーザーに送信さ**れる場合は、[**含める**] を選択して、グローバル管理者アカウントが選択されているメンバーの一覧に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a138-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="6a138-124">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a138-124">Select **Save**.</span></span>

<span data-ttu-id="6a138-125">[ **保護**] で、さまざまなポリシーを選択して、それらを構成する方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="6a138-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="6a138-126">ポリシーを作成してアクティブにした場合は、すべてのユーザーのアクセスがブロックされていないこと、またはサインインできないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6a138-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="6a138-127">これを防ぐには、グローバル管理者など、特定のユーザーアカウントを除外します。</span><span class="sxs-lookup"><span data-stu-id="6a138-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="6a138-128">テストと実験の詳細については、「 [リスクイベントをシミュレート](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a138-128">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="6a138-129">次の手順</span><span class="sxs-lookup"><span data-stu-id="6a138-129">Next step</span></span>

<span data-ttu-id="6a138-130">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="6a138-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a138-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a138-131">See also</span></span>

[<span data-ttu-id="6a138-132">Identity ロードマップ</span><span class="sxs-lookup"><span data-stu-id="6a138-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="6a138-133">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="6a138-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6a138-134">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="6a138-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6a138-135">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6a138-135">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
