---
title: 特定のグループにゲストが追加されないようにする
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 特定のグループにゲストが追加されないようにする方法について説明します。
ms.openlocfilehash: 99e78932b29d25054922b56fcadb608a7dfca432
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613058"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="29469-103">特定の Microsoft 365 グループまたは Microsoft Teams チームにゲストが追加されないようにする</span><span class="sxs-lookup"><span data-stu-id="29469-103">Prevent guests from being added to a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="29469-104">ほとんどのグループおよびチームへのゲストアクセスを許可するが、ゲストアクセスを禁止する場所がある場合は、個々のグループおよびチームのゲストアクセスをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="29469-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="29469-105">(チームへのゲストアクセスをブロックするには、関連するグループへのゲストアクセスをブロックすることによって行います)。これにより、新しいゲストは追加されませんが、グループまたはチームに既に存在するゲストは削除されません。</span><span class="sxs-lookup"><span data-stu-id="29469-105">(Blocking guest access to a team is done by blocking guest access to the associated group.) This prevents new guests from being added but does not remove guests that are already in the group or team.</span></span>

<span data-ttu-id="29469-106">組織で機密ラベルを使用する場合は、グループごとのゲストアクセスを制御するためにそれらを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="29469-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="29469-107">これを行う方法については、「 [機密ラベルを使用して Microsoft Teams、microsoft 365 グループ、および SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29469-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="29469-108">これが推奨アプローチです。</span><span class="sxs-lookup"><span data-stu-id="29469-108">This is the recommended approach.</span></span>

## <a name="change-group-settings-using-microsoft-powershell"></a><span data-ttu-id="29469-109">Microsoft PowerShell を使用してグループ設定を変更する</span><span class="sxs-lookup"><span data-stu-id="29469-109">Change group settings using Microsoft PowerShell</span></span>

<span data-ttu-id="29469-110">PowerShell を使用して、個々のグループに新しいゲストを追加することを禁止することもできます。</span><span class="sxs-lookup"><span data-stu-id="29469-110">You can also prevent the addition of new guests to individual groups by using PowerShell.</span></span>

<span data-ttu-id="29469-111">グループレベルのゲストアクセス設定を変更するには、 [Graph 用の Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (モジュール名 **AzureADPreview**) のプレビューバージョンを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29469-111">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="29469-112">以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Installing the Azure AD Module (Azure AD モジュールのインストール)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="29469-112">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="29469-113">Azure AD PowerShell モジュール (AzureAD) の 2.0 一般提供バージョンをインストールしている場合には、PowerShell セッションで `Uninstall-Module AzureAD` を実行してアンインストールし、`Install-Module AzureADPreview` を実行してプレビュー バージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29469-113">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="29469-114">プレビュー バージョンを既にインストールしている場合には、`Install-Module AzureADPreview` を実行しそれがこのモジュールの最新バージョンであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29469-114">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="29469-115">これらのコマンドを実行するには、全体管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="29469-115">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="29469-116">*/<GroupName/>* をゲスト アクセスをブロックするグループの名前に変更し、次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="29469-116">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="29469-117">設定を検証するために、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="29469-117">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="29469-118">検証は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="29469-118">The verification looks like this:</span></span>
    
![ゲスト グループのアクセスが False に設定されていることを示す PowerShell ウィンドウのスクリーンショット。](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="29469-120">ゲストのドメインに応じてゲスト アクセスを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="29469-120">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="29469-121">特定のドメインを使用しているゲストを許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="29469-121">You can allow or block guests who are using a specific domain.</span></span> <span data-ttu-id="29469-122">たとえば、ビジネス (Contoso) が別のビジネス (Fabrikam) とパートナーシップを持っている場合は、Fabrikam を許可リストに追加して、ユーザーが自分のグループにそのゲストを追加できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="29469-122">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="29469-123">詳細については、「[B2B ユーザーに対する特定組織からの招待を許可またはブロックする](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29469-123">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="29469-124">グローバル アドレス一覧にゲストを追加する</span><span class="sxs-lookup"><span data-stu-id="29469-124">Add guests to the global address list</span></span>

<span data-ttu-id="29469-125">既定では、ゲストは Exchange グローバル アドレス一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="29469-125">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="29469-126">グローバル アドレス一覧にゲストを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="29469-126">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="29469-127">を実行して、ゲストの ObjectID を検索します。</span><span class="sxs-lookup"><span data-stu-id="29469-127">Find the guest's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="29469-128">次に、ObjectID、GivenName、Surname、DisplayName、TelephoneNumber の適切な値を使用して以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="29469-128">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a><span data-ttu-id="29469-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="29469-129">Related topics</span></span>

[<span data-ttu-id="29469-130">コラボレーションガバナンスの計画のステップバイステップ</span><span class="sxs-lookup"><span data-stu-id="29469-130">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="29469-131">コラボレーションのガバナンス計画を作成する</span><span class="sxs-lookup"><span data-stu-id="29469-131">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="29469-132">グループ メンバーシップを Microsoft 365 管理センターから管理する</span><span class="sxs-lookup"><span data-stu-id="29469-132">Manage Group membership in the Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[<span data-ttu-id="29469-133">Azure Active Directory アクセス レビュー</span><span class="sxs-lookup"><span data-stu-id="29469-133">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="29469-134">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="29469-134">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
