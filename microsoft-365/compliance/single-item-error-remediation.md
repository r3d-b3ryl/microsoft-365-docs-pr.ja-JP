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
description: 詳細な電子情報開示では、一括エラー修復プロセスに従わずに、ドキュメントの処理エラーを修正することができます。
ms.openlocfilehash: c049ce4b5d3f8fc12a015a61ea927b744ae76eb3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601494"
---
# <a name="single-item-error-remediation"></a><span data-ttu-id="d1471-103">単一アイテムのエラーの修復</span><span class="sxs-lookup"><span data-stu-id="d1471-103">Single item error remediation</span></span>

<span data-ttu-id="d1471-104">エラー修復は、高度な電子情報開示ユーザーが、コンテンツを適切に処理できないようなデータの問題を修正する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="d1471-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="d1471-105">たとえば、パスワードで保護されたファイルは、ロックまたは暗号化されているため、処理できません。</span><span class="sxs-lookup"><span data-stu-id="d1471-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="d1471-106">以前は、[このワークフロー](error-remediation-when-processing-data-in-advanced-ediscovery.md)を使用して、エラーを一括で修復することはできませんでした。</span><span class="sxs-lookup"><span data-stu-id="d1471-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="d1471-107">しかし、調査しているケースに対応するファイルがあるかどうかがわからない場合は、複数のファイルのエラーを修復しても意味がありません。</span><span class="sxs-lookup"><span data-stu-id="d1471-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="d1471-108">また、ファイルのメタデータ (ファイルの場所やアクセス権を持っているなど) を確認してから、応答性についての事前の決定に役立てることができないという意味があります。</span><span class="sxs-lookup"><span data-stu-id="d1471-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="d1471-109">*単一アイテムエラー修復*という新しい機能により、電子情報開示管理者は処理エラーが発生したファイルのメタデータを表示でき、必要に応じてレビューセット内のエラーを直接修復できます。</span><span class="sxs-lookup"><span data-stu-id="d1471-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="d1471-110">この記事では、レビューセットの処理エラーが発生したファイルを特定、無視、および修復する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1471-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="d1471-111">エラーが発生したドキュメントを特定する</span><span class="sxs-lookup"><span data-stu-id="d1471-111">Identify documents with errors</span></span>

<span data-ttu-id="d1471-112">レビューセット内の処理エラーがあるドキュメントは、(バナー付きで) 識別されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d1471-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="d1471-113">エラーを修復または無視できます。</span><span class="sxs-lookup"><span data-stu-id="d1471-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="d1471-114">次のスクリーンショットは、パスワードで保護された校閲セット内の Word 文書の処理エラーバナーを示しています。</span><span class="sxs-lookup"><span data-stu-id="d1471-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="d1471-115">また、処理エラーが発生したドキュメントのファイルメタデータを表示できることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="d1471-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![処理エラーが発生したドキュメントに対して表示されるバナー](media/SIERimage1.png)

<span data-ttu-id="d1471-117">[レビューセット内のドキュメント](review-set-search.md)に対してクエリを実行するときに、**処理状態**の条件を使用して、処理エラーが発生しているドキュメントを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="d1471-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![処理状態の条件を使用してエラードキュメントを検索する](media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="d1471-119">エラーを無視する</span><span class="sxs-lookup"><span data-stu-id="d1471-119">Ignore errors</span></span>

<span data-ttu-id="d1471-120">処理エラーを無視するには、処理エラーバナーで [**無視**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1471-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="d1471-121">エラーを無視すると、そのドキュメントが[一括エラー修復ワークフロー](error-remediation-when-processing-data-in-advanced-ediscovery.md)から削除されます。</span><span class="sxs-lookup"><span data-stu-id="d1471-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="d1471-122">エラーが無視されると、ドキュメントバナーの色が変わり、処理エラーが無視されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="d1471-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="d1471-123">エラーを無視するかどうかは、[**元に戻す**] をクリックすることによって、いつでも取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="d1471-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![[無視] をクリックして処理エラーを無視する](media/SIERimage3.png)

<span data-ttu-id="d1471-125">レビューセット内のドキュメントに対してクエリを実行するときに無視される*処理*エラーの条件を使用して、無視されたすべてのドキュメントを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="d1471-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![無視されたエラードキュメントを検索するために無視する処理エラーの条件を使用する](media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="d1471-127">エラーが発生したドキュメントを修復する</span><span class="sxs-lookup"><span data-stu-id="d1471-127">Remediate a document with errors</span></span>

<span data-ttu-id="d1471-128">場合によっては、ドキュメントの処理エラーを修復する必要があります (パスワードを削除する、暗号化されたファイルを解読する、破損したドキュメントを回復するなど)。その後、修復したドキュメントをレビューセットに追加します。</span><span class="sxs-lookup"><span data-stu-id="d1471-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="d1471-129">これにより、エラー文書をレビューセット内の他のドキュメントと一緒に確認してエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="d1471-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="d1471-130">1つのドキュメントを修復するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1471-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="d1471-131">[オリジナル**のダウンロード]** をクリックして、ファイルのコピーをローカルコンピューターにダウンロードします。\*\*\*\*  > </span><span class="sxs-lookup"><span data-stu-id="d1471-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![処理エラーが発生したドキュメントをダウンロードする](media/SIERimage5.png)

2. <span data-ttu-id="d1471-133">ファイルのオフラインでエラーを修復します。</span><span class="sxs-lookup"><span data-stu-id="d1471-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="d1471-134">暗号化されたファイルについては、暗号化解除ソフトウェアを必要とするため、パスワード保護を解除するには、パスワードを指定してファイルを保存するか、パスワードのクラッカーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1471-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="d1471-135">ファイルを修復した後、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="d1471-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="d1471-136">レビューセットで、修復した処理エラーが発生したファイルを選択し、[**修復**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1471-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![処理エラーが発生したドキュメントのバナーで [修復] をクリックします。](media/SIERimage6.png)


4. <span data-ttu-id="d1471-138">[**参照**] をクリックし、ローカルコンピューター上の修復されたファイルの場所に移動して、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1471-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![[参照] をクリックし、ローカルコンピューター上で修復されたファイルを選択します。](media/SIERimage7.png)

    <span data-ttu-id="d1471-140">修復したファイルを選択すると、自動的にレビューセットにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="d1471-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="d1471-141">ファイルの処理状況を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="d1471-141">You can track the processing status of the file.</span></span>

    ![修復プロセスの状態が表示されます。](media/SIERimage8.png)

   <span data-ttu-id="d1471-143">処理が完了すると、修復されたドキュメントを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d1471-143">After processing is completed, you can view the remediated document.</span></span>

    ![修復されたファイルは、レビューセットのネイティブ形式で表示できます。](media/SIERimage9.png)

<span data-ttu-id="d1471-145">ドキュメントが修復されたときの処理の詳細については、「[ファイルが修復されたとき](error-remediation.md#what-happens-when-files-are-remediated)の処理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1471-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="d1471-146">修復済みドキュメントを検索する</span><span class="sxs-lookup"><span data-stu-id="d1471-146">Search for remediated documents</span></span>

<span data-ttu-id="d1471-147">修復された校閲セット内のすべてのドキュメントを検索するには、**キーワード**条件を使用して、次のプロパティを指定します。値のペア: **Isfromerrorremediation: true**。</span><span class="sxs-lookup"><span data-stu-id="d1471-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="d1471-148">このプロパティは、校閲セットからドキュメントをエクスポートするときに、エクスポート読み込みファイルでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1471-148">This property is also available in the export load file when you export documents from a review set.</span></span>
