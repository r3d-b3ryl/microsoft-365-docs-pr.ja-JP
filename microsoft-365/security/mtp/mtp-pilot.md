---
title: パイロットを実行する Microsoft 365 Defender プロジェクト
description: 試験的な Microsoft 365 Defender プロジェクトを運用環境で実行して、Microsoft 365 Defender の利点と導入を効果的に決定します。
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
ms.openlocfilehash: 350904022ec86acdbebf109dd5946598643aea83
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843662"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="9cafa-104">パイロットを実行する Microsoft 365 Defender プロジェクト</span><span class="sxs-lookup"><span data-stu-id="9cafa-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9cafa-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9cafa-105">**Applies to:**</span></span>
- <span data-ttu-id="9cafa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cafa-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9cafa-107">Microsoft 365 Defender の利点と導入を効果的に決定するために、パイロットプロジェクトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9cafa-107">To effectively determine the benefit and adoption of Microsoft 365 Defender, you can run a pilot project.</span></span> <span data-ttu-id="9cafa-108">運用環境で Microsoft 365 Defender を有効にし、ユースケースを開始する前に、パイロットプロジェクトに対して実行するタスクを決定し、成功の基準を設定することを計画することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9cafa-108">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="9cafa-109">このパイロットプレイブックの使用方法</span><span class="sxs-lookup"><span data-stu-id="9cafa-109">How to use this pilot playbook</span></span>

<span data-ttu-id="9cafa-110">このガイドでは、パイロットプロジェクトをセットアップする方法について、Microsoft 365 Defender の概要と詳細な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="9cafa-110">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="9cafa-111">Microsoft 365 Defender は、統合された事前違反および適用後のエンタープライズ防衛スイートで、エンドポイント、id、電子メール、およびアプリケーション間の応答をネイティブに調整し、高度な攻撃に対する統合保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="9cafa-111">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="9cafa-112">そのためには、次の機能を結合して、単一のセキュリティソリューションにオーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="9cafa-112">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="9cafa-113">エンドポイントの microsoft Defender。 Microsoft Defender Advanced Threat Protection (エンドポイント) の新しい名前</span><span class="sxs-lookup"><span data-stu-id="9cafa-113">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="9cafa-114">Microsoft Defender for Office 365、Office 365 ATP (電子メール) の新しい名前</span><span class="sxs-lookup"><span data-stu-id="9cafa-114">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="9cafa-115">Id の Microsoft Defender。 Azure ATP (identity) の新しい名前</span><span class="sxs-lookup"><span data-stu-id="9cafa-115">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="9cafa-116">Microsoft Cloud App Security (apps)</span><span class="sxs-lookup"><span data-stu-id="9cafa-116">Microsoft Cloud App Security (apps)</span></span>

![画像 of_Microsoft ユーザーの場合は 365 Defender ソリューション、エンドポイントの場合は microsoft defender、エンドポイントの場合は microsoft defender、クラウドアプリの場合は microsoft Cloud App Security、データについては Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="9cafa-118">統合された Microsoft 365 Defender ソリューションを使用することにより、セキュリティ担当者は microsoft Defender for Endpoint、microsoft defender for Office 365、Id 用 Microsoft Defender、および Microsoft Cloud App Security receive という脅威について協力することができ、脅威の完全な範囲と影響、その脅威がどのような影響を受けるか、どのように組織をどのように</span><span class="sxs-lookup"><span data-stu-id="9cafa-118">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="9cafa-119">Microsoft 365 Defender は、攻撃を阻止または停止する、または影響を受けるメールボックス、エンドポイント、ユーザー id を自己回復させるための自動操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9cafa-119">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="9cafa-120">詳細については、 [Microsoft 365 Defender の概要](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cafa-120">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>

![Microsoft 365 Defender パイロットの実行フェーズ](../../media/pilotphases.png)

<span data-ttu-id="9cafa-122">次のサンプルタイムラインは、環境内に適切なリソースがあるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9cafa-122">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="9cafa-123">一部の検出とワークフローでは、他のユーザーよりも多くの学習時間が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="9cafa-123">Some detections and workflows might need more learning time than the others.</span></span>

![Microsoft 365 Defender パイロットの実行におけるサンプルタイムライン](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="9cafa-125">最適な結果を得るには、パイロットの手順をできるだけ忠実に実行します。</span><span class="sxs-lookup"><span data-stu-id="9cafa-125">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="9cafa-126">パイロットプレイブックのフェーズ</span><span class="sxs-lookup"><span data-stu-id="9cafa-126">Pilot playbook phases</span></span> 

<span data-ttu-id="9cafa-127">Microsoft 365 Defender パイロットの実行には、次の4つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="9cafa-127">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="9cafa-128">フェーズ</span><span class="sxs-lookup"><span data-stu-id="9cafa-128">Phase</span></span> | <span data-ttu-id="9cafa-129">説明</span><span class="sxs-lookup"><span data-stu-id="9cafa-129">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="9cafa-130">![計画](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="9cafa-130">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="9cafa-131">計画</span><span class="sxs-lookup"><span data-stu-id="9cafa-131">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="9cafa-132">Microsoft 365 Defender パイロットプロジェクトを実行する前に考慮する必要のある事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="9cafa-132">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="9cafa-133">-スコープ</span><span class="sxs-lookup"><span data-stu-id="9cafa-133">- Scope</span></span> <br> <span data-ttu-id="9cafa-134">-ユースケース</span><span class="sxs-lookup"><span data-stu-id="9cafa-134">- Use cases</span></span> <br><span data-ttu-id="9cafa-135">- 要件</span><span class="sxs-lookup"><span data-stu-id="9cafa-135">- Requirements</span></span> <br><span data-ttu-id="9cafa-136">-テスト計画</span><span class="sxs-lookup"><span data-stu-id="9cafa-136">- Test plan</span></span> <br> <span data-ttu-id="9cafa-137">-成功の条件</span><span class="sxs-lookup"><span data-stu-id="9cafa-137">- Success criteria</span></span> <br> <span data-ttu-id="9cafa-138">-スコアカード</span><span class="sxs-lookup"><span data-stu-id="9cafa-138">- Scorecard</span></span> 
| <span data-ttu-id="9cafa-139">![準備](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="9cafa-139">![Preparation](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="9cafa-140">準備</span><span class="sxs-lookup"><span data-stu-id="9cafa-140">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="9cafa-141">Microsoft 365 セキュリティセンターにアクセスして、Microsoft 365 Defender パイロット環境を設定します。</span><span class="sxs-lookup"><span data-stu-id="9cafa-141">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="9cafa-142">次のようなガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cafa-142">You'll be guided to:</span></span><br><br><span data-ttu-id="9cafa-143">-パイロットの関係者を特定し、承認を求める</span><span class="sxs-lookup"><span data-stu-id="9cafa-143">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="9cafa-144">-環境に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="9cafa-144">- Environment considerations</span></span> <br><span data-ttu-id="9cafa-145">-アクセス</span><span class="sxs-lookup"><span data-stu-id="9cafa-145">- Access</span></span> <br><span data-ttu-id="9cafa-146">-Azure Active Directory のセットアップ</span><span class="sxs-lookup"><span data-stu-id="9cafa-146">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="9cafa-147">-構成の順序</span><span class="sxs-lookup"><span data-stu-id="9cafa-147">- Configuration order</span></span> <br> <span data-ttu-id="9cafa-148">-Microsoft 365 E5 試用版にサインアップする</span><span class="sxs-lookup"><span data-stu-id="9cafa-148">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="9cafa-149">-ドメインの構成</span><span class="sxs-lookup"><span data-stu-id="9cafa-149">- Configure domain</span></span> <br><span data-ttu-id="9cafa-150">-Microsoft 365 E5 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9cafa-150">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="9cafa-151">-ポータルのセットアップウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="9cafa-151">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="9cafa-152">![攻撃シミュレーション](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="9cafa-152">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="9cafa-153">攻撃シミュレーション</span><span class="sxs-lookup"><span data-stu-id="9cafa-153">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="9cafa-154">攻撃をシミュレートするために、次のように指導します。</span><span class="sxs-lookup"><span data-stu-id="9cafa-154">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="9cafa-155">-テスト環境の要件を確認する</span><span class="sxs-lookup"><span data-stu-id="9cafa-155">- Verify the test environment requirements</span></span> <br><span data-ttu-id="9cafa-156">-シミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="9cafa-156">-  Run the simulation</span></span> <br><span data-ttu-id="9cafa-157">-インシデントを調査する</span><span class="sxs-lookup"><span data-stu-id="9cafa-157">- Investigate an incident</span></span> <br><span data-ttu-id="9cafa-158">-インシデントを解決する</span><span class="sxs-lookup"><span data-stu-id="9cafa-158">- resolve the incident</span></span> 
| <span data-ttu-id="9cafa-159">![決算と概要](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="9cafa-159">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="9cafa-160">決算と概要</span><span class="sxs-lookup"><span data-stu-id="9cafa-160">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="9cafa-161">プロセスの最後に達すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9cafa-161">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="9cafa-162">-最終出力に進む</span><span class="sxs-lookup"><span data-stu-id="9cafa-162">- Go through your final output</span></span><br><span data-ttu-id="9cafa-163">-利害関係者への出力を提示する</span><span class="sxs-lookup"><span data-stu-id="9cafa-163">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="9cafa-164">-フィードバックを提供する</span><span class="sxs-lookup"><span data-stu-id="9cafa-164">- Provide feedback</span></span> <br><span data-ttu-id="9cafa-165">-次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cafa-165">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="9cafa-166">次のステップ</span><span class="sxs-lookup"><span data-stu-id="9cafa-166">Next step</span></span>
|<span data-ttu-id="9cafa-167">![計画フェーズ](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="9cafa-167">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="9cafa-168">計画フェーズ</span><span class="sxs-lookup"><span data-stu-id="9cafa-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="9cafa-169">Microsoft 365 Defender パイロットプロジェクトを計画する</span><span class="sxs-lookup"><span data-stu-id="9cafa-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
