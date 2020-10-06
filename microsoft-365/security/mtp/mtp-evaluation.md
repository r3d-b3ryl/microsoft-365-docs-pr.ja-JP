---
title: Microsoft Threat Protection を評価する
description: Microsoft の脅威保護の試用ラボまたはパイロット環境をセットアップして、デバイス、id、データ、およびアプリケーションを保護するために設計された調整脅威保護ソリューションが組織にどのように役立つかを確認します。
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 3768937fc882fee8d6a744e4fb504095882c7e81
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368061"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="39939-104">Microsoft の脅威保護の試用ラボまたはパイロット環境を作成する</span><span class="sxs-lookup"><span data-stu-id="39939-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="39939-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="39939-105">**Applies to:**</span></span>
- <span data-ttu-id="39939-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="39939-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="39939-107">この試用版またはパイロット環境を作成する目的は、Microsoft の脅威保護に関する総合的かつ統合されたインテリジェントな機能を示しています。これは、組織で使用できる検出、防止、調査、および応答に関するものです。</span><span class="sxs-lookup"><span data-stu-id="39939-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="39939-108">このガイドでは、推奨される展開パスに基づいて Microsoft の脅威保護評価を開始する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="39939-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="39939-109">目標は、完全なライセンスを使用している場合に、試用版のアカウントを使用するとき、または運用環境で試験環境で統合された Microsoft Threat Protection サービスをセットアップするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39939-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment when using a trial account, or in a pilot environment in production when using a full license.</span></span> <span data-ttu-id="39939-110">の結果は、組織内のセキュリティソリューションの意思決定者にセキュリティ操作のユースケースを提示するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39939-110">The results of which will be useful in presenting security operation use cases to security solution decision makers in your organization.</span></span> <span data-ttu-id="39939-111">攻撃のシミュレーションを実行し、結果に問題がなければ、組織内の Microsoft テクニカルセールス担当者または専門家と協力して、組織内で operationalize it を完全に展開し、それを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="39939-111">When you’re done running your attack simulations, and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="39939-112">このガイドは、次のことを支援します。</span><span class="sxs-lookup"><span data-stu-id="39939-112">This guide will help you:</span></span>
- <span data-ttu-id="39939-113">ラボサーバーとコンピューターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="39939-113">Set up your lab server and computers</span></span>
- <span data-ttu-id="39939-114">ユーザーおよびグループを使用して Active Directory を構成する</span><span class="sxs-lookup"><span data-stu-id="39939-114">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="39939-115">Azure ATP、Office ATP、Microsoft Defender ATP、および Microsoft Cloud App Security を設定および構成する</span><span class="sxs-lookup"><span data-stu-id="39939-115">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="39939-116">サーバーとコンピューターのローカルポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="39939-116">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="39939-117">Microsoft の脅威保護でテストインシデントまたはアラートを生成する脅威攻撃を模倣する</span><span class="sxs-lookup"><span data-stu-id="39939-117">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="39939-118">最適な結果を得るには、演習のセットアップの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="39939-118">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="39939-119">展開フェーズ</span><span class="sxs-lookup"><span data-stu-id="39939-119">Deployment phases</span></span>

<span data-ttu-id="39939-120">Microsoft の脅威保護のテスト環境を作成して展開するには、3つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="39939-120">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="39939-121">フェーズ</span><span class="sxs-lookup"><span data-stu-id="39939-121">Phase</span></span> | <span data-ttu-id="39939-122">説明</span><span class="sxs-lookup"><span data-stu-id="39939-122">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="39939-123">![フェーズ 1: 準備](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="39939-123">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="39939-124">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="39939-124">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="39939-125">マイクロソフトの脅威保護を試用ラボまたはパイロット環境に展開するときに考慮する必要があることについて説明します。</span><span class="sxs-lookup"><span data-stu-id="39939-125">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="39939-126">-関係者と承認</span><span class="sxs-lookup"><span data-stu-id="39939-126">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="39939-127">-環境に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="39939-127">- Environment considerations</span></span> <br><span data-ttu-id="39939-128">-アクセス</span><span class="sxs-lookup"><span data-stu-id="39939-128">- Access</span></span> <br><span data-ttu-id="39939-129">-Azure Active Directory のセットアップ</span><span class="sxs-lookup"><span data-stu-id="39939-129">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="39939-130">-構成の順序</span><span class="sxs-lookup"><span data-stu-id="39939-130">- Configuration order</span></span>
|  <span data-ttu-id="39939-131">![フェーズ 2: セットアップ](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="39939-131">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="39939-132">フェーズ 2: セットアップ</span><span class="sxs-lookup"><span data-stu-id="39939-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="39939-133">最初の手順を実行して、microsoft 365 セキュリティセンターにアクセスし、Microsoft の脅威保護の試用ラボまたはパイロット環境をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="39939-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="39939-134">次のようなガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39939-134">You'll be guided to:</span></span><br><br><span data-ttu-id="39939-135">-Microsoft 365 E5 試用版にサインアップする</span><span class="sxs-lookup"><span data-stu-id="39939-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="39939-136">-ドメインの構成</span><span class="sxs-lookup"><span data-stu-id="39939-136">- Configure domain</span></span><br><span data-ttu-id="39939-137">-Microsoft 365 E5 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="39939-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="39939-138">-ポータルのセットアップウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="39939-138">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="39939-139">![フェーズ 3: 構成 & オンボード](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="39939-139">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="39939-140">フェーズ 3: 構成 & オンボード</span><span class="sxs-lookup"><span data-stu-id="39939-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="39939-141">Microsoft の各脅威保護の柱とオンボードエンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="39939-141">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="39939-142">次のようなガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39939-142">You'll be guided to:</span></span><br><br><span data-ttu-id="39939-143">-Office 365 Advanced Threat Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="39939-143">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="39939-144">-Microsoft Cloud App Security を構成する</span><span class="sxs-lookup"><span data-stu-id="39939-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="39939-145">-Azure Advanced Threat Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="39939-145">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="39939-146">-Microsoft Defender Advanced Threat Protection を構成する</span><span class="sxs-lookup"><span data-stu-id="39939-146">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="39939-147">範囲内</span><span class="sxs-lookup"><span data-stu-id="39939-147">In scope</span></span>

<span data-ttu-id="39939-148">このガイドの対象となるタスクは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="39939-148">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="39939-149">Azure Active Directory をセットアップする</span><span class="sxs-lookup"><span data-stu-id="39939-149">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="39939-150">Microsoft の脅威保護をセットアップする</span><span class="sxs-lookup"><span data-stu-id="39939-150">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="39939-151">パイロットを実行している場合は、Microsoft 365 E5 試用版にサインアップするか、完全ライセンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="39939-151">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="39939-152">ドメインを構成する</span><span class="sxs-lookup"><span data-stu-id="39939-152">Configure domain</span></span>
    -   <span data-ttu-id="39939-153">Microsoft 365 E5 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="39939-153">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="39939-154">ポータル内のセットアップウィザードの完了</span><span class="sxs-lookup"><span data-stu-id="39939-154">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="39939-155">ベストプラクティスに基づいてすべての Microsoft 脅威保護の柱を構成する</span><span class="sxs-lookup"><span data-stu-id="39939-155">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="39939-156">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="39939-156">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="39939-157">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="39939-157">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="39939-158">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="39939-158">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="39939-159">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="39939-159">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="39939-160">対象外</span><span class="sxs-lookup"><span data-stu-id="39939-160">Out of scope</span></span>

<span data-ttu-id="39939-161">この展開ガイドの範囲外のものを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="39939-161">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="39939-162">Microsoft の脅威保護と統合される可能性があるサードパーティ製のソリューションの構成</span><span class="sxs-lookup"><span data-stu-id="39939-162">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="39939-163">運用環境でのペネトレーションテスト</span><span class="sxs-lookup"><span data-stu-id="39939-163">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="39939-164">次のステップ</span><span class="sxs-lookup"><span data-stu-id="39939-164">Next step</span></span>
<span data-ttu-id="39939-165">![フェーズ 1: 準備](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="39939-165">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="39939-166">[フェーズ 1: 準備](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="39939-166">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="39939-167">Microsoft の脅威保護の試用ラボまたはパイロット環境の準備</span><span class="sxs-lookup"><span data-stu-id="39939-167">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
