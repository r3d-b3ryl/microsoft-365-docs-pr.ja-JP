---
title: メールフローダッシュボードの配信不能レポート
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードにある配信不能レポート (Ndr またはバウンスメッセージとも呼ばれる) で、組織内の送信者に対して発生する可能性の高いエラーコードを監視する方法について説明します。
ms.openlocfilehash: 4967b3b5c294566e46bbc715dd6702c23d618105
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877683"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="3817b-103">セキュリティ & コンプライアンスセンターの配信不能レポート</span><span class="sxs-lookup"><span data-stu-id="3817b-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3817b-104">[セキュリティ & コンプライアンスセンター](https://protection.office.com)の [メールフローダッシュボード](mail-flow-insights-v2.md)の **配信不能レポート** は、組織内のユーザーの配信不能レポート (ndr またはバウンスメッセージとも呼ばれる) で最も発生したエラーコードを示しています。</span><span class="sxs-lookup"><span data-stu-id="3817b-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="3817b-105">このレポートには、メール配信の問題のトラブルシューティングに使用できる Ndr の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3817b-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードの配信不能レポートウィジェット](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="3817b-107">配信不能レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="3817b-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="3817b-108">**配信不能レポート** ウィジェットをクリックすると、 **配信不能レポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="3817b-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="3817b-109">既定では、すべてのエラーコードのアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3817b-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="3817b-110">[ **データの表示** ] をクリックすると、ドロップダウンから特定のエラーコードを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3817b-110">If you click **Show data for** , you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="3817b-111">グラフの特定の日の特定の色 (エラーコード) の上にカーソルを置くと、エラーが発生したメッセージの合計数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3817b-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![承認されていないドメインレポートのレポートビュー](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="3817b-113">配信不能レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="3817b-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="3817b-114">レポートビューで [ **詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3817b-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="3817b-115">**Date**</span><span class="sxs-lookup"><span data-stu-id="3817b-115">**Date**</span></span>
- <span data-ttu-id="3817b-116">**配信不能レポートのコード**</span><span class="sxs-lookup"><span data-stu-id="3817b-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="3817b-117">**Count**</span><span class="sxs-lookup"><span data-stu-id="3817b-117">**Count**</span></span>
- <span data-ttu-id="3817b-118">**サンプルメッセージ** : 影響を受けるメッセージのサンプルのメッセージ id。</span><span class="sxs-lookup"><span data-stu-id="3817b-118">**Sample messages** : The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="3817b-119">詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日** を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3817b-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="3817b-120">特定の日付範囲のレポートに対して1人以上の受信者を電子メールで送信するには、[ **ダウンロードの依頼** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3817b-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="3817b-121">表の行を選択すると、次の情報を含むフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3817b-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="3817b-122">**Date**</span><span class="sxs-lookup"><span data-stu-id="3817b-122">**Date**</span></span>
- <span data-ttu-id="3817b-123">**配信不能レポートコード** : 特定のエラーコードの原因と解決方法の詳細については、リンクをクリックして確認できます。</span><span class="sxs-lookup"><span data-stu-id="3817b-123">**Non-delivery report code** : You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="3817b-124">**Count**</span><span class="sxs-lookup"><span data-stu-id="3817b-124">**Count**</span></span>
- <span data-ttu-id="3817b-125">**サンプルメッセージ** : [ **サンプルメッセージの表示** ] をクリックすると、影響を受けたメッセージのサンプルの [メッセージの追跡](message-trace-scc.md) 結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3817b-125">**Sample messages** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![配信不能レポートの [詳細] テーブルビューで行を選択した後の詳細ポップアップ](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="3817b-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="3817b-127">Related topics</span></span>

<span data-ttu-id="3817b-128">メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3817b-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
