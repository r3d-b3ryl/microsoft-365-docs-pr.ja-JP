---
title: 時間のかかるメール フロー ルールの修正のインサイト
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターの低速メール フロー ルールのインサイトを使用して、組織の不効率な、または壊れていないメール フロー ルール (トランスポート ルールとも呼ばれる) を特定して修正する方法を学習できます。
ms.openlocfilehash: 6319633c47e34d7b62c4f68bfbda7fe298c0deb3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826883"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="c9de1-103">セキュリティ コンプライアンス センターの低速メール フローのルールのインサイト&を修正する</span><span class="sxs-lookup"><span data-stu-id="c9de1-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

<span data-ttu-id="c9de1-104">効率のないメール フロー ルール (トランスポート ルールとも呼ばれる) は、組織のメール フローの遅延につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c9de1-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="c9de1-105">この分析情報は、組織のメール フローに影響を与えるメール フロー ルールを報告します。</span><span class="sxs-lookup"><span data-stu-id="c9de1-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="c9de1-106">たとえば、次のような種類のルールがあります。</span><span class="sxs-lookup"><span data-stu-id="c9de1-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="c9de1-107">大規模なグループ **のメンバーとして使用** する条件。</span><span class="sxs-lookup"><span data-stu-id="c9de1-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="c9de1-108">複雑な正規表現 (regex) パターン マッチングを使用する条件。</span><span class="sxs-lookup"><span data-stu-id="c9de1-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="c9de1-109">添付ファイルでコンテンツ チェックを使用する条件。</span><span class="sxs-lookup"><span data-stu-id="c9de1-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="c9de1-110">セキュリティ &/コンプライアンス[Mail flow dashboard](mail-flow-insights-v2.md)**センターの [メール フロー]** ダッシュボードの [推奨**される**ユーザーに対しては、転送処理の低下に関するルール] の見出しの分析情報を参照してください。メール フロー ルールの処理が完了しきれい時間がかかりすぎています。</span><span class="sxs-lookup"><span data-stu-id="c9de1-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center notifies you when a mail flow rule is taking too long to complete.</span></span> <span data-ttu-id="c9de1-111">この分析情報は、条件が検出された後にのみ表示されます (メール ループがない場合、分析情報は表示されません)。</span><span class="sxs-lookup"><span data-stu-id="c9de1-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="c9de1-112">この通知を使うと、メール フローの遅延を減らすメール フロー ルールを識別して詳細に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="c9de1-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![メール フロー ダッシュボードの [推奨されるユーザーの詳細] 領域の低速メール フロー ルールの分析情報を修正する](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="c9de1-114">ウィジェ **ットの [** 詳細の表示] をクリックすると、さらに情報を含むポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9de1-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="c9de1-115">**ルール**: 概要に上にリンクすると、ルールのすべての条件、例外、アクションを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9de1-115">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="c9de1-116">概要をクリックすると、Exchange 管理センター (EAC) でルールを編集できます。</span><span class="sxs-lookup"><span data-stu-id="c9de1-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="c9de1-117">**評価されるメッセージ数**: [サンプル メッセージ **の表示** ] をクリックすると [、ルールの](message-trace-scc.md) 影響を受けったメッセージのサンプルのメッセージ トレース結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c9de1-117">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="c9de1-118">**各メッセージの平均時間**</span><span class="sxs-lookup"><span data-stu-id="c9de1-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="c9de1-119">**メッセージに使った中央**管理時間: 上半分と下半分のデータを区切る中央値。</span><span class="sxs-lookup"><span data-stu-id="c9de1-119">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![[フライト の低速メール フロー ルール] の見出しをクリックした後に表示される詳細ポップアップ](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="c9de1-121">Exchange Online 内のメール フロー ルールの条件と例外の詳細については、Exchange Online 内のメール フロー ルール [の条件と例外 (述語) を参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。</span><span class="sxs-lookup"><span data-stu-id="c9de1-121">For more information about conditions and exceptions in mail flow rules in Exchange Online, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c9de1-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c9de1-122">Related topics</span></span>

<span data-ttu-id="c9de1-123">メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="c9de1-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
