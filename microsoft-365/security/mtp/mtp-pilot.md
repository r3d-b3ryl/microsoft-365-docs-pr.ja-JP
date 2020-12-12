---
title: パイロット Microsoft 365 Defender プロジェクトを実行する
description: 実稼働環境で Microsoft 365 Defender のパイロット プロジェクトを実行し、Microsoft 365 Defender のメリットと導入を効果的に決定します。
keywords: Microsoft Threat Protection パイロット、パイロット Microsoft Threat Protection プロジェクトの実行、Microsoft Threat Protection の実稼働での Microsoft Threat Protection の評価、Microsoft Threat Protection パイロット プロジェクト、サイバー セキュリティ、高度な持続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な捜ティング
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
ms.openlocfilehash: f01e918d35ce77d9239c200355c7b4c48c9e2b84
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659323"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="16bb9-104">パイロット Microsoft 365 Defender プロジェクトを実行する</span><span class="sxs-lookup"><span data-stu-id="16bb9-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="16bb9-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="16bb9-105">**Applies to:**</span></span>
- <span data-ttu-id="16bb9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16bb9-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="16bb9-107">このガイドは、十分に構造化された計画を立て、攻撃シミュレーション機能を使用してパイロットを終了し、最終的にパイロットを終了して結果を反映および文書化することにより、パイロット プロジェクトを実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="16bb9-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Microsoft 365 Defender パイロットの実行のフェーズ](../../media/pilotphases.png)


<span data-ttu-id="16bb9-109">パイロットを実行すると、Microsoft 365 Defender を導入するメリットを効果的に判断できます。</span><span class="sxs-lookup"><span data-stu-id="16bb9-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="16bb9-110">実稼働環境で Microsoft 365 Defender を有効にし、使用例を開始する前に、パイロット プロジェクトで実行するタスクを決定し、成功基準を設定する計画を立ておきます。</span><span class="sxs-lookup"><span data-stu-id="16bb9-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="16bb9-111">このパイロット プレイブックの使い方</span><span class="sxs-lookup"><span data-stu-id="16bb9-111">How to use this pilot playbook</span></span>

<span data-ttu-id="16bb9-112">このガイドでは、Microsoft 365 Defender の概要と、パイロット プロジェクトのセットアップ方法に関する詳細な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="16bb9-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="16bb9-113">Microsoft 365 Defender は、高度な攻撃に対する統合された保護を提供するために、エンドポイント、ID、電子メール、アプリケーション間で保護、検出、防止、調査、応答をネイティブに調整する、侵害前および侵害後の統合エンタープライズ防御スイートです。</span><span class="sxs-lookup"><span data-stu-id="16bb9-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="16bb9-114">これは、次の機能を組み合わせて 1 つのセキュリティ ソリューションに統合することで実現されます。</span><span class="sxs-lookup"><span data-stu-id="16bb9-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="16bb9-115">Microsoft Defender for Endpoint、Microsoft Defender Advanced Threat Protection (エンドポイント) の新しい名前</span><span class="sxs-lookup"><span data-stu-id="16bb9-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="16bb9-116">Microsoft Defender for Office 365、 Office 365 ATP の新しい名前 (メール)</span><span class="sxs-lookup"><span data-stu-id="16bb9-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="16bb9-117">Microsoft Defender for Identity、Azure ATP (ID) の新しい名前</span><span class="sxs-lookup"><span data-stu-id="16bb9-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="16bb9-118">Microsoft Cloud App Security (アプリ)</span><span class="sxs-lookup"><span data-stu-id="16bb9-118">Microsoft Cloud App Security (apps)</span></span>

![ユーザー向of_Microsoft 365 Defender ソリューション、Id 用 Microsoft Defender、エンドポイント用の Microsoft Defender for Endpoint、クラウド アプリ、Microsoft Cloud App Security、データ用の Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="16bb9-120">統合された Microsoft 365 Defender ソリューションを使用すると、セキュリティ担当者は、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity、および Microsoft Cloud App Security が受け取る脅威シグナルをまとめ、脅威の全範囲と影響、環境にどのような影響を与え、現在組織に影響を与えているかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="16bb9-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="16bb9-121">Microsoft 365 Defender は、攻撃を防止または停止し、影響を受けるメールボックス、エンドポイント、ユーザー ID を自己回復する自動アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="16bb9-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="16bb9-122">詳細については [、Microsoft 365 Defender の概要](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16bb9-122">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>



<span data-ttu-id="16bb9-123">次のサンプル タイムラインは、環境に適切なリソースがある場合に異なります。</span><span class="sxs-lookup"><span data-stu-id="16bb9-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="16bb9-124">検出とワークフローによっては、他の検出とワークフローよりも多くの学習時間が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="16bb9-124">Some detections and workflows might need more learning time than the others.</span></span>

![Microsoft 365 Defender パイロットの実行に関するサンプル タイムライン](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="16bb9-126">最適な結果を得る場合は、パイロットの指示にできる限り近い手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="16bb9-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="16bb9-127">パイロット プレイブックフェーズ</span><span class="sxs-lookup"><span data-stu-id="16bb9-127">Pilot playbook phases</span></span> 

<span data-ttu-id="16bb9-128">Microsoft 365 Defender パイロットの実行には、次の 4 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="16bb9-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="16bb9-129">フェーズ</span><span class="sxs-lookup"><span data-stu-id="16bb9-129">Phase</span></span> | <span data-ttu-id="16bb9-130">内容</span><span class="sxs-lookup"><span data-stu-id="16bb9-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="16bb9-131">計画</span><span class="sxs-lookup"><span data-stu-id="16bb9-131">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="16bb9-132">~ 1 日</span><span class="sxs-lookup"><span data-stu-id="16bb9-132">~ 1 day</span></span>| <span data-ttu-id="16bb9-133">Microsoft 365 Defender パイロット プロジェクトを実行する前に考慮する必要がある点について説明します。</span><span class="sxs-lookup"><span data-stu-id="16bb9-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="16bb9-134">- スコープ</span><span class="sxs-lookup"><span data-stu-id="16bb9-134">- Scope</span></span> <br> <span data-ttu-id="16bb9-135">- 使用事例</span><span class="sxs-lookup"><span data-stu-id="16bb9-135">- Use cases</span></span> <br><span data-ttu-id="16bb9-136">- 要件</span><span class="sxs-lookup"><span data-stu-id="16bb9-136">- Requirements</span></span> <br><span data-ttu-id="16bb9-137">- テスト計画</span><span class="sxs-lookup"><span data-stu-id="16bb9-137">- Test plan</span></span> <br> <span data-ttu-id="16bb9-138">- 成功条件</span><span class="sxs-lookup"><span data-stu-id="16bb9-138">- Success criteria</span></span> <br> <span data-ttu-id="16bb9-139">- スコアカード</span><span class="sxs-lookup"><span data-stu-id="16bb9-139">- Scorecard</span></span> 
| [<span data-ttu-id="16bb9-140">準備</span><span class="sxs-lookup"><span data-stu-id="16bb9-140">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="16bb9-141">~2 日</span><span class="sxs-lookup"><span data-stu-id="16bb9-141">~2 days</span></span>|  <span data-ttu-id="16bb9-142">Microsoft 365 セキュリティ センターにアクセスして、Microsoft 365 Defender パイロット環境をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="16bb9-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="16bb9-143">次のガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="16bb9-143">You'll be guided to:</span></span><br><br><span data-ttu-id="16bb9-144">- 関係者を特定し、パイロットのサインオフを求める</span><span class="sxs-lookup"><span data-stu-id="16bb9-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="16bb9-145">- 環境に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="16bb9-145">- Environment considerations</span></span> <br><span data-ttu-id="16bb9-146">- Access</span><span class="sxs-lookup"><span data-stu-id="16bb9-146">- Access</span></span> <br><span data-ttu-id="16bb9-147">- Azure Active Directory のセットアップ</span><span class="sxs-lookup"><span data-stu-id="16bb9-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="16bb9-148">- 構成順序</span><span class="sxs-lookup"><span data-stu-id="16bb9-148">- Configuration order</span></span> <br> <span data-ttu-id="16bb9-149">- Microsoft 365 E5 試用版にサインアップする</span><span class="sxs-lookup"><span data-stu-id="16bb9-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="16bb9-150">- ドメインを構成する</span><span class="sxs-lookup"><span data-stu-id="16bb9-150">- Configure domain</span></span> <br><span data-ttu-id="16bb9-151">- Microsoft 365 E5 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="16bb9-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="16bb9-152">- ポータルでセットアップ ウィザードを完了する</span><span class="sxs-lookup"><span data-stu-id="16bb9-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="16bb9-153">攻撃シミュレーション</span><span class="sxs-lookup"><span data-stu-id="16bb9-153">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="16bb9-154">~2 日</span><span class="sxs-lookup"><span data-stu-id="16bb9-154">~2 days</span></span>| <span data-ttu-id="16bb9-155">攻撃をシミュレートするには、次のガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="16bb9-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="16bb9-156">- テスト環境の要件を確認する</span><span class="sxs-lookup"><span data-stu-id="16bb9-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="16bb9-157">- シミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="16bb9-157">-  Run the simulation</span></span> <br><span data-ttu-id="16bb9-158">- インシデントを調査する</span><span class="sxs-lookup"><span data-stu-id="16bb9-158">- Investigate an incident</span></span> <br><span data-ttu-id="16bb9-159">- インシデントを解決する</span><span class="sxs-lookup"><span data-stu-id="16bb9-159">- resolve the incident</span></span> 
| [<span data-ttu-id="16bb9-160">終了と概要</span><span class="sxs-lookup"><span data-stu-id="16bb9-160">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="16bb9-161">~ 1 日</span><span class="sxs-lookup"><span data-stu-id="16bb9-161">~ 1 day</span></span>| <span data-ttu-id="16bb9-162">プロセスの最後に到達すると、次のガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="16bb9-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="16bb9-163">- 最終的な出力を確認する</span><span class="sxs-lookup"><span data-stu-id="16bb9-163">- Go through your final output</span></span><br><span data-ttu-id="16bb9-164">- 関係者に出力を表示する</span><span class="sxs-lookup"><span data-stu-id="16bb9-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="16bb9-165">- フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="16bb9-165">- Provide feedback</span></span> <br><span data-ttu-id="16bb9-166">- 次の手順を実行する</span><span class="sxs-lookup"><span data-stu-id="16bb9-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="16bb9-167">次の手順</span><span class="sxs-lookup"><span data-stu-id="16bb9-167">Next step</span></span>
|[<span data-ttu-id="16bb9-168">計画フェーズ</span><span class="sxs-lookup"><span data-stu-id="16bb9-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="16bb9-169">Microsoft 365 Defender パイロット プロジェクトを計画する</span><span class="sxs-lookup"><span data-stu-id="16bb9-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
