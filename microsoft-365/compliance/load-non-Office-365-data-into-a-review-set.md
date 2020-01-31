---
title: レビュー セットに Office 365 以外のデータを読み込む
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
description: 高度な電子情報開示ケースのレビューセットに Office 365 以外のデータをインポートします。
ms.openlocfilehash: d839457824420c32a7acd006ae4218008c11b25e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41585686"
---
# <a name="load-non-office-365-data-into-a-review-set"></a><span data-ttu-id="76106-103">レビュー セットに Office 365 以外のデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="76106-103">Load non-Office 365 data into a review set</span></span>

<span data-ttu-id="76106-104">上級電子情報開示で分析する必要があるすべてのドキュメントが Office 365 にあるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="76106-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Office 365.</span></span> <span data-ttu-id="76106-105">Advanced eDiscovery で Office 365 以外のデータインポート機能を使用すると、Office 365 にないドキュメントをレビューセットにアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="76106-105">With the non-Office 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Office 365 to a review set.</span></span> <span data-ttu-id="76106-106">この記事では、非 Office 365 ドキュメントを分析のために上級電子情報開示に移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="76106-106">This article shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="76106-107">高度な電子情報開示では、組織の Microsoft 365 または Office 365 E5 サブスクリプション、および Advanced コンプライアンスアドオンサブスクリプションを備えた E3 サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="76106-107">Advanced eDiscovery requires an Microsoft 365 or Office 365 E5 subscription for your organization or an E3 subscription with the Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="76106-108">その計画がなく、高度な電子情報開示を試行する必要がある場合は、Office 365 Enterprise E5 の試用版にサインアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="76106-108">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="76106-109">始める前に</span><span class="sxs-lookup"><span data-stu-id="76106-109">Before you begin</span></span>

<span data-ttu-id="76106-110">この記事に記載されている「Office 以外の365をアップロードする」機能を使用するには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="76106-110">Using the upload non-Office 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="76106-111">Office に対応していない365コンテンツに関連付ける必要があるすべての保管担当者には、E5 ライセンスが割り当てられているか、または Advanced コンプライアンスアドオンライセンスを備えた E3 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="76106-111">All custodians that you want to associate non-Office 365 content to must be assigned an E5 license, or an E3 license with an Advanced Compliance add-on license.</span></span>

- <span data-ttu-id="76106-112">既存の高度な電子情報開示ケース。</span><span class="sxs-lookup"><span data-stu-id="76106-112">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="76106-113">Office 以外の365データをアップロードして関連付けるには、保管担当者をケースに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76106-113">Custodians must be added to the case before you can upload and associate the non-Office 365 data to them.</span></span>

- <span data-ttu-id="76106-114">Office 以外の365データは、Advanced eDiscovery でサポートされているファイルの種類である必要があります。</span><span class="sxs-lookup"><span data-stu-id="76106-114">Non-Office 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="76106-115">詳細については、「 [Advanced eDiscovery でサポートされるファイルの種類](supported-filetypes-ediscovery20.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76106-115">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="76106-116">レビューセットにアップロードされたすべてのファイルは、フォルダーに配置されている必要があります。各フォルダーは特定の保管担当者に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="76106-116">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="76106-117">これらのフォルダーの名前は、次の名前付け形式を使用する必要があります。 *alias@domainname*。</span><span class="sxs-lookup"><span data-stu-id="76106-117">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="76106-118">Alias@domainname は、ユーザーの Office 365 エイリアスおよびドメインである必要があります。</span><span class="sxs-lookup"><span data-stu-id="76106-118">The alias@domainname must be the user's Office 365 alias and domain.</span></span> <span data-ttu-id="76106-119">ルートフォルダー内のすべての alias@domainname フォルダーを収集できます。</span><span class="sxs-lookup"><span data-stu-id="76106-119">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="76106-120">ルートフォルダーには alias@domainname フォルダーのみ含めることができます。</span><span class="sxs-lookup"><span data-stu-id="76106-120">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="76106-121">ルートフォルダー内のルースファイルはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="76106-121">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="76106-122">アップロードする Office 365 以外のデータのフォルダー構造は、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="76106-122">The folder structure for the non-Office 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="76106-123">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="76106-123">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="76106-124">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="76106-124">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="76106-125">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="76106-125">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="76106-126">この例では、abraham.mcmahon@contoso.com、jewell.gordon@contoso.com、および staci.gonzalez@contoso.com は、保管担当者の SMTP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="76106-126">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Office 以外の365データアップロードフォルダーの構造](media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="76106-128">電子情報開示マネージャーの役割グループに割り当てられているアカウント (および電子情報開示管理者として追加されたもの)。</span><span class="sxs-lookup"><span data-stu-id="76106-128">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="76106-129">Office 365 以外のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされている AzCopy v2.0 ツール。</span><span class="sxs-lookup"><span data-stu-id="76106-129">The AzCopy v8.1 tool installed on a computer that has access to the non-Office 365 content folder structure.</span></span> <span data-ttu-id="76106-130">AzCopy をインストールするには、「 [Windows で AzCopy](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)v2.0 を使用してデータを転送する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76106-130">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="76106-131">AzCopy は、既定の場所である **% ProgramFiles (x86)% \ Microsoft SDKs\Azure\AzCopy**にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="76106-131">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="76106-132">AzCopy v1.1 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76106-132">You must use AzCopy v8.1.</span></span> <span data-ttu-id="76106-133">その他のバージョンの AzCopy は、高度な電子情報開示で Office 以外の365データを読み込む場合には機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="76106-133">Other versions of AzCopy may not work when loading non-Office 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="76106-134">Office 以外の365コンテンツを上級電子情報開示にアップロードする</span><span class="sxs-lookup"><span data-stu-id="76106-134">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="76106-135">電子情報開示マネージャーまたは電子情報開示管理者として、Advanced eDiscovery を開き、Office 以外の365データのアップロード先となるケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="76106-135">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="76106-136">[**チェックセット**] をクリックし、[Office 以外の365データをアップロードするレビューセット] を選択します。</span><span class="sxs-lookup"><span data-stu-id="76106-136">Click **Review sets**, and then select the review set to upload the non-Office 365 data to.</span></span>  <span data-ttu-id="76106-137">レビューセットを持っていない場合は、作成できます。</span><span class="sxs-lookup"><span data-stu-id="76106-137">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="76106-138">レビューセットで、[**レビューセットの管理**] をクリックし、[ **Office 以外の365データ**タイルの [**アップロードの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76106-138">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Office 365 data** tile.</span></span>

4. <span data-ttu-id="76106-139">[**ファイルのアップロード**] をクリックして、Office 365 以外のデータインポートウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="76106-139">Click **Upload files** to start the Non-Office 365 data import wizard.</span></span>

   ![ファイルをアップロードする](media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="76106-141">ウィザードの最初の手順では、にファイルをアップロードするための、セキュリティ保護された Microsoft 提供の Azure ストレージの場所を準備します。</span><span class="sxs-lookup"><span data-stu-id="76106-141">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="76106-142">準備が完了すると、 **[次へ: ファイルのアップロード**] ボタンがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="76106-142">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Office 以外の365のインポート: 準備](media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="76106-144">[**次へ: ファイルのアップロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76106-144">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="76106-145">[**ファイルのアップロード**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="76106-145">On the **Upload files** page, do the following:</span></span>

   ![Office 以外の365インポート: ファイルのアップロード](media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="76106-147">a. </span><span class="sxs-lookup"><span data-stu-id="76106-147">a.</span></span> <span data-ttu-id="76106-148">[**ファイルの場所のパス**] ボックスで、アップロードする Office 365 以外のデータを格納したルートフォルダーの場所を確認するか、または入力します。</span><span class="sxs-lookup"><span data-stu-id="76106-148">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Office 365 data you want to upload.</span></span> <span data-ttu-id="76106-149">たとえば、[**開始する前に] セクション**に表示されるサンプルファイルの場所については、「 **%USERPROFILE\Downloads\nonO365**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="76106-149">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="76106-150">正しい場所を指定すると、パスの下のボックスに表示される AzCopy コマンドが適切に更新されるようになります。</span><span class="sxs-lookup"><span data-stu-id="76106-150">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="76106-151">b. </span><span class="sxs-lookup"><span data-stu-id="76106-151">b.</span></span> <span data-ttu-id="76106-152">[**クリップボードにコピー** ] をクリックして、ボックスに表示されているコマンドをコピーします。</span><span class="sxs-lookup"><span data-stu-id="76106-152">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="76106-153">Windows コマンドプロンプトを起動し、前の手順でコピーしたコマンドを貼り付け、 **enter**キーを押して、azcopy コマンドを開始します。</span><span class="sxs-lookup"><span data-stu-id="76106-153">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="76106-154">コマンドを開始すると、Office 以外の365ファイルは、手順4で準備した Azure ストレージの場所にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="76106-154">After you start the command, the non-Office 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Office 以外の365インポート: AzCopy](media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="76106-156">前述したように、[**ファイルのアップロード**] ページで提供されているコマンドを正常に使用するには、azcopy v1.1 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76106-156">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="76106-157">指定した AzCopy コマンドが失敗した場合は、「 [Advanced eDiscovery での AzCopy のトラブルシューティング](troubleshooting-azcopy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76106-157">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="76106-158">セキュリティ & コンプライアンスセンターに戻り、[**次へ:** ウィザードでファイルを処理します] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76106-158">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="76106-159">これにより、Azure ストレージの場所にアップロードされた非 Office 365 ファイルの処理、テキスト抽出、およびインデックス作成が開始されます。</span><span class="sxs-lookup"><span data-stu-id="76106-159">This initiates processing, text extraction, and indexing of the non-Office 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="76106-160">Office ではない365ファイルの処理の進行状況を追跡するには、[**処理ファイル**] ページまたは [**ジョブ**] タブで、[ **office 以外の365データをレビューセットに追加する**] というジョブを表示します。</span><span class="sxs-lookup"><span data-stu-id="76106-160">Track the progress of processing the non-Office 365 files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Office 365 data to a review set**.</span></span>  <span data-ttu-id="76106-161">ジョブが完了すると、新しいファイルがレビューセットで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="76106-161">After the job is finished, the new files will be available in the review set.</span></span>

   ![Office 以外の365インポート: 処理ファイル](media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="76106-163">処理が終了したら、ウィザードを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="76106-163">After the processing is finished, you can close the wizard.</span></span>