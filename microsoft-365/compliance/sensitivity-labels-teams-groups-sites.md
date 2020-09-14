---
title: Microsoft Teams、Microsoft 365 グループ、SharePoint サイトで秘密度ラベルを使用する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 秘密度ラベルを使用して、SharePoint サイト、Microsoft Teams サイト、Microsoft 365 グループのコンテンツを保護します。
ms.openlocfilehash: b81d598c3a80a915d9d20622a1b6d2e6f4517883
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547689"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="30c92-103">秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する</span><span class="sxs-lookup"><span data-stu-id="30c92-103">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

><span data-ttu-id="30c92-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="30c92-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="30c92-105">[秘密度ラベル](sensitivity-labels.md) を使用して、ドキュメントやメールを分類および保護するだけでなく、Microsoft Teams サイト、Microsoft 365 グループ ([以前は Office 365 グループ](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))、およびSharePoint サイトなどのコンテナーにあるコンテンツを保護するために、秘密度ラベルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="30c92-105">In addition to using [sensitivity labels](sensitivity-labels.md) to classify and protect documents and emails, you can also use sensitivity labels to protect content in the following containers: Microsoft Teams sites, Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), and SharePoint sites.</span></span> <span data-ttu-id="30c92-106">コンテナー レベルの分類と保護を設定するには、次のラベル設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="30c92-106">For this container-level classification and protection, use the following label settings:</span></span>

- <span data-ttu-id="30c92-107">Microsoft 365 グループに接続されているチーム サイトのプライバシー (パブリックまたはプライベート)</span><span class="sxs-lookup"><span data-stu-id="30c92-107">Privacy (public or private) of Microsoft 365 group-connected teams sites</span></span>
- <span data-ttu-id="30c92-108">外部ユーザーのアクセス</span><span class="sxs-lookup"><span data-stu-id="30c92-108">External users access</span></span>
- <span data-ttu-id="30c92-109">非管理対象デバイスからのアクセス</span><span class="sxs-lookup"><span data-stu-id="30c92-109">Access from unmanaged devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30c92-110">**[管理されていないデバイスからのアクセス]** 設定は、SharePoint機能と連動して、[管理されていないデバイスからのアクセスを制御します](/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="30c92-110">The **Access from unmanaged devices** setting works in conjunction with the SharePoint feature to [control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span> <span data-ttu-id="30c92-111">テナントがこの設定が構成されている機密ラベルを使用するには、この依存 SharePoint 機能を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30c92-111">You must configure this dependent SharePoint feature for your tenant to use a sensitivity label that has this setting configured.</span></span> <span data-ttu-id="30c92-112">追加情報については、以下の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30c92-112">Additional information is included in the instructions that follow.</span></span>

<span data-ttu-id="30c92-113">サポートされているコンテナーにこの秘密度ラベルを適用すると、分類および保護の設定が、接続されたサイトまたはグループに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="30c92-113">When you apply this sensitivity label to a supported container, the label automatically applies the classification and protection settings to the connected site or group.</span></span>

<span data-ttu-id="30c92-114">ただし、これらのコンテナーのコンテンツは、視覚的なマーキング、または暗号化の分類および設定のラベルを継承しません。</span><span class="sxs-lookup"><span data-stu-id="30c92-114">Content in these containers however, do not inherit the labels for the classification and settings such as visual markings, or encryption.</span></span> <span data-ttu-id="30c92-115">ユーザーが SharePoint サイトまたはチーム サイトでドキュメントにラベルを付けられるようにするには、[SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にします](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="30c92-115">So that users can label their documents in SharePoint sites or team sites, make sure you've [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

> [!NOTE]
> <span data-ttu-id="30c92-116">コンテナーの秘密度ラベルは、Office 365 のコンテンツ配信ネットワーク (CDNs) ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="30c92-116">Sensitivity labels for containers aren't supported with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="using-sensitivity-labels-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="30c92-117">Microsoft Teams、Microsoft 365 グループ、およびSharePoint サイトで秘密度ラベルを使用する</span><span class="sxs-lookup"><span data-stu-id="30c92-117">Using sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="30c92-118">コンテナーの秘密度ラベルを有効化し、新しい設定の秘密度ラベルを構成する前に、ユーザーはアプリで秘密度ラベルを表示および適用できます。</span><span class="sxs-lookup"><span data-stu-id="30c92-118">Before you enable sensitivity labels for containers and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="30c92-119">たとえば、Word から: </span><span class="sxs-lookup"><span data-stu-id="30c92-119">For example, from Word:</span></span>

![Word デスクトップ アプリに表示される機密ラベル](../media/sensitivity-label-word.png)

<span data-ttu-id="30c92-121">コンテナーの秘密度ラベルを有効にして構成すると、ユーザーは追加で秘密度ラベルを表示し、Microsoft チーム サイト、Microsoft 365 グループ、および SharePoint サイトに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="30c92-121">After you enable and configure sensitivity labels for containers, users can additionally see and apply sensitivity labels to Microsoft team sites, Microsoft 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="30c92-122">たとえば、SharePoint から新しいチーム サイトを作成する場合:</span><span class="sxs-lookup"><span data-stu-id="30c92-122">For example, when you create a new team site from SharePoint:</span></span>

![SharePoint でチーム サイトを作成するときの機密ラベル](../media/sensitivity-labels-new-team-site.png)

## <a name="how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels"></a><span data-ttu-id="30c92-124">コンテナーの秘密度ラベルを有効化してラベルを同期する方法</span><span class="sxs-lookup"><span data-stu-id="30c92-124">How to enable sensitivity labels for containers and synchronize labels</span></span>

1. <span data-ttu-id="30c92-125">この機能は Azure AD 機能を使用するため、Azure AD のドキュメント [「Azure Active Directory で Microsoft 365 グループに秘密度ラベルを割り当てる」](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels) の指示に従い、秘密度ラベルのサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="30c92-125">Because this feature uses Azure AD functionality, follow the instructions from the Azure AD documentation to enable sensitivity label support: [Assign sensitivity labels to Microsoft 365 groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="30c92-126">秘密度ラベルを Azure AD に同期することが必要になります。</span><span class="sxs-lookup"><span data-stu-id="30c92-126">You now need to synchronize your sensitivity labels to Azure AD.</span></span> <span data-ttu-id="30c92-127">まず、[セキュリティ/コンプライアンス センターの PowerShell に接続します](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="30c92-127">First, [connect to Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="30c92-128">たとえば、管理者として実行している PowerShell セッションで、グローバル管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="30c92-128">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account.</span></span>

3. <span data-ttu-id="30c92-129">秘密度ラベルを Microsoft 365 グループで使用できるように、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="30c92-129">Then run the following command to ensure your sensitivity labels can be used with Microsoft 365 groups:</span></span>

    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings"></a><span data-ttu-id="30c92-130">サイトおよびグループの設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="30c92-130">How to configure site and group settings</span></span>

<span data-ttu-id="30c92-131">これで、サイトおよびグループで使用する機密ラベルを作成または編集する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="30c92-131">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="30c92-132">コンテナーの秘密度ラベルを有効にすると、秘密度のラベル付けウィザードで新しいページが表示されます: **サイトとグループの設定**</span><span class="sxs-lookup"><span data-stu-id="30c92-132">Enabling sensitivity labels for containers makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="30c92-133">機密ラベルの作成または編集に関するヘルプが必要な場合は、「[機密ラベルを作成して構成する](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30c92-133">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="30c92-134">この新しい [**サイトとグループの設定**] ページで、設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="30c92-134">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="30c92-135">**Office 365 グループに接続されたチーム サイトのプライバシー**: このラベルが適用されているチーム サイトまたはグループに組織内の誰もがアクセスできるようにする場合は、既定の [**公開 - 組織内のすべてのユーザーがサイトにアクセスできます**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="30c92-135">**Privacy of Office 365 group-connected teams sites**: Keep the default of **Public - anyone in the organization can access the site** if you want anyone in your organization to access the team site or group where this label is applied.</span></span>

  <span data-ttu-id="30c92-136">組織内の承認されたメンバーのみにアクセスを制限する場合は、[**プライベート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="30c92-136">Select **Private** if you want access to be restricted to only approved members in your organization.</span></span>

  <span data-ttu-id="30c92-137">秘密度ラベルを使用してコンテナー内のコンテンツを保護し、ユーザーが自分でプライバシー設定を構成できるようにする場合は、[**なし - ユーザーがサイトにアクセスできるユーザーを選択できるようにします**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="30c92-137">Select **None - let user chose who can access the site** when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.</span></span>

  <span data-ttu-id="30c92-138">このラベルをコンテナーに適用すると、[**パブリック**] または [**プライベート**] の設定によってプライバシー設定が設定およびロックされます。</span><span class="sxs-lookup"><span data-stu-id="30c92-138">The settings of **Public** or **Private** set and lock the privacy setting when you apply this label to the container.</span></span> <span data-ttu-id="30c92-139">選択した設定は、チームまたはグループに構成されている可能性がある以前のプライバシー設定を置き換え、プライバシー値をロックします。これにより、コンテナーから最初に秘密度ラベルを削除することによってのみ、変更できるようになります。</span><span class="sxs-lookup"><span data-stu-id="30c92-139">Your chosen setting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container.</span></span> <span data-ttu-id="30c92-140">秘密度ラベルを削除しても、ラベルからのプライバシー設定は維持され、ユーザーは再びラベルを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="30c92-140">After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span></span>

- <span data-ttu-id="30c92-141">**外部ユーザー アクセス**: グループの所有者が[ゲストをグループに追加](/office365/admin/create-groups/manage-guest-access-in-groups)できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="30c92-141">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="30c92-142">**非管理対象デバイス**: このオプションでは、Azure ADの条件付きアクセスを使用して、管理されていないデバイスからの SharePoint および OneDrive コンテンツへのアクセスをブロックまたは制限する SharePoint 機能も構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30c92-142">**Unmanaged devices**: For this option, you must also configure the SharePoint feature that uses Azure AD conditional access to block or limit access to SharePoint and OneDrive content from unmanaged devices.</span></span> <span data-ttu-id="30c92-143">手順については、「[非管理対象デバイスからのアクセスを制御する](/sharepoint/control-access-from-unmanaged-devices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30c92-143">For instructions, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span> <span data-ttu-id="30c92-144">このラベル設定に指定するオプションは、[特定のSharePointサイトまたはOneDriveへのアクセスをブロックまたは制限する](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices#block-or-limit-access-to-a-specific-sharepoint-site-or-onedrive) ことと同等です。</span><span class="sxs-lookup"><span data-stu-id="30c92-144">The option you specify for this label setting is the equivalent of [blocking or limiting access to a specific SharePoint site or OneDrive](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices#block-or-limit-access-to-a-specific-sharepoint-site-or-onedrive).</span></span>
    
    <span data-ttu-id="30c92-145">依存する SharePoint 機能を構成しない場合、ここで指定するオプションは効果がありません。</span><span class="sxs-lookup"><span data-stu-id="30c92-145">If you don't configure the dependent SharePoint feature, the option you specify here will have no effect.</span></span> <span data-ttu-id="30c92-146">また、テナントレベルで構成された設定よりも制限が少ない場合は効果がありません。</span><span class="sxs-lookup"><span data-stu-id="30c92-146">Additionally, it will have no effect if it's less restrictive than the configured setting at the tenant level.</span></span> <span data-ttu-id="30c92-147">テナントレベルの設定と同じか、より制限的なラベル設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="30c92-147">Choose a label setting that's either the same as the tenant-level setting or more restrictive.</span></span>
    
    <span data-ttu-id="30c92-148">たとえば、テナントが [**制限されたWebのみのアクセスを許可する**] に構成されている場合、フルアクセスを許可するラベル設定は制限が少ないため、効果がありません。</span><span class="sxs-lookup"><span data-stu-id="30c92-148">For example, if your tenant is configured for **Allow limited, web-only access**, the label setting that allows full access will have no effect because it's less restrictive.</span></span> <span data-ttu-id="30c92-149">このテナントレベルの設定では、アクセスをブロックするためのラベル設定 (より制限的) または制限付きアクセスのためのラベル設定 (テナント設定と同じ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="30c92-149">For this tenant-level setting, choose the label setting to block access (more restrictive) or the label setting for limited access (the same as the tenant setting).</span></span>
    
    <span data-ttu-id="30c92-150">SharePoint 機能はラベル構成とは別に構成できるため、機密ラベルウィザードで依存関係が設定されているかどうかのチェックは行われません。</span><span class="sxs-lookup"><span data-stu-id="30c92-150">Because you can configure the SharePoint feature independently from the label configuration, there's no check in the sensitivity label wizard that the dependencies are in place.</span></span>

![[サイトとグループの設定] タブ](../media/edit-sensitivity-label-site-group2.png)

> [!IMPORTANT]
> <span data-ttu-id="30c92-152">チーム、グループ、またはサイトにラベルを適用すると、それらのサイトとグループの設定のみが有効になります。</span><span class="sxs-lookup"><span data-stu-id="30c92-152">Only these site and group settings take effect when you apply the label to a team, group, or site.</span></span> <span data-ttu-id="30c92-153">暗号化やコンテンツ マーキングなどのその他のラベル設定は、チーム、グループ、またはサイト内のコンテンツに適用されません。</span><span class="sxs-lookup"><span data-stu-id="30c92-153">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
>
> <span data-ttu-id="30c92-154">テナントへの段階的なロールアウト: ユーザーがチーム、グループ、サイトを作成するときに選択できるのは、サイトの設定およびグループの設定のラベルのみです。</span><span class="sxs-lookup"><span data-stu-id="30c92-154">Gradually rolling out to tenants: Only labels with the site and group settings will be available to select when users create teams, groups, and sites.</span></span> <span data-ttu-id="30c92-155">ラベルにサイトとグループの設定が有効になっていないときに、ラベルをコンテナーに適用する場合は、ラベル名のみがコンテナーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="30c92-155">If you can currently apply a label to a container when the label doesn't have the site and group settings enabled, only the label name is applied to the container.</span></span>

<span data-ttu-id="30c92-156">秘密度ラベルがまだ公開されていない場合は、[秘密度ラベル ポリシーに追加](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)して公開します。</span><span class="sxs-lookup"><span data-stu-id="30c92-156">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="30c92-157">このラベルを含む秘密度ラベル ポリシーが割り当てられているユーザーには、サイトとグループ用にそのラベルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="30c92-157">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

<span data-ttu-id="30c92-158">このラベルをコンテナーに適用する場合、ラベル ポリシーからは、ポリシー設定 **[既定でドキュメントとメールにこのラベルを適用する]** のみが適用されます。</span><span class="sxs-lookup"><span data-stu-id="30c92-158">From the label policy, only the policy setting **Apply this label by default to documents and email** is applicable when you apply this label to containers.</span></span> <span data-ttu-id="30c92-159">必須のラベル付け、ユーザーの妥当性の要求、カスタム ヘルプ ページへのリンクなど、他のポリシー設定は適用されません。</span><span class="sxs-lookup"><span data-stu-id="30c92-159">Other policy settings are not applied, which include mandatory labeling, requiring user justification, and a link to the custom help page.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="30c92-160">機密ラベルの管理</span><span class="sxs-lookup"><span data-stu-id="30c92-160">Sensitivity label management</span></span>

<span data-ttu-id="30c92-161">サイトとグループに対して構成されている秘密度ラベルを作成、変更、または削除する場合は、次のガイダンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="30c92-161">Use the following guidance for when you create, modify, or delete sensitivity labels that are configured for sites and groups.</span></span>

### <a name="creating-and-publishing-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="30c92-162">サイトとグループに対して構成されているラベルを作成して発行する</span><span class="sxs-lookup"><span data-stu-id="30c92-162">Creating and publishing labels that are configured for sites and groups</span></span>

<span data-ttu-id="30c92-163">新しい機密ラベルを作成して公開すると、チーム、グループ、およびサイトでユーザーには、1 時間以内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="30c92-163">When a new sensitivity label is created and published, it's visible for users in teams, groups, and sites within one hour.</span></span> <span data-ttu-id="30c92-164">ただし、既存のラベルを変更する場合は、最大で 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="30c92-164">However, if you modify an existing label, allow up to 24 hours.</span></span> <span data-ttu-id="30c92-165">このラベルがサイトおよびグループの設定に対して構成されている場合、次のガイダンスを使用して、ユーザーのラベルを発行します。</span><span class="sxs-lookup"><span data-stu-id="30c92-165">Use the following guidance to publish a label for your users when that label is configured for site and group settings:</span></span>

1. <span data-ttu-id="30c92-166">秘密度ラベルを作成し構成したら、少数のテスト ユーザーにのみ適用されるラベル ポリシーにこのラベルを追加します。</span><span class="sxs-lookup"><span data-stu-id="30c92-166">After you create and configure the sensitivity label, add this label to a label policy that applies to just a few test users.</span></span>

2. <span data-ttu-id="30c92-167">変更がレプリケートされるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="30c92-167">Wait for the change to replicate:</span></span>

   - <span data-ttu-id="30c92-168">新規ラベル: 1 時間待機します。</span><span class="sxs-lookup"><span data-stu-id="30c92-168">New label: Wait for one hour.</span></span>
   - <span data-ttu-id="30c92-169">既存のラベル: 24 時間待機します。</span><span class="sxs-lookup"><span data-stu-id="30c92-169">Existing label: Wait for 24 hours.</span></span>

3. <span data-ttu-id="30c92-170">この待ち時間の後、テスト ユーザー アカウントのいずれかを使用して、手順 1 で作成したラベルを持つチーム、Microsoft 365 グループ、または SharePoint サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="30c92-170">After this wait period, use one of the test user accounts to create a team, Microsoft 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="30c92-171">この作成操作中にエラーが発生しなかった場合、テナント内のすべてのユーザーに安全にラベルを発行できます。</span><span class="sxs-lookup"><span data-stu-id="30c92-171">If there are no errors during this creation operation, you know it's safe to publish the label to all users in your tenant.</span></span>

### <a name="modifying-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="30c92-172">サイトとグループに対して構成されている発行済みのラベルを変更する</span><span class="sxs-lookup"><span data-stu-id="30c92-172">Modifying published labels that are configured for sites and groups</span></span>

<span data-ttu-id="30c92-173">ベスト プラクティスとして、秘密度ラベルを複数のチーム、グループ、またはサイトに適用した後に、ラベルのサイトとグループの設定を変更しないようにします。</span><span class="sxs-lookup"><span data-stu-id="30c92-173">As a best practice, don't change the site and group settings for a sensitivity label after the label has been applied to teams, groups, or sites.</span></span> <span data-ttu-id="30c92-174">この場合、ラベルが適用されているすべてのコンテナーに変更を複製されるまで 24 時間待機することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="30c92-174">If you do, remember to wait for 24 hours for the changes to replicate to all containers that have the label applied.</span></span>

<span data-ttu-id="30c92-175">また、**外部ユーザーのアクセス** 設定を含む変更は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="30c92-175">In addition, if your changes include the **External users access** setting:</span></span>

- <span data-ttu-id="30c92-176">新しい設定は新しいユーザーに適用されますが、既存のユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="30c92-176">The new setting applies to new users but not to existing users.</span></span> <span data-ttu-id="30c92-177">たとえば、この設定は以前に選択されていて、その結果、ゲスト ユーザーがサイトにアクセスした場合、この設定をラベル構成で解除した後も、これらのゲスト ユーザーはサイトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="30c92-177">For example, if this setting was previously selected and as a result, guest users accessed the site, these guest users can still access the site after this setting is cleared in the label configuration.</span></span>

- <span data-ttu-id="30c92-178">HiddenMembership および roleEnabled グループ プロパティのプライバシー設定は更新されません。</span><span class="sxs-lookup"><span data-stu-id="30c92-178">The privacy settings for the group properties hiddenMembership and roleEnabled aren't updated.</span></span>

### <a name="deleting-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="30c92-179">サイトとグループに対して構成されている発行済みラベルを削除する</span><span class="sxs-lookup"><span data-stu-id="30c92-179">Deleting published labels that are configured for sites and groups</span></span>

<span data-ttu-id="30c92-180">サイトとグループの設定を有効にして秘密度ラベルの削除を行い、そのラベルが 1 つ以上のラベル ポリシーに含まれている場合、新しいチーム、グループ、サイトの作成に失敗してしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="30c92-180">If you delete a sensitivity label that has the site and group settings enabled, and that label is included in one or more label policies, this action can result in creation failures for new teams, groups, and sites.</span></span> <span data-ttu-id="30c92-181">この状況を回避するには、以下のガイダンスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="30c92-181">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="30c92-182">ラベルを含むすべてのラベル ポリシーから、機密ラベルを削除します。</span><span class="sxs-lookup"><span data-stu-id="30c92-182">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="30c92-183">1 時間待機します。</span><span class="sxs-lookup"><span data-stu-id="30c92-183">Wait for one hour.</span></span>

3. <span data-ttu-id="30c92-184">この待ち時間の後、チーム、グループ、またはサイトを作成し、ラベルが表示されなくなったことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="30c92-184">After this wait period, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="30c92-185">秘密度ラベルが表示されていない場合は、ラベルを安全に削除できます。</span><span class="sxs-lookup"><span data-stu-id="30c92-185">If the sensitivity label isn't visible, you can now safely delete the label.</span></span>

## <a name="how-to-apply-sensitivity-labels-to-containers"></a><span data-ttu-id="30c92-186">コンテナーに秘密度ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="30c92-186">How to apply sensitivity labels to containers</span></span>

<span data-ttu-id="30c92-187">これで、１つまたは複数の秘密度ラベルを次のようなコンテナーに適用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="30c92-187">You're now ready to apply the sensitivity label or labels to the following containers:</span></span>

- [<span data-ttu-id="30c92-188">Azure AD の Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="30c92-188">Microsoft 365 group in Azure AD</span></span>](#apply-sensitivity-labels-to-microsoft-365-groups)
- [<span data-ttu-id="30c92-189">Microsoft Teams のチーム サイト</span><span class="sxs-lookup"><span data-stu-id="30c92-189">Microsoft Teams team site</span></span>](#apply-a-sensitivity-label-to-a-new-team)
- [<span data-ttu-id="30c92-190">Outlook on the web の Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="30c92-190">Microsoft 365 group in Outlook on the web</span></span>](#apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web)
- [<span data-ttu-id="30c92-191">SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="30c92-191">SharePoint site</span></span>](#apply-a-sensitivity-label-to-a-new-site)

<span data-ttu-id="30c92-192">[複数のサイトに秘密度ラベルを適用する](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites) 必要がある場合、PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="30c92-192">You can use PowerShell if you need to [apply a sensitivity label to multiple sites](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites).</span></span>

### <a name="apply-sensitivity-labels-to-microsoft-365-groups"></a><span data-ttu-id="30c92-193">Microsoft 365 グループに秘密度ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="30c92-193">Apply sensitivity labels to Microsoft 365 groups</span></span>

<span data-ttu-id="30c92-194">これで、1 つまたは複数の秘密度ラベルを Microsoft 365 グループに適用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="30c92-194">You're now ready to apply the sensitivity label or labels to Microsoft 365 groups.</span></span> <span data-ttu-id="30c92-195">手順については、Azure AD のドキュメントに戻ります。</span><span class="sxs-lookup"><span data-stu-id="30c92-195">Return to the Azure AD documentation for instructions:</span></span>

- <span data-ttu-id="30c92-196">「[Assign a label to a new group in Azure portal (Azure ポータルの新しいグループにラベルを割り当てる)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)」</span><span class="sxs-lookup"><span data-stu-id="30c92-196">[Assign a label to a new group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)</span></span>

- [<span data-ttu-id="30c92-197">Assign a label to an existing group in Azure portal (Azure ポータルの既存のグループにラベルを割り当てる)</span><span class="sxs-lookup"><span data-stu-id="30c92-197">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

- <span data-ttu-id="30c92-198">「[Remove a label from an existing group in Azure portal (Azure ポータルの既存のグループからラベルを削除する)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).」</span><span class="sxs-lookup"><span data-stu-id="30c92-198">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="30c92-199">新しいチームに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="30c92-199">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="30c92-200">ユーザーは、Microsoft Teams で新しいチームを作成する際に機密ラベルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="30c92-200">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="30c92-201">**[秘密度]** ドロップダウンからラベルを選択すると、プライバシー設定によってラベル構成が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="30c92-201">When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration.</span></span> <span data-ttu-id="30c92-202">ラベルに対し選択した外部ユーザーのアクセス設定に応じて、ユーザーは組織外のユーザーをチームに追加することができたり、できなかったりします。</span><span class="sxs-lookup"><span data-stu-id="30c92-202">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="30c92-203">Teams の機密ラベルの詳細について</span><span class="sxs-lookup"><span data-stu-id="30c92-203">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![新しいチームを作成する際のプライバシー設定](../media/privacy-setting-new-team.png)

<span data-ttu-id="30c92-205">チームを作成すると、すべてのチャネルの右上隅に機密ラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30c92-205">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![チームに表示される機密ラベル](../media/privacy-setting-teams.png)

<span data-ttu-id="30c92-207">このサービスは、Microsoft 365 グループおよび接続された SharePoint チーム サイトに対して同じ秘密度ラベルを自動的に適用します。</span><span class="sxs-lookup"><span data-stu-id="30c92-207">The service automatically applies the same sensitivity label to the Microsoft 365 group and the connected SharePoint team site.</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="30c92-208">Outlook on the web の新しいグループに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="30c92-208">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="30c92-209">Outlook on the web では、新しいグループを作成するときに、公開されたラベルの [**機密**] オプションを選択または変更できます。</span><span class="sxs-lookup"><span data-stu-id="30c92-209">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![グループを作成し、[機密] 下でオプションを選択する](../media/sensitivity-label-new-group.png)

### <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="30c92-211">新しいサイトに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="30c92-211">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="30c92-212">管理者およびエンド ユーザーは、[最新のチーム サイトやコミュニケーション サイトを作成する](/sharepoint/create-site-collection)際に秘密度ラベルを選択し、以下のような**詳細設定**を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="30c92-212">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection), and expand **Advanced settings**:</span></span>

![サイトを作成し、[秘密度] 下でオプションを選択する](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="30c92-214">ドロップダウン ボックスには選択したラベル名が表示され、ヘルプ アイコンにはすべてのラベル名とヒントが表示されます。これにより、ユーザーは適用するラベルを正しく選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="30c92-214">The dropdown box displays the label names for the selection, and the help icon displays all the label names with their tooltip, which can help users determine the correct label to apply.</span></span>

<span data-ttu-id="30c92-215">ラベルが適用され、ユーザーがサイトを参照すると、ラベルの名前および適用されているポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30c92-215">When the label is applied, and users browse to the site, they see the name of the label and applied policies.</span></span> <span data-ttu-id="30c92-216">たとえば、以下のサイトでは、**秘密**のラベル付けがされており、プライバシー設定は**プライベート**になっています。</span><span class="sxs-lookup"><span data-stu-id="30c92-216">For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span></span>

![機密ラベルが適用されているサイト](../media/sensitivity-label-site.png)

### <a name="use-powershell-to-apply-a-sensitivity-label-to-multiple-sites"></a><span data-ttu-id="30c92-218">PowerShell を使用して、複数のサイトに秘密度ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="30c92-218">Use PowerShell to apply a sensitivity label to multiple sites</span></span>

<span data-ttu-id="30c92-219">[Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) と [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) コマンドレットを使用して、現在の [SharePoint Online 管理シェル](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)の *SensitivityLabel* パラメーターによって、多くのサイトに秘密度ラベルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="30c92-219">You can use the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) and [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) cmdlet with the *SensitivityLabel* parameter from the current [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) to apply a sensitivity label to many sites.</span></span> <span data-ttu-id="30c92-220">サイトには、任意の SharePoint サイトコレクション、または OneDrive サイトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="30c92-220">The sites can be any SharePoint site collection, or a OneDrive site.</span></span>

<span data-ttu-id="30c92-221">SharePoint Online 管理シェルのバージョン16.0.19418.12000 以降があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="30c92-221">Make sure you have version 16.0.19418.12000 or later of the SharePoint Online Management Shell.</span></span>

1. <span data-ttu-id="30c92-222">**[管理者として実行]** オプションを使用して PowerShell セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="30c92-222">Open a PowerShell session with the **Run as Administrator** option.</span></span>

2. <span data-ttu-id="30c92-223">ラベルの GUID がわからない場合、[セキュリティ/コンプライアンス センターの PowerShellに接続し](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)、秘密度ラベルとそれらの GUID のリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="30c92-223">If you don't know your label GUID: [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and get the list of sensitivity labels and their GUIDs.</span></span>

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. <span data-ttu-id="30c92-224">ここでは、[SharePoint Online PowerShellに接続して](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)、ラベルの GUID を変数として保存します。</span><span class="sxs-lookup"><span data-stu-id="30c92-224">Now [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and store your label GUID as a variable.</span></span> <span data-ttu-id="30c92-225">例:</span><span class="sxs-lookup"><span data-stu-id="30c92-225">For example:</span></span>

   ```powershell
   $Id = [GUID]("e48058ea-98e8-4940-8db0-ba1310fd955e")
   ```

4. <span data-ttu-id="30c92-226">URL に共通の識別文字列が含まれる複数のサイトを特定する新しい変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="30c92-226">Create a new variable that identifies multiple sites that have an identifying string in common in their URL.</span></span> <span data-ttu-id="30c92-227">例:</span><span class="sxs-lookup"><span data-stu-id="30c92-227">For example:</span></span>

   ```powershell
   $sites = Get-SPOSite -IncludePersonalSite $true -Limit all -Filter "Url -like 'documents"
   ```

5. <span data-ttu-id="30c92-228">これらのサイトにラベルを適用するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="30c92-228">Run the following command to apply the label to these sites.</span></span> <span data-ttu-id="30c92-229">サンプルを使用します。</span><span class="sxs-lookup"><span data-stu-id="30c92-229">Using our examples:</span></span>

   ```powershell
   $sites | ForEach-Object {Set-SPOTenant $_.url -SensitivityLabel $Id}
   ```

<span data-ttu-id="30c92-230">異なるサイトに異なるラベルを適用するには、各サイトで次のコマンドを繰り返します。 `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span><span class="sxs-lookup"><span data-stu-id="30c92-230">To apply different labels to different sites, repeat the following command for each site: `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span></span>

## <a name="view-and-manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="30c92-231">SharePoint 管理センターで秘密度ラベルを表示し管理する</span><span class="sxs-lookup"><span data-stu-id="30c92-231">View and manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="30c92-232">適用された秘密度ラベルを表示、並べ替え、および検索するには、新しい SharePoint 管理センターの [**アクティブなサイト**] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="30c92-232">To view, sort, and search the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="30c92-233">最初に、[**機密**] 列を追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="30c92-233">You might need to first add the **Sensitivity** column:</span></span>

![[アクティブなサイト] ページの [機密] 列](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="30c92-235">列を追加する方法など、[アクティブなサイト] ページからサイトを管理する方法の詳細については、「[新しい SharePoint 管理センターでサイトを管理する](/sharepoint/manage-sites-in-new-admin-center)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30c92-235">For more information about managing sites from the Active sites page, including how to add a column, see [Manage sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

<span data-ttu-id="30c92-236">このページからラベルを変更して適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="30c92-236">You can also change and apply a label from this page:</span></span>

1. <span data-ttu-id="30c92-237">[詳細] ウィンドウを開くには、サイト名を選択します。</span><span class="sxs-lookup"><span data-stu-id="30c92-237">Select the site name to open the details pane.</span></span>

2. <span data-ttu-id="30c92-238">[**ポリシー**] タブを選択し、**秘密度** の設定で [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="30c92-238">Select the **Policies** tab, and then select **Edit** for the **Sensitivity** setting.</span></span>

3. <span data-ttu-id="30c92-239">[**秘密度の設定の編集**] ウィンドウで、サイトに適用する秘密度ラベルを選び、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="30c92-239">From the **Edit sensitivity setting** pane, select the sensitivity label you want to apply to the site, and then select **Save**.</span></span>

## <a name="support-for-sensitivity-labels"></a><span data-ttu-id="30c92-240">秘密度ラベルのサポート</span><span class="sxs-lookup"><span data-stu-id="30c92-240">Support for sensitivity labels</span></span>

<span data-ttu-id="30c92-241">次のアプリとサービスで、サイトとグループの設定用に構成した秘密度ラベルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="30c92-241">The following apps and services support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="30c92-242">管理センター:</span><span class="sxs-lookup"><span data-stu-id="30c92-242">Admin centers:</span></span>

  - <span data-ttu-id="30c92-243">SharePoint 管理センター</span><span class="sxs-lookup"><span data-stu-id="30c92-243">SharePoint admin center</span></span>
  - <span data-ttu-id="30c92-244">Azure Active Directory ポータル</span><span class="sxs-lookup"><span data-stu-id="30c92-244">Azure Active Directory portal</span></span>
  - <span data-ttu-id="30c92-245">Microsoft 365 コンプライアンス センター、Microsoft 365 セキュリティ センター、セキュリティ/コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="30c92-245">Microsoft 365 compliance center, Microsoft 365 security center, Security & Compliance Center</span></span>

- <span data-ttu-id="30c92-246">ユーザーのアプリとサービス:</span><span class="sxs-lookup"><span data-stu-id="30c92-246">User apps and services:</span></span>

  - <span data-ttu-id="30c92-247">SharePoint</span><span class="sxs-lookup"><span data-stu-id="30c92-247">SharePoint</span></span>
  - <span data-ttu-id="30c92-248">Teams</span><span class="sxs-lookup"><span data-stu-id="30c92-248">Teams</span></span>
  - <span data-ttu-id="30c92-249">Outlook on the web and for Windows、MacOS、iOS、および Android</span><span class="sxs-lookup"><span data-stu-id="30c92-249">Outlook on the web and for Windows, MacOS, iOS, and Android</span></span>
  - <span data-ttu-id="30c92-250">フォーム</span><span class="sxs-lookup"><span data-stu-id="30c92-250">Forms</span></span>
  - <span data-ttu-id="30c92-251">Stream</span><span class="sxs-lookup"><span data-stu-id="30c92-251">Stream</span></span>

<span data-ttu-id="30c92-252">次のアプリとサービスで、サイトとグループの設定用に構成した秘密度ラベルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="30c92-252">The following apps and services don't currently support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="30c92-253">管理センター:</span><span class="sxs-lookup"><span data-stu-id="30c92-253">Admin centers:</span></span>

  - <span data-ttu-id="30c92-254">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="30c92-254">Microsoft 365 admin center</span></span>
  - <span data-ttu-id="30c92-255">Teams 管理センター</span><span class="sxs-lookup"><span data-stu-id="30c92-255">Teams admin center</span></span>
  - <span data-ttu-id="30c92-256">Exchange 管理センター</span><span class="sxs-lookup"><span data-stu-id="30c92-256">Exchange admin center</span></span>

- <span data-ttu-id="30c92-257">ユーザーのアプリとサービス:</span><span class="sxs-lookup"><span data-stu-id="30c92-257">User apps and services:</span></span>

  - <span data-ttu-id="30c92-258">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="30c92-258">Dynamics 365</span></span>
  - <span data-ttu-id="30c92-259">Yammer</span><span class="sxs-lookup"><span data-stu-id="30c92-259">Yammer</span></span>
  - <span data-ttu-id="30c92-260">Planner</span><span class="sxs-lookup"><span data-stu-id="30c92-260">Planner</span></span>
  - <span data-ttu-id="30c92-261">Project</span><span class="sxs-lookup"><span data-stu-id="30c92-261">Project</span></span>
  - <span data-ttu-id="30c92-262">Power BI</span><span class="sxs-lookup"><span data-stu-id="30c92-262">Power BI</span></span>

## <a name="classic-azure-ad-group-classification"></a><span data-ttu-id="30c92-263">従来の Azure AD グループの分類</span><span class="sxs-lookup"><span data-stu-id="30c92-263">Classic Azure AD group classification</span></span>

<span data-ttu-id="30c92-264">コンテナーの秘密度ラベルを有効にすると、Microsoft 365 は新しい Microsoft 365 のグループおよび SharePoint サイト向けに古い分類をサポートしなくなります。</span><span class="sxs-lookup"><span data-stu-id="30c92-264">Microsoft 365 no longer supports the old classifications for new Microsoft 365 groups and SharePoint sites after you enable sensitivity labels for containers.</span></span> <span data-ttu-id="30c92-265">ただし、秘密度ラベルをサポートしている既存のグループおよびサイトには、秘密度ラベルを使用するように変換しない限り、古い分類値が引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="30c92-265">However, existing groups and sites that support sensitivity labels still display the old classification values until you convert them to use sensitivity labels.</span></span>

<span data-ttu-id="30c92-266">SharePoint の古いグループ分類を使用した場合の例として、「[SharePoint の "モダン" サイトの分類」](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30c92-266">As an example of how you might have used the old group classification for SharePoint, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="30c92-267">これらの分類は、Azure AD PowerShell または PnP コア ライブラリを使用し、`ClassificationList` 設定に値を定義することによって構成されています。</span><span class="sxs-lookup"><span data-stu-id="30c92-267">These classifications were configured by using Azure AD PowerShell or the PnP Core library and defining values for the `ClassificationList` setting.</span></span> <span data-ttu-id="30c92-268">テナントに分類値が定義されている場合は、[AzureADPreview PowerShell モジュール](https://www.powershellgallery.com/packages/AzureADPreview)から次のコマンドを実行すると、それらが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30c92-268">If your tenant has classification values defined, they are shown when you run the following command from the [AzureADPreview PowerShell module](https://www.powershellgallery.com/packages/AzureADPreview):</span></span>

```powershell
($setting["ClassificationList"])
```

<span data-ttu-id="30c92-269">古い分類を機密ラベルに変換するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="30c92-269">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="30c92-270">既存のラベルを使用: 既に公開されている既存の機密ラベルを編集して、サイトおよびグループに必要なラベル設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="30c92-270">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="30c92-271">新しいラベルの作成: 既存の分類と同じ名前を持つ新しい機密ラベルを作成および公開して、サイトおよびグループに必要なラベル設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="30c92-271">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="30c92-272">その後で以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="30c92-272">Then:</span></span>

1. <span data-ttu-id="30c92-273">PowerShell を使用し、既存の Microsoft 365 グループおよび SharePoint サイトに名前のマッピングを使用して秘密度ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="30c92-273">Use PowerShell to apply the sensitivity labels to existing Microsoft 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="30c92-274">手順については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="30c92-274">See the next section for instructions.</span></span>

2. <span data-ttu-id="30c92-275">既存のグループおよびサイトから古い分類を削除します。</span><span class="sxs-lookup"><span data-stu-id="30c92-275">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="30c92-276">機密ラベルをまだサポートしていないアプリやサービスでユーザーが新しいグループを作成できないようにすることはできませんが、定期的な PowerShell スクリプトを実行して、ユーザーが古い分類で作成した新しいグループを探し、機密ラベルを使用するようにそれらを変換することができます。</span><span class="sxs-lookup"><span data-stu-id="30c92-276">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span>

<span data-ttu-id="30c92-277">サイトとグループの秘密度ラベルと Azure AD の分類の共存を管理する方法については、「[Microsoft 365 グループの Azure Active Directory の分類と秘密度ラベル](migrate-aad-classification-sensitivity-labels.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30c92-277">To help you manage the coexistence of sensitivity labels and Azure AD classifications for sites and groups, see [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](migrate-aad-classification-sensitivity-labels.md).</span></span>

### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a><span data-ttu-id="30c92-278">PowerShell を使用して Microsoft 365 グループの分類を秘密度ラベルに変換する</span><span class="sxs-lookup"><span data-stu-id="30c92-278">Use PowerShell to convert classifications for Microsoft 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="30c92-279">まず、[セキュリティ/コンプライアンス センターの PowerShell に接続します](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="30c92-279">First, [connect to Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="30c92-280">たとえば、管理者として実行している PowerShell セッションで、グローバル管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="30c92-280">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>

2. <span data-ttu-id="30c92-281">[Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label) コマンドレットを使用して、機密ラベルおよびその GUID のリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="30c92-281">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label) cmdlet:</span></span>

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. <span data-ttu-id="30c92-282">Microsoft 365 グループに適用する秘密度ラベルの GUID をメモします。</span><span class="sxs-lookup"><span data-stu-id="30c92-282">Make a note of the GUIDs for the sensitivity labels you want to apply to your Microsoft 365 groups.</span></span>

4. <span data-ttu-id="30c92-283">ここでは、別の Windows PowerShell ウィンドウで [Exchange Online PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="30c92-283">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) in a separate Windows PowerShell window.</span></span>

5. <span data-ttu-id="30c92-284">次のコマンドを例として使用して、現在 "一般" の分類を持つグループのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="30c92-284">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="30c92-285">グループごとに、新しい機密ラベル GUID を追加します。</span><span class="sxs-lookup"><span data-stu-id="30c92-285">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="30c92-286">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="30c92-286">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. <span data-ttu-id="30c92-287">残りのグループ分類について、手順 5 と 6 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="30c92-287">Repeat steps 5 and 6 for your remaining group classifications.</span></span>

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="30c92-288">機密ラベル アクティビティの監査</span><span class="sxs-lookup"><span data-stu-id="30c92-288">Auditing sensitivity label activities</span></span>

<span data-ttu-id="30c92-289">誰かが機密ラベルで保護されているサイトにドキュメントをアップロードし、そのドキュメントの機密ラベルが、サイトに適用されている機密ラベルよりも[優先度が高く](sensitivity-labels.md#label-priority-order-matters)なっている場合、このアクションはブロックされません。</span><span class="sxs-lookup"><span data-stu-id="30c92-289">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="30c92-290">たとえば、「**一般**」ラベルを SharePoint サイトに適用し、誰かがこのサイトに「**社外秘**」というラベルの付けられたドキュメントをアップロードしたとします。</span><span class="sxs-lookup"><span data-stu-id="30c92-290">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="30c92-291">優先度の高い機密ラベルは、優先順位の低いコンテンツよりも機密性の高いコンテンツを識別するため、この状況はセキュリティ上の懸念になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="30c92-291">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="30c92-292">アクションはブロックされていませんが、監査され、ドキュメントをアップロードした人とサイト管理者にメールが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="30c92-292">Although the action isn't blocked, it is audited and automatically generates an email to the person who uploaded the document and the site administrator.</span></span> <span data-ttu-id="30c92-293">結果として、ユーザーと管理者の両方が、この不適切なラベルの優先順位を設定し、必要に書類を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="30c92-293">As a result, both the user and administrators can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="30c92-294">たとえば、アップロードされたドキュメントをサイトから削除または移動します。</span><span class="sxs-lookup"><span data-stu-id="30c92-294">For example, delete or move the uploaded document from the site.</span></span>

<span data-ttu-id="30c92-295">ドキュメントの機密ラベルが、サイトに適用されている機密ラベルよりも優先度が低い場合、セキュリティ上の懸念にはなりません。</span><span class="sxs-lookup"><span data-stu-id="30c92-295">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="30c92-296">たとえば、「**一般**」というラベルの付いたドキュメントが、「**社外秘**」というラベルの付いたサイトにアップロードされている場合です。</span><span class="sxs-lookup"><span data-stu-id="30c92-296">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="30c92-297">このシナリオでは、監査イベントとメールが生成されません。</span><span class="sxs-lookup"><span data-stu-id="30c92-297">In this scenario, an auditing event and email aren't generated.</span></span>

<span data-ttu-id="30c92-298">このイベントの監査ログを検索するには、[**ファイルとページのアクティビティ**] カテゴリから [**検出されたドキュメントの機密度の不一致**] を探します。</span><span class="sxs-lookup"><span data-stu-id="30c92-298">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span>

<span data-ttu-id="30c92-299">自動生成されたメールには、サブジェクト **の互換性がない秘密度ラベルが検出されました**とメールメッセージは、アップロードされたドキュメントとサイトへのリンクとのラベルの不一致を説明します。</span><span class="sxs-lookup"><span data-stu-id="30c92-299">The automatically generated email has the subject **Incompatible sensitivity label detected** and the email message explains the labeling mismatch with a link to the uploaded document and site.</span></span> <span data-ttu-id="30c92-300">ユーザーが感度ラベルを変更できるようにするドキュメントリンクも含まれています。</span><span class="sxs-lookup"><span data-stu-id="30c92-300">It also contains a documentation link that explains how users can change the sensitivity label.</span></span> <span data-ttu-id="30c92-301">現在、これらの自動メールは無効にすることも、カスタマイズすることができません。</span><span class="sxs-lookup"><span data-stu-id="30c92-301">Currently, these automated emails cannot be disabled or customized.</span></span>

<span data-ttu-id="30c92-302">サイトまたはグループに対して、または、ある人が機密ラベルを追加または削除する場合、これらのアクティビティも監査されますが、メールは自動的に生成されません。</span><span class="sxs-lookup"><span data-stu-id="30c92-302">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited but without automatically generating an email.</span></span>

<span data-ttu-id="30c92-303">これらの監査イベントはすべて、[秘密ラベルのアクティビティ](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) カテゴリに記載されています。</span><span class="sxs-lookup"><span data-stu-id="30c92-303">All these auditing events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> <span data-ttu-id="30c92-304">監査ログを検索する手順については、「[セキュリティ/コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30c92-304">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="how-to-disable-sensitivity-labels-for-containers"></a><span data-ttu-id="30c92-305">コンテナーの秘密度ラベルを無効にする方法</span><span class="sxs-lookup"><span data-stu-id="30c92-305">How to disable sensitivity labels for containers</span></span>

<span data-ttu-id="30c92-306">「[PowerShell で秘密度ラベルのサポートを有効にする](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell)」と同じ手順で、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトの秘密度ラベルをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="30c92-306">You can turn off sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="30c92-307">ただし、この機能を無効にするには、手順5で `$setting["EnableMIPLabels"] = "False"`を指定します。</span><span class="sxs-lookup"><span data-stu-id="30c92-307">However, to disable the feature, in step 5, specify `$setting["EnableMIPLabels"] = "False"`.</span></span>

<span data-ttu-id="30c92-308">秘密度ラベルを作成または編集しているときに、**サイトとグループの設定** ページが非表示になるだけでなく、この操作では、コンテナーが構成に使用するプロパティは元に戻ります。</span><span class="sxs-lookup"><span data-stu-id="30c92-308">In addition to hiding the **Sites and group settings** page when you create or edit sensitivity labels, this action reverts which property the containers use for their configuration.</span></span> <span data-ttu-id="30c92-309">Microsoft Teams、Microsoft 365 グループ、SharePoint サイトで秘密度ラベルを有効にすると、**分類** ([Azure AD グループの分類](#classic-azure-ad-group-classification) に使用) に使用されているプロパティが **秘密度** に切り替わります。</span><span class="sxs-lookup"><span data-stu-id="30c92-309">Enabling sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites switches the property used from **Classification** (used for [Azure AD group classification](#classic-azure-ad-group-classification)) to **Sensitivity**.</span></span> <span data-ttu-id="30c92-310">コンテナーの秘密度ラベルを無効にすると、コンテナーは秘密度プロパティを無視して、もう一度分類プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="30c92-310">When you disable sensitivity labels for containers, the containers ignore the Sensitivity property and use the Classification property again.</span></span>

<span data-ttu-id="30c92-311">つまり、以前コンテナーに適用されたサイトとグループのラベル設定が適用されなくなり、コンテナーにはラベルが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="30c92-311">This means that any label settings from sites and groups previously applied to containers won't be enforced, and containers no longer display the labels.</span></span>

<span data-ttu-id="30c92-312">これらのコンテナーに Azure AD 分類値が適用されている場合、コンテナーは再び分類を使用します。</span><span class="sxs-lookup"><span data-stu-id="30c92-312">If these containers have Azure AD classification values applied to them, the containers revert to using the classifications again.</span></span> <span data-ttu-id="30c92-313">この機能を有効にした後に作成された新しいサイトやグループにはラベルが表示されず、分類もされないので注意してください。</span><span class="sxs-lookup"><span data-stu-id="30c92-313">Be aware that any new sites or groups that were created after enabling the feature won't display a label or have a classification.</span></span> <span data-ttu-id="30c92-314">これらのコンテナー、および新しいコンテナーの場合、分類値を適用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="30c92-314">For these containers, and any new containers, you can now apply classification values.</span></span> <span data-ttu-id="30c92-315">詳細については、「[SharePoint の 「最新の」 サイト分類](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)」 および 「[組織の Office グループの分類を作成する](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)」 を参照してください。。</span><span class="sxs-lookup"><span data-stu-id="30c92-315">For more information, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification) and [Create classifications for Office groups in your organization](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="30c92-316">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="30c92-316">Additional resources</span></span>

<span data-ttu-id="30c92-317">[Microsoft Teams、O365 グループおよび SharePoint Online サイトでの秘密度ラベルの使用](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380)については、ウェビナーのレコーディングと回答をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="30c92-317">See the webinar recording and answered questions for [Using Sensitivity labels with Microsoft Teams, O365 Groups and SharePoint Online sites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span></span>

<span data-ttu-id="30c92-318">このウェビナーは、当該機能がまだプレビューに含まれているときに記録されているので、UI にいくつかの矛盾が見つかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="30c92-318">This webinar was recorded when the feature was still in preview, so you might notice some discrepancies in the UI.</span></span> <span data-ttu-id="30c92-319">ただし、このページに記載されている新しい機能があれば、この機能の情報は正確です。</span><span class="sxs-lookup"><span data-stu-id="30c92-319">However, the information for this feature is still accurate, with any new capabilities documented on this page.</span></span>
