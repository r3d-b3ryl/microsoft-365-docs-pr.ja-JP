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
description: ローカル コンピューター Windowsレジストリを編集して、セキュリティ コンプライアンス センターからコンテンツ検索の結果をエクスポートするときにレポートを&します。
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817856"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="7ed85-103">コンテンツ検索の結果をエクスポートするときにレポートを無効にする</span><span class="sxs-lookup"><span data-stu-id="7ed85-103">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="7ed85-104">電子情報開示エクスポート ツールを使用してセキュリティ & コンプライアンス センターでコンテンツ検索の結果をエクスポートすると、エクスポートされたコンテンツに関する追加情報を含む 2 つのレポートが自動的に作成およびエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="7ed85-104">When you use the eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="7ed85-105">これらのレポートは、Results.csv ファイルと Manifest.xml ファイルです (これらのレポート[](#frequently-asked-questions-about-disabling-export-reports)の詳細については、このトピックの「エクスポート レポートの無効化に関するよく寄せられる質問」セクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="7ed85-105">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="7ed85-106">これらのファイルは非常に大きいので、これらのファイルがエクスポートされるのを防ぐことで、ダウンロード時間を高速化し、ディスク領域を節約できます。</span><span class="sxs-lookup"><span data-stu-id="7ed85-106">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="7ed85-107">これを行うには、検索結果Windowsエクスポートするために使用するコンピューターのレジストリを変更します。</span><span class="sxs-lookup"><span data-stu-id="7ed85-107">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="7ed85-108">後でレポートを含める場合は、レジストリ設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="7ed85-108">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="7ed85-109">エクスポート レポートを無効にするレジストリ設定を作成する</span><span class="sxs-lookup"><span data-stu-id="7ed85-109">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="7ed85-110">コンテンツ検索の結果をエクスポートするために使用するコンピューターで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7ed85-110">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="7ed85-111">開いている場合は、電子情報開示エクスポート ツールを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7ed85-111">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="7ed85-112">無効にするエクスポート レポートに応じて、次の手順の 1 つまたは両方を実行します。</span><span class="sxs-lookup"><span data-stu-id="7ed85-112">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="7ed85-113">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="7ed85-113">**Results.csv**</span></span>
    
      <span data-ttu-id="7ed85-114">ファイル名のサフィックス .reg をWindowsして、次のテキストをレジストリ ファイルに保存します。たとえば、DisableResultsCsv.reg などです。</span><span class="sxs-lookup"><span data-stu-id="7ed85-114">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="7ed85-115">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="7ed85-115">**Manifest.xml**</span></span>
    
      <span data-ttu-id="7ed85-116">ファイル名のサフィックス .reg をWindowsして、次のテキストをレジストリ ファイルに保存します。たとえば、DisableManifestXml.reg などです。</span><span class="sxs-lookup"><span data-stu-id="7ed85-116">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="7ed85-117">[Windows エクスプローラーで、前の手順で作成した .reg ファイルをクリックまたはダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ed85-117">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="7ed85-118">[ユーザー アクセス制御] ウィンドウで、[ **は** い] をクリックしてレジストリ エディターで変更を行います。</span><span class="sxs-lookup"><span data-stu-id="7ed85-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="7ed85-119">続行するように求めるメッセージが表示されたら、[はい] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7ed85-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="7ed85-120">レジストリ エディターには、設定がレジストリに正常に追加されたことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ed85-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="7ed85-121">レジストリ設定を編集してエクスポート レポートを再び有効にする</span><span class="sxs-lookup"><span data-stu-id="7ed85-121">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="7ed85-122">前の手順で .reg ファイルを作成して Results.csv レポートと Manifest.xml レポートを無効にした場合は、それらのファイルを編集してレポートを再び有効にして、検索結果と一緒にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="7ed85-122">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="7ed85-123">繰り返しになりますが、結果をコンテンツ検索のエクスポートに使用するコンピューターで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7ed85-123">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="7ed85-124">開いている場合は、電子情報開示エクスポート ツールを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7ed85-124">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="7ed85-125">前の手順で作成した .reg 編集ファイルの一方または両方を編集します。</span><span class="sxs-lookup"><span data-stu-id="7ed85-125">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="7ed85-126">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="7ed85-126">**Results.csv**</span></span>
    
        <span data-ttu-id="7ed85-127">[DisableResultsCsv.reg] ファイルを開メモ帳に値を変更し、 `False` `True` ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7ed85-127">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="7ed85-128">たとえば、ファイルを編集すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7ed85-128">For example, after you edit the file, it looks like this:</span></span>
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="7ed85-129">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="7ed85-129">**Manifest.xml**</span></span>
    
        <span data-ttu-id="7ed85-130">次のコマンドで DisableManifestXml.reg ファイルを開メモ帳に値を変更し、 `False` `True` ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7ed85-130">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="7ed85-131">たとえば、ファイルを編集すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7ed85-131">For example, after you edit the file, it looks like this:</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="7ed85-132">[Windowsエクスプローラーで、前の手順で編集した .reg ファイルをクリックまたはダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ed85-132">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="7ed85-133">[ユーザー アクセス制御] ウィンドウで、[ **は** い] をクリックしてレジストリ エディターで変更を行います。</span><span class="sxs-lookup"><span data-stu-id="7ed85-133">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="7ed85-134">続行するように求めるメッセージが表示されたら、[はい] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7ed85-134">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="7ed85-135">レジストリ エディターには、設定がレジストリに正常に追加されたことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ed85-135">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="7ed85-136">エクスポート レポートの無効化に関するよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="7ed85-136">Frequently asked questions about disabling export reports</span></span>

 <span data-ttu-id="7ed85-137">**レポートとResults.csvレポートManifest.xml。**</span><span class="sxs-lookup"><span data-stu-id="7ed85-137">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="7ed85-138">ファイルResults.csvおよびManifest.xmlファイルには、エクスポートされたコンテンツに関する追加情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="7ed85-138">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="7ed85-139">**Results.csv** 検索結果Excelダウンロードされる各アイテムに関する情報を含むドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="7ed85-139">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="7ed85-140">電子メールの場合、結果ログには、次を含む各メッセージに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ed85-140">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="7ed85-141">移行元のメールボックス内のメッセージの場所 (メッセージがプライマリ メールボックスとアーカイブ メールボックスのどちらであるかを含みます)。</span><span class="sxs-lookup"><span data-stu-id="7ed85-141">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="7ed85-142">メッセージが送信または受信された日付。</span><span class="sxs-lookup"><span data-stu-id="7ed85-142">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="7ed85-143">メッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="7ed85-143">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="7ed85-144">メッセージの送信者と受信者。</span><span class="sxs-lookup"><span data-stu-id="7ed85-144">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="7ed85-145">検索結果のエクスポート時に重複除外を有効にした場合、メッセージが重複メッセージかどうか。</span><span class="sxs-lookup"><span data-stu-id="7ed85-145">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="7ed85-146">重複メッセージには、メッセージを重複として識別する [ **親 ItemId]** 列の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ed85-146">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="7ed85-147">[親 **ItemId] 列の** 値は、エクスポートされたメッセージの **[アイテム ドキュメント Id]** 列の値と同じです。</span><span class="sxs-lookup"><span data-stu-id="7ed85-147">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="7ed85-148">サイトおよびサイトSharePoint OneDrive for Business、結果ログには、次を含む各ドキュメントに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ed85-148">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="7ed85-149">ドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="7ed85-149">The URL for the document.</span></span>
    
  - <span data-ttu-id="7ed85-150">ドキュメントがあるサイト コレクションの URL。</span><span class="sxs-lookup"><span data-stu-id="7ed85-150">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="7ed85-151">ドキュメントが最後に変更された日付。</span><span class="sxs-lookup"><span data-stu-id="7ed85-151">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="7ed85-152">ドキュメントの名前 (これは、結果のログの [件名] 列にあります)。</span><span class="sxs-lookup"><span data-stu-id="7ed85-152">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="7ed85-153">**Manifest.xml** 検索結果に含まれる各アイテムに関する情報を含むマニフェスト ファイル (XML 形式)。</span><span class="sxs-lookup"><span data-stu-id="7ed85-153">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="7ed85-154">このレポートの情報は、Results.csvレポートと同じですが、電子探索参照モデル (EDRM) で指定された形式です。</span><span class="sxs-lookup"><span data-stu-id="7ed85-154">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="7ed85-155">EDRM の詳細については、 を参照してください [https://www.edrm.net](https://www.edrm.net) 。</span><span class="sxs-lookup"><span data-stu-id="7ed85-155">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="7ed85-156">**これらのレポートのエクスポートを無効にすべきな場合**</span><span class="sxs-lookup"><span data-stu-id="7ed85-156">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="7ed85-157">特定のニーズに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="7ed85-157">It depends on your specific needs.</span></span> <span data-ttu-id="7ed85-158">多くの組織は検索結果に関する追加情報を必要とし、これらのレポートを必要とします。</span><span class="sxs-lookup"><span data-stu-id="7ed85-158">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="7ed85-159">**これを実行する必要があるコンピューターは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="7ed85-159">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="7ed85-160">電子情報開示エクスポート ツールを実行するローカル コンピューターのレジストリ設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ed85-160">You have to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="7ed85-161">**この設定を変更した後、コンピューターを再起動する必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="7ed85-161">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="7ed85-162">いいえ、コンピューターを再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7ed85-162">No, you don't have to restart the computer.</span></span> <span data-ttu-id="7ed85-163">ただし、電子情報開示エクスポート ツールが実行されている場合は、レジストリ設定を変更した後、電子情報開示エクスポート ツールを閉じてから再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ed85-163">But if the eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="7ed85-164">**既存のレジストリ キーが編集されるのか、新しいキーが作成されるのか。**</span><span class="sxs-lookup"><span data-stu-id="7ed85-164">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="7ed85-165">このトピックの手順で作成した .reg ファイルを初めて実行すると、新しいレジストリ キーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7ed85-165">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="7ed85-166">その後、.reg 編集ファイルを変更して再実行する度に設定が編集されます。</span><span class="sxs-lookup"><span data-stu-id="7ed85-166">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
