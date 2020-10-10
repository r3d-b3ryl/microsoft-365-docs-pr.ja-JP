---
title: パイロットの Microsoft 脅威保護プロジェクトを実行する
description: 試験的な Microsoft の脅威保護プロジェクトを運用環境で実行して、Microsoft の脅威保護 (MTP) のメリットと導入を効果的に決定します。
keywords: Microsoft Threat Protection パイロット、パイロットを実行する Microsoft threat protection プロジェクトを実行する、microsoft threat protection を運用環境において評価する、Microsoft Threat Protection パイロットプロジェクト、サイバーセキュリティ、高度な永続脅威、エンタープライズセキュリティ、デバイス、デバイス、id、ユーザー、データ、アプリケーション、インシデント、自動化された調査と修復、高度な検索
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
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: af47f45ca4f3d14e835a39a334a9400002ac8560
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418075"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="2c08e-104">パイロットの Microsoft 脅威保護プロジェクトを実行する</span><span class="sxs-lookup"><span data-stu-id="2c08e-104">Run your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2c08e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2c08e-105">**Applies to:**</span></span>
- <span data-ttu-id="2c08e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2c08e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2c08e-107">Microsoft の脅威保護 (MTP) のメリットと導入を効果的に決定するために、パイロットプロジェクトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2c08e-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="2c08e-108">運用環境で Microsoft の脅威保護を有効にし、定義されたユースケースから開始する前に、計画プロセスに従って、このパイロットプロジェクトで達成する必要があるタスクを決定し、成功の基準を決定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2c08e-108">Before enabling Microsoft Threat Protection in your production environment and starting with defined use cases, it is best to go through a planning process to determine the tasks that must be accomplished in this pilot project, and the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="2c08e-109">このパイロットプレイブックの使用方法</span><span class="sxs-lookup"><span data-stu-id="2c08e-109">How to use this pilot playbook</span></span>

<span data-ttu-id="2c08e-110">このガイドでは、パイロットプロジェクトをセットアップする方法について、Microsoft の脅威保護と詳しい手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="2c08e-110">This guide provides an overview of Microsoft Threat Protection and step-by-step instructions on how to set up your pilot project.</span></span> 

![Microsoft の脅威保護パイロットを実行するフェーズ](../../media/pilotphases.png)

<span data-ttu-id="2c08e-112">次のサンプルタイムラインは、環境内に適切なリソースがあるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="2c08e-112">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="2c08e-113">一部の検出とワークフローでは、他のユーザーよりも多くの学習時間が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="2c08e-113">Some detections and workflows might need more learning time than the others.</span></span>

![Microsoft の脅威保護パイロット実行のサンプルタイムライン](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="2c08e-115">最適な結果を得るには、パイロットの手順をできるだけ忠実に実行します。</span><span class="sxs-lookup"><span data-stu-id="2c08e-115">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="2c08e-116">パイロットプレイブックのフェーズ</span><span class="sxs-lookup"><span data-stu-id="2c08e-116">Pilot playbook phases</span></span> 

<span data-ttu-id="2c08e-117">Microsoft の脅威保護パイロットの実行には、次の4つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="2c08e-117">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="2c08e-118">フェーズ</span><span class="sxs-lookup"><span data-stu-id="2c08e-118">Phase</span></span> | <span data-ttu-id="2c08e-119">説明</span><span class="sxs-lookup"><span data-stu-id="2c08e-119">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="2c08e-120">![計画](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="2c08e-120">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="2c08e-121">計画</span><span class="sxs-lookup"><span data-stu-id="2c08e-121">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="2c08e-122">Microsoft の脅威保護パイロットプロジェクトを実行する前に考慮する必要のある事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c08e-122">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="2c08e-123">-スコープ</span><span class="sxs-lookup"><span data-stu-id="2c08e-123">- Scope</span></span> <br> <span data-ttu-id="2c08e-124">-ユースケース</span><span class="sxs-lookup"><span data-stu-id="2c08e-124">- Use cases</span></span> <br><span data-ttu-id="2c08e-125">- 要件</span><span class="sxs-lookup"><span data-stu-id="2c08e-125">- Requirements</span></span> <br><span data-ttu-id="2c08e-126">-テスト計画</span><span class="sxs-lookup"><span data-stu-id="2c08e-126">- Test plan</span></span> <br> <span data-ttu-id="2c08e-127">-成功の条件</span><span class="sxs-lookup"><span data-stu-id="2c08e-127">- Success criteria</span></span> <br> <span data-ttu-id="2c08e-128">-スコアカード</span><span class="sxs-lookup"><span data-stu-id="2c08e-128">- Scorecard</span></span> 
| <span data-ttu-id="2c08e-129">![準備](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="2c08e-129">![Preparation](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="2c08e-130">準備</span><span class="sxs-lookup"><span data-stu-id="2c08e-130">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="2c08e-131">Microsoft 365 セキュリティセンターにアクセスして、Microsoft の脅威保護パイロット環境をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="2c08e-131">Access Microsoft 365 Security Center to setup your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="2c08e-132">次のようなガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c08e-132">You will be guided to:</span></span><br><br><span data-ttu-id="2c08e-133">-パイロットの関係者を特定し、承認を求める</span><span class="sxs-lookup"><span data-stu-id="2c08e-133">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="2c08e-134">-環境に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="2c08e-134">- Environment considerations</span></span> <br><span data-ttu-id="2c08e-135">-アクセス</span><span class="sxs-lookup"><span data-stu-id="2c08e-135">- Access</span></span> <br><span data-ttu-id="2c08e-136">-Azure Active Directory のセットアップ</span><span class="sxs-lookup"><span data-stu-id="2c08e-136">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="2c08e-137">-構成の順序</span><span class="sxs-lookup"><span data-stu-id="2c08e-137">- Configuration order</span></span> <br> <span data-ttu-id="2c08e-138">-Microsoft 365 E5 試用版にサインアップする</span><span class="sxs-lookup"><span data-stu-id="2c08e-138">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="2c08e-139">-ドメインの構成</span><span class="sxs-lookup"><span data-stu-id="2c08e-139">- Configure domain</span></span> <br><span data-ttu-id="2c08e-140">-Microsoft 365 E5 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2c08e-140">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="2c08e-141">-ポータルのセットアップウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="2c08e-141">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="2c08e-142">![攻撃シミュレーション](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="2c08e-142">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="2c08e-143">攻撃シミュレーション</span><span class="sxs-lookup"><span data-stu-id="2c08e-143">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="2c08e-144">攻撃をシミュレートするには、次のように指導します。</span><span class="sxs-lookup"><span data-stu-id="2c08e-144">To simulate an attack, you will be guided to:</span></span><br><br><span data-ttu-id="2c08e-145">-テスト環境の要件を確認する</span><span class="sxs-lookup"><span data-stu-id="2c08e-145">- Verify the test environment requirements</span></span> <br><span data-ttu-id="2c08e-146">-シミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="2c08e-146">-  Run the simulation</span></span> <br><span data-ttu-id="2c08e-147">-インシデントを調査する</span><span class="sxs-lookup"><span data-stu-id="2c08e-147">- Investigate an incident</span></span> <br><span data-ttu-id="2c08e-148">-インシデントを解決する</span><span class="sxs-lookup"><span data-stu-id="2c08e-148">- resolve the incident</span></span> 
| <span data-ttu-id="2c08e-149">![決算と概要](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="2c08e-149">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="2c08e-150">決算と概要</span><span class="sxs-lookup"><span data-stu-id="2c08e-150">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="2c08e-151">プロセスの最後に達すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2c08e-151">When you've reached the end of the process, you will be guided to:</span></span><br><br><span data-ttu-id="2c08e-152">-最終出力に進む</span><span class="sxs-lookup"><span data-stu-id="2c08e-152">- Go through your final output</span></span><br><span data-ttu-id="2c08e-153">-利害関係者への出力を提示する</span><span class="sxs-lookup"><span data-stu-id="2c08e-153">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="2c08e-154">-フィードバックを提供する</span><span class="sxs-lookup"><span data-stu-id="2c08e-154">- Provide feedback</span></span> <br><span data-ttu-id="2c08e-155">-次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2c08e-155">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="2c08e-156">次のステップ</span><span class="sxs-lookup"><span data-stu-id="2c08e-156">Next step</span></span>
|<span data-ttu-id="2c08e-157">![計画フェーズ](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="2c08e-157">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="2c08e-158">計画フェーズ</span><span class="sxs-lookup"><span data-stu-id="2c08e-158">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="2c08e-159">Microsoft の脅威保護パイロットプロジェクトを計画する</span><span class="sxs-lookup"><span data-stu-id="2c08e-159">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
