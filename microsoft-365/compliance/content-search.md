---
title: Microsoft 365 コンプライアンス センターでコンテンツ検索を作成して実行する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
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
description: Microsoft コンプライアンス センターのコンテンツ検索電子情報開示ツールを使用すると、さまざまな Microsoft 365 サービスでコンテンツを検索できます。
ms.openlocfilehash: a058c07d080962723e9f6bc7a150cbfb5074e7db
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311665"
---
# <a name="create-a-content-search"></a><span data-ttu-id="b0c07-103">コンテンツ検索の作成</span><span class="sxs-lookup"><span data-stu-id="b0c07-103">Create a content search</span></span>

<span data-ttu-id="b0c07-104">Microsoft 365 コンプライアンス センターのコンテンツ検索電子情報開示ツールを使用して、組織のメール、ドキュメント、インスタント メッセージングの会話などのインプレースのコンテンツを検索できます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-104">You can use the Content search eDiscovery tool in the Microsoft 365 compliance center to search for in-place content such as email, documents, and instant messaging conversations in your organization.</span></span> <span data-ttu-id="b0c07-105">このツールを使用して、次の Microsoft 365 データ ソース内のコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b0c07-105">Use this tool to search for content in these Microsoft 365 data sources:</span></span>
  
- <span data-ttu-id="b0c07-106">Exchange Online メールボックス</span><span class="sxs-lookup"><span data-stu-id="b0c07-106">Exchange Online mailboxes</span></span>

- <span data-ttu-id="b0c07-107">SharePoint Online サイトと OneDrive for Business アカウント</span><span class="sxs-lookup"><span data-stu-id="b0c07-107">SharePoint Online sites and OneDrive for Business accounts</span></span>

- <span data-ttu-id="b0c07-108">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b0c07-108">Microsoft Teams</span></span>

- <span data-ttu-id="b0c07-109">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="b0c07-109">Microsoft 365 Groups</span></span>

- <span data-ttu-id="b0c07-110">Yammer グループ</span><span class="sxs-lookup"><span data-stu-id="b0c07-110">Yammer Groups</span></span>

<span data-ttu-id="b0c07-p102">コンテンツ検索を実行すると、コンテンツの場所の数と予想される検索結果の数が検索のポップアップ情報に表示されます。検索クエリと一致するアイテムが最も多いコンテンツの場所など、統計情報をすばやく表示することもできます。検索を実行した後、結果をプレビューしたり、ローカル コンピューターにエクスポートしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-p102">After you run a search, the number of content locations and an estimated number of search results are displayed on the search flyout page. You can quickly view statistics, such as the content locations that have the most items that match the search query. After you run a search, you can preview the results or export them to a local computer.</span></span>

## <a name="create-and-run-a-search"></a><span data-ttu-id="b0c07-114">検索の作成と実行</span><span class="sxs-lookup"><span data-stu-id="b0c07-114">Create and run a search</span></span>

<span data-ttu-id="b0c07-115">Microsoft 365 コンプライアンス センターの [**コンテンツ検索**] ページに(検索を実行して結果をプレビューし、結果をエクスポートするために) アクセスするには、管理者、コンプライアンス責任者、または電子情報開示マネージャーが、セキュリティとコンプライアンス センターの電子情報開示マネージャーの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0c07-115">To access to the **Content search** page in the Microsoft 365 compliance center (to run searches and preview results and export results), an administrator, compliance officer, or eDiscovery manager must be a member of the eDiscovery Manager role group in Security & Compliance Center.</span></span> <span data-ttu-id="b0c07-116">詳細については、「[電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。電子情報開示のアクセス許可を割り当てる」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c07-116">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
  
1. <span data-ttu-id="b0c07-117"><https://compliance.microsoft.com> に移り、適切な許可が割り当てられているアカウントの証明書を使ってサインインします。</span><span class="sxs-lookup"><span data-stu-id="b0c07-117">Go to <https://compliance.microsoft.com> and sign in using the credentials of an account that's been assigned the appropriate permissions.</span></span>

2. <span data-ttu-id="b0c07-118">Microsoft 365 コンプライアンス センターの左側のナビゲーション ウィンドウで [**すべてを表示**] をクリックし、[**コンテンツ検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0c07-118">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Content search**.</span></span>

3. <span data-ttu-id="b0c07-119">[**コンテンツ検索**] ページで、[**新しい検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0c07-119">On the **Content search** page, click **New search**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b0c07-120">[**ID のリストで検索**] オプションでは、Exchange ID のリストを使用して特定のメール メッセージやその他のメールボックス アイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-120">The **Search by ID list** option lets you search for specific email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="b0c07-121">ID リスト検索を作成するには、検索する特定のメールボックス アイテムを識別するコンマ区切り値 (CSV) ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="b0c07-121">To create an ID list search, you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="b0c07-122">手順については、「[ID リスト検索の CSV ファイルを準備する](csv-file-for-an-id-list-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c07-122">For instructions, see [Prepare a CSV file for an ID list search](csv-file-for-an-id-list-content-search.md).</span></span>

4. <span data-ttu-id="b0c07-p105">検索の名前と、検索を識別するための説明 (省略可能) を入力します。検索の名前は、組織内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0c07-p105">Type a name for the search, an optional description that helps identify the search. The name of the search must be unique in your organization.</span></span>

5. <span data-ttu-id="b0c07-125">検索するコンテンツの [**場所**] ページで、検索するコンテンツの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0c07-125">On the **Locations** page, choose the content locations that you want to search.</span></span> <span data-ttu-id="b0c07-126">メールボックスとパブリック フォルダーを検索できます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-126">You can search mailboxes, sites, and public folders.</span></span>

    ![ホールドにするコンテンツの場所を選択する](../media/ContentSearchLocations.png)
  
   1. <span data-ttu-id="b0c07-128">**Exchange メールボックス**: トグルを **On** に設定し、[**ユーザー、グループ、またはチーム** の選択] をクリックして、ホールドするメールボックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0c07-128">**Exchange mailboxes**: Set the toggle to **On** and then click **Choose users, groups, or teams** to specify the mailboxes to place on hold.</span></span> <span data-ttu-id="b0c07-129">検索ボックスを使用して、ユーザーのメールボックス、および配布グループ (グループ メンバーのメールボックスにホールドを適用するため) を検索し、ホールドを適用します。</span><span class="sxs-lookup"><span data-stu-id="b0c07-129">Use the search box to find user mailboxes and distribution groups (to place a hold on the mailboxes of group members) to place on hold.</span></span> <span data-ttu-id="b0c07-130">Microsoft チームに関連付けられているメールボックス (チャネル メッセージの場合)、Office 365 グループ、および Yammer グループを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-130">You can also search the mailbox associated with a Microsoft Team (for channel messages), Office 365 Group, and Yammer Group.</span></span> <span data-ttu-id="b0c07-131">メールボックスに保存されているアプリケーション データの詳細については、[「eDiscovery のメールボックスに保存されているコンテンツ」](what-is-stored-in-exo-mailbox.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c07-131">For more information about the application data stored in mailboxes, see [Content stored in mailboxes for eDiscovery](what-is-stored-in-exo-mailbox.md).</span></span>

   2. <span data-ttu-id="b0c07-132">**SharePoint サイト**: トグルを **On** に設定し、[**サイトの選択]** をクリックして、ホールドする SharePoint サイトと OneDrive アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0c07-132">**SharePoint sites**: Set the toggle to **On** and then click **Choose sites** to specify SharePoint sites and OneDrive accounts to place on hold.</span></span> <span data-ttu-id="b0c07-133">ホールドを適用する各サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0c07-133">Type the URL for each site that you want to place on hold.</span></span> <span data-ttu-id="b0c07-134">また、Microsoft チーム、Office 365 グループ、または Yammer グループの SharePoint サイトの URL を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-134">You can also add the URL for the SharePoint site for a Microsoft Team, Office 365 Group, or Yammer Group.</span></span>
  
   3. <span data-ttu-id="b0c07-135">**Exchange パブリック フォルダー**: **[オン]** に切り替えて、Exchange Online 組織のすべてのパブリック フォルダーをホールドにします。</span><span class="sxs-lookup"><span data-stu-id="b0c07-135">**Exchange public folders**: Set the toggle to **On** to put all public folders in your Exchange Online organization on hold.</span></span> <span data-ttu-id="b0c07-136">ただし、ホールドにする特定のパブリック フォルダーを選ぶことはできません。</span><span class="sxs-lookup"><span data-stu-id="b0c07-136">You can't choose specific public folders to put on hold.</span></span> <span data-ttu-id="b0c07-137">パブリック フォルダーを保留にしない場合は、切り替えスイッチをオフのままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-137">Leave the toggle switch off if you don't want to put a hold on public folders.</span></span>
  
   4. <span data-ttu-id="b0c07-138">オンプレミスのユーザーの Teams コンテンツを検索するには、このチェック ボックスをオンにした状態にします。</span><span class="sxs-lookup"><span data-stu-id="b0c07-138">Keep this checkbox selected to search for Teams content for on-premises users.</span></span> <span data-ttu-id="b0c07-139">たとえば、組織内のすべての Exchange メールボックスを検索してからこのチェック ボックスも選択すると、オンプレミスのユーザーの Teams チャット データを格納するのに使用されるクラウドベースの記憶域が検索の範囲に含まれます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-139">For example, if you search all Exchange mailboxes in the organization and this checkbox is selected, the cloud-based storage used to store Teams chat data for on-premises users will be included in the scope of the search.</span></span> <span data-ttu-id="b0c07-140">詳細については、「[PowerShell を使用してオンプレミス ユーザーの Teams チャット データを検索する](search-cloud-based-mailboxes-for-on-premises-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c07-140">For more information, see [Search for Teams chat data for on-premises users](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>

6. <span data-ttu-id="b0c07-141">[**検索条件の定義**] ページで、キーワード クエリを入力して作成し、必要に応じて検索クエリに条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="b0c07-141">On the **Define your search conditions** page, type a keyword query and add conditions to the search query if necessary.</span></span>

   ![検索クエリの構成](../media/ContentSearchQuery.png)

   1. <span data-ttu-id="b0c07-143">キーワード、送信日や受信日などのメッセージ プロパティ、またはファイル名やドキュメントの最終更新日などのドキュメント プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-143">Specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="b0c07-144">**AND**、**OR**、**NOT**、**NEAR** などのブール演算子を使用するより複雑なクエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-144">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="b0c07-145">このキーワード ボックスを空のままにすると、指定したコンテンツの場所にあるすべてのコンテンツが検索結果に入ります。</span><span class="sxs-lookup"><span data-stu-id="b0c07-145">If you leave the keyword box empty, all content located in the specified content locations is included in the search results.</span></span> <span data-ttu-id="b0c07-146">詳細については、「[電子情報開示のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c07-146">For more information, see [Keyword queries and search conditions for eDiscovery](keyword-queries-and-search-conditions.md).</span></span>

   2. <span data-ttu-id="b0c07-147">また、[**キーワード リストの表示**] チェック ボックスをオンにして、各行にキーワードを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-147">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row.</span></span> <span data-ttu-id="b0c07-148">この場合、作成される検索クエリでは、各行のキーワードは **OR** 演算子の機能に似た論理演算子 (**c:s**) によって接続されます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-148">If you do this, the keywords on each row are connected by a logical operator (**c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span>

      <span data-ttu-id="b0c07-149">キーワード リストを使用する理由</span><span class="sxs-lookup"><span data-stu-id="b0c07-149">Why use the keyword list?</span></span> <span data-ttu-id="b0c07-150">各キーワードと一致するアイテム数を示す統計情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-150">You can get statistics that show how many items match each keyword.</span></span> <span data-ttu-id="b0c07-151">これは、最も有効な (および最も有効でない) キーワードをすばやく識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-151">This can help you quickly identify which keywords are the most (and least) effective.</span></span> <span data-ttu-id="b0c07-152">行で (かっこで囲まれた) キーワード フレーズを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-152">You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span> <span data-ttu-id="b0c07-153">キーワード リストの詳細については、「[検索のキーワード統計](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c07-153">For more information about the keyword list and search statistics, see [Get keyword statistics for searches](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).</span></span>

      > [!NOTE]
      > <span data-ttu-id="b0c07-154">大規模なキーワード リストによって生じる問題を軽減するため、キーワード リストの行は最大 20 行に設定されています。</span><span class="sxs-lookup"><span data-stu-id="b0c07-154">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.</span></span>

   3. <span data-ttu-id="b0c07-155">検索クエリに条件を追加して、検索を絞り込み、さらに絞り込まれた結果のセットを返すようにできます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-155">You can add search conditions to narrow a search and return a more refined set of results.</span></span> <span data-ttu-id="b0c07-156">各条件によって、作成された検索クエリに句が追加され、ユーザーが検索を開始するとそのクエリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-156">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="b0c07-157">条件は、 **AND** 演算子の機能に似た論理演算子 (**c:c**) によってキーワードのクエリ (キーワード ボックスで指定される) と論理的に接続されます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-157">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="b0c07-158">つまり、検索結果に含まれるためには、アイテムはキーワード クエリと 1 つまたは複数の条件の両方を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0c07-158">That means that items have to satisfy both the keyword query and one or more conditions to be included in the results.</span></span> <span data-ttu-id="b0c07-159">このように、条件を使用して結果を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="b0c07-159">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="b0c07-160">検索クエリで使用できる条件のリストと説明については、[「検索条件」](keyword-queries-and-search-conditions.md#search-conditions)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c07-160">For a list and description of conditions that you can use in a search query, see [Search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>

7. <span data-ttu-id="b0c07-161">検索の設定を確認し (必要に応じて編集し)、検索を送信して開始します。</span><span class="sxs-lookup"><span data-stu-id="b0c07-161">Review the search settings (and edit if necessary), and then submit the search to start it.</span></span>
  
<span data-ttu-id="b0c07-162">このコンテンツ検索に再度アクセスするか、**コンテンツ検索** ページにリストされている他のコンテンツ検索にアクセスするには、検索を選択し、**[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0c07-162">To access this content search again or access other content searches listed on the **Content search** page, select the search and then click **Open**.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="b0c07-163">次の手順</span><span class="sxs-lookup"><span data-stu-id="b0c07-163">Next steps</span></span>

<span data-ttu-id="b0c07-164">コンテンツ検索を作成して実行した後に行う手順の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="b0c07-164">Here's a list of next steps to perform after you create and run a Content search.</span></span>

- [<span data-ttu-id="b0c07-165">検索結果をプレビューする</span><span class="sxs-lookup"><span data-stu-id="b0c07-165">Preview search results</span></span>](preview-ediscovery-search-results.md)

- [<span data-ttu-id="b0c07-166">検索結果のキーワード統計を表示する</span><span class="sxs-lookup"><span data-stu-id="b0c07-166">View statistics for search results</span></span>](view-keyword-statistics-for-content-search.md)

- [<span data-ttu-id="b0c07-167">検索結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b0c07-167">Export search results</span></span>](export-search-results.md)

- [<span data-ttu-id="b0c07-168">検索レポートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b0c07-168">Export a search report</span></span>](export-a-content-search-report.md)
