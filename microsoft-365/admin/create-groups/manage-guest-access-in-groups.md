---
title: Microsoft 365 グループでゲスト アクセスを管理する
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
description: ゲストをMicrosoft 365グループに追加する方法、ゲスト ユーザーを表示する方法、PowerShell を使用してゲスト アクセスを制御する方法について説明します。
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571939"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="1f8ba-103">Microsoft 365 グループでゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="1f8ba-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="1f8ba-104">既定では、Microsoft 365 グループのゲスト アクセスは、組織で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="1f8ba-105">管理者は、グループへのゲスト アクセスを、組織全体または個々のグループに対して許可するかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="1f8ba-106">オンにすると、グループ メンバーは Web 上のOutlookを通じて、ゲスト ユーザーをMicrosoft 365 グループに招待できます。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="1f8ba-107">招待状が承認のためにグループの所有者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="1f8ba-108">承認が完了すると、ゲスト ユーザーがディレクトリとグループに追加されます。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="1f8ba-109">ネイティブ モードまたは [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) にある Yammer Enterprise ネットワークは、ネットワークのゲストをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) do not support network guests.</span></span>
> <span data-ttu-id="1f8ba-110">Microsoft 365接続Yammerグループは現在ゲスト アクセスをサポートしていませんが、Yammer ネットワーク内に接続されていない外部グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="1f8ba-111">手順については。「[Yammer の外部グループを作成して管理する](/yammer/work-with-external-users/create-and-manage-external-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-111">See [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="1f8ba-112">グループ内のゲスト アクセスは、SharePoint や Teams を含む広範囲のシナリオの一部としてよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="1f8ba-113">これらのサービスには、独自のゲスト共有設定があります。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="1f8ba-114">グループ、SharePoint、Teams 間でゲスト共有をセットアップするための詳細な手順については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="1f8ba-115">サイトでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="1f8ba-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="1f8ba-116">チームでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="1f8ba-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="1f8ba-117">グループのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="1f8ba-117">Manage groups guest access</span></span>

<span data-ttu-id="1f8ba-118">グループのゲスト アクセスを有効または無効にするには、Microsoft 365 管理センターで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="1f8ba-119">管理センターで \> **、[設定 組織** のすべての設定を表示] に移動 \> し、[**サービス**] タブで **[Microsoft 365 グループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="1f8ba-120">[Microsoft 365 **グループ**] ページで、組織外のユーザーがグループ リソースにアクセスできるようにするか、組織外のユーザーをグループに追加するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="1f8ba-121">管理センターからMicrosoft 365 グループにゲストを追加する</span><span class="sxs-lookup"><span data-stu-id="1f8ba-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="1f8ba-122">ゲストが既に自分のディレクトリ内にある場合、Microsoft 365 管理センターで、それらのゲストをグループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="1f8ba-123">(動的メンバーシップを持つグループは[、Azure Active Directoryで管理](/azure/active-directory/enterprise-users/groups-create-rule)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-123">(Groups with dynamic membership must be [managed in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="1f8ba-124">管理センターで、[**グループ**]  >  [**グループ**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="1f8ba-125">ゲストを追加するグループをクリックし、[**メンバー** ] タブで [**すべてのメンバーの表示とメンバーの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="1f8ba-126">[**メンバーを追加**] を選択し、追加するゲストの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="1f8ba-127">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-127">Select **Save**.</span></span>

<span data-ttu-id="1f8ba-128">ディレクトリに直接ゲストを追加する場合は、[Azure Portal で Azure Active Directory B2B コラボレーション ユーザーを追加する](/azure/active-directory/b2b/add-users-administrator)ことができます。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="1f8ba-129">ゲストの情報を編集する必要がある場合は、[Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)ことができます。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="related-content"></a><span data-ttu-id="1f8ba-130">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="1f8ba-130">Related content</span></span>

<span data-ttu-id="1f8ba-131">[特定のグループのゲスト ユーザーをブロック](../../solutions/per-group-guest-access.md) する (記事)</span><span class="sxs-lookup"><span data-stu-id="1f8ba-131">[Block guest users from a specific group](../../solutions/per-group-guest-access.md) (article)</span></span>

<span data-ttu-id="1f8ba-132">[Microsoft 365管理センターでのグループ メンバーシップの管理](add-or-remove-members-from-groups.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="1f8ba-132">[Manage group membership in the Microsoft 365 admin center](add-or-remove-members-from-groups.md) (article)</span></span>
  
<span data-ttu-id="1f8ba-133">[Azure Active Directoryアクセスレビュー](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (記事)</span><span class="sxs-lookup"><span data-stu-id="1f8ba-133">[Azure Active Directory access reviews](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (article)</span></span>

<span data-ttu-id="1f8ba-134">[セット-AzureADUser](/powershell/module/azuread/set-azureaduser) (記事)</span><span class="sxs-lookup"><span data-stu-id="1f8ba-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (article)</span></span>