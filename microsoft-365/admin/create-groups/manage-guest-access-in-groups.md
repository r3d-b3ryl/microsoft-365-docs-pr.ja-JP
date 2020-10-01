---
title: Microsoft 365 グループでゲストアクセスを管理する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: ゲストアクセスを制御するために、Microsoft 365 グループにゲストを追加し、ゲストユーザーを表示し、PowerShell を使用する方法について説明します。
ms.openlocfilehash: 640a35cbb1a3eb395453b224cadcf0d0db82fab8
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326521"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="28413-103">Microsoft 365 グループでゲストアクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="28413-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="28413-104">既定では、Microsoft 365 グループのゲストアクセスは組織に対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="28413-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="28413-105">管理者は、グループへのゲスト アクセスを、組織全体または個々のグループに対して許可するかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="28413-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="28413-106">グループメンバーは、オンにすると、Outlook on Web を介して Microsoft 365 グループにゲストユーザーを招待できます。</span><span class="sxs-lookup"><span data-stu-id="28413-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="28413-107">招待状が承認のためにグループの所有者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="28413-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="28413-108">承認が完了すると、ゲスト ユーザーがディレクトリとグループに追加されます。</span><span class="sxs-lookup"><span data-stu-id="28413-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="28413-109">ネイティブ モードまたは [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) にある Yammer Enterprise ネットワークは、ネットワークのゲストをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="28413-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="28413-110">Microsoft 365 Connected Yammer グループは現在、ゲストアクセスをサポートしていませんが、Yammer ネットワークに接続されていない外部グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="28413-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="28413-111">手順については。「[Yammer の外部グループを作成して管理する](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28413-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="28413-112">グループ内のゲスト アクセスは、SharePoint や Teams を含む広範囲のシナリオの一部としてよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="28413-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="28413-113">これらのサービスには、独自のゲスト共有設定があります。</span><span class="sxs-lookup"><span data-stu-id="28413-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="28413-114">グループ、SharePoint、Teams 間でゲスト共有をセットアップするための詳細な手順については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28413-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="28413-115">サイトでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="28413-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="28413-116">チームでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="28413-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="28413-117">グループのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="28413-117">Manage groups guest access</span></span>

<span data-ttu-id="28413-118">グループのゲスト アクセスを有効または無効にするには、Microsoft 365 管理センターで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="28413-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="28413-119">管理センターで、[すべての設定の表示] [組織設定 **]** の順に移動し、[ \> **Settings** \> **Org settings** **サービス**] タブの [ **Microsoft 365 グループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28413-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="28413-120">[ **Microsoft 365 Groups** ] ページで、組織外のユーザーにグループリソースへのアクセスを許可するか、グループ所有者に組織外のユーザーをグループに追加させるかを選択します。</span><span class="sxs-lookup"><span data-stu-id="28413-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="28413-121">管理センターからの Microsoft 365 グループへのゲストの追加</span><span class="sxs-lookup"><span data-stu-id="28413-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="28413-122">ゲストが既に自分のディレクトリ内にある場合、Microsoft 365 管理センターで、それらのゲストをグループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="28413-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="28413-123">管理センターで、[**グループ**]  >  [**グループ**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="28413-123">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="28413-124">ゲストを追加するグループをクリックし、[**メンバー** ] タブの [**すべて表示] および [メンバーを管理**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28413-124">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="28413-125">[**メンバーを追加**] を選択し、追加するゲストの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="28413-125">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="28413-126">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28413-126">Select **Save**.</span></span>

<span data-ttu-id="28413-127">ディレクトリに直接ゲストを追加する場合は、[Azure Portal で Azure Active Directory B2B コラボレーション ユーザーを追加する](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)ことができます。</span><span class="sxs-lookup"><span data-stu-id="28413-127">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="28413-128">ゲストの情報を編集する必要がある場合は、[Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)ことができます。</span><span class="sxs-lookup"><span data-stu-id="28413-128">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="28413-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="28413-129">See also</span></span>

[<span data-ttu-id="28413-130">特定のグループに対してゲスト ユーザーをブロックする</span><span class="sxs-lookup"><span data-stu-id="28413-130">Block guest users from a specific group</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="28413-131">Microsoft 365 管理センターでグループメンバーシップを管理する</span><span class="sxs-lookup"><span data-stu-id="28413-131">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="28413-132">Azure Active Directory アクセス レビュー</span><span class="sxs-lookup"><span data-stu-id="28413-132">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="28413-133">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="28413-133">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
