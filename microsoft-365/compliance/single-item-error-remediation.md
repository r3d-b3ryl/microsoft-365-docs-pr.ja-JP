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
description: 一括エラー修復プロセスに従わずに、Advanced eDiscovery のレビュー セット内のドキュメントの処理エラーを修正できます。
ms.openlocfilehash: 8e5d8d00f507dc5792a1beda018d4c76632b82f7
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751584"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a><span data-ttu-id="d9db9-103">Advanced eDiscovery での単一アイテムエラーの修復</span><span class="sxs-lookup"><span data-stu-id="d9db9-103">Single item error remediation in Advanced eDiscovery</span></span>

<span data-ttu-id="d9db9-104">エラー修復により、Advanced eDiscovery ユーザーは、Advanced eDiscovery がコンテンツを適切に処理しないデータの問題を修正できます。</span><span class="sxs-lookup"><span data-stu-id="d9db9-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="d9db9-105">たとえば、パスワードで保護されたファイルはロックまたは暗号化されているので処理できません。</span><span class="sxs-lookup"><span data-stu-id="d9db9-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="d9db9-106">以前は、このワークフローを使用してエラーを一括で [修復するだけでした](error-remediation-when-processing-data-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="d9db9-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="d9db9-107">ただし、調査中のケースに対応するファイルが存在しない場合は、複数のファイルのエラーを修復しても意味がない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9db9-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="d9db9-108">また、ファイルのメタデータ (ファイルの場所やアクセス権を持つユーザーなど) を確認して、応答性に関する決定を前もって行うのに役立つ可能性がある前に、エラーを修復する方法は意味がない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9db9-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="d9db9-109">単一アイテムのエラー修復と呼ばれる新機能により、電子情報開示管理者は、処理エラーを含むファイルのメタデータを表示し、必要に応じてレビュー セット内のエラーを直接修復できます。</span><span class="sxs-lookup"><span data-stu-id="d9db9-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="d9db9-110">この記事では、レビュー セット内のエラー処理を含むファイルを特定、無視、および修復する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d9db9-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="d9db9-111">エラーのあるドキュメントを特定する</span><span class="sxs-lookup"><span data-stu-id="d9db9-111">Identify documents with errors</span></span>

<span data-ttu-id="d9db9-112">レビュー セット内のエラー処理のドキュメントが (バナー付き) 識別されます。</span><span class="sxs-lookup"><span data-stu-id="d9db9-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="d9db9-113">エラーを修復または無視できます。</span><span class="sxs-lookup"><span data-stu-id="d9db9-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="d9db9-114">次のスクリーンショットは、パスワードで保護されたレビュー セット内の Word 文書の処理エラー バナーを示しています。</span><span class="sxs-lookup"><span data-stu-id="d9db9-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="d9db9-115">また、処理エラーのあるドキュメントのファイル メタデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d9db9-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![処理エラーが発生したドキュメントに対して表示されるバナー](../media/SIERimage1.png)

<span data-ttu-id="d9db9-117">また、レビュー セット内のドキュメントに対してクエリを実行するときに、処理状態条件を使用して、処理エラーのあるドキュメント[を検索することもできます](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="d9db9-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![処理状態条件を使用してエラー ドキュメントを検索する](../media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="d9db9-119">エラーを無視する</span><span class="sxs-lookup"><span data-stu-id="d9db9-119">Ignore errors</span></span>

<span data-ttu-id="d9db9-120">処理エラー バナーで [無視] **をクリックすると** 、処理エラーを無視できます。</span><span class="sxs-lookup"><span data-stu-id="d9db9-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="d9db9-121">エラーを無視すると、ドキュメントは一括エラー修復ワークフロー [から削除されます](error-remediation-when-processing-data-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="d9db9-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="d9db9-122">エラーが無視された後、ドキュメント バナーの色が変更され、処理エラーが無視されたと示されます。</span><span class="sxs-lookup"><span data-stu-id="d9db9-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="d9db9-123">いつでも、[元に戻す] をクリックして、エラーを無視するように決定を元に戻 **します**。</span><span class="sxs-lookup"><span data-stu-id="d9db9-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![[無視] をクリックして処理エラーを無視する](../media/SIERimage3.png)

<span data-ttu-id="d9db9-125">また、レビュー セット内のドキュメントに対してクエリを実行するときに、無視された処理エラー条件を使用して、処理エラーが発生したドキュメントを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="d9db9-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![無視されたエラー ドキュメントを検索するには、無視された処理エラー条件を使用します。](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="d9db9-127">エラーのあるドキュメントを修復する</span><span class="sxs-lookup"><span data-stu-id="d9db9-127">Remediate a document with errors</span></span>

<span data-ttu-id="d9db9-128">場合によっては、ドキュメントの処理エラーの修復 (パスワードの削除、暗号化されたファイルの暗号化解除、破損したドキュメントの回復) を行い、修復されたドキュメントをレビュー セットに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9db9-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="d9db9-129">これにより、エラー ドキュメントをレビュー セット内の他のドキュメントと共に確認およびエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="d9db9-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="d9db9-130">1 つのドキュメントを修復するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9db9-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="d9db9-131">[**元の**  >  **ファイルをダウンロード]** をクリックして、ファイルのコピーをローカル コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d9db9-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![処理エラーが発生したドキュメントをダウンロードする](../media/SIERimage5.png)

2. <span data-ttu-id="d9db9-133">ファイルのエラーをオフラインで修復します。</span><span class="sxs-lookup"><span data-stu-id="d9db9-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="d9db9-134">暗号化されたファイルの場合、暗号化解除ソフトウェアが必要な場合は、パスワード保護を削除するために、パスワードを入力してファイルを保存するか、パスワード 解読機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9db9-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="d9db9-135">ファイルを修復した後、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="d9db9-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="d9db9-136">レビュー セットで、修復した処理エラーを含むファイルを選択し、[修復] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="d9db9-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![処理エラーが発生したドキュメントのバナーで [修復] をクリックする](../media/SIERimage6.png)


4. <span data-ttu-id="d9db9-138">[ **参照]** をクリックし、ローカル コンピューター上の修復されたファイルの場所に移動して、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d9db9-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![[参照] をクリックし、ローカル コンピューターで修復されたファイルを選択します。](../media/SIERimage7.png)

    <span data-ttu-id="d9db9-140">修復されたファイルを選択すると、レビュー セットに自動的にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="d9db9-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="d9db9-141">ファイルの処理状態を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="d9db9-141">You can track the processing status of the file.</span></span>

    ![修復プロセスの状態が表示されます。](../media/SIERimage8.png)

   <span data-ttu-id="d9db9-143">処理が完了すると、修復されたドキュメントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d9db9-143">After processing is completed, you can view the remediated document.</span></span>

    ![修復されたファイルは、レビュー セットのネイティブ形式で表示できます。](../media/SIERimage9.png)

<span data-ttu-id="d9db9-145">ドキュメントが修復された場合の問題の詳細については、「ファイルが修復された場合の [対応」を参照してください](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated)。</span><span class="sxs-lookup"><span data-stu-id="d9db9-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="d9db9-146">修復されたドキュメントを検索する</span><span class="sxs-lookup"><span data-stu-id="d9db9-146">Search for remediated documents</span></span>

<span data-ttu-id="d9db9-147">[キーワード] 条件を使用し、次のプロパティと値のペアを指定することで、修復されたレビュー セット内のすべてのドキュメントを検索できます **。IsFromErrorRemediation:true**。</span><span class="sxs-lookup"><span data-stu-id="d9db9-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="d9db9-148">このプロパティは、レビュー セットからドキュメントをエクスポートするときに、エクスポート読み込みファイルでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9db9-148">This property is also available in the export load file when you export documents from a review set.</span></span>
