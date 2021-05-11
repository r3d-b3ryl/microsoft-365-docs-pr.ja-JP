---
title: ID リストコンテンツ検索用の CSV ファイルを準備する
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
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: 既存のコンテンツ検索の CSV ファイルを使用して、特定の電子メール アイテムを返す ID リスト検索を作成します。
ms.openlocfilehash: 37a398d0896fcfd7b7282bda1f6a549ed9f53601
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311540"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="e0198-103">ID リストコンテンツ検索用の CSV ファイルを準備する</span><span class="sxs-lookup"><span data-stu-id="e0198-103">Prepare a CSV file for an ID list Content search</span></span>

<span data-ttu-id="e0198-104">特定のメールボックスの電子メール メッセージや他のメールボックス アイテムを検索するには、特定のメールボックスのExchange使用します。</span><span class="sxs-lookup"><span data-stu-id="e0198-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="e0198-105">ID リスト検索を作成するには、検索する特定のメールボックス アイテムを識別するコンマ区切り値 (CSV) ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="e0198-105">To create an ID list search, you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="e0198-106">この CSV ファイルでは、コンテンツ検索結果をエクスポートするか、既存のコンテンツ検索からコンテンツ検索レポートをエクスポートするときに含まれるResults.csvファイルまたはインデックスのない **Items.csv** ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="e0198-106">For this CSV file, you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content search results or export a Content search report from an existing Content search.</span></span> <span data-ttu-id="e0198-107">次に、これらのファイルのいずれかを編集して、検索する特定のアイテムを示し、新しい ID リスト検索を作成し、CSV ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="e0198-107">Then you edit one of these files to indicate the specific items to search for, create a new ID list search, and submit the CSV file.</span></span>

<span data-ttu-id="e0198-108">**ID リスト検索を作成する理由**</span><span class="sxs-lookup"><span data-stu-id="e0198-108">**Why create an ID list search?**</span></span> <span data-ttu-id="e0198-109">アイテムが **Results.csv** ファイルまたはインデックス化されていない **Items.csv** ファイルのメタデータに基づいて電子情報開示要求に対応しているかどうかを判断できない場合は、ID リスト検索を使用して、そのアイテムを検索、プレビュー、エクスポートして、調査中のケースに対応しているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="e0198-109">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="e0198-110">ID リスト検索は、通常、インデックスのないアイテムの特定のセットを検索して返す場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e0198-110">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

<span data-ttu-id="e0198-111">ID リスト検索を作成するプロセスの簡単な概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e0198-111">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="e0198-112">コンプライアンス センターで新しい検索を作成Microsoft 365実行します。</span><span class="sxs-lookup"><span data-stu-id="e0198-112">Create and run a new search in the Microsoft 365 compliance center.</span></span>

2. <span data-ttu-id="e0198-113">コンテンツ検索結果またはコンテンツ検索レポートをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e0198-113">Export the content search results or the content search report.</span></span> <span data-ttu-id="e0198-114">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0198-114">For more information, see:</span></span>

    - [<span data-ttu-id="e0198-115">コンテンツ検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e0198-115">Export Content search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="e0198-116">コンテンツ検索のレポートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e0198-116">Export a Content search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="e0198-117">ID リスト **Results.csv** に含める特定のメールボックス アイテムItems.csvファイルまたはインデックス解除されたファイルを編集し、特定のメールボックス アイテムを識別します。</span><span class="sxs-lookup"><span data-stu-id="e0198-117">Edit the **Results.csv** file or **Unindexed Items.csv** file and identify the specific mailbox items to include in the ID list search.</span></span> <span data-ttu-id="e0198-118">ID リスト [検索の](#prepare-the-csv-file-for-an-id-list-search) CSV ファイルを準備する手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0198-118">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="e0198-119">新しい ID リスト検索 (手順を参照) を [作成](#create-an-id-list-search)し、準備した CSV ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="e0198-119">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="e0198-120">作成された検索クエリは、CSV ファイルで選択されたアイテムのみを検索します。</span><span class="sxs-lookup"><span data-stu-id="e0198-120">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="e0198-121">ID リストの検索は、メールボックス アイテムでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e0198-121">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="e0198-122">ID リスト検索では、SharePointドキュメントOneDriveを検索できません。</span><span class="sxs-lookup"><span data-stu-id="e0198-122">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="e0198-123">ID リスト検索用の CSV ファイルを準備する</span><span class="sxs-lookup"><span data-stu-id="e0198-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="e0198-124">検索用の検索結果またはレポートをエクスポートした後、次の手順を実行して、ID リスト検索用の CSV ファイルを準備します。</span><span class="sxs-lookup"><span data-stu-id="e0198-124">After you export the search results or report for a search, perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="e0198-125">この CSV ファイルは、ID リスト検索のすべてのアイテムを識別します。</span><span class="sxs-lookup"><span data-stu-id="e0198-125">This CSV file identifies every item in the ID list search.</span></span>

<span data-ttu-id="e0198-126">CSV ファイルは、サイトおよび SharePoint アカウントOneDrive含まれる検索から使用できますが、ID リスト検索のメールボックス アイテムのみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e0198-126">You can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can only select mailbox items for an ID list search.</span></span> <span data-ttu-id="e0198-127">ID リスト検索を作成するときに、SharePointまたはOneDriveでドキュメントを選択すると、CSV ファイルの検証が失敗します。</span><span class="sxs-lookup"><span data-stu-id="e0198-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="e0198-128">[データベース] **Results.csv** または **[インデックス** Items.csv] ファイルを開Excel。</span><span class="sxs-lookup"><span data-stu-id="e0198-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="e0198-129">[選択 **された] 列** に **、検索する** アイテムに対応するセルに「はい」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e0198-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="e0198-130">検索するアイテムごとにこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e0198-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e0198-131">[ドキュメント ID] 列で CSV ファイルExcel開いた場合、ドキュメント **ID** 列のデータ形式が [全般] に変更されている可能性 **があります**。</span><span class="sxs-lookup"><span data-stu-id="e0198-131">When you open the CSV file in Excel, the data format for the **Document ID** column may have been changed to **General**.</span></span> <span data-ttu-id="e0198-132">これにより、アイテムのドキュメント ID が科学表記で表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0198-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="e0198-133">たとえば、"481037338205" のドキュメント ID は"4.81037E+11" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0198-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11".</span></span> <span data-ttu-id="e0198-134">この場合は、次の手順を実行して、[ドキュメント **ID]** 列のデータ形式を **[数値** ] に変更して、ドキュメント ID の正しい形式を復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0198-134">If this happens, you have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="e0198-135">これを実行しない場合、CSV ファイルを使用する ID リスト検索は失敗します。</span><span class="sxs-lookup"><span data-stu-id="e0198-135">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="e0198-136">[ドキュメント ID] 列全体を **右クリックし** 、[セルの書式設定] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e0198-136">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="e0198-137">[カテゴリ] **ボックスで** 、[数値] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e0198-137">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="e0198-138">小数点以下の桁数を **0** に変更し **、[OK]** をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="e0198-138">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="e0198-139">[ドキュメント ID] 列の値が数値に変更されます。</span><span class="sxs-lookup"><span data-stu-id="e0198-139">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="e0198-140">ID リスト コンテンツ検索用に送信する準備が整った CSV ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e0198-140">Here's an example of a CSV file that's ready to be submitted for an ID list content search.</span></span>

    ![対象コンテンツ検索用の CSV ファイルの例](../media/SearchIDListCSVFile.png)

6. <span data-ttu-id="e0198-142">CSV ファイルを保存するか、[ **名前を付けて保存** ] を使用して、別のファイル名でファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="e0198-142">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="e0198-143">どちらの場合も、必ず CSV 形式でファイルを保存してください。</span><span class="sxs-lookup"><span data-stu-id="e0198-143">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="e0198-144">ID リスト検索の作成</span><span class="sxs-lookup"><span data-stu-id="e0198-144">Create an ID list search</span></span>

<span data-ttu-id="e0198-145">次の手順では、新しい ID リスト検索を作成し、前の手順で準備した CSV ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="e0198-145">The next step is to create a new ID list search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0198-146">検索結果またはレポートをエクスポートした後、2 日以内に ID リスト検索を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0198-146">You should create an ID list search no more than 2 days after exporting the search results or report.</span></span> <span data-ttu-id="e0198-147">2 日以上前にエクスポートされた検索結果またはレポートの場合は、検索結果またはレポートを再エクスポートして、更新された CSV ファイルを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0198-147">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="e0198-148">次に、更新された CSV ファイルのいずれかを準備し、それを使用して ID リスト検索を作成できます。</span><span class="sxs-lookup"><span data-stu-id="e0198-148">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="e0198-149"><https://compliance.microsoft.com> に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="e0198-149">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="e0198-150">Microsoft 365 コンプライアンス センターの左側のナビゲーション ウィンドウで [**すべてを表示**] をクリックし、[**コンテンツ検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0198-150">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Content search**.</span></span>

3. <span data-ttu-id="e0198-151">[コンテンツ検索 **] ページで** 、[ID リストで **検索] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e0198-151">On the **Content search** page, click **Search by ID List**.</span></span>

4. <span data-ttu-id="e0198-152">[ID リスト **による検索**] フライアウトで、検索に名前を付け (必要に応じて説明します) し、[参照] をクリックして、前の手順で準備した CSV ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0198-152">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="e0198-153">Microsoft 365 CSV ファイルの検証を試行します。</span><span class="sxs-lookup"><span data-stu-id="e0198-153">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="e0198-154">検証に失敗した場合は、検証エラーのトラブルシューティングに役立つ可能性があるエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0198-154">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="e0198-155">ID リスト検索を作成するには、CSV ファイルを正常に検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0198-155">The CSV file has to be successfully validated to create an ID list search.</span></span>

5. <span data-ttu-id="e0198-156">CSV ファイルが正常に検証された後、[検索] **をクリック** して ID リスト検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="e0198-156">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="e0198-157">生成されたクエリと推定検索結果数を示す ID リスト検索のフライアウト ページの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e0198-157">Here's an example of the flyout page from an ID list search that shows the query that's generated and the estimated number of search results.</span></span>

    ![ID リスト検索の検索クエリ](../media/SearchIDListFlyout.png)

    <span data-ttu-id="e0198-159">ID 検索の統計情報に表示される推定アイテムの数は、CSV ファイルで選択したアイテムの数と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0198-159">The number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

6. <span data-ttu-id="e0198-160">ID リスト検索で返されるアイテムをプレビューまたはエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e0198-160">Preview or export the items returned by the ID list search.</span></span>

## <a name="more-information"></a><span data-ttu-id="e0198-161">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e0198-161">More information</span></span>

<span data-ttu-id="e0198-162">ID リスト検索の作成後にメールボックスを移動した場合、検索のクエリは指定されたアイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="e0198-162">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="e0198-163">これは、メールボックスアイテムの **DocumentId** プロパティが、メールボックスを移動するときに変更されるためです。</span><span class="sxs-lookup"><span data-stu-id="e0198-163">That's because the **DocumentId** property for mailbox items is changed when a mailbox is moved.</span></span> <span data-ttu-id="e0198-164">まれに、ID リスト検索を作成した後にメールボックスを移動する場合は、新しいコンテンツ検索を作成し (または既存の検索の検索結果を更新する) し、検索結果またはレポートをエクスポートして、新しい ID リスト検索の作成に使用できる更新された CSV ファイルを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0198-164">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new Content search (or update the search results for an existing search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
