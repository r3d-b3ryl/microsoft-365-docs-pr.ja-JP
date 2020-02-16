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
description: ''
ms.openlocfilehash: 5421ba811e401bdd191aee0ddbff21a1286dc9fe
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074574"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="fbb81-102">データ処理中のエラー修復</span><span class="sxs-lookup"><span data-stu-id="fbb81-102">Error remediation when processing data</span></span>

<span data-ttu-id="fbb81-103">エラー修復により、電子情報開示管理者は、コンテンツを適切に処理できなくなるデータの問題を修正することができます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-103">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="fbb81-104">たとえば、ファイルがロックまたは暗号化されているため、パスワードで保護されたファイルを処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbb81-104">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="fbb81-105">エラー修復を使用すると、電子情報開示管理者は、このようなエラーのあるファイルをダウンロードし、パスワード保護を解除して、修復したファイルをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-105">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="fbb81-106">次のワークフローを使用して、高度な電子情報開示ケースでエラーが発生したファイルを修復します。</span><span class="sxs-lookup"><span data-stu-id="fbb81-106">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="fbb81-107">エラー修復セッションを作成して処理エラーが発生したファイルを修復する</span><span class="sxs-lookup"><span data-stu-id="fbb81-107">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="fbb81-108">次の手順の途中でエラー修復ウィザードが閉じられた場合は、[**表示**] ドロップダウンメニューの [ **Remediations** ] を選択して、[**処理**] タブのエラー修復セッションに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Remediations** in the **View** drop-down menu.</span></span>

1. <span data-ttu-id="fbb81-109">高度な電子情報開示ケースの [**処理**] タブで、[**表示**] ドロップダウンメニューから [**エラー** ] を選択し、[**範囲**] ドロップダウンメニューからレビューセットまたはケース全体を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbb81-109">On the **Processing** tab in the Advanced eDiscovery case, select **Errors** in the **View** drop-down menu and then select a review set or the entire case in the **Scope** drop-down menu.</span></span> <span data-ttu-id="fbb81-110">このセクションでは、特定のレビューセットのケースまたはエラーに関するすべてのエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="fbb81-110">This section displays all errors from the case or error from a specific review set.</span></span>

   ![エラーの修復](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. <span data-ttu-id="fbb81-112">エラーの種類またはファイルの種類の横にあるラジオボタンをクリックして、修復するエラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="fbb81-112">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="fbb81-113">次の例では、パスワードで保護されたファイルを修復しています。</span><span class="sxs-lookup"><span data-stu-id="fbb81-113">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="fbb81-114">[**新しいエラーの修復**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fbb81-114">Click **New error remediation**.</span></span>

    <span data-ttu-id="fbb81-115">エラー修復ワークフローは、エラーが発生したファイルを Microsoft 提供の Azure ストレージの場所にコピーして、それをローカルコンピューターにダウンロードして修復できるようにする準備段階から始まります。</span><span class="sxs-lookup"><span data-stu-id="fbb81-115">The error remediation workflow starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![エラー修復の準備](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="fbb81-117">準備が完了したら、[**次へ: ファイルのダウンロード**] をクリックして、ダウンロードを続行します。</span><span class="sxs-lookup"><span data-stu-id="fbb81-117">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![ファイルをダウンロードする](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="fbb81-119">ファイルをダウンロードするには、**ダウンロード先のパス**を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbb81-119">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="fbb81-120">これは、ファイルがダウンロードされるローカルコンピューター上の親フォルダーへのパスです。</span><span class="sxs-lookup"><span data-stu-id="fbb81-120">This is a path to the parent folder on your local computer where the file will be downloaded.</span></span>  <span data-ttu-id="fbb81-121">既定のパス%USERPROFILE%\Downloads\errors は、ログインしているユーザーの [ダウンロード] フォルダーを指します。</span><span class="sxs-lookup"><span data-stu-id="fbb81-121">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="fbb81-122">このパスは必要に応じて変更できます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-122">You can change this path if desired.</span></span> <span data-ttu-id="fbb81-123">これを変更する場合は、最適なパフォーマンスを得るためにローカルファイルパスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fbb81-123">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="fbb81-124">リモートネットワークパスは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="fbb81-124">Don't use a remote network path.</span></span> <span data-ttu-id="fbb81-125">たとえば、path **c 修復**を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-125">For example, you could use the path **C:\Remediation**.</span></span> 

   <span data-ttu-id="fbb81-126">親フォルダーへのパスは、自動的に AzCopy コマンドに追加されます ( **/Dest**パラメーターの値として)。</span><span class="sxs-lookup"><span data-stu-id="fbb81-126">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Dest** parameter).</span></span>

6. <span data-ttu-id="fbb81-127">[**クリップボードにコピー] を**クリックして、定義済みのコマンドをコピーします。</span><span class="sxs-lookup"><span data-stu-id="fbb81-127">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="fbb81-128">Windows コマンドプロンプトを開き、[AzCopy] コマンドを貼り付けて、 **enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fbb81-128">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span>  

    ![エラー修復の準備](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > <span data-ttu-id="fbb81-130">[**ファイルのダウンロード**] ページで提供されているコマンドを正常に使用するには、azcopy v1.1 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbb81-130">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="fbb81-131">また、手順10でファイルをアップロードするには、AzCopy v1.1 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbb81-131">You also must use AzCopy v8.1 to upload the files in step 10.</span></span> <span data-ttu-id="fbb81-132">このバージョンの AzCopy をインストールするには、「 [Transfer data With AzCopy v2.0 On Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbb81-132">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="fbb81-133">指定した AzCopy コマンドが失敗した場合は、「 [Advanced eDiscovery での AzCopy のトラブルシューティング](troubleshooting-azcopy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbb81-133">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

    <span data-ttu-id="fbb81-134">選択したファイルは、手順5で指定した場所にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-134">The files that you selected are downloaded to the location that you specified in step 5.</span></span> <span data-ttu-id="fbb81-135">親フォルダー ( **C:\windows 修復**など) で、次のサブフォルダー構造が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-135">In the parent folder (for example, **C:\Remediation**), the following subfolder structure is automatically created:</span></span>

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - <span data-ttu-id="fbb81-136">*サブフォルダー 1*には、手順1で選択した範囲に応じて、ケースまたはレビューセットの ID で名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-136">*Subfolder 1* is named with the ID for the case or the review set, depending on the scope that you selected in step 1.</span></span>

    - <span data-ttu-id="fbb81-137">*サブフォルダー 2*には、ダウンロードしたファイルのファイル ID が指定されています。</span><span class="sxs-lookup"><span data-stu-id="fbb81-137">*Subfolder 2* is named with the file ID of the downloaded file</span></span>

    - <span data-ttu-id="fbb81-138">ダウンロードされたファイルは*サブフォルダー 2*にあり、ファイル ID とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-138">The downloaded file is located in *Subfolder 2* and is also named with the file ID.</span></span>

    <span data-ttu-id="fbb81-139">次に、アイテムが**C:\ 修復**親フォルダーにダウンロードされたときに作成されるフォルダーパスとエラーファイル名の例を示します。</span><span class="sxs-lookup"><span data-stu-id="fbb81-139">Here's an example of the folder path and error file name that's created when items are downloaded to the **C:\Remediation** parent folder:</span></span>

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    <span data-ttu-id="fbb81-140">複数のファイルがダウンロードされている場合は、ファイル ID を指定したサブフォルダーに各ファイルがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-140">If multiple files are downloaded, each one is downloaded to a subfolder that's named with the file ID.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fbb81-141">手順9と手順10でファイルをアップロードする場合、修復済みのファイルは同じファイル名を持っている必要があり、同じサブフォルダー構造に配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbb81-141">When you upload files in step 9 and step 10, the remediated files must have that same filename and be located in the same subfolder structure.</span></span> <span data-ttu-id="fbb81-142">サブフォルダーとファイル名を使用して、修復されたファイルを元のエラーファイルに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-142">The subfolder and file names are used to associated the remediated file with the original error file.</span></span> <span data-ttu-id="fbb81-143">フォルダー構造またはファイル名が変更されると、次のエラーが表示`Cannot apply Error Remediation to the current Workingset`されます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-143">If the folder structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span> <span data-ttu-id="fbb81-144">問題を回避するために、修復されたファイルを同じ親フォルダーとサブフォルダー構造に保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fbb81-144">To prevent any issues, we recommend that keep the remediated files in the same parent folder and subfolder structure.</span></span>

7. <span data-ttu-id="fbb81-145">ファイルをダウンロードした後、適切なツールを使用して修復できます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-145">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="fbb81-146">パスワードで保護されたファイルでは、いくつかのパスワードクラッキングツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-146">For password-protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="fbb81-147">ファイルのパスワードがわかっている場合は、それらを開いてパスワード保護を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-147">If you know the passwords for the files, you can open them and remove the password protection.</span></span>

8. <span data-ttu-id="fbb81-148">[高度な電子情報開示とエラー修復ウィザード] に戻り、[**次へ: ファイルのアップロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fbb81-148">Return to Advanced eDiscovery and the error remediation wizard and then click **Next: Upload files**.</span></span>  <span data-ttu-id="fbb81-149">これで、ファイルをアップロードできる次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="fbb81-149">This moves to the next page where you can now upload the files.</span></span>

    ![ファイルをアップロードする](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="fbb81-151">修復したファイルが配置されている親フォルダーを、[**ファイルの場所へのパス**] テキストボックスで指定します。</span><span class="sxs-lookup"><span data-stu-id="fbb81-151">Specify the parent folder where the remediated files are located in the **Path to location of files** text box.</span></span> <span data-ttu-id="fbb81-152">この場合も、親フォルダーには、ファイルをダウンロードしたときに作成されたのと同じサブフォルダー構造を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbb81-152">Again, the parent folder must have the same subfolder structure that was created when you downloaded the files.</span></span>

    <span data-ttu-id="fbb81-153">親フォルダーへのパスは、( **/source**パラメーターの値として) azcopy コマンドに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-153">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Source** parameter).</span></span>

10. <span data-ttu-id="fbb81-154">[**クリップボードにコピー] を**クリックして、定義済みのコマンドをコピーします。</span><span class="sxs-lookup"><span data-stu-id="fbb81-154">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="fbb81-155">Windows コマンドプロンプトを開き、[AzCopy] コマンドを貼り付けて、 **enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fbb81-155">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span> <span data-ttu-id="fbb81-156">ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="fbb81-156">upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="fbb81-158">AzCopy コマンドを実行した後、[**次へ: ファイルの処理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fbb81-158">After you run the AzCopy command, click **Next: Process files**.</span></span>

    <span data-ttu-id="fbb81-159">処理が完了すると、「review set」に進み、修復されたファイルを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-159">When processing is complete, you can go to review set and view the remediated files.</span></span> 

## <a name="remediating-errors-in-container-files"></a><span data-ttu-id="fbb81-160">コンテナーファイルの修復エラー</span><span class="sxs-lookup"><span data-stu-id="fbb81-160">Remediating errors in container files</span></span>

<span data-ttu-id="fbb81-161">上級電子情報開示でコンテナーファイル (.zip ファイルなど) の内容を抽出できない場合は、コンテナーをダウンロードして、元のコンテナーが存在する同じフォルダーに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-161">In situations when the contents of a container file (such as a .zip file) can't be extracted by Advanced eDiscovery, the containers can be downloaded and the contents expanded into the same folder in which the original container resides.</span></span> <span data-ttu-id="fbb81-162">拡張されたファイルは、最初は Advanced 電子情報開示によって展開されたものとして、親コンテナーに属性が付けられます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-162">The expanded files will be attributed to the parent container as if it was originally expanded by Advanced eDiscovery.</span></span> <span data-ttu-id="fbb81-163">このプロセスは、1つのファイルを置換ファイルとしてアップロードする場合を除き、上記と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="fbb81-163">The process works as described as above except for uploading a single file as the replacement file.</span></span>  <span data-ttu-id="fbb81-164">修復済みのファイルをアップロードする場合は、元のコンテナーファイルを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="fbb81-164">When you upload remediated files, don't include the original container file.</span></span>

## <a name="remediating-errors-by-uploading-the-extracted-text"></a><span data-ttu-id="fbb81-165">抽出したテキストをアップロードして修復のエラーを表示する</span><span class="sxs-lookup"><span data-stu-id="fbb81-165">Remediating errors by uploading the extracted text</span></span>

<span data-ttu-id="fbb81-166">場合によっては、アドバンスト eDiscovery が解釈できるネイティブ形式にファイルを修復することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbb81-166">Sometimes it's not possible to remediate a file to native format that Advanced eDiscovery can interpret.</span></span> <span data-ttu-id="fbb81-167">ただし、元のファイルを、ネイティブファイルの元のテキストを含むテキストファイル (*テキストオーバーレイ*と呼ばれるプロセス) に置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-167">But you can replace the original file with a text file that contains the original text of the native file (in a process called *text overlay*).</span></span> <span data-ttu-id="fbb81-168">これを行うには、この記事に記載されている手順に従いますが、元のファイルをネイティブ形式で修復するのではなく、元のファイルから抽出したテキストを含むテキストファイルを作成し、元のファイル名を使用してテキストファイルをアップロードします。.txt サフィックス付きで追加されます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-168">To do this, follow the steps described in this article but instead of remediating the original file in the native format, you would create a text file that contains the extracted text from the original file, and then upload the text file using the original filename appended with a .txt suffix.</span></span> <span data-ttu-id="fbb81-169">たとえば、エラー修復中にファイルをダウンロードするには、ファイル名 33 5850cc2-660247 af0-acfa0-1d14d9128ca2. abc を使用します。</span><span class="sxs-lookup"><span data-stu-id="fbb81-169">For example, you download a file during error remediation with the filename 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.</span></span> <span data-ttu-id="fbb81-170">ネイティブアプリケーションでファイルを開き、テキストをコピーしてから、33 5850cc0-660247 af0-acfa8-1d14d9128ca2 という新しいファイルに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-170">You open the file in the native application, copy the text, and then paste it into a new file named 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt.</span></span> <span data-ttu-id="fbb81-171">この場合、修復済みのテキストファイルを上級電子情報開示にアップロードする前に、必ずネイティブ形式の元のファイルを元のファイルの修復可能な場所から削除してください。</span><span class="sxs-lookup"><span data-stu-id="fbb81-171">When you do this, be sure to remove the original file in the native format from the remediated file location on your local computer before uploading the remediated text file to Advanced eDiscovery.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="fbb81-172">ファイルが修復されたときの処理</span><span class="sxs-lookup"><span data-stu-id="fbb81-172">What happens when files are remediated</span></span>

<span data-ttu-id="fbb81-173">修復済みのファイルがアップロードされると、元のメタデータは次のフィールドを除いて保持されます。</span><span class="sxs-lookup"><span data-stu-id="fbb81-173">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="fbb81-174">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="fbb81-174">ExtractedTextSize</span></span>
- <span data-ttu-id="fbb81-175">HasText</span><span class="sxs-lookup"><span data-stu-id="fbb81-175">HasText</span></span>
- <span data-ttu-id="fbb81-176">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="fbb81-176">IsErrorRemediate</span></span>
- <span data-ttu-id="fbb81-177">LoadId</span><span class="sxs-lookup"><span data-stu-id="fbb81-177">LoadId</span></span>
- <span data-ttu-id="fbb81-178">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="fbb81-178">ProcessingErrorMessage</span></span>
- <span data-ttu-id="fbb81-179">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="fbb81-179">ProcessingStatus</span></span>
- <span data-ttu-id="fbb81-180">テキスト</span><span class="sxs-lookup"><span data-stu-id="fbb81-180">Text</span></span>
- <span data-ttu-id="fbb81-181">WordCount</span><span class="sxs-lookup"><span data-stu-id="fbb81-181">WordCount</span></span>
- <span data-ttu-id="fbb81-182">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="fbb81-182">WorkingsetId</span></span>

<span data-ttu-id="fbb81-183">Advanced eDiscovery のすべてのメタデータフィールドの定義については、「[ドキュメントメタデータフィールド](document-metadata-fields.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbb81-183">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields.md).</span></span>
