---
title: パイロット Microsoft Cloud App Security、Microsoft 365 Defenderグループの作成、条件付きアクセス制御の構成、機能の試し、テストの一部としてのセットアップを行Microsoft 365 Defender
description: デバイス、ID、Microsoft 365 Defenderアプリケーションを保護するように設計されたセキュリティ ソリューションをテストおよびエクスペリエンスするために、テストラボまたはパイロット環境をセットアップします。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e061bf213ee929f91a48b03c71b9654a7ea76b8c
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458046"
---
# <a name="pilot-microsoft-cloud-app-security-with-microsoft-365-defender"></a><span data-ttu-id="18692-103">パイロット Microsoft Cloud App SecurityとMicrosoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18692-103">Pilot Microsoft Cloud App Security with Microsoft 365 Defender</span></span>


<span data-ttu-id="18692-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="18692-104">**Applies to:**</span></span>
- <span data-ttu-id="18692-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18692-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="18692-106">この記事は、ユーザーの評価環境をセットアップするプロセスの手順[3/3](eval-defender-mcas-overview.md) Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="18692-106">This article is [Step 3 of 3](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="18692-107">このプロセスの詳細については、「概要」の記事を [参照してください](eval-defender-mcas-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="18692-107">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="18692-108">次の手順を使用して、パイロットのセットアップと構成を行Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="18692-108">Use the following steps to setup and configure the pilot for Microsoft Cloud App Security.</span></span>


![パイロットの手順Microsoft Cloud App Security](../../media/defender/m365-defender-mcas-pilot-steps.png)

- <span data-ttu-id="18692-110">手順 1.</span><span class="sxs-lookup"><span data-stu-id="18692-110">Step 1.</span></span> [<span data-ttu-id="18692-111">パイロット グループの作成 - パイロット展開を特定のユーザー グループにスコープ設定する</span><span class="sxs-lookup"><span data-stu-id="18692-111">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [<span data-ttu-id="18692-112">手順 2.保護の構成 - 条件付きアクセス アプリ制御</span><span class="sxs-lookup"><span data-stu-id="18692-112">Step 2. Configure protection — Conditional Access App Control</span></span>](#step-2-configure-protection--conditional-access-app-control)
- [<span data-ttu-id="18692-113">手順 3.機能を試す - 環境を保護するためのチュートリアルの詳細</span><span class="sxs-lookup"><span data-stu-id="18692-113">Step 3. Try out capabilities — Walk through tutorials for protecting your environment</span></span>](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a><span data-ttu-id="18692-114">手順 1.</span><span class="sxs-lookup"><span data-stu-id="18692-114">Step 1.</span></span> <span data-ttu-id="18692-115">パイロット グループの作成 - パイロット展開を特定のユーザー グループにスコープ設定する</span><span class="sxs-lookup"><span data-stu-id="18692-115">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>

<span data-ttu-id="18692-116">Microsoft Cloud App Securityを使用すると、展開の範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="18692-116">Microsoft Cloud App Security enables you to scope your deployment.</span></span> <span data-ttu-id="18692-117">スコープを使用すると、アプリの監視対象または監視から除外する特定のユーザー グループを選択できます。</span><span class="sxs-lookup"><span data-stu-id="18692-117">Scoping allows you to select certain user groups to be monitored for apps or excluded from monitoring.</span></span> <span data-ttu-id="18692-118">ユーザー グループを含めるか除外できます。</span><span class="sxs-lookup"><span data-stu-id="18692-118">You can include or exclude user groups.</span></span> <span data-ttu-id="18692-119">パイロット展開の範囲を設定するには [、「Scoped Deployment」を参照してください](/cloud-app-security/scoped-deployment)。</span><span class="sxs-lookup"><span data-stu-id="18692-119">To scope your pilot deployment, see [Scoped Deployment](/cloud-app-security/scoped-deployment).</span></span>


## <a name="step-2-configure-protection--conditional-access-app-control"></a><span data-ttu-id="18692-120">手順 2.</span><span class="sxs-lookup"><span data-stu-id="18692-120">Step 2.</span></span> <span data-ttu-id="18692-121">保護の構成 - 条件付きアクセス アプリ制御</span><span class="sxs-lookup"><span data-stu-id="18692-121">Configure protection — Conditional Access App Control</span></span>

<span data-ttu-id="18692-122">構成できる最も強力な保護の 1 つは、条件付きアクセス アプリ制御です。</span><span class="sxs-lookup"><span data-stu-id="18692-122">One of the most powerful protections you can configure is Conditional Access App Control.</span></span> <span data-ttu-id="18692-123">これには、Azure Active Directory (Azure AD) との統合が必要です。</span><span class="sxs-lookup"><span data-stu-id="18692-123">This requires integration with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="18692-124">これにより、関連するポリシー (正常なデバイスの要求など) を含む条件付きアクセス ポリシーを、承認したクラウド アプリに適用できます。</span><span class="sxs-lookup"><span data-stu-id="18692-124">It allows you to apply Conditional Access policies, including related policies (like requiring healthy devices), to cloud apps you've sanctioned.</span></span> 

<span data-ttu-id="18692-125">SaaS アプリをMicrosoft Cloud App Securityする最初の手順は、これらのアプリを検出し、それらを Azure AD テナントにADです。</span><span class="sxs-lookup"><span data-stu-id="18692-125">The first step in using Microsoft Cloud App Security to manage SaaS apps is to discover these and then add them to your Azure AD tenant.</span></span> <span data-ttu-id="18692-126">検出に関するヘルプが必要な場合は、「 [ネットワーク内の SaaS アプリを検出して管理する」を参照してください](/cloud-app-security/tutorial-shadow-it)。</span><span class="sxs-lookup"><span data-stu-id="18692-126">If you need help with discovery, see [Discover and manage SaaS apps in your network](/cloud-app-security/tutorial-shadow-it).</span></span> <span data-ttu-id="18692-127">アプリを検出した後、これらのアプリを [Azure ADテナントに追加します](/azure/active-directory/manage-apps/add-application-portal)。</span><span class="sxs-lookup"><span data-stu-id="18692-127">After you've discovered apps, [add these to your Azure AD tenant](/azure/active-directory/manage-apps/add-application-portal).</span></span>

<span data-ttu-id="18692-128">これらを管理するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="18692-128">You can begin to manage these by doing the following:</span></span>

- <span data-ttu-id="18692-129">まず、Azure ADで、新しい条件付きアクセス ポリシーを作成し、"条件付きアクセス アプリ制御を使用する" に構成します。</span><span class="sxs-lookup"><span data-stu-id="18692-129">First, in Azure AD, create a new conditional access policy and configure it to "Use Conditional Access App Control."</span></span> <span data-ttu-id="18692-130">これにより、要求がサーバーにリダイレクトCloud App Security。</span><span class="sxs-lookup"><span data-stu-id="18692-130">This redirects the request to Cloud App Security.</span></span> <span data-ttu-id="18692-131">1 つのポリシーを作成し、すべての SaaS アプリをこのポリシーに追加できます。</span><span class="sxs-lookup"><span data-stu-id="18692-131">You can create one policy and add all SaaS apps to this policy.</span></span>
- <span data-ttu-id="18692-132">次に、[セッション ポリシー Cloud App Security作成します。</span><span class="sxs-lookup"><span data-stu-id="18692-132">Next, in Cloud App Security, create session policies.</span></span> <span data-ttu-id="18692-133">適用するコントロールごとに 1 つのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="18692-133">Create one policy for each control you want to apply.</span></span>

<span data-ttu-id="18692-134">サポートされているアプリとクライアントを含む詳細については、「アプリを条件付きアクセス アプリ制御で保護Microsoft Cloud App Security[を参照してください](/cloud-app-security/proxy-intro-aad)。</span><span class="sxs-lookup"><span data-stu-id="18692-134">For more information, including supported apps and clients, see [Protect apps with Microsoft Cloud App Security Conditional Access App Control](/cloud-app-security/proxy-intro-aad).</span></span> 

<span data-ttu-id="18692-135">ポリシーの例については[、「SaaS アプリMicrosoft Cloud App Security推奨されるポリシー」を参照してください](../office-365-security/mcas-saas-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="18692-135">For example policies, see [Recommended Microsoft Cloud App Security policies for SaaS apps](../office-365-security/mcas-saas-access-policies.md).</span></span> <span data-ttu-id="18692-136">これらのポリシーは、すべての顧客の開始[](../office-365-security/microsoft-365-policies-configurations.md)点として推奨される一連の一般的な ID およびデバイス アクセス ポリシーに基になります。</span><span class="sxs-lookup"><span data-stu-id="18692-136">These policies build on a set of [common identity and device access policies](../office-365-security/microsoft-365-policies-configurations.md) that are recommended as a starting point for all customers.</span></span> 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a><span data-ttu-id="18692-137">手順 3.</span><span class="sxs-lookup"><span data-stu-id="18692-137">Step 3.</span></span> <span data-ttu-id="18692-138">機能を試す - 環境を保護するためのチュートリアルの詳細</span><span class="sxs-lookup"><span data-stu-id="18692-138">Try out capabilities — Walk through tutorials for protecting your environment</span></span> 

<span data-ttu-id="18692-139">このMicrosoft Cloud App Securityには、リスクの発見と環境の保護に役立つ一連のチュートリアルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="18692-139">The Microsoft Cloud App Security documentation includes a series of tutorials to help you discover risk and protect your environment.</span></span> 

<span data-ttu-id="18692-140">次のチュートリアルCloud App Security試してください。</span><span class="sxs-lookup"><span data-stu-id="18692-140">Try out Cloud App Security tutorials:</span></span>

- [<span data-ttu-id="18692-141">疑わしいユーザーアクティビティを検出する</span><span class="sxs-lookup"><span data-stu-id="18692-141">Detect suspicious user activity</span></span>](/cloud-app-security/tutorial-suspicious-activity)
- [<span data-ttu-id="18692-142">リスクの高いユーザーを調査する</span><span class="sxs-lookup"><span data-stu-id="18692-142">Investigate risky users</span></span>](/cloud-app-security/tutorial-ueba)
- [<span data-ttu-id="18692-143">危険な OAuth アプリを調査する</span><span class="sxs-lookup"><span data-stu-id="18692-143">Investigate risky OAuth apps</span></span>](/cloud-app-security/investigate-risky-oauth)
- [<span data-ttu-id="18692-144">機密情報の検出と保護</span><span class="sxs-lookup"><span data-stu-id="18692-144">Discover and protect sensitive information</span></span>](/cloud-app-security/tutorial-dlp)
- [<span data-ttu-id="18692-145">組織内のすべてのアプリをリアルタイムで保護する</span><span class="sxs-lookup"><span data-stu-id="18692-145">Protect any app in your organization in real time</span></span>](/cloud-app-security/tutorial-proxy)
- [<span data-ttu-id="18692-146">機密情報のダウンロードをブロックする</span><span class="sxs-lookup"><span data-stu-id="18692-146">Block downloads of sensitive information</span></span>](/cloud-app-security/use-case-proxy-block-session-aad)
- [<span data-ttu-id="18692-147">管理検疫でファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="18692-147">Protect your files with admin quarantine</span></span>](/cloud-app-security/use-case-admin-quarantine)
- [<span data-ttu-id="18692-148">リスクの高いアクション時にステップ アップ認証を要求する</span><span class="sxs-lookup"><span data-stu-id="18692-148">Require step-up authentication upon risky action</span></span>](/cloud-app-security/tutorial-step-up-authentication)

## <a name="next-steps"></a><span data-ttu-id="18692-149">次の手順</span><span class="sxs-lookup"><span data-stu-id="18692-149">Next steps</span></span>

[<span data-ttu-id="18692-150">パイロット環境で、Microsoft 365 Defenderを使用して調査と対応を行う</span><span class="sxs-lookup"><span data-stu-id="18692-150">Investigate and respond using Microsoft 365 Defender in a pilot environment</span></span>](eval-defender-investigate-respond.md)

<span data-ttu-id="18692-151">[評価] の概要[に戻Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="18692-151">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="18692-152">[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="18692-152">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>