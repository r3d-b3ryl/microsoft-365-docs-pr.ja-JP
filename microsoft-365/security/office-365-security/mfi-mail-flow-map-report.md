---
title: メール フローのマップ レポート
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローのダッシュボードにあるメールフローマップレポートの詳細を確認できます。
ms.openlocfilehash: b0850ee50573583f1a971d1a5dfd69f47fb70b99
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818845"
---
# <a name="mail-flow-map-report"></a><span data-ttu-id="95b21-103">メール フローのマップ レポート</span><span class="sxs-lookup"><span data-stu-id="95b21-103">Mail flow map report</span></span>

<span data-ttu-id="95b21-104">このレポートでは、組織を通過するメールの流れについての情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="95b21-104">This report gives insights as to how mail flows through your organization.</span></span> <span data-ttu-id="95b21-105">この情報を使用して、パターンを学習し、異常を特定し、発生した問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="95b21-105">You can use this information to learn patterns, identify anomalies, and fix issues as they arise.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードのメールフローマップレポート](../../media/mail-flow-map-selected.png)

## <a name="mail-flow-map-widget"></a><span data-ttu-id="95b21-107">メールフローマップウィジェット</span><span class="sxs-lookup"><span data-stu-id="95b21-107">Mail flow map widget</span></span>

<span data-ttu-id="95b21-108">既定では、メールフローマップは、前日からの高レベルのメールフローパターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="95b21-108">By default, the mail flow map shows the high level mail flow pattern from the previous day.</span></span> <span data-ttu-id="95b21-109">さまざまな日の左矢印と右矢印を使用できます。</span><span class="sxs-lookup"><span data-stu-id="95b21-109">You can use the left and right arrows for different days.</span></span> <span data-ttu-id="95b21-110">レポートの各領域の上にマウスカーソルを移動すると、次の図に示すように、組織との間のメールの量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="95b21-110">Hovering your mouse cursor over each area in the report will show the volume of mail to and from your organization as shown in the following diagram:</span></span>

![メールフローマップウィジェットの左および右の矢印](../../media/mail-flow-map-widget.png)

## <a name="mail-flow-map-basics"></a><span data-ttu-id="95b21-112">メールフローマップの基礎</span><span class="sxs-lookup"><span data-stu-id="95b21-112">Mail flow map basics</span></span>

<span data-ttu-id="95b21-113">**メールフローマップ**ウィジェットをクリックすると、**メールフローマップ**レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95b21-113">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span> <span data-ttu-id="95b21-114">詳細なレポートを表示するには、[詳細データの表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95b21-114">Here you can see more granular level of report, you can click View details table to see detailed data.</span></span> <span data-ttu-id="95b21-115">[要求レポート] をクリックして詳細レポートをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="95b21-115">You can also download the detailed report by clicking Request report.</span></span>

![メールフローマップレポートの概要ビュー](../../media/mail-flow-map-overview.png)

## <a name="details"></a><span data-ttu-id="95b21-117">詳細</span><span class="sxs-lookup"><span data-stu-id="95b21-117">Details</span></span>

<span data-ttu-id="95b21-118">既定では、[**データの表示]** は値の**概要**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="95b21-118">By default, **Show data for** is set to the value **Overview**.</span></span> <span data-ttu-id="95b21-119">ドロップダウンをクリックして [ **detail**] を選択すると、ビューはドメインレベルの詳細に切り替わります。</span><span class="sxs-lookup"><span data-stu-id="95b21-119">When you click on the drop down and select **Detail**, the view switches to the domain level detail.</span></span>

![メールフローマップレポートの概要表示での [データの表示] での詳細の選択](../../media/mail-flow-map-select-detail.png)

<span data-ttu-id="95b21-121">次の図に示すように、上位の送信者と受信者のドメインが表示され、残りは**他のユーザー**に配置されます。</span><span class="sxs-lookup"><span data-stu-id="95b21-121">The top sender and recipient domains are listed, and the rest will be put in **Others** as shown in the following diagrams:</span></span>

![メールフローマップレポートの詳細表示](../../media/mail-flow-map-detail.png)

## <a name="related-insights"></a><span data-ttu-id="95b21-123">関連する分析情報</span><span class="sxs-lookup"><span data-stu-id="95b21-123">Related insights</span></span>

<span data-ttu-id="95b21-124">関連する洞察は、使用可能な場合はメールフローマップの下に表示されます (たとえば、送信者のドメインの洞察やメールループの洞察など)。</span><span class="sxs-lookup"><span data-stu-id="95b21-124">Related insights are shown beneath the Mail flow map if they're available (for example, the Sender domain insight or the Mail loop insight).</span></span>

## <a name="see-also"></a><span data-ttu-id="95b21-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="95b21-125">See also</span></span>

<span data-ttu-id="95b21-126">メールフローダッシュボードのその他のメールフローインサイトの詳細については、「[セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95b21-126">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
