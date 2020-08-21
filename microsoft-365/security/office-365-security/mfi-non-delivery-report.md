---
title: メール フロー ダッシュボードの配信不能レポート
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで配信不能の詳細レポートを使用して、組織内の送信者からの配信不能レポート (NDR またはバウンス メッセージとも呼ばれる) で最も頻出されるエラー コードを監視する方法を学習できます。
ms.openlocfilehash: bdc2a2a16f76f4e6ada629c82b86423422ab56c9
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826919"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="5455d-103">セキュリティ コンプライアンス センターの配信 &不能レポート</span><span class="sxs-lookup"><span data-stu-id="5455d-103">Non-delivery report in the Security & Compliance Center</span></span>

<span data-ttu-id="5455d-104">セキュリティ &**コンプライアンス センターの**[メール フロー ダッシュボードの配信不能レポート](mail-flow-insights-v2.md)には、組織内のユーザーの配信不能レポート (NDR またはバウンス メッセージとも呼ばれる) で最も発生するエラー コードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5455d-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="5455d-105">このレポートには、メール配信の問題のトラブルシューティングを行うための NDR の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5455d-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![セキュリティ コンプライアンス センターのメール フロー ダッシュボードの配信不能レポート ウィ&ジェット](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="5455d-107">配信不能レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="5455d-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="5455d-108">配信不能 **レポート ウィジ** ェットをクリックすると、配信不能 **レポートが開きます**。</span><span class="sxs-lookup"><span data-stu-id="5455d-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="5455d-109">既定では、すべてのエラー コードのアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5455d-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="5455d-110">[データの **表示] をクリック**すると、ドロップダウンから特定のエラー コードを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5455d-110">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="5455d-111">グラフ内の特定の日付で特定の色 (エラー コード) の上に設定すると、エラーの合計メッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5455d-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

!["承認されていないドメイン" レポートのレポート ビュー](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="5455d-113">配信不能レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="5455d-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="5455d-114">レポート ビューで **詳細テーブルの表示** をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5455d-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="5455d-115">**Date**</span><span class="sxs-lookup"><span data-stu-id="5455d-115">**Date**</span></span>
- <span data-ttu-id="5455d-116">**配信不能レポート コード**</span><span class="sxs-lookup"><span data-stu-id="5455d-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="5455d-117">**Count**</span><span class="sxs-lookup"><span data-stu-id="5455d-117">**Count**</span></span>
- <span data-ttu-id="5455d-118">**サンプル メッセージ**: 影響を受けつメッセージのサンプルのメッセージ ID。</span><span class="sxs-lookup"><span data-stu-id="5455d-118">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="5455d-119">詳細テーブル ビュー**の [** フィルター] をクリックすると、開始日と終了日で**日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="5455d-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="5455d-120">特定の日付範囲のレポートを 1 名以上の受信者にメールで送信するには、[ **ダウンロードを要求] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5455d-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="5455d-121">表で行を選択すると、以下の情報を含むポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5455d-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="5455d-122">**Date**</span><span class="sxs-lookup"><span data-stu-id="5455d-122">**Date**</span></span>
- <span data-ttu-id="5455d-123">**配信不能レポートのコード**: リンクをクリックすると、特定のエラー コードの原因と解決策に関する詳細を見つけ出します。</span><span class="sxs-lookup"><span data-stu-id="5455d-123">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="5455d-124">**Count**</span><span class="sxs-lookup"><span data-stu-id="5455d-124">**Count**</span></span>
- <span data-ttu-id="5455d-125">**サンプル メッセージ**: [サンプル メッセージの **表示] をクリック** すると、影響 [を受けつ](message-trace-scc.md) つサンプル メッセージのメッセージトレース結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5455d-125">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![[Non-delivery report] レポートの [詳細] テーブル ビューで行を選択した後の詳細ポップアップ](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="5455d-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5455d-127">Related topics</span></span>

<span data-ttu-id="5455d-128">メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="5455d-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
