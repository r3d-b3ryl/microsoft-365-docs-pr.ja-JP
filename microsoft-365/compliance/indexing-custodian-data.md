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
description: 保管担当者が Advanced eDiscovery ケースに追加された場合、部分的にインデックスが作成されたと見なされたコンテンツは再処理され、完全に検索可能になります。
ms.openlocfilehash: 908d01cacc103639e1f9efe965240c33a5296ba9
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750758"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="db826-103">カストディアン データの詳細なインデックス処理</span><span class="sxs-lookup"><span data-stu-id="db826-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="db826-104">保管担当者が Advanced eDiscovery ケースに追加された場合、部分的にインデックスが作成されたと見なされたコンテンツは再処理され、完全に検索可能になります。</span><span class="sxs-lookup"><span data-stu-id="db826-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="db826-105">このプロセスは、高度な *インデックス作成と呼ばれる処理です*。</span><span class="sxs-lookup"><span data-stu-id="db826-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="db826-106">画像の存在、サポートされていないファイルの種類、ファイル サイズの制限のインデックスを作成する場合など、多くの理由から、コンテンツに部分的にインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="db826-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="db826-107">サポートと部分的にインデックスが作成されたアイテムの処理の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db826-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="db826-108">Advanced eDiscovery でサポートされるファイルの種類</span><span class="sxs-lookup"><span data-stu-id="db826-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="db826-109">Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="db826-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="db826-110">Exchange Search によってインデックス処理されるファイル形式</span><span class="sxs-lookup"><span data-stu-id="db826-110">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="db826-111">SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="db826-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="db826-112">高度なインデックス作成結果の表示</span><span class="sxs-lookup"><span data-stu-id="db826-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="db826-113">高度なインデックス作成プロセスが完了すると、再処理の有効性を理解できます。</span><span class="sxs-lookup"><span data-stu-id="db826-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="db826-114">ケースの [処理] タブの[詳細なインデックス作成の結果] ビューに、ハイブリッド インデックスに追加されたアイテムの数が *グラフに表示されます*。</span><span class="sxs-lookup"><span data-stu-id="db826-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="db826-115">ハイブリッド インデックスは、Advanced eDiscovery が再処理されたコンテンツを格納する場所です。</span><span class="sxs-lookup"><span data-stu-id="db826-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="db826-116">このビューには、修復が必要なアイテムの数と、ファイルの種類別のエラーの別のグラフも含まれます。</span><span class="sxs-lookup"><span data-stu-id="db826-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="db826-117">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db826-117">For more information, see:</span></span>

- [<span data-ttu-id="db826-118">データ処理中のエラー修復</span><span class="sxs-lookup"><span data-stu-id="db826-118">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="db826-119">単一アイテムのエラーの修復</span><span class="sxs-lookup"><span data-stu-id="db826-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="db826-120">カストディアンの高度なインデックスの更新</span><span class="sxs-lookup"><span data-stu-id="db826-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="db826-121">保管担当者が Advanced eDiscovery ケースに追加された場合、部分的にインデックスが作成されたアイテムはすべて再処理されます。</span><span class="sxs-lookup"><span data-stu-id="db826-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="db826-122">ただし、時間が経過すると、部分的にインデックスが作成されたアイテムがユーザーのメールボックスまたは OneDrive アカウントに追加される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="db826-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="db826-123">必要に応じて、特定のカストディアンのインデックスを更新できます。</span><span class="sxs-lookup"><span data-stu-id="db826-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="db826-124">詳細については [、「Advanced eDiscovery ケースで保管担当者を管理する」を参照してください](manage-new-custodians.md#re-index-custodian-data)。</span><span class="sxs-lookup"><span data-stu-id="db826-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="db826-125">ケース内のすべての保管担当者のインデックスを更新するには、[処理] タブの [更新 **] インデックス** を **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="db826-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="db826-126">カストディアン インデックスの更新は、長時間実行されるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="db826-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="db826-127">1 日に 2 回以上インデックスを更新しないでお勧めします。</span><span class="sxs-lookup"><span data-stu-id="db826-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>
