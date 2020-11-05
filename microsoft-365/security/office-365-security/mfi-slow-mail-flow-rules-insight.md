---
title: 時間のかかるメール フロー ルールの修正のインサイト
f1.keywords:
- NOCSH
ms.author: siosulli
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
description: 管理者は、セキュリティ & コンプライアンスセンターにある [低速なメールフロールールの詳細を修正する] を使用して、組織内の非効率的または壊れたメールフロールール (トランスポートルールとも呼ばれます) を特定して修正する方法を学習できます。
ms.openlocfilehash: f51c5a577fc6d9c52e35a5217cae4ae94c546c9d
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920550"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="2b53e-103">セキュリティ & コンプライアンスセンターでの低速メールフロールールの洞察を修正する</span><span class="sxs-lookup"><span data-stu-id="2b53e-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2b53e-104">非効率的なメールフロールール (トランスポートルールとも呼ばれます) は、組織のメールフロー遅延につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b53e-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="2b53e-105">この洞察は、組織のメールフローに影響を与えるメールフロールールを報告します。</span><span class="sxs-lookup"><span data-stu-id="2b53e-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="2b53e-106">これらの種類のルールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2b53e-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="2b53e-107">**が** 大規模なグループの場合、を使用する条件。</span><span class="sxs-lookup"><span data-stu-id="2b53e-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="2b53e-108">複合正規表現 (regex) パターンマッチングを使用する条件。</span><span class="sxs-lookup"><span data-stu-id="2b53e-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="2b53e-109">添付ファイルのコンテンツチェックを使用する条件。</span><span class="sxs-lookup"><span data-stu-id="2b53e-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="2b53e-110">「セキュリティの **低速メール** フロールール」では、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)のメール [フローダッシュボード](mail-flow-insights-v2.md)の **推奨事項につい** て理解しています。メールフロールールの完了に時間がかかりすぎた場合に通知します。</span><span class="sxs-lookup"><span data-stu-id="2b53e-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="2b53e-111">この洞察は、条件が検出された後にのみ表示されます (メールループがない場合は、洞察は見られません)。</span><span class="sxs-lookup"><span data-stu-id="2b53e-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="2b53e-112">メールフローの遅延を減らすために、この通知を使用して、メールフロールールを識別し、微調整することができます。</span><span class="sxs-lookup"><span data-stu-id="2b53e-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![メールフローダッシュボードのお住まいの地域で推奨されるメールフロールールの詳細を修正する](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="2b53e-114">ウィジェットの [ **詳細の表示** ] をクリックすると、詳細情報を含むフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b53e-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="2b53e-115">**ルール** : 概要にマウスカーソルを移動すると、ルールのすべての条件、例外、およびアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b53e-115">**Rule** : You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="2b53e-116">概要をクリックして、Exchange 管理センター (EAC) でルールを編集できます。</span><span class="sxs-lookup"><span data-stu-id="2b53e-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="2b53e-117">評価された **メッセージの数** : [ **サンプルメッセージの表示** ] をクリックすると、ルールの影響を受けたメッセージのサンプルのメッセージの [追跡](message-trace-scc.md)結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b53e-117">**Number of messages evaluated** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="2b53e-118">**各メッセージにかかった平均時間**</span><span class="sxs-lookup"><span data-stu-id="2b53e-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="2b53e-119">**メッセージにかかった平均** 時間: 時間データの下半分から上半分を区切る中央値。</span><span class="sxs-lookup"><span data-stu-id="2b53e-119">**Median time spent on a message** : The middle value that separates the upper half from the lower half of time data.</span></span>

![[Fix the details mail flow rules] の [詳細の表示] をクリックした後に表示される詳細ポップアップ](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="2b53e-121">メール フロー ルールにおける条件と例外の詳細については、「[Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b53e-121">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="2b53e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b53e-122">See also</span></span>

<span data-ttu-id="2b53e-123">メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b53e-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
