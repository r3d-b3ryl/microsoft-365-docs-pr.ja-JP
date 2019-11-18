---
title: 調査のためのデータの高度なインデックス作成
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
description: ''
ms.openlocfilehash: d49f94d4f77d7ed386db02eab4e4bf29a0e8fd04
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "38686724"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a><span data-ttu-id="7c165-102">調査のためのデータの高度なインデックス作成</span><span class="sxs-lookup"><span data-stu-id="7c165-102">Advanced indexing of data for an investigation</span></span>

<span data-ttu-id="7c165-103">イメージの存在、サポートされていないファイルの種類、インデックスファイルサイズの制限が発生したなど、さまざまな理由で、ライブシステムのコンテンツを部分的にインデックス処理することができます。</span><span class="sxs-lookup"><span data-stu-id="7c165-103">Content in the live system can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span> <span data-ttu-id="7c165-104">リスクの高いデータのスピルを処理している場合は、調査する必要があるすべてのデータが検索によって取得されたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c165-104">When you are dealing with high risk data spill, you want to make sure that your search captured all data that you want to investigate.</span></span> <span data-ttu-id="7c165-105">関心のある人物がデータ調査に追加されると、部分的にインデックスとして見なされた Office 365 のコンテンツはすべて、完全に検索可能になるように再処理されます。</span><span class="sxs-lookup"><span data-stu-id="7c165-105">When a person of interest is added to a Data investigation, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span> <span data-ttu-id="7c165-106">このプロセスは、*高度なインデックス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="7c165-106">This process is called *Advanced indexing*.</span></span> 

<span data-ttu-id="7c165-107">Office 365 の処理サポートと、部分的にインデックスが作成されたアイテムの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c165-107">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="7c165-108">データ調査でサポートされているファイルの種類</span><span class="sxs-lookup"><span data-stu-id="7c165-108">Supported file types in Data Investigations</span></span>](supported-filetypes-datainvestigations.md)

- [<span data-ttu-id="7c165-109">Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="7c165-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="7c165-110">Exchange Search によってインデックス処理されるファイル形式</span><span class="sxs-lookup"><span data-stu-id="7c165-110">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="7c165-111">SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="7c165-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="7c165-112">高度なインデックス作成の結果を表示する</span><span class="sxs-lookup"><span data-stu-id="7c165-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="7c165-113">高度なインデックス処理が完了すると、再処理の有効性について理解することができます。</span><span class="sxs-lookup"><span data-stu-id="7c165-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="7c165-114">[インデックス作成] ビューのユーザーには、*ハイブリッドインデックス*に追加されたすべてのアイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c165-114">In the People of interest indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="7c165-115">ハイブリッドインデックスは、データ調査 (プレビュー) が再処理されたコンテンツを格納する場所です。</span><span class="sxs-lookup"><span data-stu-id="7c165-115">The hybrid index is where Data Investigations (Preview) stores the re-processed content.</span></span>

<span data-ttu-id="7c165-116">グラフには、修復が必要な項目の数と、ファイルの種類別のエラーのグラフも表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c165-116">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="7c165-117">詳細については、「[データ処理時のエラー修復](error-remediation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c165-117">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-people-of-interest"></a><span data-ttu-id="7c165-118">関心のあるユーザーの高度なインデックスを更新する</span><span class="sxs-lookup"><span data-stu-id="7c165-118">Updating Advanced indexes for people of interest</span></span>

<span data-ttu-id="7c165-119">関心のあるユーザーがデータ調査に追加されると、部分的にインデックスが作成されたすべてのアイテムが再処理されます。</span><span class="sxs-lookup"><span data-stu-id="7c165-119">When a person of interest is added to a data investigation, all partially indexed items are re-processed.</span></span> <span data-ttu-id="7c165-120">ただし、時間が経過すると、インデックスが作成されたアイテムの数が多くなると、ユーザーのメールボックスまたは OneDrive アカウントに追加されることがあります。</span><span class="sxs-lookup"><span data-stu-id="7c165-120">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="7c165-121">必要に応じて、インデックスを更新できます。</span><span class="sxs-lookup"><span data-stu-id="7c165-121">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="7c165-122">関心のあるインデックスを持つユーザーを更新する処理は、長時間実行されています。</span><span class="sxs-lookup"><span data-stu-id="7c165-122">Updating people of interest indexes is a long running process.</span></span> <span data-ttu-id="7c165-123">調査では1日に1回のインデックスを更新しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7c165-123">It's recommended that you don't update indexes more than once per day in an investigation.</span></span>
