---
title: Microsoft 以外の365データを証拠に読み込む
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
ms.openlocfilehash: 9eef3b38ceef7efc42e1f66c45069f51a0a95d45
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632632"
---
# <a name="load-non-microsoft-365-data-into-evidence"></a><span data-ttu-id="ad56a-102">Microsoft 以外の365データを証拠に読み込む</span><span class="sxs-lookup"><span data-stu-id="ad56a-102">Load non-Microsoft 365 data into evidence</span></span>

<span data-ttu-id="ad56a-103">データ調査で分析する必要があるすべてのドキュメントが Microsoft 365 にあるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="ad56a-103">Not all documents that you may need to analyze in a data investigation will be located in Microsoft 365.</span></span> <span data-ttu-id="ad56a-104">Microsoft 以外の365コンテンツインポート機能を使用すると、Microsoft 365 に存在しないドキュメントをデータ調査で分析できるように、証拠としてアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad56a-104">With the Non-Microsoft 365 content import feature you can upload documents that don't live in Microsoft 365 into evidence so they can be analyzed in a data investigation.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ad56a-105">始める前に</span><span class="sxs-lookup"><span data-stu-id="ad56a-105">Before you begin</span></span>

<span data-ttu-id="ad56a-106">この手順の説明に従って Microsoft 以外の365機能をアップロードするには、次の条件を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad56a-106">Using the upload Non-Microsoft 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="ad56a-107">Microsoft 365 または Office 365 E5 サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="ad56a-107">A Microsoft 365 or Office 365 E5 subscription.</span></span>

- <span data-ttu-id="ad56a-108">Microsoft 以外の365のコンテンツをアップロードする対象となるすべてのユーザーには、適切な E5 または E5 アドオンライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ad56a-108">All people of interest whose non-Microsoft 365 content will be uploaded must have the appropriate E5 or E5 add-on license.</span></span>

- <span data-ttu-id="ad56a-109">既存の電子情報開示ケース。</span><span class="sxs-lookup"><span data-stu-id="ad56a-109">An existing eDiscovery case.</span></span>

- <span data-ttu-id="ad56a-110">収集されたすべてのファイルは、保管担当者ごとにフォルダーが1つ存在し、フォルダーの名前がこの形式*alias@domainname*であるフォルダーにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="ad56a-110">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname*.</span></span> <span data-ttu-id="ad56a-111">*Alias@domainname*は、ユーザーのエイリアスおよびドメインである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad56a-111">The *alias@domainname* must be user's alias and domain.</span></span> <span data-ttu-id="ad56a-112">すべての*alias@domainname*フォルダーをルートフォルダーに収集できます。</span><span class="sxs-lookup"><span data-stu-id="ad56a-112">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="ad56a-113">ルートフォルダーに含めることができるのは*alias@domainname*フォルダーのみで、ルートフォルダーには圧縮されていないファイルは存在しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad56a-113">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="ad56a-114">電子情報開示の管理者または電子情報開示管理者のいずれかであるアカウントで、Microsoft 以外の365のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされている。</span><span class="sxs-lookup"><span data-stu-id="ad56a-114">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span>

- <span data-ttu-id="ad56a-115">AzCopy をインストールします。これは、ここから行うことができます。https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="ad56a-115">Install AzCopy, which you can do from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-microsoft-365-content-in-to-a-data-investigation"></a><span data-ttu-id="ad56a-116">Microsoft 以外の365コンテンツをデータ調査にアップロードする</span><span class="sxs-lookup"><span data-stu-id="ad56a-116">Upload non-Microsoft 365 content in to a data investigation</span></span>

1. <span data-ttu-id="ad56a-117">**データ調査**を開いて、Microsoft 以外の365データがアップロードされることを調査します。</span><span class="sxs-lookup"><span data-stu-id="ad56a-117">Open **Data Investigations** and go to the investigation that the non-Microsoft 365 data will be uploaded to.</span></span>  <span data-ttu-id="ad56a-118">[**エビデンス**] タブをクリックし、データを読み込む証拠セットを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad56a-118">Click the **Evidence** tab, then select the evidence set you wish to load the data to.</span></span>  <span data-ttu-id="ad56a-119">証拠セットをまだ作成していない場合は、ここで作成できます。</span><span class="sxs-lookup"><span data-stu-id="ad56a-119">If you have not already created an evidence set, you can do so now.</span></span>  <span data-ttu-id="ad56a-120">最後に、[**証明の管理**] をクリックし、[データ] セクションで [アップロード] を**表示**します。</span><span class="sxs-lookup"><span data-stu-id="ad56a-120">Finally, click **Manage evidence** then **View uploads** in the data section</span></span>

2. <span data-ttu-id="ad56a-121">[**ファイルのアップロード**] ボタンをクリックして、Microsoft 以外の365データインポートウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="ad56a-121">Click the **Upload files** button to start the Non-Microsoft 365 data import wizard.</span></span>

![ファイルをアップロードする](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="ad56a-123">ウィザードの最初の手順では、ファイルをアップロードするために、セキュリティで保護された Azure blob を準備するだけです。</span><span class="sxs-lookup"><span data-stu-id="ad56a-123">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="ad56a-124">準備が完了したら、[**次へ: ファイルのアップロード**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad56a-124">After the preparation is complete, click the **Next: Upload files** button.</span></span>

![Microsoft 以外の365データインポートの準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="ad56a-126">[**ファイルのアップロード**] ステップで、**ファイルの場所へのパス**を指定します。この場合、インポートする予定の Microsoft 以外の365データが配置されます。</span><span class="sxs-lookup"><span data-stu-id="ad56a-126">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Microsoft 365 data you plan on importing is located.</span></span>  <span data-ttu-id="ad56a-127">正しい場所を設定することにより、AzCopy コマンドが正しく更新されます。</span><span class="sxs-lookup"><span data-stu-id="ad56a-127">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="ad56a-128">AzCopy をまだインストールしていない場合は、ここから実行できます。https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="ad56a-128">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="ad56a-129">[**クリップボードにコピー** ] リンクをクリックして、定義済みのコマンドをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ad56a-129">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="ad56a-130">Windows コマンドプロンプトを起動し、コマンドを貼り付けて、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ad56a-130">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="ad56a-131">ファイルは、次の手順のために secure Azure blob ストレージにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="ad56a-131">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Microsoft 以外の365データインポート用のファイルをアップロードする](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![AzCopy を使用して Microsoft 以外の365データをインポートする](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="ad56a-134">最後に、[セキュリティ & コンプライアンスに戻し、[**次へ: ファイルの処理**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad56a-134">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="ad56a-135">これにより、アップロードされたファイルの処理、テキストの抽出、およびインデックス作成が開始されます。</span><span class="sxs-lookup"><span data-stu-id="ad56a-135">This initiates processing, text extraction, and indexing of the uploaded files.</span></span>  <span data-ttu-id="ad56a-136">処理の進行状況を追跡するには、[**ジョブ**] タブを使用します。 完了すると、新しいファイルが証拠セットで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ad56a-136">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files are available in the evidence set.</span></span>  <span data-ttu-id="ad56a-137">処理が完了したら、ウィザードを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="ad56a-137">After processing is complete, you can dismiss the wizard.</span></span>

![Microsoft 以外の365インポートプロセスファイル](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

