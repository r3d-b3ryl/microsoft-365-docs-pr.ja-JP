---
title: コンテンツ検索の結果をエクスポートするときにレポートを無効にする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: セキュリティ & コンプライアンスセンターからコンテンツ検索の結果をエクスポートするときにレポートを無効にするには、ローカルコンピューターの Windows レジストリを編集します。
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817856"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="cb86a-103">コンテンツ検索の結果をエクスポートするときにレポートを無効にする</span><span class="sxs-lookup"><span data-stu-id="cb86a-103">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="cb86a-104">電子情報開示エクスポートツールを使用して、セキュリティ & コンプライアンスセンターのコンテンツ検索の結果をエクスポートすると、エクスポートされたコンテンツに関する追加情報を含む2つのレポートが自動的に作成およびエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="cb86a-104">When you use the eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="cb86a-105">これらのレポートは Results.csv ファイルと Manifest.xml ファイルです (これらのレポートの詳細な説明については、このトピックの「[エクスポートレポートを無効にする方法についてよく寄せられる質問](#frequently-asked-questions-about-disabling-export-reports)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="cb86a-105">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="cb86a-106">これらのファイルは非常に大きくなる可能性があるため、ダウンロード時間を短縮し、これらのファイルがエクスポートされないようにすることによって、ディスク領域を節約できます。</span><span class="sxs-lookup"><span data-stu-id="cb86a-106">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="cb86a-107">これを行うには、検索結果のエクスポートに使用するコンピューターで Windows レジストリを変更します。</span><span class="sxs-lookup"><span data-stu-id="cb86a-107">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="cb86a-108">後でレポートを含める必要がある場合は、レジストリ設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="cb86a-108">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="cb86a-109">レジストリ設定を作成してエクスポートレポートを無効にする</span><span class="sxs-lookup"><span data-stu-id="cb86a-109">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="cb86a-110">コンテンツ検索の結果をエクスポートするために使用するコンピューターで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb86a-110">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="cb86a-111">電子情報開示エクスポートツールが開いている場合は、それを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cb86a-111">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="cb86a-112">無効にするエクスポートレポートに応じて、次の手順のいずれかまたは両方を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb86a-112">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="cb86a-113">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="cb86a-113">**Results.csv**</span></span>
    
      <span data-ttu-id="cb86a-114">ファイル名サフィックス .reg を使用して、次のテキストを Windows レジストリファイルに保存します。たとえば、DisableResultsCsv のようにします。</span><span class="sxs-lookup"><span data-stu-id="cb86a-114">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="cb86a-115">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="cb86a-115">**Manifest.xml**</span></span>
    
      <span data-ttu-id="cb86a-116">ファイル名サフィックス .reg を使用して、次のテキストを Windows レジストリファイルに保存します。たとえば、DisableManifestXml のようにします。</span><span class="sxs-lookup"><span data-stu-id="cb86a-116">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="cb86a-117">エクスプローラーで、前の手順で作成した .reg ファイルをクリックまたはダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb86a-117">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="cb86a-118">[ユーザーアクセス制御] ウィンドウで、[**はい**] をクリックしてレジストリエディターに変更を許可します。</span><span class="sxs-lookup"><span data-stu-id="cb86a-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="cb86a-119">続行するように求めるメッセージが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb86a-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="cb86a-120">レジストリエディターに、設定が正常にレジストリに追加されたことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb86a-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="cb86a-121">レジストリ設定を編集してエクスポートレポートを再度有効にする</span><span class="sxs-lookup"><span data-stu-id="cb86a-121">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="cb86a-122">前の手順で .reg ファイルを作成して Results.csv を無効に Manifest.xml した場合は、それらのファイルを編集して、検索結果と共にエクスポートされるようにレポートを再度有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cb86a-122">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="cb86a-123">その後、結果をコンテンツ検索にエクスポートするために使用するコンピューターで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb86a-123">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="cb86a-124">電子情報開示エクスポートツールが開いている場合は、それを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cb86a-124">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="cb86a-125">前の手順で作成した .reg の編集ファイルのいずれかまたは両方を編集します。</span><span class="sxs-lookup"><span data-stu-id="cb86a-125">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="cb86a-126">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="cb86a-126">**Results.csv**</span></span>
    
        <span data-ttu-id="cb86a-127">DisableResultsCsv ファイルをメモ帳で開き、の値をに変更して、 `False` `True` ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="cb86a-127">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="cb86a-128">たとえば、ファイルを編集した後、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb86a-128">For example, after you edit the file, it looks like this:</span></span>
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="cb86a-129">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="cb86a-129">**Manifest.xml**</span></span>
    
        <span data-ttu-id="cb86a-130">DisableManifestXml ファイルをメモ帳で開き、の値をに変更して、 `False` `True` ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="cb86a-130">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="cb86a-131">たとえば、ファイルを編集した後、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb86a-131">For example, after you edit the file, it looks like this:</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="cb86a-132">エクスプローラーで、前の手順で編集した .reg ファイルをクリックまたはダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb86a-132">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="cb86a-133">[ユーザーアクセス制御] ウィンドウで、[**はい**] をクリックしてレジストリエディターに変更を許可します。</span><span class="sxs-lookup"><span data-stu-id="cb86a-133">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="cb86a-134">続行するように求めるメッセージが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb86a-134">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="cb86a-135">レジストリエディターに、設定が正常にレジストリに追加されたことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb86a-135">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="cb86a-136">エクスポートレポートを無効にする方法についてよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="cb86a-136">Frequently asked questions about disabling export reports</span></span>

 <span data-ttu-id="cb86a-137">**Results.csv レポートと Manifest.xml レポートとは**</span><span class="sxs-lookup"><span data-stu-id="cb86a-137">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="cb86a-138">Results.csv ファイルと Manifest.xml ファイルには、エクスポートされたコンテンツに関する追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cb86a-138">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="cb86a-139">**Results.csv**検索結果としてダウンロードされる各アイテムに関する情報を含む Excel ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="cb86a-139">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="cb86a-140">メールの場合、結果ログには、各メッセージに関する次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cb86a-140">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="cb86a-141">移行元のメールボックス内のメッセージの場所 (メッセージがプライマリ メールボックスとアーカイブ メールボックスのどちらであるかを含みます)。</span><span class="sxs-lookup"><span data-stu-id="cb86a-141">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="cb86a-142">メッセージが送信または受信された日付。</span><span class="sxs-lookup"><span data-stu-id="cb86a-142">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="cb86a-143">メッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="cb86a-143">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="cb86a-144">メッセージの送信者と受信者。</span><span class="sxs-lookup"><span data-stu-id="cb86a-144">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="cb86a-145">検索結果をエクスポートするときに重複除去を有効にした場合の、メッセージが重複しているかどうか。</span><span class="sxs-lookup"><span data-stu-id="cb86a-145">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="cb86a-146">重複するメッセージには、メッセージを重複として識別する**親 ItemId**の列に値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="cb86a-146">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="cb86a-147">**親 ItemId**列の値は、エクスポートされたメッセージの [ **Item DocumentId** ] 列の値と同じです。</span><span class="sxs-lookup"><span data-stu-id="cb86a-147">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="cb86a-148">SharePoint と OneDrive for Business サイトのドキュメントの場合、結果ログには、各ドキュメントに関する以下の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cb86a-148">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="cb86a-149">ドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="cb86a-149">The URL for the document.</span></span>
    
  - <span data-ttu-id="cb86a-150">ドキュメントがあるサイト コレクションの URL。</span><span class="sxs-lookup"><span data-stu-id="cb86a-150">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="cb86a-151">ドキュメントが最後に変更された日付。</span><span class="sxs-lookup"><span data-stu-id="cb86a-151">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="cb86a-152">ドキュメントの名前 (これは、結果のログの [件名] 列にあります)。</span><span class="sxs-lookup"><span data-stu-id="cb86a-152">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="cb86a-153">**Manifest.xml**検索結果に含まれる各アイテムに関する情報を含むマニフェストファイル (XML 形式)。</span><span class="sxs-lookup"><span data-stu-id="cb86a-153">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="cb86a-154">このレポートの情報は Results.csv レポートと同じですが、電子情報開示参照モデル (EDRM) によって指定された形式になっています。</span><span class="sxs-lookup"><span data-stu-id="cb86a-154">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="cb86a-155">EDRM の詳細については、「」を参照 [https://www.edrm.net](https://www.edrm.net) してください。</span><span class="sxs-lookup"><span data-stu-id="cb86a-155">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="cb86a-156">**これらのレポートのエクスポートを無効にする必要がある場合**</span><span class="sxs-lookup"><span data-stu-id="cb86a-156">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="cb86a-157">特定のニーズに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="cb86a-157">It depends on your specific needs.</span></span> <span data-ttu-id="cb86a-158">多くの組織では、検索結果に関する追加情報は必要ありません。これらのレポートは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cb86a-158">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="cb86a-159">**この操作を実行する必要があるコンピューター**</span><span class="sxs-lookup"><span data-stu-id="cb86a-159">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="cb86a-160">電子情報開示エクスポートツールを実行しているローカルコンピューターのレジストリ設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb86a-160">You have to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="cb86a-161">**この設定を変更した後、コンピューターを再起動する必要がありますか。**</span><span class="sxs-lookup"><span data-stu-id="cb86a-161">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="cb86a-162">いいえ、コンピューターを再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cb86a-162">No, you don't have to restart the computer.</span></span> <span data-ttu-id="cb86a-163">しかし、電子情報開示エクスポートツールが実行されている場合は、レジストリ設定を変更した後、それを閉じてから再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb86a-163">But if the eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="cb86a-164">**既存のレジストリキーを編集するか、新しいキーを作成しますか?**</span><span class="sxs-lookup"><span data-stu-id="cb86a-164">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="cb86a-165">このトピックの手順で作成した .reg ファイルを初めて実行するときに、新しいレジストリキーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cb86a-165">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="cb86a-166">その後、.reg の編集ファイルを変更して再実行するたびに、この設定が編集されます。</span><span class="sxs-lookup"><span data-stu-id="cb86a-166">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
