---
title: 電子情報開示で部分的にインデックスが作成されたアイテムの調査
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: 部分的にインデックスが作成されたアイテム (インデックスのないアイテムとも呼ばれる) を組織内の Exchange、SharePoint、OneDrive for Business から管理する方法について説明します。
ms.openlocfilehash: 6a2a1d042c52a445538903fd7db9fc54305e6c13
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655451"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="57aa5-103">電子情報開示で部分的にインデックスが作成されたアイテムの調査</span><span class="sxs-lookup"><span data-stu-id="57aa5-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="57aa5-104">Microsoft 365 コンプライアンス センターから実行する電子情報開示検索では、検索を実行すると、部分的にインデックスが作成されたアイテムが推定検索結果に自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-104">An eDiscovery search that you run from the Microsoft 365 compliance center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="57aa5-105">部分的にインデックスが作成されたアイテムは、何らかの理由で検索用に完全にはインデックスが作成されなかった SharePoint および OneDrive for Business サイト上の Exchange メールボックス アイテムとドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="57aa5-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="57aa5-106">ほとんどの電子メール メッセージとサイト ドキュメントは、電子メール メッセージのインデックス作成の制限に含むため、正常にインデックス [が作成されます](limits-for-content-search.md#indexing-limits-for-email-messages)。</span><span class="sxs-lookup"><span data-stu-id="57aa5-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="57aa5-107">ただし、一部のアイテムは、これらのインデックス作成の制限を超え、部分的にインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="57aa5-108">電子情報開示検索を実行すると、アイテムを検索用にインデックス付けできない他の理由と、部分的にインデックスが作成されたアイテムとして返される理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="57aa5-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run an eDiscovery search:</span></span>
  
- <span data-ttu-id="57aa5-109">電子メール メッセージには、イメージ ファイルなどの有効なハンドラーのない添付ファイルがあります。これは、部分的にインデックスが作成された電子メール アイテムの最も一般的な原因です。</span><span class="sxs-lookup"><span data-stu-id="57aa5-109">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items.</span></span>

- <span data-ttu-id="57aa5-110">電子メール メッセージに添付されているファイルが多すぎます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-110">Too many files attached to an email message.</span></span>

- <span data-ttu-id="57aa5-111">電子メール メッセージに添付されているファイルが大きすぎます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-111">A file attached to an email message is too large.</span></span>

- <span data-ttu-id="57aa5-112">この種のファイルのインデックス付けはサポートされているが、特定のファイルでインデックス付けエラーが発生した。</span><span class="sxs-lookup"><span data-stu-id="57aa5-112">The file type is supported for indexing but an indexing error occurred for a specific file.</span></span>

<span data-ttu-id="57aa5-113">規模は異なりますが、大部分の組織のお客様は、コンテンツのボリュームが 1% 未満で、部分的にインデックスが作成されるコンテンツのサイズが 12% 未満です。</span><span class="sxs-lookup"><span data-stu-id="57aa5-113">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="57aa5-114">ボリュームとサイズの違いは、サイズが大きいファイルの方が、完全にインデックスを作成できないコンテンツを含む可能性が高いからです。</span><span class="sxs-lookup"><span data-stu-id="57aa5-114">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="57aa5-115">部分的にインデックスが作成されたアイテムの数が検索で変更される理由</span><span class="sxs-lookup"><span data-stu-id="57aa5-115">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="57aa5-116">電子情報開示検索を実行すると、検索された場所にある部分的にインデックスが作成されたアイテムの総数とサイズが、検索の詳細な統計情報に表示される検索結果の統計情報に表示されます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-116">After you run an eDiscovery search, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="57aa5-117">これらは、検索統計では  *インデックスのないアイテム*  と呼ばれる点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="57aa5-117">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="57aa5-118">検索結果で返される部分的にインデックスが作成されたアイテムの数に影響を与えるいくつかの点を次に示します。</span><span class="sxs-lookup"><span data-stu-id="57aa5-118">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span>
  
- <span data-ttu-id="57aa5-119">アイテムが部分的にインデックス付けされ、検索クエリに一致する場合は、検索結果アイテムのカウント (およびサイズ) と部分的にインデックスが作成されたアイテムの両方に含まれます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-119">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="57aa5-120">ただし、同じ検索の結果がエクスポートされる場合、アイテムは検索結果のセットにのみ含まれます。部分的にインデックスが作成されたアイテムには含まれません。</span><span class="sxs-lookup"><span data-stu-id="57aa5-120">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>

- <span data-ttu-id="57aa5-121">(キーワード クエリに含めるか、条件を使用して) 検索クエリの日付範囲を指定した場合、日付範囲と一致しない部分的にインデックスが作成されたアイテムは、部分的にインデックスが作成されたアイテムの数には含まれません。</span><span class="sxs-lookup"><span data-stu-id="57aa5-121">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items.</span></span> <span data-ttu-id="57aa5-122">日付範囲内にある部分的にインデックスが作成されたアイテムは、インデックス付きアイテムの数に含まれます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-122">Partially indexed items that fall within date range are included in the count of indexed items.</span></span>

  > [!NOTE]
  > <span data-ttu-id="57aa5-123">SharePoint および OneDrive サイトにある部分的にインデックスが作成されたアイテムは、検索の詳細な統計情報に表示される部分的にインデックスが作成されたアイテムの推定には含まれません。</span><span class="sxs-lookup"><span data-stu-id="57aa5-123">Partially indexed items located in SharePoint and OneDrive sites *are not* included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="57aa5-124">ただし、部分的にインデックスが作成されたアイテムは、電子情報開示検索の結果をエクスポートするときにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-124">However, partially indexed items can be exported when you export the results of an eDiscovery search.</span></span> <span data-ttu-id="57aa5-125">たとえば、サイトのみを検索する場合、部分的にインデックスが作成されたアイテムの推定数は 0 になります。</span><span class="sxs-lookup"><span data-stu-id="57aa5-125">For example, if you only search sites, the estimated number partially indexed items will be zero.</span></span>
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="57aa5-126">組織内の部分的にインデックスが作成されたアイテムの比率の計算</span><span class="sxs-lookup"><span data-stu-id="57aa5-126">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="57aa5-127">部分的にインデックスが作成されたアイテムに対する組織の露出を理解するために、(空白のキーワード クエリを使用して) すべてのメールボックス内のすべてのコンテンツの検索を実行できます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-127">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="57aa5-128">次の例では、完全にインデックスが作成されたアイテムは 56,208 (4,830 MB)、部分的にインデックスが作成されたアイテムは 470 (316 MB) です。</span><span class="sxs-lookup"><span data-stu-id="57aa5-128">In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![部分的にインデックスが作成されたアイテムを示す検索統計の例](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="57aa5-130">次の計算を使用して、部分的にインデックスが作成されたアイテムの割合を確認できます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-130">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="57aa5-131">**組織内の部分的にインデックスが作成されたアイテムの比率を計算するには、次の式を使用します。**</span><span class="sxs-lookup"><span data-stu-id="57aa5-131">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`

`(470/56,208) x 100 = 0.84%`

<span data-ttu-id="57aa5-132">前の例の検索結果を使用すると、すべてのメールボックス アイテムの 0.84% が部分的にインデックス付けされます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-132">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="57aa5-133">**組織内の部分的にインデックスが作成されたアイテムのサイズの割合を計算するには、次の式を使用します。**</span><span class="sxs-lookup"><span data-stu-id="57aa5-133">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="57aa5-134">そのため、前の例では、メールボックス アイテムの合計サイズの 6.54% が部分的にインデックスが作成されたアイテムのサイズです。</span><span class="sxs-lookup"><span data-stu-id="57aa5-134">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="57aa5-135">前に説明したように、ほとんどの組織のお客様は、コンテンツのボリュームが 1% 未満で、部分的にインデックスが作成されたコンテンツのサイズが 12% 未満です。</span><span class="sxs-lookup"><span data-stu-id="57aa5-135">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="57aa5-136">部分的にインデックスが作成されたアイテムを操作する</span><span class="sxs-lookup"><span data-stu-id="57aa5-136">Working with partially indexed items</span></span>

<span data-ttu-id="57aa5-137">部分的にアイテムを調べて、関連情報が含まれているのを確認する必要がある場合は、部分的にインデックス[](export-a-content-search-report.md)が作成されたアイテムに関する情報を含むコンテンツ検索レポートをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-137">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="57aa5-138">コンテンツ検索レポートをエクスポートする場合は、部分的にインデックスが作成されたアイテムを含むエクスポート オプションのいずれかを選択してください。</span><span class="sxs-lookup"><span data-stu-id="57aa5-138">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span>
  
![部分的にインデックスが作成されたアイテムをエクスポートする 2 番目または 3 番目のオプションを選択する](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="57aa5-140">これらのオプションのいずれかを使用して電子情報開示検索結果または検索レポートをエクスポートする場合、エクスポートには Unindexed という名前のレポートがItems.csv。</span><span class="sxs-lookup"><span data-stu-id="57aa5-140">When you export eDiscovery search results or a search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="57aa5-141">このレポートには、このファイルと同じ情報の大部分がResultsLog.csvされます。ただし、インデックス付きItems.csvファイルには、部分的にインデックスが作成されたアイテムに関連するエラー タグとエラー プロパティの 2 つのフィールドも **含まれています**。</span><span class="sxs-lookup"><span data-stu-id="57aa5-141">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="57aa5-142">これらのフィールドには、部分的にインデックスが作成された各アイテムのインデックス作成エラーに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-142">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="57aa5-143">これら 2 つのフィールドの情報を使用すると、特定のインデックス作成エラーが調査に影響を与えるかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-143">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="57aa5-144">その場合は、対象を絞った検索を実行し、特定の電子メール メッセージと SharePoint または OneDrive ドキュメントを取得およびエクスポートして、調査に関連したかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-144">If it does, you can perform a targeted search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="57aa5-145">詳しい手順については、「Office [365](csv-file-for-an-id-list-content-search.md)でターゲット検索用の CSV ファイルを準備する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57aa5-145">For step-by-step instructions, see [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>

> [!NOTE]
> <span data-ttu-id="57aa5-146">Unindexed Items.csvファイルには、エラーの種類とエラー メッセージという **名前の** フィールド **も含まれています**。</span><span class="sxs-lookup"><span data-stu-id="57aa5-146">The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="57aa5-147">これらは、[エラー タグ] フィールドと [エラー プロパティ]フィールドの情報に似た情報を含み、より詳細な情報を含むレガシ フィールドです。</span><span class="sxs-lookup"><span data-stu-id="57aa5-147">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="57aa5-148">これらの従来のフィールドは無視しても問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="57aa5-148">You can safely ignore these legacy fields.</span></span>
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="57aa5-149">部分的にインデックスが作成されたアイテムに関連するエラー</span><span class="sxs-lookup"><span data-stu-id="57aa5-149">Errors related to partially indexed items</span></span>

<span data-ttu-id="57aa5-150">エラー タグは、エラーとファイルの種類の 2 つの情報からなります。</span><span class="sxs-lookup"><span data-stu-id="57aa5-150">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="57aa5-151">たとえば、このエラー/ファイルの種類のペアでは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="57aa5-151">For example, in this error/file-type pair:</span></span>

```text
 parseroutputsize_xls
```

 <span data-ttu-id="57aa5-152">`parseroutputsize` はエラーであり `xls` 、エラーが発生したファイルのファイルの種類です。</span><span class="sxs-lookup"><span data-stu-id="57aa5-152">`parseroutputsize` is the error and `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="57aa5-153">ファイルの種類が認識されない場合や、ファイルの種類がエラーに適用されない場合は、ファイルの種類の代わりの値 `noformat` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-153">In cases where the file type wasn't recognized or the file type didn't apply to the error, you will see the value `noformat` in place of the file type.</span></span>
  
<span data-ttu-id="57aa5-154">インデックス作成エラーの一覧と、エラーの考えられる原因の説明を次に示します。</span><span class="sxs-lookup"><span data-stu-id="57aa5-154">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
| <span data-ttu-id="57aa5-155">エラー タグ</span><span class="sxs-lookup"><span data-stu-id="57aa5-155">Error tag</span></span> | <span data-ttu-id="57aa5-156">内容</span><span class="sxs-lookup"><span data-stu-id="57aa5-156">Description</span></span> |
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="57aa5-157">電子メール メッセージの添付ファイルが多すぎるので、これらの添付ファイルの一部は処理されません。</span><span class="sxs-lookup"><span data-stu-id="57aa5-157">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="57aa5-158">コンテンツ取得機能とドキュメント パーサーは、他の添付ファイル内に入れ子になった添付ファイルのレベルが多すぎます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-158">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="57aa5-159">これらの添付ファイルの一部は処理されません。</span><span class="sxs-lookup"><span data-stu-id="57aa5-159">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="57aa5-160">添付ファイルは RMS で保護されたため、デコードに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="57aa5-160">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="57aa5-161">電子メール メッセージに添付されたファイルが大きすぎて処理できなかった。</span><span class="sxs-lookup"><span data-stu-id="57aa5-161">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="57aa5-162">処理された電子メール メッセージをインデックスに書き込むときに、インデックス可能なプロパティの 1 つが大きすぎて切り詰められていました。</span><span class="sxs-lookup"><span data-stu-id="57aa5-162">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="57aa5-163">切り捨てられたプロパティは、[エラーのプロパティ] フィールドに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-163">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="57aa5-164">電子メール メッセージに、有効な Unicode として処理できなかったテキストが含まれている。</span><span class="sxs-lookup"><span data-stu-id="57aa5-164">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="57aa5-165">このアイテムのインデックス作成が不完全な場合があります。</span><span class="sxs-lookup"><span data-stu-id="57aa5-165">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="57aa5-166">添付ファイルまたは電子メール メッセージのコンテンツは暗号化され、Microsoft 365 はコンテンツをデコードできなかった。</span><span class="sxs-lookup"><span data-stu-id="57aa5-166">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="57aa5-167">解析中に不明なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="57aa5-167">An unknown error occurred during parsing.</span></span> <span data-ttu-id="57aa5-168">これは通常、ソフトウェアのバグやサービスのクラッシュによって発生します。</span><span class="sxs-lookup"><span data-stu-id="57aa5-168">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="57aa5-169">添付ファイルが大きすぎてパーサーが処理できないので、その添付ファイルの解析が行えなかったか、完了しなかった。</span><span class="sxs-lookup"><span data-stu-id="57aa5-169">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="57aa5-170">添付ファイルの形式が正しくなかったので、パーサーが処理できなかった。</span><span class="sxs-lookup"><span data-stu-id="57aa5-170">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="57aa5-171">この結果は、古いファイル形式、互換性のないソフトウェアによって作成されたファイル、またはクレーム以外のファイルを名用するウイルスが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="57aa5-171">This result can be due to old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="57aa5-172">添付ファイルの解析からの出力が大きすぎるので、切り捨てる必要がありました。</span><span class="sxs-lookup"><span data-stu-id="57aa5-172">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="57aa5-173">添付ファイルのファイルの種類が Microsoft 365 で検出できなかった。</span><span class="sxs-lookup"><span data-stu-id="57aa5-173">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="57aa5-174">添付ファイルのファイルの種類は 365 Office検出できますが、そのファイルの種類の解析はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="57aa5-174">An attachment had a file type that Office 365 could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="57aa5-175">Exchange ストアの電子メール プロパティの値が大きすぎて取得できなかったので、メッセージを処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="57aa5-175">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="57aa5-176">これは通常、電子メール メッセージの body プロパティにのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="57aa5-176">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="57aa5-177">コンテンツ取得者は、RMS で保護されたメッセージのデコードに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="57aa5-177">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="57aa5-178">インデックス作成中にドキュメント内で識別された単語が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-178">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="57aa5-179">制限値に達するとプロパティの処理が停止し、プロパティは切り捨てらされます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-179">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |

<span data-ttu-id="57aa5-180">エラー フィールドは、[エラー タグ] フィールドに表示される処理エラーの影響を受けるフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="57aa5-180">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="57aa5-181">If you're searching a property such as  `subject` or , errors in the body of the message  `participants` won't impact the results of your search.</span><span class="sxs-lookup"><span data-stu-id="57aa5-181">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="57aa5-182">これは、詳細な調査が必要になる可能性がある部分的にインデックスが作成されたアイテムを正確に判断する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="57aa5-182">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="57aa5-183">PowerShell スクリプトを使用して、部分的にインデックスが作成された電子メール アイテムに対する組織の露出を特定する</span><span class="sxs-lookup"><span data-stu-id="57aa5-183">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="57aa5-184">次の手順では、すべての Exchange メールボックス内のすべてのアイテムを検索し、部分的にインデックスが作成された電子メール アイテムの組織の比率に関するレポートを (カウントおよびサイズ別に) 生成し、発生するインデックス作成エラーごとにアイテム数 (およびファイルの種類) を表示する PowerShell スクリプトを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="57aa5-184">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="57aa5-185">前のセクションのエラー タグの説明を使用して、インデックス作成エラーを特定します。</span><span class="sxs-lookup"><span data-stu-id="57aa5-185">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="57aa5-186">ファイル名サフィックス .ps1 を使用Windows PowerShellスクリプト ファイルに次のテキストを保存します。たとえば、 `PartiallyIndexedItems.ps1` .</span><span class="sxs-lookup"><span data-stu-id="57aa5-186">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

   ```powershell
     write-host "**************************************************"
     write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
     write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
     write-host "**************************************************"
     " " 
     # Create a search with Error Tags Refinders enabled
     Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
     New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
     Start-ComplianceSearch "RefinerTest"
     # Loop while search is in progress
     do{
         Write-host "Waiting for search to complete..."
         Start-Sleep -s 5
         $complianceSearch = Get-ComplianceSearch "RefinerTest"
     }while ($complianceSearch.Status -ne 'Completed')
     $refiners = $complianceSearch.Refiners | ConvertFrom-Json
     $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
     $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
     $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
     " "
     "===== Partially indexed items ====="
     "         Total          Ratio"
     "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
     "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
     " "
     Write-Host ===== Reasons for partially indexed items =====
     foreach($errorTagProperty in $errorTagProperties)
     {
         $name = $refiners.Entries.($errorTagProperty.Name).Name
         $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
         $frag = $name.Split("{_}")
         $errorTag = $frag[0]
         $fileType = $frag[1]
         if ($errorTag -ne $lastErrorTag)
         {
             $errorTag
         }
         "    " + $fileType + " => " + $count
         $lastErrorTag = $errorTag
     }
   ```

2. <span data-ttu-id="57aa5-187">[セキュリティ/コンプライアンス センター PowerShell に接続します](https://go.microsoft.com/fwlink/p/?linkid=627084)。</span><span class="sxs-lookup"><span data-stu-id="57aa5-187">[Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>

3. <span data-ttu-id="57aa5-188">セキュリティ センター & コンプライアンス センターの PowerShell で、手順 1 でスクリプトを保存したフォルダーに移動し、スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="57aa5-188">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

   ```powershell
   .\PartiallyIndexedItems.ps1
   ```

<span data-ttu-id="57aa5-189">スクリプトによって返される出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="57aa5-189">Here's an example fo the output returned by the script.</span></span>
  
![部分的にインデックスが作成された電子メール アイテムに対する組織の露出に関するレポートを生成するスクリプトからの出力の例](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)

> [!NOTE]
> <span data-ttu-id="57aa5-191">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="57aa5-191">Note the following:</span></span>
>  
> - <span data-ttu-id="57aa5-192">メール アイテムの総数とサイズ、および部分的にインデックスが作成された電子メール アイテムに対する組織の比率 (カウントおよびサイズ別)。</span><span class="sxs-lookup"><span data-stu-id="57aa5-192">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size).</span></span>
> 
> - <span data-ttu-id="57aa5-193">エラーが発生したリスト エラー タグと対応するファイルの種類。</span><span class="sxs-lookup"><span data-stu-id="57aa5-193">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="57aa5-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="57aa5-194">See also</span></span>

[<span data-ttu-id="57aa5-195">電子情報開示の部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="57aa5-195">Partially indexed items in eDiscovery</span></span>](partially-indexed-items-in-content-search.md)
