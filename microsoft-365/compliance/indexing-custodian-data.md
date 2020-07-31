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
description: 高度な電子情報開示ケースに保管担当者が追加されると、部分的にインデックスと見なされたコンテンツはすべて再利用され、完全に検索可能になります。
ms.openlocfilehash: 95e087884b65628565e596dc8ae9f33aadc4cd9f
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527557"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="261d7-103">カストディアン データの詳細なインデックス処理</span><span class="sxs-lookup"><span data-stu-id="261d7-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="261d7-104">高度な電子情報開示ケースに保管担当者が追加されると、部分的にインデックスと見なされたコンテンツはすべて再利用され、完全に検索可能になります。</span><span class="sxs-lookup"><span data-stu-id="261d7-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="261d7-105">このプロセスは、*高度なインデックス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="261d7-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="261d7-106">画像の存在、サポートされていないファイルの種類、インデックスファイルサイズの制限が発生したなど、さまざまな理由でコンテンツを部分的にインデックス処理することができます。</span><span class="sxs-lookup"><span data-stu-id="261d7-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="261d7-107">処理のサポートおよび部分的なインデックスが作成されたアイテムの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="261d7-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="261d7-108">高度な電子情報開示でサポートされているファイルの種類</span><span class="sxs-lookup"><span data-stu-id="261d7-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="261d7-109">Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="261d7-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="261d7-110">Exchange Search によってインデックス処理されるファイル形式</span><span class="sxs-lookup"><span data-stu-id="261d7-110">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="261d7-111">SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="261d7-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="261d7-112">高度なインデックス作成の結果を表示する</span><span class="sxs-lookup"><span data-stu-id="261d7-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="261d7-113">高度なインデックス処理が完了すると、再処理の有効性について理解することができます。</span><span class="sxs-lookup"><span data-stu-id="261d7-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="261d7-114">ケースに対して [**処理**] タブの [詳細なインデックス作成の結果] ビューに、*ハイブリッドインデックス*に追加されたアイテムの数がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="261d7-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="261d7-115">ハイブリッドインデックスは、高度な電子情報開示が再処理されたコンテンツを格納する場所です。</span><span class="sxs-lookup"><span data-stu-id="261d7-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="261d7-116">このビューには、修復を必要とするアイテムの数と、ファイルの種類別のエラーのグラフも含まれています。</span><span class="sxs-lookup"><span data-stu-id="261d7-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="261d7-117">詳細については、以下をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="261d7-117">For more information, see:</span></span>

- [<span data-ttu-id="261d7-118">データ処理中のエラー修復</span><span class="sxs-lookup"><span data-stu-id="261d7-118">Error remediation when processing data</span></span>](error-remediation.md)

- [<span data-ttu-id="261d7-119">単一アイテムのエラーの修復</span><span class="sxs-lookup"><span data-stu-id="261d7-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="261d7-120">保管担当者の高度なインデックスを更新する</span><span class="sxs-lookup"><span data-stu-id="261d7-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="261d7-121">高度な電子情報開示ケースに保管担当者が追加されると、部分的にインデックスが作成されたすべてのアイテムが再処理されます。</span><span class="sxs-lookup"><span data-stu-id="261d7-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="261d7-122">ただし、時間が経過すると、インデックスが作成されたアイテムの数が多くなると、ユーザーのメールボックスまたは OneDrive アカウントに追加されることがあります。</span><span class="sxs-lookup"><span data-stu-id="261d7-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="261d7-123">必要に応じて、特定の保管担当者のインデックスを更新できます。</span><span class="sxs-lookup"><span data-stu-id="261d7-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="261d7-124">詳細については、「 [Manage 保管担当者 in a Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="261d7-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="261d7-125">[**処理**] タブの [**更新インデックス**] をクリックして、すべての保管担当者のインデックスを更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="261d7-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="261d7-126">保管担当者インデックスの更新は、長時間実行されるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="261d7-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="261d7-127">ケースでは、インデックスを1日に複数回更新しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="261d7-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>
