---
title: Microsoft 365 Defender を評価する
description: 組織のMicrosoft 365 Defender、ID、データ、およびアプリケーションを保護するように設計されたセキュリティ ソリューションを試して体験するように、Microsoft 365 Defender試用版ラボまたはパイロット環境をセットアップします。
keywords: Microsoft 365 Defender試し、Microsoft 365 Defender を試し、Microsoft 365 Defender、Microsoft 365 Defender 評価ラボ、Microsoft 365 Defender パイロット、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度なハンティングを評価する
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c260588b80d8325567b74148a7a62586cfbc707
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458425"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="5fcd5-104">試用版ラボMicrosoft 365 Defenderパイロット環境を作成する</span><span class="sxs-lookup"><span data-stu-id="5fcd5-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5fcd5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5fcd5-105">**Applies to:**</span></span>
- <span data-ttu-id="5fcd5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fcd5-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="5fcd5-107">このガイドは、ユーザーとグループを使用してラボ環境をセットアップする全体にわたって作業し、Microsoft 365 Defender の機能の構成をガイドして、脅威攻撃を模倣し、有意義な試用結果を得るのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="5fcd5-108">この試用版ラボまたはパイロット環境を作成する目的は、包括的で統合されたテスト機能をMicrosoft 365 Defenderです。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="5fcd5-109">このインテリジェント セキュリティ ソリューションが組織の高度な脅威を検出、防止、自動的に調査、および対応する方法を体験してください。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="5fcd5-110">推奨される展開パスに基づいて、Microsoft 365 Defender評価を開始する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="5fcd5-111">目標は、試用版アカウントを使用してラボ環境で、またはフル ライセンスを使用して実稼働環境でセキュリティ ソリューションをセットアップする場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="5fcd5-112">試用版ラボまたはパイロット環境を準備すると、組織内の意思決定者にセキュリティ操作の使用例を提示するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="5fcd5-113">攻撃シミュレーションの実行が完了し、結果に満足したら、Microsoft Technical Sales Professionals または組織内の専門家の助けを借りて、組織に完全に展開して運用できます。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="5fcd5-114">このガイドは、次の場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-114">This guide will help you:</span></span>
- <span data-ttu-id="5fcd5-115">ラボ サーバーとコンピューターのセットアップ</span><span class="sxs-lookup"><span data-stu-id="5fcd5-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="5fcd5-116">ユーザーとグループを使用して Active Directory を構成する</span><span class="sxs-lookup"><span data-stu-id="5fcd5-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="5fcd5-117">Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint、および Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5fcd5-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="5fcd5-118">サーバーとコンピューターのローカル ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="5fcd5-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="5fcd5-119">脅威攻撃を模倣して、テスト インシデントまたはアラートを生成Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fcd5-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="5fcd5-120">最適な結果を得る場合は、可能な限りラボのセットアップ手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="5fcd5-121">展開フェーズ</span><span class="sxs-lookup"><span data-stu-id="5fcd5-121">Deployment phases</span></span>

<span data-ttu-id="5fcd5-122">試用版ラボ環境の作成には 3 つのMicrosoft 365 Defenderがあります。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![展開フェーズ: 準備、セットアップ、オンボード](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="5fcd5-124">段階</span><span class="sxs-lookup"><span data-stu-id="5fcd5-124">Phase</span></span> | <span data-ttu-id="5fcd5-125">説明</span><span class="sxs-lookup"><span data-stu-id="5fcd5-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="5fcd5-126">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="5fcd5-126">Phase 1: Prepare</span></span>](prepare-m365d-eval.md)| <span data-ttu-id="5fcd5-127">試用版ラボまたはパイロット環境にMicrosoft 365 Defender検討する必要がある点について説明します。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="5fcd5-128">- 関係者とサインオフ</span><span class="sxs-lookup"><span data-stu-id="5fcd5-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="5fcd5-129">- 環境に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="5fcd5-129">- Environment considerations</span></span> <br><span data-ttu-id="5fcd5-130">- Access</span><span class="sxs-lookup"><span data-stu-id="5fcd5-130">- Access</span></span> <br><span data-ttu-id="5fcd5-131">- Azure Active Directoryセットアップ</span><span class="sxs-lookup"><span data-stu-id="5fcd5-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="5fcd5-132">- 構成順序</span><span class="sxs-lookup"><span data-stu-id="5fcd5-132">- Configuration order</span></span>
|[<span data-ttu-id="5fcd5-133">フェーズ 2: セットアップ</span><span class="sxs-lookup"><span data-stu-id="5fcd5-133">Phase 2: Setup</span></span>](setup-m365deval.md)|  <span data-ttu-id="5fcd5-134">最初の手順を実行して、Microsoft 365セキュリティ センターにアクセスして、試用版ラボまたはMicrosoft 365 Defender環境をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="5fcd5-135">次の情報に案内されます。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-135">You'll be guided to:</span></span><br><br><span data-ttu-id="5fcd5-136">- 試用版にMicrosoft 365 E5する</span><span class="sxs-lookup"><span data-stu-id="5fcd5-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="5fcd5-137">- ドメインの構成</span><span class="sxs-lookup"><span data-stu-id="5fcd5-137">- Configure domain</span></span><br><span data-ttu-id="5fcd5-138">- ライセンスMicrosoft 365 E5割り当てる</span><span class="sxs-lookup"><span data-stu-id="5fcd5-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="5fcd5-139">- ポータルでセットアップ ウィザードを完了する</span><span class="sxs-lookup"><span data-stu-id="5fcd5-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="5fcd5-140">フェーズ 3: オンボードで&する</span><span class="sxs-lookup"><span data-stu-id="5fcd5-140">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="5fcd5-141">ピラーエンドポイントMicrosoft 365 Defenderオンボード エンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="5fcd5-142">次の情報に案内されます。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-142">You'll be guided to:</span></span><br><br><span data-ttu-id="5fcd5-143">- Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="5fcd5-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="5fcd5-144">- 構成Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5fcd5-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="5fcd5-145">- Id 用に Microsoft Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="5fcd5-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="5fcd5-146">- エンドポイント用の Microsoft Defender の構成</span><span class="sxs-lookup"><span data-stu-id="5fcd5-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="5fcd5-147">このガイドを完了すると、関係する関係者と必要な承認を特定し、適切なアクセス許可を持ち、試用版、構成済みのドメイン、および各 Microsoft 365 Defender の柱にサインアップし、エンドポイントがサービスにオンボードされます。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="5fcd5-148">主な機能</span><span class="sxs-lookup"><span data-stu-id="5fcd5-148">Key capabilities</span></span>

<span data-ttu-id="5fcd5-149">このMicrosoft 365 Defender機能を提供しますが、この展開ガイドの主な目的は、デバイスのオンボーディングを開始する方法です。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="5fcd5-150">オンボーディングに加えて、このガイダンスでは、次の機能を使用して開始できます。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="5fcd5-151">機能</span><span class="sxs-lookup"><span data-stu-id="5fcd5-151">Capability</span></span> | <span data-ttu-id="5fcd5-152">説明</span><span class="sxs-lookup"><span data-stu-id="5fcd5-152">Description</span></span> 
:---|:---
<span data-ttu-id="5fcd5-153">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="5fcd5-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="5fcd5-154">今日の脅威からOffice 365全体を保護するのに役立ちます</span><span class="sxs-lookup"><span data-stu-id="5fcd5-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="5fcd5-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="5fcd5-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="5fcd5-156">侵害された ID および悪意のあるインサイダーアクションに対する脅威を識別および検出します。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="5fcd5-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5fcd5-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="5fcd5-158">豊富な可視性、データ移動の制御、クラウド サービス全体のサイバー脅威の検出を提供します。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="5fcd5-159">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5fcd5-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="5fcd5-160">包括的なエンドポイント セキュリティを使用して、高度な脅威に対する対応機能を防止、検出、および提供します。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="5fcd5-161">スコープ内</span><span class="sxs-lookup"><span data-stu-id="5fcd5-161">In scope</span></span>

<span data-ttu-id="5fcd5-162">このガイドでは、以下のタスクが対象になります。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="5fcd5-163">Azure Active Directory をセットアップする</span><span class="sxs-lookup"><span data-stu-id="5fcd5-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="5fcd5-164">設定Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fcd5-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="5fcd5-165">パイロットを実行しているMicrosoft 365 E5試用版にサインアップするか、フル ライセンスを使用する</span><span class="sxs-lookup"><span data-stu-id="5fcd5-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="5fcd5-166">ドメインの構成</span><span class="sxs-lookup"><span data-stu-id="5fcd5-166">Configure domain</span></span>
    -   <span data-ttu-id="5fcd5-167">ライセンスMicrosoft 365 E5割り当てる</span><span class="sxs-lookup"><span data-stu-id="5fcd5-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="5fcd5-168">ポータル内でのセットアップ ウィザードの完了</span><span class="sxs-lookup"><span data-stu-id="5fcd5-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="5fcd5-169">ベスト プラクティスにMicrosoft 365 Defender、すべての柱を構成する</span><span class="sxs-lookup"><span data-stu-id="5fcd5-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="5fcd5-170">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="5fcd5-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="5fcd5-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="5fcd5-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="5fcd5-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5fcd5-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="5fcd5-173">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5fcd5-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="5fcd5-174">対象外</span><span class="sxs-lookup"><span data-stu-id="5fcd5-174">Out of scope</span></span>

<span data-ttu-id="5fcd5-175">以下は、この展開ガイドの範囲を外しています。</span><span class="sxs-lookup"><span data-stu-id="5fcd5-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="5fcd5-176">アプリケーションと統合する可能性のあるサード パーティ製ソリューションのMicrosoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fcd5-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="5fcd5-177">実稼働環境での侵入テスト</span><span class="sxs-lookup"><span data-stu-id="5fcd5-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="5fcd5-178">次の手順</span><span class="sxs-lookup"><span data-stu-id="5fcd5-178">Next step</span></span>
<span data-ttu-id="5fcd5-179">[フェーズ 1: 準備](prepare-m365d-eval.md) 
</span><span class="sxs-lookup"><span data-stu-id="5fcd5-179">[Phase 1: Prepare](prepare-m365d-eval.md) 
</span></span><br> <span data-ttu-id="5fcd5-180">テスト ラボMicrosoft 365 Defenderパイロット環境を準備する</span><span class="sxs-lookup"><span data-stu-id="5fcd5-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
