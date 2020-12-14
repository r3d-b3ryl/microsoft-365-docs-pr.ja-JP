---
title: データ分類のリリース ノート
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: データ分類についてのリリース ノート。
ms.openlocfilehash: 2b9302cfa49f9445d3cbeb5109aef70e0c8d8f7f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663042"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="47442-103">データ分類のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="47442-103">Data classification release notes</span></span>


## <a name="exchange-mailbox-count"></a><span data-ttu-id="47442-104">Exchange メールボックス数</span><span class="sxs-lookup"><span data-stu-id="47442-104">Exchange mailbox count</span></span>

<span data-ttu-id="47442-105">Exchange メールボックスに移動すると、小さなツール ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="47442-105">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="47442-106">これは、機密情報の種類、機密ラベル、および保持ラベルに表示される集計数が、メールボックス内にあるアイテムの数と正確に一致しない場合があることを示すためです。</span><span class="sxs-lookup"><span data-stu-id="47442-106">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="47442-107">これは、集計された数が計算されている間に、フォルダへのドリルダウンが分類されたコンテンツのライブ ビューをフェッチするためです。</span><span class="sxs-lookup"><span data-stu-id="47442-107">This is because the drill-down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="47442-108">暗号化されたドキュメントのレンダリング</span><span class="sxs-lookup"><span data-stu-id="47442-108">Rendering of encrypted documents</span></span>

<span data-ttu-id="47442-109">暗号化された SharePoint、Exchange、および OneDrive ファイルは、コンテンツ エクスプローラーでレンダリングを実行ません。</span><span class="sxs-lookup"><span data-stu-id="47442-109">SharePoint, Exchange, and OneDrive files that are encrypted don't render in the content explorer.</span></span> <span data-ttu-id="47442-110">これは、コンテンツ エクスプローラーでファイル コンテンツを表示する必要性とコンテンツを暗号化しておく必要性とのバランスを必要とする、慎重を期する問題です。</span><span class="sxs-lookup"><span data-stu-id="47442-110">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="47442-111">**コンテンツ エクスプローラーのリスト ビューアー**、および **コンテンツ エクスプローラーのコンテンツ ビューアー** の役割グループによってアクセス許可が付与されると、ファイルのリスト ビュー、ファイルのメタデータ、および Web クライアント経由でコンテンツにアクセスするために使用できるリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="47442-111">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="47442-112">SharePoint 検索の保持ラベル名でサポートされている文字</span><span class="sxs-lookup"><span data-stu-id="47442-112">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="47442-113">SharePoint検索では、`-` または `_` を含む保持ラベル名はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="47442-113">SharePoint search doesn't support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="47442-114">たとえば、`Label-MIP` や `Label_MIP` はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="47442-114">For example, `Label-MIP` and `Label_MIP` aren't supported.</span></span> <span data-ttu-id="47442-115">SharePoint 検索は、機密ラベル名および機密情報の種類の名前に含まれるこれらの文字はサポートします。</span><span class="sxs-lookup"><span data-stu-id="47442-115">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="47442-116">OneDrive はプレビューのまま</span><span class="sxs-lookup"><span data-stu-id="47442-116">OneDrive remains in preview</span></span>

<span data-ttu-id="47442-117">プレビュープログラム中に、OneDrive との統合に関する貴重なフィードバックをいただき、ありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="47442-117">Thanks for your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="47442-118">具体的に作業を進めていくと、一貫性がないデータ/フローに遭遇する場合があります。</span><span class="sxs-lookup"><span data-stu-id="47442-118">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="47442-119">すべての修正が行われるまでは、引き続き OneDrive をプレビューとして紹介し続けます。</span><span class="sxs-lookup"><span data-stu-id="47442-119">We'll continue to showcase OneDrive in preview until all fixes are in place.</span></span> <span data-ttu-id="47442-120">継続的なサポートに感謝いたします。</span><span class="sxs-lookup"><span data-stu-id="47442-120">We appreciate your continued support.</span></span>


## <a name="see-also"></a><span data-ttu-id="47442-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="47442-121">See also</span></span>

- [<span data-ttu-id="47442-122">データ分類の使用を開始する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="47442-122">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="47442-123">ラベル アクティビティを表示する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="47442-123">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="47442-124">ラベル付きコンテンツの表示 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="47442-124">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="47442-125">機密ラベルについて詳しく見る</span><span class="sxs-lookup"><span data-stu-id="47442-125">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="47442-126">アイテム保持ポリシーと保持ラベルの詳細</span><span class="sxs-lookup"><span data-stu-id="47442-126">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="47442-127">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="47442-127">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)