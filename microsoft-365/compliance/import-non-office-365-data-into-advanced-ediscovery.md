---
title: Microsoft 以外の365コンテンツをインポートして高度な電子情報開示分析を行う
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
description: Microsoft 365 に保存されていないコンテンツを Azure blob にインポートして、AeD で分析できるようにする手順
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be30daa35770247a9dd342b88093872083075547
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636954"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a><span data-ttu-id="ae0ae-103">Microsoft 以外の365コンテンツをインポートして高度な電子情報開示 (クラシック) 分析を行う</span><span class="sxs-lookup"><span data-stu-id="ae0ae-103">Import non-Microsoft 365 content for Advanced eDiscovery (classic) analysis</span></span>

<span data-ttu-id="ae0ae-104">上級電子情報開示を使用して分析する必要があるすべてのドキュメントが Microsoft 365 に存在するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-104">Not all documents that you may need to analyze with Advanced eDiscovery will live in Microsoft 365.</span></span> <span data-ttu-id="ae0ae-105">Advanced 電子情報開示の Microsoft 以外の365コンテンツインポート機能を使用すると、Microsoft 365 (PST ファイルを除く) に存在しないドキュメントを、ケースにリンクされた Azure ストレージ blob にアップロードし、アドバンスト eDiscovery で分析することができます。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-105">With the Non-Microsoft 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Microsoft 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="ae0ae-106">この手順では、Microsoft 以外の365ドキュメントを分析のために上級電子情報開示に移行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-106">This procedure shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae0ae-p102">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ae0ae-109">Microsoft 以外の365コンテンツについては、高度な電子情報開示データ記憶域アドオンサブスクリプションを購入できます。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-109">You can purchase an Advanced eDiscovery data storage add-on subscription for your non-Microsoft 365 content.</span></span> <span data-ttu-id="ae0ae-110">これは、Advanced eDiscovery で分析するコンテンツにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="ae0ae-111">「 [Microsoft 365 for business のアドオンを購入または編集する](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) 」の手順に従って、Advanced eDiscovery storage アドオンを購入します。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-111">Follow the steps in [Buy or edit an add-on for Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) and purchase the Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="ae0ae-112">Office 以外の365コンテンツをアップロードするための要件</span><span class="sxs-lookup"><span data-stu-id="ae0ae-112">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="ae0ae-113">この手順の説明に従って Office 365 以外のアップロード機能を使用するには、次の条件を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="ae0ae-114">高度なコンプライアンスアドオンまたは E5 サブスクリプションを備えた Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>
    
- <span data-ttu-id="ae0ae-115">Office 以外の365コンテンツをアップロードするすべての保管担当者には、高度なコンプライアンスアドオンまたは E5 ライセンスを含む E3 が必要です。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>
    
- <span data-ttu-id="ae0ae-116">既存の電子情報開示ケース。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-116">An existing eDiscovery case.</span></span>
    
- <span data-ttu-id="ae0ae-117">収集されたすべてのファイルは、保管担当者ごとにフォルダーが1つ存在し、フォルダーの名前がこの形式  *alias@domainname*  であるフォルダーにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="ae0ae-118">*Alias@domainname*は、ユーザーの Office 365 エイリアスおよびドメインである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="ae0ae-119">すべての  *alias@domainname*  フォルダーをルートフォルダーに収集できます。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="ae0ae-120">ルートフォルダーに含めることができるのは  *alias@domainname*  フォルダーのみで、ルートフォルダーには圧縮されていないファイルは存在しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder.</span></span>
    
- <span data-ttu-id="ae0ae-121">電子情報開示マネージャーまたは電子情報開示管理者のどちらかのアカウント。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-121">An account that is either an eDiscovery Manager or eDiscovery Administrator.</span></span>
    
- <span data-ttu-id="ae0ae-122">Office 365 以外のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされた[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) 。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="ae0ae-123">Office 以外の365コンテンツを上級電子情報開示にアップロードする</span><span class="sxs-lookup"><span data-stu-id="ae0ae-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>


1. <span data-ttu-id="ae0ae-124">電子情報開示マネージャーまたは電子情報開示管理者として、 **電子情報開示**を開いて、Office 以外の365データがアップロードされるケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="ae0ae-125">ケースを作成する必要がある場合は、「 [Security &amp; コンプライアンスセンターで電子情報開示ケースを管理](ediscovery-cases.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-125">If you need to create a case, see [Manage eDiscovery cases in the Security &amp; Compliance Center](ediscovery-cases.md).</span></span>
    
2. <span data-ttu-id="ae0ae-126">[ **高度な電子情報開示に切り替え] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-126">Click **Switch to Advanced eDiscovery**.</span></span>

3. <span data-ttu-id="ae0ae-127">メニューから [ **レビューセット** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-127">Select **Review Sets** from the menu.</span></span>

4. <span data-ttu-id="ae0ae-128">既存のレビューセットを選択するか、[ **レビューセットの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-128">Select an existing Review Set or choose **Add Review Set**.</span></span>

5. <span data-ttu-id="ae0ae-129">[ **レビューセットの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-129">Select **Manage review set**.</span></span>

6. <span data-ttu-id="ae0ae-130">Office 365 以外のデータカードで、[ **アップロードの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-130">In the Non-Office 365 data card, select **View Uploads**.</span></span>

7. <span data-ttu-id="ae0ae-131">[ **ファイルのアップロード** ] を選択して、ファイルアップロードウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-131">Choose **Upload files** to start the file upload wizard.</span></span>

8. <span data-ttu-id="ae0ae-132">最初のタブは **1 です。準備手順**。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-132">The first tab is **1. Prepare step**.</span></span> <span data-ttu-id="ae0ae-133">[ **次へ: ファイルのアップロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-133">Select **Next: Upload files**.</span></span>

9. <span data-ttu-id="ae0ae-134">**2[ファイルのアップロード**] タブまだインストールしていない場合は、AzCopy.exe ダウンロードするかどうかを確認するメッセージが表示されたら、ファイルの場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-134">On the **2. Upload files** tab you will be prompted to download AzCopy.exe if you have not done so already, and then to provide the path to the file location.</span></span> <span data-ttu-id="ae0ae-135">たとえば、に `C:\Upload`  は AzCopy.exe を実行するコマンドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-135">For example, `C:\Upload`  will give you the command to execute AzCopy.exe.</span></span> <span data-ttu-id="ae0ae-136">を使用 `C:\Upload` すると、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-136">Using `C:\Upload`, you will see:</span></span>

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. <span data-ttu-id="ae0ae-137">コマンドプロンプトウィンドウを開き、AzCopy.exe コマンドを実行して、データを Azure にインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-137">Open a command prompt window and execute the AzCopy.exe command to import the data into Azure.</span></span> <span data-ttu-id="ae0ae-138">すべてのデータを読み込んだら、[ **次へ: ファイルの処理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-138">Once it has loaded all of the data, select **Next: Process files**.</span></span>

11. <span data-ttu-id="ae0ae-139">次のタブは **3 です。** データが関連付けられている保管担当者が表示されるファイルを処理し、インポートされるデータの進行状況も表示します。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-139">The next tab is **3. Process files** where you will see the custodians that have data associated with them and will also show you the progress of the data being imported.</span></span>
        
    <span data-ttu-id="ae0ae-140">Azcopy 構文の詳細については、「 [Windows での AzCopy を使用してデータを転送する](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-140">For more information on Azcopy syntax, see [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span> 
    
    <span data-ttu-id="ae0ae-141">高度な電子情報開示処理の詳細については、「 [Process module を実行する」および「Advanced ediscovery (classic) でデータを読み込む](run-the-process-module-and-load-data-in-advanced-ediscovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-141">For more details on Advanced eDiscovery Processing, see [Run the Process module and load data in Advanced eDiscovery (classic)](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="ae0ae-142">ユーザーごとに1つのルートフォルダーが必要で、フォルダー名は <b>alias@domainname</b>  形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-142">There must be one root folder per user and the folder name must be in the <b>alias@domainname</b>  format.</span></span> 
   
    > [!IMPORTANT]
    > <span data-ttu-id="ae0ae-143">上級電子情報開示でコンテナーが正常に処理されると、Azure の SAS ストレージに新しいコンテンツを追加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-143">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="ae0ae-144">追加のコンテンツを収集し、高度な電子情報開示分析のケースに追加する場合は、 **Office 365 以外** の新しいデータコンテナーを作成し、この手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-144">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="ae0ae-145">*フォルダーの名前付けの問題によってコンテナーが正常に処理されず*に問題が修正された場合は、この記事の手順を使用して、新しいコンテナーと再接続を作成し、再度アップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae0ae-145">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span>
