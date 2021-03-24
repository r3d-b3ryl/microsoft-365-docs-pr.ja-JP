---
title: Microsoft 365 Defender での自動調査と対応
description: Microsoft 365 Defender の自動調査および応答機能 (自己修復とも呼ばれる) の概要を確認する
keywords: 自動化、調査、アラート、トリガー、アクション、修復、自己修復
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c12937c016875c26a7212117e41aac4349cb540d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065900"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="462de-104">Microsoft 365 Defender での自動調査と対応</span><span class="sxs-lookup"><span data-stu-id="462de-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="462de-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="462de-105">**Applies to:**</span></span>
- <span data-ttu-id="462de-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="462de-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="462de-107">組織で Microsoft [365 Defender を](microsoft-365-defender.md)使用している場合、悪意のあるアーティファクトや疑わしいアーティファクトが検出されると、セキュリティ運用チームは警告を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="462de-107">If your organization is using [Microsoft 365 Defender](microsoft-365-defender.md), your security operations team receives an alert whenever a malicious or suspicious artifact is detected.</span></span> <span data-ttu-id="462de-108">一見終わりのない脅威の流れを考えると、セキュリティ チームは多くの場合、アラートの量が多い場合に対処する上で課題に直面します。</span><span class="sxs-lookup"><span data-stu-id="462de-108">Given the seemingly never-ending flow of threats that come in, security teams often face challenges in addressing the high volume of alerts.</span></span> <span data-ttu-id="462de-109">幸いなことに、Microsoft 365 Defender には自動調査と修復 (AIR) 機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="462de-109">Fortunately, Microsoft 365 Defender includes automated investigation and remediation (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span>

<span data-ttu-id="462de-110">この記事では、AIR の概要を説明し、次の手順と追加のリソースへのリンクを含みます。</span><span class="sxs-lookup"><span data-stu-id="462de-110">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="462de-111">Microsoft 365 Defender を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="462de-111">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="462de-112">[ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。</span><span class="sxs-lookup"><span data-stu-id="462de-112">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="462de-113">自動調査と自己修復の仕組み</span><span class="sxs-lookup"><span data-stu-id="462de-113">How automated investigation and self-healing works</span></span>

<span data-ttu-id="462de-114">セキュリティアラートがトリガーされると、セキュリティ運用チームがこれらのアラートを確認し、組織を保護するための手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="462de-114">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="462de-115">警告の優先順位付けと調査には、多くの時間がかかる場合があります。調査実行中に新しい警告が出されるような状況では、この傾向が特に強くなります。</span><span class="sxs-lookup"><span data-stu-id="462de-115">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="462de-116">セキュリティ運用チームは、監視および保護を必要とする脅威の膨大さに圧倒されてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="462de-116">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="462de-117">Microsoft 365 Defender では、自己修復機能を使用した自動調査と対応機能が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="462de-117">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="462de-118">自己修復のしくみについては、次のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="462de-118">Watch the following video to see how self-healing works:</span></span> <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="462de-119">Microsoft 365 Defender では、自己修復機能を備えた自動調査と応答は、デバイス、電子メール、コンテンツ、および id 間&機能します。</span><span class="sxs-lookup"><span data-stu-id="462de-119">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="462de-120">この記事では、自動調査と対応のしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="462de-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="462de-121">これらの機能を構成するには [、「Configure automated investigation and response capabilitis in Microsoft 365 Defender」を参照してください](m365d-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="462de-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="462de-122">独自の仮想アナリスト</span><span class="sxs-lookup"><span data-stu-id="462de-122">Your own virtual analyst</span></span>

<span data-ttu-id="462de-123">Tier 1 または Tier 2 のセキュリティ運用チームに仮想アナリストを持つことを想像してください。</span><span class="sxs-lookup"><span data-stu-id="462de-123">Imagine having a virtual analyst in your Tier 1 or Tier 2 security operations team.</span></span> <span data-ttu-id="462de-124">仮想アナリストは、セキュリティ運用チームであれば実行するであろう脅威の調査と修復の最適な手順を模倣して実行します。</span><span class="sxs-lookup"><span data-stu-id="462de-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="462de-125">仮想アシスタントは、処理能力の制限なしに24時間年中無休で作業することが可能で、調査と脅威の修復を大量に処理することができます。</span><span class="sxs-lookup"><span data-stu-id="462de-125">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="462de-126">このような仮想アシスタントを使用すると、対応するまでの時間を大幅に短縮できます。その結果、セキュリティ運用チームでは、その他の重要な戦略的プロジェクトに取り組むための時間的余裕が生まれます。</span><span class="sxs-lookup"><span data-stu-id="462de-126">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="462de-127">このシナリオが SF のように聞こえる場合は、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="462de-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="462de-128">このような仮想アナリストは、Microsoft 365 Defender スイートの一部であり、その名前は自動 *調査と応答です*。</span><span class="sxs-lookup"><span data-stu-id="462de-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="462de-129">自動調査と対応機能により、セキュリティ運用チームは、セキュリティアラートやインシデントに対処する組織の能力を大幅に向上できます。</span><span class="sxs-lookup"><span data-stu-id="462de-129">Automated investigation and response capabilities enable your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="462de-130">自動調査と対応により、調査と修復の処理コストを削減し、脅威保護スイートを有効に利用できます。</span><span class="sxs-lookup"><span data-stu-id="462de-130">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="462de-131">自動調査と対応機能は、次の方法でセキュリティ運用チームを支援します。</span><span class="sxs-lookup"><span data-stu-id="462de-131">Automated investigation and response capabilities help your security operations team by:</span></span>

1. <span data-ttu-id="462de-132">脅威に対してアクションを実行する必要があるかどうかの判断。</span><span class="sxs-lookup"><span data-stu-id="462de-132">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="462de-133">必要な修復アクションを実行 (または推奨) する。</span><span class="sxs-lookup"><span data-stu-id="462de-133">Taking (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="462de-134">他の調査が行われるかどうかを決定する。そして</span><span class="sxs-lookup"><span data-stu-id="462de-134">Determining whether and what other investigations should occur; and</span></span>
4. <span data-ttu-id="462de-135">必要に応じた、他の警告に対するプロセスの反復。</span><span class="sxs-lookup"><span data-stu-id="462de-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="462de-136">自動調査のプロセス</span><span class="sxs-lookup"><span data-stu-id="462de-136">The automated investigation process</span></span>

<span data-ttu-id="462de-137">アラートによってインシデントが作成され、自動調査を開始できます。</span><span class="sxs-lookup"><span data-stu-id="462de-137">An alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="462de-138">自動調査の結果、各証拠の評決が下されます。</span><span class="sxs-lookup"><span data-stu-id="462de-138">The automated investigation results in a verdict for each piece of evidence.</span></span> <span data-ttu-id="462de-139">評決は次の場合があります。</span><span class="sxs-lookup"><span data-stu-id="462de-139">Verdicts can be:</span></span>
- <span data-ttu-id="462de-140">*悪意のある*;</span><span class="sxs-lookup"><span data-stu-id="462de-140">*Malicious*;</span></span>
- <span data-ttu-id="462de-141">*疑わしい*。または</span><span class="sxs-lookup"><span data-stu-id="462de-141">*Suspicious*; or</span></span> 
- <span data-ttu-id="462de-142">*脅威が見つかりません*。</span><span class="sxs-lookup"><span data-stu-id="462de-142">*No threats found*.</span></span> 

<span data-ttu-id="462de-143">悪意のあるエンティティまたは疑わしいエンティティの修復アクションが識別されます。</span><span class="sxs-lookup"><span data-stu-id="462de-143">Remediation actions for malicious or suspicious entities are identified.</span></span> <span data-ttu-id="462de-144">修復アクションの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="462de-144">Examples of remediation actions include:</span></span>
- <span data-ttu-id="462de-145">検疫にファイルを送信する。</span><span class="sxs-lookup"><span data-stu-id="462de-145">Sending a file to quarantine;</span></span>
- <span data-ttu-id="462de-146">プロセスの停止。</span><span class="sxs-lookup"><span data-stu-id="462de-146">Stopping a process;</span></span>
- <span data-ttu-id="462de-147">デバイスの分離。</span><span class="sxs-lookup"><span data-stu-id="462de-147">Isolating a device;</span></span>
- <span data-ttu-id="462de-148">URL をブロックする。そして</span><span class="sxs-lookup"><span data-stu-id="462de-148">Blocking a URL; and</span></span> 
- <span data-ttu-id="462de-149">その他のアクション。</span><span class="sxs-lookup"><span data-stu-id="462de-149">other actions.</span></span> <span data-ttu-id="462de-150">[(「Microsoft 365 Defender での修復アクション」を参照](m365d-remediation-actions.md)してください。</span><span class="sxs-lookup"><span data-stu-id="462de-150">(See [Remediation actions in Microsoft 365 Defender](m365d-remediation-actions.md).)</span></span>

<span data-ttu-id="462de-151">組織の [自動調査](m365d-configure-auto-investigation-response.md) および対応機能の構成方法に応じて、修復アクションは自動的に実行するか、セキュリティ運用チームによる承認を受けた場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="462de-151">Depending on [how automated investigation and response capabilities are configured](m365d-configure-auto-investigation-response.md) for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="462de-152">保留中か完了かのアクションはすべて、アクション センターに [一覧表示されます](m365d-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="462de-152">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md).</span></span>

<span data-ttu-id="462de-153">調査の実行中にその他の関連する警告が発生した場合は、それらの警告は調査が完了するまで調査に追加され続けます。</span><span class="sxs-lookup"><span data-stu-id="462de-153">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="462de-154">犯罪を起こしているエンティティが他の場所に表示される場合、自動化された調査はスコープを拡大してそのエンティティを含め、調査プロセスが繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="462de-154">If an incriminated entity is seen elsewhere, the automated investigation expands its scope to include that entity, and the investigation process repeats.</span></span> 

<span data-ttu-id="462de-155">Microsoft 365 Defender では、次の表にまとめると、各自動調査は、Microsoft Defender for Identity、Microsoft Defender for Endpoint、Defender for Office 365 の信号を相互に関連付けします。</span><span class="sxs-lookup"><span data-stu-id="462de-155">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="462de-156">エンティティ</span><span class="sxs-lookup"><span data-stu-id="462de-156">Entities</span></span> |<span data-ttu-id="462de-157">脅威対策サービス</span><span class="sxs-lookup"><span data-stu-id="462de-157">Threat protection services</span></span>  |
|:---------|:---------|
|<span data-ttu-id="462de-158">デバイス (エンドポイントとも呼ばれますが、コンピューターとも呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="462de-158">Devices (also referred to as endpoints, and sometimes referred to as machines)</span></span>     |[<span data-ttu-id="462de-159">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="462de-159">Microsoft Defender for Endpoint</span></span>](../defender-endpoint/automated-investigations.md)<br/>[<span data-ttu-id="462de-160">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="462de-160">Microsoft Defender for Identity</span></span>](/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="462de-161">電子メール コンテンツ (ファイルと URL を含む電子メール メッセージ)</span><span class="sxs-lookup"><span data-stu-id="462de-161">Email content (email messages that can contain files and URLs)</span></span>     |[<span data-ttu-id="462de-162">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="462de-162">Microsoft Defender for Office 365</span></span>](../defender-365-security/defender-for-office-365.md)         |

> [!NOTE]
> <span data-ttu-id="462de-163">すべてのアラートによって自動調査がトリガーされるのではなく、すべての調査によって自動修復アクションが発生する場合はそうではありません。組織の自動調査と対応の構成方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="462de-163">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; it depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="462de-164">「Microsoft [365 Defender で自動](m365d-configure-auto-investigation-response.md)調査と応答機能を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462de-164">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="462de-165">次の手順</span><span class="sxs-lookup"><span data-stu-id="462de-165">Next steps</span></span>

- [<span data-ttu-id="462de-166">Microsoft 365 Defender での自動調査と対応の前提条件を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462de-166">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="462de-167">組織の自動調査と対応を構成する</span><span class="sxs-lookup"><span data-stu-id="462de-167">Configure automated investigation and response for your organization</span></span>](m365d-configure-auto-investigation-response.md)
- [<span data-ttu-id="462de-168">アクション センターの詳細</span><span class="sxs-lookup"><span data-stu-id="462de-168">Learn more about the Action center</span></span>](m365d-action-center.md)
