---
title: パイロット Microsoft 365 Defender プロジェクトを実行する
description: Microsoft 365 Defender のメリットと導入を効果的に判断するには、パイロット Microsoft 365 Defender プロジェクトを実稼働環境で実行します。
keywords: Microsoft Threat Protection パイロット、パイロット Microsoft Threat Protection プロジェクトの実行、実稼働での Microsoft Threat Protection の評価、Microsoft Threat Protection パイロット プロジェクト、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な狩猟
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
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1dd310d962cbce2b339cf09d5be6317c227d3f13
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068251"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="362a4-104">パイロット Microsoft 365 Defender プロジェクトを実行する</span><span class="sxs-lookup"><span data-stu-id="362a4-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="362a4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="362a4-105">**Applies to:**</span></span>
- <span data-ttu-id="362a4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="362a4-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="362a4-107">このガイドは、パイロット プロジェクトを実行する場合に役立ちます。ポインターを使用して、適切に構造化された計画を作成し、攻撃シミュレーション機能を使用してガイドし、最終的にパイロットに主なテイクアウェイを設定して結果を反映して文書化します。</span><span class="sxs-lookup"><span data-stu-id="362a4-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Microsoft 365 Defender パイロットの実行のフェーズ](../../media/pilotphases.png)


<span data-ttu-id="362a4-109">パイロットを実行すると、Microsoft 365 Defender を採用するメリットを効果的に判断できます。</span><span class="sxs-lookup"><span data-stu-id="362a4-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="362a4-110">実稼働環境で Microsoft 365 Defender を有効にし、使用例を開始する前に、パイロット プロジェクトで実行するタスクを決定し、成功基準を設定する計画をお試しください。</span><span class="sxs-lookup"><span data-stu-id="362a4-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="362a4-111">このパイロット プレイブックの使い方</span><span class="sxs-lookup"><span data-stu-id="362a4-111">How to use this pilot playbook</span></span>

<span data-ttu-id="362a4-112">このガイドでは、Microsoft 365 Defender の概要とパイロット プロジェクトのセットアップ方法に関する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="362a4-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="362a4-113">Microsoft 365 Defender は、エンドポイント、ID、電子メール、およびアプリケーション全体の保護、検出、防止、調査、および応答をネイティブに調整し、高度な攻撃に対する統合保護を提供する統合された侵害前および侵害後のエンタープライズ防御スイートです。</span><span class="sxs-lookup"><span data-stu-id="362a4-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="362a4-114">これは、次の機能を 1 つのセキュリティ ソリューションに組み合わせて調整することで行います。</span><span class="sxs-lookup"><span data-stu-id="362a4-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="362a4-115">Microsoft Defender for Endpoint、Microsoft Defender Advanced Threat Protection (エンドポイント) の新しい名前</span><span class="sxs-lookup"><span data-stu-id="362a4-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="362a4-116">Microsoft Defender for Office 365、365 ATP のOffice名 (電子メール)</span><span class="sxs-lookup"><span data-stu-id="362a4-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="362a4-117">Microsoft Defender for Identity、Azure ATP の新しい名前 (ID)</span><span class="sxs-lookup"><span data-stu-id="362a4-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="362a4-118">Microsoft Cloud App Security (アプリ)</span><span class="sxs-lookup"><span data-stu-id="362a4-118">Microsoft Cloud App Security (apps)</span></span>

![イメージ of_Microsoftユーザー向け 365 Defender ソリューション、Microsoft Defender for Identity、エンドポイント用 Microsoft Defender for Endpoint、クラウド アプリ、Microsoft Cloud App Security、およびデータの場合、Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="362a4-120">統合された Microsoft 365 Defender ソリューションを使用すると、セキュリティ専門家は、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity、Microsoft Cloud App Security が受け取る脅威信号をまとめ、脅威の全範囲と影響、環境に入った方法、影響を受けたもの、組織にどのような影響を与えているかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="362a4-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="362a4-121">Microsoft 365 Defender は、攻撃を防止または停止し、影響を受けるメールボックス、エンドポイント、およびユーザー ID を自己回復するために自動アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="362a4-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="362a4-122">詳細については [、「Microsoft 365 Defender の概要」](microsoft-365-defender.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="362a4-122">See the [Microsoft 365 Defender overview](microsoft-365-defender.md) for details.</span></span>



<span data-ttu-id="362a4-123">次のサンプル タイムラインは、環境に適切なリソースを持つことによって異なります。</span><span class="sxs-lookup"><span data-stu-id="362a4-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="362a4-124">検出とワークフローによっては、他の検出よりも多くの学習時間が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="362a4-124">Some detections and workflows might need more learning time than the others.</span></span>

![Microsoft 365 Defender パイロットの実行のサンプル タイムライン](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="362a4-126">最適な結果を得る場合は、パイロットの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="362a4-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="362a4-127">パイロット プレイブックのフェーズ</span><span class="sxs-lookup"><span data-stu-id="362a4-127">Pilot playbook phases</span></span> 

<span data-ttu-id="362a4-128">Microsoft 365 Defender パイロットの実行には 4 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="362a4-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="362a4-129">段階</span><span class="sxs-lookup"><span data-stu-id="362a4-129">Phase</span></span> | <span data-ttu-id="362a4-130">説明</span><span class="sxs-lookup"><span data-stu-id="362a4-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="362a4-131">計画</span><span class="sxs-lookup"><span data-stu-id="362a4-131">Planning</span></span>](m365d-pilot-plan.md)<br> <span data-ttu-id="362a4-132">~ 1 日</span><span class="sxs-lookup"><span data-stu-id="362a4-132">~ 1 day</span></span>| <span data-ttu-id="362a4-133">Microsoft 365 Defender パイロット プロジェクトを実行する前に考慮する必要がある点について説明します。</span><span class="sxs-lookup"><span data-stu-id="362a4-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="362a4-134">- スコープ</span><span class="sxs-lookup"><span data-stu-id="362a4-134">- Scope</span></span> <br> <span data-ttu-id="362a4-135">- 使用例</span><span class="sxs-lookup"><span data-stu-id="362a4-135">- Use cases</span></span> <br><span data-ttu-id="362a4-136">- 要件</span><span class="sxs-lookup"><span data-stu-id="362a4-136">- Requirements</span></span> <br><span data-ttu-id="362a4-137">- テスト計画</span><span class="sxs-lookup"><span data-stu-id="362a4-137">- Test plan</span></span> <br> <span data-ttu-id="362a4-138">- 成功条件</span><span class="sxs-lookup"><span data-stu-id="362a4-138">- Success criteria</span></span> <br> <span data-ttu-id="362a4-139">- スコアカード</span><span class="sxs-lookup"><span data-stu-id="362a4-139">- Scorecard</span></span> 
| [<span data-ttu-id="362a4-140">準備</span><span class="sxs-lookup"><span data-stu-id="362a4-140">Preparation</span></span>](m365d-evaluation.md) <br><span data-ttu-id="362a4-141">~2 日間</span><span class="sxs-lookup"><span data-stu-id="362a4-141">~2 days</span></span>|  <span data-ttu-id="362a4-142">Microsoft 365 セキュリティ センターにアクセスして、Microsoft 365 Defender パイロット環境をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="362a4-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="362a4-143">次の情報に案内されます。</span><span class="sxs-lookup"><span data-stu-id="362a4-143">You'll be guided to:</span></span><br><br><span data-ttu-id="362a4-144">- 利害関係者を特定し、パイロットのサインオフを求める</span><span class="sxs-lookup"><span data-stu-id="362a4-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="362a4-145">- 環境に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="362a4-145">- Environment considerations</span></span> <br><span data-ttu-id="362a4-146">- Access</span><span class="sxs-lookup"><span data-stu-id="362a4-146">- Access</span></span> <br><span data-ttu-id="362a4-147">- Azure Active Directory のセットアップ</span><span class="sxs-lookup"><span data-stu-id="362a4-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="362a4-148">- 構成順序</span><span class="sxs-lookup"><span data-stu-id="362a4-148">- Configuration order</span></span> <br> <span data-ttu-id="362a4-149">- Microsoft 365 E5 試用版にサインアップする</span><span class="sxs-lookup"><span data-stu-id="362a4-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="362a4-150">- ドメインの構成</span><span class="sxs-lookup"><span data-stu-id="362a4-150">- Configure domain</span></span> <br><span data-ttu-id="362a4-151">- Microsoft 365 E5 ライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="362a4-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="362a4-152">- ポータルでセットアップ ウィザードを完了する</span><span class="sxs-lookup"><span data-stu-id="362a4-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="362a4-153">攻撃シミュレーション</span><span class="sxs-lookup"><span data-stu-id="362a4-153">Attack simulation</span></span>](m365d-pilot-simulate.md) <br><span data-ttu-id="362a4-154">~2 日間</span><span class="sxs-lookup"><span data-stu-id="362a4-154">~2 days</span></span>| <span data-ttu-id="362a4-155">攻撃をシミュレートするには、次の情報に案内されます。</span><span class="sxs-lookup"><span data-stu-id="362a4-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="362a4-156">- テスト環境の要件を確認する</span><span class="sxs-lookup"><span data-stu-id="362a4-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="362a4-157">- シミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="362a4-157">-  Run the simulation</span></span> <br><span data-ttu-id="362a4-158">- インシデントを調査する</span><span class="sxs-lookup"><span data-stu-id="362a4-158">- Investigate an incident</span></span> <br><span data-ttu-id="362a4-159">- インシデントを解決する</span><span class="sxs-lookup"><span data-stu-id="362a4-159">- resolve the incident</span></span> 
| [<span data-ttu-id="362a4-160">閉じると概要</span><span class="sxs-lookup"><span data-stu-id="362a4-160">Closing and summary</span></span>](m365d-pilot-close.md) <br><span data-ttu-id="362a4-161">~ 1 日</span><span class="sxs-lookup"><span data-stu-id="362a4-161">~ 1 day</span></span>| <span data-ttu-id="362a4-162">プロセスの最後に達すると、次の手順に案内されます。</span><span class="sxs-lookup"><span data-stu-id="362a4-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="362a4-163">- 最終的な出力を確認する</span><span class="sxs-lookup"><span data-stu-id="362a4-163">- Go through your final output</span></span><br><span data-ttu-id="362a4-164">- 出力を関係者に提示する</span><span class="sxs-lookup"><span data-stu-id="362a4-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="362a4-165">- フィードバックを提供する</span><span class="sxs-lookup"><span data-stu-id="362a4-165">- Provide feedback</span></span> <br><span data-ttu-id="362a4-166">- 次の手順を実行する</span><span class="sxs-lookup"><span data-stu-id="362a4-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="362a4-167">次の手順</span><span class="sxs-lookup"><span data-stu-id="362a4-167">Next step</span></span>
|[<span data-ttu-id="362a4-168">計画フェーズ</span><span class="sxs-lookup"><span data-stu-id="362a4-168">Planning phase</span></span>](m365d-pilot-plan.md) | <span data-ttu-id="362a4-169">Microsoft 365 Defender パイロット プロジェクトを計画する</span><span class="sxs-lookup"><span data-stu-id="362a4-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
