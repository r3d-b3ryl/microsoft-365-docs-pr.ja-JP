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
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Microsoft 365 グループを作成できるユーザーを制御する方法について説明します。
ms.openlocfilehash: 3fa430e44c272e5ababbfb0e4befba707c72c1ba
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122386"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="46899-103">Microsoft 365 グループを作成できるユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="46899-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="46899-104">既定では、すべてのユーザーが Microsoft 365 グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="46899-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="46899-105">IT の支援を必要とせずにユーザーが共同作業を開始できる場合、この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="46899-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="46899-106">ビジネスでグループを作成できるユーザーを制限する必要がある場合は、この記事の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="46899-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="46899-107">グループを作成できるユーザーを制限すると、アクセスにグループに依存する次のようなすべてのサービスに影響します。</span><span class="sxs-lookup"><span data-stu-id="46899-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="46899-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="46899-108">Outlook</span></span>
- <span data-ttu-id="46899-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="46899-109">SharePoint</span></span>
- <span data-ttu-id="46899-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="46899-110">Yammer</span></span>
- <span data-ttu-id="46899-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46899-111">Microsoft Teams</span></span>
- <span data-ttu-id="46899-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="46899-112">Microsoft Stream</span></span>
- <span data-ttu-id="46899-113">Planner</span><span class="sxs-lookup"><span data-stu-id="46899-113">Planner</span></span>
- <span data-ttu-id="46899-114">Power BI (クラシック)</span><span class="sxs-lookup"><span data-stu-id="46899-114">Power BI (classic)</span></span>
- <span data-ttu-id="46899-115">Project for the web / Roadmap</span><span class="sxs-lookup"><span data-stu-id="46899-115">Project for the web / Roadmap</span></span>

<span data-ttu-id="46899-116">Microsoft 365 グループの作成は、特定の Microsoft 365 グループまたはセキュリティ グループのメンバーに制限できます。</span><span class="sxs-lookup"><span data-stu-id="46899-116">You can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span> <span data-ttu-id="46899-117">制限するには、Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="46899-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="46899-118">この記事では、必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="46899-118">This article walks you through the needed steps.</span></span>

<span data-ttu-id="46899-119">この記事の手順を実行しても、特定の役割のメンバーがグループを作成できなくなることはありません。</span><span class="sxs-lookup"><span data-stu-id="46899-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="46899-120">Office 365 のグローバル管理者は、Microsoft 365 管理センター、Planner、Teams、Exchange、SharePoint Online などの方法でグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="46899-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="46899-121">他の役割は、以下のような制限付きの方法でグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="46899-121">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="46899-122">Exchange 管理者: Exchange 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="46899-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="46899-123">パートナー レベル 1 のサポート: Microsoft 365 管理センター、Exchange 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="46899-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="46899-124">パートナー レベル 2 のサポート: Microsoft 365 管理センター、Exchange 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="46899-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="46899-125">ディレクトリ製作者: Azure AD</span><span class="sxs-lookup"><span data-stu-id="46899-125">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="46899-126">SharePoint 管理者: SharePoint 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="46899-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="46899-127">Teams サービス管理者: Teams 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="46899-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="46899-128">ユーザー管理の管理者: Microsoft 365 管理センター、Yammer、Azure AD</span><span class="sxs-lookup"><span data-stu-id="46899-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>

<span data-ttu-id="46899-129">これらの役割のメンバーである場合は、制限付きユーザー用に Microsoft 365 グループを作成し、そのユーザーをグループの所有者として割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="46899-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="46899-130">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="46899-130">Licensing requirements</span></span>

<span data-ttu-id="46899-131">グループを作成するユーザーを管理するには、次のユーザーに Azure AD Premium ライセンスまたは Azure AD Basic EDU ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="46899-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="46899-132">これらのグループ作成の設定を管理している管理者</span><span class="sxs-lookup"><span data-stu-id="46899-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="46899-133">グループの作成が許可されているグループのメンバー</span><span class="sxs-lookup"><span data-stu-id="46899-133">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="46899-134">[Azure ライセンスを割り当てる方法](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)の詳細については、「Azure Active Directory ポータルでライセンスを割り当てるまたは削除する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46899-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="46899-135">以下のユーザーは Azure AD Premium ライセンスまたは Azure AD Basic EDU のライセンスが割り当てられている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="46899-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="46899-136">Microsoft 365 グループのメンバーであり、他のグループを作成できないユーザー。</span><span class="sxs-lookup"><span data-stu-id="46899-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="46899-137">手順 1: Microsoft 365 グループを作成する必要があるユーザーのグループを作成する</span><span class="sxs-lookup"><span data-stu-id="46899-137">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="46899-138">グループを作成できるユーザーを制御するために使用できるのは、組織内の 1 つのグループのみです。</span><span class="sxs-lookup"><span data-stu-id="46899-138">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="46899-139">ただし、他のグループをこのグループのメンバーとして入れ子にできます。</span><span class="sxs-lookup"><span data-stu-id="46899-139">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="46899-140">上記の役割の管理者は、このグループのメンバーである必要はなく、グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="46899-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="46899-141">管理センターで、[グループ] ページ [に移動します](https://admin.microsoft.com/adminportal/home#/groups)。</span><span class="sxs-lookup"><span data-stu-id="46899-141">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="46899-142">[**グループの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46899-142">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="46899-143">必要なグループの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="46899-143">Choose the group type you want.</span></span> <span data-ttu-id="46899-144">グループの名前は覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="46899-144">Remember the name of the group!</span></span> <span data-ttu-id="46899-145">後で必要になります。</span><span class="sxs-lookup"><span data-stu-id="46899-145">You'll need it later.</span></span>

4. <span data-ttu-id="46899-146">グループの設定を完了し、組織でグループを作成できるユーザーまたは他のグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="46899-146">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="46899-147">詳細については、「[Microsoft 365 管理センターでのセキュリティ グループの作成、編集、または削除](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46899-147">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="46899-148">手順 2: PowerShell コマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="46899-148">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="46899-149">グループレベルのゲスト アクセス設定を変更するには、[Graph 用 Azure Active Directory PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (モジュール名 **AzureADPreview**) のプレビュー バージョンを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46899-149">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="46899-150">以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Azure AD モジュールのインストール](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="46899-150">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="46899-151">Azure AD PowerShell モジュール (AzureAD) の 2.0 一般提供バージョンをインストールしている場合には、PowerShell セッションで `Uninstall-Module AzureAD` を実行してアンインストールし、`Install-Module AzureADPreview` を実行してプレビュー バージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="46899-151">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="46899-152">プレビュー バージョンを既にインストールしている場合には、`Install-Module AzureADPreview`を実行しそれがこのモジュールの最新バージョンであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="46899-152">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="46899-153">下のスクリプトを、Notepad などのテキスト エディターまたは [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise) にコピーます。</span><span class="sxs-lookup"><span data-stu-id="46899-153">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="46899-154">作成 *\<GroupName\>* したグループの名前に置き換える。</span><span class="sxs-lookup"><span data-stu-id="46899-154">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="46899-155">例:</span><span class="sxs-lookup"><span data-stu-id="46899-155">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="46899-156">GroupCreators.ps1 としてファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="46899-156">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="46899-157">PowerShell ウィンドウで、ファイルを保存した場所に移動 します ("CD <FileLocation>" と入力)。</span><span class="sxs-lookup"><span data-stu-id="46899-157">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="46899-158">次のように入力してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="46899-158">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="46899-159">サインインを求められたら、[管理者アカウントでサインイン](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription)します。</span><span class="sxs-lookup"><span data-stu-id="46899-159">and [sign in with your administrator account](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

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

<span data-ttu-id="46899-160">スクリプトの最後の行に、更新された設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="46899-160">The last line of the script will display the updated settings:</span></span>

![完了すると、設定は次のように表示されます。](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="46899-162">今後、使用するグループを変更する場合は、新しいグループの名前を使用してスクリプトを再実行できます。</span><span class="sxs-lookup"><span data-stu-id="46899-162">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="46899-163">グループ作成の制限をオフにして、もう一度すべてのユーザーがグループを作成できるようにするには、$GroupName を "" に、$AllowGroupCreation を "True" に設定して、スクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="46899-163">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="46899-164">手順 3: 動作することを確認する</span><span class="sxs-lookup"><span data-stu-id="46899-164">Step 3: Verify that it works</span></span>

<span data-ttu-id="46899-165">変更を有効にするには、30 分以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="46899-165">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="46899-166">新しい設定を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="46899-166">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="46899-167">グループを作成できないユーザーのユーザー アカウントで Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="46899-167">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="46899-168">つまり、作成したグループのメンバーまたは管理者ではありません。</span><span class="sxs-lookup"><span data-stu-id="46899-168">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="46899-169">[**Planner**] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="46899-169">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="46899-170">Planner では、左側のナビゲーションで **[新しいプラン]** を選択してプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="46899-170">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="46899-171">プランとグループの作成が無効になっていることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="46899-171">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="46899-172">グループのメンバーと同じ手順を再度実行してください。</span><span class="sxs-lookup"><span data-stu-id="46899-172">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="46899-173">グループのメンバーがグループを作成できない場合は、OWA メールボックス ポリシーによってブロックされていない [か確認します](https://go.microsoft.com/fwlink/?linkid=852135)。</span><span class="sxs-lookup"><span data-stu-id="46899-173">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>

## <a name="related-topics"></a><span data-ttu-id="46899-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="46899-174">Related topics</span></span>

[<span data-ttu-id="46899-175">グループコラボレーション ガバナンスの計画のステップ バイ ステップ</span><span class="sxs-lookup"><span data-stu-id="46899-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="46899-176">コラボレーション ガバナンス計画を作成する</span><span class="sxs-lookup"><span data-stu-id="46899-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="46899-177">Office 365 PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="46899-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="46899-178">セルフサービス グループ管理に必要な Azure Active Directory の設定</span><span class="sxs-lookup"><span data-stu-id="46899-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="46899-179">ExecutionPolicy の設定</span><span class="sxs-lookup"><span data-stu-id="46899-179">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="46899-180">グループ設定を構成するための Azure Active Directory コマンドレット</span><span class="sxs-lookup"><span data-stu-id="46899-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
