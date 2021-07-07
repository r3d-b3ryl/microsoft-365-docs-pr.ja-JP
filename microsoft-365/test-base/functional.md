---
title: テスト ベースでの機能テスト
description: 既存の自動機能テストでアプリケーションをテストする方法の詳細
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
ms.openlocfilehash: 7b5cb907756ec0fb746d303b3ab629e912bf9c96
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323224"
---
# <a name="functional-testing"></a><span data-ttu-id="a868d-103">機能テスト</span><span class="sxs-lookup"><span data-stu-id="a868d-103">Functional testing</span></span>

<span data-ttu-id="a868d-104">ソフトウェア ベンダーとして、M365 ポータルのセルフサービス テスト ベースを使用して、選択したテスト フレームワークを使用してカスタム機能テストを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a868d-104">As a software vendor, you can now perform custom functional tests, using the test framework of your choice - via the self-serve Test Base for M365 portal.</span></span> 

<span data-ttu-id="a868d-105">最初にサービスを開始した際、標準のスクリプトによって駆動される事前に定義されたテストのセットであるアウトオブボックス テストを提供しました。</span><span class="sxs-lookup"><span data-stu-id="a868d-105">When we initially launched the service, we offered the Out-of-box tests, which is a pre-defined set of tests driven through standardized scripting.</span></span> <span data-ttu-id="a868d-106">ただし、これは多くの独立したソフトウェア ベンダー (ISV) の完全なテスト範囲を達成する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="a868d-106">This, however, could not achieve full test coverage for many Independent Software Vendors (ISVs).</span></span> 

<span data-ttu-id="a868d-107">したがって、フィードバックに応じて、自動機能テストをアップロードする機能を ISV に提供しています。</span><span class="sxs-lookup"><span data-stu-id="a868d-107">Hence, in response to your feedback, we are providing our ISVs with the ability to upload automated functional tests.</span></span>

<span data-ttu-id="a868d-108">この機能を使用するには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a868d-108">To use this feature, follow the steps below:</span></span>

1. <span data-ttu-id="a868d-109">アップロード (バイナリ、依存関係、スクリプト) を単一のパッケージとして.zipします。</span><span class="sxs-lookup"><span data-stu-id="a868d-109">Upload your files (binaries, dependencies and scripts) as a single .zip package.</span></span>
2. <span data-ttu-id="a868d-110">さまざまな実行ポイントでテスト仮想マシン (VM) を再起動する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="a868d-110">Choose if you want to reboot the test Virtual Machines (VMs) at various points of execution.</span></span>
3. <span data-ttu-id="a868d-111">スクリプトで使用可能なオプションを管理します。</span><span class="sxs-lookup"><span data-stu-id="a868d-111">Manage available options for your scripts.</span></span>
4. <span data-ttu-id="a868d-112">実行中に VM に更新プログラムWindows適用する時間を選択します。</span><span class="sxs-lookup"><span data-stu-id="a868d-112">Choose when to apply the Windows update on the VM during execution.</span></span>

<span data-ttu-id="a868d-113">上記の手順の詳細な説明を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a868d-113">Detailed descriptions of the above steps are highlighted below:</span></span>

<span data-ttu-id="a868d-114">**アップロードテスト パッケージの作成**</span><span class="sxs-lookup"><span data-stu-id="a868d-114">**Upload a functional test package**</span></span>

<span data-ttu-id="a868d-115">開始するには、アップロード ページに移動し、Azure の M365 ポータルのテスト ベースの左側のナビゲーション メニューにある [アプリケーション カタログ] の下の [アップロード 新しいアプリケーション] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a868d-115">To get started, navigate to the Upload page, select Upload new application under Application catalog on the left-side navigation menu of the Test Base for M365 portal in Azure.</span></span> <span data-ttu-id="a868d-116">そこから：</span><span class="sxs-lookup"><span data-stu-id="a868d-116">From there:</span></span>

<span data-ttu-id="a868d-117">タブ 1 - 基本情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a868d-117">Tab 1 - Enter basic information.</span></span> <span data-ttu-id="a868d-118">アプリケーションの名前とバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a868d-118">Provide the name and version of your application.</span></span> <span data-ttu-id="a868d-119">[テストの種類] オプションで、[ ] を選択します ```Functional tests``` 。</span><span class="sxs-lookup"><span data-stu-id="a868d-119">In the Type of test option, select ```Functional tests```.</span></span> 

<span data-ttu-id="a868d-120">*既定では、アウトオブボックス (OOB) オプションが必要です。*</span><span class="sxs-lookup"><span data-stu-id="a868d-120">*Note that the Out-of-Box (OOB) option is required by default.*</span></span>


![[機能テスト] タブを選択する](Media/functional_testing_tab1.png)

<span data-ttu-id="a868d-122">タブ 2 - アップロードテスト全体 (バイナリ、依存関係、スクリプトなど) を使用して zip ファイルをアップロードして、パッケージのコンポーネントを管理します。</span><span class="sxs-lookup"><span data-stu-id="a868d-122">Tab 2 - Upload the components of your package by uploading a zip file with your entire test (binaries, dependencies, scripts etc).</span></span> 

<span data-ttu-id="a868d-123">詳細については aka.ms/usl-package-outline を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a868d-123">See aka.ms/usl-package-outline for details.</span></span> <span data-ttu-id="a868d-124">(注: アウトオブボックス テスト スクリプトと機能テストコンテンツの両方を同じ zip ファイルに配置する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="a868d-124">(Note: Both the Out-of-Box test scripts and the Functional test contents should be placed into the same zip file).</span></span> <span data-ttu-id="a868d-125">現在、ファイル サイズは 2 GB に制限されています。</span><span class="sxs-lookup"><span data-stu-id="a868d-125">Currently, the file size is limited to 2GB.</span></span>

<span data-ttu-id="a868d-126">タブ 3 - アウトオブボックスおよび機能テスト タスクを構成します。</span><span class="sxs-lookup"><span data-stu-id="a868d-126">Tab 3 - Configure the Out-of-Box and Functional test tasks.</span></span> <span data-ttu-id="a868d-127">ここでは、アプリケーションをインストール、起動、閉じる、アンインストールする PowerShell スクリプトのパス (Out-of-Box 用) と、機能テストを実行するためのすべてのカスタム スクリプトへのパスを選択します。</span><span class="sxs-lookup"><span data-stu-id="a868d-127">Here, choose the path(s) to the PowerShell scripts that will install, launch, close, and uninstall your application (for Out-of-Box) as well as the path(s) to all your custom scripts to perform your functional test.</span></span> <span data-ttu-id="a868d-128">**(注: アプリケーションをアンインストールするスクリプトはオプションです)。**</span><span class="sxs-lookup"><span data-stu-id="a868d-128">**(Note: A script to uninstall your application is optional).**</span></span>

<span data-ttu-id="a868d-129">現在、機能テスト用に 1 ~ 8 つのスクリプトをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="a868d-129">Currently, you can upload between 1 and 8 scripts for your functional tests.</span></span> <span data-ttu-id="a868d-130">(より多くのスクリプトが必要な場合は、この投稿にコメントしてください!</span><span class="sxs-lookup"><span data-stu-id="a868d-130">(Kindly comment on this post if you need more scripts!)</span></span>

![アップロードテストを使用して最大 8 つのスクリプトを作成する](Media/functional_testing_tab3.png)

<span data-ttu-id="a868d-132">(省略可能)インストール後に再起動を構成します。</span><span class="sxs-lookup"><span data-stu-id="a868d-132">(Optional) Configure a restart after installation.</span></span> <span data-ttu-id="a868d-133">一部のアプリケーションでは、インストール後に再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="a868d-133">Some applications require a restart after installation.</span></span> 

<span data-ttu-id="a868d-134">スクリプトの実行後に再起動を実行する場合は、[タスク] タブの特定のスクリプト ```Reboot After Execution``` を選択します。</span><span class="sxs-lookup"><span data-stu-id="a868d-134">Select ```Reboot After Execution``` for the specific Script in the Tasks tab if you would like a restart to be conducted after the execution of that script.</span></span>

<span data-ttu-id="a868d-135">タブ 4 - 更新プログラムWindowsインストールする場合を選択します。Windows更新プログラムのアプリケーションは、任意のスクリプトの前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="a868d-135">Tab 4 - Choose when the Windows update gets installed: The application of the Windows Update patch is done before any script of your choice.</span></span> <span data-ttu-id="a868d-136">アプリケーションのインストール後に更新プログラムWindowsインストールして、実際のアプリケーションの使用シナリオを密接に模倣するようにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a868d-136">It is recommended that you install a Windows update after the application's installation to closely mimic your real-world application use scenarios.</span></span>

![特定Windows後に更新プログラムをインストールできます](Media/functional_testing_tab4.png)

<span data-ttu-id="a868d-138">タブ 5 - パッケージを確認して作成します。</span><span class="sxs-lookup"><span data-stu-id="a868d-138">Tab 5 - Review and create the package.</span></span> <span data-ttu-id="a868d-139">上記の手順を完了したら、アップロード プロセスを完了 ```Create``` します。</span><span class="sxs-lookup"><span data-stu-id="a868d-139">Once you have completed the steps listed above, select ```Create``` to finish the uploading process.</span></span>

<span data-ttu-id="a868d-140">パッケージが作成されると、パッケージの検証状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a868d-140">Once your package has been created, you can check the verification status of your package.</span></span>

<span data-ttu-id="a868d-141">最初のテストを実行して、アプリケーションのインストール、起動、終了、アンインストールを行います。</span><span class="sxs-lookup"><span data-stu-id="a868d-141">We run an initial test to install, launch, close, and uninstall your application.</span></span> <span data-ttu-id="a868d-142">これにより、パッケージがエラーフリーでサービスにインストール可能な状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a868d-142">This allows us to verify that your package can install on our service error-free.</span></span>

<span data-ttu-id="a868d-143">検証プロセスには最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a868d-143">The verification process could take up to 24 hours.</span></span> <span data-ttu-id="a868d-144">検証が完了すると、メニューの状態が表示されます ```Manage packages``` 。これは、次の 2 つのエントリの 1 つになります。</span><span class="sxs-lookup"><span data-stu-id="a868d-144">Once verification is complete, you can see the status in the ```Manage packages``` menu, which would be one of two entries:</span></span>

1. <span data-ttu-id="a868d-145">検証が成功: パッケージは、選択した OS ビルドの更新プログラムWindowsリリース前に自動的にテストされます。</span><span class="sxs-lookup"><span data-stu-id="a868d-145">Verification succeeds: The package will be automatically tested against pre-release Windows updates for the OS builds you selected.</span></span>
<span data-ttu-id="a868d-146">または</span><span class="sxs-lookup"><span data-stu-id="a868d-146">or</span></span>
2. <span data-ttu-id="a868d-147">検証に失敗しました: 失敗の理由を調査し、問題を解決し、パッケージを再アップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a868d-147">Verification fails: You will need to investigate the reasons for the failure, fix the issue, and re-upload your package.</span></span>

<span data-ttu-id="a868d-148">また、Azure ポータルの通知アイコンを使用して、いずれかの結果が通知されます。</span><span class="sxs-lookup"><span data-stu-id="a868d-148">You will also be notified of either outcome via the notification icon in the Azure portal.</span></span>
