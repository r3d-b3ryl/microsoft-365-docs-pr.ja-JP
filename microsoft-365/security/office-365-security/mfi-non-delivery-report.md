---
title: メール フロー ダッシュボードの配信不可レポート
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで配信の詳細レポートを使用して、組織内の送信者からの配信前レポート (NDRs またはバウンス メッセージとも呼ばれる) で最も頻繁に発生するエラー コードを監視する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dbd27fc818a46a983874a04f0e313c622e047ea5
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029836"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="5e234-103">セキュリティ/コンプライアンス センターの配信&レポート</span><span class="sxs-lookup"><span data-stu-id="5e234-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5e234-104">[セキュリティ](https://protection.office.com)& コンプライアンス センター[](mail-flow-insights-v2.md)のメール フロー ダッシュボードの配信不可レポートには、組織内のユーザーの配信レポート (NDRs またはバウンス メッセージとも呼ばれる) で最も発生したエラー コードが表示されます。 </span><span class="sxs-lookup"><span data-stu-id="5e234-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="5e234-105">このレポートには、メール配信の問題をトラブルシューティングするための、NDRs の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e234-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボードの配信&ウィジェット](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="5e234-107">配信前レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="5e234-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="5e234-108">配信レポートウィジェット **をクリック** すると、配信先以外の **レポートにアクセスできます**。</span><span class="sxs-lookup"><span data-stu-id="5e234-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="5e234-109">既定では、すべてのエラー コードのアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e234-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="5e234-110">[データの **表示] をクリック** すると、ドロップダウンから特定のエラー コードを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5e234-110">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="5e234-111">グラフの特定の日に特定の色 (エラー コード) をポイントすると、エラーのメッセージの総数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e234-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![[非承諾ドメイン] レポートのレポート ビュー](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="5e234-113">配信不可レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="5e234-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="5e234-114">レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e234-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="5e234-115">**日付**</span><span class="sxs-lookup"><span data-stu-id="5e234-115">**Date**</span></span>
- <span data-ttu-id="5e234-116">**配信不可レポート コード**</span><span class="sxs-lookup"><span data-stu-id="5e234-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="5e234-117">**Count**</span><span class="sxs-lookup"><span data-stu-id="5e234-117">**Count**</span></span>
- <span data-ttu-id="5e234-118">**サンプル メッセージ**: 影響を受けるメッセージのサンプルのメッセージ ID。</span><span class="sxs-lookup"><span data-stu-id="5e234-118">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="5e234-119">詳細テーブル ビューで **[フィルター** ] をクリックすると、開始日と終了日で日付 **範囲** を **指定できます**。</span><span class="sxs-lookup"><span data-stu-id="5e234-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="5e234-120">特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5e234-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="5e234-121">テーブル内の行を選択すると、次の情報を含むフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e234-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="5e234-122">**日付**</span><span class="sxs-lookup"><span data-stu-id="5e234-122">**Date**</span></span>
- <span data-ttu-id="5e234-123">**配信レポートのコード**: リンクをクリックすると、特定のエラー コードの原因と解決策の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5e234-123">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="5e234-124">**Count**</span><span class="sxs-lookup"><span data-stu-id="5e234-124">**Count**</span></span>
- <span data-ttu-id="5e234-125">**サンプル メッセージ**: [サンプル メッセージの表示 [](message-trace-scc.md)]**を** クリックすると、影響を受けるメッセージのサンプルのメッセージ追跡結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5e234-125">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![配信不可レポートの [詳細] テーブル ビューで行を選択した後の詳細フライアウト](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="5e234-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e234-127">Related topics</span></span>

<span data-ttu-id="5e234-128">メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="5e234-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
