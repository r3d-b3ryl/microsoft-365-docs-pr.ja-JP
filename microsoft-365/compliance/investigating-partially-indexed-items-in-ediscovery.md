---
title: 電子情報開示で部分的にインデックス付きアイテムを調査する
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
description: 部分的にインデックスが作成されたアイテム (インデックスのないアイテムとも呼ばれる) を、Exchange、SharePoint、OneDrive for Businessから管理する方法について学習します。
ms.openlocfilehash: 539fd2687735a5ee14be543750becca8c6c3154c
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311456"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="02132-103">電子情報開示で部分的にインデックス付きアイテムを調査する</span><span class="sxs-lookup"><span data-stu-id="02132-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="02132-104">コンプライアンス センターから実行する電子情報開示検索Microsoft 365、検索を実行すると、推定検索結果に部分的にインデックス付きアイテムが自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="02132-104">An eDiscovery search that you run from the Microsoft 365 compliance center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="02132-105">部分的にインデックス付けされたExchangeは、SharePoint サイトおよび OneDrive for Business サイト上のメールボックス アイテムとドキュメントに基OneDrive for Business で、何らかの理由で検索用に完全にインデックスが作成されたのではなかっています。</span><span class="sxs-lookup"><span data-stu-id="02132-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="02132-106">ほとんどの電子メール メッセージとサイト ドキュメントは、電子メール メッセージのインデックスの制限に含まれますので、インデックス作成 [に成功しています](limits-for-content-search.md#indexing-limits-for-email-messages)。</span><span class="sxs-lookup"><span data-stu-id="02132-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="02132-107">ただし、一部のアイテムは、これらのインデックスの制限を超える可能性があります。部分的にインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="02132-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="02132-108">電子情報開示検索を実行すると、アイテムを検索用にインデックス化できない理由と、部分的にインデックス付きアイテムとして返されるその他の理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="02132-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run an eDiscovery search:</span></span>
  
- <span data-ttu-id="02132-109">電子メール メッセージには、イメージ ファイルなどの有効なハンドラーのない添付ファイルがあります。これは、部分的にインデックスが作成された電子メール アイテムの最も一般的な原因です。</span><span class="sxs-lookup"><span data-stu-id="02132-109">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items.</span></span>

- <span data-ttu-id="02132-110">電子メール メッセージに添付されているファイルが多すぎます。</span><span class="sxs-lookup"><span data-stu-id="02132-110">Too many files attached to an email message.</span></span>

- <span data-ttu-id="02132-111">電子メール メッセージに添付されているファイルが大きすぎます。</span><span class="sxs-lookup"><span data-stu-id="02132-111">A file attached to an email message is too large.</span></span>

- <span data-ttu-id="02132-112">この種のファイルのインデックス付けはサポートされているが、特定のファイルでインデックス付けエラーが発生した。</span><span class="sxs-lookup"><span data-stu-id="02132-112">The file type is supported for indexing but an indexing error occurred for a specific file.</span></span>

<span data-ttu-id="02132-113">異なりますが、ほとんどの組織のお客様は、ボリュームごとに 1% 未満のコンテンツを持ち、部分的にインデックスが作成されたサイズでコンテンツの 12% 未満です。</span><span class="sxs-lookup"><span data-stu-id="02132-113">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="02132-114">ボリュームとサイズの違いは、ファイルが大きいほど、完全にインデックスを作成できないコンテンツを含む確率が高いからです。</span><span class="sxs-lookup"><span data-stu-id="02132-114">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="02132-115">部分的にインデックスが作成されたアイテム数が検索に対して変更される理由</span><span class="sxs-lookup"><span data-stu-id="02132-115">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="02132-116">電子情報開示検索を実行すると、検索された場所の部分的にインデックスが作成されたアイテムの総数とサイズが、検索の詳細な統計情報に表示される検索結果の統計情報に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="02132-116">After you run an eDiscovery search, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="02132-117">これらは、検索統計で  *インデックスのないアイテム*  と呼ばれる点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="02132-117">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="02132-118">検索結果で返される部分的にインデックス付きアイテムの数に影響を与えるいくつかの点を次に示します。</span><span class="sxs-lookup"><span data-stu-id="02132-118">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span>
  
- <span data-ttu-id="02132-119">アイテムが部分的にインデックス付けされ、検索クエリと一致する場合は、検索結果アイテムのカウント (およびサイズ) と部分的にインデックス付きアイテムの両方に含まれます。</span><span class="sxs-lookup"><span data-stu-id="02132-119">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="02132-120">ただし、同じ検索の結果がエクスポートされる場合、アイテムは一連の検索結果にのみ含まれます。部分的にインデックス付きアイテムとして含まれません。</span><span class="sxs-lookup"><span data-stu-id="02132-120">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>

- <span data-ttu-id="02132-121">SharePoint サイトと OneDrive サイトにある部分的にインデックス付きアイテムは、検索の詳細な統計情報に表示される部分的にインデックス付きアイテムの見積もりには含まれません。</span><span class="sxs-lookup"><span data-stu-id="02132-121">Partially indexed items located in SharePoint and OneDrive sites *are not* included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="02132-122">ただし、部分的にインデックスが作成されたアイテムは、電子情報開示検索の結果をエクスポートするときにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="02132-122">However, partially indexed items can be exported when you export the results of an eDiscovery search.</span></span> <span data-ttu-id="02132-123">たとえば、サイトのみを検索する場合、部分的にインデックスが作成されたアイテムの推定数は 0 になります。</span><span class="sxs-lookup"><span data-stu-id="02132-123">For example, if you only search sites, the estimated number partially indexed items will be zero.</span></span>
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="02132-124">組織内の部分的にインデックス付きアイテムの比率を計算する</span><span class="sxs-lookup"><span data-stu-id="02132-124">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="02132-125">部分的にインデックスが作成されたアイテムに対する組織の露出を理解するために、(空白のキーワード クエリを使用して) すべてのメールボックス内のすべてのコンテンツの検索を実行できます。</span><span class="sxs-lookup"><span data-stu-id="02132-125">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="02132-126">次の例では、1,629,904 (146.46 GB) の完全インデックス付きアイテムと 10,025 (10.27 GB) の部分的なインデックス付きアイテムがあります。</span><span class="sxs-lookup"><span data-stu-id="02132-126">In the following example, there are 1,629,904 (146.46 GB) fully indexed items and 10,025 (10.27 GB) partially indexed items.</span></span>
  
![部分的にインデックス付きアイテムを表示する検索統計の例](../media/PartiallyIndexedItemsTest.png)
  
<span data-ttu-id="02132-128">次の計算を使用して、部分的にインデックス付けされたアイテムの割合を決定できます。</span><span class="sxs-lookup"><span data-stu-id="02132-128">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="02132-129">**組織内の部分的にインデックス付きアイテムの比率を計算するには、次の方法を実行します。**</span><span class="sxs-lookup"><span data-stu-id="02132-129">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`

`(10025/1629904) x 100 = 0.62%`

<span data-ttu-id="02132-130">前の例の検索結果を使用すると、すべてのメールボックス アイテムの 0.62% が部分的にインデックス付けされます。</span><span class="sxs-lookup"><span data-stu-id="02132-130">By using the search results from the previous example, 0.62% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="02132-131">**組織内の部分的にインデックスが作成されたアイテムのサイズの割合を計算するには、次の方法を実行します。**</span><span class="sxs-lookup"><span data-stu-id="02132-131">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(10.27 GB/146.46 MB) x 100 = 7.0%`

<span data-ttu-id="02132-132">したがって、前の例では、メールボックス アイテムの合計サイズの 7% が部分的にインデックス付けされたアイテムからのサイズです。</span><span class="sxs-lookup"><span data-stu-id="02132-132">So in the previous example, 7% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="02132-133">前に述べたように、ほとんどの組織のお客様は、ボリューム別にコンテンツの 1% 未満、部分的にインデックスが作成されたサイズ別のコンテンツの 12% 未満を持っています。</span><span class="sxs-lookup"><span data-stu-id="02132-133">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="02132-134">部分的にインデックス付きアイテムを操作する</span><span class="sxs-lookup"><span data-stu-id="02132-134">Working with partially indexed items</span></span>

<span data-ttu-id="02132-135">部分的にアイテムを調べて、関連する情報が含まれているのを検証する必要がある場合は、部分的に[](export-a-content-search-report.md)インデックス付けされたアイテムに関する情報を含むコンテンツ検索レポートをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="02132-135">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="02132-136">コンテンツ検索レポートをエクスポートする場合は、部分的にインデックス付けされたアイテムを含むエクスポート オプションのいずれかを選択してください。</span><span class="sxs-lookup"><span data-stu-id="02132-136">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span>
  
![2 番目または 3 番目のオプションを選択して、部分的にインデックス付きアイテムをエクスポートする](../media/PartiallyIndexedItemsExportOptions.png)
  
<span data-ttu-id="02132-138">これらのオプションのいずれかを使用して電子情報開示検索結果または検索レポートをエクスポートする場合、エクスポートには Unindexed という名前のレポートが含Items.csv。</span><span class="sxs-lookup"><span data-stu-id="02132-138">When you export eDiscovery search results or a search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="02132-139">このレポートには、ファイルファイルと同じ情報のほとんどがResultsLog.csvされます。ただし、Unindexed Items.csv ファイルには、部分的にインデックス付けされたアイテムに関連する 2 つのフィールド ( **エラー** タグとエラー プロパティ) も **含まれています**。</span><span class="sxs-lookup"><span data-stu-id="02132-139">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="02132-140">これらのフィールドには、部分的にインデックスが作成された各アイテムのインデックスエラーに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="02132-140">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="02132-141">これら 2 つのフィールドの情報を使用すると、特定のインデックスエラーが調査に影響を与えるかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="02132-141">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="02132-142">その場合は、対象の検索を実行し、特定の電子メール メッセージと SharePoint または OneDrive ドキュメントを取得およびエクスポートして、調査に関連するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="02132-142">If it does, you can perform a targeted search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="02132-143">詳細な手順については、「ターゲット検索用に[CSV](csv-file-for-an-id-list-content-search.md)ファイルを準備する」を参照Office 365。</span><span class="sxs-lookup"><span data-stu-id="02132-143">For step-by-step instructions, see [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>

> [!NOTE]
> <span data-ttu-id="02132-144">Unindexed Items.csvファイルには、エラーの種類とエラー メッセージという **名前のフィールド** も **含まれています**。</span><span class="sxs-lookup"><span data-stu-id="02132-144">The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="02132-145">これらは、[エラー タグ] フィールドと [エラー プロパティ]フィールドの情報に似ていますが、詳細情報が少ない従来のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="02132-145">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="02132-146">これらの従来のフィールドは無視しても安全です。</span><span class="sxs-lookup"><span data-stu-id="02132-146">You can safely ignore these legacy fields.</span></span>
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="02132-147">部分的にインデックス付けされたアイテムに関連するエラー</span><span class="sxs-lookup"><span data-stu-id="02132-147">Errors related to partially indexed items</span></span>

<span data-ttu-id="02132-148">エラー タグは、エラーとファイルの種類という 2 つの情報からなります。</span><span class="sxs-lookup"><span data-stu-id="02132-148">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="02132-149">たとえば、このエラー/ファイルの種類のペアでは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="02132-149">For example, in this error/file-type pair:</span></span>

```text
 parseroutputsize_xls
```

 <span data-ttu-id="02132-150">`parseroutputsize` はエラーであり `xls` 、エラーが発生したファイルのファイルの種類です。</span><span class="sxs-lookup"><span data-stu-id="02132-150">`parseroutputsize` is the error and `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="02132-151">ファイルの種類が認識されない場合、またはファイルの種類がエラーに適用されない場合は、ファイルの種類の代わりの値 `noformat` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02132-151">In cases where the file type wasn't recognized or the file type didn't apply to the error, you will see the value `noformat` in place of the file type.</span></span>
  
<span data-ttu-id="02132-152">インデックス作成エラーの一覧と、エラーの考えられる原因の説明を次に示します。</span><span class="sxs-lookup"><span data-stu-id="02132-152">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
| <span data-ttu-id="02132-153">エラー タグ</span><span class="sxs-lookup"><span data-stu-id="02132-153">Error tag</span></span> | <span data-ttu-id="02132-154">説明</span><span class="sxs-lookup"><span data-stu-id="02132-154">Description</span></span> |
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="02132-155">電子メール メッセージの添付ファイルが多すぎて、これらの添付ファイルの一部が処理されません。</span><span class="sxs-lookup"><span data-stu-id="02132-155">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="02132-156">コンテンツレトリバーとドキュメント パーサーは、他の添付ファイル内に入れ子になった添付ファイルのレベルが多すぎます。</span><span class="sxs-lookup"><span data-stu-id="02132-156">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="02132-157">これらの添付ファイルの一部は処理されません。</span><span class="sxs-lookup"><span data-stu-id="02132-157">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="02132-158">添付ファイルは RMS で保護されたため、デコードに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="02132-158">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="02132-159">電子メール メッセージに添付されたファイルが大きすぎて処理できなかった。</span><span class="sxs-lookup"><span data-stu-id="02132-159">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="02132-160">処理された電子メール メッセージをインデックスに書き込む場合、インデックス可能なプロパティの 1 つが大きすぎて切り捨てられていました。</span><span class="sxs-lookup"><span data-stu-id="02132-160">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="02132-161">切り捨てられたプロパティは、[エラーのプロパティ] フィールドに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="02132-161">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="02132-162">電子メール メッセージには、有効な Unicode として処理できなかったテキストが含まれる。</span><span class="sxs-lookup"><span data-stu-id="02132-162">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="02132-163">このアイテムのインデックス作成が不完全な場合があります。</span><span class="sxs-lookup"><span data-stu-id="02132-163">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="02132-164">添付ファイルまたは電子メール メッセージの内容が暗号化され、Microsoft 365デコードできなかった場合。</span><span class="sxs-lookup"><span data-stu-id="02132-164">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="02132-165">解析中に不明なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="02132-165">An unknown error occurred during parsing.</span></span> <span data-ttu-id="02132-166">これは通常、ソフトウェアのバグやサービスのクラッシュによって発生します。</span><span class="sxs-lookup"><span data-stu-id="02132-166">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="02132-167">添付ファイルが大きすぎてパーサーが処理できないので、その添付ファイルの解析が発生しなかったか、完了しなかった。</span><span class="sxs-lookup"><span data-stu-id="02132-167">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="02132-168">添付ファイルの形式が正しくなって、パーサーで処理できなかった。</span><span class="sxs-lookup"><span data-stu-id="02132-168">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="02132-169">この結果は、古いファイル形式、互換性のないソフトウェアによって作成されたファイル、またはクレーム以外のふりをするウイルスが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="02132-169">This result can be due to old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="02132-170">添付ファイルの解析からの出力が大きすぎて、切り捨てる必要がありました。</span><span class="sxs-lookup"><span data-stu-id="02132-170">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="02132-171">添付ファイルには、ファイルの種類Microsoft 365検出できなかった。</span><span class="sxs-lookup"><span data-stu-id="02132-171">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="02132-172">添付ファイルにはファイルの種類Office 365検出できますが、そのファイルの種類の解析はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="02132-172">An attachment had a file type that Office 365 could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="02132-173">ストア内の email プロパティのExchangeが大きすぎて取得できなかったので、メッセージを処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="02132-173">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="02132-174">これは通常、電子メール メッセージの body プロパティにのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="02132-174">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="02132-175">コンテンツレトリバーが RMS で保護されたメッセージをデコードできなかった。</span><span class="sxs-lookup"><span data-stu-id="02132-175">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="02132-176">インデックス作成中にドキュメント内で識別された単語が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="02132-176">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="02132-177">制限に達すると、プロパティの処理が停止し、プロパティが切り詰めされます。</span><span class="sxs-lookup"><span data-stu-id="02132-177">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |

<span data-ttu-id="02132-178">エラー フィールドは、[エラー タグ] フィールドに表示される処理エラーの影響を受けるフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="02132-178">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="02132-179">メッセージ本文のエラーなどのプロパティを検索しても、検索結果には  `subject`  `participants` 影響しません。</span><span class="sxs-lookup"><span data-stu-id="02132-179">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="02132-180">これは、詳細に調査する必要がある可能性がある部分的にインデックス付けされたアイテムを正確に決定する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="02132-180">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="02132-181">PowerShell スクリプトを使用して、部分的にインデックスが作成された電子メール アイテムへの組織の露出を特定する</span><span class="sxs-lookup"><span data-stu-id="02132-181">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="02132-182">次の手順では、すべての Exchange メールボックス内のすべてのアイテムを検索し、部分的にインデックス付けされた電子メール アイテムの組織の比率 (カウントとサイズ別) に関するレポートを生成し、発生するインデックスエラーごとにアイテムの数 (とそのファイルの種類) を表示する PowerShell スクリプトを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="02132-182">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="02132-183">前のセクションのエラー タグの説明を使用して、インデックスエラーを特定します。</span><span class="sxs-lookup"><span data-stu-id="02132-183">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="02132-184">ファイル名のサフィックスを使用してWindows PowerShellスクリプト ファイルに次のテキストを保存.ps1。たとえば、 `PartiallyIndexedItems.ps1` .</span><span class="sxs-lookup"><span data-stu-id="02132-184">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

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

2. <span data-ttu-id="02132-185">[セキュリティ/コンプライアンス センターの PowerShell に接続する](/powershell/exchange/exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="02132-185">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

3. <span data-ttu-id="02132-186">[セキュリティ & コンプライアンス センター PowerShell] で、手順 1 でスクリプトを保存したフォルダーに移動し、スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="02132-186">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

   ```powershell
   .\PartiallyIndexedItems.ps1
   ```

<span data-ttu-id="02132-187">スクリプトから返される出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="02132-187">Here's an example fo the output returned by the script.</span></span>
  
![部分的にインデックスが作成された電子メール アイテムへの組織の露出に関するレポートを生成するスクリプトからの出力の例](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)

> [!NOTE]
> <span data-ttu-id="02132-189">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="02132-189">Note the following:</span></span>
>  
> - <span data-ttu-id="02132-190">電子メール アイテムの総数とサイズ、および部分的にインデックスが作成された電子メール アイテムの組織の比率 (カウントとサイズ別)。</span><span class="sxs-lookup"><span data-stu-id="02132-190">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size).</span></span>
> 
> - <span data-ttu-id="02132-191">リスト エラー タグと、エラーが発生した対応するファイルの種類。</span><span class="sxs-lookup"><span data-stu-id="02132-191">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="02132-192">関連項目</span><span class="sxs-lookup"><span data-stu-id="02132-192">See also</span></span>

[<span data-ttu-id="02132-193">電子情報開示の部分的にインデックス付きアイテム</span><span class="sxs-lookup"><span data-stu-id="02132-193">Partially indexed items in eDiscovery</span></span>](partially-indexed-items-in-content-search.md)