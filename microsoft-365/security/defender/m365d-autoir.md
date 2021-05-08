---
title: Defender での自動調査Microsoft 365対応
description: Defender の自動調査および応答機能 (自己修復とも呼ばれる) の概要をMicrosoft 365する
keywords: 自動化、調査、アラート、トリガー、アクション、修復、自己修復
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: fcb7283faed6fe8c5af59cedeeb90577b557ab34
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259537"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="7ec08-104">Defender での自動調査Microsoft 365対応</span><span class="sxs-lookup"><span data-stu-id="7ec08-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7ec08-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7ec08-105">**Applies to:**</span></span>
- <span data-ttu-id="7ec08-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ec08-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7ec08-107">組織が Microsoft 365 [Defender を](microsoft-365-defender.md)使用している場合、悪意のあるアクティビティや疑わしいアクティビティやアーティファクトが検出されると、セキュリティ運用チームは Microsoft 365 セキュリティ センター内で警告を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7ec08-107">If your organization is using [Microsoft 365 Defender](microsoft-365-defender.md), your security operations team receives an alert within the Microsoft 365 security center whenever a malicious or suspicious activity or artifact is detected.</span></span> <span data-ttu-id="7ec08-108">一見終わりのない脅威の流れを考えると、セキュリティ チームは多くの場合、アラートの大きな量に対処するという課題に直面します。</span><span class="sxs-lookup"><span data-stu-id="7ec08-108">Given the seemingly never-ending flow of threats that can come in, security teams often face the challenge of addressing the high volume of alerts.</span></span> <span data-ttu-id="7ec08-109">幸いMicrosoft 365 Defender には、セキュリティ運用チームが脅威に効率的かつ効果的に対処するのに役立つ自動調査と修復 (AIR) 機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7ec08-109">Fortunately, Microsoft 365 Defender includes automated investigation and remediation (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span>

<span data-ttu-id="7ec08-110">この記事では、AIR の概要を説明し、次の手順と追加のリソースへのリンクを含みます。</span><span class="sxs-lookup"><span data-stu-id="7ec08-110">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="7ec08-111">Microsoft 365 Defender を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="7ec08-111">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="7ec08-112">[ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。</span><span class="sxs-lookup"><span data-stu-id="7ec08-112">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="7ec08-113">自動調査と自己修復の仕組み</span><span class="sxs-lookup"><span data-stu-id="7ec08-113">How automated investigation and self-healing works</span></span>

<span data-ttu-id="7ec08-114">セキュリティアラートがトリガーされると、セキュリティ運用チームがこれらのアラートを確認し、組織を保護するための手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ec08-114">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="7ec08-115">警告の優先順位付けと調査には、多くの時間がかかる場合があります。調査実行中に新しい警告が出されるような状況では、この傾向が特に強くなります。</span><span class="sxs-lookup"><span data-stu-id="7ec08-115">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="7ec08-116">セキュリティ運用チームは、監視および保護を必要とする脅威の膨大さに圧倒されてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7ec08-116">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="7ec08-117">自動調査と応答機能(自己修復機能付き)は、Defender Microsoft 365役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7ec08-117">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="7ec08-118">自己修復のしくみについては、次のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7ec08-118">Watch the following video to see how self-healing works:</span></span> <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="7ec08-119">Defender Microsoft 365、自己修復機能を使用した自動調査と応答は、デバイス、電子メール、コンテンツ、および id 間&機能します。</span><span class="sxs-lookup"><span data-stu-id="7ec08-119">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="7ec08-120">この記事では、自動調査と対応のしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec08-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="7ec08-121">これらの機能を構成するには、「Defender で自動調査と応答機能を構成する」[をMicrosoft 365してください](m365d-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="7ec08-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="7ec08-122">独自の仮想アナリスト</span><span class="sxs-lookup"><span data-stu-id="7ec08-122">Your own virtual analyst</span></span>

<span data-ttu-id="7ec08-123">Imagine第 1 層または第 2 層のセキュリティ運用チームに仮想アナリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ec08-123">Imagine having a virtual analyst in your Tier 1 or Tier 2 security operations team.</span></span> <span data-ttu-id="7ec08-124">仮想アナリストは、セキュリティ運用チームであれば実行するであろう脅威の調査と修復の最適な手順を模倣して実行します。</span><span class="sxs-lookup"><span data-stu-id="7ec08-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="7ec08-125">仮想アナリストは、無制限の容量で 24 時間 365 日動作し、調査と脅威の修復に多大な負荷を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7ec08-125">The virtual analyst could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="7ec08-126">このような仮想アナリストは、対応時間を大幅に短縮し、他の重要な脅威や戦略的なプロジェクトのためにセキュリティ運用チームを解放することができます。</span><span class="sxs-lookup"><span data-stu-id="7ec08-126">Such a virtual analyst could significantly reduce the time to respond, freeing up your security operations team for other important threats or strategic projects.</span></span> <span data-ttu-id="7ec08-127">このシナリオが SF のように聞こえる場合は、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="7ec08-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="7ec08-128">このような仮想アナリストは、Defender Microsoft 365の一部であり、その名前は自動 *調査と応答です*。</span><span class="sxs-lookup"><span data-stu-id="7ec08-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="7ec08-129">自動調査と対応機能により、セキュリティ運用チームは、セキュリティアラートやインシデントに対処する組織の能力を大幅に向上できます。</span><span class="sxs-lookup"><span data-stu-id="7ec08-129">Automated investigation and response capabilities enable your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="7ec08-130">自動調査と対応により、調査と修復の処理コストを削減し、脅威保護スイートを有効に利用できます。</span><span class="sxs-lookup"><span data-stu-id="7ec08-130">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="7ec08-131">自動調査と対応機能は、次の方法でセキュリティ運用チームを支援します。</span><span class="sxs-lookup"><span data-stu-id="7ec08-131">Automated investigation and response capabilities help your security operations team by:</span></span>

1. <span data-ttu-id="7ec08-132">脅威にアクションが必要かどうかを判断する。</span><span class="sxs-lookup"><span data-stu-id="7ec08-132">Determining whether a threat requires action.</span></span>
2. <span data-ttu-id="7ec08-133">必要な修復アクションを実行 (または推奨) します。</span><span class="sxs-lookup"><span data-stu-id="7ec08-133">Taking (or recommending) any necessary remediation actions.</span></span>
3. <span data-ttu-id="7ec08-134">他の調査が行われるかどうかと、その他の調査を行う必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="7ec08-134">Determining whether and what other investigations should occur.</span></span>
4. <span data-ttu-id="7ec08-135">必要に応じた、他の警告に対するプロセスの反復。</span><span class="sxs-lookup"><span data-stu-id="7ec08-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="7ec08-136">自動調査のプロセス</span><span class="sxs-lookup"><span data-stu-id="7ec08-136">The automated investigation process</span></span>

<span data-ttu-id="7ec08-137">アラートによってインシデントが作成され、自動調査を開始できます。</span><span class="sxs-lookup"><span data-stu-id="7ec08-137">An alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="7ec08-138">自動調査の結果、各証拠の評決が下されます。</span><span class="sxs-lookup"><span data-stu-id="7ec08-138">The automated investigation results in a verdict for each piece of evidence.</span></span> <span data-ttu-id="7ec08-139">評決は次の場合があります。</span><span class="sxs-lookup"><span data-stu-id="7ec08-139">Verdicts can be:</span></span>
- <span data-ttu-id="7ec08-140">*悪意*</span><span class="sxs-lookup"><span data-stu-id="7ec08-140">*Malicious*</span></span>
- <span data-ttu-id="7ec08-141">*Suspicious (不審)*</span><span class="sxs-lookup"><span data-stu-id="7ec08-141">*Suspicious*</span></span> 
- <span data-ttu-id="7ec08-142">*脅威は検出されませんでした*</span><span class="sxs-lookup"><span data-stu-id="7ec08-142">*No threats found*</span></span> 

<span data-ttu-id="7ec08-143">悪意のあるエンティティまたは疑わしいエンティティの修復アクションが識別されます。</span><span class="sxs-lookup"><span data-stu-id="7ec08-143">Remediation actions for malicious or suspicious entities are identified.</span></span> <span data-ttu-id="7ec08-144">修復アクションの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7ec08-144">Examples of remediation actions include:</span></span>

- <span data-ttu-id="7ec08-145">ファイルを検疫に送信する</span><span class="sxs-lookup"><span data-stu-id="7ec08-145">Sending a file to quarantine</span></span>
- <span data-ttu-id="7ec08-146">プロセスの停止</span><span class="sxs-lookup"><span data-stu-id="7ec08-146">Stopping a process</span></span>
- <span data-ttu-id="7ec08-147">デバイスの分離</span><span class="sxs-lookup"><span data-stu-id="7ec08-147">Isolating a device</span></span>
- <span data-ttu-id="7ec08-148">URL のブロック</span><span class="sxs-lookup"><span data-stu-id="7ec08-148">Blocking a URL</span></span> 
- <span data-ttu-id="7ec08-149">その他のアクション</span><span class="sxs-lookup"><span data-stu-id="7ec08-149">Other actions</span></span>

<span data-ttu-id="7ec08-150">詳細については、「Defender の修復アクション[」を参照Microsoft 365してください](m365d-remediation-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="7ec08-150">For more information, see See [Remediation actions in Microsoft 365 Defender](m365d-remediation-actions.md).</span></span>

<span data-ttu-id="7ec08-151">組織の [自動調査](m365d-configure-auto-investigation-response.md) および対応機能の構成方法に応じて、修復アクションは自動的に実行するか、セキュリティ運用チームによる承認を受けた場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="7ec08-151">Depending on [how automated investigation and response capabilities are configured](m365d-configure-auto-investigation-response.md) for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="7ec08-152">保留中か完了かのアクションはすべて、アクション センターに [一覧表示されます](m365d-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7ec08-152">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md).</span></span>

<span data-ttu-id="7ec08-153">調査の実行中にその他の関連する警告が発生した場合は、それらの警告は調査が完了するまで調査に追加され続けます。</span><span class="sxs-lookup"><span data-stu-id="7ec08-153">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="7ec08-154">影響を受けるエンティティが他の場所に表示される場合、自動調査によって対象範囲が拡大され、そのエンティティが含まれると、調査プロセスが繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="7ec08-154">If an affected entity is seen elsewhere, the automated investigation expands its scope to include that entity, and the investigation process repeats.</span></span> 

<span data-ttu-id="7ec08-155">[Microsoft 365 Defender] では、次の表に示す通り、各自動調査では、Microsoft Defender for Identity、Microsoft Defender for Endpoint、Microsoft Defender for Office 365 の信号を関連付ける。</span><span class="sxs-lookup"><span data-stu-id="7ec08-155">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Microsoft Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="7ec08-156">エンティティ</span><span class="sxs-lookup"><span data-stu-id="7ec08-156">Entities</span></span> |<span data-ttu-id="7ec08-157">脅威対策サービス</span><span class="sxs-lookup"><span data-stu-id="7ec08-157">Threat protection services</span></span>  |
|:---------|:---------|
|<span data-ttu-id="7ec08-158">デバイス (エンドポイントまたはコンピューターとも呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="7ec08-158">Devices (also referred to as endpoints or machines)</span></span> |[<span data-ttu-id="7ec08-159">Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7ec08-159">Defender for Endpoint</span></span>](../defender-endpoint/automated-investigations.md) |      
|<span data-ttu-id="7ec08-160">オンプレミスの Active Directory ユーザー、エンティティの動作、およびアクティビティ</span><span class="sxs-lookup"><span data-stu-id="7ec08-160">On-premises Active Directory users, entity behavior, and activities</span></span>     |[<span data-ttu-id="7ec08-161">Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="7ec08-161">Defender for Identity</span></span>](/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="7ec08-162">電子メール コンテンツ (ファイルと URL を含む電子メール メッセージ)</span><span class="sxs-lookup"><span data-stu-id="7ec08-162">Email content (email messages that can contain files and URLs)</span></span>     |[<span data-ttu-id="7ec08-163">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="7ec08-163">Defender for Office 365</span></span>](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> <span data-ttu-id="7ec08-164">すべてのアラートが自動調査をトリガーする場合と、すべての調査によって自動修復アクションが発生する場合ではありません。</span><span class="sxs-lookup"><span data-stu-id="7ec08-164">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions.</span></span> <span data-ttu-id="7ec08-165">組織の自動調査と対応の構成方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="7ec08-165">It depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="7ec08-166">「 [自動調査と応答機能の構成」を参照してください](m365d-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="7ec08-166">See [Configure automated investigation and response capabilities](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="viewing-a-list-of-investigations"></a><span data-ttu-id="7ec08-167">調査の一覧の表示</span><span class="sxs-lookup"><span data-stu-id="7ec08-167">Viewing a list of investigations</span></span>

<span data-ttu-id="7ec08-168">調査を表示するには、[インシデント] **ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="7ec08-168">To view investigations, go to the **Incidents** page.</span></span> <span data-ttu-id="7ec08-169">インシデントを選択し、[調査] **タブを選択** します。詳細については、「自動調査 [の詳細と結果」を参照してください](m365d-autoir-results.md)。</span><span class="sxs-lookup"><span data-stu-id="7ec08-169">Select an incident, and then select the **Investigations** tab. To learn more, see [Details and results of an automated investigation](m365d-autoir-results.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="7ec08-170">次の手順</span><span class="sxs-lookup"><span data-stu-id="7ec08-170">Next steps</span></span>

- [<span data-ttu-id="7ec08-171">自動調査と対応の前提条件を確認する</span><span class="sxs-lookup"><span data-stu-id="7ec08-171">See the prerequisites for automated investigation and response</span></span>](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="7ec08-172">組織の自動調査と対応を構成する</span><span class="sxs-lookup"><span data-stu-id="7ec08-172">Configure automated investigation and response for your organization</span></span>](m365d-configure-auto-investigation-response.md)
- [<span data-ttu-id="7ec08-173">アクション センターの詳細</span><span class="sxs-lookup"><span data-stu-id="7ec08-173">Learn more about the Action center</span></span>](m365d-action-center.md)
