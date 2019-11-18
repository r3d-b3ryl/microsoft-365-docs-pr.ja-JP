---
title: Office 以外の365データを証拠に読み込む
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
ms.openlocfilehash: e05dc26159545e4daf7a8f4109268a1657fd62d6
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2019
ms.locfileid: "38686806"
---
# <a name="load-non-office-365-data-into-evidence"></a><span data-ttu-id="d43db-102">Office 以外の365データを証拠に読み込む</span><span class="sxs-lookup"><span data-stu-id="d43db-102">Load non-Office 365 data into evidence</span></span>

<span data-ttu-id="d43db-103">データ調査で分析する必要があるすべてのドキュメントが Office 365 にあるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d43db-103">Not all documents that you may need to analyze in a data investigation will be located in Office 365.</span></span> <span data-ttu-id="d43db-104">Office 365 以外のコンテンツインポート機能を使用すると、Office 365 に存在しないドキュメントを証拠にアップロードして、データの調査で分析することができます。</span><span class="sxs-lookup"><span data-stu-id="d43db-104">With the Non-Office 365 content import feature you can upload documents that don't live in Office 365 into evidence so they can be analyzed in a data investigation.</span></span>

>[!Note]
><span data-ttu-id="d43db-105">データの調査には、組織のための高度なコンプライアンスアドオンまたは E5 サブスクリプションと共に Office 365 E3 が必要です。</span><span class="sxs-lookup"><span data-stu-id="d43db-105">Data investigation requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="d43db-106">その計画がなく、高度な電子情報開示を試行する必要がある場合は、Office 365 Enterprise E5 の試用版にサインアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="d43db-106">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d43db-107">始める前に</span><span class="sxs-lookup"><span data-stu-id="d43db-107">Before you begin</span></span>

<span data-ttu-id="d43db-108">この手順の説明に従って Office 365 以外のアップロード機能を使用するには、次の条件を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d43db-108">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="d43db-109">高度なコンプライアンスアドオンまたは E5 サブスクリプションを備えた Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="d43db-109">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="d43db-110">Office 以外の365コンテンツをアップロードするすべての保管担当者には、高度なコンプライアンスアドオンまたは E5 ライセンスを含む E3 が必要です。</span><span class="sxs-lookup"><span data-stu-id="d43db-110">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="d43db-111">既存の電子情報開示ケース。</span><span class="sxs-lookup"><span data-stu-id="d43db-111">An existing eDiscovery case.</span></span>

- <span data-ttu-id="d43db-112">収集されたすべてのファイルは、保管担当者ごとにフォルダーが1つ存在し、フォルダーの名前がこの形式*alias@domainname*であるフォルダーにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="d43db-112">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname*.</span></span> <span data-ttu-id="d43db-113">*Alias@domainname*は、ユーザーの Office 365 エイリアスおよびドメインである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d43db-113">The *alias@domainname* must be users Office 365 alias and domain.</span></span> <span data-ttu-id="d43db-114">すべての*alias@domainname*フォルダーをルートフォルダーに収集できます。</span><span class="sxs-lookup"><span data-stu-id="d43db-114">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="d43db-115">ルートフォルダーに含めることができるのは*alias@domainname*フォルダーのみで、ルートフォルダーには圧縮されていないファイルは存在しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="d43db-115">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="d43db-116">Office 365 以外のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされている、電子情報開示マネージャーまたは電子情報開示管理者の Microsoft Azure Storage Tools のどちらかのアカウント。</span><span class="sxs-lookup"><span data-stu-id="d43db-116">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="d43db-117">AzCopy をインストールします。これは、ここから行うことができます。https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="d43db-117">Install AzCopy, which you can do from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-in-to-a-data-investigation"></a><span data-ttu-id="d43db-118">Office 365 以外のコンテンツをデータ調査にアップロードする</span><span class="sxs-lookup"><span data-stu-id="d43db-118">Upload non-Office 365 content in to a data investigation</span></span>

1. <span data-ttu-id="d43db-119">Open \* \* \* \* データ調査 \* \*、Office 以外の365データがアップロードされることを調査します。</span><span class="sxs-lookup"><span data-stu-id="d43db-119">Open \*\*\*\*Data Investigations\*\*, then the investigation that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="d43db-120">[**証拠**] タブをクリックし、Office 以外の365データを読み込む証拠セットを選択します。</span><span class="sxs-lookup"><span data-stu-id="d43db-120">Click the **Evidence** tab, then select the evidence set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="d43db-121">証拠セットをまだ作成していない場合は、ここで作成できます。</span><span class="sxs-lookup"><span data-stu-id="d43db-121">If you have not already created an evidence set, you can do so now.</span></span>  <span data-ttu-id="d43db-122">最後に、[**証明の管理**] をクリックし、[Office 以外の365データ] セクションの [アップロードを**表示**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d43db-122">Finally, click **Manage evidence** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="d43db-123">[**ファイルのアップロード**] ボタンをクリックして、Office 365 以外のデータインポートウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="d43db-123">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![ファイルをアップロードする](media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="d43db-125">ウィザードの最初の手順では、ファイルをアップロードするために、セキュリティで保護された Azure blob を準備するだけです。</span><span class="sxs-lookup"><span data-stu-id="d43db-125">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="d43db-126">準備が完了したら、[**次へ: ファイルのアップロード**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d43db-126">After the preparation is complete, click the **Next: Upload files** button.</span></span>

![Office 以外の365データインポートの準備](media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="d43db-128">[**ファイルのアップロード**] ステップで、**ファイルの場所へのパス**を指定します。この場合、インポートする予定の非 Office 365 データが配置されます。</span><span class="sxs-lookup"><span data-stu-id="d43db-128">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="d43db-129">正しい場所を設定することにより、AzCopy コマンドが正しく更新されます。</span><span class="sxs-lookup"><span data-stu-id="d43db-129">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="d43db-130">AzCopy をまだインストールしていない場合は、ここから実行できます。https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="d43db-130">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="d43db-131">[**クリップボードにコピー** ] リンクをクリックして、定義済みのコマンドをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d43db-131">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="d43db-132">Windows コマンドプロンプトを起動し、コマンドを貼り付けて、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d43db-132">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="d43db-133">ファイルは、次の手順のために secure Azure blob ストレージにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="d43db-133">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Office 以外の365データインポート用のファイルをアップロードする](media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![非 Office 365 データをインポートするために AzCopy を使用する](media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="d43db-136">最後に、[セキュリティ & コンプライアンスに戻し、[**次へ: ファイルの処理**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d43db-136">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="d43db-137">これにより、アップロードされたファイルの処理、テキストの抽出、およびインデックス作成が開始されます。</span><span class="sxs-lookup"><span data-stu-id="d43db-137">This initiates processing, text extraction, and indexing of the uploaded files.</span></span>  <span data-ttu-id="d43db-138">処理の進行状況を追跡するには、[**ジョブ**] タブを使用します。 完了すると、新しいファイルが証拠セットで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d43db-138">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files are available in the evidence set.</span></span>  <span data-ttu-id="d43db-139">処理が完了したら、ウィザードを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="d43db-139">After processing is complete, you can dismiss the wizard.</span></span>

![Office 以外の365インポート処理ファイル](media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

