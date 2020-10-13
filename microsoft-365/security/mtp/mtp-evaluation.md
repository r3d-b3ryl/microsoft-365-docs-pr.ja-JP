---
title: Microsoft Threat Protection を評価する
description: 組織内のデバイス、id、データ、およびアプリケーションを保護するために設計されたセキュリティソリューションを体験して、Microsoft の脅威保護の試用ラボまたはパイロット環境を設定します。
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
ms.openlocfilehash: d3f63c8ac4ba82a80c365dce564bbd8d3dd4da4b
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447121"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="6926a-104">Microsoft の脅威保護の試用ラボまたはパイロット環境を作成する</span><span class="sxs-lookup"><span data-stu-id="6926a-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6926a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6926a-105">**Applies to:**</span></span>
- <span data-ttu-id="6926a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6926a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="6926a-107">この試用版またはパイロット環境を作成する目的は、包括的かつ統合された Microsoft の脅威保護機能を理解することです。</span><span class="sxs-lookup"><span data-stu-id="6926a-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="6926a-108">このインテリジェントセキュリティソリューションが組織に対する高度な脅威を検出、阻止、自動調査、および応答する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6926a-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="6926a-109">このガイドでは、推奨される展開パスに基づいて Microsoft の脅威保護評価を開始する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="6926a-109">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="6926a-110">ここでの目的は、試用版アカウントを使用したラボ環境で、または完全ライセンスを使用した運用環境で、セキュリティソリューションをセットアップできるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="6926a-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="6926a-111">試用ラボまたはパイロット環境の準備は、組織の意思決定者にセキュリティ操作の使用ケースを提示するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6926a-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="6926a-112">攻撃のシミュレーションの実行が完了し、結果に問題がなければ、組織内の Microsoft テクニカルセールス担当者または専門家と協力して、組織内で operationalize it を完全に展開し、その結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="6926a-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="6926a-113">このガイドは、次のことを支援します。</span><span class="sxs-lookup"><span data-stu-id="6926a-113">This guide will help you:</span></span>
- <span data-ttu-id="6926a-114">ラボサーバーとコンピューターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="6926a-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="6926a-115">ユーザーおよびグループを使用して Active Directory を構成する</span><span class="sxs-lookup"><span data-stu-id="6926a-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="6926a-116">Azure ATP、Office ATP、Microsoft Defender ATP、および Microsoft Cloud App Security を設定および構成する</span><span class="sxs-lookup"><span data-stu-id="6926a-116">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="6926a-117">サーバーとコンピューターのローカルポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="6926a-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="6926a-118">Microsoft の脅威保護でテストインシデントまたはアラートを生成する脅威攻撃を模倣する</span><span class="sxs-lookup"><span data-stu-id="6926a-118">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="6926a-119">最適な結果を得るには、演習のセットアップの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="6926a-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="6926a-120">展開フェーズ</span><span class="sxs-lookup"><span data-stu-id="6926a-120">Deployment phases</span></span>

<span data-ttu-id="6926a-121">Microsoft の脅威保護のテスト環境を作成して展開するには、3つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="6926a-121">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="6926a-122">フェーズ</span><span class="sxs-lookup"><span data-stu-id="6926a-122">Phase</span></span> | <span data-ttu-id="6926a-123">説明</span><span class="sxs-lookup"><span data-stu-id="6926a-123">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="6926a-124">![フェーズ 1: 準備](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="6926a-124">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="6926a-125">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="6926a-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="6926a-126">マイクロソフトの脅威保護を試用ラボまたはパイロット環境に展開するときに考慮する必要があることについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6926a-126">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="6926a-127">-関係者と承認</span><span class="sxs-lookup"><span data-stu-id="6926a-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="6926a-128">-環境に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="6926a-128">- Environment considerations</span></span> <br><span data-ttu-id="6926a-129">-アクセス</span><span class="sxs-lookup"><span data-stu-id="6926a-129">- Access</span></span> <br><span data-ttu-id="6926a-130">-Azure Active Directory のセットアップ</span><span class="sxs-lookup"><span data-stu-id="6926a-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="6926a-131">-構成の順序</span><span class="sxs-lookup"><span data-stu-id="6926a-131">- Configuration order</span></span>
|  <span data-ttu-id="6926a-132">![フェーズ 2: セットアップ](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="6926a-132">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="6926a-133">フェーズ 2: セットアップ</span><span class="sxs-lookup"><span data-stu-id="6926a-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="6926a-134">最初の手順を実行して、microsoft 365 セキュリティセンターにアクセスし、Microsoft の脅威保護の試用ラボまたはパイロット環境をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="6926a-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="6926a-135">次のようなガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6926a-135">You'll be guided to:</span></span><br><br><span data-ttu-id="6926a-136">-Microsoft 365 E5 試用版にサインアップする</span><span class="sxs-lookup"><span data-stu-id="6926a-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="6926a-137">-ドメインの構成</span><span class="sxs-lookup"><span data-stu-id="6926a-137">- Configure domain</span></span><br><span data-ttu-id="6926a-138">-Microsoft 365 E5 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6926a-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="6926a-139">-ポータルのセットアップウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="6926a-139">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="6926a-140">![フェーズ 3: 構成 & オンボード](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="6926a-140">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="6926a-141">フェーズ 3: 構成 & オンボード</span><span class="sxs-lookup"><span data-stu-id="6926a-141">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="6926a-142">Microsoft の各脅威保護の柱とオンボードエンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="6926a-142">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="6926a-143">次のようなガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6926a-143">You'll be guided to:</span></span><br><br><span data-ttu-id="6926a-144">-Office 365 Advanced Threat Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="6926a-144">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="6926a-145">-Microsoft Cloud App Security を構成する</span><span class="sxs-lookup"><span data-stu-id="6926a-145">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="6926a-146">-Azure Advanced Threat Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="6926a-146">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="6926a-147">-Microsoft Defender Advanced Threat Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="6926a-147">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="6926a-148">範囲内</span><span class="sxs-lookup"><span data-stu-id="6926a-148">In scope</span></span>

<span data-ttu-id="6926a-149">このガイドの対象となるタスクは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6926a-149">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="6926a-150">Azure Active Directory をセットアップする</span><span class="sxs-lookup"><span data-stu-id="6926a-150">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="6926a-151">Microsoft の脅威保護をセットアップする</span><span class="sxs-lookup"><span data-stu-id="6926a-151">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="6926a-152">パイロットを実行している場合は、Microsoft 365 E5 試用版にサインアップするか、完全ライセンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="6926a-152">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="6926a-153">ドメインを構成する</span><span class="sxs-lookup"><span data-stu-id="6926a-153">Configure domain</span></span>
    -   <span data-ttu-id="6926a-154">Microsoft 365 E5 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6926a-154">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="6926a-155">ポータル内のセットアップウィザードの完了</span><span class="sxs-lookup"><span data-stu-id="6926a-155">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="6926a-156">ベストプラクティスに基づいてすべての Microsoft 脅威保護の柱を構成する</span><span class="sxs-lookup"><span data-stu-id="6926a-156">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="6926a-157">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6926a-157">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="6926a-158">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6926a-158">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="6926a-159">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6926a-159">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="6926a-160">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6926a-160">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="6926a-161">対象外</span><span class="sxs-lookup"><span data-stu-id="6926a-161">Out of scope</span></span>

<span data-ttu-id="6926a-162">この展開ガイドの範囲外のものを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="6926a-162">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="6926a-163">Microsoft の脅威保護と統合される可能性があるサードパーティ製のソリューションの構成</span><span class="sxs-lookup"><span data-stu-id="6926a-163">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="6926a-164">運用環境でのペネトレーションテスト</span><span class="sxs-lookup"><span data-stu-id="6926a-164">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="6926a-165">次のステップ</span><span class="sxs-lookup"><span data-stu-id="6926a-165">Next step</span></span>
<span data-ttu-id="6926a-166">![フェーズ 1: 準備](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="6926a-166">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="6926a-167">[フェーズ 1: 準備](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="6926a-167">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="6926a-168">Microsoft の脅威保護の試用ラボまたはパイロット環境の準備</span><span class="sxs-lookup"><span data-stu-id="6926a-168">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
