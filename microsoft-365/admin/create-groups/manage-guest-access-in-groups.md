---
title: Office 365 グループでゲスト アクセスを管理する
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.date: 12/18/2019
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
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Office 365 グループへのゲストの追加、ゲスト ユーザーの表示、PowerShell を使用したゲスト アクセスの制御を行う方法について説明します。
ms.openlocfilehash: 02a951b1fbf43c22f12a89663a0aee279b191088
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352618"
---
# <a name="manage-guest-access-in-office-365-groups"></a><span data-ttu-id="37471-103">Office 365 グループでゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="37471-103">Manage guest access in Office 365 Groups</span></span>

<span data-ttu-id="37471-104">既定では、組織で Office 365 グループのゲスト アクセスが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="37471-104">By default, guest access for Office 365 groups is turned on for your organization.</span></span> <span data-ttu-id="37471-105">管理者は、グループへのゲスト アクセスを、組織全体または個々のグループに対して許可するかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="37471-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="37471-106">有効になっている場合、グループ メンバーは Outlook on the Web を使用して、ゲスト ユーザーを Office 365 グループに招待できます。</span><span class="sxs-lookup"><span data-stu-id="37471-106">When it's turned on, group members can invite guest users to an Office 365 group through Outlook on Web.</span></span> <span data-ttu-id="37471-107">招待状が承認のためにグループの所有者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="37471-107">Invitations are sent to the group owner for approval.</span></span>

> [!Note]
> <span data-ttu-id="37471-108">ネイティブ モードまたは [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) にある Yammer Enterprise ネットワークは、ネットワークのゲストをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="37471-108">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="37471-109">Office 365 接続 Yammer グループは、現在ゲスト アクセスをサポートしていません。ただし、接続されていない外部グループを Yammer ネットワークに作成することはできます。</span><span class="sxs-lookup"><span data-stu-id="37471-109">Office 365 Connected Yammer Groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="37471-110">手順については。「[Yammer の外部グループを作成して管理する](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37471-110">See [Create and manage external groups in Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) for instructions.</span></span>

### <a name="edit-guest-information"></a><span data-ttu-id="37471-111">ゲスト情報を編集する</span><span class="sxs-lookup"><span data-stu-id="37471-111">Edit guest information</span></span>

<span data-ttu-id="37471-112">承認が完了すると、ゲスト ユーザーがディレクトリとグループに追加されます。</span><span class="sxs-lookup"><span data-stu-id="37471-112">Once approved, the guest user is added to the directory and the group.</span></span>

<span data-ttu-id="37471-113">グループ内のゲスト アクセスは、SharePoint や Teams を含む広範囲のシナリオの一部としてよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="37471-113">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="37471-114">これらのサービスには、独自のゲスト共有設定があります。</span><span class="sxs-lookup"><span data-stu-id="37471-114">These services have their own guest sharing settings.</span></span> <span data-ttu-id="37471-115">グループ、SharePoint、Teams 間でゲスト共有をセットアップするための詳細な手順については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37471-115">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="37471-116">サイトでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="37471-116">Collaborate with guests in a site</span></span>](https://docs.microsoft.com/Office365/Enterprise/collaborate-in-a-site)
- [<span data-ttu-id="37471-117">チームでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="37471-117">Collaborate with guests in a team</span></span>](https://docs.microsoft.com/Office365/Enterprise/collaborate-as-a-team)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="37471-118">グループのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="37471-118">Manage groups guest access</span></span>

<span data-ttu-id="37471-119">グループのゲスト アクセスを有効または無効にするには、Microsoft 365 管理センターで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="37471-119">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="37471-120">管理センターで、 [**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">サービスとアドイン</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="37471-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services & add-ins</a> page.</span></span>

2. <span data-ttu-id="37471-121">[**Office 365 グループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="37471-121">Select **Office 365 Groups**.</span></span>
  
3. <span data-ttu-id="37471-122">[**Office 365 グループ**] ページで、組織外のユーザーにグループ リソースへのアクセスを許可するか、またはグループ所有者が組織外のユーザーをグループに追加できるようにするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="37471-122">On the **Office 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-an-office-365-group-from-the-admin-center"></a><span data-ttu-id="37471-123">管理センターから Office 365 グループにゲストを追加する</span><span class="sxs-lookup"><span data-stu-id="37471-123">Add guests to an Office 365 group from the admin center</span></span>

<span data-ttu-id="37471-124">ゲストが既に自分のディレクトリ内にある場合、Microsoft 365 管理センターで、それらのゲストをグループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="37471-124">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="37471-125">管理センターで、[**グループ**]  >  [**グループ**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="37471-125">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="37471-126">ゲストを追加するグループを選択し、[**メンバー**] タブで [**すべてのメンバーの表示と管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="37471-126">Select the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="37471-127">[**メンバーを追加**] を選択し、追加するゲストの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="37471-127">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="37471-128">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="37471-128">Select **Save**.</span></span>

<span data-ttu-id="37471-129">ディレクトリに直接ゲストを追加する場合は、[Azure Portal で Azure Active Directory B2B コラボレーション ユーザーを追加する](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)ことができます。</span><span class="sxs-lookup"><span data-stu-id="37471-129">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="37471-130">ゲストの情報を編集する必要がある場合は、[Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)ことができます。</span><span class="sxs-lookup"><span data-stu-id="37471-130">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>
  
## <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="37471-131">特定のグループに対してゲスト ユーザーをブロックする</span><span class="sxs-lookup"><span data-stu-id="37471-131">Block guest users from a specific group</span></span>

<span data-ttu-id="37471-132">ほとんどのグループへのゲスト アクセスを許可したいが、ゲスト アクセスを防止する必要がある場合は、Microsoft PowerShell を使用して個々のグループのゲスト アクセスをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="37471-132">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="37471-133">グループレベルのゲスト アクセス設定を変更するには、[Graph 用 Azure Active Directory PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (モジュール名 **AzureADPreview**) のプレビュー バージョンを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37471-133">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="37471-134">以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Azure AD モジュールのインストール](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="37471-134">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="37471-135">Azure AD PowerShell モジュール (AzureAD) の 2.0 一般提供バージョンをインストールしている場合には、PowerShell セッションで `Uninstall-Module AzureAD` を実行してアンインストールし、`Install-Module AzureADPreview` を実行してプレビュー バージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="37471-135">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="37471-136">プレビュー バージョンを既にインストールしている場合には、`Install-Module AzureADPreview` を実行しそれがこのモジュールの最新バージョンであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="37471-136">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="37471-137">これらのコマンドを実行するには、全体管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="37471-137">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="37471-138">*/<GroupName/>* をゲスト アクセスをブロックするグループの名前に変更し、次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="37471-138">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="37471-139">設定を検証するために、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="37471-139">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="37471-140">検証は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="37471-140">The verification looks like this:</span></span>
    
![ゲスト グループのアクセスが False に設定されていることを示す PowerShell ウィンドウのスクリーンショット。](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="37471-142">ゲストのドメインに応じてゲスト アクセスを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="37471-142">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="37471-p105">特定のドメインを使用しているゲスト ユーザーを許可またはブロックできます。たとえば、自分の会社 (Contoso) が他の会社 (Fabrikam) とパートナーシップを結んでいる場合、許可リストに Fabrikam を追加し、ユーザーが自分のグループにそれらのゲストを追加できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="37471-p105">You can allow or block guest users who are using a specific domain. For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="37471-145">詳細については、「[B2B ユーザーに対する特定組織からの招待を許可またはブロックする](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37471-145">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="37471-146">グローバル アドレス一覧にゲストを追加する</span><span class="sxs-lookup"><span data-stu-id="37471-146">Add guests to the global address list</span></span>

<span data-ttu-id="37471-147">既定では、ゲストは Exchange グローバル アドレス一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="37471-147">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="37471-148">グローバル アドレス一覧にゲストを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="37471-148">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="37471-149">ゲスト ユーザーの ObjectID を検索するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="37471-149">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="37471-150">次に、ObjectID、GivenName、Surname、DisplayName、TelephoneNumber の適切な値を使用して以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="37471-150">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="37471-151">関連記事</span><span class="sxs-lookup"><span data-stu-id="37471-151">Related articles</span></span>

[<span data-ttu-id="37471-152">グループ メンバーシップを Microsoft 365 管理センターから管理する</span><span class="sxs-lookup"><span data-stu-id="37471-152">Manage Group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="37471-153">Azure Active Directory アクセス レビュー</span><span class="sxs-lookup"><span data-stu-id="37471-153">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="37471-154">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="37471-154">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
