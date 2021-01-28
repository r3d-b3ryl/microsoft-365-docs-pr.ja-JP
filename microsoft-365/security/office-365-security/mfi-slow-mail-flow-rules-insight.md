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
description: 管理者は、セキュリティ & コンプライアンス センターで低速メール フロー ルールの修正の分析情報を使用して、組織の非効率的または破損したメール フロー ルール (トランスポート ルールとも呼ばれる) を特定して修正する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ef9f26994f563a5f9dad411f2276fd42c28496f9
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029128"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="97625-103">セキュリティ/コンプライアンス センターで低速のメール フロー ルールの&を修正する</span><span class="sxs-lookup"><span data-stu-id="97625-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="97625-104">非効率的なメール フロー ルール (トランスポート ルールとも呼ばれる) は、組織のメール フローの遅延につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97625-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="97625-105">このインサイトは、組織のメール フローに影響を与えるメール フロー ルールを報告します。</span><span class="sxs-lookup"><span data-stu-id="97625-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="97625-106">これらの種類のルールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="97625-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="97625-107">大規模なグループ **の Is メンバーを** 使用する条件。</span><span class="sxs-lookup"><span data-stu-id="97625-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="97625-108">複雑な正規表現 (regex) パターンマッチングを使用する条件。</span><span class="sxs-lookup"><span data-stu-id="97625-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="97625-109">添付ファイルのコンテンツ チェックを使用する条件。</span><span class="sxs-lookup"><span data-stu-id="97625-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="97625-110">セキュリティ & コンプライアンス センターのメールフロー ダッシュボードの [推奨されるユーザー][](https://protection.office.com)領域にある [低速メール フロー ルールの修正] の分析情報は、メール フロー ルールの完了に時間がかかっている場合に通知します。 [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="97625-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="97625-111">この分析情報は、条件が検出された後にのみ表示されます (メール ループを使用しない場合、分析情報は表示されません)。</span><span class="sxs-lookup"><span data-stu-id="97625-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="97625-112">この通知を使用すると、メール フロー ルールを特定して微調整し、メール フローの遅延を減らすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="97625-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![メール フロー ダッシュボードの [おすすめ] 領域で低速のメール フロー ルールの分析情報を修正する](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="97625-114">ウィジェットの [ **詳細の表示]** をクリックすると、詳細情報を含むフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97625-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="97625-115">**ルール**: 概要をポイントすると、ルールのすべての条件、例外、およびアクションを表示できます。</span><span class="sxs-lookup"><span data-stu-id="97625-115">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="97625-116">概要をクリックすると、Exchange 管理センター (EAC) でルールを編集できます。</span><span class="sxs-lookup"><span data-stu-id="97625-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="97625-117">**評価されるメッセージ** の数 : [サンプル メッセージの表示][](message-trace-scc.md)をクリックすると、ルールの影響を受けたメッセージのサンプルのメッセージ追跡結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="97625-117">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="97625-118">**各メッセージに費やされた平均時間**</span><span class="sxs-lookup"><span data-stu-id="97625-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="97625-119">**メッセージに費やした時間の中央** 値: 上半分と下位半分の時間データを分け合う中間値。</span><span class="sxs-lookup"><span data-stu-id="97625-119">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![[低速メール フロー ルールの修正] インサイトの [詳細の表示] をクリックした後に表示される詳細フライアウト](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="97625-121">メール フロー ルールにおける条件と例外の詳細については、「[Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97625-121">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="97625-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="97625-122">See also</span></span>

<span data-ttu-id="97625-123">メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="97625-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
