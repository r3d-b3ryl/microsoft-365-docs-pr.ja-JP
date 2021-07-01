---
title: データ処理中のエラー修復
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
description: エラー修復を使用して、コンテンツの適切な処理を妨げる可能性Advanced eDiscoveryのデータの問題を修正する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 891e8292fca629669a48684e95f522c08838d3aa
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226661"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="ac1b9-103">データ処理中のエラー修復</span><span class="sxs-lookup"><span data-stu-id="ac1b9-103">Error remediation when processing data</span></span>

<span data-ttu-id="ac1b9-104">エラー修復を使用すると、電子情報開示管理者は、ユーザーがコンテンツを適切に処理Advanced eDiscoveryデータの問題を修正できます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-104">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="ac1b9-105">たとえば、パスワードで保護されたファイルは、ファイルがロックまたは暗号化された後で処理できません。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-105">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="ac1b9-106">エラー修復を使用して、電子情報開示管理者は、このようなエラーが発生したファイルをダウンロードし、パスワード保護を削除してから、修復されたファイルをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-106">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="ac1b9-107">次のワークフローを使用して、エラーが発生したファイルを修復Advanced eDiscoveryします。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-107">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="ac1b9-108">処理エラーのあるファイルを修復するためのエラー修復セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="ac1b9-108">Create an error remediation session to remediate files with processing errors</span></span>

> [!NOTE]
> <span data-ttu-id="ac1b9-109">次の手順の間にエラー修復ウィザードがいつでも閉じている場合は、[表示] ドロップダウン メニューの [修復] を選択して、[処理]タブからエラー修復セッションに戻ります。 </span><span class="sxs-lookup"><span data-stu-id="ac1b9-109">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Remediations** in the **View** drop-down menu.</span></span>

1. <span data-ttu-id="ac1b9-110">Advanced eDiscoveryケースの [処理] タブで、[表示] ドロップダウンメニューの [エラー] を選択し、[スコープ] ドロップダウンメニューでレビュー セットまたはケース全体を選択します。 </span><span class="sxs-lookup"><span data-stu-id="ac1b9-110">On the **Processing** tab in the Advanced eDiscovery case, select **Errors** in the **View** drop-down menu and then select a review set or the entire case in the **Scope** drop-down menu.</span></span> <span data-ttu-id="ac1b9-111">このセクションには、特定のレビューセットのケースやエラーのすべてのエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-111">This section displays all errors from the case or error from a specific review set.</span></span>

   ![エラー修復](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. <span data-ttu-id="ac1b9-113">修復するエラーを選択するには、エラーの種類またはファイルの種類の横にあるラジオ ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-113">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="ac1b9-114">次の例では、パスワードで保護されたファイルを修復します。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-114">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="ac1b9-115">[新 **しいエラー修復] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-115">Click **New error remediation**.</span></span>

    <span data-ttu-id="ac1b9-116">エラー修復ワークフローは、エラーのあるファイルが Microsoft 提供の Azure Storage の場所にコピーされ、修復するためにローカル コンピューターにダウンロードできる準備段階から始まります。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-116">The error remediation workflow starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![エラー修復の準備](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="ac1b9-118">準備が完了したら、[次へ: ファイルの **ダウンロード] をクリックしてダウンロード** を続行します。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-118">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![ファイルをダウンロードする](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="ac1b9-120">ファイルをダウンロードするには、 **ダウンロードの保存先パス** を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-120">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="ac1b9-121">これは、ファイルをダウンロードするローカルコンピューター上の親フォルダーへのパスです。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-121">This is a path to the parent folder on your local computer where the file will be downloaded.</span></span>  <span data-ttu-id="ac1b9-122">既定のパス %USERPROFILE%\Downloads\errors は、ログインしているユーザーのダウンロード フォルダーをポイントします。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-122">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="ac1b9-123">必要に応じて、このパスを変更できます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-123">You can change this path if desired.</span></span> <span data-ttu-id="ac1b9-124">変更する場合は、最適なパフォーマンスを得るローカル ファイル パスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-124">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="ac1b9-125">リモート ネットワーク パスを使用しない。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-125">Don't use a remote network path.</span></span> <span data-ttu-id="ac1b9-126">たとえば、パス **C:\修復を使用できます**。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-126">For example, you could use the path **C:\Remediation**.</span></span>

   <span data-ttu-id="ac1b9-127">親フォルダーへのパスは、AzCopy コマンド (/Dest パラメーターの値として) **に自動的に追加** されます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-127">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Dest** parameter).</span></span>

6. <span data-ttu-id="ac1b9-128">定義済みコマンドをコピーするには **[クリップボードにコピー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-128">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="ac1b9-129">コマンド プロンプトをWindowsし、AzCopy コマンドを貼り付け、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-129">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span>

    ![エラー修復の準備](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="ac1b9-131">[ファイルのダウンロード] ページで提供されているコマンドを正常に使用するには、AzCopy v8.1 を **使用する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-131">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="ac1b9-132">手順 10 でファイルをアップロードするには、AzCopy v8.1 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-132">You also must use AzCopy v8.1 to upload the files in step 10.</span></span> <span data-ttu-id="ac1b9-133">このバージョンの AzCopy をインストールするには、「AzCopy [v8.1](/previous-versions/azure/storage/storage-use-azcopy)を使用してデータを転送する」を参照Windows。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-133">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="ac1b9-134">指定された AzCopy コマンドが失敗した場合は、「トラブルシューティング[AzCopy in Advanced eDiscovery」 を参照してください](troubleshooting-azcopy.md)。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-134">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

    <span data-ttu-id="ac1b9-135">手順5で指定した場所に、選択したファイルがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-135">The files that you selected are downloaded to the location that you specified in step 5.</span></span> <span data-ttu-id="ac1b9-136">親フォルダー(例: **C:\Remediation**) に、次のサブフォルダー構造が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-136">In the parent folder (for example, **C:\Remediation**), the following subfolder structure is automatically created:</span></span>

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - <span data-ttu-id="ac1b9-137">*サブフォルダー 1* には、手順1で選択した範囲に応じて、ケースまたはレビューセットの ID の名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-137">*Subfolder 1* is named with the ID for the case or the review set, depending on the scope that you selected in step 1.</span></span>

    - <span data-ttu-id="ac1b9-138">*サブフォルダー 2* には、ダウンロードしたファイルのファイル ID が付いています。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-138">*Subfolder 2* is named with the file ID of the downloaded file</span></span>

    - <span data-ttu-id="ac1b9-139">ダウンロードしたファイルは *サブフォルダー 2* に保存され、ファイル ID で呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-139">The downloaded file is located in *Subfolder 2* and is also named with the file ID.</span></span>

    <span data-ttu-id="ac1b9-140">アイテムを **C:\Remediation** 親フォルダーにダウンロードするときに作成されるフォルダー パスとエラー ファイル名の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-140">Here's an example of the folder path and error file name that's created when items are downloaded to the **C:\Remediation** parent folder:</span></span>

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    <span data-ttu-id="ac1b9-141">複数のファイルがダウンロードされた場合、各ファイルは、ファイル ID で名前が付けられたサブフォルダーにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-141">If multiple files are downloaded, each one is downloaded to a subfolder that's named with the file ID.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ac1b9-142">手順 9 と手順 10 でファイルをアップロードする場合、修復されたファイルは同じファイル名を持ち、同じサブフォルダー構造にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-142">When you upload files in step 9 and step 10, the remediated files must have that same filename and be located in the same subfolder structure.</span></span> <span data-ttu-id="ac1b9-143">サブフォルダーとファイル名は、修復されたファイルを元のエラー ファイルに関連付けするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-143">The subfolder and file names are used to associated the remediated file with the original error file.</span></span> <span data-ttu-id="ac1b9-144">フォルダー構造またはファイル名が変更された場合は、次のエラーが表示されます `Cannot apply Error Remediation to the current Workingset` 。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-144">If the folder structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span> <span data-ttu-id="ac1b9-145">問題を回避するには、修復されたファイルを同じ親フォルダーとサブフォルダー構造に保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-145">To prevent any issues, we recommend that keep the remediated files in the same parent folder and subfolder structure.</span></span>

7. <span data-ttu-id="ac1b9-146">ファイルをダウンロードしたら、適切なツールで修復できます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-146">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="ac1b9-147">パスワードで保護されたファイルの場合、使用できるパスワード割れツールがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-147">For password-protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="ac1b9-148">ファイルのパスワードがわかっている場合は、ファイルを開いてパスワード保護を削除できます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-148">If you know the passwords for the files, you can open them and remove the password protection.</span></span>

8. <span data-ttu-id="ac1b9-149">エラー修復ウィザードAdvanced eDiscoveryに戻り、[次へ: ファイルを開 **く] をアップロードします**。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-149">Return to Advanced eDiscovery and the error remediation wizard and then click **Next: Upload files**.</span></span>  <span data-ttu-id="ac1b9-150">これで、次のページに移動して、ファイルをアップロードできるようになります。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-150">This moves to the next page where you can now upload the files.</span></span>

    ![アップロードファイル](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="ac1b9-152">**[ファイルの場所へのパス]** テキストボックス内の修復されたファイルが保存されている親フォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-152">Specify the parent folder where the remediated files are located in the **Path to location of files** text box.</span></span> <span data-ttu-id="ac1b9-153">ここでも、親フォルダーには、ファイルのダウンロード時に作成されたのと同じサブフォルダー構造が必要です。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-153">Again, the parent folder must have the same subfolder structure that was created when you downloaded the files.</span></span>

    <span data-ttu-id="ac1b9-154">親フォルダーへのパスは、(/Source パラメーターの値として) AzCopy コマンド **に自動的に追加** されます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-154">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Source** parameter).</span></span>

10. <span data-ttu-id="ac1b9-155">定義済みコマンドをコピーするには **[クリップボードにコピー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-155">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="ac1b9-156">コマンド プロンプトをWindowsし、AzCopy コマンドを貼り付け、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-156">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span> <span data-ttu-id="ac1b9-157">ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-157">upload the files.</span></span>

    ![Azcopy での修復されたファイルの正常なアップロードの結果](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="ac1b9-159">AzCopy コマンドを実行した後、[次へ: ファイルの処理 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-159">After you run the AzCopy command, click **Next: Process files**.</span></span>

    <span data-ttu-id="ac1b9-160">処理が完了したら、セットを確認し、修復されたファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-160">When processing is complete, you can go to review set and view the remediated files.</span></span>

## <a name="remediating-errors-in-container-files"></a><span data-ttu-id="ac1b9-161">コンテナー ファイルのエラーの修復</span><span class="sxs-lookup"><span data-stu-id="ac1b9-161">Remediating errors in container files</span></span>

<span data-ttu-id="ac1b9-162">Advanced eDiscovery によってコンテナー ファイル (.zip ファイルなど) の内容を抽出できない場合は、コンテナーをダウンロードして、元のコンテナーが存在する同じフォルダーに展開できます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-162">In situations when the contents of a container file (such as a .zip file) can't be extracted by Advanced eDiscovery, the containers can be downloaded and the contents expanded into the same folder in which the original container resides.</span></span> <span data-ttu-id="ac1b9-163">展開されたファイルは、親コンテナーが最初に展開された場合と同様に親コンテナーにAdvanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-163">The expanded files will be attributed to the parent container as if it was originally expanded by Advanced eDiscovery.</span></span> <span data-ttu-id="ac1b9-164">このプロセスは、1 つのファイルを置換ファイルとしてアップロードする場合を除き、上記のように動作します。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-164">The process works as described as above except for uploading a single file as the replacement file.</span></span>  <span data-ttu-id="ac1b9-165">修復されたファイルをアップロードする場合は、元のコンテナー ファイルを含めないことです。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-165">When you upload remediated files, don't include the original container file.</span></span>

## <a name="remediating-errors-by-uploading-the-extracted-text"></a><span data-ttu-id="ac1b9-166">抽出されたテキストをアップロードしてエラーを修復する</span><span class="sxs-lookup"><span data-stu-id="ac1b9-166">Remediating errors by uploading the extracted text</span></span>

<span data-ttu-id="ac1b9-167">ファイルを解釈できるネイティブ形式に修復できないAdvanced eDiscovery場合があります。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-167">Sometimes it's not possible to remediate a file to native format that Advanced eDiscovery can interpret.</span></span> <span data-ttu-id="ac1b9-168">ただし、元のファイルをネイティブ ファイルの元のテキストを含むテキスト ファイルに置き換えることができます (テキスト オーバーレイと呼ばれる *プロセス* で)。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-168">But you can replace the original file with a text file that contains the original text of the native file (in a process called *text overlay*).</span></span> <span data-ttu-id="ac1b9-169">これを行うには、この記事で説明する手順に従いますが、元のファイルをネイティブ形式で修復する代わりに、元のファイルから抽出されたテキストを含むテキスト ファイルを作成し、.txt サフィックスが付加された元のファイル名を使用してテキスト ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-169">To do this, follow the steps described in this article but instead of remediating the original file in the native format, you would create a text file that contains the extracted text from the original file, and then upload the text file using the original filename appended with a .txt suffix.</span></span> <span data-ttu-id="ac1b9-170">たとえば、ファイル名 335850cc-6602-4af0-acfa-1d14d9128ca2.abc でエラー修復中にファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-170">For example, you download a file during error remediation with the filename 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.</span></span> <span data-ttu-id="ac1b9-171">ネイティブ アプリケーションでファイルを開き、テキストをコピーし、そのファイルを 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt という名前の新しいファイルに貼り335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-171">You open the file in the native application, copy the text, and then paste it into a new file named 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt.</span></span> <span data-ttu-id="ac1b9-172">これを行う場合は、修復されたテキスト ファイルを Advanced eDiscovery にアップロードする前に、ローカル コンピューターの修復されたファイルの場所からネイティブ形式の元のファイルを削除してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-172">When you do this, be sure to remove the original file in the native format from the remediated file location on your local computer before uploading the remediated text file to Advanced eDiscovery.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="ac1b9-173">ファイルが修復された場合の対応</span><span class="sxs-lookup"><span data-stu-id="ac1b9-173">What happens when files are remediated</span></span>

<span data-ttu-id="ac1b9-174">修復されたファイルがアップロードされると、次のフィールドを除き、元のメタデータが保持されます。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-174">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span>

- <span data-ttu-id="ac1b9-175">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="ac1b9-175">ExtractedTextSize</span></span>
- <span data-ttu-id="ac1b9-176">HasText</span><span class="sxs-lookup"><span data-stu-id="ac1b9-176">HasText</span></span>
- <span data-ttu-id="ac1b9-177">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="ac1b9-177">IsErrorRemediate</span></span>
- <span data-ttu-id="ac1b9-178">LoadId</span><span class="sxs-lookup"><span data-stu-id="ac1b9-178">LoadId</span></span>
- <span data-ttu-id="ac1b9-179">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="ac1b9-179">ProcessingErrorMessage</span></span>
- <span data-ttu-id="ac1b9-180">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="ac1b9-180">ProcessingStatus</span></span>
- <span data-ttu-id="ac1b9-181">テキスト</span><span class="sxs-lookup"><span data-stu-id="ac1b9-181">Text</span></span>
- <span data-ttu-id="ac1b9-182">WordCount</span><span class="sxs-lookup"><span data-stu-id="ac1b9-182">WordCount</span></span>
- <span data-ttu-id="ac1b9-183">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="ac1b9-183">WorkingsetId</span></span>

<span data-ttu-id="ac1b9-184">ドキュメント内のすべてのメタデータ フィールドの定義についてはAdvanced eDiscoveryドキュメント メタデータ フィールド[を参照してください](document-metadata-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="ac1b9-184">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields-in-advanced-ediscovery.md).</span></span>