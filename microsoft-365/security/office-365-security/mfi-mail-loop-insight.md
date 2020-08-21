---
title: メール ループの可能性の修正のインサイト
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ &/コンプライアンス センターのメール フロー ダッシュボードでメール ループの可能性に関する分析情報を使用して、組織のメール ループを特定し、修正する方法を学習できます。
ms.openlocfilehash: 162752ce6981e27d6ae2923aeb0fc33aec42bb0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826955"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="bff80-103">セキュリティ コンプライアンス センターのメール ループの可能性を&する</span><span class="sxs-lookup"><span data-stu-id="bff80-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

<span data-ttu-id="bff80-104">メール ループは、システム リソースを消費し、組織のメール量クォータを消費し、配信不能レポート (NDR またはバウンス メッセージとも呼ばれる) を元の送信者に送信しているため、不正です。</span><span class="sxs-lookup"><span data-stu-id="bff80-104">A mail loop is bad because it wastes system resources, consumes your organization's mail volume quota, and sends confusing non-delivery reports (also known as NDRs or bounce messages) to the original senders.</span></span>

<span data-ttu-id="bff80-105">セキュリティ **& コンプライアンス センターの**メール フロー ダッシュボードの **[推奨**されるメール[Mail flow dashboard](mail-flow-insights-v2.md)フロー] 領域でメール ループの可能性の分析情報により、組織内でメール ループが検出された場合に、そのユーザーにおすすめが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bff80-105">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center notifies you when a mail loop is detected in your organization.</span></span> <span data-ttu-id="bff80-106">この分析情報は、条件が検出された後にのみ表示されます (メール ループがない場合、分析情報は表示されません)。</span><span class="sxs-lookup"><span data-stu-id="bff80-106">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![メール フロー ダッシュボードの [推奨されるユーザーの詳細] 領域の低速メール フロー ルールの分析情報を修正する](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="bff80-108">ウィジェ **ットの [** 詳細の表示] をクリックすると、さらに情報を含むポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bff80-108">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="bff80-109">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="bff80-109">**Domain**</span></span>
- <span data-ttu-id="bff80-110">**[メッセージ数]:**[ **サンプル メッセージの表示] をクリック** すると、 [ループの](message-trace-scc.md) 影響を受けていたメッセージのサンプルに関するメッセージ トレース結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="bff80-110">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="bff80-111">**ドメインの**種類は、「権限のあるアイテム」または「権限のない」です。</span><span class="sxs-lookup"><span data-stu-id="bff80-111">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="bff80-112">**MX レコード**: ドメインの MX**レコード**のホスト ( メール サーバー) と **Priority** の値。</span><span class="sxs-lookup"><span data-stu-id="bff80-112">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="bff80-113">**ループの** 理由 **と解決方法**: 最も一般的なメール ループのシナリオを特定し、ループを修正するための推奨アクション (ある場合) を提供します。</span><span class="sxs-lookup"><span data-stu-id="bff80-113">**Loop reason** and **How to fix**: We'll try to identify the most common mail loop scenarios and provide the recommended actions (if available) to fix the loop.</span></span>

![[修正] の [修正] の [詳細を表示] をクリックした後に表示される詳細ポップアップ](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a><span data-ttu-id="bff80-115">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bff80-115">Related topics</span></span>

<span data-ttu-id="bff80-116">メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="bff80-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
