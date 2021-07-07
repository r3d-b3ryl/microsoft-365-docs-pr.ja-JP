---
title: テスト タスクを設定する
description: テスト タスクを設定する
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
ms.openlocfilehash: 64abb5b10e3dc1d52b6baf8ceccd5aff2baacefe
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322951"
---
# <a name="step-4-the-tasks-tab"></a><span data-ttu-id="e529d-103">手順 4: [タスク] タブ</span><span class="sxs-lookup"><span data-stu-id="e529d-103">Step 4: The tasks tab</span></span>

<span data-ttu-id="e529d-104">[タスク] タブで、[バイナリ] タブでアップロードした zip フォルダーにあるテスト スクリプトへのパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e529d-104">On the tasks tab, you are expected to provide the paths to your test scripts which are in the zip folder you uploaded under the binaries tab.</span></span>

  - <span data-ttu-id="e529d-105">**アウト オブ ボックスのテスト スクリプト:** インストール、起動、閉じる、アンインストールするスクリプトへの相対パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e529d-105">**Out of Box Test Scripts:** Type in the relative paths to your install, launch, close and uninstall scripts.</span></span> <span data-ttu-id="e529d-106">インストール スクリプトの追加設定を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="e529d-106">You also have the option to select additional settings for the install script.</span></span>
  - <span data-ttu-id="e529d-107">**機能テスト スクリプト:** アップロードされた各機能テスト スクリプトへの相対パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e529d-107">**Functional Test Scripts:** Type in the relative path to each functional test script uploaded.</span></span> <span data-ttu-id="e529d-108">ボタンを使用して、追加の機能テスト スクリプトを追加 ```Add Script``` できます。</span><span class="sxs-lookup"><span data-stu-id="e529d-108">Additional functional test scripts can be added using the ```Add Script``` button.</span></span> <span data-ttu-id="e529d-109">少なくとも 1 つのスクリプトが必要で、最大 8 つの機能テスト スクリプトを追加できます。</span><span class="sxs-lookup"><span data-stu-id="e529d-109">You need a minimum of one (1) script and can add up to eight (8) functional test scripts.</span></span> 
  
    <span data-ttu-id="e529d-110">スクリプトはアップロード シーケンスで実行され、特定のスクリプトでエラーが発生すると、後続のスクリプトの実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="e529d-110">The scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>
    <span data-ttu-id="e529d-111">また、各スクリプトに対して追加の設定を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="e529d-111">You also have the option of selecting additional settings for each script provided.</span></span>

## <a name="set-script-path"></a><span data-ttu-id="e529d-112">スクリプト パスの設定</span><span class="sxs-lookup"><span data-stu-id="e529d-112">Set script path</span></span>

![テスト タスクのイメージ](Media/testtask.png)

<span data-ttu-id="e529d-114">フォルダー構造に相対パスを指定する方法のサンプルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e529d-114">Sample of how to provide the relative path on a folder structure is below:</span></span>

<span data-ttu-id="e529d-115">_**Zip_file_uploaded**_</span><span class="sxs-lookup"><span data-stu-id="e529d-115">_**Zip_file_uploaded**_</span></span>
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="e529d-116">**ScriptX.ps1** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="e529d-116">**ScriptX.ps1** would have.</span></span> <span data-ttu-id="e529d-117">_ScriptX.ps1_ パスとして指定します。</span><span class="sxs-lookup"><span data-stu-id="e529d-117">_ScriptX.ps1_ as the relative path.</span></span>
  - <span data-ttu-id="e529d-118">**Script.ps1** フォルダー _1/script.ps1パス_ として指定します。</span><span class="sxs-lookup"><span data-stu-id="e529d-118">**Script.ps1** would have _folder1/script.ps1_ as the relative path.</span></span>


## <a name="next-steps"></a><span data-ttu-id="e529d-119">次の手順</span><span class="sxs-lookup"><span data-stu-id="e529d-119">Next steps</span></span>

<span data-ttu-id="e529d-120">次の記事の [テスト オプション] タブの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="e529d-120">View details of the Test Options tab in the next article</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="e529d-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="e529d-121">Next step</span></span>](testoptions.md)
