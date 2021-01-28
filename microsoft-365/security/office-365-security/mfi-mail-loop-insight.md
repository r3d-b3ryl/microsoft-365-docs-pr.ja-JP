---
title: メール ループの可能性の修正のインサイト
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで、メール ループの可能性がある修正の分析情報を使用して、組織内のメール ループを特定して修正する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f08c27c761cdfe4acbbd8cf80e8ab6da8012b55f
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029896"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="d3beb-103">セキュリティ/コンプライアンス センターで考えられるメール ループ&修正</span><span class="sxs-lookup"><span data-stu-id="d3beb-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d3beb-104">メール ループは、次の理由から悪い場合があります。</span><span class="sxs-lookup"><span data-stu-id="d3beb-104">Mail loops are bad because:</span></span>

- <span data-ttu-id="d3beb-105">システム リソースを無駄に使います。</span><span class="sxs-lookup"><span data-stu-id="d3beb-105">They waste system resources.</span></span>
- <span data-ttu-id="d3beb-106">組織のメール ボリューム クォータが消費されます。</span><span class="sxs-lookup"><span data-stu-id="d3beb-106">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="d3beb-107">元のメッセージ送信者に、混乱を招く配信不可レポート (NDRs またはバウンス メッセージとも呼ばれる) を送信します。</span><span class="sxs-lookup"><span data-stu-id="d3beb-107">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="d3beb-108">セキュリティ **&** コンプライアンス センターのメール フロー ダッシュボードの [推奨されるユーザー [](https://protection.office.com) ] 領域にあるメール ループの修正に関する分析情報は、組織内でメール ループが検出されると通知します。  [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="d3beb-108">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="d3beb-109">この分析情報は、条件が検出された後にのみ表示されます (メール ループを使用しない場合、分析情報は表示されません)。</span><span class="sxs-lookup"><span data-stu-id="d3beb-109">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![メール フロー ダッシュボードの [おすすめ] 領域で低速のメール フロー ルールの分析情報を修正する](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="d3beb-111">ウィジェットの [ **詳細の表示]** をクリックすると、詳細情報を含むフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3beb-111">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="d3beb-112">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="d3beb-112">**Domain**</span></span>
- <span data-ttu-id="d3beb-113">**メッセージ数**: [サンプルメッセージの表示][](message-trace-scc.md)をクリックすると、ループの影響を受けたメッセージのサンプルのメッセージ追跡結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d3beb-113">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="d3beb-114">**ドメインの種類**" たとえば、権限がある、または権限が不必要です。</span><span class="sxs-lookup"><span data-stu-id="d3beb-114">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="d3beb-115">**MX レコード**:**ドメインの** MXレコードのホスト ( メール サーバー) と優先度の値。</span><span class="sxs-lookup"><span data-stu-id="d3beb-115">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="d3beb-116">**ループの** 理由と **修正方法**: 最も一般的なメール ループ シナリオを特定し、ループを修正するための推奨アクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="d3beb-116">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![[可能なメール ループの分析情報を修正する] の [詳細の表示] をクリックした後に表示される詳細フライアウト](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="d3beb-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3beb-118">See also</span></span>

<span data-ttu-id="d3beb-119">メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="d3beb-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
