---
title: カストディアン データの詳細なインデックス処理
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
ms.openlocfilehash: ba85ef90570dfbf2228148bf5211a4b041a1cb61
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37085057"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="6cb75-102">カストディアン データの詳細なインデックス処理</span><span class="sxs-lookup"><span data-stu-id="6cb75-102">Advanced indexing of custodian data</span></span>

<span data-ttu-id="6cb75-103">高度な電子情報開示ケースに保管担当者が追加されると、部分的にインデックスと見なされた Office 365 のコンテンツはすべて、完全に検索可能になるように再処理されます。</span><span class="sxs-lookup"><span data-stu-id="6cb75-103">When a custodian is added to an Advanced eDiscovery case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span>  <span data-ttu-id="6cb75-104">このプロセスは、*高度なインデックス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="6cb75-104">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="6cb75-105">画像の存在、サポートされていないファイルの種類、インデックスファイルサイズの制限が発生したなど、さまざまな理由でコンテンツを部分的にインデックス処理することができます。</span><span class="sxs-lookup"><span data-stu-id="6cb75-105">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="6cb75-106">Office 365 の処理サポートと、部分的にインデックスが作成されたアイテムの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cb75-106">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="6cb75-107">高度な電子情報開示でサポートされているファイルの種類</span><span class="sxs-lookup"><span data-stu-id="6cb75-107">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)
- [<span data-ttu-id="6cb75-108">Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="6cb75-108">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
- [<span data-ttu-id="6cb75-109">Exchange Search によってインデックス処理されるファイル形式</span><span class="sxs-lookup"><span data-stu-id="6cb75-109">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [<span data-ttu-id="6cb75-110">SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="6cb75-110">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="6cb75-111">高度なインデックス作成の結果を表示する</span><span class="sxs-lookup"><span data-stu-id="6cb75-111">Viewing Advanced indexing results</span></span>

<span data-ttu-id="6cb75-112">高度なインデックス処理が完了すると、再処理の有効性について理解することができます。</span><span class="sxs-lookup"><span data-stu-id="6cb75-112">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="6cb75-113">[保管担当者 Indexing] ビューでは、*ハイブリッドインデックス*に追加されたすべてのアイテムがグラフに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="6cb75-113">In the Custodian Indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="6cb75-114">ハイブリッドインデックスは、高度な電子情報開示が再処理されたコンテンツを格納する場所です。</span><span class="sxs-lookup"><span data-stu-id="6cb75-114">The hybrid index is where Advanced eDiscovery stores the re-processed content.</span></span>

<span data-ttu-id="6cb75-115">グラフには、修復が必要な項目の数と、ファイルの種類別のエラーのグラフも表示されます。</span><span class="sxs-lookup"><span data-stu-id="6cb75-115">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="6cb75-116">詳細については、「[データ処理時のエラー修復](error-remediation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cb75-116">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-custodians"></a><span data-ttu-id="6cb75-117">保管担当者の高度なインデックスを更新する</span><span class="sxs-lookup"><span data-stu-id="6cb75-117">Updating Advanced indexes for custodians</span></span>

<span data-ttu-id="6cb75-118">高度な電子情報開示ケースに保管担当者が追加されると、部分的にインデックスが作成されたすべてのアイテムが再処理されます。</span><span class="sxs-lookup"><span data-stu-id="6cb75-118">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are re-processed.</span></span> <span data-ttu-id="6cb75-119">ただし、時間が経過すると、インデックスが作成されたアイテムの数が多くなると、ユーザーのメールボックスまたは OneDrive アカウントに追加されることがあります。</span><span class="sxs-lookup"><span data-stu-id="6cb75-119">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="6cb75-120">必要に応じて、インデックスを更新できます。</span><span class="sxs-lookup"><span data-stu-id="6cb75-120">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="6cb75-121">保管担当者インデックスの更新は、長時間実行されるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="6cb75-121">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="6cb75-122">ケースでは、1日に1回のインデックスを更新しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6cb75-122">It's recommended that you don't update indexes more than once per day in a case.</span></span>
