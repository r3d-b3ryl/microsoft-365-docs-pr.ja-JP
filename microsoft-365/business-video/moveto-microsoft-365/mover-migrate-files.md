---
title: 'Google ファイルを Microsoft 365 for business に移行する '
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
description: Mover を使用して Google ファイルを Microsoft 365 for business に移行する方法について説明します。
ms.openlocfilehash: 72ea81ad86a20e01b4650915fef96a713b207c3b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166161"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="176d2-103">Google ファイルを Microsoft 365 for business に移行する</span><span class="sxs-lookup"><span data-stu-id="176d2-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="176d2-104">ビジネス向け Microsoft 365 に移行する場合は、Google ドライブからファイルを移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="176d2-104">When you move to Microsoft 365 for business, you'll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="176d2-105">Mover アプリを使って、個人用ドライブと共有ドライブからファイルを移動できます。</span><span class="sxs-lookup"><span data-stu-id="176d2-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="176d2-106">詳細については [、「Mover クラウド移行」を参照してください](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)。</span><span class="sxs-lookup"><span data-stu-id="176d2-106">For more information, see [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="176d2-107">Mover は、ファイルのコピーを作成し、コピーを Microsoft 365 for business に移動します。</span><span class="sxs-lookup"><span data-stu-id="176d2-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="176d2-108">元のファイルは Google ドライブにも保持されます。</span><span class="sxs-lookup"><span data-stu-id="176d2-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="176d2-109">始める前に</span><span class="sxs-lookup"><span data-stu-id="176d2-109">Before you start</span></span>

<span data-ttu-id="176d2-110">すべてのユーザーが Microsoft 365 for business にサインインし、OneDrive for Business をセットアップしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="176d2-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="176d2-111">これを行うには、[Office.com][](https://office.com)に移動し、ビジネス向け Microsoft 365 の資格情報でサインインし、[OneDrive] を選択します。</span><span class="sxs-lookup"><span data-stu-id="176d2-111">To do this, go to [office.com](https://office.com), sign in with your Microsoft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="176d2-112">演習</span><span class="sxs-lookup"><span data-stu-id="176d2-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="176d2-113">Mover をインストールする</span><span class="sxs-lookup"><span data-stu-id="176d2-113">Install Mover</span></span>

1. <span data-ttu-id="176d2-114">Google Workspace 管理コンソールにサインインするには、 [次の](https://admin.google.com)admin.google.com。</span><span class="sxs-lookup"><span data-stu-id="176d2-114">Sign in to your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="176d2-115">Choose **Apps**  >  **Google Workspace Marketplace apps** Add app to Domain Install  >  **list**.</span><span class="sxs-lookup"><span data-stu-id="176d2-115">Choose **Apps** > **Google Workspace Marketplace apps** > **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="176d2-116">Mover を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="176d2-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="176d2-117">Choose **Domain Install,** then **Continue**.</span><span class="sxs-lookup"><span data-stu-id="176d2-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="176d2-118">アクセス許可を確認し、条件に同意するチェック ボックスをオンにして、[許可] を選択し、[次へ]、次に **[完了**] の順に選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="176d2-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="176d2-119">コネクタを作成して移行を実行する</span><span class="sxs-lookup"><span data-stu-id="176d2-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="176d2-120">Google **Workspace Marketplace アプリに戻ります**。</span><span class="sxs-lookup"><span data-stu-id="176d2-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="176d2-121">ブラウザーを更新し **、Mover アプリを選択** します。</span><span class="sxs-lookup"><span data-stu-id="176d2-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="176d2-122">下にスクロールして、ユニバーサル ナビゲーション リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="176d2-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="176d2-123">[ **新しいコネクタの承認] を** 選択し **、[G Suite (管理者)**] を見つけて 、[承認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="176d2-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="176d2-124">必要に応 **じ、表示名** を変更し、[承認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="176d2-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="176d2-125">Google 管理者アカウントを選択し、アクセス許可を確認して、[許可] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="176d2-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="176d2-126">Mover には、検出されたチーム ドライブとユーザー ドライブの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="176d2-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="176d2-127">[ **宛先の選択] で**、[ **新しいコネクタ** の承認] を選択し、[Office **365]** を見つけて、[承認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="176d2-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="176d2-128">Azure Active Directory で Mover アプリにアクセス許可を付与するには、次の操作[aka.ms/Office365MoverAuth。](https://aka.ms/Office365MoverAuth)</span><span class="sxs-lookup"><span data-stu-id="176d2-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="176d2-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span><span class="sxs-lookup"><span data-stu-id="176d2-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="176d2-130">アカウントを選択し、アクセス許可を確認して、[承諾] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="176d2-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="176d2-131">[プロパティ **] を** 選択し、[ユーザーの割 **り当てが必要か]** がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="176d2-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="176d2-132">Mover アプリに戻り、表示名を変更します (必要な場合は、[**承認**] を選択し、Microsoft 管理者アカウントを選択します)。</span><span class="sxs-lookup"><span data-stu-id="176d2-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="176d2-133">Mover は、SharePoint Online (または SPO) サイトの数と検出されたユーザーについて通知します。</span><span class="sxs-lookup"><span data-stu-id="176d2-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="176d2-134">Choose **Continue Migration Setup,** select **Add Users,** then **Automatically Discover and Add Users**.</span><span class="sxs-lookup"><span data-stu-id="176d2-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="176d2-135">Mover アプリは、Google のソース パスから Microsoft 365 の宛先パスにドライブをマップします。</span><span class="sxs-lookup"><span data-stu-id="176d2-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="176d2-136">ドライブが自動的にマップしない場合は、そのドライブの保存先パスを CSV ファイルに追加します。これは後で共有ドライブを SharePoint ドキュメント ライブラリに移行するために使用します。</span><span class="sxs-lookup"><span data-stu-id="176d2-136">If a drive doesn't map automatically, add its destination path to a CSV file, which we'll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="176d2-137">この例では、Migrated ファイルという SharePoint サイトを追加し、ドキュメント ページの URL をメモしています。</span><span class="sxs-lookup"><span data-stu-id="176d2-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="176d2-138">次に、ソース パス、宛先パス、タグの形式を使用して CSV ファイルを作成しました。</span><span class="sxs-lookup"><span data-stu-id="176d2-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="176d2-139">詳細については、以下を[aka.ms/movercsv。](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv)</span><span class="sxs-lookup"><span data-stu-id="176d2-139">For details see [aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="176d2-140">宛先パスの URL を追加する場合は、共有ドキュメントの後にあるすべてを削除します。</span><span class="sxs-lookup"><span data-stu-id="176d2-140">When adding the Destination Path URL, remove everything after Shared Documents.</span></span> <span data-ttu-id="176d2-141">たとえば、次の完全な URL はエラーを発生します。`https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="176d2-141">For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="176d2-142">次のように変更してください。`https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="176d2-142">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="176d2-143">CSV ファイルの準備ができたら、[移行操作] 、[移行 **に追加]**、アップロード **するファイルの選択を選択します**。</span><span class="sxs-lookup"><span data-stu-id="176d2-143">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="176d2-144">CSV ファイルに移動して選択し、[開く] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="176d2-144">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="176d2-145">ファイルを移行するユーザー ドライブを選択し、[ユーザーの移行の開始] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="176d2-145">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="176d2-146">移行情報を確認し、移行を開始する時間を選択し、使用条件に同意して、[続行] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="176d2-146">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="176d2-147">移行プロセスが完了すると、Mover アプリから通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="176d2-147">The Mover app will inform you when the migration process is complete.</span></span>
