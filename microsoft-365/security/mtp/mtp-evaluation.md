---
title: Microsoft 365 Defender
description: Microsoft 365 Defender 試用版ラボまたはパイロット環境をセットアップし、組織内のデバイス、ID、データ、アプリケーションを保護するために設計されたセキュリティ ソリューションを試して体験します。
keywords: Microsoft Threat Protection 試用版、Microsoft Threat Protection の評価、Microsoft Threat Protection 評価ラボ、Microsoft Threat Protection パイロット、サイバー セキュリティ、高度な持続的脅威、エンタープライズ セキュリティ、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な捜問
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6735817a71f9fb50843acad3a13596ec247aa407
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930212"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="e57e8-104">Microsoft 365 Defender 試用版ラボまたはパイロット環境を作成する</span><span class="sxs-lookup"><span data-stu-id="e57e8-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e57e8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e57e8-105">**Applies to:**</span></span>
- <span data-ttu-id="e57e8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e57e8-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="e57e8-107">このガイドは、ユーザーとグループを含むラボ環境のセットアップに関する作業を行うのに役立ち、Microsoft 365 Defender の機能の構成について説明します。これにより、脅威攻撃を模倣し、有意義な評価版の結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="e57e8-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="e57e8-108">この試験ラボまたはパイロット環境を作成する目的は、Microsoft 365 Defender の包括的で統合された機能を説明する目的です。</span><span class="sxs-lookup"><span data-stu-id="e57e8-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="e57e8-109">このインテリジェント なセキュリティ ソリューションが、組織の高度な脅威を検出、防止、自動的に調査、および対応する方法を体験します。</span><span class="sxs-lookup"><span data-stu-id="e57e8-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="e57e8-110">推奨される展開パスに基づいて Microsoft 365 Defender の評価を開始する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="e57e8-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="e57e8-111">目標は、試験アカウントを使用したラボ環境、またはフル ライセンスの実稼働環境でのセキュリティ ソリューションのセットアップを支援します。</span><span class="sxs-lookup"><span data-stu-id="e57e8-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="e57e8-112">試験ラボまたはパイロット環境を準備すると、組織内の意思決定者にセキュリティ操作の使用事例を提示するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e57e8-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="e57e8-113">攻撃シミュレーションの実行が完了し、その結果に満足したら、Microsoft Technical Sales Professionals または組織内の専門家の支援を受け、組織に完全に展開して運用することができます。</span><span class="sxs-lookup"><span data-stu-id="e57e8-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="e57e8-114">このガイドは、次の場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e57e8-114">This guide will help you:</span></span>
- <span data-ttu-id="e57e8-115">ラボ サーバーとコンピューターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="e57e8-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="e57e8-116">ユーザーとグループを使用して Active Directory を構成する</span><span class="sxs-lookup"><span data-stu-id="e57e8-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="e57e8-117">Id 用の Microsoft Defender、Office 365 用 Microsoft Defender、エンドポイント用 Microsoft Defender、および Microsoft Cloud App Security をセットアップして構成する</span><span class="sxs-lookup"><span data-stu-id="e57e8-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="e57e8-118">サーバーとコンピューターのローカル ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="e57e8-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="e57e8-119">脅威攻撃を模倣して、Microsoft 365 Defender でテスト インシデントまたはアラートを生成する</span><span class="sxs-lookup"><span data-stu-id="e57e8-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="e57e8-120">最適な結果を得る場合は、可能な限りラボのセットアップ手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="e57e8-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="e57e8-121">展開フェーズ</span><span class="sxs-lookup"><span data-stu-id="e57e8-121">Deployment phases</span></span>

<span data-ttu-id="e57e8-122">Microsoft 365 Defender 試用版ラボ環境を作成するには、3 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="e57e8-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![展開フェーズ: 準備、セットアップ、オンボード](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="e57e8-124">フェーズ</span><span class="sxs-lookup"><span data-stu-id="e57e8-124">Phase</span></span> | <span data-ttu-id="e57e8-125">説明</span><span class="sxs-lookup"><span data-stu-id="e57e8-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="e57e8-126">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="e57e8-126">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="e57e8-127">試用版ラボまたはパイロット環境で Microsoft 365 Defender を展開する際に考慮する必要がある点について説明します。</span><span class="sxs-lookup"><span data-stu-id="e57e8-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="e57e8-128">- 関係者とサインオフ</span><span class="sxs-lookup"><span data-stu-id="e57e8-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="e57e8-129">- 環境に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="e57e8-129">- Environment considerations</span></span> <br><span data-ttu-id="e57e8-130">- Access</span><span class="sxs-lookup"><span data-stu-id="e57e8-130">- Access</span></span> <br><span data-ttu-id="e57e8-131">- Azure Active Directory のセットアップ</span><span class="sxs-lookup"><span data-stu-id="e57e8-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="e57e8-132">- 構成順序</span><span class="sxs-lookup"><span data-stu-id="e57e8-132">- Configuration order</span></span>
|[<span data-ttu-id="e57e8-133">フェーズ 2: セットアップ</span><span class="sxs-lookup"><span data-stu-id="e57e8-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="e57e8-134">最初の手順を実行して Microsoft 365 セキュリティ センターにアクセスし、Microsoft 365 Defender 試用版ラボまたはパイロット環境をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="e57e8-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="e57e8-135">次のガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e57e8-135">You'll be guided to:</span></span><br><br><span data-ttu-id="e57e8-136">- Microsoft 365 E5 試用版にサインアップする</span><span class="sxs-lookup"><span data-stu-id="e57e8-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="e57e8-137">- ドメインを構成する</span><span class="sxs-lookup"><span data-stu-id="e57e8-137">- Configure domain</span></span><br><span data-ttu-id="e57e8-138">- Microsoft 365 E5 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e57e8-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="e57e8-139">- ポータルでセットアップ ウィザードを完了する</span><span class="sxs-lookup"><span data-stu-id="e57e8-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="e57e8-140">フェーズ 3: オンボードの&する</span><span class="sxs-lookup"><span data-stu-id="e57e8-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="e57e8-141">各 Microsoft 365 Defender の柱とオンボード エンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="e57e8-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="e57e8-142">次のガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e57e8-142">You'll be guided to:</span></span><br><br><span data-ttu-id="e57e8-143">- Microsoft Defender を Office 365 用に構成する</span><span class="sxs-lookup"><span data-stu-id="e57e8-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="e57e8-144">- Microsoft Cloud App Security を構成する</span><span class="sxs-lookup"><span data-stu-id="e57e8-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="e57e8-145">- Id 用に Microsoft Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="e57e8-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="e57e8-146">- エンドポイント用に Microsoft Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="e57e8-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="e57e8-147">このガイドを完了すると、関係する関係者と必要な承認を特定し、適切なアクセス許可を持ち、試用版にサインアップし、ドメインを構成し、Microsoft 365 Defender の各柱を構成すると、エンドポイントがサービスにオンボードされます。</span><span class="sxs-lookup"><span data-stu-id="e57e8-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="e57e8-148">主な機能</span><span class="sxs-lookup"><span data-stu-id="e57e8-148">Key capabilities</span></span>

<span data-ttu-id="e57e8-149">Microsoft 365 Defender は多くの機能を提供しますが、この展開ガイドの主な目的は、デバイスのオンボーディングを開始することで開始します。</span><span class="sxs-lookup"><span data-stu-id="e57e8-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="e57e8-150">オンボーディングに加えて、このガイダンスでは次の機能を開始できます。</span><span class="sxs-lookup"><span data-stu-id="e57e8-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="e57e8-151">機能</span><span class="sxs-lookup"><span data-stu-id="e57e8-151">Capability</span></span> | <span data-ttu-id="e57e8-152">説明</span><span class="sxs-lookup"><span data-stu-id="e57e8-152">Description</span></span> 
:---|:---
<span data-ttu-id="e57e8-153">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="e57e8-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="e57e8-154">今日の脅威から 365 Office全体を保護するのに役立ちます</span><span class="sxs-lookup"><span data-stu-id="e57e8-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="e57e8-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="e57e8-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="e57e8-156">侵害された ID と悪意のあるインサイダーアクションに対する脅威を特定し、検出します。</span><span class="sxs-lookup"><span data-stu-id="e57e8-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="e57e8-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e57e8-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="e57e8-158">豊富な可視性を提供し、データの移動を制御し、クラウド サービス全体でサイバー脅威を検出します。</span><span class="sxs-lookup"><span data-stu-id="e57e8-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="e57e8-159">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e57e8-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="e57e8-160">包括的なエンドポイント セキュリティを使用して、高度な脅威に対する対応機能を防止、検出、および提供します。</span><span class="sxs-lookup"><span data-stu-id="e57e8-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="e57e8-161">スコープ内</span><span class="sxs-lookup"><span data-stu-id="e57e8-161">In scope</span></span>

<span data-ttu-id="e57e8-162">このガイドでは、以下のタスクを対象とします。</span><span class="sxs-lookup"><span data-stu-id="e57e8-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="e57e8-163">Azure Active Directory をセットアップする</span><span class="sxs-lookup"><span data-stu-id="e57e8-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="e57e8-164">Microsoft 365 Defender のセットアップ</span><span class="sxs-lookup"><span data-stu-id="e57e8-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="e57e8-165">Microsoft 365 E5 試用版にサインアップするか、パイロットを実行している場合は完全なライセンスを使用する</span><span class="sxs-lookup"><span data-stu-id="e57e8-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="e57e8-166">ドメインを構成する</span><span class="sxs-lookup"><span data-stu-id="e57e8-166">Configure domain</span></span>
    -   <span data-ttu-id="e57e8-167">Microsoft 365 E5 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e57e8-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="e57e8-168">ポータル内でセットアップ ウィザードを完了する</span><span class="sxs-lookup"><span data-stu-id="e57e8-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="e57e8-169">ベスト プラクティスに基づいてすべての Microsoft 365 Defender の柱を構成する</span><span class="sxs-lookup"><span data-stu-id="e57e8-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="e57e8-170">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="e57e8-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="e57e8-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="e57e8-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="e57e8-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e57e8-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="e57e8-173">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e57e8-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="e57e8-174">対象外</span><span class="sxs-lookup"><span data-stu-id="e57e8-174">Out of scope</span></span>

<span data-ttu-id="e57e8-175">この展開ガイドの対象範囲を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e57e8-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="e57e8-176">Microsoft 365 Defender と統合される可能性があるサード パーティ製ソリューションの構成</span><span class="sxs-lookup"><span data-stu-id="e57e8-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="e57e8-177">実稼働環境での侵入テスト</span><span class="sxs-lookup"><span data-stu-id="e57e8-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="e57e8-178">次の手順</span><span class="sxs-lookup"><span data-stu-id="e57e8-178">Next step</span></span>
<span data-ttu-id="e57e8-179">[フェーズ 1: 準備](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="e57e8-179">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="e57e8-180">Microsoft 365 Defender 試用版ラボまたはパイロット環境を準備する</span><span class="sxs-lookup"><span data-stu-id="e57e8-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
