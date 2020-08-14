---
title: 特定のグループに対してゲスト ユーザーをブロックする
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 特定のグループに対してゲスト ユーザーをブロックする
ms.openlocfilehash: 923a9e5cd09d232f377f55fd6a9f499f8f536a84
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662715"
---
# <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="b1db9-103">特定のグループに対してゲスト ユーザーをブロックする</span><span class="sxs-lookup"><span data-stu-id="b1db9-103">Block guest users from a specific group</span></span>

<span data-ttu-id="b1db9-104">ほとんどのグループへのゲストアクセスを許可し、ゲストアクセスを禁止する場所がある場合は、個々のグループのゲストアクセスをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="b1db9-104">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups.</span></span>

<span data-ttu-id="b1db9-105">組織で機密ラベルを使用する場合は、グループごとのゲストアクセスを制御するためにそれらを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b1db9-105">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="b1db9-106">これを行う方法については、「 [機密ラベルを使用して Microsoft Teams、microsoft 365 グループ、および SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1db9-106">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="b1db9-107">これが推奨アプローチです。</span><span class="sxs-lookup"><span data-stu-id="b1db9-107">This is the recommended approach.</span></span>

<span data-ttu-id="b1db9-108">Microsoft PowerShell を使用して個々のグループへのゲストアクセスをブロックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b1db9-108">You can also block guest access to individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="b1db9-109">グループレベルのゲストアクセス設定を変更するには、 [Graph 用の Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (モジュール名 **AzureADPreview**) のプレビューバージョンを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1db9-109">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="b1db9-110">以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Installing the Azure AD Module (Azure AD モジュールのインストール)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="b1db9-110">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="b1db9-111">Azure AD PowerShell モジュール (AzureAD) の 2.0 一般提供バージョンをインストールしている場合には、PowerShell セッションで `Uninstall-Module AzureAD` を実行してアンインストールし、`Install-Module AzureADPreview` を実行してプレビュー バージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1db9-111">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="b1db9-112">プレビュー バージョンを既にインストールしている場合には、`Install-Module AzureADPreview` を実行しそれがこのモジュールの最新バージョンであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1db9-112">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="b1db9-113">これらのコマンドを実行するには、全体管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="b1db9-113">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="b1db9-114">*/<GroupName/>* をゲスト アクセスをブロックするグループの名前に変更し、次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="b1db9-114">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="b1db9-115">設定を検証するために、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b1db9-115">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="b1db9-116">検証は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b1db9-116">The verification looks like this:</span></span>
    
![ゲスト グループのアクセスが False に設定されていることを示す PowerShell ウィンドウのスクリーンショット。](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="b1db9-118">ゲストのドメインに応じてゲスト アクセスを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="b1db9-118">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="b1db9-p102">特定のドメインを使用しているゲスト ユーザーを許可またはブロックできます。たとえば、自分の会社 (Contoso) が他の会社 (Fabrikam) とパートナーシップを結んでいる場合、許可リストに Fabrikam を追加し、ユーザーが自分のグループにそれらのゲストを追加できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b1db9-p102">You can allow or block guest users who are using a specific domain. For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="b1db9-121">詳細については、「[B2B ユーザーに対する特定組織からの招待を許可またはブロックする](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1db9-121">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="b1db9-122">グローバル アドレス一覧にゲストを追加する</span><span class="sxs-lookup"><span data-stu-id="b1db9-122">Add guests to the global address list</span></span>

<span data-ttu-id="b1db9-123">既定では、ゲストは Exchange グローバル アドレス一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="b1db9-123">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="b1db9-124">グローバル アドレス一覧にゲストを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="b1db9-124">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="b1db9-125">ゲスト ユーザーの ObjectID を検索するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b1db9-125">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="b1db9-126">次に、ObjectID、GivenName、Surname、DisplayName、TelephoneNumber の適切な値を使用して以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="b1db9-126">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="b1db9-127">関連記事</span><span class="sxs-lookup"><span data-stu-id="b1db9-127">Related articles</span></span>

[<span data-ttu-id="b1db9-128">グループ メンバーシップを Microsoft 365 管理センターから管理する</span><span class="sxs-lookup"><span data-stu-id="b1db9-128">Manage Group membership in the Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[<span data-ttu-id="b1db9-129">Azure Active Directory アクセス レビュー</span><span class="sxs-lookup"><span data-stu-id="b1db9-129">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="b1db9-130">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="b1db9-130">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)