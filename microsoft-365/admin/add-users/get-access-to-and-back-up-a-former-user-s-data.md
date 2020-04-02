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
description: 従業員が辞職したときに、そのファイルやメールを保存する方法について説明します。
ms.openlocfilehash: 2b608b51060e746d0b69fd887882b51735578496
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2020
ms.locfileid: "43105761"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="e7ef0-103">元ユーザーのデータにアクセスしてバックアップを作成する</span><span class="sxs-lookup"><span data-stu-id="e7ef0-103">Get access to and back up a former user's data</span></span>


<span data-ttu-id="e7ef0-104">従業員が組織を離れた場合、該当者のデータ (ドキュメントやメール) にアクセスして、その内容の検証、バックアップの作成、または新しい従業員に渡すことが必要になるのではないでしょうか。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-104">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="e7ef0-105">元のユーザーの OneDrive ドキュメントにアクセスする</span><span class="sxs-lookup"><span data-stu-id="e7ef0-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="e7ef0-106">ユーザーのライセンスを削除し、アカウントを削除しない場合、ユーザーの OneDrive のコンテンツへのアクセス権を自分に与えることができます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="e7ef0-107">ユーザーのアカウントを削除した場合、元のユーザーの OneDrive データにアクセスするための既定の期間は 30 日です。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-107">If you delete the user's account, you have 30 days by default to access the former user’s OneDrive data.</span></span> <span data-ttu-id="e7ef0-108">[削除されたユーザーに OneDrive の保持を設定する方法を学習します](/onedrive/set-retention)。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="e7ef0-109">この時間内に[ユーザー アカウントを復元](/office365/admin/add-users/restore-user)しない場合、OneDrive コンテンツは削除されます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="e7ef0-110">元のユーザーの OneDrive ファイルを保存するには、まず自分の OneDrive にアクセスしてから、保持するファイルを移動します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e7ef0-111">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-111">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="e7ef0-112">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="e7ef0-113">ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-113">Select a user.</span></span>

3. <span data-ttu-id="e7ef0-114">右側のウィンドウで、[**OneDrive**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-114">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="e7ef0-115">[**ファイルへのアクセス**] で、[**ファイルへのリンクの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-115">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="e7ef0-116">リンクを選択してファイルの場所を開きます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-116">Select the link to open the file location.</span></span> <span data-ttu-id="e7ef0-117">ファイルをコンピューターにダウンロードするか、[**移動先**] または [**指定の場所にコピー**] を選択して、自分の OneDrive または共有ライブラリに移動またはコピーします。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-117">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="e7ef0-118">一度に最大 500 MB のファイルとフォルダーを移動またはコピーできます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-118">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="e7ef0-119">バージョン履歴のあるドキュメントを移動またはコピーすると、最新バージョンのみ移動されます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-119">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e7ef0-120">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="e7ef0-121">ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-121">Select a user.</span></span>

3. <span data-ttu-id="e7ef0-122">右側のウィンドウで [**OneDrive の設定**] を展開し、[**アクセス]** の横にある [\*\* ファイルにアクセスする\*\*] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-122">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="e7ef0-123">リンクを選択してファイルの場所を開きます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-123">Select the link to open the file location.</span></span> <span data-ttu-id="e7ef0-124">ファイルをコンピューターにダウンロードするか、[**移動先**] または [**指定の場所にコピー**] を選択して、自分の OneDrive または共有ライブラリに移動またはコピーします。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-124">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="e7ef0-125">一度に最大 500 MB のファイルとフォルダーを移動またはコピーできます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-125">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="e7ef0-126">バージョン履歴のあるドキュメントを移動またはコピーすると、最新バージョンのみ移動されます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-126">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e7ef0-127">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="e7ef0-128">ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-128">Select a user.</span></span>

3. <span data-ttu-id="e7ef0-129">右側のウィンドウで [**OneDrive の設定**] を展開し、[**アクセス]** の横にある [\*\* ファイルにアクセスする\*\*] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-129">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="e7ef0-130">リンクを選択してファイルの場所を開きます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-130">Select the link to open the file location.</span></span> <span data-ttu-id="e7ef0-131">ファイルをコンピューターにダウンロードするか、[**移動先**] または [**指定の場所にコピー**] を選択して、自分の OneDrive または共有ライブラリに移動またはコピーします。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-131">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="e7ef0-132">一度に最大 500 MB のファイルとフォルダーを移動またはコピーできます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-132">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="e7ef0-133">バージョン履歴のあるドキュメントを移動またはコピーすると、最新バージョンのみ移動されます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-133">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="e7ef0-134">ユーザーの OneDrive への管理者アクセスを無効にする</span><span class="sxs-lookup"><span data-stu-id="e7ef0-134">Revoke admin access to a user’s OneDrive</span></span>

<span data-ttu-id="e7ef0-135">全体管理者は、ユーザーの OneDrive コンテンツへのアクセス権を自分に与えることができますが、必要がなくなったらアクセス権を削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-135">As global admin, you can give yourself access to the content in a user’s OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e7ef0-136">グローバル管理者または SharePoint 管理者として、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-136">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span> 

    <span data-ttu-id="e7ef0-137">管理者センターにアクセスする権限がないというメッセージが表示される場合は、組織には管理者権限がありません。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-137">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e7ef0-138">グローバル管理者または SharePoint 管理者として、<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-138">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="e7ef0-139">管理者センターにアクセスする権限がないというメッセージが表示される場合は、組織には管理者権限がありません。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-139">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e7ef0-140">グローバル管理者または SharePoint 管理者として、<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-140">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="e7ef0-141">管理者センターにアクセスする権限がないというメッセージが表示される場合は、組織には管理者権限がありません。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-141">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

2. <span data-ttu-id="e7ef0-142">左側のウィンドウで、[**管理センター**] \> [**SharePoint**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-142">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="e7ef0-143">(場合によっては、管理センターのリストを表示するために **[すべて表示]** を選択する必要があります。)</span><span class="sxs-lookup"><span data-stu-id="e7ef0-143">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="e7ef0-144">従来の SharePoint 管理センターが表示された場合は、ページ上部の [**今すぐ起動する**] を選択します。これにより、新しい SharePoint 管理センターが開きます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-144">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

4. <span data-ttu-id="e7ef0-145">ウィンドウの左側で [**その他の機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-145">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="e7ef0-146">[**ユーザー プロファイル**] で、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-146">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="e7ef0-147">[**人**] の [**ユーザー プロファイルの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-147">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="e7ef0-148">ユーザーの名前を入力し、[**検索**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-148">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="e7ef0-149">ユーザーを右クリックし、[**サイト コレクションの所有者の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-149">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="e7ef0-150">ユーザーのデータへのアクセスが不要になったユーザーを削除し、[\*\*O \*\*] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-150">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="e7ef0-151">元のユーザーの Outlook データにアクセスする</span><span class="sxs-lookup"><span data-stu-id="e7ef0-151">Access the Outlook data of a former user</span></span>

<span data-ttu-id="e7ef0-152">元従業員のメール メッセージ、予定表、タスク、連絡先を保存するには、情報を Outlook データ ファイル (.pst) にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-152">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="e7ef0-153">Outlook に [元従業員のメールを追加](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx)します ([ユーザーのパスワードの再設定](reset-passwords.md)を行えば、自分しか知らないパスワードに設定し直すことができます)。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-153">[Add the former employee's email](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="e7ef0-154">Outlook で、[**ファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-154">In Outlook, select **File**.</span></span>
    
    ![これは、Outlook 2016 のリボンの外観です。](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="e7ef0-156">[**開く&amp;エクスポート**]\>[**インポート/エクスポート**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-156">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Backstage ビューの [インポート/エクスポート]](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="e7ef0-158">[**ファイルのエクスポート]** を選んで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-158">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![インポート/エクスポート ウィンドウの [ファイルのエクスポート] オプション](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="e7ef0-160">[**Outlook データ ファイル (.pst)**] を選択して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-160">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="e7ef0-161">Mailbox-Anne Weiler または anne@contoso.com などの名前またはメール アドレスを選択して、エクスポートするアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-161">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="e7ef0-162">アカウントのすべての内容 (メール、予定表、連絡先、タスク、メモなど) をエクスポートする場合、[ **サブフォルダーを含む**] チェック ボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-162">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e7ef0-p108">一度にエクスポートできるアカウントは 1 つだけです。複数のアカウントをエクスポートする場合は、アカウントがエクスポートされるたびに、上の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-p108">You can export one account at a time. If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![一番上のフォルダーが選択され、[サブフォルダーを含む] がオンになっている [Outlook データ ファイルのエクスポート] ダイアログ ボックス](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="e7ef0-166">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-166">Select **Next**.</span></span>
    
8. <span data-ttu-id="e7ef0-167">[**参照**] を選択して、Outlook データ ファイル (.pst) の保存場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-167">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="e7ef0-168">*ファイル名*を入力して [**OK**] を選択し、続行します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-168">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e7ef0-169">以前にエクスポートしたことがある場合は、そのときのフォルダーの場所とファイル名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-169">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="e7ef0-170">*別のファイル名*を入力し、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-170">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="e7ef0-171">既存の Outlook データ ファイル (.pst) にエクスポートする場合は、[**オプション**] で、ファイルに既に存在しているアイテムをエクスポートするときの処理を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-171">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="e7ef0-172">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-172">Select **Finish**.</span></span>
    
<span data-ttu-id="e7ef0-173">Outlook により、エクスポートがすぐに開始されます。ただし、新しい Outlook データ ファイル (.pst) を作成するか、パスワードで保護されたファイルを使う場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-173">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="e7ef0-174">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span><span class="sxs-lookup"><span data-stu-id="e7ef0-174">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="e7ef0-175">[**Outlook データ ファイルの作成**] ダイアログ ボックスが表示されたら、[**パスワード**] ボックスと [**パスワードの確認**] ボックスに*パスワード*を入力し、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-175">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="e7ef0-176">[**Outlook データ ファイルのパスワード**] ダイアログ ボックスで*パスワード*を入力し、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-176">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="e7ef0-177">パスワードで保護された既存の Outlook データ ファイル (.pst) にエクスポートする場合は、[**Outlook データ ファイルのパスワード**] ダイアログボックスで、*パスワード*を入力して [**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-177">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="e7ef0-178">Outlook 2010で「[メール、連絡先、予定表を Outlook の .pst ファイルにエクスポートまたはバックアップする](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx)」方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-178">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="e7ef0-179">既定では、メールは12か月の間オフラインで利用できます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-179">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="e7ef0-180">必要に応じて、「[オフラインで利用可能なデータを増やす](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-180">If required, see how to [increase the data available offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="e7ef0-181">元のユーザーのメールへのアクセス権を別のユーザーに付与する</span><span class="sxs-lookup"><span data-stu-id="e7ef0-181">Give another user access to a former user's email</span></span> 

<span data-ttu-id="e7ef0-182">元従業員のメール メッセージ、予定表、タスク、連絡先に他の従業員がアクセスできるようにするには、情報を他の従業員の Outlook 受信トレイにインポートします。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-182">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="e7ef0-183">[元のユーザーのメールボックスを共有メールボックスに変換](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox)、または[前の従業員のメールを別の従業員に転送](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)することもできます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-183">You can also [convert the former user's mailbox to a shared mailbox](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="e7ef0-184">Outlook で [**ファイル**]\>[**開く&amp;エクスポート**]\>[**インポート/エクスポート**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-184">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="e7ef0-185">これにより、インポート/エクスポート ウィザードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-185">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="e7ef0-186">[**他のプログラムまたはファイルからのインポート**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-186">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![インポート/エクスポート ウィザード](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="e7ef0-188">[**Outlook データ ファイル (.pst)**] を選んで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-188">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="e7ef0-189">インポートする .pst ファイルを探して選びます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-189">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="e7ef0-190">[**オプション**] で、重複するアイテムの処理方法を選びます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-190">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="e7ef0-191">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-191">Select **Next**.</span></span>
    
7. <span data-ttu-id="e7ef0-192">Outlook データ ファイル (.pst) にパスワードが割り当てられていた場合は、パスワードを入力し、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-192">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="e7ef0-193">アイテムのインポートに関するオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-193">Set the options for importing items.</span></span> <span data-ttu-id="e7ef0-194">通常、既定の設定を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-194">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="e7ef0-195">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-195">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="e7ef0-196">既存のユーザーの OneDrive および電子メールデータにアクセスする場合、手順は変わりません。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-196">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="e7ef0-197">Outlook データ ファイル (.pst) からいくつかのアイテムのみをインポートまたは復元する場合は、Outlook データ ファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-197">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="e7ef0-198">次に、ナビゲーション ウィンドウで、Outlook データ ファイル フォルダーから既存の Outlook フォルダーにアイテムをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="e7ef0-198">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="e7ef0-199">関連記事</span><span class="sxs-lookup"><span data-stu-id="e7ef0-199">Related articles</span></span>
[<span data-ttu-id="e7ef0-200">Office 365 から元従業員を削除する</span><span class="sxs-lookup"><span data-stu-id="e7ef0-200">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="e7ef0-201">OneDrive アカウントで管理者を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="e7ef0-201">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="e7ef0-202">削除された OneDrive を復元する</span><span class="sxs-lookup"><span data-stu-id="e7ef0-202">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="e7ef0-203">OneDrive の保持と削除</span><span class="sxs-lookup"><span data-stu-id="e7ef0-203">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
  
