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
ms.openlocfilehash: f49f1afe5461a4f2eff0a3049f1d14d1892f70ce
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477022"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="a9991-104">パイロットの Microsoft 脅威保護プロジェクトを実行する</span><span class="sxs-lookup"><span data-stu-id="a9991-104">Run your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a9991-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a9991-105">**Applies to:**</span></span>
- <span data-ttu-id="a9991-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a9991-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a9991-107">Microsoft の脅威保護 (MTP) のメリットと導入を効果的に決定するために、パイロットプロジェクトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a9991-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="a9991-108">運用環境で Microsoft の脅威保護を有効にし、ユースケースを開始する前に、パイロットプロジェクトに対して実行するタスクを決定し、成功の基準を設定することを計画することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a9991-108">Before enabling Microsoft Threat Protection in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="a9991-109">このパイロットプレイブックの使用方法</span><span class="sxs-lookup"><span data-stu-id="a9991-109">How to use this pilot playbook</span></span>

<span data-ttu-id="a9991-110">このガイドでは、パイロットプロジェクトをセットアップする方法について、Microsoft の脅威保護と詳しい手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="a9991-110">This guide provides an overview of Microsoft Threat Protection and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="a9991-111">Microsoft Threat Protection は、統合された事前違反のエンタープライズ防御スイートであり、エンドポイント、id、電子メール、およびアプリケーション間の応答をネイティブに調整し、高度な攻撃から統合された保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="a9991-111">Microsoft Threat Protection is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="a9991-112">そのためには、次の機能を結合して、単一のセキュリティソリューションにオーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="a9991-112">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="a9991-113">エンドポイントの microsoft Defender。 Microsoft Defender Advanced Threat Protection (エンドポイント) の新しい名前</span><span class="sxs-lookup"><span data-stu-id="a9991-113">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="a9991-114">Microsoft Defender for Office 365、Office 365 ATP (電子メール) の新しい名前</span><span class="sxs-lookup"><span data-stu-id="a9991-114">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="a9991-115">Id の Microsoft Defender。 Azure ATP (identity) の新しい名前</span><span class="sxs-lookup"><span data-stu-id="a9991-115">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="a9991-116">Microsoft Cloud App Security (apps)</span><span class="sxs-lookup"><span data-stu-id="a9991-116">Microsoft Cloud App Security (apps)</span></span>

![<span data-ttu-id="a9991-117">画像 of_Microsoft ユーザーのための脅威保護ソリューション、Azure Advanced Threat Protection、エンドポイントの Microsoft Defender Advanced Threat Protection、クラウドアプリ、Microsoft Cloud App Security、およびデータについては、Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a9991-117">Image of_Microsoft Threat Protection solution for users, Azure Advanced Threat Protection, for endpoints Microsoft Defender Advanced Threat Protection, for cloud apps, Microsoft Cloud App Security, and for data, Office 365 Advanced Threat Protection</span></span>  ](../../media/mtp/m365pillars.png)

<span data-ttu-id="a9991-118">統合された Microsoft の脅威保護ソリューションを使用すると、セキュリティ担当者は、Microsoft Defender Advanced Threat Protection、Office 365 ATP、Azure ATP、および Microsoft Cloud App Security receive を使用して、脅威の完全な範囲と影響、どのように環境を入力したか、どのように影響を受けるか、どのように組織をどのように影響して</span><span class="sxs-lookup"><span data-stu-id="a9991-118">With the integrated Microsoft Threat Protection solution, security professionals can stitch together the threat signals that Microsoft Defender Advanced Threat Protection, Office 365 ATP, Azure ATP, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="a9991-119">Microsoft の脅威保護は、攻撃を阻止または停止したり、影響を受けるメールボックス、エンドポイント、ユーザー id を自己回復させるための自動操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a9991-119">Microsoft Threat Protection takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="a9991-120">詳細については、 [Microsoft の脅威保護の概要](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9991-120">See the [Microsoft Threat Protection overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>

![Microsoft の脅威保護パイロットを実行するフェーズ](../../media/pilotphases.png)

<span data-ttu-id="a9991-122">次のサンプルタイムラインは、環境内に適切なリソースがあるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="a9991-122">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="a9991-123">一部の検出とワークフローでは、他のユーザーよりも多くの学習時間が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="a9991-123">Some detections and workflows might need more learning time than the others.</span></span>

![Microsoft の脅威保護パイロット実行のサンプルタイムライン](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="a9991-125">最適な結果を得るには、パイロットの手順をできるだけ忠実に実行します。</span><span class="sxs-lookup"><span data-stu-id="a9991-125">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="a9991-126">パイロットプレイブックのフェーズ</span><span class="sxs-lookup"><span data-stu-id="a9991-126">Pilot playbook phases</span></span> 

<span data-ttu-id="a9991-127">Microsoft の脅威保護パイロットの実行には、次の4つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="a9991-127">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="a9991-128">フェーズ</span><span class="sxs-lookup"><span data-stu-id="a9991-128">Phase</span></span> | <span data-ttu-id="a9991-129">説明</span><span class="sxs-lookup"><span data-stu-id="a9991-129">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="a9991-130">![計画](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="a9991-130">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="a9991-131">計画</span><span class="sxs-lookup"><span data-stu-id="a9991-131">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="a9991-132">Microsoft の脅威保護パイロットプロジェクトを実行する前に考慮する必要のある事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="a9991-132">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="a9991-133">-スコープ</span><span class="sxs-lookup"><span data-stu-id="a9991-133">- Scope</span></span> <br> <span data-ttu-id="a9991-134">-ユースケース</span><span class="sxs-lookup"><span data-stu-id="a9991-134">- Use cases</span></span> <br><span data-ttu-id="a9991-135">- 要件</span><span class="sxs-lookup"><span data-stu-id="a9991-135">- Requirements</span></span> <br><span data-ttu-id="a9991-136">-テスト計画</span><span class="sxs-lookup"><span data-stu-id="a9991-136">- Test plan</span></span> <br> <span data-ttu-id="a9991-137">-成功の条件</span><span class="sxs-lookup"><span data-stu-id="a9991-137">- Success criteria</span></span> <br> <span data-ttu-id="a9991-138">-スコアカード</span><span class="sxs-lookup"><span data-stu-id="a9991-138">- Scorecard</span></span> 
| <span data-ttu-id="a9991-139">![準備](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="a9991-139">![Preparation](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="a9991-140">準備</span><span class="sxs-lookup"><span data-stu-id="a9991-140">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="a9991-141">Microsoft 365 セキュリティセンターにアクセスして、Microsoft の脅威保護パイロット環境をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="a9991-141">Access Microsoft 365 Security Center to set up your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="a9991-142">次のようなガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9991-142">You'll be guided to:</span></span><br><br><span data-ttu-id="a9991-143">-パイロットの関係者を特定し、承認を求める</span><span class="sxs-lookup"><span data-stu-id="a9991-143">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="a9991-144">-環境に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="a9991-144">- Environment considerations</span></span> <br><span data-ttu-id="a9991-145">-アクセス</span><span class="sxs-lookup"><span data-stu-id="a9991-145">- Access</span></span> <br><span data-ttu-id="a9991-146">-Azure Active Directory のセットアップ</span><span class="sxs-lookup"><span data-stu-id="a9991-146">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="a9991-147">-構成の順序</span><span class="sxs-lookup"><span data-stu-id="a9991-147">- Configuration order</span></span> <br> <span data-ttu-id="a9991-148">-Microsoft 365 E5 試用版にサインアップする</span><span class="sxs-lookup"><span data-stu-id="a9991-148">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="a9991-149">-ドメインの構成</span><span class="sxs-lookup"><span data-stu-id="a9991-149">- Configure domain</span></span> <br><span data-ttu-id="a9991-150">-Microsoft 365 E5 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9991-150">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="a9991-151">-ポータルのセットアップウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="a9991-151">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="a9991-152">![攻撃シミュレーション](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="a9991-152">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="a9991-153">攻撃シミュレーション</span><span class="sxs-lookup"><span data-stu-id="a9991-153">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="a9991-154">攻撃をシミュレートするために、次のように指導します。</span><span class="sxs-lookup"><span data-stu-id="a9991-154">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="a9991-155">-テスト環境の要件を確認する</span><span class="sxs-lookup"><span data-stu-id="a9991-155">- Verify the test environment requirements</span></span> <br><span data-ttu-id="a9991-156">-シミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="a9991-156">-  Run the simulation</span></span> <br><span data-ttu-id="a9991-157">-インシデントを調査する</span><span class="sxs-lookup"><span data-stu-id="a9991-157">- Investigate an incident</span></span> <br><span data-ttu-id="a9991-158">-インシデントを解決する</span><span class="sxs-lookup"><span data-stu-id="a9991-158">- resolve the incident</span></span> 
| <span data-ttu-id="a9991-159">![決算と概要](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="a9991-159">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="a9991-160">決算と概要</span><span class="sxs-lookup"><span data-stu-id="a9991-160">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="a9991-161">プロセスの最後に達すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a9991-161">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="a9991-162">-最終出力に進む</span><span class="sxs-lookup"><span data-stu-id="a9991-162">- Go through your final output</span></span><br><span data-ttu-id="a9991-163">-利害関係者への出力を提示する</span><span class="sxs-lookup"><span data-stu-id="a9991-163">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="a9991-164">-フィードバックを提供する</span><span class="sxs-lookup"><span data-stu-id="a9991-164">- Provide feedback</span></span> <br><span data-ttu-id="a9991-165">-次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9991-165">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="a9991-166">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a9991-166">Next step</span></span>
|<span data-ttu-id="a9991-167">![計画フェーズ](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="a9991-167">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="a9991-168">計画フェーズ</span><span class="sxs-lookup"><span data-stu-id="a9991-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="a9991-169">Microsoft の脅威保護パイロットプロジェクトを計画する</span><span class="sxs-lookup"><span data-stu-id="a9991-169">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
