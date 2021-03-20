---
title: カストディアン データの詳細なインデックス処理
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 高度な電子情報開示ケースに保管担当者を追加すると、部分的にインデックスが作成されたと見なされたコンテンツが再処理され、完全に検索可能になります。
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911211"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="8fc25-103">カストディアン データの詳細なインデックス処理</span><span class="sxs-lookup"><span data-stu-id="8fc25-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="8fc25-104">高度な電子情報開示ケースに保管担当者を追加すると、部分的にインデックスが作成されたと見なされたコンテンツが再処理され、完全に検索可能になります。</span><span class="sxs-lookup"><span data-stu-id="8fc25-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="8fc25-105">このプロセスは Advanced *indexing と呼ばれる。*</span><span class="sxs-lookup"><span data-stu-id="8fc25-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="8fc25-106">画像の存在、サポートされていないファイルの種類、またはファイル サイズの制限のインデックスを作成する場合など、さまざまな理由でコンテンツを部分的にインデックス化できます。</span><span class="sxs-lookup"><span data-stu-id="8fc25-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="8fc25-107">サポートの処理と部分的にインデックス付きアイテムの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fc25-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="8fc25-108">Advanced eDiscovery でサポートされるファイルの種類</span><span class="sxs-lookup"><span data-stu-id="8fc25-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="8fc25-109">Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="8fc25-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="8fc25-110">Exchange Search によってインデックス処理されるファイル形式</span><span class="sxs-lookup"><span data-stu-id="8fc25-110">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="8fc25-111">SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="8fc25-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="8fc25-112">高度なインデックス作成結果の表示</span><span class="sxs-lookup"><span data-stu-id="8fc25-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="8fc25-113">高度なインデックス作成プロセスが完了したら、再処理の有効性を理解できます。</span><span class="sxs-lookup"><span data-stu-id="8fc25-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="8fc25-114">ケースの [処理] タブの[高度なインデックス作成結果] ビューで、ハイブリッド インデックスに追加されたアイテムの数が *グラフに一覧表示されます*。</span><span class="sxs-lookup"><span data-stu-id="8fc25-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="8fc25-115">ハイブリッド インデックスは、Advanced eDiscovery が再処理されたコンテンツを格納する場所です。</span><span class="sxs-lookup"><span data-stu-id="8fc25-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="8fc25-116">このビューには、修復が必要なアイテムの数と、ファイルの種類別のエラーの別のグラフも含まれます。</span><span class="sxs-lookup"><span data-stu-id="8fc25-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="8fc25-117">詳しくは、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fc25-117">For more information, see:</span></span>

- [<span data-ttu-id="8fc25-118">データ処理中のエラー修復</span><span class="sxs-lookup"><span data-stu-id="8fc25-118">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="8fc25-119">単一アイテムのエラーの修復</span><span class="sxs-lookup"><span data-stu-id="8fc25-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="8fc25-120">保管担当者の高度なインデックスの更新</span><span class="sxs-lookup"><span data-stu-id="8fc25-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="8fc25-121">高度な電子情報開示ケースに保管担当者を追加すると、部分的にインデックスが作成されたアイテムすべてが再処理されます。</span><span class="sxs-lookup"><span data-stu-id="8fc25-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="8fc25-122">ただし、時間が経過すると、ユーザーのメールボックスまたは OneDrive アカウントに、より部分的にインデックス付きアイテムが追加される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8fc25-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="8fc25-123">必要に応じて、特定の保管担当者のインデックスを更新できます。</span><span class="sxs-lookup"><span data-stu-id="8fc25-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="8fc25-124">詳細については、「Advanced [eDiscovery case で保管担当者を管理する」を参照してください](manage-new-custodians.md#re-index-custodian-data)。</span><span class="sxs-lookup"><span data-stu-id="8fc25-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="8fc25-125">[処理] タブの [更新] インデックスをクリックすると、ケース内のすべての保管担当者の **インデックス** を **更新** することもできます。</span><span class="sxs-lookup"><span data-stu-id="8fc25-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="8fc25-126">保管担当者インデックスの更新は、長時間実行されるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="8fc25-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="8fc25-127">1 つのケースで 1 日に 2 回以上インデックスを更新しない方が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="8fc25-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>