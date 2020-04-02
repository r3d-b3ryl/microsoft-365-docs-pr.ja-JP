---
title: Office 以外の365データを証拠に読み込む
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
description: ''
ms.openlocfilehash: 7d2f4fe685e17690b76124517468e0eceec8b414
ms.sourcegitcommit: 825037f166eea3ba70f8980cedc5492f90c1cc56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2020
ms.locfileid: "43097220"
---
# <a name="load-non-office-365-data-into-evidence"></a><span data-ttu-id="4a986-102">Office 以外の365データを証拠に読み込む</span><span class="sxs-lookup"><span data-stu-id="4a986-102">Load non-Office 365 data into evidence</span></span>

<span data-ttu-id="4a986-103">データ調査で分析する必要があるすべてのドキュメントが Office 365 にあるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="4a986-103">Not all documents that you may need to analyze in a data investigation will be located in Office 365.</span></span> <span data-ttu-id="4a986-104">Office 365 以外のコンテンツインポート機能を使用すると、Office 365 に存在しないドキュメントを証拠にアップロードして、データの調査で分析することができます。</span><span class="sxs-lookup"><span data-stu-id="4a986-104">With the Non-Office 365 content import feature you can upload documents that don't live in Office 365 into evidence so they can be analyzed in a data investigation.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4a986-105">はじめに</span><span class="sxs-lookup"><span data-stu-id="4a986-105">Before you begin</span></span>

<span data-ttu-id="4a986-106">この手順の説明に従って Office 365 以外のアップロード機能を使用するには、次の条件を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a986-106">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="4a986-107">Microsoft 365 または Office 365 E5 サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="4a986-107">A Microsoft 365 or Office 365 E5 subscription.</span></span>

- <span data-ttu-id="4a986-108">Office 以外の365コンテンツをアップロードする対象となるユーザーには、適切な E5 または E5 アドオンライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="4a986-108">All people of interest whose non-Office 365 content will be uploaded must have the appropriate E5 or E5 add-on license.</span></span>

- <span data-ttu-id="4a986-109">既存の電子情報開示ケース。</span><span class="sxs-lookup"><span data-stu-id="4a986-109">An existing eDiscovery case.</span></span>

- <span data-ttu-id="4a986-110">収集されたすべてのファイルは、保管担当者ごとにフォルダーが1つ存在し、フォルダーの名前がこの形式*alias@domainname*であるフォルダーにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="4a986-110">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname*.</span></span> <span data-ttu-id="4a986-111">*Alias@domainname*は、ユーザーの Office 365 エイリアスおよびドメインである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a986-111">The *alias@domainname* must be users Office 365 alias and domain.</span></span> <span data-ttu-id="4a986-112">すべての*alias@domainname*フォルダーをルートフォルダーに収集できます。</span><span class="sxs-lookup"><span data-stu-id="4a986-112">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="4a986-113">ルートフォルダーに含めることができるのは*alias@domainname*フォルダーのみで、ルートフォルダーには圧縮されていないファイルは存在しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a986-113">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="4a986-114">Office 365 以外のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされている、電子情報開示マネージャーまたは電子情報開示管理者の Microsoft Azure Storage Tools のどちらかのアカウント。</span><span class="sxs-lookup"><span data-stu-id="4a986-114">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="4a986-115">AzCopy をインストールします。これは、ここから行うことができます。https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="4a986-115">Install AzCopy, which you can do from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-in-to-a-data-investigation"></a><span data-ttu-id="4a986-116">Office 365 以外のコンテンツをデータ調査にアップロードする</span><span class="sxs-lookup"><span data-stu-id="4a986-116">Upload non-Office 365 content in to a data investigation</span></span>

1. <span data-ttu-id="4a986-117">**データ調査**を開いて、Office ではない365データのアップロード先の調査に移動します。</span><span class="sxs-lookup"><span data-stu-id="4a986-117">Open **Data Investigations** and go to the investigation that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="4a986-118">[**証拠**] タブをクリックし、Office 以外の365データを読み込む証拠セットを選択します。</span><span class="sxs-lookup"><span data-stu-id="4a986-118">Click the **Evidence** tab, then select the evidence set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="4a986-119">証拠セットをまだ作成していない場合は、ここで作成できます。</span><span class="sxs-lookup"><span data-stu-id="4a986-119">If you have not already created an evidence set, you can do so now.</span></span>  <span data-ttu-id="4a986-120">最後に、[**証明の管理**] をクリックし、[Office 以外の365データ] セクションの [アップロードを**表示**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4a986-120">Finally, click **Manage evidence** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="4a986-121">[**ファイルのアップロード**] ボタンをクリックして、Office 365 以外のデータインポートウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="4a986-121">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![ファイルをアップロードする](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="4a986-123">ウィザードの最初の手順では、ファイルをアップロードするために、セキュリティで保護された Azure blob を準備するだけです。</span><span class="sxs-lookup"><span data-stu-id="4a986-123">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="4a986-124">準備が完了したら、[**次へ: ファイルのアップロード**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4a986-124">After the preparation is complete, click the **Next: Upload files** button.</span></span>

![Office 以外の365データインポートの準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="4a986-126">[**ファイルのアップロード**] ステップで、**ファイルの場所へのパス**を指定します。この場合、インポートする予定の非 Office 365 データが配置されます。</span><span class="sxs-lookup"><span data-stu-id="4a986-126">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="4a986-127">正しい場所を設定することにより、AzCopy コマンドが正しく更新されます。</span><span class="sxs-lookup"><span data-stu-id="4a986-127">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="4a986-128">AzCopy をまだインストールしていない場合は、ここから実行できます。https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="4a986-128">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="4a986-129">[**クリップボードにコピー** ] リンクをクリックして、定義済みのコマンドをコピーします。</span><span class="sxs-lookup"><span data-stu-id="4a986-129">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="4a986-130">Windows コマンドプロンプトを起動し、コマンドを貼り付けて、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4a986-130">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="4a986-131">ファイルは、次の手順のために secure Azure blob ストレージにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="4a986-131">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Office 以外の365データインポート用のファイルをアップロードする](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![非 Office 365 データをインポートするために AzCopy を使用する](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="4a986-134">最後に、[セキュリティ & コンプライアンスに戻し、[**次へ: ファイルの処理**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4a986-134">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="4a986-135">これにより、アップロードされたファイルの処理、テキストの抽出、およびインデックス作成が開始されます。</span><span class="sxs-lookup"><span data-stu-id="4a986-135">This initiates processing, text extraction, and indexing of the uploaded files.</span></span>  <span data-ttu-id="4a986-136">処理の進行状況を追跡するには、[**ジョブ**] タブを使用します。 完了すると、新しいファイルが証拠セットで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4a986-136">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files are available in the evidence set.</span></span>  <span data-ttu-id="4a986-137">処理が完了したら、ウィザードを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="4a986-137">After processing is complete, you can dismiss the wizard.</span></span>

![Office 以外の365インポート処理ファイル](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

