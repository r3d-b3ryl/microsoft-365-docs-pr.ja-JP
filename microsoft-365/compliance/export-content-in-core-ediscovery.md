---
title: コア電子情報開示ケースからコンテンツをエクスポートおよびダウンロードする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: コア電子情報開示ケースからコンテンツをエクスポートおよびダウンロードする方法について説明します。Microsoft 365。
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310844"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="f3d7f-103">コア電子情報開示ケースからコンテンツをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="f3d7f-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="f3d7f-104">Core 電子情報開示ケースに関連付けられた検索が正常に実行された後、検索結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-104">After a search associated with a Core eDiscovery case is successfully run, you can export the search results.</span></span> <span data-ttu-id="f3d7f-105">検索結果をエクスポートすると、メールボックス アイテムは PST ファイルまたは個々のメッセージとしてダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="f3d7f-106">サイトからコンテンツをエクスポートSharePoint、OneDrive for Businessドキュメントや他のドキュメントのOfficeコピーがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="f3d7f-107">エクスポートResults.csvに関する情報を含むファイルと、すべての検索結果に関する情報を含むマニフェスト ファイル (XML 形式) もエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
## <a name="export-search-results"></a><span data-ttu-id="f3d7f-108">検索結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="f3d7f-108">Export search results</span></span>

1. <span data-ttu-id="f3d7f-109">適切な電子情報開示アクセス許可が割り当てられているユーザー アカウントの資格情報を使用して、アクセスして [https://compliance.microsoft.com](https://compliance.microsoft.com) サインインします。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-109">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="f3d7f-110">コンプライアンス センターの左側のナビゲーション ウィンドウでMicrosoft 365を表示]をクリックし、[電子情報開示] をクリックして [コア>**します**。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-110">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="f3d7f-111">[コア **電子情報開示]** ページで、保留リストを作成するケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-111">On the **Core eDiscovery** page, click the name of the case that you want to create the hold in.</span></span>

4. <span data-ttu-id="f3d7f-112">ケースの **ホーム** ページで、[検索] **タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-112">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="f3d7f-113">[フライアウト **] ページ** の下部にある [操作] メニューで、[結果のエクスポート] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-113">On the **Actions** menu at the bottom of the flyout page, click **Export results**.</span></span>

   ![[操作] メニューの [結果のエクスポート] オプション](../media/ActionMenuExportResults.png)

   <span data-ttu-id="f3d7f-115">Core 電子情報開示ケースに関連付けられた検索の結果をエクスポートするワークフローは、[コンテンツ検索] ページで検索の検索結果をエクスポートする場合 **と同** じです。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-115">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="f3d7f-116">詳細な手順については、「コンテンツ検索結果のエクスポート [」を参照してください](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-116">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="f3d7f-p103">検索されたメールボックスで同じメール メッセージの複数のインスタンスが検出された可能性がある場合でも、検索結果をエクスポートするときに、メール メッセージの 1 つのコピーのみがエクスポートされるようにする重複除去オプションを有効にできます。重複除去および重複したアイテムの特定方法の詳細については、「[電子情報開示検索結果での重複除去](de-duplication-in-ediscovery-search-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-p103">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched. For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

   <span data-ttu-id="f3d7f-119">エクスポートを開始すると、検索結果はダウンロード用に準備されます。つまり、検索結果は Microsoft クラウド内の Microsoft 提供のAzure Storageに転送されます。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-119">After you start the export, the search results are prepared for downloading, which means they are transferred to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="f3d7f-120">ケースの **[エクスポート]** タブをクリックして、エクスポート ジョブの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-120">Click the **Exports** tab in the case to display the list of export jobs.</span></span>
  
   ![コア電子情報開示ケースの [エクスポート] タブでジョブをエクスポートする](../media/CoreeDiscoveryExport.png)

   <span data-ttu-id="f3d7f-122">[更新] を **クリックして** エクスポート ジョブの一覧を更新し、作成したエクスポート ジョブを表示する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-122">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="f3d7f-123">エクスポート ジョブの名前は、対応する検索と同じ名前で、_Export **に追加** されます。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-123">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="f3d7f-124">作成したエクスポート ジョブをクリックして、フライアウト ページに状態情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-124">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="f3d7f-125">この情報には、ユーザーの場所に転送されたアイテムのAzure Storage含まれます。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-125">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="f3d7f-126">すべてのアイテムが転送された後、[結果のダウンロード] **をクリックして** 、検索結果をローカル コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-126">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="f3d7f-127">検索結果のダウンロードの詳細については、「コンテンツ検索結果のエクスポート」の「手順 [2」を参照してください。](export-search-results.md#step-2-download-the-search-results)</span><span class="sxs-lookup"><span data-stu-id="f3d7f-127">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

### <a name="more-information-about-exporting-searches-from-a-case"></a><span data-ttu-id="f3d7f-128">ケースからの検索のエクスポートの詳細</span><span class="sxs-lookup"><span data-stu-id="f3d7f-128">More information about exporting searches from a case</span></span>

- <span data-ttu-id="f3d7f-129">検索結果をエクスポートするときに含まれるエクスポート ファイルの詳細については、「コンテンツ検索レポートのエクスポート [」を参照してください](export-a-content-search-report.md#whats-included-in-the-report)。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-129">For more information about the export files that are included when you export search results, see [Export a Content search report](export-a-content-search-report.md#whats-included-in-the-report).</span></span>

- <span data-ttu-id="f3d7f-130">エクスポートを再開した場合、エクスポート ジョブを構成する検索のクエリに対する変更は、取得される検索結果には影響を与えかねない。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-130">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="f3d7f-131">エクスポートを再開すると、エクスポート ジョブの作成時に実行されたのと同じ検索クエリ ジョブが再度実行されます。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-131">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="f3d7f-132">また、エクスポートを再開すると、エクスポート先の場所にコピー Azure Storage結果が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-132">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="f3d7f-133">コピーされた以前の結果はダウンロードできません。</span><span class="sxs-lookup"><span data-stu-id="f3d7f-133">The previous results that were copied won't be available to be downloaded.</span></span>
