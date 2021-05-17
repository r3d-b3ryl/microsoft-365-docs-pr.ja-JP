---
title: 'Google ファイルをビジネス向Microsoft 365に移行する '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Mover を使用して Google ファイルをビジネス向Microsoft 365移行する方法について説明します。
ms.openlocfilehash: 6feabff7e36e84f7dba56e74333648325cf43920
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913576"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="ef6b1-103">Google ファイルをビジネス向Microsoft 365に移行する</span><span class="sxs-lookup"><span data-stu-id="ef6b1-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="ef6b1-104">ビジネス向けMicrosoft 365に移動する場合は、ファイルを移行する必要Google ドライブ。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-104">When you move to Microsoft 365 for business, you'll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="ef6b1-105">Mover アプリを使用して、個人用ドライブと共有ドライブからファイルを移動できます。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="ef6b1-106">詳細については [、「Mover Cloud Migration」を参照してください](/sharepointmigration/mover-plan-migration)。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-106">For more information, see [Mover Cloud Migration](/sharepointmigration/mover-plan-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="ef6b1-107">Mover はファイルのコピーを作成し、そのコピーをビジネス向Microsoft 365移動します。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="ef6b1-108">元のファイルは Google ドライブにも保存されます。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="ef6b1-109">始める前に</span><span class="sxs-lookup"><span data-stu-id="ef6b1-109">Before you start</span></span>

<span data-ttu-id="ef6b1-110">すべてのユーザーが、ビジネス向け Microsoft 365にサインインし、そのユーザーのOneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="ef6b1-111">これを行うには、[office.com][に移動](https://office.com)し、Microsoft 365資格情報を使用してサインインし、[OneDrive] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-111">To do this, go to [office.com](https://office.com), sign in with your Microsoft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="ef6b1-112">お試しください!</span><span class="sxs-lookup"><span data-stu-id="ef6b1-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="ef6b1-113">Mover のインストール</span><span class="sxs-lookup"><span data-stu-id="ef6b1-113">Install Mover</span></span>

1. <span data-ttu-id="ef6b1-114">Google Workspace 管理コンソールにサインインするには[、admin.google.com。](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="ef6b1-114">Sign in to your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="ef6b1-115">[アプリ  >  **] [Google ワークスペース マーケットプレース アプリ]**  >  **[ドメイン インストールリストにアプリを追加する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-115">Choose **Apps** > **Google Workspace Marketplace apps** > **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="ef6b1-116">Mover を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="ef6b1-117">[ドメイン **インストール] を選択し**、[続行] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="ef6b1-118">アクセス許可を確認し、条件に同意するチェック ボックスをオンにし、[許可] を選択し、[ **次** へ] 、[完了] **の順** に **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="ef6b1-119">コネクタの作成と移行の実行</span><span class="sxs-lookup"><span data-stu-id="ef6b1-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="ef6b1-120">Google Workspace **Marketplace アプリに戻ります**。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="ef6b1-121">ブラウザーを更新し **、Mover アプリを選択** します。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="ef6b1-122">下にスクロールして、ユニバーサル ナビゲーション リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="ef6b1-123">[ **新しいコネクタの承認] を** 選択し **、G Suite (Admin) を** 見つけて、[承認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="ef6b1-124">必要に応 **じ、[表示名]** を変更し、[承認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="ef6b1-125">Google 管理者アカウントを選択し、アクセス許可を確認してから、[許可] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="ef6b1-126">Mover には、検出されたチーム ドライブとユーザー ドライブの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="ef6b1-127">[**宛先の選択] で**、[新しい **コネクタの承認]** を選択し、[Office 365]**を探し、[** 承認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="ef6b1-128">アプリ内の Mover アプリにアクセス許可を付与するにはAzure Active Directory[に移動](https://aka.ms/Office365MoverAuth)aka.ms/Office365MoverAuth。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="ef6b1-129">**[Office 365] [権限]** を選択 **し、\*\*\*\*会社の管理者の同意を付与します**。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="ef6b1-130">アカウントを選択し、アクセス許可を確認し、[同意する] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="ef6b1-131">[プロパティ **] を** 選択し、[ユーザーの **割り当てが必要か]** がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="ef6b1-132">Mover アプリに戻り、表示 **名を変更** します 。必要に応じ、[ **承認**] を選択し、Microsoft 管理者アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="ef6b1-133">Mover は、オンライン (または SPO) サイトSharePoint検出されたユーザーの数について通知します。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="ef6b1-134">[ **移行セットアップの続行] を** 選択し、[ **ユーザーの追加] 、[** ユーザー **の自動検出と追加] の順に選択します**。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="ef6b1-135">Mover アプリは、Google のソース パスから移行先パスにドライブをマップMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="ef6b1-136">ドライブが自動的にマップしない場合は、移行先のパスを CSV ファイルに追加します。このパスは、後で共有ドライブを別のドキュメント ライブラリに移行SharePointします。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-136">If a drive doesn't map automatically, add its destination path to a CSV file, which we'll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="ef6b1-137">この場合、移行済みファイルというSharePointサイトが追加され、ドキュメント ページの URL がメモされます。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="ef6b1-138">次に、ソース パス、宛先パス、およびタグの形式を使用して CSV ファイルを作成しました。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="ef6b1-139">詳細については、「aka.ms/movercsv」 [を参照してください](/sharepointmigration/mover-create-migration-csv)。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-139">For details see [aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="ef6b1-140">宛先パス URL を追加する場合は、共有ドキュメントの後にすべてを削除します。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-140">When adding the Destination Path URL, remove everything after Shared Documents.</span></span> <span data-ttu-id="ef6b1-141">たとえば、次の完全な URL はエラーを発生します。`https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="ef6b1-141">For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="ef6b1-142">次のように変更してください。`https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="ef6b1-142">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="ef6b1-143">CSV ファイルの準備ができたら、[移行アクション] 、[移行 **に** 追加] **、[アップロード** する **ファイルの選択] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-143">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="ef6b1-144">CSV ファイルに移動して選択し、[開く] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-144">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="ef6b1-145">ファイルを移行するユーザー ドライブを選択し、[ユーザーの移行の開始 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-145">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="ef6b1-146">移行情報を確認し、移行を開始する時間を選択し、利用規約に同意し、[続行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-146">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="ef6b1-147">Mover アプリは、移行プロセスが完了すると通知します。</span><span class="sxs-lookup"><span data-stu-id="ef6b1-147">The Mover app will inform you when the migration process is complete.</span></span>