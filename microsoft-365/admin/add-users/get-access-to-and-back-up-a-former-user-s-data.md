---
title: 元ユーザーのデータにアクセスしてバックアップを作成する
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
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: ユーザーが組織を離れたときに、従業員のファイルと電子メールを保存する方法について説明します。
ms.openlocfilehash: 92e863e3b849f6a89e6d67d805fdb5024879999f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241632"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="0d73c-103">元ユーザーのデータにアクセスしてバックアップを作成する</span><span class="sxs-lookup"><span data-stu-id="0d73c-103">Get access to and back up a former user's data</span></span>


<span data-ttu-id="0d73c-104">従業員が組織を離れる場合は、データ (ドキュメントと電子メール) にアクセスして、それを確認し、バックアップするか、新しい従業員に提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d73c-104">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="0d73c-105">以前のユーザーの OneDrive ドキュメントにアクセスする</span><span class="sxs-lookup"><span data-stu-id="0d73c-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="0d73c-106">ユーザーのライセンスを削除してもアカウントを削除しない場合は、ユーザーの OneDrive のコンテンツにアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="0d73c-107">ユーザーのアカウントを削除した場合、既定では30日間で、以前のユーザーの OneDrive データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-107">If you delete the user's account, you have 30 days by default to access the former user’s OneDrive data.</span></span> <span data-ttu-id="0d73c-108">[削除されたユーザーの OneDrive の保持を設定する方法について説明](/onedrive/set-retention)します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="0d73c-109">この時間内に[ユーザーアカウントを復元](/office365/admin/add-users/restore-user)しない場合は、その OneDrive コンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="0d73c-110">以前のユーザーの OneDrive ファイルを保持するには、まず自分の OneDrive にアクセスして、保存するファイルを移動します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="0d73c-111">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-111">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="0d73c-112">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="0d73c-113">ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-113">Select a user.</span></span>

3. <span data-ttu-id="0d73c-114">右側のウィンドウで、[ **OneDrive**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-114">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="0d73c-115">[**ファイルへのアクセスを取得**] で、[**ファイルへのリンクの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-115">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="0d73c-116">リンクを選択して、ファイルの場所を開きます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-116">Select the link to open the file location.</span></span> <span data-ttu-id="0d73c-117">ファイルをコンピューターにダウンロードするか、[**移動**] または [**コピー** ] を選択して、自分の OneDrive または共有ライブラリにファイルを移動またはコピーします。</span><span class="sxs-lookup"><span data-stu-id="0d73c-117">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="0d73c-118">一度に 500 MB のファイルとフォルダーを移動またはコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-118">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="0d73c-119">バージョン履歴があるドキュメントを移動またはコピーすると、最新バージョンのみが移動されます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-119">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0d73c-120">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="0d73c-121">ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-121">Select a user.</span></span>

3. <span data-ttu-id="0d73c-122">右側のウィンドウで、[ **OneDrive の設定**] を展開し、[**アクセス**] の横にある [ **access ファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-122">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="0d73c-123">リンクを選択して、ファイルの場所を開きます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-123">Select the link to open the file location.</span></span> <span data-ttu-id="0d73c-124">ファイルをコンピューターにダウンロードするか、[**移動**] または [**コピー** ] を選択して、自分の OneDrive または共有ライブラリにファイルを移動またはコピーします。</span><span class="sxs-lookup"><span data-stu-id="0d73c-124">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="0d73c-125">一度に 500 MB のファイルとフォルダーを移動またはコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-125">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="0d73c-126">バージョン履歴があるドキュメントを移動またはコピーすると、最新バージョンのみが移動されます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-126">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0d73c-127">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="0d73c-128">ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-128">Select a user.</span></span>

3. <span data-ttu-id="0d73c-129">右側のウィンドウで、[ **OneDrive の設定**] を展開し、[**アクセス**] の横にある [ **access ファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-129">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="0d73c-130">リンクを選択して、ファイルの場所を開きます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-130">Select the link to open the file location.</span></span> <span data-ttu-id="0d73c-131">ファイルをコンピューターにダウンロードするか、[**移動**] または [**コピー** ] を選択して、自分の OneDrive または共有ライブラリにファイルを移動またはコピーします。</span><span class="sxs-lookup"><span data-stu-id="0d73c-131">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="0d73c-132">一度に 500 MB のファイルとフォルダーを移動またはコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-132">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="0d73c-133">バージョン履歴があるドキュメントを移動またはコピーすると、最新バージョンのみが移動されます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-133">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="0d73c-134">ユーザーの OneDrive への管理者アクセスを無効にする</span><span class="sxs-lookup"><span data-stu-id="0d73c-134">Revoke admin access to a user’s OneDrive</span></span>

<span data-ttu-id="0d73c-135">グローバル管理者は、ユーザーの OneDrive のコンテンツにアクセスできるようにすることができますが、不要になった場合はアクセスを削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d73c-135">As global admin, you can give yourself access to the content in a user’s OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0d73c-136">グローバル管理者または SharePoint 管理者として、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0d73c-136">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>  as a global admin or SharePoint admin.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0d73c-137">グローバル管理者または SharePoint 管理者として、<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0d73c-137">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>  as a global admin or SharePoint admin.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0d73c-138">グローバル管理者または SharePoint 管理者として、<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0d73c-138">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>  as a global admin or SharePoint admin.</span></span>

::: moniker-end

   <span data-ttu-id="0d73c-139">管理センターにアクセスするためのアクセス許可がないことを示すメッセージが表示された場合は、組織の管理者のアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="0d73c-139">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

2. <span data-ttu-id="0d73c-140">左側のウィンドウで、[**管理センター**] \> [**SharePoint**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-140">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="0d73c-141">(場合によっては、管理センターのリストを表示するために **[すべて表示]** を選択する必要があります。)</span><span class="sxs-lookup"><span data-stu-id="0d73c-141">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="0d73c-142">従来の SharePoint 管理センターが表示された場合は、ページ上部の [**今すぐ起動する**] を選択します。これにより、新しい SharePoint 管理センターが開きます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-142">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

4. <span data-ttu-id="0d73c-143">左側のウィンドウで、[**その他の機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-143">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="0d73c-144">[**ユーザープロファイル**] で、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-144">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="0d73c-145">[**人**] で、[**ユーザープロファイルの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-145">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="0d73c-146">ユーザーの名前を入力し、[**検索**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-146">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="0d73c-147">ユーザーを右クリックし、[**サイトコレクションの所有者の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-147">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="0d73c-148">ユーザーのデータへのアクセスが不要になったユーザーを削除し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-148">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="0d73c-149">以前のユーザーの Outlook データにアクセスする</span><span class="sxs-lookup"><span data-stu-id="0d73c-149">Access the Outlook data of a former user</span></span>

<span data-ttu-id="0d73c-150">元従業員のメール メッセージ、予定表、タスク、連絡先を保存するには、情報を Outlook データ ファイル (.pst) にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="0d73c-150">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="0d73c-151">Outlook に [元従業員のメールを追加](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx)します ([ユーザーのパスワードの再設定](reset-passwords.md)を行えば、自分しか知らないパスワードに設定し直すことができます)。</span><span class="sxs-lookup"><span data-stu-id="0d73c-151">[Add the former employee's email](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="0d73c-152">Outlook で、[**ファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-152">In Outlook, select **File**.</span></span>
    
    ![Outlook 2016 のリボンの外観。](../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="0d73c-154">[\*\*エクスポート&amp; \*\* \> **インポート/エクスポート**を開く] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-154">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Backstage ビューの [インポート/エクスポート]](../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="0d73c-156">[**ファイルへエクスポート**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-156">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![インポート/エクスポート ウィンドウの [ファイルへエクスポート] オプション](../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="0d73c-158">[ **Outlook データファイル (.pst)**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-158">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="0d73c-159">[メールボックス-Ayano Weiler] や [anne@contoso.com] などの名前または電子メールアドレスを選択して、エクスポートするアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-159">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="0d73c-160">アカウントのすべての内容 (メール、予定表、連絡先、タスク、メモなど) をエクスポートする場合、[ **サブフォルダーを含む**] チェック ボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-160">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0d73c-p108">一度にエクスポートできるアカウントは 1 つだけです。複数のアカウントをエクスポートする場合は、アカウントがエクスポートされるたびに、上の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-p108">You can export one account at a time. If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![一番上のフォルダーが選択され、[サブフォルダーを含む] がオンになった [Outlook データ ファイルのエクスポート] ダイアログ ボックス](../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="0d73c-164">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-164">Select **Next**.</span></span>
    
8. <span data-ttu-id="0d73c-165">[**参照**] を選択して、Outlook データファイル (.pst) の保存場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-165">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="0d73c-166">*ファイル名*を入力し、[ **OK** ] を選択して続行します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-166">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0d73c-167">If you've used export before, the previous folder location and file name appear.</span><span class="sxs-lookup"><span data-stu-id="0d73c-167">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="0d73c-168">別の*ファイル名*を入力してから、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-168">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="0d73c-169">既存の Outlook データ ファイル (.pst) にエクスポートする場合は、[ **オプション**] で、ファイルに既に存在しているアイテムをエクスポートするときの処理を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-169">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="0d73c-170">**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-170">Select **Finish**.</span></span>
    
<span data-ttu-id="0d73c-171">Outlook により、エクスポートがすぐに開始されます。ただし、新しい Outlook データ ファイル (.pst) を作成するか、パスワードで保護されたファイルを使う場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-171">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="0d73c-172">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span><span class="sxs-lookup"><span data-stu-id="0d73c-172">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="0d73c-173">[ **Outlook データファイルの作成**] ダイアログボックスが表示されたら、 **[パスワード] ボックスと [** パスワードの**確認**] ボックスに*パスワード*を入力し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-173">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="0d73c-174">[ **Outlook データファイルのパスワード**] ダイアログボックスで、*パスワード*を入力し、[ **OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-174">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="0d73c-175">パスワードで保護された既存の Outlook データファイル (.pst) にエクスポートする場合は、[ **Outlook データファイルのパスワード**] ダイアログボックスで、*パスワード*を入力し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-175">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="0d73c-176">Outlook 2010 で、[電子メール、連絡先、予定表を outlook の .pst ファイルにエクスポートまたはバックアップ](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx)する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d73c-176">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) in Outlook 2010.</span></span> 
  
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="0d73c-177">元のユーザーの電子メールに別のユーザーがアクセスできるようにする</span><span class="sxs-lookup"><span data-stu-id="0d73c-177">Give another user access to a former user's email</span></span> 

<span data-ttu-id="0d73c-178">元従業員の電子メールメッセージ、予定表、タスク、および連絡先に別の従業員へのアクセス権を付与するには、別の従業員の Outlook 受信トレイに情報をインポートします。</span><span class="sxs-lookup"><span data-stu-id="0d73c-178">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="0d73c-179">また[、以前のユーザーのメールボックスを共有メールボックスに変換](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox)したり、元[従業員の電子メールを別の従業員に転送](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-179">You can also [convert the former user's mailbox to a shared mailbox](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="0d73c-180">Outlook で、[**ファイル** \> ] [エクスポート\>の**インポート/エクスポート**] を\*\*開き&amp; \*\*ます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-180">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="0d73c-181">これにより、インポート/エクスポート ウィザードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-181">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="0d73c-182">[**別のプログラムまたはファイルからのインポート**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-182">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![インポート/エクスポート ウィザード](../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="0d73c-184">[ **Outlook データファイル (.pst)**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-184">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="0d73c-185">インポートする .pst ファイルを探して選びます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-185">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="0d73c-186">[ **オプション**] で、重複するアイテムの処理方法を選びます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-186">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="0d73c-187">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-187">Select **Next**.</span></span>
    
7. <span data-ttu-id="0d73c-188">Outlook データファイル (.pst) にパスワードが割り当てられている場合は、パスワードを入力し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-188">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="0d73c-189">アイテムのインポートに関するオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-189">Set the options for importing items.</span></span> <span data-ttu-id="0d73c-190">通常、既定の設定を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0d73c-190">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="0d73c-191">**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d73c-191">Select **Finish**.</span></span>
    
> [!TIP]
> <span data-ttu-id="0d73c-192">Outlook データファイル (.pst) から少数のアイテムのみをインポートまたは復元する場合は、Outlook データファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="0d73c-192">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="0d73c-193">次に、ナビゲーションウィンドウで、Outlook データファイルフォルダーから既存の Outlook フォルダーにアイテムをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="0d73c-193">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="0d73c-194">関連記事</span><span class="sxs-lookup"><span data-stu-id="0d73c-194">Related articles</span></span>
[<span data-ttu-id="0d73c-195">Office 365 から元従業員を削除する</span><span class="sxs-lookup"><span data-stu-id="0d73c-195">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="0d73c-196">OneDrive アカウントの管理者を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="0d73c-196">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="0d73c-197">削除された OneDrive を復元する</span><span class="sxs-lookup"><span data-stu-id="0d73c-197">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="0d73c-198">OneDrive の保持と削除</span><span class="sxs-lookup"><span data-stu-id="0d73c-198">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
  

