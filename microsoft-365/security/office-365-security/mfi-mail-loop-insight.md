---
title: メール ループの可能性の修正のインサイト
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードにある考えられるメールループの洞察を使用して、組織内のメールループを特定して修正する方法について説明します。
ms.openlocfilehash: 1d49fd93b2ea068986e003b36077672215a2dd57
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920569"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="aebc9-103">セキュリティ & コンプライアンスセンターで使用可能なメールループの洞察を修正する</span><span class="sxs-lookup"><span data-stu-id="aebc9-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="aebc9-104">次の理由により、メールループが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="aebc9-104">Mail loops are bad because:</span></span>

- <span data-ttu-id="aebc9-105">システムリソースが浪費されます。</span><span class="sxs-lookup"><span data-stu-id="aebc9-105">They waste system resources.</span></span>
- <span data-ttu-id="aebc9-106">組織のメールボリュームクォータを消費します。</span><span class="sxs-lookup"><span data-stu-id="aebc9-106">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="aebc9-107">送信者は、元のメッセージの送信者に、わかりづらい配信不能レポート (Ndr またはバウンスメッセージとも呼ばれます) を送信します。</span><span class="sxs-lookup"><span data-stu-id="aebc9-107">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="aebc9-108">[セキュリティ & コンプライアンスセンター](https://protection.office.com)の [メールフローダッシュボード](mail-flow-insights-v2.md)の [お客様 **に推奨** されるメールループ] 領域で、組織内でメールループが検出されたときに通知する **メールループを修正** します。</span><span class="sxs-lookup"><span data-stu-id="aebc9-108">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="aebc9-109">この洞察は、条件が検出された後にのみ表示されます (メールループがない場合は、洞察は見られません)。</span><span class="sxs-lookup"><span data-stu-id="aebc9-109">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![メールフローダッシュボードのお住まいの地域で推奨されるメールフロールールの詳細を修正する](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="aebc9-111">ウィジェットの [ **詳細の表示** ] をクリックすると、詳細情報を含むフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="aebc9-111">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="aebc9-112">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="aebc9-112">**Domain**</span></span>
- <span data-ttu-id="aebc9-113">**メッセージ数** : [ **サンプルメッセージの表示** ] をクリックすると、ループの影響を受けたメッセージのサンプルの [追跡](message-trace-scc.md) 結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aebc9-113">**Number of messages** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="aebc9-114">**ドメインの種類** 。たとえば、権限のある、または権限がない。</span><span class="sxs-lookup"><span data-stu-id="aebc9-114">**Domain type** " For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="aebc9-115">**Mx レコード** : ドメインの mx レコードのホスト ( **メールサーバー** ) と **優先度** の値。</span><span class="sxs-lookup"><span data-stu-id="aebc9-115">**MX record** : The host ( **Mail server** ) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="aebc9-116">**ループの理由** と **解決方法** : 最も一般的なメールループシナリオを特定し、そのループを解決するために推奨されるアクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="aebc9-116">**Loop reason** and **How to fix** : We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![考えられるメールループの状況を修正する [詳細の表示] をクリックした後に表示される詳細ポップアップ](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="aebc9-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="aebc9-118">See also</span></span>

<span data-ttu-id="aebc9-119">メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aebc9-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
