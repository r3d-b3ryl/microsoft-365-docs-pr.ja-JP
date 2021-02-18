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
ms.openlocfilehash: 7fde0041dfb9901cb0a327eafec78d98a40b4cb9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290563"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="b1467-103">セキュリティ/コンプライアンス センターで考えられるメール ループ&修正</span><span class="sxs-lookup"><span data-stu-id="b1467-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b1467-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="b1467-104">**Applies to**</span></span>
- [<span data-ttu-id="b1467-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b1467-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b1467-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="b1467-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b1467-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1467-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="b1467-108">メール ループは、次の理由から悪い場合があります。</span><span class="sxs-lookup"><span data-stu-id="b1467-108">Mail loops are bad because:</span></span>

- <span data-ttu-id="b1467-109">システム リソースを無駄に使います。</span><span class="sxs-lookup"><span data-stu-id="b1467-109">They waste system resources.</span></span>
- <span data-ttu-id="b1467-110">組織のメール ボリューム クォータが消費されます。</span><span class="sxs-lookup"><span data-stu-id="b1467-110">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="b1467-111">元のメッセージ送信者に、混乱を招く配信不可レポート (NDRs またはバウンス メッセージとも呼ばれる) を送信します。</span><span class="sxs-lookup"><span data-stu-id="b1467-111">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="b1467-112">セキュリティ **&** コンプライアンス センターのメール フロー ダッシュボードの [推奨されるユーザー [](https://protection.office.com) ] 領域にあるメール ループの修正に関する分析情報は、組織内でメール ループが検出されると通知します。  [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="b1467-112">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="b1467-113">この分析情報は、条件が検出された後にのみ表示されます (メール ループを使用しない場合、分析情報は表示されません)。</span><span class="sxs-lookup"><span data-stu-id="b1467-113">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![メール フロー ダッシュボードの [おすすめ] 領域で低速のメール フロー ルールの分析情報を修正する](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="b1467-115">ウィジェットの [ **詳細の表示]** をクリックすると、詳細情報を含むフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1467-115">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="b1467-116">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="b1467-116">**Domain**</span></span>
- <span data-ttu-id="b1467-117">**メッセージ数**: [サンプルメッセージの表示][](message-trace-scc.md)をクリックすると、ループの影響を受けたメッセージのサンプルのメッセージ追跡結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b1467-117">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="b1467-118">**ドメインの種類**" たとえば、権限がある、または権限が不必要です。</span><span class="sxs-lookup"><span data-stu-id="b1467-118">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="b1467-119">**MX レコード**:**ドメインの** MXレコードのホスト ( メール サーバー) と優先度の値。</span><span class="sxs-lookup"><span data-stu-id="b1467-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="b1467-120">**ループの** 理由と **修正方法**: 最も一般的なメール ループ シナリオを特定し、ループを修正するための推奨アクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="b1467-120">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![[可能なメール ループの分析情報を修正する] の [詳細の表示] をクリックした後に表示される詳細フライアウト](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="b1467-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1467-122">See also</span></span>

<span data-ttu-id="b1467-123">メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="b1467-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
