---
title: PST ファイルをインポートするときに、データをフィルター処理する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
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
description: PST ファイルを Office 365 にインポートするときに、Office 365 import service のインテリジェントなインポート機能を使用してデータをフィルター処理する方法について説明します。
ms.openlocfilehash: d511c1277104a27076116fafcb4b71bc851baaca
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817726"
---
# <a name="filter-data-when-importing-pst-files"></a><span data-ttu-id="fcd68-103">PST ファイルをインポートするときに、データをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="fcd68-103">Filter data when importing PST files</span></span>

<span data-ttu-id="fcd68-104">Office 365 インポートサービスの新しいインテリジェントインポート機能を使用して、実際にターゲットメールボックスにインポートされる PST ファイル内のアイテムをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="fcd68-104">Use the new Intelligent Import feature in the Office 365 Import service to filter the items in PST files that actually get imported to the target mailboxes.</span></span> <span data-ttu-id="fcd68-105">次に、動作のしくみを示します。</span><span class="sxs-lookup"><span data-stu-id="fcd68-105">Here's how it works:</span></span>
  
- <span data-ttu-id="fcd68-106">PST インポートジョブを作成して送信すると、PST ファイルが Microsoft クラウドの Azure ストレージ領域にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-106">After you create and submit a PST import job, PST files are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
    
- <span data-ttu-id="fcd68-107">Microsoft 365 は、メールボックスアイテムの保存期間と PST ファイルに含まれるさまざまなメッセージの種類を識別することによって、PST ファイル内のデータを安全かつ安全な方法で分析します。</span><span class="sxs-lookup"><span data-stu-id="fcd68-107">Microsoft 365 analyzes the data in the PST files, in a safe and secure manner, by identifying the age of the mailbox items and the different message types included in the PST files.</span></span>
    
- <span data-ttu-id="fcd68-108">分析が完了し、データをインポートする準備ができたら、すべてのデータをその PST ファイルにインポートするか、またはインポートするデータを制御するフィルターを設定することによってインポートされたデータをトリミングするかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-108">When the analysis is complete and the data is ready to import, you have the option to import all data in the PST files as is or trim the data that's imported by setting filters that control what data gets imported.</span></span> <span data-ttu-id="fcd68-109">たとえば、次のことを選択できます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-109">For example, you can choose to:</span></span>
    
  - <span data-ttu-id="fcd68-110">特定の期間のアイテムのみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="fcd68-110">Import only items of a certain age.</span></span>
    
  - <span data-ttu-id="fcd68-111">選択したメッセージの種類をインポートします。</span><span class="sxs-lookup"><span data-stu-id="fcd68-111">Import selected message types.</span></span>
    
  - <span data-ttu-id="fcd68-112">特定のユーザーによって送受信されたメッセージを除外します。</span><span class="sxs-lookup"><span data-stu-id="fcd68-112">Exclude messages sent or received by specific people.</span></span>
    
- <span data-ttu-id="fcd68-113">フィルター設定を構成した後、Microsoft 365 は、インポートジョブで指定されたターゲットメールボックスに対するフィルター条件に一致するデータのみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="fcd68-113">After you configure the filter settings, Microsoft 365 imports only the data that meets the filtering criteria to the target mailboxes specified in the import job.</span></span>
    
<span data-ttu-id="fcd68-114">次の図は、インテリジェントなインポート処理を示しており、実行するタスクと Office 365 によって実行されるタスクを強調表示しています。</span><span class="sxs-lookup"><span data-stu-id="fcd68-114">The following graphic shows the Intelligent Import process, and highlights the tasks you perform and the tasks performed by Office 365.</span></span>
  
![Office 365 のインテリジェントなインポートプロセス](../media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="create-a-pst-import-job"></a><span data-ttu-id="fcd68-116">PST インポートジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="fcd68-116">Create a PST import job</span></span>

- <span data-ttu-id="fcd68-117">このトピックの手順では、ネットワークアップロードまたはドライブ出荷を使用して、Office 365 インポートサービスに PST インポートジョブを作成したことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="fcd68-117">The steps in this topic assume that you've created a PST import job in the Office 365 Import service by using network upload or drive shipping.</span></span> <span data-ttu-id="fcd68-118">詳細な手順については、以下のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcd68-118">For step-by-step instructions, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="fcd68-119">ネットワーク アップロードを使用して PST ファイルを Office 365 にインストールする</span><span class="sxs-lookup"><span data-stu-id="fcd68-119">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
    
  - [<span data-ttu-id="fcd68-120">ドライブの送付を使用して PST ファイルを Office 365 にインポートする</span><span class="sxs-lookup"><span data-stu-id="fcd68-120">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- <span data-ttu-id="fcd68-121">ネットワークアップロードを使用してインポートジョブを作成した後、セキュリティ & コンプライアンスセンターの [インポート] ページのインポートジョブの状態が [**進行中**] に設定されています。これは、Microsoft 365 がアップロードした PST ファイルのデータを分析していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="fcd68-121">After you create an import job by using network upload, the status for the import job on the Import page in the Security & Compliance Center is set to **Analysis in progress**, which means that Microsoft 365 is analyzing the data in the PST files that you uploaded.</span></span> <span data-ttu-id="fcd68-122">[**更新**の更新] をクリックして、 ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) インポートジョブの状態を更新します。</span><span class="sxs-lookup"><span data-stu-id="fcd68-122">Click **Refresh**![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the status for the import job.</span></span> 
    
- <span data-ttu-id="fcd68-123">ドライブを送付するインポートジョブの場合、Microsoft データセンターの担当者がハードドライブを受信し、PST ファイルを組織の Azure ストレージ領域にアップロードした後、Microsoft 365 によってデータが分析されます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-123">For drive shipping import jobs, the data will be analyzed by Microsoft 365 after Microsoft datacenter personnel receive your hard drive and upload the PST files to the Azure storage area for your organization.</span></span>
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a><span data-ttu-id="fcd68-124">メールボックスにインポートされるデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="fcd68-124">Filter data that gets imported to mailboxes</span></span>

<span data-ttu-id="fcd68-125">PST インポートジョブを作成したら、次の手順に従って、Office 365 にインポートする前にデータをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="fcd68-125">After you've created a PST import job, follow these steps to filter the data before you import it to Office 365.</span></span>
  
1. <span data-ttu-id="fcd68-126">[https://protection.office.com/](https://protection.office.com/) に移動し、組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="fcd68-126">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your organization.</span></span> 
    
2. <span data-ttu-id="fcd68-127">[**情報ガバナンス**] [インポート \> **Import** \> **PST ファイル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd68-127">Click **Information governance** \> **Import** \> **Import PST files**.</span></span>
    
    <span data-ttu-id="fcd68-128">組織のインポートジョブは、[ **PST ファイルのインポート**] ページに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-128">The import jobs for your organization are listed on the **Import PST files** page.</span></span> <span data-ttu-id="fcd68-129">[**状態**] 列の [**分析完了**] の値は、Microsoft 365 によって分析され、インポートの準備が整っているインポートジョブを示していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fcd68-129">Note that the **Analysis completed** value in the **Status** column indicates the import jobs that have been analyzed by Microsoft 365 and are ready for you to import.</span></span> 
    
    ![分析完了状態 Microsoft 365 が PST ファイルのデータを分析したことを示します。](../media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. <span data-ttu-id="fcd68-131">完了するインポートジョブについては、[準備完了] をクリックして**Office 365 にインポート**します。</span><span class="sxs-lookup"><span data-stu-id="fcd68-131">Click **Ready to import to Office 365** for the import job that you want to complete.</span></span> 
    
    <span data-ttu-id="fcd68-132">PST ファイルに関する情報とインポート ジョブに関するその他の情報を示すポップアップ ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-132">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
4. <span data-ttu-id="fcd68-133">[ **Office 365 へのインポート] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd68-133">Click **Import to Office 365**.</span></span>
    
    <span data-ttu-id="fcd68-134">[**データのフィルター処理**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-134">The **Filter your data** page is displayed.</span></span> <span data-ttu-id="fcd68-135">このサイトには、データの保存期間に関する情報を含む、インポートジョブの PST ファイル内のデータに関するデータの情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fcd68-135">It contains data insights about the data in the PST files for the import job, including information about the age of the data.</span></span> 
    
    ![[データをフィルターする] ページに、インポートジョブの PST ファイルのデータ分析情報が表示されます。](../media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. <span data-ttu-id="fcd68-137">Microsoft 365 にインポートされたデータをトリミングするかどうかに基づいて、[**データにフィルターを適用しますか?**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fcd68-137">Based on whether or not you want to trim the data that's imported to Microsoft 365, under **Do you want to filter your data?**, do one of the following:</span></span>
    
    <span data-ttu-id="fcd68-138">a.</span><span class="sxs-lookup"><span data-stu-id="fcd68-138">a.</span></span> <span data-ttu-id="fcd68-139">[**はい、インポートする前にフィルターを適用**して、インポートしたデータをトリミングします] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd68-139">Click **Yes, I want to filter it before importing** to trim the data that you import, and then click **Next**.</span></span>
    
    <span data-ttu-id="fcd68-140">**Office 365 にデータをインポートする**ページページに、Microsoft 365 が実行した分析から詳細なデータ分析情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-140">The **Import data to Office 365 page** page is displayed with detailed data insights from the analysis that Microsoft 365 performed.</span></span> 
    
    ![Microsoft 365 は、PST ファイルの分析から詳細なデータの洞察を示しています。](../media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    <span data-ttu-id="fcd68-142">このページのグラフには、インポートされるデータの量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-142">The graph on this page shows the amount of data that will be imported.</span></span> <span data-ttu-id="fcd68-143">PST ファイルに含まれる各メッセージの種類に関する情報が、グラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-143">Information about each message type found in the PST files is displayed in the graph.</span></span> <span data-ttu-id="fcd68-144">各バーの上にカーソルを置くと、そのメッセージの種類に関する特定の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-144">You can hover the cursor over each bar to display specific information about that message type.</span></span> <span data-ttu-id="fcd68-145">また、PST ファイルの分析に基づいて、保存期間の値が異なるドロップダウンリストもあります。</span><span class="sxs-lookup"><span data-stu-id="fcd68-145">There is also a drop-down list with different age values based on the analysis of the PST files.</span></span> <span data-ttu-id="fcd68-146">ドロップダウンリストで年齢を選択すると、グラフが更新されて、選択した期間にインポートされるデータの量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-146">When you select an age in the drop-down list, the graph is updated to show how much data will be imported for the selected age.</span></span> 
    
    <span data-ttu-id="fcd68-147">b.</span><span class="sxs-lookup"><span data-stu-id="fcd68-147">b.</span></span> <span data-ttu-id="fcd68-148">追加フィルターを構成して、インポートされるデータの量を減らすには、[**その他のフィルターオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd68-148">To configure addition filters to reduce the amount of data that's imported, click **More filtering options**.</span></span>
    
    ![[その他のオプション] ページでフィルターを構成して、インポートされたデータをトリミングします。](../media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    <span data-ttu-id="fcd68-150">これらのフィルターは、次のように構成できます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-150">You can configure these filters:</span></span>
    
      - <span data-ttu-id="fcd68-151">**Age** -年齢を選択すると、指定した期間より新しいアイテムのみがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-151">**Age** - Select an age so only items that are newer than the specified age will be imported.</span></span> <span data-ttu-id="fcd68-152">Microsoft 365 が**年齢**フィルターの年齢バケットを決定する方法については、「 [More information](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcd68-152">See the [More information](#more-information) section for a description about how Microsoft 365 determines the age buckets for the **Age** filter.</span></span> 
    
      - <span data-ttu-id="fcd68-153">**種類**-このセクションには、インポートジョブの PST ファイルにあるすべてのメッセージの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-153">**Type** - This section shows all the message types that were found in the PST files for the import job.</span></span> <span data-ttu-id="fcd68-154">除外するメッセージの種類の横にあるチェックボックスをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-154">You can uncheck a box next to a message type that you want to exclude.</span></span> <span data-ttu-id="fcd68-155">他の種類のメッセージは除外できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fcd68-155">Note that you can't exclude the Other message type.</span></span> <span data-ttu-id="fcd68-156">他のカテゴリに含まれるメールボックスアイテムの一覧については、「 [More information](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcd68-156">See the [More information](#more-information) section for a list of mailbox items that are included in the Other category.</span></span> 
    
      - <span data-ttu-id="fcd68-157">**ユーザー** -特定のユーザーが送信または受信したメッセージを除外することができます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-157">**Users** - You can exclude messages that are sent or received by specific people.</span></span> <span data-ttu-id="fcd68-158">メッセージの [差出人:] フィールド、[宛先] フィールド、または [Cc:] フィールドに表示されるユーザーを除外するには、その受信者の種類の横にある [**ユーザーを除外**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd68-158">To exclude people who appear in the From: field, To: field, or the Cc: field of messages, click **Exclude users** next to that recipient type.</span></span> <span data-ttu-id="fcd68-159">ユーザーの電子メールアドレス (SMTP アドレス) を入力し、[新しいアイコンの**追加**] をクリックして、 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) その受信者の種類の除外対象ユーザーの一覧に追加します。次に、[**保存**] をクリックして、除外されるユーザーの一覧を保存します。</span><span class="sxs-lookup"><span data-stu-id="fcd68-159">Type the email address (SMTP address) of the person, click **Add**![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) to add them to the list of excluded users for that recipient type, and then click **Save** to save the list of excluded users.</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="fcd68-160">Microsoft 365 は、**ユーザー**フィルターを設定することによって得られるデータ洞察を示していません。</span><span class="sxs-lookup"><span data-stu-id="fcd68-160">Microsoft 365 doesn't show data insights that result from setting the **People** filter.</span></span> <span data-ttu-id="fcd68-161">ただし、特定のユーザーが送信または受信したメッセージを除外するようにこのフィルターを設定すると、実際のインポート処理中にこれらのメッセージは除外されます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-161">However, if you set this filter to exclude messages sent or received by specific people, those messages will be excluded during the actual import process.</span></span> 
  
    <span data-ttu-id="fcd68-162">c.</span><span class="sxs-lookup"><span data-stu-id="fcd68-162">c.</span></span> <span data-ttu-id="fcd68-163">フィルターの設定を保存するには、[**その他のフィルターオプション**] ページの [**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd68-163">Click **Apply** in the **More filtering options** fly out page to save your filter settings.</span></span> 
    
    <span data-ttu-id="fcd68-164">[ **Office へのデータのインポート 365** ] ページのデータ分析は、フィルター設定に基づいてインポートされるデータの総量など、フィルター設定に基づいて更新されます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-164">The data insights on the **Import data to Office 365** page are updated based on your filter settings, including the total amount of data that will be imported based on the filter settings.</span></span> <span data-ttu-id="fcd68-165">フィルター設定の概要も表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fcd68-165">Note that a summary of the filter settings is also shown.</span></span> <span data-ttu-id="fcd68-166">必要に応じて、フィルターの横にある [**編集**] をクリックして設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-166">You can click **Edit** next to a filter to change the setting if necessary.</span></span> 
    
    ![データ分析情報は、フィルター設定に基づいて更新されます。](../media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    <span data-ttu-id="fcd68-168">d.</span><span class="sxs-lookup"><span data-stu-id="fcd68-168">d.</span></span> <span data-ttu-id="fcd68-169">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd68-169">Click **Next**.</span></span>
    
    <span data-ttu-id="fcd68-170">フィルター設定を示す状態ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-170">A status page is displayed showing your filter settings.</span></span> <span data-ttu-id="fcd68-171">この場合も、任意のフィルター設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-171">Again, you can edit any of the filter settings.</span></span>
    
    <span data-ttu-id="fcd68-172">e.</span><span class="sxs-lookup"><span data-stu-id="fcd68-172">e.</span></span> <span data-ttu-id="fcd68-173">[**データのインポート**] をクリックしてインポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="fcd68-173">Click **Import data** to start the import .</span></span> <span data-ttu-id="fcd68-174">インポートされるデータの合計量が表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fcd68-174">Note that the total amount of data that will be imported is displayed.</span></span> 
    
    <span data-ttu-id="fcd68-175">または</span><span class="sxs-lookup"><span data-stu-id="fcd68-175">Or</span></span>
    
    <span data-ttu-id="fcd68-176">a.</span><span class="sxs-lookup"><span data-stu-id="fcd68-176">a.</span></span> <span data-ttu-id="fcd68-177">[**いいえ、** PST ファイルのすべてのデータを Office 365 にインポートするためにすべてインポートします] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd68-177">Click **No, I want to import everything** to import all data in the PST files to Office 365, and then click **Next**.</span></span>
    
    <span data-ttu-id="fcd68-178">b.</span><span class="sxs-lookup"><span data-stu-id="fcd68-178">b.</span></span> <span data-ttu-id="fcd68-179">[ **Office へのデータのインポート 365** ] ページで、[**データのインポート**] をクリックしてインポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="fcd68-179">On the **Import data to Office 365** page, click **Import data** to start the import.</span></span> <span data-ttu-id="fcd68-180">インポートされるデータの合計量が表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fcd68-180">Note that the total amount of data that will be imported is displayed.</span></span> 
    
6. <span data-ttu-id="fcd68-181">[ **PST ファイルのインポート**] ページで、[最新の情報に更新]**をクリックし** ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) ます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-181">On the **Import PST files** page, click **Refresh** ![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png).</span></span> <span data-ttu-id="fcd68-182">インポートジョブの状態は、[**状態**] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-182">The status for the import job is displayed in the **Status** column.</span></span> 
    
7. <span data-ttu-id="fcd68-183">[ジョブのインポート] をクリックして、各 PST ファイルの状態、構成したフィルター設定などの詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="fcd68-183">Click the import the job to display more detailed information, such as the status for each PST file and the filter settings that you configured.</span></span>

  
## <a name="more-information"></a><span data-ttu-id="fcd68-184">詳細情報</span><span class="sxs-lookup"><span data-stu-id="fcd68-184">More information</span></span>

- <span data-ttu-id="fcd68-185">Microsoft 365 は、年齢フィルターの増分をどのように決定しますか?</span><span class="sxs-lookup"><span data-stu-id="fcd68-185">How does Microsoft 365 determine the increments for the age filter?</span></span> <span data-ttu-id="fcd68-186">Microsoft 365 では、PST ファイルを分析する際に、各アイテムの送受信タイムスタンプを確認します (アイテムに送信と受信の両方のタイムスタンプがある場合は、最も古い日付が選択されます)。</span><span class="sxs-lookup"><span data-stu-id="fcd68-186">When Microsoft 365 analyzes a PST file, it looks at the sent or received time stamp of each item (if an item has both a sent and received timestamp, the oldest date is selected).</span></span> <span data-ttu-id="fcd68-187">次に、Microsoft 365 は、そのタイムスタンプの年の値を参照し、それを現在の日付と比較して、アイテムの保存期間を判断します。</span><span class="sxs-lookup"><span data-stu-id="fcd68-187">Then Microsoft 365 looks at the year value for that timestamp and compares it to the current date to determine the age of the item.</span></span> <span data-ttu-id="fcd68-188">これらの年齢は、**年齢**フィルターのドロップダウンリストの値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="fcd68-188">These ages are then used as the values in the drop-down list for the **Age** filter.</span></span> <span data-ttu-id="fcd68-189">たとえば、PST ファイルに2016、2015、および2014のメッセージが含まれている場合、 **Age**フィルターの値は**1 年**、 **2 年**、 **3 年**になります。</span><span class="sxs-lookup"><span data-stu-id="fcd68-189">For example, if a PST file has messages from 2016, 2015, and 2014, then values in the **Age** filter would be **1 year**, **2 years**, and **3 years**.</span></span>
    
- <span data-ttu-id="fcd68-190">次の表に、[その他の**オプション**] フライアウトページの [フィルターの**種類**] で、**他の**カテゴリに含まれるメッセージの種類を示します (前の手順の手順5b を参照)。</span><span class="sxs-lookup"><span data-stu-id="fcd68-190">The following table lists the message types that are included in the **Other** category in the **Type** filter on the **More options** fly out page (see Step 5b in the previous procedure).</span></span> <span data-ttu-id="fcd68-191">現時点では、Pst を Office 365 にインポートするときに、"その他の" カテゴリのアイテムを除外することはできません。</span><span class="sxs-lookup"><span data-stu-id="fcd68-191">Currently, you can't exclude items in the "Other" category when you import PSTs to Office 365.</span></span> 
    
    |<span data-ttu-id="fcd68-192">**メッセージ クラス ID**</span><span class="sxs-lookup"><span data-stu-id="fcd68-192">**Message class ID**</span></span>|<span data-ttu-id="fcd68-193">**このメッセージクラスを使用するメールボックスアイテム**</span><span class="sxs-lookup"><span data-stu-id="fcd68-193">**Mailbox items that use this message class**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="fcd68-194">IPM.運用</span><span class="sxs-lookup"><span data-stu-id="fcd68-194">IPM.Activity</span></span>  <br/> |<span data-ttu-id="fcd68-195">履歴項目</span><span class="sxs-lookup"><span data-stu-id="fcd68-195">Journal entries</span></span>  <br/> |
    |<span data-ttu-id="fcd68-196">IPM.Document</span><span class="sxs-lookup"><span data-stu-id="fcd68-196">IPM.Document</span></span>  <br/> |<span data-ttu-id="fcd68-197">ドキュメントとファイル (電子メールメッセージに添付されていない)</span><span class="sxs-lookup"><span data-stu-id="fcd68-197">Documents and files (not attached to an email message)</span></span>  <br/> |
    |<span data-ttu-id="fcd68-198">IPM.拡張子</span><span class="sxs-lookup"><span data-stu-id="fcd68-198">IPM.File</span></span>  <br/> |<span data-ttu-id="fcd68-199">(IPM.Docと同じ ument)</span><span class="sxs-lookup"><span data-stu-id="fcd68-199">(same as IPM.Document)</span></span>  <br/> |
    |<span data-ttu-id="fcd68-200">IPM.メモ: 通知</span><span class="sxs-lookup"><span data-stu-id="fcd68-200">IPM.Note.IMC.Notification</span></span>  <br/> |<span data-ttu-id="fcd68-201">インターネットメール接続によって送信されるレポート。インターネットへの Exchange サーバーゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="fcd68-201">Reports sent by Internet Mail Connect, which is the Exchange Server gateway to the Internet</span></span>  <br/> |
    |<span data-ttu-id="fcd68-202">IPM.注: Microsoft Fax</span><span class="sxs-lookup"><span data-stu-id="fcd68-202">IPM.Note.Microsoft.Fax</span></span>  <br/> |<span data-ttu-id="fcd68-203">Fax メッセージ</span><span class="sxs-lookup"><span data-stu-id="fcd68-203">Fax messages</span></span>  <br/> |
    |<span data-ttu-id="fcd68-204">IPM.注: Microsoft では、</span><span class="sxs-lookup"><span data-stu-id="fcd68-204">IPM.Note.Rules.Oof.Template.Microsoft</span></span>  <br/> |<span data-ttu-id="fcd68-205">不在時の自動応答メッセージ</span><span class="sxs-lookup"><span data-stu-id="fcd68-205">Out-of-office auto-reply messages</span></span>  <br/> |
    |<span data-ttu-id="fcd68-206">IPM.注 ReplyTemplate。</span><span class="sxs-lookup"><span data-stu-id="fcd68-206">IPM.Note.Rules.ReplyTemplate.Microsoft</span></span>  <br/> |<span data-ttu-id="fcd68-207">受信トレイルールによって送信された返信</span><span class="sxs-lookup"><span data-stu-id="fcd68-207">Replies sent by an inbox rule</span></span>  <br/> |
    |<span data-ttu-id="fcd68-208">IPM.OLE.クラス</span><span class="sxs-lookup"><span data-stu-id="fcd68-208">IPM.OLE.Class</span></span>  <br/> |<span data-ttu-id="fcd68-209">定期的なアイテムの例外</span><span class="sxs-lookup"><span data-stu-id="fcd68-209">Exceptions for a recurring series</span></span>  <br/> |
    |<span data-ttu-id="fcd68-210">IPM.取り消し。レポート</span><span class="sxs-lookup"><span data-stu-id="fcd68-210">IPM.Recall.Report</span></span>  <br/> |<span data-ttu-id="fcd68-211">メッセージ取り消しレポート</span><span class="sxs-lookup"><span data-stu-id="fcd68-211">Message recall reports</span></span>  <br/> |
    |<span data-ttu-id="fcd68-212">IPM.リモート</span><span class="sxs-lookup"><span data-stu-id="fcd68-212">IPM.Remote</span></span>  <br/> |<span data-ttu-id="fcd68-213">リモートメールメッセージ</span><span class="sxs-lookup"><span data-stu-id="fcd68-213">Remote mail messages</span></span>  <br/> |
    |<span data-ttu-id="fcd68-214">IPM.レポート</span><span class="sxs-lookup"><span data-stu-id="fcd68-214">IPM.Report</span></span>  <br/> |<span data-ttu-id="fcd68-215">アイテムの進捗レポート</span><span class="sxs-lookup"><span data-stu-id="fcd68-215">Item status reports</span></span>  <br/> |
