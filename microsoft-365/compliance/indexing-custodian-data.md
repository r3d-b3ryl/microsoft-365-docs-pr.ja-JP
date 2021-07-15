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
description: 保管担当者を Advanced eDiscovery ケースに追加すると、部分的にインデックスが作成されたと見なされたコンテンツが再処理され、完全に検索可能になります。
ms.openlocfilehash: 34855eb168dd10fc500e2e57fe1d57ad81449452
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437978"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="8d3ff-103">カストディアン データの詳細なインデックス処理</span><span class="sxs-lookup"><span data-stu-id="8d3ff-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="8d3ff-104">保管担当者が Advanced eDiscovery ケースに追加された場合、部分的にインデックスが作成されたと見なされたコンテンツ、またはインデックスエラーが発生したコンテンツは、インデックスを再作成して完全に検索可能になります。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed or had indexing errors with is reindexed to make it fully searchable.</span></span>  <span data-ttu-id="8d3ff-105">このインデックスの再作成プロセスは、Advanced *indexing と呼ばれる。*</span><span class="sxs-lookup"><span data-stu-id="8d3ff-105">This reindexing process is called *Advanced indexing*.</span></span> <span data-ttu-id="8d3ff-106">コンテンツが部分的にインデックス付けされている、またはインデックスエラーが発生する理由は多数ある。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-106">There are a number of reasons that content is partially indexed or has indexing errors.</span></span> <span data-ttu-id="8d3ff-107">これには、イメージ ファイル、またはファイル内のイメージの存在、サポートされていないファイルの種類、またはファイル サイズのインデックスの制限が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-107">This includes image files or the presence of images in a file, unsupported file types, or file sized indexing limits.</span></span> <span data-ttu-id="8d3ff-108">ファイルSharePoint高度なインデックス作成は、アイテムに対してのみ実行され、部分的にインデックスが付いているか、インデックスエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-108">For SharePoint files, Advanced indexing only runs on items are marked as partially indexed or that have indexing errors.</span></span> <span data-ttu-id="8d3ff-109">このExchange、画像添付ファイルを持つ電子メール メッセージは、部分的にインデックス付けまたはインデックス作成エラーとしてマークされません。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-109">In Exchange, email messages that have image attachments are not marked as partially indexed or with indexing errors.</span></span> <span data-ttu-id="8d3ff-110">つまり、これらのファイルは Advanced インデックス処理によってインデックスが再作成されません。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-110">This means that those files will not be reindexed by the Advanced indexing process.</span></span>

<span data-ttu-id="8d3ff-111">サポートの処理と部分的にインデックス付きアイテムの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-111">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="8d3ff-112">サポートされているファイルの種類 (Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8d3ff-112">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="8d3ff-113">Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="8d3ff-113">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="8d3ff-114">Exchange Search によってインデックス処理されるファイル形式</span><span class="sxs-lookup"><span data-stu-id="8d3ff-114">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="8d3ff-115">SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="8d3ff-115">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="8d3ff-116">高度なインデックス作成結果の表示</span><span class="sxs-lookup"><span data-stu-id="8d3ff-116">Viewing Advanced indexing results</span></span>

<span data-ttu-id="8d3ff-117">高度なインデックス作成プロセスが完了したら、再処理の有効性を理解できます。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-117">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="8d3ff-118">ケースの [処理] タブの[高度なインデックス作成結果] ビューで、ハイブリッド インデックスに追加されたアイテムの数が *グラフに一覧表示されます*。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-118">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="8d3ff-119">ハイブリッド インデックスは、再Advanced eDiscoveryコンテンツを格納する場所です。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-119">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="8d3ff-120">このビューには、修復が必要なアイテムの数と、ファイルの種類別のエラーの別のグラフも含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-120">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="8d3ff-121">詳しくは、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-121">For more information, see:</span></span>

- [<span data-ttu-id="8d3ff-122">データ処理中のエラー修復</span><span class="sxs-lookup"><span data-stu-id="8d3ff-122">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="8d3ff-123">単一アイテムのエラーの修復</span><span class="sxs-lookup"><span data-stu-id="8d3ff-123">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="8d3ff-124">保管担当者の高度なインデックスの更新</span><span class="sxs-lookup"><span data-stu-id="8d3ff-124">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="8d3ff-125">保管担当者がケースに追加Advanced eDiscovery、部分的にインデックスが作成されたアイテムはすべて再処理されます。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-125">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="8d3ff-126">ただし、時間が経過すると、部分的にインデックスが作成されたアイテムがユーザーのメールボックスまたはアカウントに追加OneDriveがあります。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-126">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="8d3ff-127">必要に応じて、特定の保管担当者のインデックスを更新できます。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-127">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="8d3ff-128">詳細については、「Manage [custodians in an Advanced eDiscovery ケース」を参照してください](manage-new-custodians.md#re-index-custodian-data)。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-128">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="8d3ff-129">[処理] タブの [更新] インデックスをクリックすると、ケース内のすべての保管担当者の **インデックス** を **更新** することもできます。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-129">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="8d3ff-130">保管担当者インデックスの更新は、長時間実行されるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-130">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="8d3ff-131">1 つのケースで 1 日に 2 回以上インデックスを更新しない方が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="8d3ff-131">It's recommended that you don't update indexes more than once a day in a case.</span></span>
