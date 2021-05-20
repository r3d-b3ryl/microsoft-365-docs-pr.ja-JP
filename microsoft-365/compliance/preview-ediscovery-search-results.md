---
title: 電子情報開示検索の結果をプレビューする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 コンプライアンス センターのコンテンツ検索またはコア電子情報開示検索によって返される結果サンプルをプレビューします。
ms.openlocfilehash: a89c8c9ed2500b4e2a859c75be3da177203d1406
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538599"
---
# <a name="preview-ediscovery-search-results"></a><span data-ttu-id="88d37-103">電子情報開示検索結果をプレビューする</span><span class="sxs-lookup"><span data-stu-id="88d37-103">Preview eDiscovery search results</span></span>

<span data-ttu-id="88d37-104">コンテンツ検索、またはコア電子情報開示ケースに関連付けられている検索を実行すると、検索によって返される結果サンプルをプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="88d37-104">After you run a Content search or a search associated with a Core eDiscovery case, you can preview a sample of the results returned by the search.</span></span> <span data-ttu-id="88d37-105">検索クエリによって返されたアイテムをプレビューすると、検索が所望の結果を返しているかどうか、検索クエリを変更して検索を再実行する必要があるのかどうかを把握することができます。</span><span class="sxs-lookup"><span data-stu-id="88d37-105">Previewing items returned by the search query can help you determine if the search is returning the results you hope for or if you need to change the search query and rerun the search.</span></span>

<span data-ttu-id="88d37-106">検索によって返される結果サンプルをプレビューするには、次の方法があります。</span><span class="sxs-lookup"><span data-stu-id="88d37-106">To preview a sample of results returned by a search:</span></span>

1. <span data-ttu-id="88d37-107">Microsoft 365 コンプライアンス センターで、コンテンツ検索ページまたはコア電子情報開示ケースに移動します。</span><span class="sxs-lookup"><span data-stu-id="88d37-107">In the Microsoft 365 compliance center, go to the Content search page or a Core eDiscovery case.</span></span>

2. <span data-ttu-id="88d37-108">検索を選択して、ポップアップ ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="88d37-108">Select search to display the flyout page.</span></span>

3. <span data-ttu-id="88d37-109">ポップアップ ページの下部で、**[サンプルのレビュー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="88d37-109">On the bottom of the flyout page, click **Review sample**.</span></span>

   ![ポップアップ ページで [サンプルのレビュー] をクリックして結果をプレビューする](../media/PreviewSearchResults1.png)

   <span data-ttu-id="88d37-111">検索結果のサンプルを含むページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="88d37-111">A page is displayed containing a sample of the search results.</span></span>

4. <span data-ttu-id="88d37-112">閲覧ウィンドウでアイテムを選んで内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="88d37-112">Select an item to view its contents in the reading pane.</span></span>

   ![閲覧ウィンドウでアイテムをプレビュー](../media/PreviewSearchResults2.png)

   <span data-ttu-id="88d37-114">前述のスクリーンショットでは、アイテムをプレビューする場合に、検索クエリのキーワードが強調表示されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="88d37-114">In the previous screenshot, notice that keywords from the search query are highlighted when you preview items.</span></span>

## <a name="how-the-search-result-samples-are-selected"></a><span data-ttu-id="88d37-115">検索結果のサンプルを選択する方法</span><span class="sxs-lookup"><span data-stu-id="88d37-115">How the search result samples are selected</span></span>

<span data-ttu-id="88d37-116">最大 1,000 個のランダムに選ばれたアイテムをプレビューすることができます。</span><span class="sxs-lookup"><span data-stu-id="88d37-116">A maximum of 1,000 randomly selected items are available to preview.</span></span> <span data-ttu-id="88d37-117">プレビューで利用可能なアイテムは、無作為に選ばれたものに加えて、以下の条件を満たすものです。</span><span class="sxs-lookup"><span data-stu-id="88d37-117">In addition to being randomly selected, items available for preview must also meet the following criteria:</span></span>

- <span data-ttu-id="88d37-118">単一のコンテンツの場所 (メールボックスまたはサイト) で最大 100 個のアイテムをプレビューすることができます。</span><span class="sxs-lookup"><span data-stu-id="88d37-118">A maximum of 100 items from a single content location (a mailbox or a site) can be previewed.</span></span> <span data-ttu-id="88d37-119">つまり、1,000 個未満のアイテムをプレビューできる可能性があるということです。</span><span class="sxs-lookup"><span data-stu-id="88d37-119">This means that it's possible that less than 1,000 items might be available for preview.</span></span> <span data-ttu-id="88d37-120">たとえば、4 つのメールボックスを検索して 1,500 件の推定値が返ってきた場合、各メール ボックスから 100 件しかプレビューできないため、400 件のみプレビュー可能になります。</span><span class="sxs-lookup"><span data-stu-id="88d37-120">For example, if you search four mailboxes and the search returns 1,500 estimated items, only 400 will be available for preview because only 100 items from each mailbox can be previewed.</span></span>

- <span data-ttu-id="88d37-121">メールボックス アイテムの場合、プレビューできるのはメールのメッセージのみです。</span><span class="sxs-lookup"><span data-stu-id="88d37-121">For mailbox items, only email messages are available to preview.</span></span> <span data-ttu-id="88d37-122">タスク、予定表のアイテム、連絡先などのアイテムは、プレビューできません。</span><span class="sxs-lookup"><span data-stu-id="88d37-122">Items like tasks, calendar items, and contacts can't be previewed.</span></span>

- <span data-ttu-id="88d37-123">サイト アイテムの場合は、ドキュメントのみプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="88d37-123">For site items, only documents are available to preview.</span></span> <span data-ttu-id="88d37-124">フォルダー、リスト、リストの添付ファイルなどのアイテムはプレビューできません。</span><span class="sxs-lookup"><span data-stu-id="88d37-124">Items like folders, lists, or list attachments can't be previewed.</span></span>

## <a name="file-types-supported-when-previewing-search-results"></a><span data-ttu-id="88d37-125">検索結果をプレビューする場合にサポートされるファイルの種類</span><span class="sxs-lookup"><span data-stu-id="88d37-125">File types supported when previewing search results</span></span>

<span data-ttu-id="88d37-126">サポートされているファイルの種類は、プレビュー ウィンドウでプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="88d37-126">You can preview supported file types in the preview pane.</span></span> <span data-ttu-id="88d37-127">サポートされていないファイルの種類の場合は、ファイルのコピーをローカル コンピューターにダウンロードする必要があります(**元のアイテムをダウンロード** をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="88d37-127">If a file type isn't supported, you have to download a copy of the file to your local computer (by clicking **Download original item**).</span></span> <span data-ttu-id="88d37-128">.aspx Web ページの場合、ページの URL が含まれていても、ページへのアクセス許可を持っていないことがあります。</span><span class="sxs-lookup"><span data-stu-id="88d37-128">For .aspx Web pages, the URL for the page is included though you may not have permissions to access the page.</span></span> <span data-ttu-id="88d37-129">インデックスのないアイテムはプレビュー表示できません。</span><span class="sxs-lookup"><span data-stu-id="88d37-129">Unindexed items aren't available for previewing.</span></span>

<span data-ttu-id="88d37-130">次のファイルの種類はサポートされており、検索結果ウィンドウでプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="88d37-130">The following file types are supported and can be previewed in the search results pane.</span></span>
  
- <span data-ttu-id="88d37-131">.txt、.html、.mhtml</span><span class="sxs-lookup"><span data-stu-id="88d37-131">.txt, .html, .mhtml</span></span>

- <span data-ttu-id="88d37-132">.eml</span><span class="sxs-lookup"><span data-stu-id="88d37-132">.eml</span></span>

- <span data-ttu-id="88d37-133">.doc、.docx、.docm</span><span class="sxs-lookup"><span data-stu-id="88d37-133">.doc, .docx, .docm</span></span>

- <span data-ttu-id="88d37-134">.pptm、.pptx</span><span class="sxs-lookup"><span data-stu-id="88d37-134">.pptm, .pptx</span></span>

- <span data-ttu-id="88d37-135">.pdf</span><span class="sxs-lookup"><span data-stu-id="88d37-135">.pdf</span></span>

<span data-ttu-id="88d37-p107">また、次のファイル コンテナーの種類もサポートされています。プレビュー ウィンドウでは、コンテナー内のファイルの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="88d37-p107">Also, the following file container types are supported. You can view the list of files in the container in the preview pane.</span></span>
  
- <span data-ttu-id="88d37-138">.zip</span><span class="sxs-lookup"><span data-stu-id="88d37-138">.zip</span></span>

- <span data-ttu-id="88d37-139">.gzip</span><span class="sxs-lookup"><span data-stu-id="88d37-139">.gzip</span></span>