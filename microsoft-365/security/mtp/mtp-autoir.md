---
title: Microsoft Threat Protection での自動調査および対応
description: Microsoft の脅威保護における自動調査と応答機能の概要 (自己復旧とも呼ばれる) を取得する
keywords: 自動化、調査、警告、トリガー、アクション、修復、自己復旧
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: f2a0a439996f13cea3823815aceb9dd1c235e2f2
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962667"
---
# <a name="automated-investigation-and-response-in-microsoft-threat-protection"></a><span data-ttu-id="28e8b-104">Microsoft Threat Protection での自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="28e8b-104">Automated investigation and response in Microsoft Threat Protection</span></span>

<span data-ttu-id="28e8b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="28e8b-105">**Applies to:**</span></span>
- <span data-ttu-id="28e8b-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="28e8b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="28e8b-107">セキュリティの警告がトリガーされたときに、そのような警告を確認し、組織を保護するための手順を実行することは、セキュリティ運用チームにかかっています。</span><span class="sxs-lookup"><span data-stu-id="28e8b-107">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="28e8b-108">警告の優先順位付けと調査には、多くの時間がかかる場合があります。調査実行中に新しい警告が出されるような状況では、この傾向が特に強くなります。</span><span class="sxs-lookup"><span data-stu-id="28e8b-108">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="28e8b-109">セキュリティ運用チームは、監視および保護を必要とする脅威の膨大さに圧倒されてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="28e8b-109">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="28e8b-110">自動化された調査と応答の機能、自動修復機能、Microsoft の脅威保護が役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="28e8b-110">Automated investigation and response capabilities, with self-healing, in Microsoft Threat Protection can help.</span></span>

<span data-ttu-id="28e8b-111">セルフ修復のしくみについては、次のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="28e8b-111">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="28e8b-112">Microsoft の脅威保護では、自動調査と自己復旧機能による応答は、デバイス、電子メール & コンテンツ、および id に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="28e8b-112">In Microsoft Threat Protection, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span> <span data-ttu-id="28e8b-113">Microsoft の脅威保護は、次の機能を統合します。</span><span class="sxs-lookup"><span data-stu-id="28e8b-113">Microsoft Threat Protection brings together capabilities from:</span></span> 
- [<span data-ttu-id="28e8b-114">Microsoft Defender Advanced Threat Protection の自動化された調査と修復</span><span class="sxs-lookup"><span data-stu-id="28e8b-114">Automated investigation and remediation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [<span data-ttu-id="28e8b-115">Office 365 Advanced Threat Protection の自動調査と応答</span><span class="sxs-lookup"><span data-stu-id="28e8b-115">Automated investigation and response in Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [<span data-ttu-id="28e8b-116">Azure advanced threat detection</span><span class="sxs-lookup"><span data-stu-id="28e8b-116">Azure advanced threat detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [<span data-ttu-id="28e8b-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="28e8b-117">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
<span data-ttu-id="28e8b-118">この記事では、自動化された調査と応答のしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="28e8b-118">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="28e8b-119">これらの機能を構成するには、「 [Microsoft Threat Protection で自動調査と応答機能を構成](mtp-configure-auto-investigation-response.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28e8b-119">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft Threat Protection](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-virtual-analyst"></a><span data-ttu-id="28e8b-120">仮想アナリスト</span><span class="sxs-lookup"><span data-stu-id="28e8b-120">Your virtual analyst</span></span>

<span data-ttu-id="28e8b-121">組織のレベル 1 またはレベル 2 のセキュリティ運用チームは、仮想アナリストを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="28e8b-121">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="28e8b-122">仮想アナリストは、セキュリティ運用チームであれば実行するであろう脅威の調査と修復の最適な手順を模倣して実行します。</span><span class="sxs-lookup"><span data-stu-id="28e8b-122">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="28e8b-123">仮想アシスタントは、処理能力の制限なしに24時間年中無休で作業することが可能で、調査と脅威の修復を大量に処理することができます。</span><span class="sxs-lookup"><span data-stu-id="28e8b-123">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="28e8b-124">このような仮想アシスタントを使用すると、対応するまでの時間を大幅に短縮できます。その結果、セキュリティ運用チームでは、その他の重要な戦略的プロジェクトに取り組むための時間的余裕が生まれます。</span><span class="sxs-lookup"><span data-stu-id="28e8b-124">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="28e8b-125">このシナリオがサイエンスのように聞こえる場合は、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="28e8b-125">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="28e8b-126">このような仮想アナリストは、Microsoft の脅威保護スイートの一部であり、その名前は自動化された *調査と応答*です。</span><span class="sxs-lookup"><span data-stu-id="28e8b-126">Such a virtual analyst is part of your Microsoft Threat Protection suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="28e8b-127">自動化された調査と応答により、セキュリティ運用チームはセキュリティの警告とインシデントを処理するために組織の処理能力を飛躍的に向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="28e8b-127">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="28e8b-128">自動調査と応答を使用すると、調査および修復アクティビティを処理するコストを削減し、脅威保護スイートを最大限に活用することができます。</span><span class="sxs-lookup"><span data-stu-id="28e8b-128">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="28e8b-129">自動化された調査と応答によって、セキュリティ運用チームは次のことができます。</span><span class="sxs-lookup"><span data-stu-id="28e8b-129">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="28e8b-130">脅威に対してアクションを実行する必要があるかどうかの判断。</span><span class="sxs-lookup"><span data-stu-id="28e8b-130">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="28e8b-131">必要な修復アクションの実行 (または推奨)。</span><span class="sxs-lookup"><span data-stu-id="28e8b-131">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="28e8b-132">実行する必要がある追加の調査の特定。</span><span class="sxs-lookup"><span data-stu-id="28e8b-132">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="28e8b-133">必要に応じた、他の警告に対するプロセスの反復。</span><span class="sxs-lookup"><span data-stu-id="28e8b-133">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="28e8b-134">自動調査のプロセス</span><span class="sxs-lookup"><span data-stu-id="28e8b-134">The automated investigation process</span></span>

<span data-ttu-id="28e8b-135">[**Alert (警告)**] > [**incident (インシデント)**] > [**automated investigation (自動調査)**] > [**verdict (判定)**] > [**remediation action (修復アクション)**]</span><span class="sxs-lookup"><span data-stu-id="28e8b-135">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="28e8b-136">トリガーされた通知は、インシデントを作成します。これにより、自動調査が開始されます。</span><span class="sxs-lookup"><span data-stu-id="28e8b-136">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="28e8b-137">この調査の結果、1 つまたは複数の修復アクションが実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="28e8b-137">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="28e8b-138">Microsoft Threat Protection では、次の表にまとめたとおり、各自動調査により Azure Advanced Threat Protection (Azure ATP)、Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)、Office 365 Advanced Threat Protection (Office 365 ATP) の間でシグナルの関連付けが行われます。</span><span class="sxs-lookup"><span data-stu-id="28e8b-138">In Microsoft Threat Protection, each automated investigation correlates signals across Azure Advanced Threat Protection (Azure ATP), Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP), and Office 365 Advanced Threat Protection (Office 365 ATP), as summarized in the following table:</span></span> 

|<span data-ttu-id="28e8b-139">エンティティ</span><span class="sxs-lookup"><span data-stu-id="28e8b-139">Entities</span></span> |<span data-ttu-id="28e8b-140">脅威対策サービス</span><span class="sxs-lookup"><span data-stu-id="28e8b-140">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="28e8b-141">デバイス (エンドポイントとも呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="28e8b-141">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="28e8b-142">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="28e8b-142">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="28e8b-143">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="28e8b-143">Azure ATP</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="28e8b-144">メールの内容 (メールボックス内のファイルとメッセージ)</span><span class="sxs-lookup"><span data-stu-id="28e8b-144">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="28e8b-145">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="28e8b-145">Office 365 ATP</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="28e8b-146">各調査では、調査対象の各証拠に対して、verdicts (*悪意*、 *疑わしい*、または *脅威なし) が*生成されます。</span><span class="sxs-lookup"><span data-stu-id="28e8b-146">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="28e8b-147">脅威の種類および結果の verdict に応じて、修復アクションは自動的に、または組織のセキュリティ運用チームによる承認時に発生します。</span><span class="sxs-lookup"><span data-stu-id="28e8b-147">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="28e8b-148">保留中および完了済みのアクションは、[アクション センター](mtp-action-center.md)に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="28e8b-148">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="28e8b-149">調査の実行中にその他の関連する警告が発生した場合は、それらの警告は調査が完了するまで調査に追加され続けます。</span><span class="sxs-lookup"><span data-stu-id="28e8b-149">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="28e8b-150">有害なエンティティが別の場所に見つかった場合、そのエンティティを対象に含めるために自動調査の対象範囲が拡大され、全般的なセキュリティのプレイブックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="28e8b-150">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="28e8b-151">すべてのアラートが自動化された調査をトリガーするわけではなく、自動修復処理で調査結果がすべて行われるわけではありません。これは、組織で自動化された調査と応答の構成方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="28e8b-151">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="28e8b-152">「 [Configure 自動調査および応答機能を Microsoft の脅威保護に構成する](mtp-configure-auto-investigation-response.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28e8b-152">See [Configure automated investigation and response capabilities in Microsoft Threat Protection](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="28e8b-153">次の手順</span><span class="sxs-lookup"><span data-stu-id="28e8b-153">Next steps</span></span>

- [<span data-ttu-id="28e8b-154">Microsoft の脅威保護における自動調査と応答の前提条件を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28e8b-154">See the prerequisites for automated investigation and response in Microsoft Threat Protection</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection)
- [<span data-ttu-id="28e8b-155">組織の自動化された調査と応答を構成する</span><span class="sxs-lookup"><span data-stu-id="28e8b-155">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="28e8b-156">アクション センターの詳細</span><span class="sxs-lookup"><span data-stu-id="28e8b-156">Learn more about the Action center</span></span>](mtp-action-center.md)
