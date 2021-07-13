---
title: グループ内のゲスト アクセスMicrosoft 365する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: ゲストをグループに追加し、Microsoft 365ユーザーを表示し、PowerShell を使用してゲスト アクセスを制御する方法について説明します。
ms.openlocfilehash: 41a42a0b4fc76b71892f758519db56f4c1adc897
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394065"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="5c87c-103">グループ内のゲスト アクセスMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="5c87c-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="5c87c-104">既定では、組織Microsoft 365グループのゲスト アクセスが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="5c87c-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="5c87c-105">管理者は、グループへのゲスト アクセスを、組織全体または個々のグループに対して許可するかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="5c87c-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="5c87c-106">オンにすると、グループ メンバーは、Web 上のユーザーを通じて、Microsoft 365グループOutlook招待できます。</span><span class="sxs-lookup"><span data-stu-id="5c87c-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="5c87c-107">招待状が承認のためにグループの所有者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="5c87c-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="5c87c-108">承認が完了すると、ゲスト ユーザーがディレクトリとグループに追加されます。</span><span class="sxs-lookup"><span data-stu-id="5c87c-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="5c87c-109">ネイティブ モードまたは [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) にある Yammer Enterprise ネットワークは、ネットワークのゲストをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5c87c-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) do not support network guests.</span></span>
> <span data-ttu-id="5c87c-110">Microsoft 365接続Yammerグループは現在、ゲスト アクセスをサポートしていないが、ネットワーク内に接続されていない外部グループをYammerできます。</span><span class="sxs-lookup"><span data-stu-id="5c87c-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="5c87c-111">手順については。「[Yammer の外部グループを作成して管理する](/yammer/work-with-external-users/create-and-manage-external-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c87c-111">See [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="5c87c-112">グループ内のゲスト アクセスは、SharePoint や Teams を含む広範囲のシナリオの一部としてよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="5c87c-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="5c87c-113">これらのサービスには、独自のゲスト共有設定があります。</span><span class="sxs-lookup"><span data-stu-id="5c87c-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="5c87c-114">グループ、SharePoint、Teams 間でゲスト共有をセットアップするための詳細な手順については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c87c-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="5c87c-115">サイトでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="5c87c-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="5c87c-116">チームでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="5c87c-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="5c87c-117">グループのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="5c87c-117">Manage groups guest access</span></span>

<span data-ttu-id="5c87c-118">グループのゲスト アクセスを有効または無効にするには、Microsoft 365 管理センターで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5c87c-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="5c87c-119">管理センターで、[組織の設定設定を表示する] \> **に移動し、[** サービス] タブで [グループ] を \> **Microsoft 365します**。 </span><span class="sxs-lookup"><span data-stu-id="5c87c-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="5c87c-120">[グループ **Microsoft 365]** ページで、組織外のユーザーにグループ リソースへのアクセスを許可するか、グループ所有者が組織外のユーザーをグループに追加するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c87c-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="5c87c-121">管理センターからゲストMicrosoft 365グループに追加する</span><span class="sxs-lookup"><span data-stu-id="5c87c-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="5c87c-122">ゲストが既に自分のディレクトリ内にある場合、Microsoft 365 管理センターで、それらのゲストをグループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="5c87c-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="5c87c-123">(動的メンバーシップを持つグループは、[グループ内](/azure/active-directory/enterprise-users/groups-create-rule)でAzure Active Directory必要があります。)</span><span class="sxs-lookup"><span data-stu-id="5c87c-123">(Groups with dynamic membership must be [managed in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="5c87c-124">管理センターで、[**グループ**]  >  [**グループ**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="5c87c-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="5c87c-125">ゲストを追加するグループをクリックし、[メンバー] **タブで** [すべて表示してメンバーを管理する] **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="5c87c-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="5c87c-126">[**メンバーを追加**] を選択し、追加するゲストの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c87c-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="5c87c-127">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c87c-127">Select **Save**.</span></span>

<span data-ttu-id="5c87c-128">ディレクトリに直接ゲストを追加する場合は、[Azure Portal で Azure Active Directory B2B コラボレーション ユーザーを追加する](/azure/active-directory/b2b/add-users-administrator)ことができます。</span><span class="sxs-lookup"><span data-stu-id="5c87c-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="5c87c-129">ゲストの情報を編集する必要がある場合は、[Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)ことができます。</span><span class="sxs-lookup"><span data-stu-id="5c87c-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="related-content"></a><span data-ttu-id="5c87c-130">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="5c87c-130">Related content</span></span>

<span data-ttu-id="5c87c-131">[特定のグループからのゲスト ユーザーのブロック](../../solutions/per-group-guest-access.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="5c87c-131">[Block guest users from a specific group](../../solutions/per-group-guest-access.md) (article)</span></span>\
<span data-ttu-id="5c87c-132">[グループ メンバーシップを管理するには、Microsoft 365 管理センター](add-or-remove-members-from-groups.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="5c87c-132">[Manage group membership in the Microsoft 365 admin center](add-or-remove-members-from-groups.md) (article)</span></span>\
<span data-ttu-id="5c87c-133">[Azure Active Directoryアクセス レビュー](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (記事)</span><span class="sxs-lookup"><span data-stu-id="5c87c-133">[Azure Active Directory access reviews](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (article)</span></span>\
<span data-ttu-id="5c87c-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (記事)</span><span class="sxs-lookup"><span data-stu-id="5c87c-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (article)</span></span>