---
title: PST ファイルをインポートするときに、データをフィルター処理する
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
ms.custom: seo-marvel-apr2020
description: PST ファイルをインポートする際に、Microsoft 365 インポート サービスのインテリジェント インポート機能を使用してデータをフィルター処理するMicrosoft 365。
ms.openlocfilehash: fc89467e3ea9c0af86ec6b9ef6a9d7d61079e116
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730572"
---
# <a name="filter-data-when-importing-pst-files"></a><span data-ttu-id="1428f-103">PST ファイルをインポートするときに、データをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="1428f-103">Filter data when importing PST files</span></span>

<span data-ttu-id="1428f-104">ターゲット メールボックスに実際にインポートされる PST ファイル内のアイテムをフィルター処理するには、Microsoft 365 インポート サービスの新しいインテリジェント インポート機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="1428f-104">Use the new Intelligent Import feature in the Microsoft 365 Import service to filter the items in PST files that actually get imported to the target mailboxes.</span></span> <span data-ttu-id="1428f-105">次に、動作のしくみを示します。</span><span class="sxs-lookup"><span data-stu-id="1428f-105">Here's how it works:</span></span>
  
- <span data-ttu-id="1428f-106">PST インポート ジョブを作成して送信すると、PST ファイルが Microsoft クラウドの Azure ストレージ領域にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="1428f-106">After you create and submit a PST import job, PST files are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
  
- <span data-ttu-id="1428f-107">Microsoft 365、メールボックス アイテムの年齢と PST ファイルに含まれるさまざまなメッセージの種類を識別して、安全かつ安全な方法で PST ファイル内のデータを分析します。</span><span class="sxs-lookup"><span data-stu-id="1428f-107">Microsoft 365 analyzes the data in the PST files, in a safe and secure manner, by identifying the age of the mailbox items and the different message types included in the PST files.</span></span>
  
- <span data-ttu-id="1428f-108">分析が完了し、データをインポートする準備ができたら、PST ファイル内のすべてのデータを現在の状態でインポートするか、インポートするデータを制御するフィルターを設定してインポートされるデータをトリミングするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="1428f-108">When the analysis is complete and the data is ready to import, you have the option to import all data in the PST files as is or trim the data that's imported by setting filters that control what data gets imported.</span></span> <span data-ttu-id="1428f-109">たとえば、次のオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1428f-109">For example, you can choose to:</span></span>
  
  - <span data-ttu-id="1428f-110">特定の年齢のアイテムのみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1428f-110">Import only items of a certain age.</span></span>
  
  - <span data-ttu-id="1428f-111">選択したメッセージの種類をインポートします。</span><span class="sxs-lookup"><span data-stu-id="1428f-111">Import selected message types.</span></span>
  
  - <span data-ttu-id="1428f-112">特定のユーザーが送信または受信したメッセージを除外します。</span><span class="sxs-lookup"><span data-stu-id="1428f-112">Exclude messages sent or received by specific people.</span></span>
  
- <span data-ttu-id="1428f-113">フィルター設定を構成した後Microsoft 365、フィルター条件を満たすデータのみをインポート ジョブで指定されたターゲット メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="1428f-113">After you configure the filter settings, Microsoft 365 imports only the data that meets the filtering criteria to the target mailboxes specified in the import job.</span></span>
  
<span data-ttu-id="1428f-114">次の図は、インテリジェント インポート プロセスを示し、実行するタスクと、ユーザーが実行するタスクを強調表示Office 365。</span><span class="sxs-lookup"><span data-stu-id="1428f-114">The following graphic shows the Intelligent Import process, and highlights the tasks you perform and the tasks performed by Office 365.</span></span>
  
![インテリジェント インポート プロセス (Office 365](../media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="create-a-pst-import-job"></a><span data-ttu-id="1428f-116">PST インポート ジョブの作成</span><span class="sxs-lookup"><span data-stu-id="1428f-116">Create a PST import job</span></span>

- <span data-ttu-id="1428f-117">このトピックの手順では、ネットワークアップロードまたはドライブ配布を使用して、Office 365 インポート サービスで PST インポート ジョブを作成したと仮定します。</span><span class="sxs-lookup"><span data-stu-id="1428f-117">The steps in this topic assume that you've created a PST import job in the Office 365 Import service by using network upload or drive shipping.</span></span> <span data-ttu-id="1428f-118">手順については、次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1428f-118">For step-by-step instructions, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="1428f-119">ネットワーク アップロードを使用して PST ファイルを Office 365 にインストールする</span><span class="sxs-lookup"><span data-stu-id="1428f-119">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
    
  - [<span data-ttu-id="1428f-120">ドライブの送付を使用して PST ファイルを Office 365 にインポートする</span><span class="sxs-lookup"><span data-stu-id="1428f-120">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- <span data-ttu-id="1428f-121">ネットワーク アップロードを使用してインポート ジョブを作成すると、セキュリティ & コンプライアンス センターの [インポート] ページのインポート ジョブの状態が [分析中] に設定されます。つまり、Microsoft 365 はアップロードした PST ファイル内のデータを分析しています。</span><span class="sxs-lookup"><span data-stu-id="1428f-121">After you create an import job by using network upload, the status for the import job on the Import page in the Security & Compliance Center is set to **Analysis in progress**, which means that Microsoft 365 is analyzing the data in the PST files that you uploaded.</span></span> <span data-ttu-id="1428f-122">[**更新]** ![ を ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) クリックして、インポート ジョブの状態を更新します。</span><span class="sxs-lookup"><span data-stu-id="1428f-122">Click **Refresh**![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the status for the import job.</span></span> 
    
- <span data-ttu-id="1428f-123">ドライブ配布インポート ジョブの場合、Microsoft データセンター担当者がハード ドライブを受け取り、組織の Azure ストレージ領域に PST ファイルをアップロードした後、データは Microsoft 365 によって分析されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-123">For drive shipping import jobs, the data will be analyzed by Microsoft 365 after Microsoft datacenter personnel receive your hard drive and upload the PST files to the Azure storage area for your organization.</span></span>
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a><span data-ttu-id="1428f-124">メールボックスにインポートされるデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="1428f-124">Filter data that gets imported to mailboxes</span></span>

<span data-ttu-id="1428f-125">PST インポート ジョブを作成した後、次の手順に従ってデータをフィルター処理してから、データを別のユーザーにインポートOffice 365。</span><span class="sxs-lookup"><span data-stu-id="1428f-125">After you've created a PST import job, follow these steps to filter the data before you import it to Office 365.</span></span>
  
1. <span data-ttu-id="1428f-126"><https://compliance.microsoft.com> に移動し、組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="1428f-126">Go to <https://compliance.microsoft.com> and sign in using the credentials for an administrator account in your organization.</span></span>
    
2. <span data-ttu-id="1428f-127">Microsoft 365 コンプライアンス センターの左のウィンドウで、[**情報ガバナンス**] \> [**インポート**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1428f-127">In the left pane of the Microsoft 365 compliance center, click **Information governance** \> **Import**.</span></span>
    
    <span data-ttu-id="1428f-128">組織のインポート ジョブが [インポート] タブに **表示** されます。[**状態] 列の** **[** 分析の完了] 値は、Microsoft 365によって分析され、インポートする準備ができているインポート ジョブを示します。</span><span class="sxs-lookup"><span data-stu-id="1428f-128">The import jobs for your organization are listed on the **Import** tab. The **Analysis completed** value in the **Status** column indicates the import jobs that have been analyzed by Microsoft 365 and are ready for you to import.</span></span>
    
    ![分析の完全な状態は、Microsoft 365 PST ファイル内のデータを分析したかどうかを示します。](../media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. <span data-ttu-id="1428f-130">完了するインポート ジョブを選択し、[インポートして完了] をクリック **Office 365。**</span><span class="sxs-lookup"><span data-stu-id="1428f-130">Select the import job that you want to complete and click **Import to Office 365**.</span></span>
  
    <span data-ttu-id="1428f-131">PST ファイルに関する情報とインポート ジョブに関するその他の情報を示すポップアップ ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-131">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>

4. <span data-ttu-id="1428f-132">[インポート **] をクリックしてOffice 365** します。</span><span class="sxs-lookup"><span data-stu-id="1428f-132">Click **Import to Office 365**.</span></span>
    
    <span data-ttu-id="1428f-133">[**データのフィルター処理**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-133">The **Filter your data** page is displayed.</span></span> <span data-ttu-id="1428f-134">インポート ジョブの PST ファイル内のデータに関するデータ分析情報が含まれており、データの年齢に関する情報も含めます。</span><span class="sxs-lookup"><span data-stu-id="1428f-134">It contains data insights about the data in the PST files for the import job, including information about the age of the data.</span></span> 
    
    ![[データのフィルター] ページには、インポート ジョブの PST ファイルのデータ分析情報が表示されます。](../media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. <span data-ttu-id="1428f-136">Microsoft 365 にインポートされたデータをトリミングするかどうかに基づいて、[データをフィルター処理しますか **?**</span><span class="sxs-lookup"><span data-stu-id="1428f-136">Based on whether or not you want to trim the data that's imported to Microsoft 365, under **Do you want to filter your data?**, do one of the following:</span></span>
  
    <span data-ttu-id="1428f-137">a.</span><span class="sxs-lookup"><span data-stu-id="1428f-137">a.</span></span> <span data-ttu-id="1428f-138">[ **はい] をクリック** し、インポートする前にフィルター処理してインポートするデータをトリミングし、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1428f-138">Click **Yes, I want to filter it before importing** to trim the data that you import, and then click **Next**.</span></span>
  
    <span data-ttu-id="1428f-139">[**データのインポート] Office 365ページ** には、実行した分析の詳細なデータMicrosoft 365表示されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-139">The **Import data to Office 365 page** page is displayed with detailed data insights from the analysis that Microsoft 365 performed.</span></span> 
  
    ![Microsoft 365 PST ファイルの分析から詳細なデータ分析を表示する](../media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    <span data-ttu-id="1428f-141">このページのグラフには、インポートされるデータの量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-141">The graph on this page shows the amount of data that will be imported.</span></span> <span data-ttu-id="1428f-142">PST ファイルにある各メッセージの種類に関する情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-142">Information about each message type found in the PST files is displayed in the graph.</span></span> <span data-ttu-id="1428f-143">各バーにカーソルを合わせると、そのメッセージの種類に関する特定の情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="1428f-143">You can hover the cursor over each bar to display specific information about that message type.</span></span> <span data-ttu-id="1428f-144">また、PST ファイルの分析に基づいて年齢の値が異なるドロップダウン リストも表示されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-144">There is also a drop-down list with different age values based on the analysis of the PST files.</span></span> <span data-ttu-id="1428f-145">ドロップダウン リストで年齢を選択すると、グラフが更新され、選択した年齢に対してインポートされるデータの量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-145">When you select an age in the drop-down list, the graph is updated to show how much data will be imported for the selected age.</span></span> 
  
    <span data-ttu-id="1428f-146">b.</span><span class="sxs-lookup"><span data-stu-id="1428f-146">b.</span></span> <span data-ttu-id="1428f-147">インポートされるデータの量を減らすために追加フィルターを構成するには、[その他のフィルター オプション] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1428f-147">To configure addition filters to reduce the amount of data that's imported, click **More filtering options**.</span></span>
  
    ![[その他のオプション] ページでフィルターを構成して、インポートされたデータをトリミングする](../media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    <span data-ttu-id="1428f-149">次のフィルターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1428f-149">You can configure these filters:</span></span>
  
      - <span data-ttu-id="1428f-150">**[年齢** ] - 指定した年齢より新しいアイテムのみをインポートするように、年齢を選択します。</span><span class="sxs-lookup"><span data-stu-id="1428f-150">**Age** - Select an age so only items that are newer than the specified age will be imported.</span></span> <span data-ttu-id="1428f-151">年齢フィルター [の年齢バケット](#more-information)をMicrosoft 365する方法については、「詳細」セクション **を参照** してください。</span><span class="sxs-lookup"><span data-stu-id="1428f-151">See the [More information](#more-information) section for a description about how Microsoft 365 determines the age buckets for the **Age** filter.</span></span> 
  
      - <span data-ttu-id="1428f-152">**Type** - このセクションには、インポート ジョブの PST ファイルに含まれるすべてのメッセージの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-152">**Type** - This section shows all the message types that were found in the PST files for the import job.</span></span> <span data-ttu-id="1428f-153">除外するメッセージの種類の横にあるボックスをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="1428f-153">You can uncheck a box next to a message type that you want to exclude.</span></span> <span data-ttu-id="1428f-154">その他のメッセージの種類を除外できない。</span><span class="sxs-lookup"><span data-stu-id="1428f-154">You can't exclude the Other message type.</span></span> <span data-ttu-id="1428f-155">その他 [のカテゴリに](#more-information) 含まれるメールボックス アイテムの一覧については、「詳細」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1428f-155">See the [More information](#more-information) section for a list of mailbox items that are included in the Other category.</span></span>
  
      - <span data-ttu-id="1428f-156">**ユーザー** - 特定のユーザーが送信または受信したメッセージを除外できます。</span><span class="sxs-lookup"><span data-stu-id="1428f-156">**Users** - You can exclude messages that are sent or received by specific people.</span></span> <span data-ttu-id="1428f-157">[送信者:] フィールド、宛先: フィールド、またはメッセージの [Cc:] フィールドに表示されるユーザーを除外するには、その受信者の種類の横にある [ユーザーを除外する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1428f-157">To exclude people who appear in the From: field, To: field, or the Cc: field of messages, click **Exclude users** next to that recipient type.</span></span> <span data-ttu-id="1428f-158">ユーザーの電子メール アドレス (SMTP アドレス)を入力し、[新しい追加] アイコンをクリックして、その受信者の種類の除外ユーザーの一覧に追加し、[保存] をクリックして除外されたユーザーの一覧を保存します。 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) </span><span class="sxs-lookup"><span data-stu-id="1428f-158">Type the email address (SMTP address) of the person, click **Add**![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) to add them to the list of excluded users for that recipient type, and then click **Save** to save the list of excluded users.</span></span> 
  
        > [!NOTE]
        > <span data-ttu-id="1428f-159">Microsoft 365ユーザー フィルターを設定した結果として得られるデータ分析情報は **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-159">Microsoft 365 doesn't show data insights that result from setting the **People** filter.</span></span> <span data-ttu-id="1428f-160">ただし、特定のユーザーが送信または受信したメッセージを除外するためにこのフィルターを設定した場合、それらのメッセージは実際のインポート プロセス中に除外されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-160">However, if you set this filter to exclude messages sent or received by specific people, those messages will be excluded during the actual import process.</span></span> 
  
    <span data-ttu-id="1428f-161">c.</span><span class="sxs-lookup"><span data-stu-id="1428f-161">c.</span></span> <span data-ttu-id="1428f-162">[ **その他の** フィルター オプション **] ページの [適用]** をクリックして、フィルター設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="1428f-162">Click **Apply** in the **More filtering options** fly out page to save your filter settings.</span></span> 
  
    <span data-ttu-id="1428f-163">[データを Office 365にインポートする] ページのデータ分析情報は、フィルター設定に基づいてインポートされるデータの合計量を含む、フィルター設定に基づいて更新されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-163">The data insights on the **Import data to Office 365** page are updated based on your filter settings, including the total amount of data that will be imported based on the filter settings.</span></span> <span data-ttu-id="1428f-164">フィルター設定の概要も表示されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-164">A summary of the filter settings is also shown.</span></span> <span data-ttu-id="1428f-165">フィルターの横にある **[編集]** をクリックすると、必要に応じて設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1428f-165">You can click **Edit** next to a filter to change the setting if necessary.</span></span> 
  
    ![データ分析情報は、フィルター設定に基づいて更新されます。](../media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    <span data-ttu-id="1428f-167">d.</span><span class="sxs-lookup"><span data-stu-id="1428f-167">d.</span></span> <span data-ttu-id="1428f-168">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1428f-168">Click **Next**.</span></span>
  
    <span data-ttu-id="1428f-169">フィルター設定を示す状態ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-169">A status page is displayed showing your filter settings.</span></span> <span data-ttu-id="1428f-170">繰り返しますが、任意のフィルター設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="1428f-170">Again, you can edit any of the filter settings.</span></span>
  
    <span data-ttu-id="1428f-171">e.</span><span class="sxs-lookup"><span data-stu-id="1428f-171">e.</span></span> <span data-ttu-id="1428f-172">[データ **のインポート] を** クリックしてインポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="1428f-172">Click **Import data** to start the import.</span></span> <span data-ttu-id="1428f-173">インポートされるデータの合計量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-173">The total amount of data that will be imported is displayed.</span></span> 
  
    <span data-ttu-id="1428f-174">または</span><span class="sxs-lookup"><span data-stu-id="1428f-174">Or</span></span>
  
    <span data-ttu-id="1428f-175">a.</span><span class="sxs-lookup"><span data-stu-id="1428f-175">a.</span></span> <span data-ttu-id="1428f-176">[**いいえ]をクリックし**、PST ファイル内のすべてのデータをインポートして[次へ]をクリックOffice 365を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1428f-176">Click **No, I want to import everything** to import all data in the PST files to Office 365, and then click **Next**.</span></span>
  
    <span data-ttu-id="1428f-177">b.</span><span class="sxs-lookup"><span data-stu-id="1428f-177">b.</span></span> <span data-ttu-id="1428f-178">[データの **インポート先] ページOffice 365[** データのインポート]**をクリックして** インポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="1428f-178">On the **Import data to Office 365** page, click **Import data** to start the import.</span></span> <span data-ttu-id="1428f-179">インポートされるデータの合計量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-179">The total amount of data that will be imported is displayed.</span></span> 
  
6. <span data-ttu-id="1428f-180">[インポート] **タブで** 、[最新の情報に更新] **を** ![ クリックします ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) 。</span><span class="sxs-lookup"><span data-stu-id="1428f-180">On the **Import** tab, click **Refresh** ![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png).</span></span> <span data-ttu-id="1428f-181">インポート ジョブの状態が [状態] 列 **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-181">The status for the import job is displayed in the **Status** column.</span></span>
  
7. <span data-ttu-id="1428f-182">ジョブのインポートをクリックすると、各 PST ファイルの状態や構成したフィルター設定などの詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-182">Click the import the job to display more detailed information, such as the status for each PST file and the filter settings that you configured.</span></span>

## <a name="more-information"></a><span data-ttu-id="1428f-183">詳細</span><span class="sxs-lookup"><span data-stu-id="1428f-183">More information</span></span>

- <span data-ttu-id="1428f-184">年齢フィルター Microsoft 365増分を決定する方法</span><span class="sxs-lookup"><span data-stu-id="1428f-184">How does Microsoft 365 determine the increments for the age filter?</span></span> <span data-ttu-id="1428f-185">PST Microsoft 365分析すると、各アイテムの送信または受信タイムスタンプを確認します (アイテムに送信タイムスタンプと受信タイムスタンプの両方がある場合は、最も古い日付が選択されます)。</span><span class="sxs-lookup"><span data-stu-id="1428f-185">When Microsoft 365 analyzes a PST file, it looks at the sent or received time stamp of each item (if an item has both a sent and received timestamp, the oldest date is selected).</span></span> <span data-ttu-id="1428f-186">次Microsoft 365タイムスタンプの年の値を確認し、現在の日付と比較してアイテムの年齢を決定します。</span><span class="sxs-lookup"><span data-stu-id="1428f-186">Then Microsoft 365 looks at the year value for that timestamp and compares it to the current date to determine the age of the item.</span></span> <span data-ttu-id="1428f-187">これらの年齢は、Age フィルターのドロップダウン リストの値として **使用** されます。</span><span class="sxs-lookup"><span data-stu-id="1428f-187">These ages are then used as the values in the drop-down list for the **Age** filter.</span></span> <span data-ttu-id="1428f-188">たとえば、PST ファイルに 2016、2015、および 2014 からのメッセージがある場合 **、Age** フィルターの値は **1** 年 **、2** 年、 **および 3 年になります**。</span><span class="sxs-lookup"><span data-stu-id="1428f-188">For example, if a PST file has messages from 2016, 2015, and 2014, then values in the **Age** filter would be **1 year**, **2 years**, and **3 years**.</span></span>
  
- <span data-ttu-id="1428f-189">次の表に、[その他のオプション] ページの [種類] フィルターの[その他] カテゴリに含まれるメッセージの種類を示します (前の手順の「手順 5b」を参照)。 </span><span class="sxs-lookup"><span data-stu-id="1428f-189">The following table lists the message types that are included in the **Other** category in the **Type** filter on the **More options** fly out page (see Step 5b in the previous procedure).</span></span> <span data-ttu-id="1428f-190">現在、PST をインポートして他のカテゴリのアイテムを除外Office 365。</span><span class="sxs-lookup"><span data-stu-id="1428f-190">Currently, you can't exclude items in the "Other" category when you import PSTs to Office 365.</span></span> 
  
    |<span data-ttu-id="1428f-191">**メッセージ クラス ID**</span><span class="sxs-lookup"><span data-stu-id="1428f-191">**Message class ID**</span></span>|<span data-ttu-id="1428f-192">**このメッセージ クラスを使用するメールボックス アイテム**</span><span class="sxs-lookup"><span data-stu-id="1428f-192">**Mailbox items that use this message class**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1428f-193">IPM。アクティビティ</span><span class="sxs-lookup"><span data-stu-id="1428f-193">IPM.Activity</span></span>  <br/> |<span data-ttu-id="1428f-194">履歴項目</span><span class="sxs-lookup"><span data-stu-id="1428f-194">Journal entries</span></span>  <br/> |
    |<span data-ttu-id="1428f-195">IPM.Document</span><span class="sxs-lookup"><span data-stu-id="1428f-195">IPM.Document</span></span>  <br/> |<span data-ttu-id="1428f-196">ドキュメントとファイル (電子メール メッセージに添付されていない)</span><span class="sxs-lookup"><span data-stu-id="1428f-196">Documents and files (not attached to an email message)</span></span>  <br/> |
    |<span data-ttu-id="1428f-197">IPM。ファイル</span><span class="sxs-lookup"><span data-stu-id="1428f-197">IPM.File</span></span>  <br/> |<span data-ttu-id="1428f-198">(ument とIPM.Doc)</span><span class="sxs-lookup"><span data-stu-id="1428f-198">(same as IPM.Document)</span></span>  <br/> |
    |<span data-ttu-id="1428f-199">IPM。Note.IMC.Notification</span><span class="sxs-lookup"><span data-stu-id="1428f-199">IPM.Note.IMC.Notification</span></span>  <br/> |<span data-ttu-id="1428f-200">インターネット へのゲートウェイConnectであるインターネット メール Exchange Server送信されるレポート</span><span class="sxs-lookup"><span data-stu-id="1428f-200">Reports sent by Internet Mail Connect, which is the Exchange Server gateway to the Internet</span></span>  <br/> |
    |<span data-ttu-id="1428f-201">IPM。Note.Microsoft.Fax</span><span class="sxs-lookup"><span data-stu-id="1428f-201">IPM.Note.Microsoft.Fax</span></span>  <br/> |<span data-ttu-id="1428f-202">FAX メッセージ</span><span class="sxs-lookup"><span data-stu-id="1428f-202">Fax messages</span></span>  <br/> |
    |<span data-ttu-id="1428f-203">IPM。Note.Rules.Oof.Template.Microsoft</span><span class="sxs-lookup"><span data-stu-id="1428f-203">IPM.Note.Rules.Oof.Template.Microsoft</span></span>  <br/> |<span data-ttu-id="1428f-204">アウトオブオフィスの自動表示メッセージ</span><span class="sxs-lookup"><span data-stu-id="1428f-204">Out-of-office autoreply messages</span></span>  <br/> |
    |<span data-ttu-id="1428f-205">IPM。Note.Rules.ReplyTemplate.Microsoft</span><span class="sxs-lookup"><span data-stu-id="1428f-205">IPM.Note.Rules.ReplyTemplate.Microsoft</span></span>  <br/> |<span data-ttu-id="1428f-206">受信トレイ ルールによって送信された返信</span><span class="sxs-lookup"><span data-stu-id="1428f-206">Replies sent by an inbox rule</span></span>  <br/> |
    |<span data-ttu-id="1428f-207">IPM。OLE。クラス</span><span class="sxs-lookup"><span data-stu-id="1428f-207">IPM.OLE.Class</span></span>  <br/> |<span data-ttu-id="1428f-208">定期的なシリーズの例外</span><span class="sxs-lookup"><span data-stu-id="1428f-208">Exceptions for a recurring series</span></span>  <br/> |
    |<span data-ttu-id="1428f-209">IPM。Recall.Report</span><span class="sxs-lookup"><span data-stu-id="1428f-209">IPM.Recall.Report</span></span>  <br/> |<span data-ttu-id="1428f-210">メッセージ取り消しレポート</span><span class="sxs-lookup"><span data-stu-id="1428f-210">Message recall reports</span></span>  <br/> |
    |<span data-ttu-id="1428f-211">IPM。リモート</span><span class="sxs-lookup"><span data-stu-id="1428f-211">IPM.Remote</span></span>  <br/> |<span data-ttu-id="1428f-212">リモート メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="1428f-212">Remote mail messages</span></span>  <br/> |
    |<span data-ttu-id="1428f-213">IPM。レポート</span><span class="sxs-lookup"><span data-stu-id="1428f-213">IPM.Report</span></span>  <br/> |<span data-ttu-id="1428f-214">アイテムの状態レポート</span><span class="sxs-lookup"><span data-stu-id="1428f-214">Item status reports</span></span>  <br/> |
