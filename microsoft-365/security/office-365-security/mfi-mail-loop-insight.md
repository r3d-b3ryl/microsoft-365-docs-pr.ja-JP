---
title: 考えられるメールループの洞察を修正する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードにある考えられるメールループの洞察を使用して、組織内のメールループを特定して修正する方法について説明します。
ms.openlocfilehash: 54240cffc534b4be708492b37b827636edab280e
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577629"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="658f0-103">セキュリティ & コンプライアンスセンターで使用可能なメールループの洞察を修正する</span><span class="sxs-lookup"><span data-stu-id="658f0-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

<span data-ttu-id="658f0-104">メールループは、システムリソースが浪費され、組織のメールボリュームクォータを使用して、元の送信者に (Ndr またはバウンスメッセージとも呼ばれる) 混乱しない配信不能レポートを送信するため、不正です。</span><span class="sxs-lookup"><span data-stu-id="658f0-104">A mail loop is bad because it wastes system resources, consumes your organization's mail volume quota, and sends confusing non-delivery reports (also known as NDRs or bounce messages) to the original senders.</span></span>

<span data-ttu-id="658f0-105">セキュリティ & コンプライアンスセンターの[メールフローダッシュボード](mail-flow-insights-v2.md)の [お客様**に推奨**されるメールループ] 領域で、組織内でメールループが検出されたときに通知する**メールループを修正**します。</span><span class="sxs-lookup"><span data-stu-id="658f0-105">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center notifies you when a mail loop is detected in your organization.</span></span> <span data-ttu-id="658f0-106">この洞察は、条件が検出された後にのみ表示されます (メールループがない場合は、洞察は見られません)。</span><span class="sxs-lookup"><span data-stu-id="658f0-106">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![メールフローダッシュボードのお住まいの地域で推奨されるメールフロールールの詳細を修正する](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="658f0-108">ウィジェットの [**詳細の表示**] をクリックすると、詳細情報を含むフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="658f0-108">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="658f0-109">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="658f0-109">**Domain**</span></span>
- <span data-ttu-id="658f0-110">**メッセージ数**: [**サンプルメッセージの表示**] をクリックすると、ループの影響を受けたメッセージのサンプルの[追跡](message-trace-scc.md)結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="658f0-110">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="658f0-111">**ドメインの種類**。たとえば、権限のある、または権限がない。</span><span class="sxs-lookup"><span data-stu-id="658f0-111">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="658f0-112">**Mx レコード**: ドメインの mx レコードのホスト (**メールサーバー**) と**優先度**の値。</span><span class="sxs-lookup"><span data-stu-id="658f0-112">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="658f0-113">**ループの理由**と**解決方法**: 最も一般的なメールループシナリオを特定し、そのループを解決するために推奨されるアクション (使用可能な場合) を指定します。</span><span class="sxs-lookup"><span data-stu-id="658f0-113">**Loop reason** and **How to fix**: We'll try to identify the most common mail loop scenarios and provide the recommended actions (if available) to fix the loop.</span></span>

![考えられるメールループの状況を修正する [詳細の表示] をクリックした後に表示される詳細ポップアップ](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a><span data-ttu-id="658f0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="658f0-115">Related topics</span></span>

<span data-ttu-id="658f0-116">メールフローダッシュボードの他の洞察の詳細については、「[セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="658f0-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
