---
title: 監査ログ レコードをエクスポート、構成、表示する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
ms.custom: seo-marvel-apr2020
description: この記事では、Microsoft 365 監査ログ レコードをエクスポート、構成、および表示する方法について説明します。
ms.openlocfilehash: 4cea867b46d3bda7d3b3a8cd38f3d01938da8764
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906868"
---
# <a name="export-configure-and-view-audit-log-records"></a><span data-ttu-id="e4a4f-103">監査ログ レコードをエクスポート、構成、表示する</span><span class="sxs-lookup"><span data-stu-id="e4a4f-103">Export, configure, and view audit log records</span></span>

<span data-ttu-id="e4a4f-104">監査ログを検索して検索結果を CSV ファイルにダウンロードした後、ファイルには **AuditData** という名前の列が含まれます。各イベントに関する追加情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-104">After you search the audit log and download the search results to a CSV file, the file contains a column named **AuditData**, which contains additional information about each event.</span></span> <span data-ttu-id="e4a4f-105">この列のデータは JSON オブジェクトとして書式設定され、コンマで区切られた *property:value* ペアとして構成された複数のプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-105">The data in this column is formatted as a JSON object, which contains multiple properties that are configured as *property:value* pairs separated by commas.</span></span> <span data-ttu-id="e4a4f-106">Excel の Power Query Editor の JSON 変換機能を使用すると **、AuditData** 列の JSON オブジェクト内の各プロパティを複数の列に分割して、各プロパティに独自の列を設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-106">You can use the JSON transform feature in the Power Query Editor in Excel to split each property in the JSON object in the **AuditData** column into multiple columns so that each property has its own column.</span></span> <span data-ttu-id="e4a4f-107">これにより、これらのプロパティの 1 つ以上を並べ替え、フィルター処理し、探している特定の監査データをすばやく見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-107">This lets you sort and filter on one or more of these properties, which can help you quickly locate the specific auditing data you're looking for.</span></span>

## <a name="step-1-export-audit-log-search-results"></a><span data-ttu-id="e4a4f-108">手順 1: 監査ログの検索結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e4a4f-108">Step 1: Export audit log search results</span></span>

<span data-ttu-id="e4a4f-109">最初の手順は、監査ログを検索し、その結果をコンマ区切り値 (CSV) ファイルにローカル コンピューターにエクスポートすることです。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-109">The first step is to search the audit log and then export the results in a comma-separated value (CSV) file to your local computer.</span></span>
  
1. <span data-ttu-id="e4a4f-110">必要に [応じて監査ログ検索](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) を実行し、必要に応じて検索条件を変更します。目的の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-110">Run an [audit log search](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) and revise the search criteria if necessary until you have the desired results.</span></span>

2. <span data-ttu-id="e4a4f-111">[結果 **のエクスポート] をクリック** し、[すべての結果 **をダウンロードする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-111">Click **Export results** and select **Download all results**.</span></span> 

   ![[すべての結果をダウンロードする] をクリックします。](../media/ExportAuditSearchResults.png)

   <span data-ttu-id="e4a4f-113">このオプションは、手順 1 で実行した監査ログ検索からすべての監査レコードをエクスポートし、未加工データを監査ログから CSV ファイルにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-113">This option to exports all the audit records from the audit log search you ran in step 1, and downloads the raw data from the audit log to a CSV file.</span></span> 

   <span data-ttu-id="e4a4f-114">ウィンドウの下部にメッセージが表示され、CSV ファイルを開くまたは保存するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-114">A message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span> 

3. <span data-ttu-id="e4a4f-115">[ **名前を>保存] をクリックし** 、CSV ファイルをローカル コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-115">Click **Save > Save as** and save the CSV file to your local computer.</span></span> <span data-ttu-id="e4a4f-116">多くの検索結果をダウンロードするには、しばらく時間が必要です。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-116">It takes a while to download many search results.</span></span> <span data-ttu-id="e4a4f-117">これは通常、すべてのアクティビティまたは広い日付範囲を検索する場合に当てはまっています。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-117">This is typically the case when searching for all activities or a broad date range.</span></span> <span data-ttu-id="e4a4f-118">CSV ファイルのダウンロードが完了すると、ウィンドウの下部にメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-118">A message at the bottom of the windows is displayed when the CSV file is finished downloading.</span></span>

   ![CSV ファイルのダウンロードが完了すると表示されるメッセージ](../media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > <span data-ttu-id="e4a4f-120">1 回の監査ログ検索から最大 50,000 エントリを CSV ファイルにダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-120">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="e4a4f-121">CSV ファイルに 50,000 エントリがダウンロードされている場合は、検索条件を満たすイベントが 50,000 件を超える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-121">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="e4a4f-122">この制限を超える値をエクスポートするには、日付範囲を使用して監査ログ レコードの数を減らしてみてください。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-122">To export more than this limit, try using a date range to reduce the number of audit log records.</span></span> <span data-ttu-id="e4a4f-123">50,000 を超えるエントリをエクスポートするには、日付範囲が小さい複数の検索を実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-123">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a><span data-ttu-id="e4a4f-124">手順 2: Power Query Editor を使用してエクスポートされた監査ログを書式設定する</span><span class="sxs-lookup"><span data-stu-id="e4a4f-124">Step 2: Format the exported audit log using the Power Query Editor</span></span>

<span data-ttu-id="e4a4f-125">次の手順では、Excel の Power Query Editor の JSON 変換機能を使用して **、AuditData** 列の JSON オブジェクトの各プロパティを独自の列に分割します。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-125">The next step is to use the JSON transform feature in the Power Query Editor in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="e4a4f-126">次に、列をフィルター処理して、特定のプロパティの値に基づいてレコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-126">Then you filter columns to view records based on the values of specific properties.</span></span> <span data-ttu-id="e4a4f-127">これにより、探している特定の監査データをすばやく見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-127">This can help you quickly locate the specific auditing data you're looking for.</span></span>

1. <span data-ttu-id="e4a4f-128">Excel 365、Excel 2019、または Excel 2016 用の空白のブックを開Office Excel で開きます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-128">Open a blank workbook in Excel for Office 365, Excel 2019, or Excel 2016.</span></span>

2. <span data-ttu-id="e4a4f-129">[データ **] タブの** [データ変換 **&]** リボン グループで、[テキスト/CSV から] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-129">On the **Data** tab, in the **Get & Transform Data** ribbon group, click **From Text/CSV**.</span></span>

    ![[データ] タブで、[テキスト/CSV から] をクリックします。](../media/JSONTransformOpenCSVFile.png)

3. <span data-ttu-id="e4a4f-131">手順 1 でダウンロードした CSV ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-131">Open the CSV file that you downloaded in Step 1.</span></span>

4. <span data-ttu-id="e4a4f-132">表示されるウィンドウで、[データの変換] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-132">In the window that's displayed, click **Transform Data**.</span></span>

   ![[データの変換] をクリックします。](../media/JSONOpenPowerQuery.png)

   <span data-ttu-id="e4a4f-134">CSV ファイルはクエリ エディターで **開きます**。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-134">The CSV file is opened in the **Query Editor**.</span></span> <span data-ttu-id="e4a4f-135">次の 4 つの列があります。CreationDate、UserIds、Operations、AuditData です。    </span><span class="sxs-lookup"><span data-stu-id="e4a4f-135">There are four columns: **CreationDate**, **UserIds**, **Operations**, and **AuditData**.</span></span> <span data-ttu-id="e4a4f-136">**AuditData 列は**、複数のプロパティを含む JSON オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-136">The **AuditData** column is a JSON object that contains multiple properties.</span></span> <span data-ttu-id="e4a4f-137">次の手順では、JSON オブジェクト内の各プロパティの列を作成します。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-137">The next step is to create a column for each property in the JSON object.</span></span>

5. <span data-ttu-id="e4a4f-138">**[AuditData]** 列でタイトルを右クリックし、[変換] を **クリックし\*\*\*\*、[JSON] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-138">Right-click the title in the **AuditData** column, click **Transform**, and then click **JSON**.</span></span> 

   ![[AuditData] 列を右クリックし、[変換] をクリックし、[JSON] を選択します。](../media/JSONTransform.png)

6. <span data-ttu-id="e4a4f-140">**[AuditData]** 列の右上隅にある展開アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-140">In the upper-right corner of the **AuditData** column, click the expand icon.</span></span>

   ![[AuditData] 列で、[展開] アイコンをクリックします。](../media/JSONTransformExpandIcon.png)

   <span data-ttu-id="e4a4f-142">**AuditData** 列の JSON オブジェクトのプロパティの一部が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-142">A partial list of the properties in the JSON objects in the **AuditData** column is displayed.</span></span>

7. <span data-ttu-id="e4a4f-143">[ **詳細を読み込** む] をクリックして **、[AuditData]** 列の JSON オブジェクトのすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-143">Click **Load more** to display all properties in the JSON objects in the **AuditData** column.</span></span>

   ![JSON オブジェクトのすべてのプロパティを表示するには、[その他の読み込み] をクリックします。](../media/JSONTransformLoadJSONProperties.png)

   <span data-ttu-id="e4a4f-145">含めたくないプロパティの横にあるチェック ボックスをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-145">You can unselect the checkbox next to any property that you don't want to include.</span></span> <span data-ttu-id="e4a4f-146">調査に役立てない列を削除すると、監査ログに表示されるデータ量を減らすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-146">Eliminating columns that aren't useful for your investigation is a good way to reduce the amount of data displayed in the audit log.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="e4a4f-147">前のスクリーンショットに表示された JSON プロパティ ([追加の読み込み] をクリックした **後)** は、CSV ファイルの最初の 1,000 行の **AuditData** 列にあるプロパティに基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-147">The JSON properties displayed in the previous screenshot (after you click **Load more**) are based on the properties found in the **AuditData** column from the first 1,000 rows in the CSV file.</span></span> <span data-ttu-id="e4a4f-148">最初の 1,000 行の後にレコードに異なる JSON プロパティがある場合 **、AuditData** 列が複数の列に分割されている場合、これらのプロパティ (および対応する列) は含まれません。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-148">If there are different JSON properties in records after the first 1,000 rows, these properties (and a corresponding column) won't be included when the **AuditData** column is split into multiple columns.</span></span> <span data-ttu-id="e4a4f-149">これを防ぐには、監査ログの検索を再実行し、検索基準を絞り込み、返されるレコードを少なくします。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-149">To help prevent this, consider re-running the audit log search and narrow the search criteria so that fewer records are returned.</span></span> <span data-ttu-id="e4a4f-150">もう 1 つの回避策は、[ **操作** ] 列内のアイテムをフィルター処理して、(上記の手順 5 を実行する前に) **AuditData** 列で JSON オブジェクトを変換する前に行数を減らすことです。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-150">Another workaround is to filter items in the **Operations** column to reduce the number of rows (before you perform step 5 above) before transforming the JSON object in the **AuditData** column.</span></span>

   > [!TIP]
   > <span data-ttu-id="e4a4f-151">AuditData.AffectedItems などのリスト内の属性を表示するには、属性をプルする列の右上隅にある [展開] アイコンをクリックし、[新しい行に展開] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-151">To view an attribute within a list such as AuditData.AffectedItems, click the **Expand** icon in the upper right corner of the column you want to pull an attribute from, and then select **Expand to New Row**.</span></span>  <span data-ttu-id="e4a4f-152">そこからレコードが作成され、列の右上隅にある [展開] アイコンをクリックし、属性を表示し、表示または抽出する属性を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-152">From there it will be a record and you can click the **Expand** icon in the upper right corner of the column, view the attributes, and select the one you want to view or extract.</span></span>

8. <span data-ttu-id="e4a4f-153">次のいずれかの操作を実行して、選択した JSON プロパティごとに追加される列のタイトルを書式設定します。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-153">Do one of the following things to format the title of the columns that are added for each JSON property that's selected.</span></span>

    - <span data-ttu-id="e4a4f-154">[元の **列名をプレフィックスとして使用** する] チェック ボックスをオフにして、JSON プロパティの名前を列名として使用します。たとえば **、RecordType または** **SourceFileName**.</span><span class="sxs-lookup"><span data-stu-id="e4a4f-154">Unselect the **Use original column name as prefix** checkbox to use the name of the JSON property as the column names; for example, **RecordType** or **SourceFileName**.</span></span>

    - <span data-ttu-id="e4a4f-155">[元の **列名をプレフィックスとして** 使用する] チェック ボックスをオンのままにして、列名に AuditData プレフィックスを追加します。たとえば **、AuditData.RecordType または** **AuditData.SourceFileName** などです。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-155">Leave the **Use original column name as prefix** checkbox selected to add the AuditData prefix to the column names; for example, **AuditData.RecordType** or **AuditData.SourceFileName**.</span></span>

9. <span data-ttu-id="e4a4f-156">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-156">Click **OK**.</span></span>

    <span data-ttu-id="e4a4f-157">**AuditData 列** は複数の列に分割されます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-157">The **AuditData** column is split into multiple columns.</span></span> <span data-ttu-id="e4a4f-158">新しい各列は、AuditData JSON オブジェクトのプロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-158">Each new column corresponds to a property in the AuditData JSON object.</span></span> <span data-ttu-id="e4a4f-159">列の各行には、プロパティの値が含まれる。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-159">Each row in the column contains the value for the property.</span></span> <span data-ttu-id="e4a4f-160">プロパティに値が含まれている場合は *、null 値が* 表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-160">If the property doesn't contain a value, the *null* value is displayed.</span></span> <span data-ttu-id="e4a4f-161">Excel では、null 値を持つセルは空です。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-161">In Excel, cells with null values are empty.</span></span>
  
10. <span data-ttu-id="e4a4f-162">[ホーム **] タブで**、[読み込み&閉じる] をクリックして Power Query Editor を閉じ、変換された CSV ファイルを Excel ブックで開きます。 </span><span class="sxs-lookup"><span data-stu-id="e4a4f-162">On the **Home** tab, click **Close & Load** to close the Power Query Editor and open the transformed CSV file in an Excel workbook.</span></span>

## <a name="use-powershell-to-search-and-export-audit-log-records"></a><span data-ttu-id="e4a4f-163">PowerShell を使用して監査ログ レコードを検索およびエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e4a4f-163">Use PowerShell to search and export audit log records</span></span>

<span data-ttu-id="e4a4f-164">セキュリティ & コンプライアンス センターの監査ログ検索ツールを使用する代わりに、Exchange Online PowerShell の [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) コマンドレットを使用して、監査ログ検索の結果を CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-164">Instead of using the audit log search tool in the Security & Compliance Center, you can use the [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) cmdlet in Exchange Online PowerShell to export the results of an audit log search to a CSV file.</span></span> <span data-ttu-id="e4a4f-165">次に、手順 2 で説明したのと同じ手順に従って、Power Query エディターを使用して監査ログを書式設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-165">Then you can follow the same procedure described in Step 2 to format the audit log using the Power Query editor.</span></span> <span data-ttu-id="e4a4f-166">PowerShell コマンドレットを使用する利点の 1 つは *、RecordType* パラメーターを使用して特定のサービスからイベントを検索できるという利点です。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-166">One advantage of using the PowerShell cmdlet is that you can search for events from a specific service by using the *RecordType* parameter.</span></span> <span data-ttu-id="e4a4f-167">手順 2 で説明したように、PowerShell を使用して監査レコードを CSV ファイルにエクスポートして、Power Query エディターを使用して **AuditData** 列の JSON オブジェクトを変換する例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-167">Here are few examples of using PowerShell to export audit records to a CSV file so you can use the Power Query editor to transform the JSON object in the **AuditData** column as described in Step 2.</span></span>

<span data-ttu-id="e4a4f-168">この例では、次のコマンドを実行して、SharePoint 共有操作に関連するすべてのレコードを返します。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-168">In this example, run the following commands to return all records related to SharePoint sharing operations.</span></span>

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

<span data-ttu-id="e4a4f-169">検索結果は、CreationDate、UserIds、RecordType、AuditData の 4 つの列を含む *PowerShellAuditlog* という名前の CSV ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-169">The search results are exported to a CSV file named *PowerShellAuditlog* that contains four columns: CreationDate, UserIds, RecordType, AuditData).</span></span>

<span data-ttu-id="e4a4f-170">レコードの種類の名前または列挙値を RecordType パラメーターの値 *として使用* することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-170">You can also use the name or enum value for the record type as the value for the *RecordType* parameter.</span></span> <span data-ttu-id="e4a4f-171">レコードの種類名とそれに対応する列挙値の一覧については、365 管理アクティビティ API スキーマの *AuditLogRecordType* [Officeを参照してください](/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32)。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-171">For a list of record type names and their corresponding enum values, see the *AuditLogRecordType* table in [Office 365 Management Activity API schema](/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32).</span></span>

<span data-ttu-id="e4a4f-172">RecordType パラメーターには、1 つの値 *のみを含* めできます。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-172">You can only include a single value for the *RecordType* parameter.</span></span> <span data-ttu-id="e4a4f-173">他のレコードの種類の監査レコードを検索するには、前の 2 つのコマンドを再度実行して別のレコードの種類を指定し、それらの結果を元の CSV ファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-173">To search for audit records for other record types, you have to run the two previous commands again to specify a different record type and append those results to the original CSV file.</span></span> <span data-ttu-id="e4a4f-174">たとえば、次の 2 つのコマンドを実行して、SharePoint ファイルアクティビティを同じ日付範囲から同じ日付範囲のファイルに追加PowerShellAuditlog.csvします。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-174">For example, you would run the following two commands to add SharePoint file activities from the same date range to the PowerShellAuditlog.csv file.</span></span>

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a><span data-ttu-id="e4a4f-175">監査ログのエクスポートと表示に関するヒント</span><span class="sxs-lookup"><span data-stu-id="e4a4f-175">Tips for exporting and viewing the audit log</span></span>

<span data-ttu-id="e4a4f-176">JSON 変換機能を使用して **AuditData** 列を複数の列に分割する前と後に監査ログをエクスポートおよび表示するヒントと例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-176">Here are some tips and examples of exporting and viewing the audit log before and after you use the JSON transform feature to split the **AuditData** column into multiple columns.</span></span>

- <span data-ttu-id="e4a4f-177">**[RecordType] 列を** フィルター処理して、特定のサービスまたは機能領域のレコードのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-177">Filter the **RecordType** column to display only the records from a specific service or functional area.</span></span> <span data-ttu-id="e4a4f-178">たとえば、SharePoint 共有に関連するイベントを表示するには **、14** (SharePoint 共有アクティビティによってトリガーされるレコードの列挙値) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-178">For example, to show events related to SharePoint sharing, you would select **14** (the enum value for records triggered by SharePoint sharing activities).</span></span> <span data-ttu-id="e4a4f-179">**[RecordType]** 列に表示される列挙値に対応するサービスの一覧については、「監査ログの詳細なプロパティ」[を参照してください](detailed-properties-in-the-office-365-audit-log.md)。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-179">For a list of the services that correspond to the enum values displayed in the **RecordType** column, see [Detailed properties in the audit log](detailed-properties-in-the-office-365-audit-log.md).</span></span>

- <span data-ttu-id="e4a4f-180">[操作] **列を** フィルター処理して、特定のアクティビティのレコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-180">Filter the **Operations** column to display the records for specific activities.</span></span> <span data-ttu-id="e4a4f-181">セキュリティ & コンプライアンス センターの監査ログ検索ツールで検索可能なアクティビティに対応するほとんどの操作の一覧については、「セキュリティ & コンプライアンス センターの監査ログを検索する」の「監査アクティビティ [」セクションを](search-the-audit-log-in-security-and-compliance.md#audited-activities)参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4a4f-181">For a list of most operations that correspond to a searchable activity in the audit log search tool in the Security & Compliance Center, see the "Audited activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span>