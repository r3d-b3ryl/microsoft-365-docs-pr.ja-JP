---
title: パイロット プロジェクトをMicrosoft 365 Defenderする
description: 実稼働環境でパイロット Microsoft 365 Defenderプロジェクトを実行して、プロジェクトのメリットと導入を効果的にMicrosoft 365 Defender。
keywords: Microsoft 365 Defenderパイロット、パイロット Microsoft 365 Defender プロジェクトの実行、実稼働での Microsoft 365 Defender の評価、Microsoft 365 Defender パイロット プロジェクト、サイバーセキュリティ、高度な永続的な脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な狩猟
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
ms.openlocfilehash: fd84ef93d679be6e1e42f823dcac1f2d5181f1e9
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458417"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="8275b-104">パイロット プロジェクトをMicrosoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="8275b-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8275b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8275b-105">**Applies to:**</span></span>
- <span data-ttu-id="8275b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8275b-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="8275b-107">このガイドは、パイロット プロジェクトを実行する場合に役立ちます。ポインターを使用して、適切に構造化された計画を作成し、攻撃シミュレーション機能を使用してガイドし、最終的にパイロットに主なテイクアウェイを設定して結果を反映して文書化します。</span><span class="sxs-lookup"><span data-stu-id="8275b-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![パイロットの実行Microsoft 365 Defenderフェーズ](../../media/pilotphases.png)


<span data-ttu-id="8275b-109">パイロットを実行すると、パイロットを採用するメリットを効果的にMicrosoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="8275b-109">Running a pilot helps you effectively determine the benefit of adopting Microsoft 365 Defender.</span></span> <span data-ttu-id="8275b-110">実稼働環境Microsoft 365 Defenderを有効にし、使用例を開始する前に、パイロット プロジェクトで実行するタスクを決定し、成功基準を設定してください。</span><span class="sxs-lookup"><span data-stu-id="8275b-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="8275b-111">このパイロット プレイブックの使い方</span><span class="sxs-lookup"><span data-stu-id="8275b-111">How to use this pilot playbook</span></span>

<span data-ttu-id="8275b-112">このガイドでは、パイロット プロジェクトMicrosoft 365 Defenderの手順と手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="8275b-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="8275b-113">Microsoft 365 Defender は、エンドポイント、ID、電子メール、およびアプリケーション間で保護、検出、防止、調査、応答をネイティブに調整し、高度な攻撃に対する統合保護を提供する統合された侵害前および侵害後のエンタープライズ防御スイートです。</span><span class="sxs-lookup"><span data-stu-id="8275b-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="8275b-114">これは、次の機能を 1 つのセキュリティ ソリューションに組み合わせて調整することで行います。</span><span class="sxs-lookup"><span data-stu-id="8275b-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>

- <span data-ttu-id="8275b-115">エンドポイント用 Microsoft Defender (エンドポイント)</span><span class="sxs-lookup"><span data-stu-id="8275b-115">Microsoft Defender for Endpoint (endpoints)</span></span>
- <span data-ttu-id="8275b-116">Microsoft Defender for Office 365 (メール)</span><span class="sxs-lookup"><span data-stu-id="8275b-116">Microsoft Defender for Office 365 (email)</span></span>
- <span data-ttu-id="8275b-117">Microsoft Defender for Identity (IDENTITY)</span><span class="sxs-lookup"><span data-stu-id="8275b-117">Microsoft Defender for Identity (identity)</span></span>
- <span data-ttu-id="8275b-118">Microsoft Cloud App Security (アプリ)</span><span class="sxs-lookup"><span data-stu-id="8275b-118">Microsoft Cloud App Security (apps)</span></span>

![イメージ of_Microsoftユーザー向け 365 Defender ソリューション、Microsoft Defender for Identity、エンドポイント用 Microsoft Defender for Endpoint、クラウド アプリ、Microsoft Cloud App Security、データの場合は Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="8275b-120">統合された Microsoft 365 Defender ソリューションを使用すると、セキュリティ専門家は、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity、および Microsoft Cloud App Security が受け取る脅威信号をまとめ、脅威の全範囲と影響、環境への影響、影響を受ける環境への影響、組織に対する現在の影響を判断できます。</span><span class="sxs-lookup"><span data-stu-id="8275b-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="8275b-121">Microsoft 365 Defender攻撃を防止または停止し、影響を受けるメールボックス、エンドポイント、およびユーザー ID を自己回復する自動アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="8275b-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="8275b-122">詳細については[、「Microsoft 365 Defender概要」](microsoft-365-defender.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8275b-122">See the [Microsoft 365 Defender overview](microsoft-365-defender.md) for details.</span></span>

<span data-ttu-id="8275b-123">次のサンプル タイムラインは、環境に適切なリソースを持つことによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8275b-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="8275b-124">検出とワークフローによっては、他の検出よりも多くの学習時間が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8275b-124">Some detections and workflows might need more learning time than the others.</span></span>

![パイロットの実行に関するタイムラインMicrosoft 365 Defender例](../../media/phase-diagrams/pilot-phases.png)

> [!IMPORTANT]
> <span data-ttu-id="8275b-126">最適な結果を得る場合は、パイロットの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="8275b-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>

### <a name="pilot-playbook-phases"></a><span data-ttu-id="8275b-127">パイロット プレイブックのフェーズ</span><span class="sxs-lookup"><span data-stu-id="8275b-127">Pilot playbook phases</span></span>

<span data-ttu-id="8275b-128">パイロットの実行には 4 つのMicrosoft 365 Defenderがあります。</span><span class="sxs-lookup"><span data-stu-id="8275b-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="8275b-129">段階</span><span class="sxs-lookup"><span data-stu-id="8275b-129">Phase</span></span> | <span data-ttu-id="8275b-130">説明</span><span class="sxs-lookup"><span data-stu-id="8275b-130">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="8275b-131">計画</span><span class="sxs-lookup"><span data-stu-id="8275b-131">Planning</span></span>](m365d-pilot-plan.md)<br> <span data-ttu-id="8275b-132">~ 1 日</span><span class="sxs-lookup"><span data-stu-id="8275b-132">~ 1 day</span></span>| <span data-ttu-id="8275b-133">パイロット プロジェクトを実行する前に考慮する必要Microsoft 365 Defender確認します。</span><span class="sxs-lookup"><span data-stu-id="8275b-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="8275b-134">- スコープ</span><span class="sxs-lookup"><span data-stu-id="8275b-134">- Scope</span></span> <br> <span data-ttu-id="8275b-135">- 使用例</span><span class="sxs-lookup"><span data-stu-id="8275b-135">- Use cases</span></span> <br><span data-ttu-id="8275b-136">- 要件</span><span class="sxs-lookup"><span data-stu-id="8275b-136">- Requirements</span></span> <br><span data-ttu-id="8275b-137">- テスト計画</span><span class="sxs-lookup"><span data-stu-id="8275b-137">- Test plan</span></span> <br> <span data-ttu-id="8275b-138">- 成功条件</span><span class="sxs-lookup"><span data-stu-id="8275b-138">- Success criteria</span></span> <br> <span data-ttu-id="8275b-139">- スコアカード</span><span class="sxs-lookup"><span data-stu-id="8275b-139">- Scorecard</span></span> 
| [<span data-ttu-id="8275b-140">準備</span><span class="sxs-lookup"><span data-stu-id="8275b-140">Preparation</span></span>](m365d-evaluation.md) <br><span data-ttu-id="8275b-141">~2 日間</span><span class="sxs-lookup"><span data-stu-id="8275b-141">~2 days</span></span>|  <span data-ttu-id="8275b-142">セキュリティ Microsoft 365にアクセスして、パイロット環境Microsoft 365 Defender設定します。</span><span class="sxs-lookup"><span data-stu-id="8275b-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="8275b-143">次の情報に案内されます。</span><span class="sxs-lookup"><span data-stu-id="8275b-143">You'll be guided to:</span></span><br><br><span data-ttu-id="8275b-144">- 利害関係者を特定し、パイロットのサインオフを求める</span><span class="sxs-lookup"><span data-stu-id="8275b-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="8275b-145">- 環境に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="8275b-145">- Environment considerations</span></span> <br><span data-ttu-id="8275b-146">- Access</span><span class="sxs-lookup"><span data-stu-id="8275b-146">- Access</span></span> <br><span data-ttu-id="8275b-147">- Azure Active Directoryセットアップ</span><span class="sxs-lookup"><span data-stu-id="8275b-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="8275b-148">- 構成順序</span><span class="sxs-lookup"><span data-stu-id="8275b-148">- Configuration order</span></span> <br> <span data-ttu-id="8275b-149">- 試用版にMicrosoft 365 E5する</span><span class="sxs-lookup"><span data-stu-id="8275b-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="8275b-150">- ドメインの構成</span><span class="sxs-lookup"><span data-stu-id="8275b-150">- Configure domain</span></span> <br><span data-ttu-id="8275b-151">- ライセンスMicrosoft 365 E5割り当てる</span><span class="sxs-lookup"><span data-stu-id="8275b-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="8275b-152">- ポータルでセットアップ ウィザードを完了する</span><span class="sxs-lookup"><span data-stu-id="8275b-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="8275b-153">攻撃シミュレーション</span><span class="sxs-lookup"><span data-stu-id="8275b-153">Attack simulation</span></span>](m365d-pilot-simulate.md) <br><span data-ttu-id="8275b-154">~2 日間</span><span class="sxs-lookup"><span data-stu-id="8275b-154">~2 days</span></span>| <span data-ttu-id="8275b-155">攻撃をシミュレートするには、次の情報に案内されます。</span><span class="sxs-lookup"><span data-stu-id="8275b-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="8275b-156">- テスト環境の要件を確認する</span><span class="sxs-lookup"><span data-stu-id="8275b-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="8275b-157">- シミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="8275b-157">-  Run the simulation</span></span> <br><span data-ttu-id="8275b-158">- インシデントを調査する</span><span class="sxs-lookup"><span data-stu-id="8275b-158">- Investigate an incident</span></span> <br><span data-ttu-id="8275b-159">- インシデントを解決する</span><span class="sxs-lookup"><span data-stu-id="8275b-159">- resolve the incident</span></span> 
| [<span data-ttu-id="8275b-160">閉じると概要</span><span class="sxs-lookup"><span data-stu-id="8275b-160">Closing and summary</span></span>](m365d-pilot-close.md) <br><span data-ttu-id="8275b-161">~ 1 日</span><span class="sxs-lookup"><span data-stu-id="8275b-161">~ 1 day</span></span>| <span data-ttu-id="8275b-162">プロセスの最後に達すると、次の手順に案内されます。</span><span class="sxs-lookup"><span data-stu-id="8275b-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="8275b-163">- 最終的な出力を確認する</span><span class="sxs-lookup"><span data-stu-id="8275b-163">- Go through your final output</span></span><br><span data-ttu-id="8275b-164">- 出力を関係者に提示する</span><span class="sxs-lookup"><span data-stu-id="8275b-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="8275b-165">- フィードバックを提供する</span><span class="sxs-lookup"><span data-stu-id="8275b-165">- Provide feedback</span></span> <br><span data-ttu-id="8275b-166">- 次の手順を実行する</span><span class="sxs-lookup"><span data-stu-id="8275b-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="8275b-167">次の手順</span><span class="sxs-lookup"><span data-stu-id="8275b-167">Next step</span></span>

|[<span data-ttu-id="8275b-168">計画フェーズ</span><span class="sxs-lookup"><span data-stu-id="8275b-168">Planning phase</span></span>](m365d-pilot-plan.md) | <span data-ttu-id="8275b-169">パイロット プロジェクトMicrosoft 365 Defender計画する</span><span class="sxs-lookup"><span data-stu-id="8275b-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
