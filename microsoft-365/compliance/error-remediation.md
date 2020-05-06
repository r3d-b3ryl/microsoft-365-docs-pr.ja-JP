---
title: 調査のためにデータを処理するときのエラー修復
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
description: エラー修復を使用して、コンテンツの適切な処理を妨げる可能性があるデータ調査 (プレビュー) のデータ問題を修正する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c833ce9ae93f5395e06ee3dbde54ff4a8d5d4a00
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035119"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a><span data-ttu-id="b8234-103">調査のためにデータを処理するときのエラー修復</span><span class="sxs-lookup"><span data-stu-id="b8234-103">Error remediation when processing data for an investigation</span></span>

<span data-ttu-id="b8234-104">エラー修復を使用すると、調査担当はデータ調査 (プレビュー) がコンテンツを適切に処理しないようなデータの問題を修正することができます。</span><span class="sxs-lookup"><span data-stu-id="b8234-104">Error remediation allows investigators the ability to rectify data issues that prevent Data Investigations (Preview) from properly processing the content.</span></span> <span data-ttu-id="b8234-105">たとえば、ファイルがロックまたは暗号化されているため、パスワードで保護されたファイルを処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="b8234-105">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="b8234-106">エラー修復を使用する調査官は、このようなエラーのあるファイルをダウンロードし、パスワード保護を解除して、修復されたファイルをアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="b8234-106">Using error remediation, investigators can download files with such errors, remove the password protection, and upload the remediated files.</span></span>

<span data-ttu-id="b8234-107">データ調査 (プレビュー) ケースでエラーが発生したファイルを修復するには、次のワークフローを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8234-107">Use the following workflow to remediate files with errors in Data Investigations (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="b8234-108">処理エラーが発生したファイルを修復するためのエラー修復セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="b8234-108">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="b8234-109">次の手順の途中でエラー修復ウィザードが閉じられた場合は、[**表示**] ドロップダウンメニューから [error **remediations** **] を**選択することにより、エラー修復セッションに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="b8234-109">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="b8234-110">データ調査の [**処理**] タブで、[**表示**] ドロップダウンメニューから [**エラー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8234-110">On the **Processing** tab in a data investigation, select **Errors** in the **View** dropdown menu.</span></span>

2. <span data-ttu-id="b8234-111">エラーの種類またはファイルの種類の横にあるラジオボタンをクリックして、修復するエラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b8234-111">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="b8234-112">次の例では、パスワードで保護されたファイルを修復しています。</span><span class="sxs-lookup"><span data-stu-id="b8234-112">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="b8234-113">[ **+ 新しいエラーの修復**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8234-113">Click **+ New error remediation**.</span></span>

    ![エラーの修復](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="b8234-115">エラー修復セッションが開始され、エラーが発生しているファイルが、ダウンロード可能な Azure の安全な場所にコピーされる準備段階から開始されます。</span><span class="sxs-lookup"><span data-stu-id="b8234-115">The error remediation session begins, starting with a preparation stage where the files with errors are copied to a secure Azure location so that they can be downloaded.</span></span>

    ![エラー修復の準備](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="b8234-117">準備が完了したら、[**次へ: ファイルのダウンロード**] をクリックして、ダウンロードを続行します。</span><span class="sxs-lookup"><span data-stu-id="b8234-117">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![ファイルをダウンロードする](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="b8234-119">ファイルをダウンロードするには、**ダウンロード先のパス**を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8234-119">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="b8234-120">これは、ファイルをダウンロードするローカルコンピューター上のパスです。</span><span class="sxs-lookup"><span data-stu-id="b8234-120">This is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="b8234-121">既定のパス%USERPROFILE%\Downloads\errors は、ログインしているユーザーの [ダウンロード] フォルダーを指します。必要に応じて変更できます。</span><span class="sxs-lookup"><span data-stu-id="b8234-121">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="b8234-122">最適なパフォーマンスを得るには、リモートネットワークパスの代わりにローカルファイルパスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b8234-122">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8234-123">AzCopy をインストールしていない場合は、ここからインストールできます。https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="b8234-123">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="b8234-124">[**クリップボードにコピー] を**クリックして、定義済みのコマンドをコピーします。</span><span class="sxs-lookup"><span data-stu-id="b8234-124">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="b8234-125">Windows コマンドプロンプトを起動し、コマンドを貼り付けて、 **enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b8234-125">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="b8234-126">ファイルがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="b8234-126">The files will be downloaded.</span></span>

    ![エラー修復の準備](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="b8234-128">このコマンドの実行に関する問題がある場合は、「 [Advanced eDiscovery での AzCopy のトラブルシューティング](troubleshooting-azcopy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8234-128">If you have issues running this command, see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

7. <span data-ttu-id="b8234-129">ファイルをダウンロードした後、適切なツールを使用して修復できます。</span><span class="sxs-lookup"><span data-stu-id="b8234-129">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="b8234-130">パスワードで保護されたファイルでは、いくつかのパスワードクラッキングツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8234-130">For password protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="b8234-131">ファイルのパスワードがわかっている場合は、それらを開いてパスワード保護を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="b8234-131">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    
   > [!NOTE]
    > <span data-ttu-id="b8234-132">修復されたファイルのディレクトリ構造とファイル名を保持することが重要です。</span><span class="sxs-lookup"><span data-stu-id="b8234-132">It's important that you retain the directory structure and file names of the remediated files.</span></span> <span data-ttu-id="b8234-133">ダウンロードしたファイルとフォルダーのパス名によって、修復済みのファイルを元のファイルに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="b8234-133">The path names of the downloaded files and folders make it possible to associate the remediated files with the original files.</span></span>  <span data-ttu-id="b8234-134">ディレクトリ構造またはファイル名が変更されると、次のエラーが表示`Cannot apply Error Remediation to the current Evidenceset`されます。</span><span class="sxs-lookup"><span data-stu-id="b8234-134">If the directory structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Evidenceset`.</span></span>

8. <span data-ttu-id="b8234-135">データの調査 (プレビュー) に戻り、[**次へ: ファイルのアップロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8234-135">Now, return to Data Investigations (Preview) and click **Next: Upload files**.</span></span>  <span data-ttu-id="b8234-136">これにより、次の手順に進み、ファイルをアップロードできるようになります。</span><span class="sxs-lookup"><span data-stu-id="b8234-136">This will move to the next step where you can now upload the files.</span></span>

    ![ファイルをアップロードする](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="b8234-138">[**ファイルの場所へのパス**] テキストボックスに修復したファイルの場所を指定し、[**クリップボードにコピー] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="b8234-138">Specify the location of the remediated files in the **Path to location of files** text box, then click **Copy to clipboard**.</span></span>

10. <span data-ttu-id="b8234-139">コマンドを Windows コマンドプロンプトに貼り付け、 **enter**キーを押してファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="b8234-139">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="b8234-141">最後に、データ調査 (プレビュー) に戻り、[**次へ: プロセスファイル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8234-141">Finally, return to Data Investigations (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="b8234-142">処理が完了したとき。</span><span class="sxs-lookup"><span data-stu-id="b8234-142">When processing is complete.</span></span>  <span data-ttu-id="b8234-143">ワーキングセットに戻り、修復されたファイルを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="b8234-143">You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="b8234-144">ファイルが修復されたときの処理</span><span class="sxs-lookup"><span data-stu-id="b8234-144">What happens when files are remediated</span></span>

<span data-ttu-id="b8234-145">修復済みのファイルがアップロードされると、元のメタデータは次のフィールドを除いて保持されます。</span><span class="sxs-lookup"><span data-stu-id="b8234-145">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="b8234-146">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="b8234-146">ExtractedTextSize</span></span>
- <span data-ttu-id="b8234-147">HasText</span><span class="sxs-lookup"><span data-stu-id="b8234-147">HasText</span></span>
- <span data-ttu-id="b8234-148">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="b8234-148">IsErrorRemediate</span></span>
- <span data-ttu-id="b8234-149">LoadId</span><span class="sxs-lookup"><span data-stu-id="b8234-149">LoadId</span></span>
- <span data-ttu-id="b8234-150">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="b8234-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="b8234-151">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="b8234-151">ProcessingStatus</span></span>
- <span data-ttu-id="b8234-152">テキスト</span><span class="sxs-lookup"><span data-stu-id="b8234-152">Text</span></span>
- <span data-ttu-id="b8234-153">WordCount</span><span class="sxs-lookup"><span data-stu-id="b8234-153">WordCount</span></span>
- <span data-ttu-id="b8234-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="b8234-154">WorkingsetId</span></span>

<span data-ttu-id="b8234-155">データ調査 (プレビュー) 内のすべてのドキュメントメタデータフィールドの定義については、「[ドキュメントメタデータフィールド](document-metadata-fields.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8234-155">For a definition of all document metadata fields in Data Investigations (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>
