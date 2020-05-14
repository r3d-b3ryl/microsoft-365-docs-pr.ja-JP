---
title: グループを作成できるユーザーを管理する
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
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
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Microsoft 365 グループを作成できるユーザーを制御する方法について説明します。
ms.openlocfilehash: 7a699a01687aec47fd39ce108c5a8c7a888afe65
ms.sourcegitcommit: 98782ee4497d72232462c51a3071fae313282980
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44222385"
---
# <a name="manage-who-can-create-groups"></a><span data-ttu-id="9fcbc-103">グループを作成できるユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="9fcbc-103">Manage who can create Groups</span></span>

  
<span data-ttu-id="9fcbc-104">ユーザーは、Microsoft 365 グループを作成するのが簡単なので、他のユーザーに代わってそれらを作成するための要求は殺到しません。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-104">Because it's so easy for users to create Microsoft 365 groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="9fcbc-105">ただし、業務によっては、グループを作成できるユーザーを制御したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="9fcbc-106">この記事では、次のようなグループを使用するすべての Microsoft 365 サービスでグループを作成する機能を無効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-106">This article explains how to disable the ability to create groups in all Microsoft 365 services that use groups, including:</span></span>
  
- <span data-ttu-id="9fcbc-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="9fcbc-107">Outlook</span></span>
    
- <span data-ttu-id="9fcbc-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="9fcbc-108">SharePoint</span></span>
    
- <span data-ttu-id="9fcbc-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="9fcbc-109">Yammer</span></span>
    
- <span data-ttu-id="9fcbc-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9fcbc-110">Microsoft Teams</span></span>

- <span data-ttu-id="9fcbc-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="9fcbc-111">Microsoft Stream</span></span>
    
- <span data-ttu-id="9fcbc-112">StaffHub</span><span class="sxs-lookup"><span data-stu-id="9fcbc-112">StaffHub</span></span>
    
- <span data-ttu-id="9fcbc-113">Planner</span><span class="sxs-lookup"><span data-stu-id="9fcbc-113">Planner</span></span>
    
- <span data-ttu-id="9fcbc-114">PowerBI</span><span class="sxs-lookup"><span data-stu-id="9fcbc-114">PowerBI</span></span>

- <span data-ttu-id="9fcbc-115">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="9fcbc-115">Roadmap</span></span>
    
<span data-ttu-id="9fcbc-116">Microsoft 365 グループの作成を特定のセキュリティグループのメンバーに制限できます。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-116">You can restrict Microsoft 365 group creation to the members of a particular security group.</span></span> <span data-ttu-id="9fcbc-117">制限するには、Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="9fcbc-118">この記事では、必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="9fcbc-119">この記事の手順を実行しても、特定の役割のメンバーがグループを作成できなくなることはありません。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="9fcbc-120">グローバル管理者は、Microsoft 365 管理センター、Planner、Teams、Exchange、SharePoint Online などの任意の方法でグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-120">Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="9fcbc-121">他の役割は、以下のような制限付きの方法でグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="9fcbc-122">Exchange 管理者: Exchange 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="9fcbc-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="9fcbc-123">パートナー レベル 1 のサポート: Microsoft 365 管理センター、Exchange 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="9fcbc-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="9fcbc-124">パートナー レベル 2 のサポート: Microsoft 365 管理センター、Exchange 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="9fcbc-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="9fcbc-125">ディレクトリ製作者: Azure AD</span><span class="sxs-lookup"><span data-stu-id="9fcbc-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="9fcbc-126">SharePoint 管理者: SharePoint 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="9fcbc-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="9fcbc-127">Teams サービス管理者: Teams 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="9fcbc-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="9fcbc-128">ユーザー管理の管理者: Microsoft 365 管理センター、Yammer、Azure AD</span><span class="sxs-lookup"><span data-stu-id="9fcbc-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="9fcbc-129">これらの役割のいずれかのメンバーである場合は、制限されたユーザーに対して Microsoft 365 グループを作成し、そのユーザーをグループの所有者として割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-129">If you're a member of one of these roles, you can create Microsoft 365 groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="9fcbc-130">この役割を持つユーザーは、作成を妨げる可能性のある PowerShell 設定に関係なく、Yammer で接続済みグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-130">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="9fcbc-131">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="9fcbc-131">Licensing requirements</span></span>

<span data-ttu-id="9fcbc-132">グループを作成するユーザーを管理するには、以下のユーザーが Azure AD Premium ライセンスまたは Azure AD Basic EDU のライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-132">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="9fcbc-133">これらのグループ作成の設定を管理している管理者</span><span class="sxs-lookup"><span data-stu-id="9fcbc-133">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="9fcbc-134">グループの作成が許可されているセキュリティグループのメンバー</span><span class="sxs-lookup"><span data-stu-id="9fcbc-134">The members of the security group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="9fcbc-135">Azure ライセンスの割り当て方法の詳細については[、「Azure Active Directory ポータルでライセンスを割り当てるまたは削除](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-135">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="9fcbc-136">以下のユーザーは Azure AD Premium ライセンスまたは Azure AD Basic EDU のライセンスが割り当てられている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-136">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="9fcbc-137">Microsoft 365 グループのメンバーであり、他のグループを作成する機能を持たないユーザー。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-137">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="9fcbc-138">手順 1: Microsoft 365 グループを作成する必要があるユーザーのセキュリティグループを作成する</span><span class="sxs-lookup"><span data-stu-id="9fcbc-138">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="9fcbc-139">グループを作成できるユーザーを制御するために使用できる組織内のセキュリティ グループは 1 つです。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-139">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="9fcbc-140">ただし、このグループのメンバーとして、他のセキュリティ グループをネストすることができます。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-140">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="9fcbc-141">たとえば、Allow Group Creation という名前のグループが指定されたセキュリティ グループで、Microsoft Planner Users and Exchange Online Users という名前のグループがそのグループのメンバーであるとします。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-141">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="9fcbc-142">上記の役割の管理者は、このグループのメンバーである必要はなく、グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-142">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9fcbc-143">グループを作成できるユーザーを制限するには、必ず **セキュリティー グループ** を使用してください。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-143">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="9fcbc-144">Microsoft 365 グループを使用しようとしても、メンバーはセキュリティグループをチェックするため、SharePoint からグループを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-144">If you try to use a Microsoft 365 group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="9fcbc-145">管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-145">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="9fcbc-146">[**グループの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-146">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="9fcbc-147">グループの種類として [**セキュリティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-147">Choose **Security** as the group type.</span></span> <span data-ttu-id="9fcbc-148">グループの名前は覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-148">Remember the name of the group!</span></span> <span data-ttu-id="9fcbc-149">後で必要になります。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-149">You'll need it later.</span></span>
  
4. <span data-ttu-id="9fcbc-150">セキュリティグループの設定を終了し、組織内でグループを作成できるユーザーまたは他のセキュリティグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-150">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="9fcbc-151">詳細については、「[Microsoft 365 管理センターでのセキュリティ グループの作成、編集、または削除](../email/create-edit-or-delete-a-security-group.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-151">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="9fcbc-152">手順 2: PowerShell コマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="9fcbc-152">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="9fcbc-153">グループレベルのゲスト アクセス設定を変更するには、[Graph 用 Azure Active Directory PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (モジュール名 **AzureADPreview**) のプレビュー バージョンを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-153">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="9fcbc-154">以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Azure AD モジュールのインストール](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-154">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="9fcbc-155">Azure AD PowerShell モジュール (AzureAD) の 2.0 一般提供バージョンをインストールしている場合には、PowerShell セッションで `Uninstall-Module AzureAD` を実行してアンインストールし、`Install-Module AzureADPreview` を実行してプレビュー バージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-155">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="9fcbc-156">プレビュー バージョンを既にインストールしている場合には、`Install-Module AzureADPreview`を実行しそれがこのモジュールの最新バージョンであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-156">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>



<span data-ttu-id="9fcbc-157">下のスクリプトを、Notepad などのテキスト エディターまたは [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise) にコピーます。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-157">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="9fcbc-158">*\<SecurityGroupName\>* を、作成したセキュリティグループの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-158">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="9fcbc-159">例:</span><span class="sxs-lookup"><span data-stu-id="9fcbc-159">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="9fcbc-160">GroupCreators.ps1 としてファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-160">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="9fcbc-161">PowerShell ウィンドウで、ファイルを保存した場所に移動 します ("CD <FileLocation>" と入力)。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-161">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="9fcbc-162">次のように入力してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-162">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="9fcbc-163">サインインを求められたら、[管理者アカウントでサインイン](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription)します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-163">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -Filter "DisplayName eq '$GroupName'").objectId
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="9fcbc-164">スクリプトの最後の行に、更新された設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-164">The last line of the script will display the updated settings:</span></span>

![完了すると、設定は次のように表示されます。](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="9fcbc-166">使用するセキュリティグループを変更する場合は、新しいセキュリティグループの名前でスクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-166">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="9fcbc-167">グループ作成の制限をオフにして、もう一度すべてのユーザーがグループを作成できるようにするには、$GroupName を "" に、$AllowGroupCreation を "True" に設定して、スクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-167">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="9fcbc-168">手順 4: 動作することを確認する</span><span class="sxs-lookup"><span data-stu-id="9fcbc-168">Step 4: Verify that it works</span></span>

<span data-ttu-id="9fcbc-169">変更が有効になるまでに30分以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-169">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="9fcbc-170">新しい設定を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-170">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="9fcbc-171">グループを作成する権限を持たないユーザーのユーザーアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-171">Sign in with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="9fcbc-172">作成したセキュリティ グループのメンバーまたは管理者ではないユーザーのアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-172">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="9fcbc-173">[**Planner**] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-173">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="9fcbc-174">Planner では、左側のナビゲーションで **[新しいプラン]** を選択してプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-174">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="9fcbc-175">プランとグループの作成が無効になっていることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-175">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="9fcbc-176">セキュリティグループのメンバーと同じ手順をもう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-176">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="9fcbc-177">セキュリティグループのメンバーがグループを作成できない場合は、そのグループが [OWA メールボックス ポリシー](https://go.microsoft.com/fwlink/?linkid=852135) によってブロックされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9fcbc-177">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="9fcbc-178">関連記事</span><span class="sxs-lookup"><span data-stu-id="9fcbc-178">Related articles</span></span>

[<span data-ttu-id="9fcbc-179">Office 365 PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="9fcbc-179">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="9fcbc-180">セルフサービス グループ管理に必要な Azure Active Directory の設定</span><span class="sxs-lookup"><span data-stu-id="9fcbc-180">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="9fcbc-181">ExecutionPolicy の設定</span><span class="sxs-lookup"><span data-stu-id="9fcbc-181">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="9fcbc-182">グループ設定を構成するための Azure Active Directory コマンドレット</span><span class="sxs-lookup"><span data-stu-id="9fcbc-182">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
