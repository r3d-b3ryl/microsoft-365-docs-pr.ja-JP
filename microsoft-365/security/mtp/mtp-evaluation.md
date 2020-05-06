---
title: Microsoft の脅威保護を評価する
description: Microsoft の脅威保護の試用ラボ環境をセットアップして、デバイス、id、データ、およびアプリケーションを保護するために設計された調整脅威保護ソリューションが組織にどのように役立つかを確認します。
keywords: Microsoft Threat Protection の試用版、microsoft の脅威保護の評価、microsoft の脅威保護評価ラボ、サイバーセキュリティ、高度な脅威、エンタープライズセキュリティ、デバイス、デバイス、id、ユーザー、データ、アプリケーション、インシデント、自動化された調査と修復、高度な検索
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: f6ee8147965a29b87d84690535116f096e4c6006
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049641"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="341c8-104">Microsoft の脅威保護のテスト環境を作成する</span><span class="sxs-lookup"><span data-stu-id="341c8-104">Create a Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="341c8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="341c8-105">**Applies to:**</span></span>
- <span data-ttu-id="341c8-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="341c8-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="341c8-107">この試用版ラボ環境を作成する目的は、組織で使用できる検出、防止、調査、および応答に関する Microsoft の脅威保護の総合的かつ統合化された機能を説明することです。</span><span class="sxs-lookup"><span data-stu-id="341c8-107">The purpose of creating this trial lab environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="341c8-108">このガイドでは、推奨される展開パスに基づいて Microsoft の脅威保護評価を開始する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="341c8-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="341c8-109">目標は、組織のセキュリティソリューション意思決定者に提示する際に、統合された Microsoft Threat Protection サービスをラボ環境で設定したり、概念実証 (POC) として設定したりするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="341c8-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment or as a proof of concept (POC) when presenting to security solution decision makers in your organization.</span></span> <span data-ttu-id="341c8-110">攻撃のシミュレーション、自動化された調査、および応答を実行し、結果に満足している場合は、Microsoft テクニカルセールス担当者または組織内の専門家と協力して運用環境に展開できます。</span><span class="sxs-lookup"><span data-stu-id="341c8-110">When you’re done running your attack simulations, automated investigation and response, and are satisfied with the results, you can deploy it in your production environment with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="341c8-111">このガイドは、次のことを支援します。</span><span class="sxs-lookup"><span data-stu-id="341c8-111">This guide will help you:</span></span>
- <span data-ttu-id="341c8-112">ラボサーバーとコンピューターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="341c8-112">Set up your lab server and computers</span></span>
- <span data-ttu-id="341c8-113">ユーザーおよびグループを使用して Active Directory を構成する</span><span class="sxs-lookup"><span data-stu-id="341c8-113">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="341c8-114">Azure ATP、Office ATP、Microsoft Defender ATP、および Microsoft Cloud App Security を設定および構成する</span><span class="sxs-lookup"><span data-stu-id="341c8-114">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="341c8-115">サーバーとコンピューターのローカルポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="341c8-115">Setup local policies for your server and computers</span></span>
- <span data-ttu-id="341c8-116">Microsoft の脅威保護でテストインシデントまたはアラートを生成する脅威攻撃を模倣する</span><span class="sxs-lookup"><span data-stu-id="341c8-116">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="341c8-117">最適な結果を得るには、演習のセットアップの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="341c8-117">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="341c8-118">展開フェーズ</span><span class="sxs-lookup"><span data-stu-id="341c8-118">Deployment phases</span></span>

<span data-ttu-id="341c8-119">Microsoft の脅威保護のテスト環境を作成して展開するには、3つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="341c8-119">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="341c8-120">フェーズ</span><span class="sxs-lookup"><span data-stu-id="341c8-120">Phase</span></span> | <span data-ttu-id="341c8-121">説明</span><span class="sxs-lookup"><span data-stu-id="341c8-121">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="341c8-122">![フェーズ 1: 準備](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="341c8-122">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="341c8-123">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="341c8-123">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="341c8-124">マイクロソフトの脅威保護を試用ラボ環境に展開するときに考慮する必要があることについて説明します。</span><span class="sxs-lookup"><span data-stu-id="341c8-124">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab environment:</span></span> <br><br><span data-ttu-id="341c8-125">-関係者と承認</span><span class="sxs-lookup"><span data-stu-id="341c8-125">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="341c8-126">-環境に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="341c8-126">- Environment considerations</span></span> <br><span data-ttu-id="341c8-127">-アクセス</span><span class="sxs-lookup"><span data-stu-id="341c8-127">- Access</span></span> <br><span data-ttu-id="341c8-128">-Azure Active Directory のセットアップ</span><span class="sxs-lookup"><span data-stu-id="341c8-128">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="341c8-129">-構成の順序</span><span class="sxs-lookup"><span data-stu-id="341c8-129">- Configuration order</span></span>
|  <span data-ttu-id="341c8-130">![フェーズ 2: セットアップ](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="341c8-130">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="341c8-131">フェーズ 2: セットアップ</span><span class="sxs-lookup"><span data-stu-id="341c8-131">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="341c8-132">最初の手順を実行して、microsoft 365 セキュリティセンターにアクセスし、Microsoft の脅威保護のテスト環境をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="341c8-132">Take the initial steps to access Microsoft 365 Security Center to setup your Microsoft Threat Protection trial lab environment.</span></span> <span data-ttu-id="341c8-133">次のようなガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="341c8-133">You will be guided to:</span></span><br><br><span data-ttu-id="341c8-134">-Microsoft 365 E5 試用版にサインアップする</span><span class="sxs-lookup"><span data-stu-id="341c8-134">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="341c8-135">-ドメインの構成</span><span class="sxs-lookup"><span data-stu-id="341c8-135">- Configure domain</span></span><br><span data-ttu-id="341c8-136">-Microsoft 365 E5 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="341c8-136">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="341c8-137">-ポータルのセットアップウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="341c8-137">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="341c8-138">![フェーズ 3: 構成 & オンボード](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="341c8-138">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="341c8-139">フェーズ 3: 構成 & オンボード</span><span class="sxs-lookup"><span data-stu-id="341c8-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="341c8-140">Microsoft の各脅威保護の柱とオンボードエンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="341c8-140">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="341c8-141">次のようなガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="341c8-141">You will be guided to:</span></span><br><br><span data-ttu-id="341c8-142">-Office 365 Advanced Threat Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="341c8-142">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="341c8-143">-Microsoft Cloud App Security を構成する</span><span class="sxs-lookup"><span data-stu-id="341c8-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="341c8-144">-Azure Advanced Threat Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="341c8-144">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="341c8-145">-Microsoft Defender Advanced Threat Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="341c8-145">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="341c8-146">範囲内</span><span class="sxs-lookup"><span data-stu-id="341c8-146">In scope</span></span>

<span data-ttu-id="341c8-147">この試用版ラボ環境ガイドの範囲は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="341c8-147">The following is in scope for this trial lab environment guide:</span></span>
-   <span data-ttu-id="341c8-148">Azure Active Directory をセットアップする</span><span class="sxs-lookup"><span data-stu-id="341c8-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="341c8-149">Microsoft の脅威保護をセットアップする</span><span class="sxs-lookup"><span data-stu-id="341c8-149">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="341c8-150">Microsoft 365 E5 試用版にサインアップする</span><span class="sxs-lookup"><span data-stu-id="341c8-150">Sign up for Microsoft 365 E5 Trial</span></span>
    -   <span data-ttu-id="341c8-151">ドメインを構成する</span><span class="sxs-lookup"><span data-stu-id="341c8-151">Configure domain</span></span>
    -   <span data-ttu-id="341c8-152">Microsoft 365 E5 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="341c8-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="341c8-153">ポータル内のセットアップウィザードの完了</span><span class="sxs-lookup"><span data-stu-id="341c8-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="341c8-154">ベストプラクティスに基づいてすべての Microsoft 脅威保護の柱を構成する</span><span class="sxs-lookup"><span data-stu-id="341c8-154">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="341c8-155">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="341c8-155">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="341c8-156">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="341c8-156">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="341c8-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="341c8-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="341c8-158">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="341c8-158">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="341c8-159">対象外</span><span class="sxs-lookup"><span data-stu-id="341c8-159">Out of scope</span></span>

<span data-ttu-id="341c8-160">この展開ガイドの範囲外のものを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="341c8-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="341c8-161">Microsoft Defender ATP と統合される可能性があるサードパーティ製のソリューションの構成</span><span class="sxs-lookup"><span data-stu-id="341c8-161">Configuration of third-party solutions that might integrate with Microsoft Defender ATP</span></span>
-   <span data-ttu-id="341c8-162">運用環境でのペネトレーションテスト</span><span class="sxs-lookup"><span data-stu-id="341c8-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="341c8-163">次の手順</span><span class="sxs-lookup"><span data-stu-id="341c8-163">Next step</span></span>
|||
|:-------|:-----|
|<span data-ttu-id="341c8-164">![フェーズ 1: 準備](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="341c8-164">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br>[<span data-ttu-id="341c8-165">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="341c8-165">Phase 1: Prepare</span></span>](prepare-mtpeval.md) | <span data-ttu-id="341c8-166">Microsoft の脅威保護評価ラボ環境の準備</span><span class="sxs-lookup"><span data-stu-id="341c8-166">Prepare your Microsoft Threat Protection evaluation lab environment</span></span>
