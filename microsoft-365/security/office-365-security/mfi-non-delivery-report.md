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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで配信不可の詳細レポートを使用して、組織内の送信者からの配信不可レポート (NDRs またはバウンス メッセージとも呼ばれる) で最も頻繁に発生するエラー コードを監視する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01d25f11051606139c2ee8b88cade18963de599d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206320"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="96611-103">セキュリティ コンプライアンス センターの配信&レポート</span><span class="sxs-lookup"><span data-stu-id="96611-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="96611-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="96611-104">**Applies to**</span></span>
- [<span data-ttu-id="96611-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="96611-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="96611-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="96611-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="96611-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96611-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="96611-108">セキュリティ [&](https://protection.office.com)コンプライアンス センター[](mail-flow-insights-v2.md)のメール フロー ダッシュボードの配信不可レポートには、組織内のユーザーの配信不可レポート (NDRs またはバウンス メッセージとも呼ばれる) で最も発生したエラー コードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="96611-108">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="96611-109">このレポートには、メール配信の問題をトラブルシューティングするための、NDRs の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="96611-109">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![セキュリティ センターコンプライアンス センターのメール フロー ダッシュボードの配信&ウィジェット](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="96611-111">配信不可レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="96611-111">Report view for the Non-delivery report</span></span>

<span data-ttu-id="96611-112">[配信不可レポート **] ウィジェットをクリック** すると、[配信不可] **レポートにアクセスします**。</span><span class="sxs-lookup"><span data-stu-id="96611-112">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="96611-113">既定では、すべてのエラー コードのアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="96611-113">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="96611-114">[データの表示 **] をクリックすると**、ドロップダウンから特定のエラー コードを選択できます。</span><span class="sxs-lookup"><span data-stu-id="96611-114">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="96611-115">グラフ内の特定の日に特定の色 (エラー コード) にカーソルを合わせると、エラーのメッセージの総数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="96611-115">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![非承諾ドメイン レポートのレポート ビュー](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="96611-117">配信不可レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="96611-117">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="96611-118">レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="96611-118">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="96611-119">**日付**</span><span class="sxs-lookup"><span data-stu-id="96611-119">**Date**</span></span>
- <span data-ttu-id="96611-120">**配信不可レポート コード**</span><span class="sxs-lookup"><span data-stu-id="96611-120">**Non-delivery report code**</span></span>
- <span data-ttu-id="96611-121">**Count**</span><span class="sxs-lookup"><span data-stu-id="96611-121">**Count**</span></span>
- <span data-ttu-id="96611-122">**サンプル メッセージ**: 影響を受けるメッセージのサンプルのメッセージの ID です。</span><span class="sxs-lookup"><span data-stu-id="96611-122">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="96611-123">詳細テーブル ビューで **[フィルター** ] をクリックすると、[開始日] と [終了日] で日付 **範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="96611-123">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="96611-124">特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="96611-124">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="96611-125">テーブル内の行を選択すると、次の情報を含むフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="96611-125">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="96611-126">**日付**</span><span class="sxs-lookup"><span data-stu-id="96611-126">**Date**</span></span>
- <span data-ttu-id="96611-127">**配信不可レポート コード**: リンクをクリックすると、特定のエラー コードの原因と解決策の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="96611-127">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="96611-128">**Count**</span><span class="sxs-lookup"><span data-stu-id="96611-128">**Count**</span></span>
- <span data-ttu-id="96611-129">**サンプル メッセージ**: [サンプル メッセージの [](message-trace-scc.md)**表示] を** クリックすると、影響を受けるメッセージのサンプルのメッセージ トレース結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="96611-129">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![[配信不可] レポートの [詳細] テーブル ビューで行を選択した後の詳細の飛び出し](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="96611-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="96611-131">Related topics</span></span>

<span data-ttu-id="96611-132">メール フロー ダッシュボードの他の分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="96611-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
