---
title: アップロードアプリケーション バイナリ
description: M365 のテスト ベースの使用を開始する方法
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
ms.openlocfilehash: 1c4ff6ac03989cc9be70e18a1b8634f2da11e721
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323164"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a><span data-ttu-id="dacf0-103">手順 3: アップロード、依存関係、およびスクリプトを削除する</span><span class="sxs-lookup"><span data-stu-id="dacf0-103">Step 3: Upload your binaries, dependencies, and scripts</span></span>

<span data-ttu-id="dacf0-104">このタブでは、テスト スイートの実行に使用するバイナリ、依存関係、スクリプトを含む単一の zip パッケージをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="dacf0-104">On this tab, you will upload a single zip package containing your binaries, dependencies and scripts used to run your test suite.</span></span>

## <a name="upload-package-zip-file"></a><span data-ttu-id="dacf0-105">アップロード zip ファイル</span><span class="sxs-lookup"><span data-stu-id="dacf0-105">Upload package zip file</span></span>

![アップロードバイナリの作成](Media/AddBinaries.png)

  - <span data-ttu-id="dacf0-107">アップロードされた依存関係には、テスト フレームワーク、スクリプト エンジン、またはアプリケーションまたはテスト ケースを実行するためにアクセスされるデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dacf0-107">Uploaded dependencies can include test frameworks, scripting engines or data that will be accessed to run your application or test cases.</span></span> <span data-ttu-id="dacf0-108">たとえば、ブラウザー ベースのテストの実行に役立つ Selenium インストーラーと Webdriver インストーラーをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="dacf0-108">For example, you can upload Selenium and a webdriver installer to help run browser-based tests.</span></span>
  - <span data-ttu-id="dacf0-109">スクリプトアクティビティがモジュール形式で保持されるのがベスト プラクティスです。</span><span class="sxs-lookup"><span data-stu-id="dacf0-109">It is best practice to ensure your script activities are kept modular i.e.</span></span> 
    - <span data-ttu-id="dacf0-110">スクリプト ```Install``` はインストール操作のみを実行します。</span><span class="sxs-lookup"><span data-stu-id="dacf0-110">The ```Install``` script only performs install operations.</span></span>
    - <span data-ttu-id="dacf0-111">スクリプト ```Launch``` はアプリケーションのみを起動します。</span><span class="sxs-lookup"><span data-stu-id="dacf0-111">The ```Launch``` script only launches the application.</span></span>
    - <span data-ttu-id="dacf0-112">スクリプト ```Close``` はアプリケーションのみを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dacf0-112">The ```Close``` script only closes the application.</span></span>
    - <span data-ttu-id="dacf0-113">オプションの ```Uninstall``` スクリプトは、アプリケーションのみをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="dacf0-113">The optional ```Uninstall``` script only uninstalls the application.</span></span>

<span data-ttu-id="dacf0-114">**現在、ポータルは PowerShell スクリプトのみをサポートしています。**</span><span class="sxs-lookup"><span data-stu-id="dacf0-114">**Currently, the portal only supports PowerShell scripts.**</span></span>


## <a name="next-steps"></a><span data-ttu-id="dacf0-115">次の手順</span><span class="sxs-lookup"><span data-stu-id="dacf0-115">Next steps</span></span> 

<span data-ttu-id="dacf0-116">次の記事に進み、「手順 4: テスト タスクを設定 **する」に進みます**。</span><span class="sxs-lookup"><span data-stu-id="dacf0-116">Advance to the next article to go onto Step 4: **Set your Test Tasks**.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="dacf0-117">戻ってください</span><span class="sxs-lookup"><span data-stu-id="dacf0-117">Go back</span></span>](uploadApplication.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="dacf0-118">次の手順</span><span class="sxs-lookup"><span data-stu-id="dacf0-118">Next step</span></span>](testtask.md)

