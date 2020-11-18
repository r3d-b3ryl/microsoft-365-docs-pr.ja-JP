---
title: Microsoft 365 Defender を評価する
description: Microsoft 365 Defender 試用ラボまたはパイロット環境を設定して、組織内のデバイス、id、データ、およびアプリケーションを保護するために設計されたセキュリティソリューションを体験してみてください。
keywords: Microsoft threat Protection の試用版、microsoft threat protection の評価、microsoft の脅威保護の評価ラボ、microsoft の脅威保護のパイロット、サイバーセキュリティ、高度な脅威、企業のセキュリティ、デバイス、デバイス、id、ユーザー、データ、アプリケーション、インシデント、自動化された調査と修復、高度な検索
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: fe0a06dd104f0f0532363ee046f4bad1c03c5400
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130890"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="774de-104">Microsoft 365 Defender 試用ラボまたはパイロット環境を作成する</span><span class="sxs-lookup"><span data-stu-id="774de-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="774de-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="774de-105">**Applies to:**</span></span>
- <span data-ttu-id="774de-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="774de-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="774de-107">この試用ラボまたはパイロット環境を作成する目的は、包括的かつ統合された Microsoft 365 Defender 機能を説明することです。</span><span class="sxs-lookup"><span data-stu-id="774de-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="774de-108">このインテリジェントセキュリティソリューションが組織に対する高度な脅威を検出、阻止、自動調査、および応答する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="774de-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="774de-109">このガイドでは、推奨される展開パスに基づいて Microsoft 365 Defender 評価を開始する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="774de-109">This guide takes you through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="774de-110">ここでの目的は、試用版アカウントを使用したラボ環境で、または完全ライセンスを使用した運用環境で、セキュリティソリューションをセットアップできるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="774de-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="774de-111">試用ラボまたはパイロット環境の準備は、組織の意思決定者にセキュリティ操作の使用ケースを提示するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="774de-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="774de-112">攻撃のシミュレーションの実行が完了し、結果に問題がなければ、組織内の Microsoft テクニカルセールス担当者または専門家と協力して、組織内で operationalize it を完全に展開し、その結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="774de-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="774de-113">このガイドは、次のことを支援します。</span><span class="sxs-lookup"><span data-stu-id="774de-113">This guide will help you:</span></span>
- <span data-ttu-id="774de-114">ラボサーバーとコンピューターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="774de-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="774de-115">ユーザーおよびグループを使用して Active Directory を構成する</span><span class="sxs-lookup"><span data-stu-id="774de-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="774de-116">Id に対して Microsoft Defender をセットアップおよび構成する、Microsoft Defender for Office 365、Microsoft defender for Endpoint、microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="774de-116">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="774de-117">サーバーとコンピューターのローカルポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="774de-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="774de-118">Microsoft 365 Defender でテストインシデントまたはアラートを生成する脅威攻撃を模倣する</span><span class="sxs-lookup"><span data-stu-id="774de-118">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="774de-119">最適な結果を得るには、演習のセットアップの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="774de-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="774de-120">展開フェーズ</span><span class="sxs-lookup"><span data-stu-id="774de-120">Deployment phases</span></span>

<span data-ttu-id="774de-121">Microsoft 365 Defender 試用ラボ環境を作成して展開するには、3つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="774de-121">There are three phases in creating a Microsoft 365 Defender trial lab environment and deploying it:</span></span>

![展開フェーズ: 準備、セットアップ、オンボード](../../media/phase-diagrams/deployment-phases.png)

|<span data-ttu-id="774de-123">フェーズ</span><span class="sxs-lookup"><span data-stu-id="774de-123">Phase</span></span> | <span data-ttu-id="774de-124">説明</span><span class="sxs-lookup"><span data-stu-id="774de-124">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="774de-125">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="774de-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="774de-126">トライアルラボまたはパイロット環境に Microsoft 365 Defender を展開するときに考慮する必要がある事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="774de-126">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="774de-127">-関係者と承認</span><span class="sxs-lookup"><span data-stu-id="774de-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="774de-128">-環境に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="774de-128">- Environment considerations</span></span> <br><span data-ttu-id="774de-129">-アクセス</span><span class="sxs-lookup"><span data-stu-id="774de-129">- Access</span></span> <br><span data-ttu-id="774de-130">-Azure Active Directory のセットアップ</span><span class="sxs-lookup"><span data-stu-id="774de-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="774de-131">-構成の順序</span><span class="sxs-lookup"><span data-stu-id="774de-131">- Configuration order</span></span>
|[<span data-ttu-id="774de-132">フェーズ 2: セットアップ</span><span class="sxs-lookup"><span data-stu-id="774de-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="774de-133">Microsoft 365 セキュリティセンターにアクセスするための最初の手順を実行して、Microsoft 365 Defender 試用ラボまたはパイロット環境を設定します。</span><span class="sxs-lookup"><span data-stu-id="774de-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="774de-134">次のようなガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="774de-134">You'll be guided to:</span></span><br><br><span data-ttu-id="774de-135">-Microsoft 365 E5 試用版にサインアップする</span><span class="sxs-lookup"><span data-stu-id="774de-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="774de-136">-ドメインの構成</span><span class="sxs-lookup"><span data-stu-id="774de-136">- Configure domain</span></span><br><span data-ttu-id="774de-137">-Microsoft 365 E5 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="774de-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="774de-138">-ポータルのセットアップウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="774de-138">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="774de-139">フェーズ 3: 構成 & オンボード</span><span class="sxs-lookup"><span data-stu-id="774de-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="774de-140">各 Microsoft 365 Defender 柱およびオンボードエンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="774de-140">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="774de-141">次のようなガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="774de-141">You'll be guided to:</span></span><br><br><span data-ttu-id="774de-142">-Office 365 の Microsoft Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="774de-142">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="774de-143">-Microsoft Cloud App Security を構成する</span><span class="sxs-lookup"><span data-stu-id="774de-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="774de-144">-Identity の Microsoft Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="774de-144">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="774de-145">-エンドポイントの Microsoft Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="774de-145">- Configure Microsoft Defender for Endpoint</span></span>


## <a name="in-scope"></a><span data-ttu-id="774de-146">範囲内</span><span class="sxs-lookup"><span data-stu-id="774de-146">In scope</span></span>

<span data-ttu-id="774de-147">このガイドの対象となるタスクは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="774de-147">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="774de-148">Azure Active Directory をセットアップする</span><span class="sxs-lookup"><span data-stu-id="774de-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="774de-149">Microsoft 365 Defender をセットアップする</span><span class="sxs-lookup"><span data-stu-id="774de-149">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="774de-150">パイロットを実行している場合は、Microsoft 365 E5 試用版にサインアップするか、完全ライセンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="774de-150">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="774de-151">ドメインを構成する</span><span class="sxs-lookup"><span data-stu-id="774de-151">Configure domain</span></span>
    -   <span data-ttu-id="774de-152">Microsoft 365 E5 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="774de-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="774de-153">ポータル内のセットアップウィザードの完了</span><span class="sxs-lookup"><span data-stu-id="774de-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="774de-154">ベストプラクティスに基づいてすべての Microsoft 365 Defender 柱を構成する</span><span class="sxs-lookup"><span data-stu-id="774de-154">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="774de-155">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="774de-155">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="774de-156">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="774de-156">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="774de-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="774de-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="774de-158">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="774de-158">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="774de-159">対象外</span><span class="sxs-lookup"><span data-stu-id="774de-159">Out of scope</span></span>

<span data-ttu-id="774de-160">この展開ガイドの範囲外のものを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="774de-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="774de-161">Microsoft 365 Defender と統合される可能性のあるサードパーティ製ソリューションの構成</span><span class="sxs-lookup"><span data-stu-id="774de-161">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="774de-162">運用環境でのペネトレーションテスト</span><span class="sxs-lookup"><span data-stu-id="774de-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="774de-163">次の手順</span><span class="sxs-lookup"><span data-stu-id="774de-163">Next step</span></span>
<span data-ttu-id="774de-164">[フェーズ 1: 準備](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="774de-164">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="774de-165">Microsoft 365 Defender 試用ラボまたはパイロット環境の準備</span><span class="sxs-lookup"><span data-stu-id="774de-165">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
