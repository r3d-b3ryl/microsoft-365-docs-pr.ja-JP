---
title: Microsoft 365 グループのゲスト アクセスを管理する
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Microsoft 365 グループにゲストを追加し、ゲスト ユーザーを表示し、PowerShell を使用してゲスト アクセスを制御する方法について説明します。
ms.openlocfilehash: 114fc1b5262f1632c7e7a8d1aa339c2470223288
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908608"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="67a5f-103">Microsoft 365 グループのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="67a5f-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="67a5f-104">既定では、組織の Microsoft 365 グループのゲスト アクセスが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="67a5f-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="67a5f-105">管理者は、グループへのゲスト アクセスを、組織全体または個々のグループに対して許可するかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="67a5f-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="67a5f-106">オンにすると、グループ メンバーは Outlook on Web を介して Microsoft 365 グループにゲスト ユーザーを招待できます。</span><span class="sxs-lookup"><span data-stu-id="67a5f-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="67a5f-107">招待状が承認のためにグループの所有者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="67a5f-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="67a5f-108">承認が完了すると、ゲスト ユーザーがディレクトリとグループに追加されます。</span><span class="sxs-lookup"><span data-stu-id="67a5f-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="67a5f-109">ネイティブ モードまたは [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) にある Yammer Enterprise ネットワークは、ネットワークのゲストをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="67a5f-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) do not support network guests.</span></span>
> <span data-ttu-id="67a5f-110">Microsoft 365 Connected Yammerグループは現在、ゲスト アクセスをサポートしていないが、ネットワーク内に接続されていない外部グループYammerできます。</span><span class="sxs-lookup"><span data-stu-id="67a5f-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="67a5f-111">手順については。「[Yammer の外部グループを作成して管理する](/yammer/work-with-external-users/create-and-manage-external-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67a5f-111">See [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="67a5f-112">グループ内のゲスト アクセスは、SharePoint や Teams を含む広範囲のシナリオの一部としてよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="67a5f-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="67a5f-113">これらのサービスには、独自のゲスト共有設定があります。</span><span class="sxs-lookup"><span data-stu-id="67a5f-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="67a5f-114">グループ、SharePoint、Teams 間でゲスト共有をセットアップするための詳細な手順については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67a5f-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="67a5f-115">サイトでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="67a5f-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="67a5f-116">チームでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="67a5f-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="67a5f-117">グループのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="67a5f-117">Manage groups guest access</span></span>

<span data-ttu-id="67a5f-118">グループのゲスト アクセスを有効または無効にするには、Microsoft 365 管理センターで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="67a5f-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="67a5f-119">管理センターで、[すべての設定組織の設定を表示する] に移動し、[サービス] タブで \>  \> **[Microsoft 365** グループ] を選択します。 </span><span class="sxs-lookup"><span data-stu-id="67a5f-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="67a5f-120">**[Microsoft 365 グループ**] ページで、組織外のユーザーがグループ リソースにアクセスできるかどうか、またはグループ所有者が組織外のユーザーをグループに追加するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="67a5f-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="67a5f-121">管理センターから Microsoft 365 グループにゲストを追加する</span><span class="sxs-lookup"><span data-stu-id="67a5f-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="67a5f-122">ゲストが既に自分のディレクトリ内にある場合、Microsoft 365 管理センターで、それらのゲストをグループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="67a5f-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="67a5f-123">(動的メンバーシップを持つグループは [、Azure Active Directory で管理する必要があります](/azure/active-directory/enterprise-users/groups-create-rule)。)</span><span class="sxs-lookup"><span data-stu-id="67a5f-123">(Groups with dynamic membership must be [managed in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="67a5f-124">管理センターで、[**グループ**]  >  [**グループ**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="67a5f-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="67a5f-125">ゲストを追加するグループをクリックし、[メンバー] **タブで** [すべて表示してメンバーを管理する] **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="67a5f-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="67a5f-126">[**メンバーを追加**] を選択し、追加するゲストの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="67a5f-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="67a5f-127">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="67a5f-127">Select **Save**.</span></span>

<span data-ttu-id="67a5f-128">ディレクトリに直接ゲストを追加する場合は、[Azure Portal で Azure Active Directory B2B コラボレーション ユーザーを追加する](/azure/active-directory/b2b/add-users-administrator)ことができます。</span><span class="sxs-lookup"><span data-stu-id="67a5f-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="67a5f-129">ゲストの情報を編集する必要がある場合は、[Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)ことができます。</span><span class="sxs-lookup"><span data-stu-id="67a5f-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="67a5f-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="67a5f-130">See also</span></span>

[<span data-ttu-id="67a5f-131">特定のグループに対してゲスト ユーザーをブロックする</span><span class="sxs-lookup"><span data-stu-id="67a5f-131">Block guest users from a specific group</span></span>](../../solutions/per-group-guest-access.md)

[<span data-ttu-id="67a5f-132">Microsoft 365 管理センターでグループ メンバーシップを管理する</span><span class="sxs-lookup"><span data-stu-id="67a5f-132">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="67a5f-133">Azure Active Directory アクセス レビュー</span><span class="sxs-lookup"><span data-stu-id="67a5f-133">Azure Active Directory access reviews</span></span>](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="67a5f-134">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="67a5f-134">Set-AzureADUser</span></span>](/powershell/module/azuread/set-azureaduser)