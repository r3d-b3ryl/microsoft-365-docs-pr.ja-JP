---
title: データ分類プレビューのリリース ノート (プレビュー)
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
description: データ分類パブリック プレビューのリリース ノート。
ms.openlocfilehash: 1beae92089833327cedf6090690530d9e5457a37
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076364"
---
# <a name="data-classification-public-preview-release-notes-preview"></a><span data-ttu-id="8198f-103">データ分類パブリック プレビューのリリース ノート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="8198f-103">Data classification public preview release notes (preview)</span></span>

<span data-ttu-id="8198f-104">このパブリック プレビューでは、ポリシーを作成する *前に* 機密コンテンツとラベル付きコンテンツのスキャンを開始する新しい機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="8198f-104">This public preview introduces new functionality where scanning of your sensitive content and labeled content starts *before* you create any policies.</span></span> <span data-ttu-id="8198f-105">これは **ゼロ変更管理** と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="8198f-105">This is called **zero change management**.</span></span> <span data-ttu-id="8198f-106">これにより、すべての保持ラベルおよび機密ラベルが環境に与える影響を確認でき、保護ポリシーおよびガバナンス ポリシーのニーズの評価を開始できます。</span><span class="sxs-lookup"><span data-stu-id="8198f-106">This lets you see the impact that all the retention and sensitivity labels are having in your environment and empower you to start assessing your protection and governance policy needs.</span></span>

<span data-ttu-id="8198f-107">このパブリック プレビューで最高の体験ができるように、これらのリリース ノートを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8198f-107">Please review these release notes so that you have the best experience with this public preview.</span></span> <span data-ttu-id="8198f-108">現在と一般提供 (GA) の間のこれらのポイントに対処する作業を行います。</span><span class="sxs-lookup"><span data-stu-id="8198f-108">We will be working on addressing these points between now and general availability (GA).</span></span>

## <a name="permissions-for-accessing-content-explorer"></a><span data-ttu-id="8198f-109">コンテンツ エクスプローラーにアクセスするためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8198f-109">Permissions for accessing content explorer</span></span>

<span data-ttu-id="8198f-110">コンテンツ エクスプローラーへのアクセスは、スキャンしたファイルのコンテンツを読み取ることができるため、厳しく制限されています。</span><span class="sxs-lookup"><span data-stu-id="8198f-110">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span> <span data-ttu-id="8198f-111">コンテンツ エクスプローラーにアクセスするには、**コンテンツ エクスプローラーのリスト ビューアー** および **コンテンツ エクスプローラーのコンテンツ ビューアー** の役割グループのメンバーシップが必要です。</span><span class="sxs-lookup"><span data-stu-id="8198f-111">Access to content explorer requires membership in the **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups.</span></span> <span data-ttu-id="8198f-112">既定では、コンテンツ エクスプローラーにアクセスできるアカウントはありません。</span><span class="sxs-lookup"><span data-stu-id="8198f-112">No account has access to content explorer by default.</span></span> <span data-ttu-id="8198f-113">「[データ分類コンテンツ エクスプローラー (プレビュー)](data-classification-content-explorer.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8198f-113">See, [Using data classification content explorer (preview)](data-classification-content-explorer.md#permissions).</span></span> <span data-ttu-id="8198f-114">グローバル管理者、コンプライアンス管理者、またはデータ管理者は、必要な **コンテンツ エクスプローラーのリスト ビューアー**、および **コンテンツ エクスプローラーのコンテンツ ビューアー** の役割グループのメンバーシップを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8198f-114">A Global admin, Compliance admin, or Data admin can assign the necessary **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role group membership.</span></span>

> [!TIP]
> <span data-ttu-id="8198f-115">ロール ベースのアクセス制御 (RBAC) が世界中に展開されている間、**コンテンツ エクスプローラーのリスト ビューアー**、および **コンテンツ エクスプローラーのコンテンツ ビューアー** の役割グループがアクセス許可のページに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="8198f-115">The **Content Explorer List Viewer**, and the **Content Explorer Content Viewer** role groups may not appear on the permissions page while the Role Based Access Controls (RBAC) are being deployed worldwide.</span></span> <span data-ttu-id="8198f-116">アクセス許可のページに表示されない場合は、カスタム役割グループを作成し、`data classification list viewer` ロールまたは `data classification content viewer` ロールをカスタム役割グループに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8198f-116">If they aren't appearing on the permissions page, you must create a custom role group and assign the `data classification list viewer` role and or the `data classification content viewer` roles to your custom role group.</span></span>

## <a name="exchange-mailbox-count"></a><span data-ttu-id="8198f-117">Exchange メールボックス数</span><span class="sxs-lookup"><span data-stu-id="8198f-117">Exchange mailbox count</span></span>

<span data-ttu-id="8198f-118">Exchange メールボックスに移動すると、小さなツール ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8198f-118">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="8198f-119">これは、機密情報の種類、機密ラベル、および保持ラベルに表示される集計数が、メールボックス内にあるアイテムの数と正確に一致しない場合があることを示すためです。</span><span class="sxs-lookup"><span data-stu-id="8198f-119">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="8198f-120">これは、集計された数が計算されている間に、フォルダへのドリルダウンが分類されたコンテンツのライブ ビューをフェッチするためです。</span><span class="sxs-lookup"><span data-stu-id="8198f-120">This is because the drill down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>

## <a name="seeing-guids-instead-of-label-names"></a><span data-ttu-id="8198f-121">ラベル名の代わりに GUID を表示する</span><span class="sxs-lookup"><span data-stu-id="8198f-121">Seeing GUIDs instead of label names</span></span>

<span data-ttu-id="8198f-122">プライベート プレビューのお客様の場合、コンテンツが既にスタンプされたラベルの移行またはラベルを削除するとコンテンツ エクスプローラーおよびアクティビティ エクスプローラーでラベル名の代わりに 32 ビット GUID に解決されるインスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8198f-122">Private preview customers have seen instances where the migrated labels or deletion of a label that content has already been stamped with results in label names resolving to a 32-bit GUID in content explorer and activity explorer instead of the label name.</span></span> 

## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="8198f-123">暗号化されたドキュメントのレンダリング</span><span class="sxs-lookup"><span data-stu-id="8198f-123">Rendering of encrypted documents</span></span>

<span data-ttu-id="8198f-124">暗号化された SharePoint、Exchange、および OneDrive ファイルは、コンテンツ エクスプローラーにレンダリングされません。</span><span class="sxs-lookup"><span data-stu-id="8198f-124">SharePoint, Exchange, and OneDrive files that are encrypted will not render in the content explorer.</span></span> <span data-ttu-id="8198f-125">これは、コンテンツ エクスプローラーでファイル コンテンツを表示する必要性とコンテンツを暗号化しておく必要性とのバランスを必要とする、慎重を期する問題です。</span><span class="sxs-lookup"><span data-stu-id="8198f-125">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="8198f-126">**コンテンツ エクスプローラーのリスト ビューアー**、および **コンテンツ エクスプローラーのコンテンツ ビューアー** の役割グループによってアクセス許可が付与されると、ファイルのリスト ビュー、ファイルのメタデータ、および Web クライアント経由でコンテンツにアクセスするために使用できるリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8198f-126">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="8198f-127">SharePoint 検索の保持ラベル名でサポートされている文字</span><span class="sxs-lookup"><span data-stu-id="8198f-127">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="8198f-128">SharePoint検索では、`-` または `_` を含む保持ラベル名はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8198f-128">SharePoint search does not support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="8198f-129">たとえば、`Label-MIP` や `Label_MIP` はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8198f-129">For example `Label-MIP` and `Label_MIP` are not supported.</span></span> <span data-ttu-id="8198f-130">SharePoint 検索は、機密ラベル名および機密情報の種類の名前に含まれるこれらの文字はサポートします。</span><span class="sxs-lookup"><span data-stu-id="8198f-130">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="see-also"></a><span data-ttu-id="8198f-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="8198f-131">See also</span></span>

- [<span data-ttu-id="8198f-132">データ分類の使用を開始する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="8198f-132">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="8198f-133">ラベル アクティビティを表示する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="8198f-133">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="8198f-134">ラベル付きコンテンツの表示 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="8198f-134">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="8198f-135">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="8198f-135">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="8198f-136">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="8198f-136">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="8198f-137">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="8198f-137">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

