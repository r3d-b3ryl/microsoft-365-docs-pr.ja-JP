---
title: 電子情報開示での部分的にインデックスが作成されたアイテムの調査
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
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
description: 組織内の Exchange、SharePoint、および OneDrive から、部分的にインデックス化 (またはインデックスを作成) されたアイテムを管理する方法について説明します。
ms.openlocfilehash: 4c2da954316450e22f481f1a5093077be79cc67e
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357379"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="f4751-103">電子情報開示での部分的にインデックスが作成されたアイテムの調査</span><span class="sxs-lookup"><span data-stu-id="f4751-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="f4751-104">セキュリティ & コンプライアンスセンターから実行するコンテンツ検索では、検索を実行すると、予想される検索結果に、部分的にインデックスが作成されたアイテムが自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4751-104">A Content Search that you run from the Security & Compliance Center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="f4751-105">部分的にインデックスが作成されたアイテムは、何らかの理由で検索用に完全にインデックス付けされていなかった SharePoint および OneDrive for business サイトの Exchange メールボックスアイテムとドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="f4751-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="f4751-106">ほとんどの電子メールメッセージとサイトドキュメントは、 [電子メールメッセージのインデックス付けの制限](limits-for-content-search.md#indexing-limits-for-email-messages)の範囲内にあるため、正常にインデックス付けされます。</span><span class="sxs-lookup"><span data-stu-id="f4751-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="f4751-107">ただし、アイテムによっては、これらのインデックスの制限を超えている場合があり、部分的にインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f4751-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="f4751-108">コンテンツ検索を実行するときに、アイテムが検索用にインデックス付けされず、部分的にインデックスが付けられたアイテムとして返されるその他の理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f4751-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run a Content Search:</span></span>
  
- <span data-ttu-id="f4751-109">電子メールメッセージには、インデックスを作成できないファイルの種類の添付ファイルがあります。ほとんどの場合、ファイルの種類が認識されない[か、インデックス処理がサポート](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)されていません。</span><span class="sxs-lookup"><span data-stu-id="f4751-109">Email messages have an attached file of a file type that can't be indexed; in most cases, the file type is [unrecognized or unsupported for indexing](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span></span>
    
- <span data-ttu-id="f4751-110">電子メールメッセージには、有効なハンドラー (画像ファイルなど) のない添付ファイルがあります。これは、部分的にインデックスが作成された電子メールアイテムの最も一般的な原因です。</span><span class="sxs-lookup"><span data-stu-id="f4751-110">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items</span></span>
    
- <span data-ttu-id="f4751-111">電子メールメッセージに添付されたファイルが多すぎます</span><span class="sxs-lookup"><span data-stu-id="f4751-111">Too many files attached to an email message</span></span>
    
- <span data-ttu-id="f4751-112">電子メールメッセージに添付されたファイルが大きすぎます</span><span class="sxs-lookup"><span data-stu-id="f4751-112">A file attached to an email message is too large</span></span>
    
- <span data-ttu-id="f4751-113">このファイルの種類はインデックス作成に対してサポートされていますが、特定のファイルに対してインデックス作成エラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="f4751-113">The file type is supported for indexing but an indexing error occurred for a specific file</span></span>
    
<span data-ttu-id="f4751-114">多くの組織では変化はありませんが、大部分の組織では、ボリュームごとにコンテンツの数が1% 未満で、部分的なインデックスが作成されたサイズによるコンテンツの12% 未満です。</span><span class="sxs-lookup"><span data-stu-id="f4751-114">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="f4751-115">ボリュームとサイズの違いがあるのは、コンテンツを完全にインデックス処理できない可能性が高いファイルの方が大きいためです。</span><span class="sxs-lookup"><span data-stu-id="f4751-115">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="f4751-116">検索によって、部分的にインデックス付けされたアイテム数が変化するのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="f4751-116">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="f4751-117">セキュリティ & コンプライアンスセンターでコンテンツ検索を実行すると、検索の詳細な統計情報に表示される検索結果の統計に、検索された場所に含まれる部分的なインデックスアイテムの合計数とサイズが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4751-117">After you run a Content Search in the Security & Compliance Center, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="f4751-118">メモこれらは、検索統計ではインデックスのない  *アイテム*  と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f4751-118">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="f4751-119">検索結果で返される、部分的にインデックスが作成されたアイテムの数に影響を与えるいくつかの点を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="f4751-119">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span> 
  
- <span data-ttu-id="f4751-120">アイテムが部分的にインデックス処理され、検索クエリと一致する場合は、検索結果アイテムの数 (およびサイズ) と、部分的にインデックスが作成されたアイテムの両方に含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4751-120">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="f4751-121">ただし、同じ検索結果がエクスポートされると、アイテムは一連の検索結果にのみ含まれます。部分的にインデックスが作成されたアイテムとして含まれていません。</span><span class="sxs-lookup"><span data-stu-id="f4751-121">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>
    
- <span data-ttu-id="f4751-122">検索クエリに日付範囲を指定した場合 (キーワードクエリに含めるか、条件を使用して)、その日付範囲に一致しない部分的なインデックスアイテムは、部分的にインデックスが作成されたアイテムのカウントに含まれません。</span><span class="sxs-lookup"><span data-stu-id="f4751-122">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items.</span></span> <span data-ttu-id="f4751-123">部分的にインデックスが作成されたアイテムのみが、日付範囲内にある場合、インデックスが作成されたアイテムのカウントに含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4751-123">Only the partially indexed items that fall within date range are included in the count of partially indexed items.</span></span>
    
 <span data-ttu-id="f4751-124">**注:** SharePoint および OneDrive サイトにある、部分的にインデックスが作成されたアイテムは、検索の詳細な統計情報に表示される、部分的にインデックスが作成されたアイテムの推定に含まれて  *いません*  。</span><span class="sxs-lookup"><span data-stu-id="f4751-124">**Note:** Partially indexed items located in SharePoint and OneDrive sites  *are not*  included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="f4751-125">ただし、コンテンツ検索の結果をエクスポートする場合は、部分的にインデックスが作成されたアイテムをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="f4751-125">However, partially indexed items can be exported when you export the results of a Content Search.</span></span> <span data-ttu-id="f4751-126">たとえば、コンテンツ検索でサイトのみを検索した場合は、推定数が部分的にインデックス付けされたアイテムは0になります。</span><span class="sxs-lookup"><span data-stu-id="f4751-126">For example, if you only search sites in a Content Search, the estimated number partially indexed items will be zero.</span></span> 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="f4751-127">組織内の部分的にインデックスが作成されたアイテムの比率を計算する</span><span class="sxs-lookup"><span data-stu-id="f4751-127">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="f4751-128">部分的にインデックスが作成されたアイテムに対する組織の影響を理解するには、すべてのメールボックス内のすべてのコンテンツについて検索を実行します (空白のキーワードクエリを使用)。</span><span class="sxs-lookup"><span data-stu-id="f4751-128">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="f4751-129">次の例では、56208 (4830 MB) の完全にインデックスが作成されたアイテムと、470 (316 MB) の一部のインデックスアイテムがあります。</span><span class="sxs-lookup"><span data-stu-id="f4751-129">In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![部分的にインデックスが作成されたアイテムを示す検索統計の例](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="f4751-131">次の計算を使用して、部分的にインデックスが作成されたアイテムのパーセンテージを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="f4751-131">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="f4751-132">**組織内で部分的にインデックスが作成されたアイテムの比率を計算するには、次のようにします。**</span><span class="sxs-lookup"><span data-stu-id="f4751-132">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
<span data-ttu-id="f4751-133">前の例からの検索結果を使用して、すべてのメールボックスアイテムの84% が部分的にインデックス処理されます。</span><span class="sxs-lookup"><span data-stu-id="f4751-133">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="f4751-134">**組織内で部分的にインデックス付けされたアイテムのサイズの割合を計算するには、次のようにします。**</span><span class="sxs-lookup"><span data-stu-id="f4751-134">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="f4751-135">そのため、前の例では、メールボックスアイテムの合計サイズの6.54% が、部分的にインデックス付けされたアイテムからのものです。</span><span class="sxs-lookup"><span data-stu-id="f4751-135">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="f4751-136">前述したように、ほとんどの組織のお客様は、ボリュームごとのコンテンツの数が1% 未満で、部分的にインデックスが作成されているサイズによるコンテンツの12% 未満になっています。</span><span class="sxs-lookup"><span data-stu-id="f4751-136">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="f4751-137">部分的にインデックスが作成されたアイテムを処理する</span><span class="sxs-lookup"><span data-stu-id="f4751-137">Working with partially indexed items</span></span>

<span data-ttu-id="f4751-138">部分的なアイテムを調べて、関連する情報が含まれていないことを検証する必要がある場合は、部分的にインデックスが作成されたアイテムに関する情報を含む [コンテンツ検索レポートをエクスポート](export-a-content-search-report.md) できます。</span><span class="sxs-lookup"><span data-stu-id="f4751-138">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="f4751-139">コンテンツ検索レポートをエクスポートする場合は、部分的にインデックスが作成されたアイテムを含むエクスポートオプションのいずれかを選択するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f4751-139">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span> 
  
![2番目または3番目のオプションを選択して、部分的にインデックス付けされたアイテムをエクスポート](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="f4751-141">これらのオプションのいずれかを使用してコンテンツ検索結果またはコンテンツ検索レポートをエクスポートすると、インデックスが作成されていない Items.csv という名前のレポートがエクスポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4751-141">When you export content search results or a content search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="f4751-142">このレポートには、ResultsLog.csv ファイルと同じ情報が含まれています。ただし、インデックスが作成されていない Items.csv ファイルには、部分的にインデックスが作成されたアイテムに関連する **エラータグ** と **エラープロパティ**の2つのフィールドもあります。</span><span class="sxs-lookup"><span data-stu-id="f4751-142">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="f4751-143">これらのフィールドには、インデックスが設定された各アイテムのインデックス作成エラーに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4751-143">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="f4751-144">これら2つのフィールドの情報を使用すると、特定のインデックス作成エラーが調査に影響を与えるかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f4751-144">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="f4751-145">その場合は、対象コンテンツ検索を実行し、特定の電子メールメッセージと SharePoint または OneDrive ドキュメントを取得およびエクスポートして、調査に関連しているかどうかを確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f4751-145">If it does, you can perform a targeted content search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="f4751-146">詳細な手順については、「 [Office 365 で対象コンテンツ検索の CSV ファイルを準備](csv-file-for-an-id-list-content-search.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4751-146">For step-by-step instructions, see [Prepare a CSV file for a targeted Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
  
 <span data-ttu-id="f4751-147">**注:** インデックスのない Items.csv ファイルには、 **エラーの種類** と **エラーメッセージ**という名前のフィールドも含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4751-147">**Note:** The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="f4751-148">これらは、 **エラータグ** と **エラーのプロパティ** フィールドの情報に似た情報を含む従来のフィールドですが、詳細な情報は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="f4751-148">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="f4751-149">これらの従来のフィールドは無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="f4751-149">You can safely ignore these legacy fields.</span></span> 
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="f4751-150">部分的にインデックスが作成されたアイテムに関連するエラー</span><span class="sxs-lookup"><span data-stu-id="f4751-150">Errors related to partially indexed items</span></span>

<span data-ttu-id="f4751-151">エラータグは、エラーとファイルの種類の2つの情報で構成されています。</span><span class="sxs-lookup"><span data-stu-id="f4751-151">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="f4751-152">たとえば、このエラー/filetype ペアの場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f4751-152">For example, in this error/filetype pair:</span></span>

```text
 parseroutputsize_xls
```

   
 <span data-ttu-id="f4751-153">`parseroutputsize` は error で、  `xls` エラーが発生したファイルの種類です。</span><span class="sxs-lookup"><span data-stu-id="f4751-153">`parseroutputsize` is the error and  `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="f4751-154">ファイルの種類が認識されなかった場合や、ファイルの種類がエラーに該当しない場合は、  `noformat` ファイルの種類の代わりに値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4751-154">In cases were the file type wasn't recognized or the file type was doesn't apply to the error, you will see the value  `noformat` in place of the file type.</span></span> 
  
<span data-ttu-id="f4751-155">次に、インデックス作成エラーの一覧と、エラーの考えられる原因についての説明を示します。</span><span class="sxs-lookup"><span data-stu-id="f4751-155">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
|<span data-ttu-id="f4751-156">**エラータグ**</span><span class="sxs-lookup"><span data-stu-id="f4751-156">**Error tag**</span></span>|<span data-ttu-id="f4751-157">**説明**</span><span class="sxs-lookup"><span data-stu-id="f4751-157">**Description**</span></span>|
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="f4751-158">電子メールメッセージの添付ファイルが多すぎたため、これらの添付ファイルの一部は処理されませんでした。</span><span class="sxs-lookup"><span data-stu-id="f4751-158">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="f4751-159">コンテンツ取得とドキュメントパーサーで、他の添付ファイル内にネストされた添付ファイルのレベルが多すぎます。</span><span class="sxs-lookup"><span data-stu-id="f4751-159">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="f4751-160">これらの添付ファイルの一部は処理されませんでした。</span><span class="sxs-lookup"><span data-stu-id="f4751-160">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="f4751-161">添付ファイルは RMS で保護されていたため、デコードに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="f4751-161">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="f4751-162">電子メールメッセージに添付されたファイルが大きすぎて処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="f4751-162">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="f4751-163">処理された電子メールメッセージをインデックスに書き込むときに、インデックス可能なプロパティのいずれかが大きすぎたため、切り捨てられました。</span><span class="sxs-lookup"><span data-stu-id="f4751-163">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="f4751-164">切り捨てられたプロパティは、[Error Properties] フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4751-164">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="f4751-165">有効な Unicode として処理できなかったテキストが電子メールメッセージに含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4751-165">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="f4751-166">このアイテムのインデックス処理が完了していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f4751-166">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="f4751-167">添付ファイルまたは電子メールメッセージの内容は暗号化されており、Microsoft 365 はコンテンツをデコードできませんでした。</span><span class="sxs-lookup"><span data-stu-id="f4751-167">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="f4751-168">解析中に不明なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f4751-168">An unknown error occurred during parsing.</span></span> <span data-ttu-id="f4751-169">これは通常、ソフトウェアバグまたはサービスのクラッシュによって生じます。</span><span class="sxs-lookup"><span data-stu-id="f4751-169">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="f4751-170">添付ファイルが大きすぎてパーサーで処理できなかったため、添付ファイルの解析が行われなかったか、完了しませんでした。</span><span class="sxs-lookup"><span data-stu-id="f4751-170">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="f4751-171">添付ファイルの形式が正しくないため、パーサーで処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="f4751-171">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="f4751-172">これにより、古いファイル形式、互換性のないソフトウェアによって作成されたファイル、または要求された以外のものを装ったウイルスが発生します。</span><span class="sxs-lookup"><span data-stu-id="f4751-172">This result from can old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="f4751-173">添付ファイルの解析からの出力が大きすぎたため、切り捨てる必要がありました。</span><span class="sxs-lookup"><span data-stu-id="f4751-173">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="f4751-174">添付ファイルのファイルの種類が Microsoft 365 で検出できませんでした。</span><span class="sxs-lookup"><span data-stu-id="f4751-174">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="f4751-175">添付ファイルのファイルの種類が Office 365 によって検出されましたが、そのファイルの種類を解析することはできません。</span><span class="sxs-lookup"><span data-stu-id="f4751-175">An attachment had a file type that Office 365could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="f4751-176">Exchange ストアの電子メールプロパティの値が大きすぎて取得できなかったため、メッセージを処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="f4751-176">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="f4751-177">これは通常、電子メールメッセージの body プロパティにのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="f4751-177">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="f4751-178">コンテンツ取得元は、RMS で保護されたメッセージのデコードに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="f4751-178">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="f4751-179">ドキュメントでインデックス処理中に識別された単語の数が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="f4751-179">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="f4751-180">制限値に達したときにプロパティの処理が停止され、プロパティが切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="f4751-180">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |
   
<span data-ttu-id="f4751-181">エラーフィールドは、Error Tags フィールドにリストされている処理エラーの影響を受けるフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="f4751-181">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="f4751-182">やなどのプロパティを検索する場合  `subject`  `participants` 、メッセージ本文のエラーは検索結果に影響しません。</span><span class="sxs-lookup"><span data-stu-id="f4751-182">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="f4751-183">これは、さらに調査する必要がある、部分的にインデックスが作成されたアイテムを正確に判断する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f4751-183">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="f4751-184">PowerShell スクリプトを使用して、部分的にインデックスが作成された電子メールアイテムに対する組織の公開を決定する</span><span class="sxs-lookup"><span data-stu-id="f4751-184">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="f4751-185">次の手順では、すべての Exchange メールボックス内のすべてのアイテムを検索する PowerShell スクリプトを実行し、組織の部分的にインデックスが作成された電子メールアイテムの比率 (カウントとサイズ順) についてのレポートを生成し、発生した各インデックスエラーのアイテム数 (およびそのファイルの種類) を表示します。</span><span class="sxs-lookup"><span data-stu-id="f4751-185">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="f4751-186">前のセクションのエラータグの説明を使用して、インデックス作成エラーを特定します。</span><span class="sxs-lookup"><span data-stu-id="f4751-186">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="f4751-187">ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、のように `PartiallyIndexedItems.ps1` なります。</span><span class="sxs-lookup"><span data-stu-id="f4751-187">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

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

2. <span data-ttu-id="f4751-188">[セキュリティ/コンプライアンス センター PowerShell に接続します](https://go.microsoft.com/fwlink/p/?linkid=627084)。</span><span class="sxs-lookup"><span data-stu-id="f4751-188">[Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>
    
3. <span data-ttu-id="f4751-189">[セキュリティ & コンプライアンスセンター] PowerShell で、手順1でスクリプトを保存したフォルダーに移動し、スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="f4751-189">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

    ```powershell
    .\PartiallyIndexedItems.ps1
    ```

<span data-ttu-id="f4751-190">このスクリプトによって返される出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f4751-190">Here's an example fo the output returned by the script.</span></span>
  
![部分的にインデックスが作成された電子メールアイテムに対する組織の公開に関するレポートを生成するスクリプトからの出力の例](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
<span data-ttu-id="f4751-192">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="f4751-192">Note the following:</span></span>
  
1. <span data-ttu-id="f4751-193">電子メールアイテムの合計数とサイズ、および部分的にインデックスが作成された電子メールアイテムの組織の比率 (カウントとサイズ順)</span><span class="sxs-lookup"><span data-stu-id="f4751-193">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size)</span></span>
    
2. <span data-ttu-id="f4751-194">エラーが発生したエラータグと対応するファイルの種類を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f4751-194">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f4751-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4751-195">See also</span></span>

[<span data-ttu-id="f4751-196">Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="f4751-196">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
