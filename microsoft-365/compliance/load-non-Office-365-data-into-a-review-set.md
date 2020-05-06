---
title: Microsoft 以外の365データをレビューセットに読み込む
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
description: 高度な電子情報開示ケースで分析のために Microsoft 以外の365データをレビューセットにインポートする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed4a26ea1dd68b9198cce67ce0f97580ed4b2a99
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034425"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a><span data-ttu-id="9f3bd-103">Microsoft 以外の365データをレビューセットに読み込む</span><span class="sxs-lookup"><span data-stu-id="9f3bd-103">Load non-Microsoft 365 data into a review set</span></span>

<span data-ttu-id="9f3bd-104">Advanced eDiscovery で分析する必要があるすべてのドキュメントが Microsoft 365 にあるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Microsoft 365.</span></span> <span data-ttu-id="9f3bd-105">Advanced eDiscovery の Microsoft 以外の365データインポート機能を使用すると、Microsoft 365 に含まれていないドキュメントをレビューセットにアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-105">With the non-Microsoft 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Microsoft 365 to a review set.</span></span> <span data-ttu-id="9f3bd-106">この記事では、Microsoft 以外の365ドキュメントを分析のために上級電子情報開示に移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-106">This article shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9f3bd-107">はじめに</span><span class="sxs-lookup"><span data-stu-id="9f3bd-107">Before you begin</span></span>

<span data-ttu-id="9f3bd-108">この記事に記載されている 365 Microsoft 以外のアップロードをアップロードする機能を使用するには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-108">Using the upload non-Microsoft 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="9f3bd-109">Microsoft 以外の365コンテンツに関連付ける必要があるすべての保管担当者には、適切なライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-109">All custodians that you want to associate non-Microsoft 365 content to must be assigned the appropriate license.</span></span> <span data-ttu-id="9f3bd-110">詳細については、「 [Advanced eDiscovery の概要](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-110">For more information, see [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span></span>

- <span data-ttu-id="9f3bd-111">既存の高度な電子情報開示ケース。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-111">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="9f3bd-112">Microsoft 以外の365データをアップロードして関連付けするには、その前に保管担当者をケースに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-112">Custodians must be added to the case before you can upload and associate the non-Microsoft 365 data to them.</span></span>

- <span data-ttu-id="9f3bd-113">Microsoft 以外の365データは、Advanced eDiscovery でサポートされているファイルの種類である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-113">Non-Microsoft 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="9f3bd-114">詳細については、「 [Advanced eDiscovery でサポートされるファイルの種類](supported-filetypes-ediscovery20.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-114">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="9f3bd-115">レビューセットにアップロードされたすべてのファイルは、フォルダーに配置されている必要があります。各フォルダーは特定の保管担当者に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-115">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="9f3bd-116">これらのフォルダーの名前は、次の名前付け形式を使用する必要があります。 *alias@domainname*。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-116">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="9f3bd-117">Alias@domainname は、ユーザーの Microsoft 365 エイリアスおよびドメインである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-117">The alias@domainname must be the user's Microsoft 365 alias and domain.</span></span> <span data-ttu-id="9f3bd-118">ルートフォルダー内のすべての alias@domainname フォルダーを収集できます。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-118">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="9f3bd-119">ルートフォルダーには alias@domainname フォルダーのみ含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-119">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="9f3bd-120">ルートフォルダー内のルースファイルはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-120">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="9f3bd-121">アップロードする Microsoft 以外の365データのフォルダー構造は、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-121">The folder structure for the non-Microsoft 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="9f3bd-122">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9f3bd-122">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="9f3bd-123">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9f3bd-123">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="9f3bd-124">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9f3bd-124">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="9f3bd-125">この例では、abraham.mcmahon@contoso.com、jewell.gordon@contoso.com、および staci.gonzalez@contoso.com は、保管担当者の SMTP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-125">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Microsoft 以外の365データアップロードフォルダーの構造](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="9f3bd-127">電子情報開示マネージャーの役割グループに割り当てられているアカウント (および電子情報開示管理者として追加されたもの)。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-127">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="9f3bd-128">Microsoft 以外の365コンテンツフォルダー構造にアクセスできるコンピューターにインストールされている AzCopy v2.0 ツール。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-128">The AzCopy v8.1 tool installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span> <span data-ttu-id="9f3bd-129">AzCopy をインストールするには、「 [Windows で AzCopy](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)v2.0 を使用してデータを転送する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-129">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="9f3bd-130">AzCopy は、既定の場所である **% ProgramFiles (x86)% \ Microsoft SDKs\Azure\AzCopy**にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-130">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="9f3bd-131">AzCopy v1.1 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-131">You must use AzCopy v8.1.</span></span> <span data-ttu-id="9f3bd-132">その他のバージョンの AzCopy は、高度な電子情報開示で Microsoft 以外の365データを読み込む場合には機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-132">Other versions of AzCopy may not work when loading non-Microsoft 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a><span data-ttu-id="9f3bd-133">Microsoft 以外の365コンテンツを上級電子情報開示にアップロードする</span><span class="sxs-lookup"><span data-stu-id="9f3bd-133">Upload non-Microsoft 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="9f3bd-134">電子情報開示マネージャーまたは電子情報開示管理者として、Advanced eDiscovery を開いて、Microsoft 以外の365データがアップロードされるケースに進みます。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-134">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, and go to the case that the non-Microsoft 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="9f3bd-135">[**チェックセット**] をクリックし、[Microsoft 以外の365データをアップロードするためのレビューセット] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-135">Click **Review sets**, and then select the review set to upload the non-Microsoft 365 data to.</span></span>  <span data-ttu-id="9f3bd-136">レビューセットを持っていない場合は、作成できます。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-136">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="9f3bd-137">レビューセットで、[**レビューセットの管理**] をクリックし、 **Microsoft 以外の365データ**タイルで [アップロードの**表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-137">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Microsoft 365 data** tile.</span></span>

4. <span data-ttu-id="9f3bd-138">[**ファイルのアップロード**] をクリックして、データインポートウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-138">Click **Upload files** to start the data import wizard.</span></span>

   ![ファイルをアップロードする](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="9f3bd-140">ウィザードの最初の手順では、にファイルをアップロードするための、セキュリティ保護された Microsoft 提供の Azure ストレージの場所を準備します。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-140">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="9f3bd-141">準備が完了すると、 **[次へ: ファイルのアップロード**] ボタンがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-141">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Microsoft 以外の365インポート: Prepare](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="9f3bd-143">[**次へ: ファイルのアップロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-143">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="9f3bd-144">[**ファイルのアップロード**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-144">On the **Upload files** page, do the following:</span></span>

   ![Microsoft 以外の365インポート: ファイルのアップロード](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="9f3bd-146">a. </span><span class="sxs-lookup"><span data-stu-id="9f3bd-146">a.</span></span> <span data-ttu-id="9f3bd-147">[**ファイルの場所のパス**] ボックスに、アップロードする Microsoft 以外の365データを格納したルートフォルダーの場所を確認するか、または入力します。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-147">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Microsoft 365 data you want to upload.</span></span> <span data-ttu-id="9f3bd-148">たとえば、[**開始する前に] セクション**に表示されるサンプルファイルの場所については、「 **%USERPROFILE\Downloads\nonO365**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-148">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="9f3bd-149">正しい場所を指定すると、パスの下のボックスに表示される AzCopy コマンドが適切に更新されるようになります。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-149">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="9f3bd-150">b.</span><span class="sxs-lookup"><span data-stu-id="9f3bd-150">b.</span></span> <span data-ttu-id="9f3bd-151">[**クリップボードにコピー** ] をクリックして、ボックスに表示されているコマンドをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-151">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="9f3bd-152">Windows コマンドプロンプトを起動し、前の手順でコピーしたコマンドを貼り付け、 **enter**キーを押して、azcopy コマンドを開始します。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-152">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="9f3bd-153">コマンドを開始すると、Microsoft 以外の365ファイルは、手順4で準備した Azure ストレージの場所にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-153">After you start the command, the non-Microsoft 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Microsoft 以外の365インポート: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="9f3bd-155">前述したように、[**ファイルのアップロード**] ページで提供されているコマンドを正常に使用するには、azcopy v1.1 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-155">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="9f3bd-156">指定した AzCopy コマンドが失敗した場合は、「 [Advanced eDiscovery での AzCopy のトラブルシューティング](troubleshooting-azcopy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-156">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="9f3bd-157">セキュリティ & コンプライアンスセンターに戻り、[**次へ:** ウィザードでファイルを処理します] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="9f3bd-158">これにより、Azure ストレージの場所にアップロードされた Microsoft 以外の365ファイルの処理、テキスト抽出、およびインデックス作成が開始されます。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-158">This initiates processing, text extraction, and indexing of the non-Microsoft 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="9f3bd-159">「**プロセスファイル**」ページまたは「**ジョブ**」タブでファイルの処理の進行状況を追跡するには、「 **Microsoft 以外の365データをレビューセットに追加する**」という名前のジョブを表示します。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-159">Track the progress of processing the files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Microsoft 365 data to a review set**.</span></span>  <span data-ttu-id="9f3bd-160">ジョブが完了すると、新しいファイルがレビューセットで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![Microsoft 以外の365インポート: プロセスファイル](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="9f3bd-162">処理が終了したら、ウィザードを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="9f3bd-162">After the processing is finished, you can close the wizard.</span></span>
