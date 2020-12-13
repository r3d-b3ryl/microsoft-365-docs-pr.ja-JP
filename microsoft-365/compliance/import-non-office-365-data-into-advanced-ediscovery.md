---
title: Advanced eDiscovery 分析用に Microsoft 365 以外のコンテンツをインポートする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Microsoft 365 に保存されていないコンテンツを Azure BLOB にインポートして AeD で分析する方法
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 03220e6baf16662ad8dfa970ef4d7077d08b0826
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662902"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a><span data-ttu-id="8db60-103">Advanced eDiscovery (クラシック) 分析用に Microsoft 365 以外のコンテンツをインポートする</span><span class="sxs-lookup"><span data-stu-id="8db60-103">Import non-Microsoft 365 content for Advanced eDiscovery (classic) analysis</span></span>

<span data-ttu-id="8db60-104">Advanced eDiscovery を使用して分析する必要がある可能性のあるすべてのドキュメントが Microsoft 365 に保存されるとは異なる。</span><span class="sxs-lookup"><span data-stu-id="8db60-104">Not all documents that you may need to analyze with Advanced eDiscovery will live in Microsoft 365.</span></span> <span data-ttu-id="8db60-105">Advanced eDiscovery の Microsoft 365 以外のコンテンツ インポート機能を使用すると、Microsoft 365 (PST ファイルを除く) に保存されていないドキュメントを、Azure ストレージ BLOB をリンクされたケースにアップロードし、Advanced eDiscovery で分析できます。</span><span class="sxs-lookup"><span data-stu-id="8db60-105">With the Non-Microsoft 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Microsoft 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="8db60-106">この手順では、Microsoft 365 以外のドキュメントを分析のために Advanced eDiscovery に取り込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8db60-106">This procedure shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8db60-p102">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="8db60-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8db60-109">Microsoft 365 以外のコンテンツの Advanced eDiscovery データ ストレージ アドオン サブスクリプションを購入できます。</span><span class="sxs-lookup"><span data-stu-id="8db60-109">You can purchase an Advanced eDiscovery data storage add-on subscription for your non-Microsoft 365 content.</span></span> <span data-ttu-id="8db60-110">これは、Advanced eDiscovery で分析されるコンテンツに対して排他的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="8db60-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="8db60-111">「ビジネス向け [Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) のアドオンを購入または編集する」の手順に従って、Advanced eDiscovery ストレージ アドオンを購入します。</span><span class="sxs-lookup"><span data-stu-id="8db60-111">Follow the steps in [Buy or edit an add-on for Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) and purchase the Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="8db60-112">365 以外のコンテンツOfficeアップロードする要件</span><span class="sxs-lookup"><span data-stu-id="8db60-112">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="8db60-113">この手順で説明するように、Office 365 以外のアップロード機能を使用するには、以下が必要です。</span><span class="sxs-lookup"><span data-stu-id="8db60-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="8db60-114">Advanced Compliance Officeまたは E5 サブスクリプションを使用する 365 E3 をサポートします。</span><span class="sxs-lookup"><span data-stu-id="8db60-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>
    
- <span data-ttu-id="8db60-115">365 以外のコンテンツOfficeアップロードされるすべての保管担当者は、Advanced Compliance アドオンまたは E5 ライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db60-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>
    
- <span data-ttu-id="8db60-116">既存の電子情報開示ケース。</span><span class="sxs-lookup"><span data-stu-id="8db60-116">An existing eDiscovery case.</span></span>
    
- <span data-ttu-id="8db60-117">アップロードするファイルはすべて、保管担当者ごとに 1 つのフォルダーが含まれ、フォルダーの名前が次の形式 *alias@domainname。*</span><span class="sxs-lookup"><span data-stu-id="8db60-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="8db60-118">この  *alias@domainname*  は、365 エイリアスOfficeドメインを持つユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db60-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="8db60-119">ルート フォルダーには  *、alias@domainname*  フォルダーを収集できます。</span><span class="sxs-lookup"><span data-stu-id="8db60-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="8db60-120">ルート フォルダーには、ルートフォルダー alias@domainname、ルート フォルダーにルース ファイルが含まれている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8db60-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder.</span></span>
    
- <span data-ttu-id="8db60-121">電子情報開示マネージャーまたは電子情報開示管理者であるアカウント。</span><span class="sxs-lookup"><span data-stu-id="8db60-121">An account that is either an eDiscovery Manager or eDiscovery Administrator.</span></span>
    
- <span data-ttu-id="8db60-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) は、365 以外のコンテンツ フォルダー構造にアクセスOfficeコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8db60-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="8db60-123">Advanced eDiscovery Office 365 以外のコンテンツをアップロードする</span><span class="sxs-lookup"><span data-stu-id="8db60-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>


1. <span data-ttu-id="8db60-124">電子情報開示マネージャーまたは電子情報開示管理者として電子情報開示を開き、非電子情報開示 365 データOfficeアップロードするケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="8db60-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="8db60-125">ケースを作成する必要がある場合は、「セキュリティ コンプライアンス センターで電子情報開示ケースを管理する [」を &amp; 参照してください](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="8db60-125">If you need to create a case, see [Manage eDiscovery cases in the Security &amp; Compliance Center](ediscovery-cases.md).</span></span>
    
2. <span data-ttu-id="8db60-126">[Advanced **eDiscovery に切り替える] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8db60-126">Click **Switch to Advanced eDiscovery**.</span></span>

3. <span data-ttu-id="8db60-127">メニュー **から [Review Sets]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8db60-127">Select **Review Sets** from the menu.</span></span>

4. <span data-ttu-id="8db60-128">既存のレビュー セットを選択するか、[レビュー セットの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8db60-128">Select an existing Review Set or choose **Add Review Set**.</span></span>

5. <span data-ttu-id="8db60-129">[レビュー **セットの管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8db60-129">Select **Manage review set**.</span></span>

6. <span data-ttu-id="8db60-130">In the Non-Office 365 data card, select **View Uploads**.</span><span class="sxs-lookup"><span data-stu-id="8db60-130">In the Non-Office 365 data card, select **View Uploads**.</span></span>

7. <span data-ttu-id="8db60-131">[ファイル **のアップロード] を** 選択して、ファイルのアップロード ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="8db60-131">Choose **Upload files** to start the file upload wizard.</span></span>

8. <span data-ttu-id="8db60-132">最初のタブは **1 です。手順を準備します**。</span><span class="sxs-lookup"><span data-stu-id="8db60-132">The first tab is **1. Prepare step**.</span></span> <span data-ttu-id="8db60-133">[次 **へ] を選択します。ファイルをアップロードします**。</span><span class="sxs-lookup"><span data-stu-id="8db60-133">Select **Next: Upload files**.</span></span>

9. <span data-ttu-id="8db60-134">On the **2.[ファイル** のアップロード] タブでは、まだダウンロードしていない場合AzCopy.exeをダウンロードし、ファイルの場所へのパスを指定するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8db60-134">On the **2. Upload files** tab you will be prompted to download AzCopy.exe if you have not done so already, and then to provide the path to the file location.</span></span> <span data-ttu-id="8db60-135">たとえば、 `C:\Upload`  このコマンドを実行するコマンドが表示AzCopy.exe。</span><span class="sxs-lookup"><span data-stu-id="8db60-135">For example, `C:\Upload`  will give you the command to execute AzCopy.exe.</span></span> <span data-ttu-id="8db60-136">使用 `C:\Upload` すると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8db60-136">Using `C:\Upload`, you will see:</span></span>

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. <span data-ttu-id="8db60-137">コマンド プロンプト ウィンドウを開き、AzCopy.exeコマンドを実行してデータを Azure にインポートします。</span><span class="sxs-lookup"><span data-stu-id="8db60-137">Open a command prompt window and execute the AzCopy.exe command to import the data into Azure.</span></span> <span data-ttu-id="8db60-138">すべてのデータが読み込まれたら、[次へ: ファイルの処理 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8db60-138">Once it has loaded all of the data, select **Next: Process files**.</span></span>

11. <span data-ttu-id="8db60-139">次のタブは **3 です。データが** 関連付けられている保管担当者が表示され、インポートされるデータの進行状況も表示されるプロセス ファイル。</span><span class="sxs-lookup"><span data-stu-id="8db60-139">The next tab is **3. Process files** where you will see the custodians that have data associated with them and will also show you the progress of the data being imported.</span></span>
        
    <span data-ttu-id="8db60-140">Azcopy 構文の詳細については、「Windows での AzCopy によるデータの [転送」を参照してください](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="8db60-140">For more information on Azcopy syntax, see [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span> 
    
    <span data-ttu-id="8db60-141">Advanced eDiscovery 処理の詳細については、「プロセス モジュールを実行し、Advanced eDiscovery でデータを読み込む [(クラシック)」を参照してください](run-the-process-module-and-load-data-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="8db60-141">For more details on Advanced eDiscovery Processing, see [Run the Process module and load data in Advanced eDiscovery (classic)](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="8db60-142">ユーザーごとに 1 つのルート フォルダーが必要です。また、フォルダー名は新しいフォルダー <b>形式alias@domainnameがあります</b>  。</span><span class="sxs-lookup"><span data-stu-id="8db60-142">There must be one root folder per user and the folder name must be in the <b>alias@domainname</b>  format.</span></span> 
   
    > [!IMPORTANT]
    > <span data-ttu-id="8db60-143">コンテナーが Advanced eDiscovery で正常に処理されると、Azure の SAS ストレージに新しいコンテンツを追加できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8db60-143">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="8db60-144">追加のコンテンツを収集し、Advanced eDiscovery 分析のケースに追加する場合は、新しい非 Office **365 データ コンテナー** を作成し、この手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db60-144">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="8db60-145">フォルダーの名前付けの問題が原因でコンテナーが正常に処理されない場合に問題を修正した場合でも、この記事の手順を使用して新しいコンテナーを作成し、再接続してアップロードし直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db60-145">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span>
