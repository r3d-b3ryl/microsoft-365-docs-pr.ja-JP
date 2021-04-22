---
title: Microsoft 365 Defender
description: Microsoft 365 Defender 試用版ラボまたはパイロット環境をセットアップして、組織内のデバイス、ID、データ、アプリケーションを保護するように設計されたセキュリティ ソリューションを試して体験します。
keywords: Microsoft 365 Defender 試用版、Microsoft 365 Defender の試用、Microsoft 365 Defender、Microsoft 365 Defender 評価ラボ、Microsoft 365 Defender パイロット、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な狩猟
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
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933171"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="fabb8-104">Microsoft 365 Defender 試用版ラボまたはパイロット環境を作成する</span><span class="sxs-lookup"><span data-stu-id="fabb8-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fabb8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fabb8-105">**Applies to:**</span></span>
- <span data-ttu-id="fabb8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fabb8-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="fabb8-107">このガイドは、ユーザーとグループを使用してラボ環境をセットアップする場合に役立ち、脅威攻撃を模倣して有意義な試用結果を得るために、Microsoft 365 Defender の機能の構成をガイドします。</span><span class="sxs-lookup"><span data-stu-id="fabb8-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="fabb8-108">この試用版ラボまたはパイロット環境を作成する目的は、Microsoft 365 Defender の包括的で統合された機能を説明する目的です。</span><span class="sxs-lookup"><span data-stu-id="fabb8-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="fabb8-109">このインテリジェント セキュリティ ソリューションが組織の高度な脅威を検出、防止、自動的に調査、および対応する方法を体験してください。</span><span class="sxs-lookup"><span data-stu-id="fabb8-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="fabb8-110">推奨される展開パスに基づいて Microsoft 365 Defender 評価を開始する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="fabb8-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="fabb8-111">目標は、試用版アカウントを使用してラボ環境で、またはフル ライセンスを使用して実稼働環境でセキュリティ ソリューションをセットアップする場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fabb8-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="fabb8-112">試用版ラボまたはパイロット環境を準備すると、組織内の意思決定者にセキュリティ操作の使用例を提示するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fabb8-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="fabb8-113">攻撃シミュレーションの実行が完了し、結果に満足したら、Microsoft Technical Sales Professionals または組織内の専門家の助けを借りて、組織に完全に展開して運用できます。</span><span class="sxs-lookup"><span data-stu-id="fabb8-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="fabb8-114">このガイドは、次の場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fabb8-114">This guide will help you:</span></span>
- <span data-ttu-id="fabb8-115">ラボ サーバーとコンピューターのセットアップ</span><span class="sxs-lookup"><span data-stu-id="fabb8-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="fabb8-116">ユーザーとグループを使用して Active Directory を構成する</span><span class="sxs-lookup"><span data-stu-id="fabb8-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="fabb8-117">Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint、Microsoft Cloud App Security のセットアップと構成</span><span class="sxs-lookup"><span data-stu-id="fabb8-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="fabb8-118">サーバーとコンピューターのローカル ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="fabb8-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="fabb8-119">Microsoft 365 Defender でテスト インシデントまたはアラートを生成する脅威攻撃を模倣する</span><span class="sxs-lookup"><span data-stu-id="fabb8-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="fabb8-120">最適な結果を得る場合は、可能な限りラボのセットアップ手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fabb8-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="fabb8-121">展開フェーズ</span><span class="sxs-lookup"><span data-stu-id="fabb8-121">Deployment phases</span></span>

<span data-ttu-id="fabb8-122">Microsoft 365 Defender 試用版ラボ環境の作成には 3 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="fabb8-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![展開フェーズ: 準備、セットアップ、オンボード](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="fabb8-124">段階</span><span class="sxs-lookup"><span data-stu-id="fabb8-124">Phase</span></span> | <span data-ttu-id="fabb8-125">説明</span><span class="sxs-lookup"><span data-stu-id="fabb8-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="fabb8-126">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="fabb8-126">Phase 1: Prepare</span></span>](prepare-m365d-eval.md)| <span data-ttu-id="fabb8-127">試用版ラボまたはパイロット環境で Microsoft 365 Defender を展開する際に考慮する必要がある点について説明します。</span><span class="sxs-lookup"><span data-stu-id="fabb8-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="fabb8-128">- 関係者とサインオフ</span><span class="sxs-lookup"><span data-stu-id="fabb8-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="fabb8-129">- 環境に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="fabb8-129">- Environment considerations</span></span> <br><span data-ttu-id="fabb8-130">- Access</span><span class="sxs-lookup"><span data-stu-id="fabb8-130">- Access</span></span> <br><span data-ttu-id="fabb8-131">- Azure Active Directory のセットアップ</span><span class="sxs-lookup"><span data-stu-id="fabb8-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="fabb8-132">- 構成順序</span><span class="sxs-lookup"><span data-stu-id="fabb8-132">- Configuration order</span></span>
|[<span data-ttu-id="fabb8-133">フェーズ 2: セットアップ</span><span class="sxs-lookup"><span data-stu-id="fabb8-133">Phase 2: Setup</span></span>](setup-m365deval.md)|  <span data-ttu-id="fabb8-134">Microsoft 365 セキュリティ センターにアクセスする最初の手順を実行して、Microsoft 365 Defender 試用版ラボまたはパイロット環境をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="fabb8-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="fabb8-135">次の情報に案内されます。</span><span class="sxs-lookup"><span data-stu-id="fabb8-135">You'll be guided to:</span></span><br><br><span data-ttu-id="fabb8-136">- Microsoft 365 E5 試用版にサインアップする</span><span class="sxs-lookup"><span data-stu-id="fabb8-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="fabb8-137">- ドメインの構成</span><span class="sxs-lookup"><span data-stu-id="fabb8-137">- Configure domain</span></span><br><span data-ttu-id="fabb8-138">- Microsoft 365 E5 ライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="fabb8-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="fabb8-139">- ポータルでセットアップ ウィザードを完了する</span><span class="sxs-lookup"><span data-stu-id="fabb8-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="fabb8-140">フェーズ 3: オンボードで&する</span><span class="sxs-lookup"><span data-stu-id="fabb8-140">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="fabb8-141">各 Microsoft 365 Defender の柱とオンボード エンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="fabb8-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="fabb8-142">次の情報に案内されます。</span><span class="sxs-lookup"><span data-stu-id="fabb8-142">You'll be guided to:</span></span><br><br><span data-ttu-id="fabb8-143">- Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="fabb8-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="fabb8-144">- Microsoft Cloud App Security の構成</span><span class="sxs-lookup"><span data-stu-id="fabb8-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="fabb8-145">- Id 用に Microsoft Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="fabb8-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="fabb8-146">- エンドポイント用の Microsoft Defender の構成</span><span class="sxs-lookup"><span data-stu-id="fabb8-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="fabb8-147">このガイドを完了すると、関係する関係者と必要な承認を特定し、適切なアクセス許可を持ち、試用版にサインアップし、ドメインを構成し、Microsoft 365 Defender の各柱を構成し、エンドポイントがサービスにオンボードされます。</span><span class="sxs-lookup"><span data-stu-id="fabb8-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="fabb8-148">主な機能</span><span class="sxs-lookup"><span data-stu-id="fabb8-148">Key capabilities</span></span>

<span data-ttu-id="fabb8-149">Microsoft 365 Defender には多くの機能があります。この展開ガイドの主な目的は、デバイスのオンボードを開始する方法です。</span><span class="sxs-lookup"><span data-stu-id="fabb8-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="fabb8-150">オンボーディングに加えて、このガイダンスでは、次の機能を使用して開始できます。</span><span class="sxs-lookup"><span data-stu-id="fabb8-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="fabb8-151">機能</span><span class="sxs-lookup"><span data-stu-id="fabb8-151">Capability</span></span> | <span data-ttu-id="fabb8-152">説明</span><span class="sxs-lookup"><span data-stu-id="fabb8-152">Description</span></span> 
:---|:---
<span data-ttu-id="fabb8-153">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="fabb8-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="fabb8-154">今日の脅威から 365 のOffice全体を保護するのに役立ちます</span><span class="sxs-lookup"><span data-stu-id="fabb8-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="fabb8-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="fabb8-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="fabb8-156">侵害された ID および悪意のあるインサイダーアクションに対する脅威を識別および検出します。</span><span class="sxs-lookup"><span data-stu-id="fabb8-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="fabb8-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fabb8-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="fabb8-158">豊富な可視性、データ移動の制御、クラウド サービス全体のサイバー脅威の検出を提供します。</span><span class="sxs-lookup"><span data-stu-id="fabb8-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="fabb8-159">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fabb8-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="fabb8-160">包括的なエンドポイント セキュリティを使用して、高度な脅威に対する対応機能を防止、検出、および提供します。</span><span class="sxs-lookup"><span data-stu-id="fabb8-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="fabb8-161">スコープ内</span><span class="sxs-lookup"><span data-stu-id="fabb8-161">In scope</span></span>

<span data-ttu-id="fabb8-162">このガイドでは、以下のタスクが対象になります。</span><span class="sxs-lookup"><span data-stu-id="fabb8-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="fabb8-163">Azure Active Directory をセットアップする</span><span class="sxs-lookup"><span data-stu-id="fabb8-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="fabb8-164">Microsoft 365 Defender のセットアップ</span><span class="sxs-lookup"><span data-stu-id="fabb8-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="fabb8-165">パイロットを実行している場合は、Microsoft 365 E5 試用版にサインアップするか、フル ライセンスを使用する</span><span class="sxs-lookup"><span data-stu-id="fabb8-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="fabb8-166">ドメインの構成</span><span class="sxs-lookup"><span data-stu-id="fabb8-166">Configure domain</span></span>
    -   <span data-ttu-id="fabb8-167">Microsoft 365 E5 ライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="fabb8-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="fabb8-168">ポータル内でのセットアップ ウィザードの完了</span><span class="sxs-lookup"><span data-stu-id="fabb8-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="fabb8-169">ベスト プラクティスに基づいてすべての Microsoft 365 Defender の柱を構成する</span><span class="sxs-lookup"><span data-stu-id="fabb8-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="fabb8-170">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="fabb8-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="fabb8-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="fabb8-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="fabb8-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fabb8-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="fabb8-173">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fabb8-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="fabb8-174">対象外</span><span class="sxs-lookup"><span data-stu-id="fabb8-174">Out of scope</span></span>

<span data-ttu-id="fabb8-175">以下は、この展開ガイドの範囲を外しています。</span><span class="sxs-lookup"><span data-stu-id="fabb8-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="fabb8-176">Microsoft 365 Defender と統合する可能性のあるサード パーティ製ソリューションの構成</span><span class="sxs-lookup"><span data-stu-id="fabb8-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="fabb8-177">実稼働環境での侵入テスト</span><span class="sxs-lookup"><span data-stu-id="fabb8-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="fabb8-178">次の手順</span><span class="sxs-lookup"><span data-stu-id="fabb8-178">Next step</span></span>
<span data-ttu-id="fabb8-179">[フェーズ 1: 準備](prepare-m365d-eval.md) 
</span><span class="sxs-lookup"><span data-stu-id="fabb8-179">[Phase 1: Prepare](prepare-m365d-eval.md) 
</span></span><br> <span data-ttu-id="fabb8-180">Microsoft 365 Defender 試用版ラボまたはパイロット環境を準備する</span><span class="sxs-lookup"><span data-stu-id="fabb8-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
