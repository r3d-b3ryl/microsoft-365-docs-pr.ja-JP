---
title: Microsoft Teams、Office 365 グループ、SharePoint サイトで機密ラベルを使用する (パブリック プレビュー)
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
description: Microsoft Teams、Office 365 グループ、SharePoint サイトにラベルを適用することができます。
ms.openlocfilehash: 1e08df688a62d6c15ef0100b5379e62482ed7b50
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372035"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="a22c1-103">Microsoft Teams、Office 365 グループ、SharePoint サイトで機密ラベルを使用する (パブリック プレビュー)</span><span class="sxs-lookup"><span data-stu-id="a22c1-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="a22c1-104">[Microsoft 365 コンプライアンス センター](https://protection.office.com/)で機密ラベルを作成する場合、次のコンテナーへと適用できるようになりました: Microsoft Teams、Office 365 グループ、SharePoint サイト。</span><span class="sxs-lookup"><span data-stu-id="a22c1-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to the following containers: Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="a22c1-105">ラベル設定を使用して、これらのコンテナーの次のオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-105">Use label settings to control the following options for these containers:</span></span>

- <span data-ttu-id="a22c1-106">Office 365 グループに接続されているチーム サイトのプライバシー(パブリックまたはプライベート)</span><span class="sxs-lookup"><span data-stu-id="a22c1-106">Privacy (public or private) of Office 365 group-connected teams sites</span></span>
- <span data-ttu-id="a22c1-107">外部ユーザーのアクセス</span><span class="sxs-lookup"><span data-stu-id="a22c1-107">External users access</span></span>
- <span data-ttu-id="a22c1-108">非管理対象デバイスからのアクセス</span><span class="sxs-lookup"><span data-stu-id="a22c1-108">Access from unmanaged devices</span></span> 

<span data-ttu-id="a22c1-109">サポートされているコンテナーの 1 つにこのラベルを適用すると、構成済みオプションが接続された SharePoint サイトまたはチーム サイトに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-109">When you apply this label to one of the supported containers, the label automatically applies the configured options to the connected SharePoint site or team site.</span></span> 

<span data-ttu-id="a22c1-110">ただし、これらのコンテナーのコンテンツは、ラベル名、視覚的なマーキング、暗号化などの設定のラベルを継承しません。</span><span class="sxs-lookup"><span data-stu-id="a22c1-110">Content in those containers however, do not inherit the labels for settings such as the label name, visual markings, or encryption.</span></span> <span data-ttu-id="a22c1-111">SharePoint サイトまたはチーム サイトのファイルにラベルを付けるには、[SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にします](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="a22c1-111">To label files in SharePoint sites or team sites, [enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="a22c1-112">Microsoft Teams、Office 365 グループ、および SharePoint サイトのパブリック プレビューについて</span><span class="sxs-lookup"><span data-stu-id="a22c1-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="a22c1-113">Microsoft Teams、Office 365 グループ、および SharePoint サイト向けの機密ラベルは徐々にテナントへと展開され、最終リリース前に変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a22c1-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites are gradually rolling out to tenants and might change before final release.</span></span> <span data-ttu-id="a22c1-114">このパブリック プレビューは、Office 365 コンテンツ配信ネットワーク (CDN) では機能しません。</span><span class="sxs-lookup"><span data-stu-id="a22c1-114">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

<span data-ttu-id="a22c1-115">このプレビューを有効にして新しい設定の機密ラベルを構成する前に、ユーザーはアプリで機密ラベルを表示および適用できます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-115">Before you enable this preview and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="a22c1-116">たとえば、Word から: </span><span class="sxs-lookup"><span data-stu-id="a22c1-116">For example, from Word:</span></span>

![Word デスクトップ アプリに表示される機密ラベル](../media/sensitivity-label-word.png)

<span data-ttu-id="a22c1-118">このプレビューを有効にして構成すると、ユーザーは追加で機密ラベルを表示し、Microsoft Teams、Office 365 グループ、および SharePoint サイトに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-118">After you enable and configure this preview, users can additionally see and apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="a22c1-119">たとえば、SharePoint から新しいチーム サイトを作成する場合:</span><span class="sxs-lookup"><span data-stu-id="a22c1-119">For example, when you create a new team site from SharePoint:</span></span>

![SharePoint でチーム サイトを作成するときの機密ラベル](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a><span data-ttu-id="a22c1-121">このプレビューを有効にしてラベルを同期する</span><span class="sxs-lookup"><span data-stu-id="a22c1-121">Enable this preview and synchronize labels</span></span>

1. <span data-ttu-id="a22c1-122">この機能は Azure AD 機能を使用するため、Azure AD のドキュメントの指示に従ってプレビューを有効にします: [Assign sensitivity labels to Office 365 groups in Azure Active Directory (preview) (Azure Active Directory の Office 365 グループに機密ラベルを割り当てる (プレビュー))](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="a22c1-122">Because this feature uses Azure AD functionality, follow the instructions in the Azure AD documentation to enable the preview: [Assign sensitivity labels to Office 365 groups in Azure Active Directory (preview)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="a22c1-123">PowerShell セッションで、グローバル管理者特権を持つ職場または学校のアカウントを使用して、セキュリティ/コンプライアンス センターに接続します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-123">In a PowerShell session, connect to the Security & Compliance Center by using a work or school account that has global admin privileges.</span></span> <span data-ttu-id="a22c1-124">例:</span><span class="sxs-lookup"><span data-stu-id="a22c1-124">For example:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```
    
    <span data-ttu-id="a22c1-125">詳細な手順については、「[Office 365 セキュリティ/コンプライアンス センターの PowerShell への接続](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a22c1-125">For full instructions, see [Connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="a22c1-126">秘密度ラベルを Office 365 グループで使用できるように、次のコマンドを実行して秘密度ラベルを Azure AD に同期させます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-126">Run the following command to synchronize your sensitivity labels to Azure AD, so that they can be used with Office 365 groups:</span></span>
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="a22c1-127">機密ラベルを作成または編集する際に、サイトおよびグループの設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="a22c1-127">How to configure site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="a22c1-128">これで、サイトおよびグループで使用する機密ラベルを作成または編集する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="a22c1-128">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="a22c1-129">プレビューを有効にすると、秘密度のラベル付けウィザードで新しいページが表示されます: **サイトとグループの設定**</span><span class="sxs-lookup"><span data-stu-id="a22c1-129">Enabling the preview makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="a22c1-130">機密ラベルの作成または編集に関するヘルプが必要な場合は、「[機密ラベルを作成して構成する](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a22c1-130">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="a22c1-131">この新しい [**サイトとグループの設定**] ページで、設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-131">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="a22c1-132">**Office 365 グループに接続されたチーム サイトのプライバシー**: デフォルト設定の [**パブリック**] は自動的に選択されます。つまり、組織内のすべてのユーザーがこのラベルが適用されているチーム サイトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-132">**Privacy of Office 365 group-connected teams sites**: The default setting of **Public** is automatically selected, which means anyone in your organization can access the team site where this label is applied.</span></span> <span data-ttu-id="a22c1-133">組織内の承認されたメンバーのみがグループのチーム サイトにアクセスできるようにする場合は、[**プライベート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-133">Select **Private** when you want only approved members in your organization to access the group's team site.</span></span> 
    
    <span data-ttu-id="a22c1-134">選択した設定は、グループに構成されている可能性がある以前のプライバシー設定を置き換え、プライバシー値をロックします。よって、チーム サイトまたはグループから最初に機密ラベルを削除することによってのみ、変更できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a22c1-134">The setting selected replaces a previous privacy setting that might be configured for the group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the team site or group.</span></span> <span data-ttu-id="a22c1-135">機密ラベルを削除しても、ラベルからのプライバシー設定は維持され、必要に応じて変更できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a22c1-135">After you remove the sensitivity label, the privacy setting from the label remains and you can now change it if necessary.</span></span>

- <span data-ttu-id="a22c1-136">**外部ユーザー アクセス**: グループの所有者が[ゲストをグループに追加](/office365/admin/create-groups/manage-guest-access-in-groups)できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-136">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="a22c1-137">**非管理対象デバイス**: [非管理対象デバイス](/sharepoint/control-access-from-unmanaged-devices)の場合、フル アクセスを許可するか、Web のみのアクセスを許可するか、またはアクセスを完全にブロックします。</span><span class="sxs-lookup"><span data-stu-id="a22c1-137">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> 

![[サイトとグループの設定] タブ](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="a22c1-139">チーム、グループ、またはサイトにラベルを適用すると、それらのサイトとグループの設定のみが有効になります。</span><span class="sxs-lookup"><span data-stu-id="a22c1-139">Only these site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="a22c1-140">暗号化やコンテンツ マーキングなどのその他のラベル設定は、チーム、グループ、またはサイト内のコンテンツに適用されません。</span><span class="sxs-lookup"><span data-stu-id="a22c1-140">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="a22c1-141">同様に、ラベルを作成しそれらのサイトとグループの設定をオンにしない場合には、ユーザーがチーム、グループ、およびサイトを作成するときにラベルは引き続き使用できますが、ラベル名のみが適用されます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-141">Similarly, if you create a label and don't turn on these site and group settings, the label will still be available when users create teams, groups, and sites, but only the label name will be applied.</span></span>

<span data-ttu-id="a22c1-142">秘密度ラベルがまだ公開されていない場合は、[秘密度ラベル ポリシーに追加](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)して公開します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-142">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="a22c1-143">このラベルを含む秘密度ラベル ポリシーが割り当てられているユーザーには、サイトとグループ用にそのラベルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-143">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="a22c1-144">機密ラベルの管理</span><span class="sxs-lookup"><span data-stu-id="a22c1-144">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="a22c1-145">Microsoft Teams、Office 365 グループ、および SharePoint サイトに使用する機密ラベルを作成、変更、および削除するには、ラベル ポリシーをユーザーに発行する際に慎重な調整が必要です。</span><span class="sxs-lookup"><span data-stu-id="a22c1-145">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Office 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="a22c1-146">以下のガイダンスを使用して、すべてのユーザーに影響を与える可能性のあるサイトおよびグループの作成エラーを回避します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-146">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="a22c1-147">**ラベルの作成と発行:**</span><span class="sxs-lookup"><span data-stu-id="a22c1-147">**Creating and publishing labels:**</span></span>

<span data-ttu-id="a22c1-148">機密ラベルを作成して公開した後、チーム、グループ、およびサイトでユーザーがラベルを表示できるようになるまでに最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a22c1-148">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="a22c1-149">以下の手順を使用して、テナント内のすべてのユーザーにラベルを発行します:</span><span class="sxs-lookup"><span data-stu-id="a22c1-149">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="a22c1-150">機密ラベルを作成し、テナント内の少数のユーザー アカウントに対してのみ発行します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-150">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="a22c1-151">24 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-151">Wait for 24 hours.</span></span>

3. <span data-ttu-id="a22c1-152">この 24 時間の待ち時間の後、手順 1 で指定したユーザー アカウントのいずれかを使用して、手順 1 で作成したラベルを持つチーム、Office 365 グループ、または SharePoint サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-152">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Office 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="a22c1-153">手順 3 の作成操作中にエラーが発生しなかった場合、テナント内のすべてのユーザーにラベルを発行します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-153">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="a22c1-154">エラーがある場合には、[Microsoft サポート](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)へお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="a22c1-154">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="a22c1-155">**発行済みラベルの変更および削除:**</span><span class="sxs-lookup"><span data-stu-id="a22c1-155">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="a22c1-156">1 つ以上のラベル ポリシーに含まれる機密ラベルを変更または削除すると、これらのアクションによりすべてのチーム、グループ、およびサイトの作成が失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a22c1-156">If you modify or delete a sensitivity label that is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="a22c1-157">この状況を回避するには、以下のガイダンスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="a22c1-157">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="a22c1-158">ラベルを含むすべてのラベル ポリシーから、機密ラベルを削除します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-158">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="a22c1-159">48 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-159">Wait for 48 hours.</span></span>

3. <span data-ttu-id="a22c1-160">48 時間待ってからチーム、グループ、またはサイトを作成し、ラベルが表示されなくなったことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a22c1-160">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="a22c1-161">機密ラベルが表示されていない場合は、ラベルを安全に変更または削除できます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-161">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="a22c1-162">ラベルがまだ表示されている場合には、[Microsoft サポート](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="a22c1-162">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="assign-sensitivity-labels-to-office-365-groups"></a><span data-ttu-id="a22c1-163">Office 365 グループに機密ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a22c1-163">Assign sensitivity labels to Office 365 groups</span></span>

<span data-ttu-id="a22c1-164">これで、1 つまたは複数の機密ラベルを Office 365 グループに適用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="a22c1-164">You're now ready to apply the sensitivity label or labels to Office 365 groups.</span></span> <span data-ttu-id="a22c1-165">手順については、Azure AD のドキュメントに戻ります。</span><span class="sxs-lookup"><span data-stu-id="a22c1-165">Return to the Azure AD documentation for instructions:</span></span>

- <span data-ttu-id="a22c1-166">「[Assign a label to a new group in Azure portal (Azure ポータルの新しいグループにラベルを割り当てる)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)」</span><span class="sxs-lookup"><span data-stu-id="a22c1-166">[Assign a label to a new group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)</span></span>

-  [<span data-ttu-id="a22c1-167">Assign a label to an existing group in Azure portal (Azure ポータルの既存のグループにラベルを割り当てる)</span><span class="sxs-lookup"><span data-stu-id="a22c1-167">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="a22c1-168">「[Remove a label from an existing group in Azure portal (Azure ポータルの既存のグループからラベルを削除する)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).」</span><span class="sxs-lookup"><span data-stu-id="a22c1-168">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="a22c1-169">新しいチームに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="a22c1-169">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="a22c1-170">ユーザーは、Microsoft Teams で新しいチームを作成する際に機密ラベルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-170">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="a22c1-171">ユーザーが機密レベルを選択すると、必要に応じてプライバシー設定が変更されます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-171">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="a22c1-172">ラベルに対し選択した外部ユーザーのアクセス設定に応じて、ユーザーは組織外のユーザーをチームに追加することができたり、できなかったりします。</span><span class="sxs-lookup"><span data-stu-id="a22c1-172">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="a22c1-173">Teams の機密ラベルの詳細について</span><span class="sxs-lookup"><span data-stu-id="a22c1-173">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![新しいチームを作成する際のプライバシー設定](../media/privacy-setting-new-team.png)

<span data-ttu-id="a22c1-175">チームを作成すると、すべてのチャネルの右上隅に機密ラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-175">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![チームに表示される機密ラベル](../media/privacy-setting-teams.png)

<span data-ttu-id="a22c1-177">このサービスは、Office 365 グループおよび接続された SharePoint チーム サイトに対して同じ機密ラベルを自動的に適用します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-177">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="a22c1-178">Outlook on the web の新しいグループに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="a22c1-178">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="a22c1-179">Outlook on the web では、新しいグループを作成するときに、公開されたラベルの [**機密**] オプションを選択または変更できます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-179">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![グループを作成し、[機密] 下でオプションを選択する](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="a22c1-181">新しいサイトに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="a22c1-181">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="a22c1-182">管理者およびエンド ユーザーは、[最新のチーム サイトやコミュニケーション サイトを作成する](/sharepoint/create-site-collection)際に機密ラベルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-182">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection).</span></span>

<span data-ttu-id="a22c1-183">ユーザーが最新のチームおよびコミュニケーション サイトを作成すると、規定で機密ラベルがすでに選択されています。</span><span class="sxs-lookup"><span data-stu-id="a22c1-183">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="a22c1-184">ユーザーは [ヘルプ] アイコンを選択し、ラベルの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-184">Users can select the help icon to learn more about the labels.</span></span>

![サイトを作成し、[機密] 下でオプションを選択する](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="a22c1-186">ユーザーがサイトを参照すると、ラベルの名前および適用されているポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-186">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![機密ラベルが適用されているサイト](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="a22c1-188">SharePoint 管理センターで機密ラベルを表示する</span><span class="sxs-lookup"><span data-stu-id="a22c1-188">View sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="a22c1-189">適用された機密ラベルを表示するには、新しい SharePoint 管理センターの [**アクティブなサイト**] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-189">To view the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="a22c1-190">最初に、[**機密**] 列を追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a22c1-190">You might need to first add the **Sensitivity** column:</span></span>

![[アクティブなサイト] ページの [機密] 列](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="a22c1-192">[新しい SharePoint 管理センターでのサイト管理の詳細をご覧ください](/sharepoint/manage-sites-in-new-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="a22c1-192">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="a22c1-193">ラベル向けのサイトとグループの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="a22c1-193">Change site and group settings for a label</span></span>

<span data-ttu-id="a22c1-194">ラベルのサイトとグループの設定を変更するたびに、チーム、サイト、グループが新しい設定を使用できるように、次の PowerShell コマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a22c1-194">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="a22c1-195">ベスト プラクティスとして、ラベルを複数のチーム、グループ、またはサイトに適用した後にラベルのサイトとグループの設定を変更しないようにします。</span><span class="sxs-lookup"><span data-stu-id="a22c1-195">As a best practice, don't the change site and group settings for a label after you've applied the label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="a22c1-196">次のコマンドを実行して、Office 365 セキュリティ/コンプライアンス センターの PowerShell に接続し、機密ラベルとそれらの GUID のリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-196">Run the following commands to connect to Office 365 Security & Compliance Center PowerShell and get the list of sensitivity labels and their GUIDs.</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. <span data-ttu-id="a22c1-197">変更を行ったラベルの GUID をメモします。</span><span class="sxs-lookup"><span data-stu-id="a22c1-197">Make a note of the GUID for the label or labels you have changed.</span></span>

3. <span data-ttu-id="a22c1-198">次に、Exchange Online PowerShell に接続して、Get-UnifiedGroup コマンドレットを実行します。GUID 例の "e48058ea-98e8-4940-8db0-ba1310fd955e" の代わりにラベルの GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-198">Now connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. <span data-ttu-id="a22c1-199">各グループについて、GUID 例の "e48058ea-98e8-4940-8db0-ba1310fd955e" の代わりにラベルの GUID を指定して機密ラベルを再適用します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-199">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a><span data-ttu-id="a22c1-200">機密ラベルのサポート</span><span class="sxs-lookup"><span data-stu-id="a22c1-200">Support for the sensitivity labels</span></span>

<span data-ttu-id="a22c1-201">次のアプリとサービスで、サイトとグループの設定用に構成した機密ラベルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-201">You can use the sensitivity labels that you've configured for site and group settings with the following apps and services:</span></span>

- <span data-ttu-id="a22c1-202">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a22c1-202">SharePoint Online</span></span>
- <span data-ttu-id="a22c1-203">Teams</span><span class="sxs-lookup"><span data-stu-id="a22c1-203">Teams</span></span>
- <span data-ttu-id="a22c1-204">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="a22c1-204">Outlook on the web</span></span>
- <span data-ttu-id="a22c1-205">SharePoint 管理センター</span><span class="sxs-lookup"><span data-stu-id="a22c1-205">SharePoint admin center</span></span>
- <span data-ttu-id="a22c1-206">Azure AD 管理センター</span><span class="sxs-lookup"><span data-stu-id="a22c1-206">Azure AD admin center</span></span>

<span data-ttu-id="a22c1-207">サイトおよびグループの設定用に構成した機密ラベルを現在使用できない他のアプリとサービスには、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="a22c1-207">Other apps and services that you can't currently use the sensitivity labels that you've configured for site and group settings include:</span></span>

- <span data-ttu-id="a22c1-208">Outlook for the Mac</span><span class="sxs-lookup"><span data-stu-id="a22c1-208">Outlook for the Mac</span></span>
- <span data-ttu-id="a22c1-209">Outlook モバイル</span><span class="sxs-lookup"><span data-stu-id="a22c1-209">Outlook mobile</span></span>
- <span data-ttu-id="a22c1-210">Outlook デスクトップ for Windows</span><span class="sxs-lookup"><span data-stu-id="a22c1-210">Outlook desktop for Windows</span></span>
- <span data-ttu-id="a22c1-211">Forms</span><span class="sxs-lookup"><span data-stu-id="a22c1-211">Forms</span></span>
- <span data-ttu-id="a22c1-212">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a22c1-212">Dynamics 365</span></span>
- <span data-ttu-id="a22c1-213">Yammer</span><span class="sxs-lookup"><span data-stu-id="a22c1-213">Yammer</span></span>
- <span data-ttu-id="a22c1-214">Stream</span><span class="sxs-lookup"><span data-stu-id="a22c1-214">Stream</span></span>
- <span data-ttu-id="a22c1-215">Planner</span><span class="sxs-lookup"><span data-stu-id="a22c1-215">Planner</span></span>
- <span data-ttu-id="a22c1-216">Project</span><span class="sxs-lookup"><span data-stu-id="a22c1-216">Project</span></span>
- <span data-ttu-id="a22c1-217">PowerBI</span><span class="sxs-lookup"><span data-stu-id="a22c1-217">PowerBI</span></span>
- <span data-ttu-id="a22c1-218">Teams 管理センター</span><span class="sxs-lookup"><span data-stu-id="a22c1-218">Teams admin center</span></span>
- <span data-ttu-id="a22c1-219">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="a22c1-219">Microsoft 365 admin center</span></span>
- <span data-ttu-id="a22c1-220">Exchange 管理センター</span><span class="sxs-lookup"><span data-stu-id="a22c1-220">Exchange admin center</span></span>


## <a name="classic-azure-ad-site-classification"></a><span data-ttu-id="a22c1-221">従来の Azure AD サイト分類</span><span class="sxs-lookup"><span data-stu-id="a22c1-221">Classic Azure AD site classification</span></span>

<span data-ttu-id="a22c1-222">このプレビューを有効にすると、Office 365 は新しいグループおよび SharePoint サイト向けに古い分類をサポートしなくなります。</span><span class="sxs-lookup"><span data-stu-id="a22c1-222">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="a22c1-223">ただし、既存のグループおよびサイトには、機密ラベルを使用するように変換しない限り、古い分類が引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-223">However, existing groups and sites still display the old classifications unless you convert them to use sensitivity labels.</span></span> <span data-ttu-id="a22c1-224">古い分類には、おそらく Azure AD PowerShell または PnP コア ライブラリを介して設定した、`ClassificationList`設定用の値を定義した "モダンな" サイト分類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a22c1-224">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="a22c1-225">たとえば、PowerShell の場合には以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="a22c1-225">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="a22c1-226">古い分類方法の詳細については、「[SharePoint の "モダン" サイトの分類](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a22c1-226">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="a22c1-227">古い分類を機密ラベルに変換するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a22c1-227">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="a22c1-228">既存のラベルを使用: 既に公開されている既存の機密ラベルを編集して、サイトおよびグループに必要なラベル設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-228">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="a22c1-229">新しいラベルの作成: 既存の分類と同じ名前を持つ新しい機密ラベルを作成および公開して、サイトおよびグループに必要なラベル設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-229">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="a22c1-230">その後で以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a22c1-230">Then:</span></span> 

1. <span data-ttu-id="a22c1-231">PowerShell を使用して、既存の Office 365 グループおよび SharePoint サイトに名前のマッピングを使用して機密ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-231">Use PowerShell to apply the sensitivity labels to existing Office 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="a22c1-232">手順については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a22c1-232">See the next section for instructions.</span></span>

2. <span data-ttu-id="a22c1-233">既存のグループおよびサイトから古い分類を削除します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-233">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="a22c1-234">機密ラベルをまだサポートしていないアプリやサービスでユーザーが新しいグループを作成できないようにすることはできませんが、定期的な PowerShell スクリプトを実行して、ユーザーが古い分類で作成した新しいグループを探し、機密ラベルを使用するようにそれらを変換することができます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-234">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

#### <a name="use-powershell-to-convert-classifications-for-office-365-groups-to-sensitivity-labels"></a><span data-ttu-id="a22c1-235">PowerShell を使用して、Office 365 グループの分類を機密ラベルに変換する</span><span class="sxs-lookup"><span data-stu-id="a22c1-235">Use PowerShell to convert classifications for Office 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="a22c1-236">SharePoint Online 管理シェルのバージョン 16.0.19418.12000 以降を実行していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a22c1-236">Ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="a22c1-237">既に最新バージョンを使用している場合は、手順 4 に進みます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-237">If you already have the latest version, skip to step 4.</span></span>

2. <span data-ttu-id="a22c1-238">PowerShell ギャラリーから以前のバージョンの SharePoint Online 管理シェルをインストールした場合、次のコマンドレットを実行してモジュールを更新できます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-238">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>
    
    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

3. <span data-ttu-id="a22c1-239">Microsoft ダウンロード センターから以前のバージョンの SharePoint Online 管理シェルをインストールした場合は、[**プログラムの追加と削除**] に移動して、SharePoint Online 管理シェルをアンインストールします。 </span><span class="sxs-lookup"><span data-stu-id="a22c1-239">If you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span> <span data-ttu-id="a22c1-240">次に、[ダウンロード センター](https://go.microsoft.com/fwlink/p/?LinkId=255251) から最新の SharePoint Online 管理シェルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a22c1-240">Then, install the latest SharePoint Online Management Shell from the [Download Center](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="a22c1-241">Office 365 のグローバル管理者または SharePoint 管理者権限を持つ職場または学校のアカウントを使用して、SharePoint Online 管理シェルへと接続します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-241">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="a22c1-242">方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a22c1-242">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

5. <span data-ttu-id="a22c1-243">以下のコマンドを実行し、機密ラベルおよびその GUID のリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-243">Run the following commands to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

6. <span data-ttu-id="a22c1-244">Office 365 グループに適用する機密ラベルの GUID をメモします。</span><span class="sxs-lookup"><span data-stu-id="a22c1-244">Make a note of the GUIDs for the sensitivity labels you want to apply to your Office 365 groups.</span></span>

7. <span data-ttu-id="a22c1-245">次のコマンドを例として使用して、現在 "一般" の分類を持つグループのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-245">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="a22c1-246">グループごとに、新しい機密ラベル GUID を追加します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-246">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="a22c1-247">例:</span><span class="sxs-lookup"><span data-stu-id="a22c1-247">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="a22c1-248">機密ラベル アクティビティの監査</span><span class="sxs-lookup"><span data-stu-id="a22c1-248">Auditing sensitivity label activities</span></span>

<span data-ttu-id="a22c1-249">誰かが機密ラベルで保護されているサイトにドキュメントをアップロードし、そのドキュメントの機密ラベルが、サイトに適用されている機密ラベルよりも[優先度が高く](sensitivity-labels.md#label-priority-order-matters)なっている場合、このアクションはブロックされません。</span><span class="sxs-lookup"><span data-stu-id="a22c1-249">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="a22c1-250">たとえば、「**一般**」ラベルを SharePoint サイトに適用し、誰かがこのサイトに「**社外秘**」というラベルの付けられたドキュメントをアップロードしたとします。</span><span class="sxs-lookup"><span data-stu-id="a22c1-250">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="a22c1-251">優先度の高い機密ラベルは、優先順位の低いコンテンツよりも機密性の高いコンテンツを識別するため、この状況はセキュリティ上の懸念になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a22c1-251">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="a22c1-252">アクションはブロックされませんが、監査されるため、ラベルの優先度にこのようなずれが見られるドキュメントを特定し、必要に応じてアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-252">Although the action isn't blocked, it is audited, so you can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="a22c1-253">たとえば、アップロードされたドキュメントをサイトから削除または移動します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-253">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="a22c1-254">ドキュメントの機密ラベルが、サイトに適用されている機密ラベルよりも優先度が低い場合、セキュリティ上の懸念にはなりません。</span><span class="sxs-lookup"><span data-stu-id="a22c1-254">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="a22c1-255">たとえば、「**一般**」というラベルの付いたドキュメントが、「**社外秘**」というラベルの付いたサイトにアップロードされている場合です。</span><span class="sxs-lookup"><span data-stu-id="a22c1-255">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="a22c1-256">このシナリオでは、監査イベントは生成されません。</span><span class="sxs-lookup"><span data-stu-id="a22c1-256">In this scenario, an auditing event isn't generated.</span></span>

<span data-ttu-id="a22c1-257">このイベントの監査ログを検索するには、[**ファイルとページのアクティビティ**] カテゴリから [**検出されたドキュメントの機密度の不一致**] を探します。</span><span class="sxs-lookup"><span data-stu-id="a22c1-257">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="a22c1-258">誰かがサイトまたはグループに対して機密ラベルの追加または削除を行うと、これらのアクティビティも監査されます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-258">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited.</span></span> <span data-ttu-id="a22c1-259">これらのイベントは、[[機密ラベル アクティビティ](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)] カテゴリにあります。</span><span class="sxs-lookup"><span data-stu-id="a22c1-259">These events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> 

<span data-ttu-id="a22c1-260">監査ログを検索する手順については、「[セキュリティ/コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a22c1-260">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="a22c1-261">機密ラベルの展開のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a22c1-261">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="a22c1-262">Microsoft Teams、Office 365 グループ、および SharePoint サイトの機密ラベルに問題がありますか ?</span><span class="sxs-lookup"><span data-stu-id="a22c1-262">Having problems with sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites?</span></span> <span data-ttu-id="a22c1-263">以下を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a22c1-263">Check the following:</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="a22c1-264">発行後にラベルが表示されない</span><span class="sxs-lookup"><span data-stu-id="a22c1-264">Labels not visible after publishing</span></span>
<span data-ttu-id="a22c1-265">これらの設定を有効にした後、または機密ラベルの説明を変更した後でチームまたは Office 365 グループを作成する際に問題が発生した場合には、ラベルの変更を保存してから数時間待ち、その後チームまたはグループの作成を再試行してみてください。</span><span class="sxs-lookup"><span data-stu-id="a22c1-265">If you experience issues when you create a team or Office 365 group after you enable these settings or modify a sensitivity label's description, wait a few hours after saving the label changes, and then try to create the team or group again.</span></span> <span data-ttu-id="a22c1-266">詳細については、「[Schedule roll-out after you create or change a sensitivity label (機密ラベルを作成または変更した後にロールアウトをスケジュールする)](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a22c1-266">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="a22c1-267">それでも SharePoint Online から新しい機密ラベルを表示できない場合には、[Microsoft サポート](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)へお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="a22c1-267">If you are still not able to see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="a22c1-268">チーム、グループ、または SharePoint サイトの作成エラー</span><span class="sxs-lookup"><span data-stu-id="a22c1-268">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="a22c1-269">パブリック プレビュー中に作成エラーが発生した場合、2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="a22c1-269">If you experience creation errors during the public preview, you have two options:</span></span>

- <span data-ttu-id="a22c1-270">どのユーザーに対しても機密ラベルが必須ではないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a22c1-270">Ensure that sensitivity labels are not mandatory for any user.</span></span>

- <span data-ttu-id="a22c1-271">[[Enable sensitivity label support in PowerShell (PowerShell で機密ラベルのサポートを有効にする)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell)] と同じ手順を使用することで、Microsoft Teams、Office 365 グループ、および SharePoint サイトの機密ラベルをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="a22c1-271">You can turn off sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="a22c1-272">ただし、プレビューを無効にするには、手順 5 で `$setting["EnableMIPLabels"] = "False"` を使用して機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a22c1-272">However, to disable the preview, in step 5, disable the feature by using `$setting["EnableMIPLabels"] = "False"`.</span></span>

