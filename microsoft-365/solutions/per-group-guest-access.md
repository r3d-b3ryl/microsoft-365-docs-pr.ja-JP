---
title: ゲストが特定のグループに追加されるのを防ぐ
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
description: 特定のグループにゲストが追加されるのを防ぐ方法について説明します。
ms.openlocfilehash: 572746a666586920ad85dafddbd78997940490d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907942"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="4aa3f-103">ゲストが特定の Microsoft 365 グループまたは Microsoft Teams チームに追加されるのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="4aa3f-103">Prevent guests from being added to a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="4aa3f-104">ほとんどのグループとチームへのゲスト アクセスを許可するが、ゲスト アクセスを防止する場所がある場合は、個々のグループとチームのゲスト アクセスをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="4aa3f-105">(チームへのゲスト アクセスをブロックするには、関連付けられたグループへのゲスト アクセスをブロックします)。これにより、新しいゲストが追加されるのを防ぎ、グループまたはチームに既に存在するゲストは削除されません。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-105">(Blocking guest access to a team is done by blocking guest access to the associated group.) This prevents new guests from being added but does not remove guests that are already in the group or team.</span></span>

<span data-ttu-id="4aa3f-106">組織内で感度ラベルを使用する場合は、グループごとにゲスト アクセスを制御するために使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="4aa3f-107">これを行う方法の詳細については、「感度ラベルを使用して [Microsoft Teams、Microsoft 365](../compliance/sensitivity-labels-teams-groups-sites.md)グループ、および SharePoint サイトのコンテンツを保護する」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span> <span data-ttu-id="4aa3f-108">これが推奨アプローチです。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-108">This is the recommended approach.</span></span>

## <a name="change-group-settings-using-microsoft-powershell"></a><span data-ttu-id="4aa3f-109">Microsoft PowerShell を使用してグループ設定を変更する</span><span class="sxs-lookup"><span data-stu-id="4aa3f-109">Change group settings using Microsoft PowerShell</span></span>

<span data-ttu-id="4aa3f-110">PowerShell を使用して、個々のグループに新しいゲストを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-110">You can also prevent the addition of new guests to individual groups by using PowerShell.</span></span> <span data-ttu-id="4aa3f-111">(チームに関連付けられている SharePoint サイトには、個別の [ゲスト共有コントロールがあります](/sharepoint/change-external-sharing-site)。)</span><span class="sxs-lookup"><span data-stu-id="4aa3f-111">(Remember that the team's associated SharePoint site has [separate guest sharing controls](/sharepoint/change-external-sharing-site).)</span></span>

<span data-ttu-id="4aa3f-112">グループ レベルのゲスト アクセス設定を変更するには、プレビュー バージョンの [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) (モジュール名 **AzureADPreview)** を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-112">You must use the preview version of [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="4aa3f-113">以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Installing the Azure AD Module (Azure AD モジュールのインストール)](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-113">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="4aa3f-114">Azure AD PowerShell モジュール (AzureAD) の 2.0 一般提供バージョンをインストールしている場合には、PowerShell セッションで `Uninstall-Module AzureAD` を実行してアンインストールし、`Install-Module AzureADPreview` を実行してプレビュー バージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-114">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="4aa3f-115">プレビュー バージョンを既にインストールしている場合には、`Install-Module AzureADPreview` を実行しそれがこのモジュールの最新バージョンであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-115">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="4aa3f-116">これらのコマンドを実行するには、全体管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-116">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="4aa3f-117">*/<GroupName/>* をゲスト アクセスをブロックするグループの名前に変更し、次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-117">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="4aa3f-118">設定を検証するために、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-118">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="4aa3f-119">検証は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-119">The verification looks like this:</span></span>
    
![ゲスト グループのアクセスが False に設定されていることを示す PowerShell ウィンドウのスクリーンショット。](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="4aa3f-121">ゲストのドメインに応じてゲスト アクセスを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="4aa3f-121">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="4aa3f-122">特定のドメインを使用しているゲストを許可またはブロックできます。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-122">You can allow or block guests who are using a specific domain.</span></span> <span data-ttu-id="4aa3f-123">たとえば、ビジネス (Contoso) が別のビジネス (Fabrikam) と提携している場合は、Fabrikam を許可リストに追加して、ユーザーがそれらのゲストをグループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-123">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="4aa3f-124">詳細については、「[B2B ユーザーに対する特定組織からの招待を許可またはブロックする](/azure/active-directory/b2b/allow-deny-list)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-124">For more information, see [Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="4aa3f-125">グローバル アドレス一覧にゲストを追加する</span><span class="sxs-lookup"><span data-stu-id="4aa3f-125">Add guests to the global address list</span></span>

<span data-ttu-id="4aa3f-126">既定では、ゲストは Exchange グローバル アドレス一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-126">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="4aa3f-127">グローバル アドレス一覧にゲストを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-127">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="4aa3f-128">次のコマンドを実行して、ゲストの ObjectID を検索します。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-128">Find the guest's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="4aa3f-129">次に、ObjectID、GivenName、Surname、DisplayName、TelephoneNumber の適切な値を使用して以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="4aa3f-129">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a><span data-ttu-id="4aa3f-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="4aa3f-130">Related topics</span></span>

[<span data-ttu-id="4aa3f-131">コラボレーション ガバナンス計画のステップ バイ ステップ</span><span class="sxs-lookup"><span data-stu-id="4aa3f-131">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="4aa3f-132">コラボレーション ガバナンス 計画の作成</span><span class="sxs-lookup"><span data-stu-id="4aa3f-132">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="4aa3f-133">グループ メンバーシップを Microsoft 365 管理センターから管理する</span><span class="sxs-lookup"><span data-stu-id="4aa3f-133">Manage Group membership in the Microsoft 365 admin center</span></span>](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="4aa3f-134">Azure Active Directory アクセス レビュー</span><span class="sxs-lookup"><span data-stu-id="4aa3f-134">Azure Active Directory access reviews</span></span>](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="4aa3f-135">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="4aa3f-135">Set-AzureADUser</span></span>](/powershell/module/azuread/set-azureaduser)