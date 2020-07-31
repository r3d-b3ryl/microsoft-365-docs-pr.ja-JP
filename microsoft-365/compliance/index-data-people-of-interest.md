---
title: 調査のためのデータの高度なインデックス作成
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
description: 高度なインデックスを使用して、調査する必要があるすべてのデータが検索によって取得されるようにする方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6e72ec4a41d5b32ef3837e52f21836207c6f66e1
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527579"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a><span data-ttu-id="4c0e6-103">調査のためのデータの高度なインデックス作成</span><span class="sxs-lookup"><span data-stu-id="4c0e6-103">Advanced indexing of data for an investigation</span></span>

<span data-ttu-id="4c0e6-104">イメージの存在、サポートされていないファイルの種類、インデックスファイルサイズの制限が発生したなど、さまざまな理由で、ライブシステムのコンテンツを部分的にインデックス処理することができます。</span><span class="sxs-lookup"><span data-stu-id="4c0e6-104">Content in the live system can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span> <span data-ttu-id="4c0e6-105">リスクの高いデータのスピルを処理している場合は、調査する必要があるすべてのデータが検索によって取得されたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c0e6-105">When you are dealing with high risk data spill, you want to make sure that your search captured all data that you want to investigate.</span></span> <span data-ttu-id="4c0e6-106">関心のある人物がデータ調査に追加されると、部分的にインデックスとして見なされたコンテンツはすべて再利用され、完全に検索可能になります。</span><span class="sxs-lookup"><span data-stu-id="4c0e6-106">When a person of interest is added to a Data investigation, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span> <span data-ttu-id="4c0e6-107">このプロセスは、*高度なインデックス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4c0e6-107">This process is called *Advanced indexing*.</span></span> 

<span data-ttu-id="4c0e6-108">処理のサポートおよび部分的なインデックスが作成されたアイテムの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c0e6-108">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="4c0e6-109">データ調査でサポートされているファイルの種類</span><span class="sxs-lookup"><span data-stu-id="4c0e6-109">Supported file types in Data Investigations</span></span>](supported-filetypes-datainvestigations.md)

- [<span data-ttu-id="4c0e6-110">Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="4c0e6-110">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="4c0e6-111">Exchange Search によってインデックス処理されるファイル形式</span><span class="sxs-lookup"><span data-stu-id="4c0e6-111">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="4c0e6-112">SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="4c0e6-112">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="4c0e6-113">高度なインデックス作成の結果を表示する</span><span class="sxs-lookup"><span data-stu-id="4c0e6-113">Viewing Advanced indexing results</span></span>

<span data-ttu-id="4c0e6-114">高度なインデックス処理が完了すると、再処理の有効性について理解することができます。</span><span class="sxs-lookup"><span data-stu-id="4c0e6-114">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="4c0e6-115">[インデックス作成] ビューのユーザーには、*ハイブリッドインデックス*に追加されたすべてのアイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c0e6-115">In the People of interest indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="4c0e6-116">ハイブリッドインデックスは、データ調査 (プレビュー) が再処理されたコンテンツを格納する場所です。</span><span class="sxs-lookup"><span data-stu-id="4c0e6-116">The hybrid index is where Data Investigations (Preview) stores the reprocessed content.</span></span>

<span data-ttu-id="4c0e6-117">グラフには、修復が必要な項目の数と、ファイルの種類別のエラーのグラフも表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c0e6-117">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="4c0e6-118">詳細については、「[データ処理時のエラー修復](error-remediation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c0e6-118">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-people-of-interest"></a><span data-ttu-id="4c0e6-119">関心のあるユーザーの高度なインデックスを更新する</span><span class="sxs-lookup"><span data-stu-id="4c0e6-119">Updating Advanced indexes for people of interest</span></span>

<span data-ttu-id="4c0e6-120">関心のある人物がデータ調査に追加されると、部分的にインデックスが作成されたすべてのアイテムが再処理されます。</span><span class="sxs-lookup"><span data-stu-id="4c0e6-120">When a person of interest is added to a data investigation, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="4c0e6-121">ただし、時間が経過すると、インデックスが作成されたアイテムの数が多くなると、ユーザーのメールボックスまたは OneDrive アカウントに追加されることがあります。</span><span class="sxs-lookup"><span data-stu-id="4c0e6-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="4c0e6-122">必要に応じて、インデックスを更新できます。</span><span class="sxs-lookup"><span data-stu-id="4c0e6-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="4c0e6-123">関心のあるインデックスを持つユーザーを更新する処理は、長時間実行されています。</span><span class="sxs-lookup"><span data-stu-id="4c0e6-123">Updating people of interest indexes is a long running process.</span></span> <span data-ttu-id="4c0e6-124">調査では1日に1回のインデックスを更新しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4c0e6-124">It's recommended that you don't update indexes more than once per day in an investigation.</span></span>
