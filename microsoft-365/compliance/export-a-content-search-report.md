---
title: コンテンツ検索レポートのエクスポート
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: コンテンツ検索の &実際の結果は、Office 365 のセキュリティ コンプライアンス センターでエクスポートする代わりに、検索結果レポートをエクスポートできます。 レポートには、検索結果の概要と、エクスポートされる各アイテムに関する詳細情報を含むドキュメントが含まれる。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 094e67812b45ab1544d629ba6ddabcd86c70c633
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311575"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="c03ce-104">コンテンツ検索のレポートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="c03ce-104">Export a Content search report</span></span>

<span data-ttu-id="c03ce-105">Microsoft 365 コンプライアンス センターのコンテンツ検索 (または Core 電子情報開示ケースに関連付けられている検索) から検索結果の完全なセットをエクスポートする代わりに、実際の検索結果をエクスポートするときに生成されるレポートと同じレポートをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-105">Instead of exporting the full set of search results from a Content search in the Microsoft 365 compliance Center (or from a search that's associated with a Core eDiscovery case), you can export the same reports that are generated when you export the actual search results.</span></span>
  
<span data-ttu-id="c03ce-106">レポートをエクスポートすると、レポート ファイルは、コンテンツ検索と同じ名前を持つローカル コンピューター上のフォルダーにダウンロードされますが、そのフォルダーには _ReportsOnly が *追加されます*。</span><span class="sxs-lookup"><span data-stu-id="c03ce-106">When you export a report, the report files are downloaded to a folder on your local computer that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="c03ce-107">たとえば、コンテンツ検索の名前が ContosoCase0815 の場合、レポートは *"ContosoCase0815"* という名前のフォルダー *にContosoCase0815_ReportsOnly。*</span><span class="sxs-lookup"><span data-stu-id="c03ce-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="c03ce-108">レポートに含まれるドキュメントの一覧については、「レポートに含まれるもの」 [を参照してください](#whats-included-in-the-report)。</span><span class="sxs-lookup"><span data-stu-id="c03ce-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-export-a-search-report"></a><span data-ttu-id="c03ce-109">検索レポートをエクスポートする前に</span><span class="sxs-lookup"><span data-stu-id="c03ce-109">Before you export a search report</span></span>

- <span data-ttu-id="c03ce-110">検索レポートをエクスポートするには、コンプライアンス センターのセキュリティ とコンプライアンス センターでコンプライアンス検索&必要があります。</span><span class="sxs-lookup"><span data-stu-id="c03ce-110">To export a search report, you have to be assigned the Compliance Search management role in Security & Compliance Center.</span></span> <span data-ttu-id="c03ce-111">この役割は、既定で組み込みの電子情報開示マネージャーと組織の管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="c03ce-112">詳細については、「Assign [eDiscovery permissions 」を参照してください](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="c03ce-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="c03ce-113">レポートをエクスポートすると、データがローカル コンピューターにダウンロードされる前Azure Storage Microsoft クラウド内の場所に一時的に保存されます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-113">When you export a report, the data is temporarily stored in an Azure Storage location in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="c03ce-114">組織が Azure のエンドポイント **\* (.blob.core.windows.net** )に接続できます (ワイルドカードはエクスポートの一意の識別子を表します)。</span><span class="sxs-lookup"><span data-stu-id="c03ce-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="c03ce-115">検索結果データは、作成Azure Storage 2 週間後に、検索結果の場所から削除されます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-115">The search results data is deleted from the Azure Storage location two weeks after it's created.</span></span>

- <span data-ttu-id="c03ce-116">検索結果をエクスポートする際に使用するコンピューターは、次のシステム要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="c03ce-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="c03ce-117">最新バージョンの Windows (32 ビットまたは 64 ビット)</span><span class="sxs-lookup"><span data-stu-id="c03ce-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="c03ce-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="c03ce-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="c03ce-119">電子情報開示エクスポート ツール 1 を実行するには、次のサポートされているブラウザーのいずれかを使用する<sup>必要があります</sup>。</span><span class="sxs-lookup"><span data-stu-id="c03ce-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="c03ce-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="c03ce-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="c03ce-121">OR</span><span class="sxs-lookup"><span data-stu-id="c03ce-121">OR</span></span>

  - <span data-ttu-id="c03ce-122">Microsoft Internet Explorer 10以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="c03ce-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="c03ce-123"><sup>1</sup> Microsoft は、サードパーティ製の拡張機能やアドオンを、他のアプリケーションClickOnce行わない。</span><span class="sxs-lookup"><span data-stu-id="c03ce-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="c03ce-124">サードパーティの拡張機能またはアドオンを使用して、サポートされていないブラウザーを使用して検索結果をエクスポートする機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c03ce-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="c03ce-125"><sup>2</sup>最新の変更の結果、Microsoft EdgeサポートClickOnceは既定で有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="c03ce-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="c03ce-126">Edge でのサポートの有効化ClickOnce手順については、「電子情報開示エクスポート ツールを使用する」を参照[Microsoft Edge。](configure-edge-to-export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="c03ce-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="c03ce-127">検索によって返される結果の推定合計サイズが 2 TB を超えると、レポートのエクスポートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c03ce-127">If the estimated total size of the results returned by search exceeds 2 TB, exporting the reports fails.</span></span> <span data-ttu-id="c03ce-128">レポートを正常にエクスポートするには、範囲を絞り込み、検索結果の推定サイズが 2 TB 未満の検索を再実行してください。</span><span class="sxs-lookup"><span data-stu-id="c03ce-128">To successfully export the reports, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="c03ce-129">検索の結果が 7 日を超え、エクスポート レポート ジョブを送信すると、検索結果を更新するために検索を再実行するように求めるエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-129">If the results of a search are older than 7 days and you submit an export report job, an error message is displayed prompting you to rerun the search to update the search results.</span></span> <span data-ttu-id="c03ce-130">この場合は、エクスポートを取り消し、検索を再実行してから、エクスポートを再度開始します。</span><span class="sxs-lookup"><span data-stu-id="c03ce-130">If this happens, cancel the export, rerun the search, and then start the export again.</span></span>

- <span data-ttu-id="c03ce-131">検索レポートのエクスポートは、同時に実行されるエクスポートの最大数と、1 人のユーザーが実行できるエクスポートの最大数に対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-131">Exporting search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="c03ce-132">エクスポートの制限の詳細については、「コンテンツのエクスポート [検索結果」を参照してください](export-search-results.md#export-limits)。</span><span class="sxs-lookup"><span data-stu-id="c03ce-132">For more information about export limits, see [Export Content search results](export-search-results.md#export-limits).</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="c03ce-133">手順 1: エクスポート用のレポートを生成する</span><span class="sxs-lookup"><span data-stu-id="c03ce-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="c03ce-134">最初の手順は、エクスポートするコンピューターにダウンロードするためのレポートを準備します。</span><span class="sxs-lookup"><span data-stu-id="c03ce-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="c03ce-135">レポートをエクスポートすると、レポート ドキュメントは Microsoft クラウドのAzure Storageにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-135">When you export the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="c03ce-136">[コンプライアンス Microsoft 365] で、レポートをエクスポートするコンテンツ検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="c03ce-136">In the Microsoft 365 compliance center, select the Content search that you want to export the report from.</span></span>
  
2. <span data-ttu-id="c03ce-137">検索フライ **アウト ページの** 下部にある [アクション] メニューで、[レポートのエクスポート] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c03ce-137">On the **Actions** menu at the bottom of the search flyout page, click **Export report**.</span></span>

   ![[操作] メニューの [レポートのエクスポート] オプション](../media/ActionMenuExportReport.png)

   <span data-ttu-id="c03ce-139">[ **レポートのエクスポート]** フライアウト ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-139">The **Export report** flyout page is displayed.</span></span> <span data-ttu-id="c03ce-140">検索に関する情報をエクスポートするために使用できるエクスポート レポート オプションは、検索結果がメールボックスまたはサイトにあるか、両方の組み合わせかによって異なっています。</span><span class="sxs-lookup"><span data-stu-id="c03ce-140">The export report options available to export information about the search depend on whether search results are located in mailboxes or sites or a combination of both.</span></span>
  
3. <span data-ttu-id="c03ce-141">[ **出力オプション] で**、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c03ce-141">Under **Output options**, choose one of the following options:</span></span>
  
   ![出力オプションのエクスポート](../media/ExportOutputOptions.png)

    - <span data-ttu-id="c03ce-143">**認識できない形式の** アイテムを除くすべてのアイテムが暗号化される、または他の理由でインデックスが作成されていない。</span><span class="sxs-lookup"><span data-stu-id="c03ce-143">**All items, excluding ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="c03ce-144">このオプションは、インデックス付きアイテムに関する情報のみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="c03ce-144">This option only exports information about indexed items.</span></span>
  
    - <span data-ttu-id="c03ce-145">**認識されていない形式の** アイテムを含むすべてのアイテムが暗号化されている、または他の理由でインデックスが作成されていない。</span><span class="sxs-lookup"><span data-stu-id="c03ce-145">**All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="c03ce-146">このオプションは、インデックス付きアイテムとインデックス付きアイテムに関する情報をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="c03ce-146">This option exports information about indexed and unindexed items.</span></span>
  
    - <span data-ttu-id="c03ce-147">**認識できない形式のアイテム**、暗号化されているアイテム、または他の理由でインデックスが作成されていないアイテムのみ。</span><span class="sxs-lookup"><span data-stu-id="c03ce-147">**Only items that have an unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="c03ce-148">このオプションは、インデックスが作成されていないアイテムに関する情報のみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="c03ce-148">This option only exports information about unindexed items.</span></span>

4. <span data-ttu-id="c03ce-149">[コンテンツ **の重複除外を有効にする] Exchange構成** します。</span><span class="sxs-lookup"><span data-stu-id="c03ce-149">Configure the **Enable de-duplication for Exchange content** option.</span></span>
  
   - <span data-ttu-id="c03ce-150">このオプションを選択すると、重複するメッセージの数 (重複除外前と重複除外後) がエクスポート概要レポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-150">If you select this option, the count of duplicate messages (before de-duplication and after de-duplication) is included in the export summary report.</span></span> <span data-ttu-id="c03ce-151">また、メッセージのコピーは、メッセージ ファイルに 1 manifest.xmlされます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-151">Also, only one copy of a message will be included in the manifest.xml file.</span></span> <span data-ttu-id="c03ce-152">ただし、エクスポート結果レポートには重複メッセージのコピーごとに行が含まれるので、重複するメッセージのコピーを含むメールボックスを識別できます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-152">But the export results report will contain a row for every copy of a duplicate message so that you can identify the mailboxes that contain a copy of the duplicate message.</span></span> <span data-ttu-id="c03ce-153">エクスポートされたレポートの詳細については、「 [レポートに含まれるもの」を参照してください](#whats-included-in-the-report)。</span><span class="sxs-lookup"><span data-stu-id="c03ce-153">For more information about the exported reports, see [What's included in the report](#whats-included-in-the-report).</span></span>

   - <span data-ttu-id="c03ce-154">このオプションを選択しない場合、エクスポート レポートには、重複を含む、検索によって返されるすべてのメッセージに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-154">If you don't select this option, the export reports will contain information about all messages returned by the search, including duplicates.</span></span>

     <span data-ttu-id="c03ce-155">重複除外と重複アイテムの識別方法の詳細については、「電子情報開示検索結果の重複除外 [」を参照してください](de-duplication-in-ediscovery-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="c03ce-155">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

5. <span data-ttu-id="c03ce-156">[レポート **の生成] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c03ce-156">Click **Generate report**.</span></span>

   <span data-ttu-id="c03ce-157">検索レポートはダウンロード用に準備されています。つまり、レポート ドキュメントは Microsoft クラウド内Azure Storage場所にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-157">The search reports are prepared for downloading, which means the report documents are uploaded to an Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="c03ce-158">この処理には数分間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c03ce-158">This may take several minutes.</span></span>

<span data-ttu-id="c03ce-159">エクスポートされた検索レポートをダウンロードする手順については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c03ce-159">See the next section for instructions to download the exported search reports.</span></span>
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="c03ce-160">手順 2: レポートをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="c03ce-160">Step 2: Download the report</span></span>

<span data-ttu-id="c03ce-161">次の手順では、レポートをローカル コンピューター Azure Storageからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c03ce-161">The next step is to download the report from the Azure Storage area to your local computer.</span></span>

1. <span data-ttu-id="c03ce-162">コンプライアンス センター **の [** コンテンツ検索] Microsoft 365で、[エクスポート]**タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c03ce-162">On the **Content search** page in the Microsoft 365 compliance center, select the **Exports** tab</span></span>
  
   <span data-ttu-id="c03ce-163">[更新] を **クリックして** エクスポート ジョブの一覧を更新し、作成したエクスポート ジョブを表示する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="c03ce-163">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="c03ce-164">レポート ジョブのエクスポートには、対応する検索と同じ名前 **が付き** 、_ReportsOnlyに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-164">Export report jobs have the same name as the corresponding search with **_ReportsOnly** appended to the search name.</span></span>
  
2. <span data-ttu-id="c03ce-165">手順 1 で作成したエクスポート ジョブを選択します。</span><span class="sxs-lookup"><span data-stu-id="c03ce-165">Select the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="c03ce-166">[エクスポート] **キーの [レポートの** エクスポート] フライアウト ページ **で、[** クリップボード **にコピー] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c03ce-166">On the **Export report** flyout page under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="c03ce-167">手順 6 でこのキーを使用して検索結果をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c03ce-167">You use this key in step 6 to download the search results.</span></span>
  
   > [!IMPORTANT]
   > <span data-ttu-id="c03ce-168">誰でも電子情報開示エクスポート ツールをインストールして起動し、このキーを使用して検索レポートをダウンロードすることができますので、パスワードや他のセキュリティ関連情報を保護するのと同じ方法で、このキーを保護するための予防措置を取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="c03ce-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span>

4. <span data-ttu-id="c03ce-169">フライアウト ページの上部にある [結果のダウンロード] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c03ce-169">At the top of the flyout page, click **Download results**.</span></span>

5. <span data-ttu-id="c03ce-170">電子情報開示エクスポート ツールのインストールを求 **めるメッセージが** 表示されたら、[インストール] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c03ce-170">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>

6. <span data-ttu-id="c03ce-171">電子情報開示 **エクスポート ツールで、** 次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c03ce-171">In the **eDiscovery Export Tool**, do the following:</span></span>

   ![電子情報開示エクスポート ツール](../media/eDiscoveryExportTool.png)

   1. <span data-ttu-id="c03ce-173">手順 3 でコピーしたエクスポート キーを適切なボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-173">Paste the export key that you copied in step 3 in the appropriate box.</span></span>
  
   2. <span data-ttu-id="c03ce-174">[ **参照]** をクリックして、検索レポート ファイルをダウンロードする場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="c03ce-174">Click **Browse** to specify the location where you want to download the search report files.</span></span>

7. <span data-ttu-id="c03ce-175">**[開始]** をクリックして、検索結果をコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c03ce-175">Click **Start** to download the search results to your computer.</span></span>
  
    <span data-ttu-id="c03ce-176">**電子情報開示エクスポート ツール** には、ダウンロードする残りのアイテムの数とサイズの見積もりなど、エクスポート プロセスの状態に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-176">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="c03ce-177">エクスポート プロセスが完了すると、ダウンロードされた場所にあるファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-177">When the export process is complete, you can access the files in the location where they were downloaded.</span></span>
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="c03ce-178">レポートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="c03ce-178">What's included in the report</span></span>

<span data-ttu-id="c03ce-179">コンテンツ検索の結果に関するレポートを生成およびエクスポートすると、次のドキュメントがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-179">When you generate and export a report about the results of a Content search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="c03ce-180">**エクスポートの概要:** エクスポートExcelを含むドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c03ce-180">**Export summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="c03ce-181">これには、検索されたコンテンツ ソースの数、各コンテンツの場所からの検索結果の数、アイテムの推定数、エクスポートされるアイテムの実際の数、エクスポートされるアイテムの推定サイズと実際のサイズなどの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-181">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span>

   <span data-ttu-id="c03ce-182">レポートのエクスポート時にインデックスのないアイテムを含める場合、インデックスのないアイテムの数は、推定検索結果の総数と、エクスポート概要レポートに表示されるダウンロードされた検索結果の総数 (検索結果をエクスポートする場合) に含まれます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-182">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the export summary report.</span></span> <span data-ttu-id="c03ce-183">つまり、ダウンロードされるアイテムの総数は、推定結果の総数とインデックスのないアイテムの総数と等しくなります。</span><span class="sxs-lookup"><span data-stu-id="c03ce-183">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span>
  
- <span data-ttu-id="c03ce-184">**マニフェスト:** 検索結果に含まれる各アイテムに関する情報を含むマニフェスト ファイル (XML 形式)。</span><span class="sxs-lookup"><span data-stu-id="c03ce-184">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="c03ce-185">重複除外オプションを有効にした場合、重複するメッセージはマニフェスト ファイルに含まれません。</span><span class="sxs-lookup"><span data-stu-id="c03ce-185">If you enabled the de-duplication option, duplicate message are not included in the manifest file.</span></span>

- <span data-ttu-id="c03ce-186">**結果:** 検索結果Excelエクスポートされる各インデックス付きアイテムに関する情報を含む行を含むドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="c03ce-186">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="c03ce-187">電子メールの場合、結果ログには、次を含む各メッセージに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-187">For email, the result log contains information about each message, including:</span></span> 

  - <span data-ttu-id="c03ce-188">移行元のメールボックス内のメッセージの場所 (メッセージがプライマリ メールボックスとアーカイブ メールボックスのどちらであるかを含みます)。</span><span class="sxs-lookup"><span data-stu-id="c03ce-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>

  - <span data-ttu-id="c03ce-189">メッセージが送信または受信された日付。</span><span class="sxs-lookup"><span data-stu-id="c03ce-189">The date the message was sent or received.</span></span>

  - <span data-ttu-id="c03ce-190">メッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="c03ce-190">The Subject line from the message.</span></span>

  - <span data-ttu-id="c03ce-191">メッセージの送信者と受信者。</span><span class="sxs-lookup"><span data-stu-id="c03ce-191">The sender and recipients of the message.</span></span>

  <span data-ttu-id="c03ce-192">サイトおよびサイトSharePoint OneDrive for Business、結果ログには、次を含む各ドキュメントに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c03ce-192">For documents from SharePoint and OneDrive for Business sites, the results log contains information about each document, including:</span></span>

  - <span data-ttu-id="c03ce-193">ドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="c03ce-193">The URL for the document.</span></span>

  - <span data-ttu-id="c03ce-194">ドキュメントがあるサイト コレクションの URL。</span><span class="sxs-lookup"><span data-stu-id="c03ce-194">The URL for the site collection where the document is located.</span></span>

  - <span data-ttu-id="c03ce-195">ドキュメントが最後に変更された日付。</span><span class="sxs-lookup"><span data-stu-id="c03ce-195">The date that the document was last modified.</span></span>

  - <span data-ttu-id="c03ce-196">ドキュメントの名前 (これは、結果のログの [件名] 列にあります)。</span><span class="sxs-lookup"><span data-stu-id="c03ce-196">The name of the document (which is located in the Subject column in the result log).</span></span>

  > [!NOTE]
  > <span data-ttu-id="c03ce-197">結果レポートの行数は、検索結果の総数からインデックスが作成されていないアイテム レポートに表示されるアイテムの総数を引いた値 **と等し** くなります。</span><span class="sxs-lookup"><span data-stu-id="c03ce-197">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span>
  
- <span data-ttu-id="c03ce-198">**Trace.log**: エクスポート プロセスに関する詳細なログ情報を含み、エクスポート中に問題を発見するのに役立つトレース ログ。</span><span class="sxs-lookup"><span data-stu-id="c03ce-198">**Trace.log**: A trace log that contains detailed logging information about the export process and can help uncover issues during export.</span></span> <span data-ttu-id="c03ce-199">検索レポートのエクスポートに関連する問題について Microsoft サポートと一緒にチケットを開く場合は、このトレース ログの提供を求めるメッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c03ce-199">If you open a ticket with Microsoft Support about an issue related to exporting search reports, you may be asked to provide this trace log.</span></span>

- <span data-ttu-id="c03ce-200">**インデックスが作成されていないアイテム:** 検索結果Excel含まれるインデックスのないアイテムに関する情報を含むドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="c03ce-200">**Unindexed items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="c03ce-201">検索結果レポートを生成するときにインデックスのないアイテムを含めなかった場合、このレポートはダウンロードされますが、空になります。</span><span class="sxs-lookup"><span data-stu-id="c03ce-201">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
