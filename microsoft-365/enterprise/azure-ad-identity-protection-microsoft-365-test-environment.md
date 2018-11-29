---
title: Microsoft 365 エンタープライズ向けの azure の AD のアイデンティティ保護環境をテストします。
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Azure AD Id 保護を構成し、Microsoft 365 エンタープライズ テスト環境の現在のアカウントを分析します。
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869083"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f823d-103">Microsoft 365 エンタープライズ向けの azure の AD のアイデンティティ保護環境をテストします。</span><span class="sxs-lookup"><span data-stu-id="f823d-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f823d-p101">Azure AD の識別情報の保護を使用すると、潜在的な脆弱性の影響、組織の識別情報を与えることを検出しへの自動応答を構成し、インシデントを調査できます。この資料では、Azure AD Id 保護を有効にして、テスト環境のアカウントの分析を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f823d-p101">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents. This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="f823d-106">Microsoft 365 エンタープライズ テスト環境での Azure AD の Id の保護を設定するのには 2 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="f823d-106">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="f823d-107">Microsoft 365 エンタープライズ テスト環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="f823d-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="f823d-108">有効にして、Azure AD Id 保護を使用します。</span><span class="sxs-lookup"><span data-stu-id="f823d-108">Enable and use Azure AD Identity Protection.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="f823d-110">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f823d-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f823d-111">フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。</span><span class="sxs-lookup"><span data-stu-id="f823d-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f823d-112">Azure AD Id 保護を最低限の要件を持つ軽量な方法でテストする場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="f823d-112">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f823d-113">シミュレートされた企業で Azure AD Id 保護をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="f823d-113">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f823d-p102">Azure AD Id 保護をテストは、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されていると Windows サーバーの AD フォレストの場合、ディレクトリ同期します。Azure AD Id 保護をテストし、通常の組織を表す環境で実験するためのオプションとしてここで。</span><span class="sxs-lookup"><span data-stu-id="f823d-p102">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="f823d-116">フェーズ 2: を有効にして、Azure AD Id 保護を使用して、</span><span class="sxs-lookup"><span data-stu-id="f823d-116">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="f823d-117">お使いのブラウザーのプライベート インスタンスを開くし、Azure ポータルにサインイン[https://portal.azure.com](https://portal.azure.com)Microsoft 365 エンタープライズ テスト環境のグローバル管理者アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="f823d-117">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="f823d-118">Azure のポータルをクリックして**のすべてのサービス > 市場**です。</span><span class="sxs-lookup"><span data-stu-id="f823d-118">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="f823d-119">**Azure AD Id 保護**を入力し、[] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f823d-119">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="f823d-120">**はじめ**のブレードで**Onboard**を [**設定**] をクリックして**をダッシュ ボードには、暗証番号 (pin)**、し、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f823d-120">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="f823d-121">Azure のポータルでは、ダッシュ ボードの**Azure AD Id 保護**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f823d-121">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="f823d-p103">ダッシュ ボードで、 **Azure AD アイデンティティ保護概要**ブレードを参照してくださいする必要があります。の下**の脆弱性**、多要素認証登録なしのユーザー アカウントの数を決定するを確認します。この番号は、以前 Microsoft 365 エンタープライズ テスト ラボ ガイドを行うことにより異なります。</span><span class="sxs-lookup"><span data-stu-id="f823d-p103">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard. Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration. This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="f823d-125">あるかどうか、ユーザーまたは検出されたイベントを表示するのには**調査**のカテゴリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f823d-125">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="f823d-126">さらにテストと実験を行うには、[リスク イベントのシミュレーション](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f823d-126">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="f823d-127">情報と実稼働環境での Azure AD のアイデンティティの保護の展開へのリンクの識別段階では、[侵害の資格情報を保護する](identity-azure-ad-identity-protection.md)手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f823d-127">See the [Protect against credential compromise](identity-azure-ad-identity-protection.md) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="f823d-128">次の手順</span><span class="sxs-lookup"><span data-stu-id="f823d-128">Next step</span></span>

<span data-ttu-id="f823d-129">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="f823d-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f823d-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="f823d-130">See also</span></span>

[<span data-ttu-id="f823d-131">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="f823d-131">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="f823d-132">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="f823d-132">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f823d-133">Microsoft 365 エンタープライズ展開</span><span class="sxs-lookup"><span data-stu-id="f823d-133">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f823d-134">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="f823d-134">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
