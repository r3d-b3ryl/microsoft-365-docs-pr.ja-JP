---
title: 時間のかかるメール フロー ルールの修正のインサイト
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターで [低速メール フロー ルールの修正] 分析情報を使用して、組織内の非効率的または壊れたメール フロー ルール (トランスポート ルールとも呼ばれる) を特定して修正する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 51ffa92402fd3e7c9e76115642426d3cce0a9e19
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205293"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="e8aa6-103">セキュリティ コンプライアンス センターでメール フロー ルールの分析情報が遅&修正する</span><span class="sxs-lookup"><span data-stu-id="e8aa6-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e8aa6-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="e8aa6-104">**Applies to**</span></span>
- [<span data-ttu-id="e8aa6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e8aa6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e8aa6-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="e8aa6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e8aa6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8aa6-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e8aa6-108">非効率的なメール フロー ルール (トランスポート ルールとも呼ばれる) は、組織のメール フローの遅延につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e8aa6-108">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="e8aa6-109">この分析情報は、組織のメール フローに影響を与えるメール フロー ルールを報告します。</span><span class="sxs-lookup"><span data-stu-id="e8aa6-109">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="e8aa6-110">これらの種類のルールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e8aa6-110">Examples of these types of rules include:</span></span>

- <span data-ttu-id="e8aa6-111">大規模なグループ **の Is メンバーを** 使用する条件。</span><span class="sxs-lookup"><span data-stu-id="e8aa6-111">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="e8aa6-112">複雑な正規表現 (regex) パターンマッチングを使用する条件。</span><span class="sxs-lookup"><span data-stu-id="e8aa6-112">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="e8aa6-113">添付ファイルのコンテンツ チェックインを使用する条件。</span><span class="sxs-lookup"><span data-stu-id="e8aa6-113">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="e8aa6-114">セキュリティ [&](https://protection.office.com)コンプライアンス センターのメールフロー ダッシュボードの[](mail-flow-insights-v2.md)[推奨されるユーザー] 領域にある [メール フロー ルールの修正] インサイトは、メール フロー ルールの完了に時間がかかっているときに通知します。</span><span class="sxs-lookup"><span data-stu-id="e8aa6-114">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="e8aa6-115">この分析情報は、条件が検出された後にのみ表示されます (メール ループが発生しない場合は、分析情報は表示されません)。</span><span class="sxs-lookup"><span data-stu-id="e8aa6-115">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="e8aa6-116">この通知を使用すると、メール フロー ルールを特定して微調整し、メール フローの遅延を減らすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e8aa6-116">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![メール フロー ダッシュボードの [おすすめ] 領域でメール フロー ルールの低速分析情報を修正する](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="e8aa6-118">ウィジェットの [ **詳細の表示]** をクリックすると、詳細情報が表示されるフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8aa6-118">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="e8aa6-119">**ルール**: 概要にカーソルを合わせると、ルールのすべての条件、例外、およびアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8aa6-119">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="e8aa6-120">概要をクリックすると、管理センター (EAC) のExchange編集できます。</span><span class="sxs-lookup"><span data-stu-id="e8aa6-120">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="e8aa6-121">**評価されるメッセージの** 数 : [サンプル メッセージの表示][](message-trace-scc.md)をクリックすると、ルールの影響を受けたメッセージのサンプルのメッセージ トレース結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e8aa6-121">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="e8aa6-122">**各メッセージに費やされた平均時間**</span><span class="sxs-lookup"><span data-stu-id="e8aa6-122">**Average time spent on each message**</span></span>
- <span data-ttu-id="e8aa6-123">**メッセージに費やされた時間の** 中央値 : 上半分と下半分の時間データを分離する中央値。</span><span class="sxs-lookup"><span data-stu-id="e8aa6-123">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![[低速メール フロー ルールの修正] インサイトの [詳細の表示] をクリックした後に表示される詳細フライアウト](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="e8aa6-125">メール フロー ルールにおける条件と例外の詳細については、「[Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8aa6-125">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="e8aa6-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8aa6-126">See also</span></span>

<span data-ttu-id="e8aa6-127">メール フロー ダッシュボードの他の分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="e8aa6-127">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>