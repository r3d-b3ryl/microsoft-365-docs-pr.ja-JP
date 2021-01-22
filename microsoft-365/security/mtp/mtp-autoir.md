---
title: Microsoft 365 Defender での自動調査と対応
description: Microsoft 365 Defender で自動調査および対応機能 (自己修復とも呼ばれる) の概要を確認する
keywords: 自動化, 調査, アラート, トリガー, アクション, 修復, 自己修復
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930332"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="e1b89-104">Microsoft 365 Defender での自動調査と対応</span><span class="sxs-lookup"><span data-stu-id="e1b89-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e1b89-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e1b89-105">**Applies to:**</span></span>
- <span data-ttu-id="e1b89-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1b89-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="e1b89-107">Microsoft 365 Defender を体験したい場合</span><span class="sxs-lookup"><span data-stu-id="e1b89-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="e1b89-108">ラボ環境 [で評価したり、](https://aka.ms/mtp-trial-lab) パイロット プロジェクトを実 [稼働環境で実行することができます](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="e1b89-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="e1b89-109">自動調査と自己修復のしくみ</span><span class="sxs-lookup"><span data-stu-id="e1b89-109">How automated investigation and self-healing works</span></span>

<span data-ttu-id="e1b89-110">セキュリティの警告がトリガーされると、セキュリティ運用チームがそれらのアラートを確認し、組織を保護するための手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1b89-110">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="e1b89-111">警告の優先順位付けと調査には、多くの時間がかかる場合があります。調査実行中に新しい警告が出されるような状況では、この傾向が特に強くなります。</span><span class="sxs-lookup"><span data-stu-id="e1b89-111">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="e1b89-112">セキュリティ運用チームは、監視および保護を必要とする脅威の膨大さに圧倒されてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1b89-112">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="e1b89-113">Microsoft 365 Defender の自動調査および対応機能 (自己修復機能) が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e1b89-113">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="e1b89-114">自己修復のしくみについては、次のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e1b89-114">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="e1b89-115">Microsoft 365 Defender では、自動調査と自動修復機能による対応は、デバイス、電子メール、メール、コンテンツ& ID 全体で機能します。</span><span class="sxs-lookup"><span data-stu-id="e1b89-115">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="e1b89-116">この記事では、自動調査と対応のしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e1b89-116">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="e1b89-117">これらの機能を構成するには [、「Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)で自動調査および対応機能を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1b89-117">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="e1b89-118">独自の仮想アナリスト</span><span class="sxs-lookup"><span data-stu-id="e1b89-118">Your own virtual analyst</span></span>

<span data-ttu-id="e1b89-119">組織のレベル 1 またはレベル 2 のセキュリティ運用チームは、仮想アナリストを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e1b89-119">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="e1b89-120">仮想アナリストは、セキュリティ運用チームであれば実行するであろう脅威の調査と修復の最適な手順を模倣して実行します。</span><span class="sxs-lookup"><span data-stu-id="e1b89-120">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="e1b89-121">仮想アシスタントは、処理能力の制限なしに24時間年中無休で作業することが可能で、調査と脅威の修復を大量に処理することができます。</span><span class="sxs-lookup"><span data-stu-id="e1b89-121">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="e1b89-122">このような仮想アシスタントを使用すると、対応するまでの時間を大幅に短縮できます。その結果、セキュリティ運用チームでは、その他の重要な戦略的プロジェクトに取り組むための時間的余裕が生まれます。</span><span class="sxs-lookup"><span data-stu-id="e1b89-122">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="e1b89-123">このシナリオがサイエンス フィクションのように聞こえる場合は、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="e1b89-123">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="e1b89-124">このような仮想アナリストは、Microsoft 365 Defender スイートの一部であり、その名前は自動 *調査と対応です*。</span><span class="sxs-lookup"><span data-stu-id="e1b89-124">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="e1b89-125">自動調査と対応により、セキュリティ運用チームは、セキュリティの警告やインシデントに対処する組織の能力を大幅に増やします。</span><span class="sxs-lookup"><span data-stu-id="e1b89-125">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="e1b89-126">自動調査と対応により、調査と修復アクティビティに対応するコストを削減し、脅威保護スイートを最大に引き出します。</span><span class="sxs-lookup"><span data-stu-id="e1b89-126">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="e1b89-127">自動調査と対応により、セキュリティ運用チームは次の作業を行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e1b89-127">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="e1b89-128">脅威に対してアクションを実行する必要があるかどうかの判断。</span><span class="sxs-lookup"><span data-stu-id="e1b89-128">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="e1b89-129">必要な修復アクションの実行 (または推奨)。</span><span class="sxs-lookup"><span data-stu-id="e1b89-129">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="e1b89-130">実行する必要がある追加の調査の特定。</span><span class="sxs-lookup"><span data-stu-id="e1b89-130">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="e1b89-131">必要に応じた、他の警告に対するプロセスの反復。</span><span class="sxs-lookup"><span data-stu-id="e1b89-131">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="e1b89-132">自動調査のプロセス</span><span class="sxs-lookup"><span data-stu-id="e1b89-132">The automated investigation process</span></span>

<span data-ttu-id="e1b89-133">[**Alert (警告)**] > [**incident (インシデント)**] > [**automated investigation (自動調査)**] > [**verdict (判定)**] > [**remediation action (修復アクション)**]</span><span class="sxs-lookup"><span data-stu-id="e1b89-133">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="e1b89-134">トリガーされたアラートによってインシデントが作成され、自動調査を開始できます。</span><span class="sxs-lookup"><span data-stu-id="e1b89-134">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="e1b89-135">この調査の結果、1 つまたは複数の修復アクションが実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1b89-135">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="e1b89-136">Microsoft 365 Defender では、次の表にまとめると、各自動調査では、Id 用 Microsoft Defender、エンドポイント用 Microsoft Defender、および Office 365 用 Defender のシグナルが関連付けされます。</span><span class="sxs-lookup"><span data-stu-id="e1b89-136">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="e1b89-137">エンティティ</span><span class="sxs-lookup"><span data-stu-id="e1b89-137">Entities</span></span> |<span data-ttu-id="e1b89-138">脅威対策サービス</span><span class="sxs-lookup"><span data-stu-id="e1b89-138">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="e1b89-139">デバイス (エンドポイントとも呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="e1b89-139">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="e1b89-140">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e1b89-140">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="e1b89-141">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="e1b89-141">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="e1b89-142">メールの内容 (メールボックス内のファイルとメッセージ)</span><span class="sxs-lookup"><span data-stu-id="e1b89-142">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="e1b89-143">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="e1b89-143">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="e1b89-144">各調査では、調査した各証拠に対して、(*悪意* のある、疑わしい、または検出された脅威 *がない)* という特定の証拠が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e1b89-144">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="e1b89-145">脅威の種類と結果の特定の状況に応じて、修復アクションは自動的に行われるか、組織のセキュリティ運用チームの承認を受け、実行されます。</span><span class="sxs-lookup"><span data-stu-id="e1b89-145">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="e1b89-146">保留中および完了済みのアクションは、[アクション センター](mtp-action-center.md)に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1b89-146">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="e1b89-147">調査の実行中にその他の関連する警告が発生した場合は、それらの警告は調査が完了するまで調査に追加され続けます。</span><span class="sxs-lookup"><span data-stu-id="e1b89-147">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="e1b89-148">有害なエンティティが別の場所に見つかった場合、そのエンティティを対象に含めるために自動調査の対象範囲が拡大され、全般的なセキュリティのプレイブックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e1b89-148">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="e1b89-149">すべてのアラートによって自動調査がトリガーされるのではなく、すべての調査結果が自動修復アクションで発生する場合ではありません。これはすべて、組織に対して自動調査と対応がどのように構成されているのかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e1b89-149">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="e1b89-150">[「Microsoft 365 Defender での自動調査および対応機能の構成」をご覧ください](mtp-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="e1b89-150">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="e1b89-151">次の手順</span><span class="sxs-lookup"><span data-stu-id="e1b89-151">Next steps</span></span>

- [<span data-ttu-id="e1b89-152">Microsoft 365 Defender での自動調査と対応の前提条件を確認する</span><span class="sxs-lookup"><span data-stu-id="e1b89-152">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="e1b89-153">組織の自動調査と対応を構成する</span><span class="sxs-lookup"><span data-stu-id="e1b89-153">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="e1b89-154">アクション センターの詳細</span><span class="sxs-lookup"><span data-stu-id="e1b89-154">Learn more about the Action center</span></span>](mtp-action-center.md)
