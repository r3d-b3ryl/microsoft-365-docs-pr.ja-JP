---
title: 削除済みの Office 365 グループを復元する
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 'Exchange 管理センターを使用して、削除された Office 365 グループを復元する方法について説明します。 '
ms.openlocfilehash: 98eb00d90f5b607a58cd32728ce43cb4a1de1ff5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242594"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="5e1ca-103">削除済みの Office 365 グループを復元する</span><span class="sxs-lookup"><span data-stu-id="5e1ca-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="5e1ca-104">Office 365 グループの所有者である場合は、次の手順に従って自分でグループを復元できます。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-104">If you are the owner of an Office 365 group, you can restore the group yourself by following these steps.</span></span>

1. <span data-ttu-id="5e1ca-105">[[削除さ](https://outlook.office.com/people/group/deleted)れたグループ] ページで、[**グループ**] ノードの下の [**グループの管理**] オプションを選択し、[**削除済み**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-105">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="5e1ca-106">復元するグループの横にある [**復元**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-106">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="5e1ca-107">削除されたグループがここに表示されない場合は、管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-107">If the deleted group doesn't appear here, contact an administrator.</span></span>
  
<span data-ttu-id="5e1ca-108">Office 365 グループの復元を希望するユーザーの場合は、管理者に依頼してこれらの手順を実行するか、ヘルプデスクにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-108">If you're a user who wants to restore an Office 365 group, ask an administrator to do these steps for you or contact your help desk.</span></span>  
   
<span data-ttu-id="5e1ca-109">グループを削除した場合、既定では30日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-109">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="5e1ca-110">この30日の期間は、引き続きグループを復元できるため、"ソフト削除" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-110">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="5e1ca-111">30日後、グループとそれに関連するコンテンツは完全に削除され、復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-111">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>
  
<span data-ttu-id="5e1ca-112">"削除" という期間の間、ユーザーがサイトにアクセスしようとすると、404の_禁止_メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-112">During the "soft-delete" period, if a user tries to access the site they will get a 404 _forbidden_ message.</span></span> <span data-ttu-id="5e1ca-113">この期間が過ぎると、ユーザーがサイトにアクセスしようとすると、404_見つかりません_メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-113">After this period, if a user tries to access the site, they will get a 404 _not found_ message.</span></span>
  
<span data-ttu-id="5e1ca-114">グループを復元すると、次のコンテンツが復元されます。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-114">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="5e1ca-115">Azure Active Directory (AD) Office 365 のグループオブジェクト、プロパティ、およびメンバー。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-115">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="5e1ca-116">グループの電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-116">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="5e1ca-117">Exchange Online の共有の受信トレイと予定表。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-117">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="5e1ca-118">SharePoint Online チームサイトとファイル。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-118">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="5e1ca-119">OneNote ノートブック</span><span class="sxs-lookup"><span data-stu-id="5e1ca-119">OneNote notebook</span></span>
    
- <span data-ttu-id="5e1ca-120">Planner</span><span class="sxs-lookup"><span data-stu-id="5e1ca-120">Planner</span></span>
    
- <span data-ttu-id="5e1ca-121">Teams</span><span class="sxs-lookup"><span data-stu-id="5e1ca-121">Teams</span></span>

- <span data-ttu-id="5e1ca-122">Yammer グループおよびグループコンテンツ (Yammer から Office 365 グループが作成されている場合)</span><span class="sxs-lookup"><span data-stu-id="5e1ca-122">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>
    
<span data-ttu-id="5e1ca-123">コンテンツの保持期限の 30 日間が経過してから完全に削除されるまで待てない場合、[Office 365 グループを完全に削除する](#permanently-delete-an-office-365-group)こともできます。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-123">You can also [Permanently delete an Office 365 group](#permanently-delete-an-office-365-group) if you can't wait the 30 days for the retention period to expire for the content to be permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="5e1ca-124">削除された Office 365 グループの所有者は、グループを復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-124">The owner of the deleted Office 365 group is also able to restore the group.</span></span> <span data-ttu-id="5e1ca-125">管理者権限のない所有者アクセス許可を使用して office 365 グループを復元するには、「 [PowerShell を使用して office 365 グループを復元](#restore-an-office-365-group-using-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-125">To restore an office 365 group using owner permission without administrator permission, see [Restore an Office 365 Group using PowerShell](#restore-an-office-365-group-using-powershell).</span></span>

## <a name="restore-an-office-365-group-using-the-exchange-admin-center"></a><span data-ttu-id="5e1ca-126">Exchange 管理センターを使用して Office 365 グループを復元する</span><span class="sxs-lookup"><span data-stu-id="5e1ca-126">Restore an Office 365 Group using the Exchange admin center</span></span>

<span data-ttu-id="5e1ca-127">Office 365 グローバル管理者のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-127">You must have Office 365 global administrator permissions.</span></span>

1. <span data-ttu-id="5e1ca-128"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-128">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
    
2. <span data-ttu-id="5e1ca-129">Exchange 管理センターで、[ **受信者**]、[ **グループ**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-129">In the Exchange admin center, select **recipients**, and then choose **groups**.</span></span> <span data-ttu-id="5e1ca-130">グループがアクティブであるか、または削除されているかを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-130">You can view whether the group is Active or soft-deleted.</span></span> <span data-ttu-id="5e1ca-131">グループが完全に削除された場合、グループはまったく表示されません。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-131">If the group has been permanently deleted, it won't be listed at all.</span></span>
  
3. <span data-ttu-id="5e1ca-132">グループがソフト削除された正確な時間を表示するには、グループを選択して、右側のウィンドウに情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-132">To view the exact time when the group was soft-deleted, select the group and view the info in the right pane.</span></span>
      
4. <span data-ttu-id="5e1ca-133">復元するグループを選択し、[復元] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-133">Select the group you want to restore, and then select the restore icon.</span></span>
    
    ![復元するグループを選択し、[復元] アイコンを選択します。](../media/restore-group.png)
  
5. <span data-ttu-id="5e1ca-135">[更新] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-135">Select refresh</span></span> ![[更新] アイコン](../media/6464df90-2a91-4c1f-92a6-9a38c7696ac3.gif) <span data-ttu-id="5e1ca-137">を選んで、ページの情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-137">to update the information on the page.</span></span> <span data-ttu-id="5e1ca-138">使用しているグループは、"アクティブ" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-138">Your group will show as Active.</span></span> <span data-ttu-id="5e1ca-139">グループに関連付けられているフォームおよびフォームデータも復元されます。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-139">Any forms and form data associated with your group will also be restored.</span></span>
    
## <a name="restore-an-office-365-group-using-powershell"></a><span data-ttu-id="5e1ca-140">PowerShell を使用して Office 365 グループを復元する</span><span class="sxs-lookup"><span data-stu-id="5e1ca-140">Restore an Office 365 Group using PowerShell</span></span>

<span data-ttu-id="5e1ca-141">Office 365 グローバル管理者のアクセス許可を持っているか、または削除された Office 365 グループの以前の所有者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-141">You must have Office 365 global administrator permissions, or be a former owner of the deleted Office 365 group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e1ca-142">PowerShell で MsolGroup を使用してグループを削除した場合、グループは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-142">If you use Remove-MsolGroup in PowerShell to delete a group, this will delete the group permanently.</span></span> <span data-ttu-id="5e1ca-143">PowerShell を使用してグループを削除する場合は、 **Remove-AzureADMSGroup** を使用して Office 365 グループを論理的に削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-143">When using PowerShell to delete groups, it's best practice to use **Remove-AzureADMSGroup** to soft-delete the Office 365 group.</span></span> <span data-ttu-id="5e1ca-144">そうすれば、必要に応じて、復元することができます。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-144">That way you can restore it if needed.</span></span> 
  
### <a name="install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a><span data-ttu-id="5e1ca-145">Graph 用 Azure Active Directory PowerShell のプレビュー バージョンをインストールする</span><span class="sxs-lookup"><span data-stu-id="5e1ca-145">Install the preview version of the Azure Active Directory PowerShell for Graph</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e1ca-146">同じコンピューターにプレビュー バージョンと GA バージョンの両方を同時にインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-146">You cannot install both the preview and GA versions on the same computer at the same time.</span></span>
  
<span data-ttu-id="5e1ca-147">ベストプラクティスとして、*常に*最新の状態を維持することをお勧めします。つまり、old AzureADPreview または old AzureAD version をアンインストールし、最新のバージョンを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-147">As a best practice, we recommend *always* staying current, i.e. uninstall the old AzureADPreview or old AzureAD version and get the latest one.</span></span> 
  
 
1. <span data-ttu-id="5e1ca-148">検索バーに「Windows PowerShell」と入力します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-148">In your search bar, type Windows PowerShell.</span></span>
    
2. <span data-ttu-id="5e1ca-149">**[Windows PowerShell]** を右クリックし、**[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-149">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span></span>
  
2. <span data-ttu-id="5e1ca-150">インストールされているモジュールを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-150">Review your installed modules:</span></span>
    
  ```
  Get-InstalledModule -Name "AzureAD*"
  ```

3. <span data-ttu-id="5e1ca-151">AzureADPreview または AzureAD の以前のバージョンをアンインストールするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-151">To uninstall a previous version of AzureADPreview or AzureAD, run this command:</span></span>
  
```
   Uninstall-Module AzureADPreview
```

<span data-ttu-id="5e1ca-152">または</span><span class="sxs-lookup"><span data-stu-id="5e1ca-152">or</span></span>
  
```
   Uninstall-Module AzureAD
```

4. <span data-ttu-id="5e1ca-153">AzureADPreview の最新のバージョンをインストールするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-153">To install the latest version of AzureADPreview, run this command:</span></span>
  
```
   Install-Module AzureADPreview
```



<span data-ttu-id="5e1ca-154">信頼されていないリポジトリに関するメッセージに対して「**Y**」と入力します。新しいモジュールのインストールには 1 分ほどかかります。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-154">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.</span></span>
  
### <a name="restore-the-deleted-group"></a><span data-ttu-id="5e1ca-155">削除したグループを復元する</span><span class="sxs-lookup"><span data-stu-id="5e1ca-155">Restore the deleted group</span></span>
  
1. <span data-ttu-id="5e1ca-156">Previoius セクション「Windows PowerShell 用 Azure Active Directory モジュールのプレビューバージョンをインストールする」に記載されているように、 **AzureADPreview**モジュールをインストールしましたか?</span><span class="sxs-lookup"><span data-stu-id="5e1ca-156">Did you install the **AzureADPreview** module, as instructed in the previoius section "Install the preview version of the Azure Active Directory Module for Windows PowerShell"?</span></span>  <span data-ttu-id="5e1ca-157">Not having the most current **preview** version is the #1 reason these steps don't work for people.</span><span class="sxs-lookup"><span data-stu-id="5e1ca-157">Not having the most current **preview** version is the #1 reason these steps don't work for people.</span></span> 
    
2. <span data-ttu-id="5e1ca-158">まだ開いていない場合は、コンピューターで Windows PowerShell ウィンドウを開きます (標準の Windows PowerShell ウィンドウか、[ **管理者として実行**] を選択して開いたウィンドウかは関係ありません)。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-158">If you haven't already, open a Windows PowerShell window on your computer (it doesn't matter if it's a normal Windows PowerShell window, or one you opened by selecting **Run as administrator**).</span></span>
    
3. <span data-ttu-id="5e1ca-159">各コマンドの後に**enter**キーを押して、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-159">Run the following commands by pressing **Enter** after each one:</span></span> 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```



  <span data-ttu-id="5e1ca-160">開いている [**アカウントにサインインする**] 画面に、Azure AD サービスに接続するための管理者アカウントのユーザー名とパスワードを入力し、[**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-160">On the **Sign in to your Account** screen that opens, enter your administrative account user name and password to connect you to your Azure AD service, and select **Sign in**.</span></span>
  
4. <span data-ttu-id="5e1ca-161">次のコマンドを実行して、組織内の回復可能な削除によって削除されたすべての Office 365 グループを、まだ30日の回復可能な削除期間内に表示します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-161">Run this command to display all soft-deleted Office 365 groups in your organization that are still within the 30 day soft-deletion period:</span></span>
    
  ```
  Get-AzureADMSDeletedGroup
  ```

5. <span data-ttu-id="5e1ca-162">復元する 1 つまたは複数のグループのオブジェクト ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-162">Take note of the object ID of the group, or groups, you want to restore.</span></span> <span data-ttu-id="5e1ca-163">このリストに含まれているグループが表示されていない場合は、既に完全に削除されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-163">If you don't see the group you're looking for on this list then it has likely been permanently purged already.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="5e1ca-164">削除したグループと同じエイリアスまたは SMTP アドレスを持つ新しいグループが作成されている場合、削除したグループを復元するには、その新しいグループを事前に削除しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-164">If a new group has been created with the same alias or SMTP address as your deleted group, you will have to delete that new group before you'll be able to restore your deleted group.</span></span> 
  
6. <span data-ttu-id="5e1ca-165">そのグループを復元するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-165">To restore that group, run this command:</span></span>
    
  ```
  Restore-AzureADMSDeletedDirectoryObject -Id <objectId>
  ```

7. <span data-ttu-id="5e1ca-166">通常、この処理には数分しかかかりませんが、ほとんどの場合、完全に復元するまでに24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-166">This process usually takes just a few minutes but in a few rare cases it can take as long as 24 hours to be completely restored.</span></span> <span data-ttu-id="5e1ca-167">グループが正常に復元されたことを確認するには、PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-167">To verify that the group has been successfully restored, run this command in PowerShell:</span></span>
    
  ```
  Get-AzureADGroup -ObjectId <objectId>
  ```

<span data-ttu-id="5e1ca-p110">復元が正常に完了すると、Outlook および Outlook on the web のナビゲーション ウィンドウにグループが再び表示されます。SharePoint や Planner などの復元されたすべてのコンテンツをグループ メンバーが再び利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-p110">Once the restore has successfully completed, the group should reappear on the navigation pane in Outlook and Outlook on the web. All restored content, including SharePoint and Planner, should be available to the group members again.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="5e1ca-170">Office 365 グループを完全に削除する</span><span class="sxs-lookup"><span data-stu-id="5e1ca-170">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="5e1ca-171">場合によっては、30日間のソフト削除期間が経過するのを待たずに、グループを完全に削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-171">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="5e1ca-172">それを行うには、PowerShell を起動し、次のコマンドを実行して、グループのオブジェクト ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-172">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="5e1ca-173">完全に削除するグループまたはグループのオブジェクト ID を書き留めておきます。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-173">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="5e1ca-174">グループを削除すると、グループとそのデータが永久に削除されます。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-174">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="5e1ca-175">グループを削除するには、PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-175">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="5e1ca-p112">グループが正常に削除されたことを確認するには、 *Get AzureADMSDeletedGroup*  コマンドレットをもう一度実行して、グループが論理的に削除されたグループの一覧に表示されなくなったことを確認します。グループとそのすべてのデータが完全に削除されるまで 24 時間ほどかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-p112">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="5e1ca-178">Office 365 についてご質問がある場合</span><span class="sxs-lookup"><span data-stu-id="5e1ca-178">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="5e1ca-179">[Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups)を参照して、Office 365 グループに関する質問を投稿し、会話に参加してください。</span><span class="sxs-lookup"><span data-stu-id="5e1ca-179">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="5e1ca-180">関連記事</span><span class="sxs-lookup"><span data-stu-id="5e1ca-180">Related articles</span></span>

[<span data-ttu-id="5e1ca-181">PowerShell で Office 365 グループを管理する</span><span class="sxs-lookup"><span data-stu-id="5e1ca-181">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="5e1ca-182">Remove-UnifiedGroup コマンドレットを使用してグループを削除する</span><span class="sxs-lookup"><span data-stu-id="5e1ca-182">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="5e1ca-183">グループに接続されたチーム サイトの設定を管理する</span><span class="sxs-lookup"><span data-stu-id="5e1ca-183">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="5e1ca-184">Outlook でグループを削除する</span><span class="sxs-lookup"><span data-stu-id="5e1ca-184">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
