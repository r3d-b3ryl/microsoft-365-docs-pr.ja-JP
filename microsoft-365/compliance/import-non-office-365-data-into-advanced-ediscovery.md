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
ms.openlocfilehash: be49e7d44c56988baa3cdc718498a03ee4acd50b
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214541"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a><span data-ttu-id="1d46d-103">Microsoft 以外の365コンテンツをインポートして高度な電子情報開示 (クラシック) 分析を行う</span><span class="sxs-lookup"><span data-stu-id="1d46d-103">Import non-Microsoft 365 content for Advanced eDiscovery (classic) analysis</span></span>

<span data-ttu-id="1d46d-104">上級電子情報開示を使用して分析する必要があるすべてのドキュメントが Microsoft 365 に存在するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="1d46d-104">Not all documents that you may need to analyze with Advanced eDiscovery will live in Microsoft 365.</span></span> <span data-ttu-id="1d46d-105">Advanced 電子情報開示の Microsoft 以外の365コンテンツインポート機能を使用すると、Microsoft 365 (PST ファイルを除く) に存在しないドキュメントを、ケースにリンクされた Azure ストレージ blob にアップロードし、アドバンスト eDiscovery で分析することができます。</span><span class="sxs-lookup"><span data-stu-id="1d46d-105">With the Non-Microsoft 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Microsoft 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="1d46d-106">この手順では、Microsoft 以外の365ドキュメントを分析のために上級電子情報開示に移行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1d46d-106">This procedure shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1d46d-p102">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="1d46d-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1d46d-109">Microsoft 以外の365コンテンツについては、高度な電子情報開示データ記憶域アドオンサブスクリプションを購入できます。</span><span class="sxs-lookup"><span data-stu-id="1d46d-109">You can purchase an Advanced eDiscovery data storage add-on subscription for your non-Microsoft 365 content.</span></span> <span data-ttu-id="1d46d-110">これは、Advanced eDiscovery で分析するコンテンツにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d46d-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="1d46d-111">「 [Microsoft 365 for business のアドオンを購入または編集する](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on)」の手順に従って、Advanced eDiscovery storage アドオンを購入します。</span><span class="sxs-lookup"><span data-stu-id="1d46d-111">Follow the steps in [Buy or edit an add-on for Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) and purchase the Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="1d46d-112">始める前に</span><span class="sxs-lookup"><span data-stu-id="1d46d-112">Before you begin</span></span>

<span data-ttu-id="1d46d-113">この手順の説明に従って Office 365 以外のアップロード機能を使用するには、次の条件を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d46d-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="1d46d-114">高度なコンプライアンスアドオンまたは E5 サブスクリプションを使用した Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="1d46d-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription</span></span>
    
- <span data-ttu-id="1d46d-115">Office 以外の365コンテンツをアップロードするすべての保管担当者には、高度なコンプライアンスアドオンまたは E5 ライセンスを含む E3 が必要です。</span><span class="sxs-lookup"><span data-stu-id="1d46d-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses</span></span>
    
- <span data-ttu-id="1d46d-116">既存の電子情報開示ケース</span><span class="sxs-lookup"><span data-stu-id="1d46d-116">An existing eDiscovery case</span></span>
    
- <span data-ttu-id="1d46d-117">収集されたすべてのファイルは、保管担当者ごとにフォルダーが1つ存在し、フォルダーの名前がこの形式*alias@domainname*であるフォルダーにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="1d46d-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="1d46d-118">*Alias@domainname*は、ユーザーの Office 365 エイリアスおよびドメインである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d46d-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="1d46d-119">すべての*alias@domainname*フォルダーをルートフォルダーに収集できます。</span><span class="sxs-lookup"><span data-stu-id="1d46d-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="1d46d-120">ルートフォルダーには*alias@domainname*フォルダーのみ含めることができます。ルートフォルダーには圧縮されていないファイルは存在しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d46d-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder</span></span> 
    
- <span data-ttu-id="1d46d-121">電子情報開示マネージャーまたは電子情報開示管理者のどちらかのアカウント</span><span class="sxs-lookup"><span data-stu-id="1d46d-121">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>
    
- <span data-ttu-id="1d46d-122">Office 365 以外のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされた[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) 。</span><span class="sxs-lookup"><span data-stu-id="1d46d-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="1d46d-123">Office 以外の365コンテンツを上級電子情報開示にアップロードする</span><span class="sxs-lookup"><span data-stu-id="1d46d-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>


1. <span data-ttu-id="1d46d-124">電子情報開示マネージャーまたは電子情報開示管理者として、**電子情報開示**を開いて、Office 以外の365データがアップロードされるケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="1d46d-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="1d46d-125">ケースを作成する必要がある場合は、「 [Security &amp; コンプライアンスセンターで電子情報開示ケースを管理](ediscovery-cases.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d46d-125">If you need to create a case, see [Manage eDiscovery cases in the Security &amp; Compliance Center](ediscovery-cases.md)</span></span>
    
2. <span data-ttu-id="1d46d-126">[**高度な電子情報開示に切り替え] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="1d46d-126">Click **Switch to Advanced eDiscovery**</span></span>
    
3. <span data-ttu-id="1d46d-127">[**ソースの種類**] で **、[Office 以外の365データ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d46d-127">Under **Source type** select **Non-Office 365 data**.</span></span>
    
4. <span data-ttu-id="1d46d-128">[**コンテナーの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d46d-128">Click **Add container**.</span></span> <span data-ttu-id="1d46d-129">コンテナーの名前を指定し、説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="1d46d-129">Name the container and add a description.</span></span>
    
5. <span data-ttu-id="1d46d-130">[コンテナー] ボックスの一覧から新しく追加したコンテナーを選択し、[コンテナー詳細] ウィンドウに表示される URL をコピーして、ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="1d46d-130">Select the newly added container from the container list and copy the URL that appears in the container details pane and then close the pane</span></span>
    
6. <span data-ttu-id="1d46d-131">管理者としてコマンドプロンプトを開き、AzCopy がインストールされているフォルダーにディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="1d46d-131">Open a command prompt as an administrator and change directory to folder where you have AzCopy installed..</span></span>
    
7. <span data-ttu-id="1d46d-132">AzCopy コマンドラインを作成して、次のようにファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="1d46d-132">Construct the AzCopy command line to upload the files like this:</span></span>
    
    <span data-ttu-id="1d46d-133">AzCopy/Source: "*ローカルコンピューター上のルートフォルダーへの完全なパス*"/Dest: "*コンテナー URL があるかどうか*。</span><span class="sxs-lookup"><span data-stu-id="1d46d-133">AzCopy /Source:" *full path to root folder on local machine*  " /Dest:"  *container URL up to but not including the ?*</span></span>  <span data-ttu-id="1d46d-134">"/Destsas:"*コンテナー url の残りの部分を end* "/S.</span><span class="sxs-lookup"><span data-stu-id="1d46d-134">" /DestSAS:"  *remainder of the container url from the ? to the end*  " /S.</span></span> 
    
    <span data-ttu-id="1d46d-135">たとえば、次のような値を使用します。</span><span class="sxs-lookup"><span data-stu-id="1d46d-135">For example, using these values:</span></span> 
    
  - <span data-ttu-id="1d46d-136">ルートフォルダー-c/一度収集したデータ</span><span class="sxs-lookup"><span data-stu-id="1d46d-136">root folder - C:\Collected Data</span></span> 
    
  - <span data-ttu-id="1d46d-137">コンテナーの url- https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp ; sr = c &amp; Si = NonOfficeData15% 7C0 &amp; sig = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3d</span><span class="sxs-lookup"><span data-stu-id="1d46d-137">container url - https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D</span></span>
    
    <span data-ttu-id="1d46d-138">AzCopy コマンドライン構文は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1d46d-138">the AzCopy command line syntax would be:</span></span>
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    <span data-ttu-id="1d46d-139">Azcopy 構文の詳細については、「 [Windows での AzCopy を使用してデータを転送する](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d46d-139">For more information on Azcopy syntax see, [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="1d46d-140">ユーザーごとに1つのルートフォルダーが必要で、フォルダー名は*alias@domainname*形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d46d-140">There must be one root folder per user and the folder name must be in the  *alias@domainname*  format.</span></span> 
  
8. <span data-ttu-id="1d46d-141">フォルダーのアップロードが完了したら、[Advanced eDiscovery] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="1d46d-141">Once the folders have finished uploading, switch back to Advanced eDiscovery.</span></span> <span data-ttu-id="1d46d-142">アップロードしたフォルダーの内容は、高度な電子情報開示で処理する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="1d46d-142">The content in the folders you uploaded is now ready to be processed in Advanced eDiscovery.</span></span> <span data-ttu-id="1d46d-143">コンテナーを選択し、[プロセス] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d46d-143">Select the container and click the Process button.</span></span> <span data-ttu-id="1d46d-144">高度な電子情報開示の処理の詳細については、「 [Process モジュールを実行する」および「Advanced ediscovery でデータを読み込む](run-the-process-module-and-load-data-in-advanced-ediscovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d46d-144">For more details on Advanced eDiscovery Processing see, [Run the Process module and load data in Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1d46d-145">上級電子情報開示でコンテナーが正常に処理されると、Azure の SAS ストレージに新しいコンテンツを追加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="1d46d-145">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="1d46d-146">追加のコンテンツを収集し、高度な電子情報開示分析のケースに追加する場合は、 **Office 365 以外**の新しいデータコンテナーを作成し、この手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d46d-146">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="1d46d-147">*フォルダーの名前付けの問題によってコンテナーが正常に処理されず*に問題が修正された場合は、この記事の手順を使用して、新しいコンテナーと再接続を作成し、再度アップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d46d-147">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span>
