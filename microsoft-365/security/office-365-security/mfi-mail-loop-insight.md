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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで[メール ループの修正] インサイトを使用して、組織内のメール ループを特定して修正する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206345"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="ca1df-103">セキュリティ コンプライアンス センターで考えられるメール ループ&修正する</span><span class="sxs-lookup"><span data-stu-id="ca1df-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ca1df-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="ca1df-104">**Applies to**</span></span>
- [<span data-ttu-id="ca1df-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ca1df-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ca1df-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="ca1df-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ca1df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca1df-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ca1df-108">メール ループが悪いのは、次の理由からです。</span><span class="sxs-lookup"><span data-stu-id="ca1df-108">Mail loops are bad because:</span></span>

- <span data-ttu-id="ca1df-109">システム リソースを無駄にしています。</span><span class="sxs-lookup"><span data-stu-id="ca1df-109">They waste system resources.</span></span>
- <span data-ttu-id="ca1df-110">組織のメール ボリューム クォータを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca1df-110">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="ca1df-111">元のメッセージ送信者に、わかりにくい配信以外のレポート (NDRs またはバウンス メッセージとも呼ばれる) を送信します。</span><span class="sxs-lookup"><span data-stu-id="ca1df-111">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="ca1df-112">セキュリティ **&** コンプライアンス センターのメール フロー ダッシュボードの [推奨されるユーザー [](https://protection.office.com) ] 領域の [メール ループの修正] 領域で、組織内でメール ループが検出されると通知されます。  [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="ca1df-112">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="ca1df-113">この分析情報は、条件が検出された後にのみ表示されます (メール ループが発生しない場合は、分析情報は表示されません)。</span><span class="sxs-lookup"><span data-stu-id="ca1df-113">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![メール フロー ダッシュボードの [おすすめ] 領域でメール フロー ルールの低速分析情報を修正する](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="ca1df-115">ウィジェットの [ **詳細の表示]** をクリックすると、詳細情報が表示されるフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca1df-115">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="ca1df-116">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="ca1df-116">**Domain**</span></span>
- <span data-ttu-id="ca1df-117">**メッセージ数**: [サンプル メッセージの表示][](message-trace-scc.md)を **クリックすると、** ループの影響を受けたメッセージのサンプルのメッセージ トレース結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ca1df-117">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="ca1df-118">**ドメインの種類**" たとえば、権限を持つもの、権限が無い場合などです。</span><span class="sxs-lookup"><span data-stu-id="ca1df-118">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="ca1df-119">**MX レコード**:**ドメインの** MXレコードのホスト (メール サーバー) と優先度の値。</span><span class="sxs-lookup"><span data-stu-id="ca1df-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="ca1df-120">**ループの理由\*\*\*\*と修正方法**: 最も一般的なメール ループシナリオを特定し、ループを修正するための推奨アクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="ca1df-120">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![[可能なメール ループの分析情報を修正する] の [詳細を表示する] をクリックした後に表示される詳細フライアウト](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="ca1df-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca1df-122">See also</span></span>

<span data-ttu-id="ca1df-123">メール フロー ダッシュボードの他の分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="ca1df-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
