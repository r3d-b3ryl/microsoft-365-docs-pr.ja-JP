---
title: テスト パッケージのガイドライン
description: テスト パッケージに関するガイドラインを確認する
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323044"
---
# <a name="test-package-guidelines"></a><span data-ttu-id="c3157-103">テスト パッケージのガイドライン</span><span class="sxs-lookup"><span data-stu-id="c3157-103">Test package guidelines</span></span>

## <a name="1---script-referencing"></a><span data-ttu-id="c3157-104">1. スクリプト参照</span><span class="sxs-lookup"><span data-stu-id="c3157-104">1.   Script referencing</span></span>

<span data-ttu-id="c3157-105">ポータルに .zipファイルをアップロードすると、そのファイルのすべてのコンテンツをルート フォルダーに解凍します。</span><span class="sxs-lookup"><span data-stu-id="c3157-105">When you upload a .zip file to the portal, we unzip all the content of that file into a root folder.</span></span> <span data-ttu-id="c3157-106">この最初の解凍操作を実行するためにコードを記述する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c3157-106">You do not need to write any code to do this initial unzip operation.</span></span> <span data-ttu-id="c3157-107">また、アップロードされた zip ファイルを基準.zipパスを使用して、ファイル内の任意のファイルを参照できます。</span><span class="sxs-lookup"><span data-stu-id="c3157-107">You also can reference any file within the .zip by using the path relative to the zip file uploaded.</span></span>

<span data-ttu-id="c3157-108">以下の例では、[タスク] タブの入力フィールドからバイナリ/スクリプトを参照する方法を示します。青のテキストは、二重引用符を付けずに **[スクリプト** パス] **フィールドに入力する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="c3157-108">In the example below, we show how you can reference your binaries/scripts from the input field in the Tasks tab. The text in blue should be entered into the **Script path** field **without the quotation marks.**</span></span>

<span data-ttu-id="c3157-109">アップロードする前に、zip ファイル内のコンテンツを認識することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c3157-109">It is important you are aware of the content within your zip file before uploading it.</span></span> <span data-ttu-id="c3157-110">多くの場合、フォルダーを圧縮すると、ローカル コンピューターは zip ファイルの下にメイン フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3157-110">Often when zipping a folder, your local machine will create a main folder underneath the zip file.</span></span> <span data-ttu-id="c3157-111">この場合、参照元は次の太字で **示** されます。</span><span class="sxs-lookup"><span data-stu-id="c3157-111">In this case, the referencing will be as shown in **bold** below:</span></span>

 <span data-ttu-id="c3157-112">**Contoso_App_Folder.zip**</span><span class="sxs-lookup"><span data-stu-id="c3157-112">**Contoso_App_Folder.zip**</span></span>
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - <span data-ttu-id="c3157-113">ScriptX.ps1 – **"Contoso_App_Folder/ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="c3157-113">ScriptX.ps1 – **“Contoso_App_Folder/ScriptX.ps1”**</span></span>
  - <span data-ttu-id="c3157-114">Script.ps1 – **"Contoso_App_Folder/folder1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="c3157-114">Script.ps1 – **“Contoso_App_Folder/folder1/script.ps1”**</span></span>

<span data-ttu-id="c3157-115">その他の場合、zip ファイルの下にファイルやコンテンツが含めることもできます。つまり、2nd レベルのフォルダーはありません。</span><span class="sxs-lookup"><span data-stu-id="c3157-115">Other times, your zip file may have your files or content right underneath it i.e. no 2nd-level folder:</span></span>

 <span data-ttu-id="c3157-116">**Zip_file_uploaded.zip**</span><span class="sxs-lookup"><span data-stu-id="c3157-116">**Zip_file_uploaded.zip**</span></span>
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="c3157-117">ScriptX.ps1 – **"ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="c3157-117">ScriptX.ps1 – **“ScriptX.ps1”**</span></span>
  - <span data-ttu-id="c3157-118">Script.ps1 – **"folder1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="c3157-118">Script.ps1 – **“folder1/script.ps1”**</span></span>
  
## <a name="2---script-execution"></a><span data-ttu-id="c3157-119">2. スクリプトの実行</span><span class="sxs-lookup"><span data-stu-id="c3157-119">2.   Script execution</span></span>

<span data-ttu-id="c3157-120">**アウトオブボックステスト:** アプリケーション パッケージには、アプリケーションとその依存関係の無人インストール、起動、および終了を実行する少なくとも 3 つの PowerShell スクリプトが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3157-120">**Out-of-Box tests:** The application package needs to contain at least three PowerShell scripts that will execute unattended installing, launching, and closing of the application and its dependencies.</span></span> <span data-ttu-id="c3157-121">各スクリプトは、独自の前提条件の確認、成功した検証、およびそれ自体の後のクリーンアップ (必要な場合) を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3157-121">Each script should handle checking its own prerequisites, validating it succeeded, as well as cleaning up after itself (if necessary).</span></span>

<span data-ttu-id="c3157-122">**機能テスト:** アプリケーション パッケージには、少なくとも 1 つの PowerShell スクリプトが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3157-122">**Functional tests:** The application package needs to contain at least one PowerShell script.</span></span> <span data-ttu-id="c3157-123">複数のスクリプトが提供されている場合、スクリプトはアップロード シーケンスで実行され、特定のスクリプトでエラーが発生すると、後続のスクリプトの実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="c3157-123">Where more than one script is provided, the scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>

### <a name="script-requirements"></a><span data-ttu-id="c3157-124">スクリプトの要件</span><span class="sxs-lookup"><span data-stu-id="c3157-124">Script requirements</span></span>

<span data-ttu-id="c3157-125">• PowerShell バージョン 5.1 以上</span><span class="sxs-lookup"><span data-stu-id="c3157-125">•   PowerShell Version 5.1+</span></span>     

<span data-ttu-id="c3157-126">• 無人実行</span><span class="sxs-lookup"><span data-stu-id="c3157-126">•   Unattended execution</span></span>    

<span data-ttu-id="c3157-127">• エラー戻りコード</span><span class="sxs-lookup"><span data-stu-id="c3157-127">•   Error return code</span></span>               

<span data-ttu-id="c3157-128">• 成功の検証</span><span class="sxs-lookup"><span data-stu-id="c3157-128">•   Validate success</span></span>            

<span data-ttu-id="c3157-129">• スクリプト固有のログ フォルダーへのログ記録</span><span class="sxs-lookup"><span data-stu-id="c3157-129">•   Logging to script specific log folder</span></span>

<span data-ttu-id="c3157-130">テスト パイプラインで正常に実行するには、各スクリプトを完全に無人で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3157-130">Each script needs to run completely unattended to successfully execute in the test pipeline.</span></span>

> [!Note]
> <span data-ttu-id="c3157-131">スクリプトは、正常に完了すると "0" を返し、実行中にエラーが発生した場合はゼロ以外のエラー コードを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3157-131">Scripts should return “0” on successful completion and a non-zero error code if any error occurs during execution.</span></span>

<span data-ttu-id="c3157-132">各スクリプトは、正常に実行されたことを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3157-132">Each script should validate that it ran successfully.</span></span> <span data-ttu-id="c3157-133">例:</span><span class="sxs-lookup"><span data-stu-id="c3157-133">E.g.</span></span> <span data-ttu-id="c3157-134">インストール スクリプトは、インストーラー バイナリの実行が終了した後に、システム上の特定のバイナリやレジストリ キーの存在を確認し、インストールが成功したという程度の信頼を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3157-134">the install script should check for the existence of certain binaries and/or registry keys on the system, after the installer binary finishes executing to ensure with a reasonable degree of confidence that the installation was successful.</span></span> 

<span data-ttu-id="c3157-135">これは、テストの実行時にエラーが発生する場所 (アプリケーションを正常にインストールできない場合と起動できないなど) を適切に診断するために必要です。</span><span class="sxs-lookup"><span data-stu-id="c3157-135">This is necessary to properly diagnose where errors occur during a test run, e.g. unable to install the application successfully versus being unable to launch it.</span></span>

> [!Important]
> <span data-ttu-id="c3157-136">**次の問題を回避します。** スクリプトはコンピューターを再起動し、再起動が必要な場合は、スクリプトのアップロード中にこれを指定してください。</span><span class="sxs-lookup"><span data-stu-id="c3157-136">**Avoid the following:** Scripts should not reboot the machine, if a reboot is necessary please specify this during the upload of your scripts.</span></span>

## <a name="3---log-collection"></a><span data-ttu-id="c3157-137">3. ログ収集</span><span class="sxs-lookup"><span data-stu-id="c3157-137">3.   Log collection</span></span>

<span data-ttu-id="c3157-138">各スクリプトは、生成されたログをという名前のフォルダーに出力する必要があります ```logs``` 。</span><span class="sxs-lookup"><span data-stu-id="c3157-138">Each script should output any logs it generates into a folder named ```logs```.</span></span> <span data-ttu-id="c3157-139">という名前のディレクトリ内のすべてのフォルダー ```logs``` がコピーされ、ページにダウンロード用に表示 ```Test Results``` されます。</span><span class="sxs-lookup"><span data-stu-id="c3157-139">All folders in the directory named ```logs``` will be copied and presented for download on the ```Test Results``` page.</span></span>

<span data-ttu-id="c3157-140">たとえば、インストール スクリプト **(App/scripts/install** ディレクトリに含まれます) は、ログ **/install.log** にログを出力し、最終的なログは **Apps/script/install/logs/install.log** に出力できます。</span><span class="sxs-lookup"><span data-stu-id="c3157-140">For example, the installation script (which may be located in the **App/scripts/install** directory) can output its logs to: **logs/install.log**, such that the final log will be at: **Apps/scripts/install/logs/install.log**</span></span>

<span data-ttu-id="c3157-141">システムは、他のフォルダー内の他のファイルと共にファイルをピックアップし ```install.log``` ```logs``` 、ダウンロードのために照合します。</span><span class="sxs-lookup"><span data-stu-id="c3157-141">The system will pick up the ```install.log``` file along with other files within other ```logs``` folders and collate it for download.</span></span>


## <a name="4---application-binaries"></a><span data-ttu-id="c3157-142">4. アプリケーション バイナリ</span><span class="sxs-lookup"><span data-stu-id="c3157-142">4.   Application binaries</span></span>

<span data-ttu-id="c3157-143">バイナリと依存関係は、1 つの zip ファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3157-143">Any binaries and dependencies should be included in the single zip file.</span></span> 

<span data-ttu-id="c3157-144">これには、アプリケーションのインストールに必要なすべてが含まれる必要があります (たとえば、アプリケーション インストーラー)。アプリケーションが .NET Core/Standard や .NET Framework などのフレームワークに依存している場合は、ファイルに含め、提供されたスクリプトで正しく参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3157-144">These should include everything necessary for installation of the application (e.g. the application installer); if the application has a dependency on any frameworks, such as .NET Core/Standard or .NET Framework, these should be included in the file and referenced correctly in the provided scripts.</span></span>


> [!Note]
> <span data-ttu-id="c3157-145">アップロードされた zip ファイルの名前にスペースや特殊文字を含めることはできません</span><span class="sxs-lookup"><span data-stu-id="c3157-145">The uploaded zip file cannot have any spaces or special characters in its name</span></span>

## <a name="next-steps"></a><span data-ttu-id="c3157-146">次の手順</span><span class="sxs-lookup"><span data-stu-id="c3157-146">Next steps</span></span>

<span data-ttu-id="c3157-147">次の記事に進み、よく寄せられる **質問 (FAQ) を表示する**</span><span class="sxs-lookup"><span data-stu-id="c3157-147">Advance to the next article to view some **Frequently Asked Questions (FAQ)**</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="c3157-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="c3157-148">Next step</span></span>](faq.md)
