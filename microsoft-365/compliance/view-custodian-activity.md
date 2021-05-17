---
title: カストディアンの監査アクティビティを表示する
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
ms.assetid: ''
description: ケース内Advanced eDiscovery管理ツールを使用して、アクティビティに簡単にアクセスして検索します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f9e96d0b5dd3bf42dbba56a6e1be91014485ce98
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024767"
---
# <a name="view-custodian-audit-activity"></a><span data-ttu-id="a04a0-103">カストディアンの監査アクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="a04a0-103">View custodian audit activity</span></span>

<span data-ttu-id="a04a0-104">ユーザーが特定のドキュメントを表示したかどうか、またはメールボックスからアイテムを削除したかどうかを確認する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="a04a0-104">Need to find if a user viewed a specific document or purged an item from their mailbox?</span></span> <span data-ttu-id="a04a0-105">Advanced eDiscoveryは、セキュリティ コンプライアンス センターの既存の監査ログ検索ツール&統合されています。</span><span class="sxs-lookup"><span data-stu-id="a04a0-105">Advanced eDiscovery is now integrated with the existing audit log search tool in the Security & Compliance Center.</span></span> <span data-ttu-id="a04a0-106">この埋め込みエクスペリエンスを使用すると、Advanced eDiscovery カストディアン管理ツールを使用して、ケース内の保管担当者のアクティビティに簡単にアクセスして検索することで、調査を容易に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-106">Using this embedded experience, you can use the Advanced eDiscovery Custodian Management tool to facilitate your investigation by easily accessing and searching the activity for custodians within your case.</span></span>

## <a name="get-permissions"></a><span data-ttu-id="a04a0-107">アクセス許可の取得</span><span class="sxs-lookup"><span data-stu-id="a04a0-107">Get permissions</span></span>

<span data-ttu-id="a04a0-108">監査ログを検索するには、Exchange Online で閲覧限定の監査ログまたは監査ログの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a04a0-108">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the audit log.</span></span> <span data-ttu-id="a04a0-109">既定では、これらの役割は Exchange 管理センターの [アクセス許可] ページでコンプライアンス管理役割グループまたは組織管理役割グループに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="a04a0-109">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="a04a0-110">最小限の特権レベルで Advanced eDiscovery 監査ログを検索する権限をユーザーに付与するには、Exchange Online でカスタムの役割グループを作成し、閲覧限定の監査ログまたは監査ログの役割を追加し、この新しい役割グループのメンバーとしてユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a04a0-110">To give a user the ability to search the Advanced eDiscovery audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="a04a0-111">詳細については、「Exchange Online で役割グループを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a04a0-111">For more information, see Manage role groups in Exchange Online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a04a0-112">セキュリティ & コンプライアンス センターの [アクセス許可] ページでユーザーに View-Only 監査ログまたは監査ログの役割を割り当てると、監査ログを検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="a04a0-112">If you assign a user the View-Only Audit Logs or Audit Logs role on the Permissions page in the Security & Compliance Center, they won't be able to search the audit log.</span></span> <span data-ttu-id="a04a0-113">Exchange Online でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a04a0-113">You have to assign the permissions in Exchange Online.</span></span> <span data-ttu-id="a04a0-114">これは、監査ログの検索に使用される基本のコマンドレットが ExchangeOnline コマンドレットだからです。</span><span class="sxs-lookup"><span data-stu-id="a04a0-114">This is because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet.</span></span>

## <a name="step-1-search-the-audit-log-for-activities-performed-by-a-custodian"></a><span data-ttu-id="a04a0-115">手順 1: 保管担当者によって実行されるアクティビティの監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="a04a0-115">Step 1: Search the audit log for activities performed by a custodian</span></span>

1. <span data-ttu-id="a04a0-116">[電子情報開示 **] に> Advanced eDiscovery** ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-116">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="a04a0-117">[ソース] **タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="a04a0-117">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="a04a0-118">[カ **ストディアン] ページで**、リストからカストディアンを選択し、フライアウト ページで [保管担当者のアクティビティの表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a04a0-118">On the **Custodians** page, select a custodian from the list, and then click **View custodian activity** on the flyout page.</span></span>

    <span data-ttu-id="a04a0-119">[保管担当者のアクティビティ] 検索ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-119">The Custodian activities search page is displayed.</span></span> <span data-ttu-id="a04a0-120">前の手順で選択したカストディアンが [カストディアン] ドロップダウン **ボックスに表示** されます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-120">Note the custodian you selected in the previous step is displayed in the **Custodian** drop-down box.</span></span> <span data-ttu-id="a04a0-121">ドロップダウン ボックスで別の保管担当者を選択できますが、一度に検索できるアクティビティは 1 人の保管担当者のみです。</span><span class="sxs-lookup"><span data-stu-id="a04a0-121">You can select different custodians in the drop-down box, but you can only search for activities for one custodian at a time.</span></span>

    ![カストディアンアクティビティの検索ページ](../media/AeDCustodianActivities1.png)
   
4. <span data-ttu-id="a04a0-123">次の検索条件を設定します。</span><span class="sxs-lookup"><span data-stu-id="a04a0-123">Configure the following search criteria:</span></span>
      
   1. <span data-ttu-id="a04a0-124">**[アクティビティ** ] - ドロップダウン リストをクリックして、検索できるアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="a04a0-124">**Activities** - Click the drop-down list to display the activities that you can search for.</span></span> <span data-ttu-id="a04a0-125">検索の実行後、選択したアクティビティの監査ログ エントリのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-125">After you run the search, only the audit records for the selected activities are displayed.</span></span> <span data-ttu-id="a04a0-126">[すべてのアクティビティ **の結果を表示する** ] を選択すると、他の検索条件に一致する保管担当者が実行したすべてのアクティビティの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-126">Selecting **Show results for all activities** will display results for all activities performed by the custodian that match the other search criteria.</span></span>

      ![アクティビティの一覧](../media/CustodianActivityAudit.PNG)
      
   1. <span data-ttu-id="a04a0-128">**開始日と終了日** - 日付と時刻の範囲を選択して、その期間に発生したイベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="a04a0-128">**Start date and End date** - Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="a04a0-129">既定では、最後の 7 日間が選択されています。</span><span class="sxs-lookup"><span data-stu-id="a04a0-129">The last seven days are selected by default.</span></span> <span data-ttu-id="a04a0-130">日付と時間は、協定世界時 (UTC) 形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="a04a0-130">The date and time are presented in Coordinated Universal Time (UTC) format.</span></span> <span data-ttu-id="a04a0-131">指定できる最大日付範囲は 1 年です。</span><span class="sxs-lookup"><span data-stu-id="a04a0-131">The maximum date range that you can specify is one year.</span></span>
      
   1. <span data-ttu-id="a04a0-132">**カストディアン** - このボックスをクリックし、検索結果を表示する特定の保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="a04a0-132">**Custodians** - Click in this box and then select a specific custodian to display search results for.</span></span> <span data-ttu-id="a04a0-133">このボックスで選択したユーザーが実行した選択したアクティビティの監査レコードが、結果の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-133">Audit records for the selected activity performed by the users you select in this box are displayed in the list of results.</span></span>
      
5. <span data-ttu-id="a04a0-134">上</span><span class="sxs-lookup"><span data-stu-id="a04a0-134">Click</span></span> ![[検索] ボタン](../media/SearchButton.PNG)  <span data-ttu-id="a04a0-136">をクリックして、検索条件を使用して検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="a04a0-136">to run the search using your search criteria.</span></span> <span data-ttu-id="a04a0-137">検索結果が読み込まれ、しばらくすると、[保管者のアクティビティ] 検索ページの [結果] に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-137">The search results are loaded, and after a few moments they are displayed under Results on the Custodian Activities search page.</span></span> 

## <a name="step-2-view-the-audit-log-search-results"></a><span data-ttu-id="a04a0-138">手順 2: 監査ログの検索結果を表示する</span><span class="sxs-lookup"><span data-stu-id="a04a0-138">Step 2: View the audit log search results</span></span>

<span data-ttu-id="a04a0-139">監査ログ検索の結果は、[カストディアン監査ログ] ページの [結果] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-139">The results of an audit log search are displayed under Results on the Custodian Audit log page.</span></span> <span data-ttu-id="a04a0-140">最大 5,000 (最新) のイベントが 150 イベントずつ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-140">A maximum of 5,000 (newest) events are displayed in increments of 150 events.</span></span> <span data-ttu-id="a04a0-141">より多くのイベントを表示するには、[結果] ウィンドウでスクロール バーを使用するか、Shift + End キーを押して次の 150 イベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-141">To display more events you can use the scroll bar in the Results pane or you can press Shift + End to display the next 150 events.</span></span>

<span data-ttu-id="a04a0-142">検索結果には、検索によって返された各イベントに関する次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-142">The results contain the following information about each event returned by the search.</span></span>
- <span data-ttu-id="a04a0-143">[**日付**]: イベントが発生した日付と時刻 (UTC 形式)。</span><span class="sxs-lookup"><span data-stu-id="a04a0-143">**Date**: The date and time (in UTC format) when the event occurred.</span></span>

- <span data-ttu-id="a04a0-144">[**IP アドレス**]: アクティビティがログに記録されたときに使用されたデバイスの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="a04a0-144">**IP address**: The IP address of the device that was used when the activity was logged.</span></span> <span data-ttu-id="a04a0-145">IP アドレスは、IPv4 または IPv6 アドレスの形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-145">The IP address is displayed in either an IPv4 or IPv6 address format.</span></span>

- <span data-ttu-id="a04a0-146">[**ユーザー**]: イベントをトリガーしたアクションを実行したユーザー (またはサービス アカウント)。</span><span class="sxs-lookup"><span data-stu-id="a04a0-146">**User**: The user (or service account) who performed the action that triggered the event.</span></span>

- <span data-ttu-id="a04a0-147">[**アクティビティ**]: ユーザーが実行したアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="a04a0-147">**Activity**: The activity performed by the user.</span></span> <span data-ttu-id="a04a0-148">この値は [アクティビティ] ドロップダウン リストで選択したアクティビティに対応します。</span><span class="sxs-lookup"><span data-stu-id="a04a0-148">This value corresponds to the activities that you selected in the Activities drop down list.</span></span> <span data-ttu-id="a04a0-149">Exchange 管理者監査ログのイベントの場合、この列の値は、Exchange コマンドレットになります。</span><span class="sxs-lookup"><span data-stu-id="a04a0-149">For an event from the Exchange admin audit log, the value in this column is an Exchange cmdlet.</span></span>

- <span data-ttu-id="a04a0-150">[**アイテム**]: 対応するアクティビティの結果として作成または変更されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a04a0-150">**Item**: The object that was created or modified as a result of the corresponding activity.</span></span> <span data-ttu-id="a04a0-151">たとえば、表示または変更されたファイルまたは更新されたユーザー アカウントなどです。</span><span class="sxs-lookup"><span data-stu-id="a04a0-151">For example, the file that was viewed or modified or the user account that was updated.</span></span> <span data-ttu-id="a04a0-152">すべてのアクティビティにこの列の値があるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="a04a0-152">Not all activities have a value in this column.</span></span>

- <span data-ttu-id="a04a0-153">[**詳細**]: アクティビティに関する追加の詳細。</span><span class="sxs-lookup"><span data-stu-id="a04a0-153">**Detail**: Additional detail about an activity.</span></span> <span data-ttu-id="a04a0-154">ここでも、すべてのアクティビティに値があるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="a04a0-154">Again, not all activities will have a value.</span></span>

## <a name="step-3-filter-the-search-results"></a><span data-ttu-id="a04a0-155">手順 3: 検索結果をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="a04a0-155">Step 3: Filter the search results</span></span>

<span data-ttu-id="a04a0-156">並べ替えに加えて、監査ログの検索の結果をフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-156">In addition to sorting, you can also filter the results of an audit log search.</span></span> <span data-ttu-id="a04a0-157">これにより、特定のユーザーまたはアクティビティの結果をすばやくフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-157">This can help you quickly filter the results for a specific user or activity.</span></span> 

<span data-ttu-id="a04a0-158">結果をフィルター処理するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a04a0-158">To filter the results:</span></span>

 1. <span data-ttu-id="a04a0-159">監査ログ検索を作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="a04a0-159">Create and run an audit log search.</span></span>
  
2. <span data-ttu-id="a04a0-160">結果が表示されたら、[**結果をフィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a04a0-160">When the results are displayed, click **Filter results**.</span></span>
 
3. <span data-ttu-id="a04a0-161">各列見出しの下にキーワード ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-161">Keyword boxes are displayed under each column header.</span></span>
  
4. <span data-ttu-id="a04a0-p115">フィルター処理の対象となる列の列見出しの下に表示されたボックスのいずれかをクリックして語句を入力します。検索結果が動的に調整され、フィルターに一致するイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-p115">Click one of the boxes under a column header and type a word or phrase, depending on the column you're filtering on. The results will dynamically readjust to display the events that match your filter.</span></span>
  
5. <span data-ttu-id="a04a0-164">フィルターをクリアするには、フィルター ボックスの [**X**] をクリックするか、[**フィルターの非表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a04a0-164">To clear a filter, click the **X** in the filter box or just click **Hide filtering**.</span></span>

## <a name="export-the-search-results-to-a-file"></a><span data-ttu-id="a04a0-165">検索結果をファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="a04a0-165">Export the search results to a file</span></span>

<span data-ttu-id="a04a0-p116">監査ログの検索結果をローカル コンピューター上のコンマ区切り値 (CSV) ファイルにエクスポートできます。このファイルを Microsoft Excel で開いて、検索、並べ替え、フィルター処理、複数値セルを含む単一列の複数列への分割などの機能を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-p116">You can export the results of an audit log search to a comma separated value (CSV) file on your local computer. You can open this file in Microsoft Excel and use features such as search, sorting, filtering, and splitting a single column (that contains multi-value cells) into multiple columns.</span></span>

1. <span data-ttu-id="a04a0-168">監査ログの検索を実行して、目的の結果が得られるまで検索条件を変更します。</span><span class="sxs-lookup"><span data-stu-id="a04a0-168">Run an audit log search, and then revise the search criteria until you have the desired results.</span></span>
  
2. <span data-ttu-id="a04a0-169">[結果のエクスポート] をクリックして、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a04a0-169">Click Export results and select one of the following options:</span></span>

    - <span data-ttu-id="a04a0-170">**読み込まれた結果を保存する:**[カストディアン監査ログの検索] ページの[結果] に表示されるエントリのみをエクスポートするには、この **オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="a04a0-170">**Save loaded results:** Choose this option to export only the entries that are displayed under **Results** on the **Custodian Audit log search** page.</span></span> <span data-ttu-id="a04a0-171">ダウンロードした CSV ファイルには、ページに表示されている同じ列 (およびデータ) (日付、ユーザー、アクティビティ、アイテム、詳細) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a04a0-171">The CSV file that is downloaded contains the same columns (and data) displayed on the page (Date, User, Activity, Item, and Details).</span></span> <span data-ttu-id="a04a0-172">監査ログ エントリの詳細情報を含む CSV ファイルには、追加の列 ("More" というタイトル) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a04a0-172">An additional column (titled **More**) is included in the CSV file that contains more information from the audit log entry.</span></span> <span data-ttu-id="a04a0-173">[監査ログの検索] ページに読み込まれた (および表示可能な) 同じ結果をエクスポートしているため、最大 5,000 件のエントリがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-173">Because you're exporting the same results that are loaded (and viewable) on the Audit log search page, a maximum of 5,000 entries are exported.</span></span>
        
    - <span data-ttu-id="a04a0-174">**すべての結果をダウンロードします。** 検索条件を満たす監査ログからすべてのエントリをエクスポートするには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a04a0-174">**Download all results:** Choose this option to export all entries from the audit log that meet the search criteria.</span></span> <span data-ttu-id="a04a0-175">検索結果の大規模なセットの場合は、このオプションを選択して、カストディアン監査ログ検索ページに表示できる 5,000 件の結果に加えて、監査ログからすべてのエントリ **をダウンロードします** 。</span><span class="sxs-lookup"><span data-stu-id="a04a0-175">For a large set of search results, choose this option to download all entries from the audit log in addition to the 5,000 results that can be displayed on the **Custodian Audit log** search page.</span></span> <span data-ttu-id="a04a0-176">このオプションを使用すると、監査ログから CSV ファイルに生データがダウンロードされ、AuditData という名前の列に監査ログ エントリからの追加情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-176">This option will download the raw data from the audit log to a CSV file, and contains additional information from the audit log entry in a column named AuditData.</span></span> <span data-ttu-id="a04a0-177">このエクスポート オプションを選択した場合、ファイルが他のオプションを選択した場合にダウンロードされるファイルよりはるかに大きくなる可能性があるため、ファイルのダウンロードには時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="a04a0-177">It may take longer to download the file if you choose this export option because the file may be much larger than the one that's downloaded if you choose the other option.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="a04a0-p119">1 回の監査ログの検索で、最大 50,000 件のエントリを CSV ファイルにダウンロードできます。50,000 件のエントリが CSV ファイルにダウンロードされた場合、検索条件に一致したエントリが 50,000 件を超える可能性があります。この制限を超えてエクスポートするには、日付範囲を使用して監査ログ エントリの件数を削減してみてください。50,000 件を超えるエントリをエクスポートするには、日付範囲を狭めて検索を複数回実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a04a0-p119">You can download a maximum of 50,000 entries to a CSV file from a single audit log search. If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria. To export more than this limit, try using a date range to reduce the number of audit log entries. You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>
        

3. <span data-ttu-id="a04a0-182">エクスポート オプションを選択すると、ウィンドウの下部にメッセージが表示され、CSV ファイルを開く、ダウンロード フォルダーに保存する、または特定のフォルダーに保存するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a04a0-182">After you select an export option, a message is displayed at the bottom of the window that prompts you to open the CSV file, save it to the Downloads folder, or save it to a specific folder</span></span>

<span data-ttu-id="a04a0-183">監査ログ検索結果の表示、フィルター処理、またはエクスポートの詳細については、「Security & コンプライアンス センターで監査ログ [を検索する」を参照してください](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="a04a0-183">For more information about viewing, filtering, or exporting audit log search results, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
