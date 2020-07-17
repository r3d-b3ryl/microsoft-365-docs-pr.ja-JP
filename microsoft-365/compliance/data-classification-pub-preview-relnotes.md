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
ms.openlocfilehash: 71d8e8e4fffddc4c9373a2bdd37d4509337ec231
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127142"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="27379-103">データ分類のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="27379-103">Data classification release notes</span></span>

<span data-ttu-id="27379-104">データ分類について最高の体験ができるように、これらのリリース ノートをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="27379-104">Please review these release notes so that you have the best experience with data classification.</span></span>

## <a name="exchange-mailbox-count"></a><span data-ttu-id="27379-105">Exchange メールボックス数</span><span class="sxs-lookup"><span data-stu-id="27379-105">Exchange mailbox count</span></span>

<span data-ttu-id="27379-106">Exchange メールボックスに移動すると、小さなツール ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27379-106">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="27379-107">これは、機密情報の種類、機密ラベル、および保持ラベルに表示される集計数が、メールボックス内にあるアイテムの数と正確に一致しない場合があることを示すためです。</span><span class="sxs-lookup"><span data-stu-id="27379-107">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="27379-108">これは、集計された数が計算されている間に、フォルダへのドリルダウンが分類されたコンテンツのライブ ビューをフェッチするためです。</span><span class="sxs-lookup"><span data-stu-id="27379-108">This is because the drill down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="27379-109">暗号化されたドキュメントのレンダリング</span><span class="sxs-lookup"><span data-stu-id="27379-109">Rendering of encrypted documents</span></span>

<span data-ttu-id="27379-110">暗号化された SharePoint、Exchange、および OneDrive ファイルは、コンテンツ エクスプローラーにレンダリングされません。</span><span class="sxs-lookup"><span data-stu-id="27379-110">SharePoint, Exchange, and OneDrive files that are encrypted will not render in the content explorer.</span></span> <span data-ttu-id="27379-111">これは、コンテンツ エクスプローラーでファイル コンテンツを表示する必要性とコンテンツを暗号化しておく必要性とのバランスを必要とする、慎重を期する問題です。</span><span class="sxs-lookup"><span data-stu-id="27379-111">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="27379-112">**コンテンツ エクスプローラーのリスト ビューアー**、および **コンテンツ エクスプローラーのコンテンツ ビューアー** の役割グループによってアクセス許可が付与されると、ファイルのリスト ビュー、ファイルのメタデータ、および Web クライアント経由でコンテンツにアクセスするために使用できるリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27379-112">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="27379-113">SharePoint 検索の保持ラベル名でサポートされている文字</span><span class="sxs-lookup"><span data-stu-id="27379-113">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="27379-114">SharePoint検索では、`-` または `_` を含む保持ラベル名はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="27379-114">SharePoint search does not support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="27379-115">たとえば、`Label-MIP` や `Label_MIP` はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="27379-115">For example `Label-MIP` and `Label_MIP` are not supported.</span></span> <span data-ttu-id="27379-116">SharePoint 検索は、機密ラベル名および機密情報の種類の名前に含まれるこれらの文字はサポートします。</span><span class="sxs-lookup"><span data-stu-id="27379-116">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="27379-117">OneDrive はプレビューのまま</span><span class="sxs-lookup"><span data-stu-id="27379-117">OneDrive remains in preview</span></span>

<span data-ttu-id="27379-118">プレビュープログラム中に、OneDrive との統合に関する貴重なフィードバックをいただきました。</span><span class="sxs-lookup"><span data-stu-id="27379-118">We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="27379-119">具体的に作業を進めていくと、一貫性がないデータ/フローに遭遇する場合があります。</span><span class="sxs-lookup"><span data-stu-id="27379-119">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="27379-120">すべての修正が行われるまでは、引き続き OneDrive をプレビューとして紹介し続けます。</span><span class="sxs-lookup"><span data-stu-id="27379-120">We will continue to showcase OneDrive in preview till all fixes are in place.</span></span> <span data-ttu-id="27379-121">今後ともサポートをよろしくお願いいたします。</span><span class="sxs-lookup"><span data-stu-id="27379-121">We appreciate your continued support on this.</span></span>


## <a name="see-also"></a><span data-ttu-id="27379-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="27379-122">See also</span></span>

- [<span data-ttu-id="27379-123">データ分類の使用を開始する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="27379-123">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="27379-124">ラベル アクティビティを表示する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="27379-124">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="27379-125">ラベル付きコンテンツの表示 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="27379-125">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="27379-126">機密ラベルについて詳しく見る</span><span class="sxs-lookup"><span data-stu-id="27379-126">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="27379-127">保持ポリシーおよび保持ラベルについて詳しく見る</span><span class="sxs-lookup"><span data-stu-id="27379-127">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="27379-128">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="27379-128">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)