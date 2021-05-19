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
recommendations: false
description: ユーザーがグループを作成できるユーザーを制御Microsoft 365します。
ms.openlocfilehash: 19a106d255708f4b1df8f798219ea7ea778bbef3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539181"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="8d683-103">Microsoft 365 グループを作成できるユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="8d683-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="8d683-104">既定では、すべてのユーザーがグループMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="8d683-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="8d683-105">IT の支援を必要とせずにユーザーが共同作業を開始できるので、この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d683-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="8d683-106">ビジネスでグループを作成できるユーザーを制限する必要がある場合は、グループMicrosoft 365グループまたはセキュリティ グループのメンバー Microsoft 365制限できます。</span><span class="sxs-lookup"><span data-stu-id="8d683-106">If your business requires that you restrict who can create groups, you can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span>

<span data-ttu-id="8d683-107">ビジネス標準に準拠しないチームまたはグループを作成するユーザーが気になる場合は、ユーザーにトレーニング コースを完了し、許可されたユーザーのグループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d683-107">If you're concerned about users creating teams or groups that don't comply with your business standards, consider requiring users to complete a training course and then adding them to the group of allowed users.</span></span>

<span data-ttu-id="8d683-108">グループを作成できるユーザーを制限すると、グループに依存してアクセスを行うすべてのサービスに影響します。</span><span class="sxs-lookup"><span data-stu-id="8d683-108">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="8d683-109">Outlook</span><span class="sxs-lookup"><span data-stu-id="8d683-109">Outlook</span></span>
- <span data-ttu-id="8d683-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="8d683-110">SharePoint</span></span>
- <span data-ttu-id="8d683-111">Yammer</span><span class="sxs-lookup"><span data-stu-id="8d683-111">Yammer</span></span>
- <span data-ttu-id="8d683-112">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8d683-112">Microsoft Teams</span></span>
- <span data-ttu-id="8d683-113">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="8d683-113">Microsoft Stream</span></span>
- <span data-ttu-id="8d683-114">Planner</span><span class="sxs-lookup"><span data-stu-id="8d683-114">Planner</span></span>
- <span data-ttu-id="8d683-115">Power BI (クラシック)</span><span class="sxs-lookup"><span data-stu-id="8d683-115">Power BI (classic)</span></span>
- <span data-ttu-id="8d683-116">Projectの詳細 / ロードマップ</span><span class="sxs-lookup"><span data-stu-id="8d683-116">Project for the web / Roadmap</span></span>

<span data-ttu-id="8d683-117">この記事の手順を実行しても、特定の役割のメンバーがグループを作成できなくなることはありません。</span><span class="sxs-lookup"><span data-stu-id="8d683-117">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="8d683-118">Office 365グローバル管理者は、管理センター、Planner、Microsoft 365、およびオンラインからグループExchange作成SharePointできます。</span><span class="sxs-lookup"><span data-stu-id="8d683-118">Office 365 Global admins can create Groups via the Microsoft 365 admin center, Planner, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="8d683-119">他の役割は、以下のような制限付きの方法でグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8d683-119">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="8d683-120">Exchange 管理者: Exchange 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="8d683-120">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="8d683-121">パートナー レベル 1 のサポート: Microsoft 365 管理センター、Exchange 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="8d683-121">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="8d683-122">パートナー レベル 2 のサポート: Microsoft 365 管理センター、Exchange 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="8d683-122">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="8d683-123">ディレクトリ製作者: Azure AD</span><span class="sxs-lookup"><span data-stu-id="8d683-123">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="8d683-124">SharePoint 管理者: SharePoint 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="8d683-124">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="8d683-125">Teams サービス管理者: Teams 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="8d683-125">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="8d683-126">ユーザー管理者: Microsoft 365センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="8d683-126">User Administrator: Microsoft 365 Admin center, Azure AD</span></span>

<span data-ttu-id="8d683-127">これらの役割の 1 つのメンバーである場合は、制限付きユーザー Microsoft 365グループを作成し、そのユーザーをグループの所有者として割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8d683-127">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="8d683-128">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="8d683-128">Licensing requirements</span></span>

<span data-ttu-id="8d683-129">グループを作成するユーザーを管理するには、次のユーザーに Azure AD プレミアム ライセンスまたは Azure AD EDU ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d683-129">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="8d683-130">これらのグループ作成の設定を管理している管理者</span><span class="sxs-lookup"><span data-stu-id="8d683-130">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="8d683-131">グループの作成が許可されているグループのメンバー</span><span class="sxs-lookup"><span data-stu-id="8d683-131">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="8d683-132">Azure[ライセンスの割り当て方法の詳細については、「Azure Active Directory ポータル](/azure/active-directory/fundamentals/license-users-groups)でライセンスを割り当てるまたは削除する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d683-132">See [Assign or remove licenses in the Azure Active Directory portal](/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="8d683-133">以下のユーザーは Azure AD Premium ライセンスまたは Azure AD Basic EDU のライセンスが割り当てられている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8d683-133">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="8d683-134">グループのメンバー Microsoft 365他のグループを作成できないユーザー。</span><span class="sxs-lookup"><span data-stu-id="8d683-134">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="8d683-135">手順 1: グループを作成する必要があるユーザーのグループをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="8d683-135">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="8d683-136">グループを作成できるユーザーを制御するには、組織内の 1 つのグループのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d683-136">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="8d683-137">ただし、他のグループをこのグループのメンバーとして入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8d683-137">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="8d683-138">上記の役割の管理者は、このグループのメンバーである必要はなく、グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="8d683-138">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="8d683-139">管理センターで、[グループ] ページ [に移動します](https://admin.microsoft.com/adminportal/home#/groups)。</span><span class="sxs-lookup"><span data-stu-id="8d683-139">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="8d683-140">[**グループの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d683-140">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="8d683-141">必要なグループの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d683-141">Choose the group type you want.</span></span> <span data-ttu-id="8d683-142">グループの名前は覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="8d683-142">Remember the name of the group!</span></span> <span data-ttu-id="8d683-143">後で必要になります。</span><span class="sxs-lookup"><span data-stu-id="8d683-143">You'll need it later.</span></span>

4. <span data-ttu-id="8d683-144">グループの設定を完了し、組織でグループを作成できるユーザーまたは他のグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d683-144">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="8d683-145">詳細については、「[Microsoft 365 管理センターでのセキュリティ グループの作成、編集、または削除](../admin/email/create-edit-or-delete-a-security-group.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d683-145">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../admin/email/create-edit-or-delete-a-security-group.md).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="8d683-146">手順 2: PowerShell コマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="8d683-146">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="8d683-147">グループレベルのゲスト アクセス設定を変更するには、[Graph 用 Azure Active Directory PowerShell (AzureAD)](/powershell/azure/active-directory/install-adv2) (モジュール名 **AzureADPreview**) のプレビュー バージョンを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d683-147">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="8d683-148">以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Azure AD モジュールのインストール](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="8d683-148">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="8d683-149">Azure AD PowerShell モジュール (AzureAD) の 2.0 一般提供バージョンをインストールしている場合には、PowerShell セッションで `Uninstall-Module AzureAD` を実行してアンインストールし、`Install-Module AzureADPreview` を実行してプレビュー バージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d683-149">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="8d683-150">プレビュー バージョンを既にインストールしている場合には、`Install-Module AzureADPreview`を実行しそれがこのモジュールの最新バージョンであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d683-150">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="8d683-151">下のスクリプトを、Notepad などのテキスト エディターまたは [Windows PowerShell ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise) にコピーます。</span><span class="sxs-lookup"><span data-stu-id="8d683-151">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="8d683-152">作成 *\<GroupName\>* したグループの名前に置き換える。</span><span class="sxs-lookup"><span data-stu-id="8d683-152">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="8d683-153">例:</span><span class="sxs-lookup"><span data-stu-id="8d683-153">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="8d683-154">GroupCreators.ps1 としてファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="8d683-154">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="8d683-155">PowerShell ウィンドウで、ファイルを保存した場所に移動 します ("CD <FileLocation>" と入力)。</span><span class="sxs-lookup"><span data-stu-id="8d683-155">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="8d683-156">次のように入力してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d683-156">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="8d683-157">サインインを求められたら、[管理者アカウントでサインイン](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription)します。</span><span class="sxs-lookup"><span data-stu-id="8d683-157">and [sign in with your administrator account](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

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

<span data-ttu-id="8d683-158">スクリプトの最後の行に、更新された設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d683-158">The last line of the script will display the updated settings:</span></span>

![PowerShell スクリプト出力のスクリーンショット。](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="8d683-160">今後、使用するグループを変更する場合は、新しいグループの名前でスクリプトを再実行できます。</span><span class="sxs-lookup"><span data-stu-id="8d683-160">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="8d683-161">グループ作成の制限をオフにして、もう一度すべてのユーザーがグループを作成できるようにするには、$GroupName を "" に、$AllowGroupCreation を "True" に設定して、スクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="8d683-161">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="8d683-162">手順 3: 動作することを確認する</span><span class="sxs-lookup"><span data-stu-id="8d683-162">Step 3: Verify that it works</span></span>

<span data-ttu-id="8d683-163">変更を有効にするには、30 分以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d683-163">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="8d683-164">新しい設定を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8d683-164">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="8d683-165">グループを作成Microsoft 365する必要があるユーザーのユーザー アカウントを使用して、グループにサインインします。</span><span class="sxs-lookup"><span data-stu-id="8d683-165">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="8d683-166">つまり、作成したグループまたは管理者のメンバーではありません。</span><span class="sxs-lookup"><span data-stu-id="8d683-166">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="8d683-167">[**Planner**] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d683-167">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="8d683-168">Planner では、左側のナビゲーションで **[新しいプラン]** を選択してプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d683-168">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="8d683-169">プランとグループの作成が無効になっていることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d683-169">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="8d683-170">グループのメンバーと同じ手順を再度実行します。</span><span class="sxs-lookup"><span data-stu-id="8d683-170">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="8d683-171">グループのメンバーがグループを作成できない場合は、OWA メールボックス ポリシーによってブロックされていない [か確認します](/powershell/module/exchange/set-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="8d683-171">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8d683-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d683-172">Related topics</span></span>

[<span data-ttu-id="8d683-173">コラボレーション ガバナンス計画のステップ バイ ステップ</span><span class="sxs-lookup"><span data-stu-id="8d683-173">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="8d683-174">コラボレーション ガバナンス 計画の作成</span><span class="sxs-lookup"><span data-stu-id="8d683-174">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="8d683-175">Office 365 PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="8d683-175">Getting started with Office 365 PowerShell</span></span>](../enterprise/getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="8d683-176">セルフサービス グループ管理に必要な Azure Active Directory の設定</span><span class="sxs-lookup"><span data-stu-id="8d683-176">Set up self-service group management in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="8d683-177">ExecutionPolicy の設定</span><span class="sxs-lookup"><span data-stu-id="8d683-177">Set-ExecutionPolicy</span></span>](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="8d683-178">グループ設定を構成するための Azure Active Directory コマンドレット</span><span class="sxs-lookup"><span data-stu-id="8d683-178">Azure Active Directory cmdlets for configuring group settings</span></span>](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
