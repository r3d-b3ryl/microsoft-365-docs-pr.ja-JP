---
title: 単一アイテムのエラーの修復
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
description: 一括エラー修復プロセスに従わずに、Advanced eDiscovery内のドキュメントの処理エラーを修正できます。
ms.openlocfilehash: 8e5d8d00f507dc5792a1beda018d4c76632b82f7
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751584"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a><span data-ttu-id="9a223-103">単一アイテムのエラー修復 (Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="9a223-103">Single item error remediation in Advanced eDiscovery</span></span>

<span data-ttu-id="9a223-104">エラー修復により、Advanced eDiscoveryユーザーは、ユーザーがコンテンツを適切に処理Advanced eDiscoveryデータの問題を修正できます。</span><span class="sxs-lookup"><span data-stu-id="9a223-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="9a223-105">たとえば、パスワードで保護されたファイルは、ロックまたは暗号化されたファイルなので処理できません。</span><span class="sxs-lookup"><span data-stu-id="9a223-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="9a223-106">以前は、このワークフローを使用してエラーを一括で [修復するのみ可能でした](error-remediation-when-processing-data-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="9a223-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="9a223-107">ただし、調査中のケースに対応するファイルが存在しない場合は、複数のファイルのエラーを修復しても意味がない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9a223-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="9a223-108">また、ファイルのメタデータ (ファイルの場所やアクセス権を持ったユーザーなど) を確認して、応答性に関する意思決定を行う前に、エラーを修復する場合は意味がない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9a223-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="9a223-109">単一アイテム エラー修復と呼ばれる新しい機能により、電子情報開示管理者は、処理エラーを含むファイルのメタデータを表示し、必要に応じてレビュー セットでエラーを直接修復できます。</span><span class="sxs-lookup"><span data-stu-id="9a223-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="9a223-110">この記事では、レビュー セットの処理エラーを含むファイルを識別、無視、修復する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a223-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="9a223-111">エラーのあるドキュメントを特定する</span><span class="sxs-lookup"><span data-stu-id="9a223-111">Identify documents with errors</span></span>

<span data-ttu-id="9a223-112">レビュー セット内の処理エラーのあるドキュメントが識別されます (バナー付き)。</span><span class="sxs-lookup"><span data-stu-id="9a223-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="9a223-113">エラーを修復または無視できます。</span><span class="sxs-lookup"><span data-stu-id="9a223-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="9a223-114">次のスクリーンショットは、パスワードで保護されたレビュー セット内の Word 文書の処理エラー バナーを示しています。</span><span class="sxs-lookup"><span data-stu-id="9a223-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="9a223-115">また、処理エラーが発生したドキュメントのファイル メタデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9a223-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![処理エラーが発生したドキュメントに対して表示されるバナー](../media/SIERimage1.png)

<span data-ttu-id="9a223-117">また、レビュー セット内のドキュメントにクエリを実行するときに処理状態条件を使用して、処理エラーが発生したドキュメント[を検索することもできます](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="9a223-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![エラー ドキュメントを検索するには、処理状態条件を使用します。](../media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="9a223-119">エラーを無視する</span><span class="sxs-lookup"><span data-stu-id="9a223-119">Ignore errors</span></span>

<span data-ttu-id="9a223-120">処理エラー バナーの [無視] **をクリックすると** 、処理エラーを無視できます。</span><span class="sxs-lookup"><span data-stu-id="9a223-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="9a223-121">エラーを無視すると、ドキュメントは一括エラー修復ワークフロー [から削除されます](error-remediation-when-processing-data-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="9a223-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="9a223-122">エラーが無視された後、ドキュメント バナーは色を変更し、処理エラーが無視されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9a223-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="9a223-123">[元に戻す] をクリックすると、エラーを無視する決定をいつでも元に **戻します**。</span><span class="sxs-lookup"><span data-stu-id="9a223-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![[無視] をクリックして処理エラーを無視します。](../media/SIERimage3.png)

<span data-ttu-id="9a223-125">また、レビュー セット内のドキュメントを照会するときに無視処理エラー条件を使用して、無視された処理エラーが発生したすべてのドキュメントを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="9a223-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![無視されたエラー ドキュメントを検索するには、無視処理エラー条件を使用します。](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="9a223-127">エラーのあるドキュメントを修復する</span><span class="sxs-lookup"><span data-stu-id="9a223-127">Remediate a document with errors</span></span>

<span data-ttu-id="9a223-128">場合によっては、ドキュメントの処理エラー (パスワードの削除、暗号化されたファイルの暗号化解除、破損したドキュメントの回復) を修復し、修復されたドキュメントをレビュー セットに追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9a223-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="9a223-129">これにより、エラー ドキュメントをレビュー セット内の他のドキュメントと共に確認およびエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="9a223-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="9a223-130">1 つのドキュメントを修復するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9a223-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="9a223-131">[**元の**  >  **ダウンロード] を** クリックして、ファイルのコピーをローカル コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9a223-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![処理エラーが発生したドキュメントをダウンロードする](../media/SIERimage5.png)

2. <span data-ttu-id="9a223-133">ファイルのエラーをオフラインで修復します。</span><span class="sxs-lookup"><span data-stu-id="9a223-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="9a223-134">暗号化されたファイルの場合、暗号化解除ソフトウェアが必要な場合、パスワード保護を削除するには、パスワードを指定してファイルを保存するか、パスワードクラッカーを使用します。</span><span class="sxs-lookup"><span data-stu-id="9a223-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="9a223-135">ファイルを修復した後、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="9a223-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="9a223-136">レビュー セットで、修復した処理エラーが発生したファイルを選択し、[修復] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9a223-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![処理エラーが発生したドキュメントのバナーで [修復] をクリックします。](../media/SIERimage6.png)


4. <span data-ttu-id="9a223-138">[ **参照]** をクリックし、ローカル コンピューター上の修復されたファイルの場所に移動し、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="9a223-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![[参照] をクリックし、ローカル コンピューターで修復されたファイルを選択します。](../media/SIERimage7.png)

    <span data-ttu-id="9a223-140">修復されたファイルを選択すると、レビュー セットに自動的にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="9a223-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="9a223-141">ファイルの処理状態を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="9a223-141">You can track the processing status of the file.</span></span>

    ![修復プロセスの状態が表示されます](../media/SIERimage8.png)

   <span data-ttu-id="9a223-143">処理が完了したら、修復されたドキュメントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9a223-143">After processing is completed, you can view the remediated document.</span></span>

    ![修復されたファイルは、レビュー セットのネイティブ形式で表示できます。](../media/SIERimage9.png)

<span data-ttu-id="9a223-145">ドキュメントが修復された場合の対応の詳細については、「ファイルが修復された場合の対応 [」を参照してください](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated)。</span><span class="sxs-lookup"><span data-stu-id="9a223-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="9a223-146">修復されたドキュメントを検索する</span><span class="sxs-lookup"><span data-stu-id="9a223-146">Search for remediated documents</span></span>

<span data-ttu-id="9a223-147">Keywords 条件を使用し、次のプロパティ:値のペアを指定することで、修復されたレビュー セット内のすべてのドキュメントを検索できます **。IsFromErrorRemediation:true** を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a223-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="9a223-148">このプロパティは、レビュー セットからドキュメントをエクスポートするときに、エクスポート読み込みファイルでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="9a223-148">This property is also available in the export load file when you export documents from a review set.</span></span>
