---
title: Microsoft 365 グループを作成できるユーザーを管理する
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Microsoft 365 グループを作成できるユーザーを制御する方法について説明します。
ms.openlocfilehash: 49fdaa98d0b88b306b9fd3d84e52bcf52d9fdf7f
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662714"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="3257a-103">Microsoft 365 グループを作成できるユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="3257a-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="3257a-104">既定では、すべてのユーザーが Microsoft 365 グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3257a-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="3257a-105">これは、ユーザーが支援を必要とせずに共同作業を開始できるため、推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="3257a-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="3257a-106">組織でグループを作成できるユーザーを制限する必要がある場合は、この記事の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="3257a-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="3257a-107">グループを作成できるユーザーを制限すると、次のようなアクセスのためにグループに依存するすべてのサービスに影響します。</span><span class="sxs-lookup"><span data-stu-id="3257a-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="3257a-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="3257a-108">Outlook</span></span>
    
- <span data-ttu-id="3257a-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3257a-109">SharePoint</span></span>
    
- <span data-ttu-id="3257a-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="3257a-110">Yammer</span></span>
    
- <span data-ttu-id="3257a-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3257a-111">Microsoft Teams</span></span>

- <span data-ttu-id="3257a-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="3257a-112">Microsoft Stream</span></span>

- <span data-ttu-id="3257a-113">Planner</span><span class="sxs-lookup"><span data-stu-id="3257a-113">Planner</span></span>
    
- <span data-ttu-id="3257a-114">PowerBI (クラシック)</span><span class="sxs-lookup"><span data-stu-id="3257a-114">PowerBI (classic)</span></span>
    
- <span data-ttu-id="3257a-115">Web/ロードマップのプロジェクト</span><span class="sxs-lookup"><span data-stu-id="3257a-115">Project for the web / Roadmap</span></span>
    
<span data-ttu-id="3257a-116">Microsoft 365 グループの作成を特定のセキュリティグループのメンバーに制限できます。</span><span class="sxs-lookup"><span data-stu-id="3257a-116">You can restrict Microsoft 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="3257a-117">制限するには、Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="3257a-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="3257a-118">この記事では、必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3257a-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="3257a-119">この記事の手順を実行しても、特定の役割のメンバーがグループを作成できなくなることはありません。</span><span class="sxs-lookup"><span data-stu-id="3257a-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="3257a-120">Office 365 のグローバル管理者は、Microsoft 365 管理センター、Planner、Teams、Exchange、SharePoint Online などの方法でグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3257a-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="3257a-121">他の役割は、以下のような制限付きの方法でグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3257a-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="3257a-122">Exchange 管理者: Exchange 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="3257a-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="3257a-123">パートナー レベル 1 のサポート: Microsoft 365 管理センター、Exchange 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="3257a-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="3257a-124">パートナー レベル 2 のサポート: Microsoft 365 管理センター、Exchange 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="3257a-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="3257a-125">ディレクトリ製作者: Azure AD</span><span class="sxs-lookup"><span data-stu-id="3257a-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="3257a-126">SharePoint 管理者: SharePoint 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="3257a-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="3257a-127">Teams サービス管理者: Teams 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="3257a-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="3257a-128">ユーザー管理の管理者: Microsoft 365 管理センター、Yammer、Azure AD</span><span class="sxs-lookup"><span data-stu-id="3257a-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="3257a-129">これらの役割のいずれかのメンバーである場合は、制限されたユーザーに対して Microsoft 365 グループを作成し、そのユーザーをグループの所有者として割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3257a-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="3257a-130">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="3257a-130">Licensing requirements</span></span>

<span data-ttu-id="3257a-131">グループを作成するユーザーを管理するには、次のユーザーに Azure AD Premium ライセンスまたは Azure AD Basic EDU ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3257a-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="3257a-132">これらのグループ作成の設定を管理している管理者</span><span class="sxs-lookup"><span data-stu-id="3257a-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="3257a-133">グループの作成が許可されているセキュリティグループのメンバー</span><span class="sxs-lookup"><span data-stu-id="3257a-133">The members of the security group who are allowed to create groups</span></span>
 
> [!NOTE]
> <span data-ttu-id="3257a-134">Azure ライセンスの割り当て方法の詳細については [、「Azure Active Directory ポータルでライセンスを割り当てるまたは削除](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3257a-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="3257a-135">以下のユーザーは Azure AD Premium ライセンスまたは Azure AD Basic EDU のライセンスが割り当てられている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3257a-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="3257a-136">Microsoft 365 グループのメンバーであり、他のグループを作成する機能を持たないユーザー。</span><span class="sxs-lookup"><span data-stu-id="3257a-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="3257a-137">手順 1: Microsoft 365 グループを作成する必要があるユーザーのセキュリティグループを作成する</span><span class="sxs-lookup"><span data-stu-id="3257a-137">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="3257a-138">グループを作成できるユーザーを制御するために使用できる組織内のセキュリティ グループは 1 つです。</span><span class="sxs-lookup"><span data-stu-id="3257a-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="3257a-139">ただし、このグループのメンバーとして、他のセキュリティ グループをネストすることができます。</span><span class="sxs-lookup"><span data-stu-id="3257a-139">But, you can nest other security groups as members of this group.</span></span>

<span data-ttu-id="3257a-140">上記の役割の管理者は、このグループのメンバーである必要はなく、グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="3257a-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3257a-141">グループを作成できるユーザーを制限するには、必ず **セキュリティー グループ** を使用してください。</span><span class="sxs-lookup"><span data-stu-id="3257a-141">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="3257a-142">Microsoft 365 グループの使用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3257a-142">Using a Microsoft 365 group is not supported.</span></span> 
    
1. <span data-ttu-id="3257a-143">管理センターで、[ [グループ] ページ](https://admin.microsoft.com/adminportal/home#/groups)に移動します。</span><span class="sxs-lookup"><span data-stu-id="3257a-143">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="3257a-144">[**グループの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3257a-144">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="3257a-145">グループの種類として [**セキュリティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3257a-145">Choose **Security** as the group type.</span></span> <span data-ttu-id="3257a-146">グループの名前は覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="3257a-146">Remember the name of the group!</span></span> <span data-ttu-id="3257a-147">後で必要になります。</span><span class="sxs-lookup"><span data-stu-id="3257a-147">You'll need it later.</span></span>
  
4. <span data-ttu-id="3257a-148">セキュリティグループの設定を終了し、組織内でグループを作成できるユーザーまたは他のセキュリティグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="3257a-148">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="3257a-149">詳細については、「[Microsoft 365 管理センターでのセキュリティ グループの作成、編集、または削除](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3257a-149">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="3257a-150">手順 2: PowerShell コマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="3257a-150">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="3257a-151">グループレベルのゲスト アクセス設定を変更するには、[Graph 用 Azure Active Directory PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (モジュール名 **AzureADPreview**) のプレビュー バージョンを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3257a-151">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="3257a-152">以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Azure AD モジュールのインストール](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="3257a-152">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="3257a-153">Azure AD PowerShell モジュール (AzureAD) の 2.0 一般提供バージョンをインストールしている場合には、PowerShell セッションで `Uninstall-Module AzureAD` を実行してアンインストールし、`Install-Module AzureADPreview` を実行してプレビュー バージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3257a-153">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="3257a-154">プレビュー バージョンを既にインストールしている場合には、`Install-Module AzureADPreview`を実行しそれがこのモジュールの最新バージョンであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3257a-154">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="3257a-155">下のスクリプトを、Notepad などのテキスト エディターまたは [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise) にコピーます。</span><span class="sxs-lookup"><span data-stu-id="3257a-155">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="3257a-156">を、 *\<SecurityGroupName\>* 作成したセキュリティグループの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3257a-156">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="3257a-157">例:</span><span class="sxs-lookup"><span data-stu-id="3257a-157">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="3257a-158">GroupCreators.ps1 としてファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="3257a-158">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="3257a-159">PowerShell ウィンドウで、ファイルを保存した場所に移動 します ("CD <FileLocation>" と入力)。</span><span class="sxs-lookup"><span data-stu-id="3257a-159">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="3257a-160">次のように入力してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="3257a-160">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="3257a-161">サインインを求められたら、[管理者アカウントでサインイン](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription)します。</span><span class="sxs-lookup"><span data-stu-id="3257a-161">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

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
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="3257a-162">スクリプトの最後の行に、更新された設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3257a-162">The last line of the script will display the updated settings:</span></span>

![完了すると、設定は次のように表示されます。](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="3257a-164">使用するセキュリティグループを変更する場合は、新しいセキュリティグループの名前でスクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="3257a-164">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="3257a-165">グループ作成の制限をオフにして、もう一度すべてのユーザーがグループを作成できるようにするには、$GroupName を "" に、$AllowGroupCreation を "True" に設定して、スクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="3257a-165">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="3257a-166">手順 4: 動作することを確認する</span><span class="sxs-lookup"><span data-stu-id="3257a-166">Step 4: Verify that it works</span></span>

<span data-ttu-id="3257a-167">変更が有効になるまでに30分以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3257a-167">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="3257a-168">新しい設定を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3257a-168">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="3257a-169">グループを作成する権限を持たないユーザーアカウントを使用して、Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="3257a-169">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="3257a-170">作成したセキュリティ グループのメンバーまたは管理者ではないユーザーのアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="3257a-170">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="3257a-171">[**Planner**] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3257a-171">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="3257a-172">Planner では、左側のナビゲーションで **[新しいプラン]** を選択してプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="3257a-172">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="3257a-173">プランとグループの作成が無効になっていることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3257a-173">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="3257a-174">セキュリティグループのメンバーと同じ手順をもう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="3257a-174">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="3257a-175">セキュリティグループのメンバーがグループを作成できない場合は、そのグループが [OWA メールボックス ポリシー](https://go.microsoft.com/fwlink/?linkid=852135) によってブロックされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3257a-175">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="3257a-176">関連記事</span><span class="sxs-lookup"><span data-stu-id="3257a-176">Related articles</span></span>

[<span data-ttu-id="3257a-177">Office 365 PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="3257a-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="3257a-178">セルフサービス グループ管理に必要な Azure Active Directory の設定</span><span class="sxs-lookup"><span data-stu-id="3257a-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="3257a-179">ExecutionPolicy の設定</span><span class="sxs-lookup"><span data-stu-id="3257a-179">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="3257a-180">グループ設定を構成するための Azure Active Directory コマンドレット</span><span class="sxs-lookup"><span data-stu-id="3257a-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
