---
title: エンタープライズ AD環境向け Azure Microsoft 365 ID 保護
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
description: Azure AD Id Protection を構成し、エンタープライズ テスト環境用にMicrosoft 365アカウントを分析します。
ms.openlocfilehash: 0cb0acf3faee13676573b04178bd6b4d3d36da4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905346"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="c8b75-103">エンタープライズ AD環境向け Azure Microsoft 365 ID 保護</span><span class="sxs-lookup"><span data-stu-id="c8b75-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="c8b75-104">*このテスト ラボ ガイドは、エンタープライズ テスト環境Microsoft 365にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="c8b75-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="c8b75-105">Azure Active Directory (Azure AD) IDENTITY Protection を使用して、組織の ID に影響を与える潜在的な脆弱性を検出し、自動応答を構成し、インシデントを調査できます。</span><span class="sxs-lookup"><span data-stu-id="c8b75-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="c8b75-106">この記事では、Azure AD Id Protection を使用してテスト環境アカウントの分析を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8b75-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="c8b75-107">エンタープライズ テスト環境ADで Azure id Protection をMicrosoft 365には、次の 2 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="c8b75-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="c8b75-108">フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する</span><span class="sxs-lookup"><span data-stu-id="c8b75-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="c8b75-109">フェーズ 2: Azure AD ID 保護を使用する</span><span class="sxs-lookup"><span data-stu-id="c8b75-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="c8b75-111">エンタープライズ テスト ラボ ガイド スタックの Microsoft 365 内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="c8b75-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="c8b75-112">フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する</span><span class="sxs-lookup"><span data-stu-id="c8b75-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="c8b75-113">最小要件を使用して Azure AD Id Protection のみを軽量な方法でテストする場合は、「Lightweight 基本構成」の手順 [に従います](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="c8b75-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c8b75-114">シミュレートされたエンタープライズで Azure AD ID 保護をテストする場合は、「パススルー認証」の手順 [に従います](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="c8b75-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8b75-115">Azure AD Identity Protection のテストでは、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="c8b75-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="c8b75-116">ここではオプションとして提供され、Azure AD Id Protection をテストし、一般的な組織を表す環境でテストできます。</span><span class="sxs-lookup"><span data-stu-id="c8b75-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="c8b75-117">フェーズ 2: Azure AD ID 保護を使用する</span><span class="sxs-lookup"><span data-stu-id="c8b75-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="c8b75-118">ブラウザーのプライベート インスタンスを開き、エンタープライズ テスト環境のグローバル管理者アカウントを使用して Azure portal [https://portal.azure.com](https://portal.azure.com) Microsoft 365サインインします。</span><span class="sxs-lookup"><span data-stu-id="c8b75-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="c8b75-119">Azure portal で、検索ボックスに **「ID 保護** 」と入力し、[Azure AD **Id Protection] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8b75-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="c8b75-120">[Identity **Protection - Overview] ブレードで** 、各レポートを選択して、レポートの概要を確認します。</span><span class="sxs-lookup"><span data-stu-id="c8b75-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="c8b75-121">[通知 **] で**、[ **危険にさらされているユーザーが検出されたアラート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8b75-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="c8b75-122">[危険にさら **されているユーザーが検出された通知] ウィンドウで、[** 中] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8b75-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="c8b75-123">[**メールが次のユーザー** に送信される]で、[含める] を選択し、グローバル管理者アカウントが選択したメンバーの一覧に含まれているか確認します。</span><span class="sxs-lookup"><span data-stu-id="c8b75-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="c8b75-124">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8b75-124">Select **Save**.</span></span>

<span data-ttu-id="c8b75-125">[ **保護] で**、さまざまなポリシーを選択して、それらを構成する方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="c8b75-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="c8b75-126">ポリシーを作成してアクティブ化する場合は、すべてのユーザーのアクセスがブロックされていないか、サインインできない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c8b75-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="c8b75-127">これを防ぐには、グローバル管理者などの特定のユーザー アカウントを除外します。</span><span class="sxs-lookup"><span data-stu-id="c8b75-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="c8b75-128">テストと実験の詳細については、「リスク イベント [のシミュレート」を参照してください](/azure/active-directory/active-directory-identityprotection-playbook)。</span><span class="sxs-lookup"><span data-stu-id="c8b75-128">For further testing and experimentation, see [Simulating risk events](/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="c8b75-129">次の手順</span><span class="sxs-lookup"><span data-stu-id="c8b75-129">Next step</span></span>

<span data-ttu-id="c8b75-130">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="c8b75-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8b75-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8b75-131">See also</span></span>

[<span data-ttu-id="c8b75-132">ID ロードマップ</span><span class="sxs-lookup"><span data-stu-id="c8b75-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="c8b75-133">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="c8b75-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c8b75-134">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="c8b75-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c8b75-135">Microsoft 365 for enterprise のドキュメント</span><span class="sxs-lookup"><span data-stu-id="c8b75-135">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)