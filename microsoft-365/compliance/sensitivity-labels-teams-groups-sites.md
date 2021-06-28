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
ms.openlocfilehash: 844391ee20d2c8e8b94261659b18de0690dee119
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149192"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="627c0-103">秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する</span><span class="sxs-lookup"><span data-stu-id="627c0-103">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

><span data-ttu-id="627c0-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="627c0-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="627c0-105">[秘密度ラベル](sensitivity-labels.md) を使用して、ドキュメントやメールを分類および保護するだけでなく、Microsoft Teams サイト、Microsoft 365 グループ ([以前は Office 365 グループ](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))、およびSharePoint サイトなどのコンテナーにあるコンテンツを保護するために、秘密度ラベルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="627c0-105">In addition to using [sensitivity labels](sensitivity-labels.md) to classify and protect documents and emails, you can also use sensitivity labels to protect content in the following containers: Microsoft Teams sites, Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), and SharePoint sites.</span></span> <span data-ttu-id="627c0-106">コンテナー レベルの分類と保護を設定するには、次のラベル設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="627c0-106">For this container-level classification and protection, use the following label settings:</span></span>

- <span data-ttu-id="627c0-107">チーム サイトおよび Microsoft 365 グループのプライバシー (パブリックまたはプライベート)</span><span class="sxs-lookup"><span data-stu-id="627c0-107">Privacy (public or private) of teams sites and Microsoft 365 groups</span></span>
- <span data-ttu-id="627c0-108">外部ユーザーのアクセス</span><span class="sxs-lookup"><span data-stu-id="627c0-108">External user access</span></span>
- <span data-ttu-id="627c0-109">SharePoint サイトからの外部共有</span><span class="sxs-lookup"><span data-stu-id="627c0-109">External sharing from SharePoint sites</span></span>
- <span data-ttu-id="627c0-110">非管理対象デバイスからのアクセス</span><span class="sxs-lookup"><span data-stu-id="627c0-110">Access from unmanaged devices</span></span>
- <span data-ttu-id="627c0-111">認証コンテキスト (プレビュー段階)</span><span class="sxs-lookup"><span data-stu-id="627c0-111">Authentication contexts (in preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="627c0-112">非管理対象デバイスと認証コンテキストの設定は、Azure Active Directory の条件付きアクセスと連動しています。</span><span class="sxs-lookup"><span data-stu-id="627c0-112">The settings for unmanaged devices and authentication contexts work in conjunction with Azure Active Directory Conditional Access.</span></span> <span data-ttu-id="627c0-113">これらの設定に秘密度ラベルを使用したい場合は、この依存機能を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="627c0-113">You must configure this dependent feature if you want to use a sensitivity label for these settings.</span></span> <span data-ttu-id="627c0-114">追加情報については、以下の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="627c0-114">Additional information is included in the instructions that follow.</span></span>

<span data-ttu-id="627c0-115">サポートされているコンテナーにこの秘密度ラベルを適用すると、分類および構成された保護の設定がサイトまたはグループに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="627c0-115">When you apply this sensitivity label to a supported container, the label automatically applies the classification and configured protection settings to the site or group.</span></span>

<span data-ttu-id="627c0-116">ただし、これらのコンテナーのコンテンツは、視覚的なマーキング、および暗号化の分類またはファイルとメールの設定のラベルを継承しません。</span><span class="sxs-lookup"><span data-stu-id="627c0-116">Content in these containers however, do not inherit the labels for the classification or settings for files and emails, such as visual markings and encryption.</span></span> <span data-ttu-id="627c0-117">ユーザーが SharePoint サイトまたはチーム サイトでドキュメントにラベルを付けられるようにするには、[SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にします](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="627c0-117">So that users can label their documents in SharePoint sites or team sites, make sure you've [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

> [!NOTE]
> <span data-ttu-id="627c0-118">コンテナーの秘密度ラベルは、Office 365 のコンテンツ配信ネットワーク (CDNs) ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="627c0-118">Sensitivity labels for containers aren't supported with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="using-sensitivity-labels-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="627c0-119">Microsoft Teams、Microsoft 365 グループ、およびSharePoint サイトで秘密度ラベルを使用する</span><span class="sxs-lookup"><span data-stu-id="627c0-119">Using sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="627c0-p104">コンテナーの秘密度ラベルを有効化し、新しい設定の秘密度ラベルを構成する前に、ユーザーはアプリで秘密度ラベルを表示および適用できます。たとえば、Word では次のようなことができます。</span><span class="sxs-lookup"><span data-stu-id="627c0-p104">Before you enable sensitivity labels for containers and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps. For example, from Word:</span></span>

![Word デスクトップ アプリに表示される機密ラベル](../media/sensitivity-label-word.png)

<span data-ttu-id="627c0-p105">コンテナーの秘密度ラベルを有効にして構成すると、ユーザーは追加で秘密度ラベルを表示し、Microsoft チーム サイト、Microsoft 365 グループ、および SharePoint サイトに適用することができます。たとえば、SharePoint から新しいチーム サイトを作成する場合:</span><span class="sxs-lookup"><span data-stu-id="627c0-p105">After you enable and configure sensitivity labels for containers, users can additionally see and apply sensitivity labels to Microsoft team sites, Microsoft 365 groups, and SharePoint sites. For example, when you create a new team site from SharePoint:</span></span>

![SharePoint でチーム サイトを作成するときの機密ラベル](../media/sensitivity-labels-new-team-site.png)

## <a name="how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels"></a><span data-ttu-id="627c0-126">コンテナーの秘密度ラベルを有効化してラベルを同期する方法</span><span class="sxs-lookup"><span data-stu-id="627c0-126">How to enable sensitivity labels for containers and synchronize labels</span></span>

<span data-ttu-id="627c0-127">まだコンテナーの秘密度ラベルを有効にしていない場合は、以下の一連の手順を一度だけ実行してください。</span><span class="sxs-lookup"><span data-stu-id="627c0-127">If you haven't yet enabled sensitivity labels for containers, do the following set of steps as a one-time procedure:</span></span>

1. <span data-ttu-id="627c0-128">この機能は Azure AD 機能を使用するため、Azure AD のドキュメント [「Azure Active Directory で Microsoft 365 グループに秘密度ラベルを割り当てる」](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels) の指示に従い、秘密度ラベルのサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="627c0-128">Because this feature uses Azure AD functionality, follow the instructions from the Azure AD documentation to enable sensitivity label support: [Assign sensitivity labels to Microsoft 365 groups in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="627c0-129">秘密度ラベルを Azure AD に同期することが必要になります。</span><span class="sxs-lookup"><span data-stu-id="627c0-129">You now need to synchronize your sensitivity labels to Azure AD.</span></span> <span data-ttu-id="627c0-130">まず、[セキュリティ/コンプライアンス センターの PowerShell に接続します](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="627c0-130">First, [connect to Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="627c0-131">たとえば、管理者として実行している PowerShell セッションで、グローバル管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="627c0-131">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account.</span></span>

3. <span data-ttu-id="627c0-132">秘密度ラベルを Microsoft 365 グループで使用できるように、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="627c0-132">Then run the following command to ensure your sensitivity labels can be used with Microsoft 365 groups:</span></span>

    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-groups-and-site-settings"></a><span data-ttu-id="627c0-133">グループとサイト設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="627c0-133">How to configure groups and site settings</span></span>

<span data-ttu-id="627c0-134">前のセクションで説明したとおり、コンテナーの秘密度レベルを有効にすると、秘密度レベル ウィザードでグループとサイトの保護設定を構成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="627c0-134">After sensitivity labels are enabled for containers as described in the previous section, you can then configure protection settings for groups and sites in the sensitivity labeling wizard.</span></span> <span data-ttu-id="627c0-135">コンテナーの秘密度ラベルが有効になるまでは、ウィザードに設定が表示されますが、構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="627c0-135">Until sensitivity labels are enabled for containers, the settings are visible in the wizard but you can't configure them.</span></span>

1. <span data-ttu-id="627c0-136">一般的な手順に従って、[秘密度レベルを作成または編集](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)し、ラベルのスコープとして **[グループとサイト]** を選択していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="627c0-136">Follow the general instructions to [create or edit a sensitivity label](create-sensitivity-labels.md#create-and-configure-sensitivity-labels) and make sure you select **Groups & sites** for the label's scope:</span></span> 
    
    ![ファイルとメールの秘密度レベル スコープ オプション](../media/groupsandsites-scope-options-sensitivity-label.png)
    
    <span data-ttu-id="627c0-138">ラベルにこのスコープのみが選択されている場合、秘密度レベルをサポートする Office アプリにはラベルが表示されず、ファイルやメールに適用できません。</span><span class="sxs-lookup"><span data-stu-id="627c0-138">When only this scope is selected for the label, the label won't be displayed in Office apps that support sensitivity labels and can't be applied to files and emails.</span></span> <span data-ttu-id="627c0-139">このようにラベルを分離すると、ユーザーと管理者の両方に役立ちますが、ラベルの展開が複雑になる可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="627c0-139">Having this separation of labels can be helpful for both users and administrators, but can also add to the complexity of your label deployment.</span></span>
    
    <span data-ttu-id="627c0-140">たとえば、SharePoint はラベル付きドキュメントがラベル付きサイトにアップロードされたことを検出するため、[ラベルの順序](sensitivity-labels.md#label-priority-order-matters)を注意深く確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="627c0-140">For example, you need to carefully review your [label ordering](sensitivity-labels.md#label-priority-order-matters) because SharePoint detects when a labeled document is uploaded to a labeled site.</span></span> <span data-ttu-id="627c0-141">このシナリオでは、ドキュメントの秘密度ラベルの優先度がサイトのラベルよりも高い場合、監査イベントとメールが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="627c0-141">In this scenario, an audit event and email are automatically generated when the document has a higher priority sensitivity label than the site's label.</span></span> <span data-ttu-id="627c0-142">詳細については、このページの「[秘密度レベル アクティビティの監査](#auditing-sensitivity-label-activities)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="627c0-142">For more information, see the [Auditing sensitivity label activities](#auditing-sensitivity-label-activities) section on this page.</span></span> 

2. <span data-ttu-id="627c0-143">次に、**[グループとサイトの保護設定の定義]** ページで、使用可能なオプションの 1 つまたは両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="627c0-143">Then, on the **Define protection settings for groups and sites** page, select one or both of the available options:</span></span>
    
    - <span data-ttu-id="627c0-144">**[プライバシーと外部ユーザーのアクセス設定]** を使用して、**[プライバシー]** と **[外部ユーザーのアクセス]** 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="627c0-144">**Privacy and external user access settings** to configure the **Privacy** and **External users access** settings.</span></span> 
    - <span data-ttu-id="627c0-145">**[外部共有および条件付きアクセスの設定]** で、**[ラベル付けされた SharePoint サイトからの外部共有を制御する]** および **[Azure AD 条件付きアクセスを使用して、ラベル付き SharePoint サイトを保護]** 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="627c0-145">**External sharing and Conditional Access settings** to configure the **Control external sharing from labeled SharePoint sites** and **Use Azure AD Conditional Access to protect labeled SharePoint sites** setting.</span></span>

3. <span data-ttu-id="627c0-146">**[プライバシーと外部ユーザー アクセス設定]** を選択した場合は、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="627c0-146">If you selected **Privacy and external user access settings**, now configure the following settings:</span></span>
    
    - <span data-ttu-id="627c0-147">**プライバシー**: 組織内の誰かがこのラベルが適用されているチーム サイトまたはグループにアクセスできるようにする場合は、既定の **[パブリック]** をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="627c0-147">**Privacy**: Keep the default of **Public** if you want anyone in your organization to access the team site or group where this label is applied.</span></span>
        
        <span data-ttu-id="627c0-148">組織内の承認されたメンバーのみにアクセスを制限する場合は、[**プライベート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="627c0-148">Select **Private** if you want access to be restricted to only approved members in your organization.</span></span>
        
        <span data-ttu-id="627c0-149">秘密度ラベルを使用してコンテナー内のコンテンツを保護し、ユーザーが自分でプライバシー設定を構成できるようにする場合は、**[なし]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="627c0-149">Select **None** when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.</span></span>
        
        <span data-ttu-id="627c0-150">このラベルをコンテナーに適用すると、[**パブリック**] または [**プライベート**] の設定によってプライバシー設定が設定およびロックされます。</span><span class="sxs-lookup"><span data-stu-id="627c0-150">The settings of **Public** or **Private** set and lock the privacy setting when you apply this label to the container.</span></span> <span data-ttu-id="627c0-151">選択した設定は、チームまたはグループに構成されている可能性がある以前のプライバシー設定を置き換え、プライバシー値をロックします。これにより、コンテナーから最初に秘密度ラベルを削除することによってのみ、変更できるようになります。</span><span class="sxs-lookup"><span data-stu-id="627c0-151">Your chosen setting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container.</span></span> <span data-ttu-id="627c0-152">秘密度ラベルを削除しても、ラベルからのプライバシー設定は維持され、ユーザーは再びラベルを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="627c0-152">After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span></span>
    
    - <span data-ttu-id="627c0-153">**外部ユーザー アクセス**: グループの所有者が [ゲストをグループに追加](/office365/admin/create-groups/manage-guest-access-in-groups)できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="627c0-153">**External user access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

4. <span data-ttu-id="627c0-154">**[デバイスの外部共有とデバイス アクセスの設定]** を選択した場合は、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="627c0-154">If you selected **Device external sharing and device access settings**, now configure the following settings:</span></span>
    
    - <span data-ttu-id="627c0-155">**[ラベル付き SharePoint サイトからの外部共有を制御]**: このオプションを選択して、すべてのユーザー、新規および既存のゲストを選択するか、組織内のユーザのみを選択します。</span><span class="sxs-lookup"><span data-stu-id="627c0-155">**Control external sharing from labeled SharePoint sites**: Select this option to then select either external sharing for anyone, new and existing guests, existing guests, or only people in your organization.</span></span> <span data-ttu-id="627c0-156">この構成と設定の詳細については、「SharePoint ドキュメント」で [サイトへのの外部共有を有効または無効にする](/sharepoint/change-external-sharing-site) を参照します。</span><span class="sxs-lookup"><span data-stu-id="627c0-156">For more information about this configuration and settings, see the SharePoint documentation, [Turn external sharing on or off for a site](/sharepoint/change-external-sharing-site).</span></span>
    
    - <span data-ttu-id="627c0-157">**Azure AD 条件付きアクセスを使用して、ラベル付き SharePoint サイトを保護**: [Azure Active Directory の条件付きアクセス](/azure/active-directory/conditional-access/overview)を構成して使用している場合のみ、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="627c0-157">**Use Azure AD Conditional Access to protect labeled SharePoint sites**: Select this option only if your organization has configured and is using [Azure Active Directory Conditional Access](/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="627c0-158">次に、次のいずれかの設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="627c0-158">Then, select one of the following settings:</span></span>
    
        - <span data-ttu-id="627c0-159">**ユーザーが管理外のデバイスから SharePoint サイトにアクセスできるかどうかを決定する**: このオプションでは、Azure ADの条件付きアクセスを使用して、管理されていないデバイスからの SharePoint および OneDrive コンテンツへのアクセスをブロックまたは制限する SharePoint 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="627c0-159">**Determine whether users can access SharePoint sites from unmanaged devices**: This option uses the SharePoint feature that uses Azure AD Conditional Access to block or limit access to SharePoint and OneDrive content from unmanaged devices.</span></span> <span data-ttu-id="627c0-160">詳細については、SharePoint ドキュメントの「[非管理対象デバイスからのアクセスの制御](/sharepoint/control-access-from-unmanaged-devices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="627c0-160">For more information, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices) from the SharePoint documentation.</span></span> <span data-ttu-id="627c0-161">このラベル設定を指定するオプションは、SharePoint の手順から「[特定の SharePoint サイトまたは OneDrive からのアクセスをブロックまたは制限する](/sharepoint/control-access-from-unmanaged-devices#block-or-limit-access-to-a-specific-sharepoint-site-or-onedrive)」セクションの手順 3 - 5 で説明しているように、サイトの PowerShell コマンドを実行することと同じです。</span><span class="sxs-lookup"><span data-stu-id="627c0-161">The option you specify for this label setting is the equivalent of running a PowerShell command for a site, as described in steps 3-5 from the [Block or limit access to a specific SharePoint site or OneDrive](/sharepoint/control-access-from-unmanaged-devices#block-or-limit-access-to-a-specific-sharepoint-site-or-onedrive) section from the SharePoint instructions.</span></span>
            
            <span data-ttu-id="627c0-162">追加の構成情報については、このセクションの最後にある「[非管理対象デバイス オプションの依存関係に関する詳細情報](#more-information-about-the-dependencies-for-the-unmanaged-devices-option)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="627c0-162">For additional configuration information, see [More information about the dependencies for the unmanaged devices option](#more-information-about-the-dependencies-for-the-unmanaged-devices-option) at the end of this section.</span></span>
            
        - <span data-ttu-id="627c0-163">**既存の認証コンテキストを選択する**: 現在プレビュー版ですが、このラベルが適用されている SharePoint サイトにユーザーがアクセスする場合に、より厳しいアクセス条件を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="627c0-163">**Choose an existing authentication context**: Currently in preview, this option lets you enforce more stringent access conditions when users access SharePoint sites that have this label applied.</span></span> <span data-ttu-id="627c0-164">これらの条件は、組織の条件付きアクセスを展開するために作成され、公開された既存の認証コンテキストを選択した場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="627c0-164">These conditions are enforced when you select an existing authentication context that has been created and published for your organization's Conditional Access deployment.</span></span> <span data-ttu-id="627c0-165">ユーザーが構成された条件を満たさない場合や、認証コンテキストをサポートしていないアプリを使用している場合は、アクセスが拒否されます。</span><span class="sxs-lookup"><span data-stu-id="627c0-165">If users don't meet the configured conditions or if they use apps that don't support authentication contexts, they are denied access.</span></span>
            
            <span data-ttu-id="627c0-166">追加の構成情報については、このセクションの最後にある「[認証コンテキスト オプションの依存関係に関する詳細情報](#more-information-about-the-dependencies-for-the-authentication-context-option)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="627c0-166">For additional configuration information, see [More information about the dependencies for the authentication context option](#more-information-about-the-dependencies-for-the-authentication-context-option) at the end of this section.</span></span>
            
            <span data-ttu-id="627c0-167">このラベルの構成例は、以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="627c0-167">Examples for this label configuration:</span></span>
            
             - <span data-ttu-id="627c0-168">[多要素認証 (MFA)](/azure/active-directory/conditional-access/untrusted-networks) を必要とするように構成された認証コンテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="627c0-168">You choose an authentication context that is configured to require [multi-factor authentication (MFA)](/azure/active-directory/conditional-access/untrusted-networks).</span></span> <span data-ttu-id="627c0-169">このラベルは、非常に機密性の高い社外秘のアイテムを含む SharePoint サイトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="627c0-169">This label is then applied to a SharePoint site that contains highly confidential items.</span></span> <span data-ttu-id="627c0-170">その結果、信頼されていないネットワークのユーザーがこのサイトのドキュメントにアクセスしようとすると、ドキュメントにアクセスする前に完了する必要がある MFA プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="627c0-170">As a result, when users from an untrusted network attempt to access a document in this site, they see the MFA prompt that they must complete before they can access the document.</span></span>
             
             - <span data-ttu-id="627c0-171">[使用条件 (ToU) ポリシー](/azure/active-directory/conditional-access/terms-of-use)に基づいて構成された認証コンテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="627c0-171">You choose an authentication context that is configured for [terms of use (ToU) policies](/azure/active-directory/conditional-access/terms-of-use).</span></span> <span data-ttu-id="627c0-172">このラベルは、法務上またはコンプライアンス上の理由から使用条件の承認が必要なアイテムを含む SharePoint サイトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="627c0-172">This label is then applied to a SharePoint site that contains items that require a terms of use acceptance for legal or compliance reasons.</span></span> <span data-ttu-id="627c0-173">その結果、ユーザーがこのサイト内の文書にアクセスしようとすると、使用条件のドキュメントが表示され、それに同意しないと元の文書にアクセスできないようになっています。</span><span class="sxs-lookup"><span data-stu-id="627c0-173">As a result, when users attempt to access a document in this site, they see a terms of use document that they must accept before they can access the original document.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="627c0-174">チーム、グループ、またはサイトにラベルを適用すると、それらのサイトとグループの設定のみが有効になります。</span><span class="sxs-lookup"><span data-stu-id="627c0-174">Only these site and group settings take effect when you apply the label to a team, group, or site.</span></span> <span data-ttu-id="627c0-175">[ラベルのスコープ](sensitivity-labels.md#label-scopes)にファイルとメールが含まれている場合、暗号化やコンテンツ マーキングなどのその他のラベル設定は、チーム、グループ、またはサイト内のコンテンツに適用されません。</span><span class="sxs-lookup"><span data-stu-id="627c0-175">If the [label's scope](sensitivity-labels.md#label-scopes) includes files and emails, other label settings such as encryption and content marking aren't applied to the content within the team, group, or site.</span></span>

<span data-ttu-id="627c0-176">秘密度ラベルがまだ公開されていない場合は、[秘密度ラベル ポリシーに追加](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)して公開します。</span><span class="sxs-lookup"><span data-stu-id="627c0-176">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="627c0-177">このラベルを含む秘密度ラベル ポリシーが割り当てられているユーザーには、サイトとグループ用にそのラベルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="627c0-177">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

##### <a name="more-information-about-the-dependencies-for-the-unmanaged-devices-option"></a><span data-ttu-id="627c0-178">非管理対象デバイス オプションの依存関係に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="627c0-178">More information about the dependencies for the unmanaged devices option</span></span>

<span data-ttu-id="627c0-179">「[アプリによる制限の使用](/sharepoint/app-enforced-restrictions)」に記載されているように SharePoint の依存条件付きアクセス ポリシーを構成しない場合は、ここで指定したオプションに影響ありません。</span><span class="sxs-lookup"><span data-stu-id="627c0-179">If you don't configure the dependent conditional access policy for SharePoint as documented in [Use app-enforced restrictions](/sharepoint/app-enforced-restrictions), the option you specify here will have no effect.</span></span> <span data-ttu-id="627c0-180">また、テナントレベルで構成された設定よりも制限が少ない場合は影響はありません。</span><span class="sxs-lookup"><span data-stu-id="627c0-180">Additionally, it will have no effect if it's less restrictive than a configured setting at the tenant level.</span></span> <span data-ttu-id="627c0-181">管理されていないデバイスの組織全体の設定を構成している場合は、同じかより制限の厳しいレベルのラベル設定を選択します</span><span class="sxs-lookup"><span data-stu-id="627c0-181">If you have configured an organization-wide setting for unmanaged devices, choose a label setting that's either the same or more restrictive</span></span>

<span data-ttu-id="627c0-182">たとえば、テナントが [**制限されたWebのみのアクセスを許可する**] に構成されている場合、フルアクセスを許可するラベル設定は制限が少ないため、効果がありません。</span><span class="sxs-lookup"><span data-stu-id="627c0-182">For example, if your tenant is configured for **Allow limited, web-only access**, the label setting that allows full access will have no effect because it's less restrictive.</span></span> <span data-ttu-id="627c0-183">このテナントレベルの設定では、アクセスをブロックするためのラベル設定 (より制限的) または制限付きアクセスのためのラベル設定 (テナント設定と同じ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="627c0-183">For this tenant-level setting, choose the label setting to block access (more restrictive) or the label setting for limited access (the same as the tenant setting).</span></span>

<span data-ttu-id="627c0-184">SharePoint 設定はラベル構成とは別に構成できるため、秘密度ラベル ウィザードで依存関係が設定されているかどうかのチェックは行われません。</span><span class="sxs-lookup"><span data-stu-id="627c0-184">Because you can configure the SharePoint settings separately from the label configuration, there's no check in the sensitivity label wizard that the dependencies are in place.</span></span> <span data-ttu-id="627c0-185">これらの依存関係は、ラベルが作成および公開された後、およびラベルが適用された後でも構成できます。</span><span class="sxs-lookup"><span data-stu-id="627c0-185">These dependencies can be configured after the label is created and published, and even after the label is applied.</span></span> <span data-ttu-id="627c0-186">ただし、ラベルがすでに適用されている場合、ラベル設定は、ユーザーが次に認証するまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="627c0-186">However, if the label is already applied, the label setting won't take effect until after the user next authenticates.</span></span>

##### <a name="more-information-about-the-dependencies-for-the-authentication-context-option"></a><span data-ttu-id="627c0-187">認証コンテキスト オプションの依存関係に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="627c0-187">More information about the dependencies for the authentication context option</span></span>

<span data-ttu-id="627c0-188">ドロップダウン リストに表示して選択するには、Azure Active Directory 条件付きアクセスの構成の一部として、認証コンテキストを作成し、構成して公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="627c0-188">To display in the drop-down list for selection, authentication contexts must be created, configured, and published as part of your Azure Active Directory Condition Access configuration.</span></span> <span data-ttu-id="627c0-189">詳細および手順については、Azure AD 条件付きアクセス ドキュメントの[[認証コンテキストの構成]](/azure/active-directory/conditional-access/concept-conditional-access-cloud-apps#configure-authentication-contexts) セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="627c0-189">For more information and instructions, see the [Configure authentication contexts](/azure/active-directory/conditional-access/concept-conditional-access-cloud-apps#configure-authentication-contexts) section from the Azure AD Conditional Access documentation.</span></span>

<span data-ttu-id="627c0-p123">すべてのアプリが認証コンテクストをサポートするわけではありません。サポートされていないアプリを使用しているユーザーが、認証コンテキストを構成済みのサイトにアクセスすると、アクセス拒否のメッセージが表示されるか、認証を求められるものの拒否される問題が発生します。現在、認証コンテクストをサポートするアプリは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="627c0-p123">Not all apps support authentication contexts. If a user with an unsupported app connects to the site that's configured for an authentication context, they see either an access denied message or they are prompted to authenticate but rejected. The apps that currently support authentication contexts:</span></span>

- <span data-ttu-id="627c0-193">Office for the Web (Web 用 Office を含む)</span><span class="sxs-lookup"><span data-stu-id="627c0-193">Office for the web, which includes Outlook for the web</span></span>

- <span data-ttu-id="627c0-194">Windows および macOS 用の Microsoft Teams (Teams Web アプリを除く)</span><span class="sxs-lookup"><span data-stu-id="627c0-194">Microsoft Teams for Windows and macOS (excludes Teams web app)</span></span>

- <span data-ttu-id="627c0-195">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="627c0-195">Microsoft Planner</span></span>

- <span data-ttu-id="627c0-196">Microsoft 365 Apps for Word、Excel、PowerPoint の最小バージョンは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="627c0-196">Microsoft 365 Apps for Word, Excel, and PowerPoint; minimum versions:</span></span>
    - <span data-ttu-id="627c0-197">Windows: 2103</span><span class="sxs-lookup"><span data-stu-id="627c0-197">Windows: 2103</span></span>
    - <span data-ttu-id="627c0-198">macOS: 16.45.1202</span><span class="sxs-lookup"><span data-stu-id="627c0-198">macOS: 16.45.1202</span></span>
    - <span data-ttu-id="627c0-199">iOS: 2.48.303</span><span class="sxs-lookup"><span data-stu-id="627c0-199">iOS: 2.48.303</span></span>
    - <span data-ttu-id="627c0-200">Android: 16.0.13924.10000</span><span class="sxs-lookup"><span data-stu-id="627c0-200">Android: 16.0.13924.10000</span></span>

- <span data-ttu-id="627c0-201">Microsoft 365 Apps for Outlook の最小バージョンは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="627c0-201">Microsoft 365 Apps for Outlook; minimum versions:</span></span>
    - <span data-ttu-id="627c0-202">Windows: 2103</span><span class="sxs-lookup"><span data-stu-id="627c0-202">Windows: 2103</span></span>
    - <span data-ttu-id="627c0-203">macOS: 16.45.1202</span><span class="sxs-lookup"><span data-stu-id="627c0-203">macOS: 16.45.1202</span></span>
    - <span data-ttu-id="627c0-204">iOS: 4.2109.0</span><span class="sxs-lookup"><span data-stu-id="627c0-204">iOS: 4.2109.0</span></span>
    - <span data-ttu-id="627c0-205">Android: 4.2025.1</span><span class="sxs-lookup"><span data-stu-id="627c0-205">Android: 4.2025.1</span></span>

- <span data-ttu-id="627c0-206">OneDrive 同期アプリの最小バージョンは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="627c0-206">OneDrive sync app, minimum versions:</span></span>
    - <span data-ttu-id="627c0-207">Windows: 21.002</span><span class="sxs-lookup"><span data-stu-id="627c0-207">Windows: 21.002</span></span>
    - <span data-ttu-id="627c0-208">macOS: 21.002</span><span class="sxs-lookup"><span data-stu-id="627c0-208">macOS: 21.002</span></span>
    - <span data-ttu-id="627c0-209">iOS: 12 月 30 日にロールアウト</span><span class="sxs-lookup"><span data-stu-id="627c0-209">iOS: Rolling out in 12.30</span></span>
    - <span data-ttu-id="627c0-210">Android: まだサポートされていません</span><span class="sxs-lookup"><span data-stu-id="627c0-210">Android: Not yet supported</span></span>

<span data-ttu-id="627c0-211">このプレビューでの既知の制限事項は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="627c0-211">Known limitations for this preview:</span></span>

- <span data-ttu-id="627c0-212">OneDrive 同期アプリについては、OneDrive のみサポートし、他のサイトはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="627c0-212">For the OneDrive sync app, supported for OneDrive only and not for other sites.</span></span>

- <span data-ttu-id="627c0-213">次の機能やアプリは、認証コンテキストとの互換性がない場合があるため、ユーザーが認証コンテキストを使用してサイトへのアクセスに成功した後、これらの機能が継続して動作するかどうかを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="627c0-213">The following features and apps might be incompatible with authentication contexts, so we encourage you to check that these continue to work after a user successfully accesses  a site by using an authentication context:</span></span>
    
    - <span data-ttu-id="627c0-214">PowerApps や Power Automate を使用したワークフロー</span><span class="sxs-lookup"><span data-stu-id="627c0-214">Workflows that use PowerApps or Power Automate</span></span>
    - <span data-ttu-id="627c0-215">サードパーティ製アプリ</span><span class="sxs-lookup"><span data-stu-id="627c0-215">Third-party apps</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="627c0-216">機密ラベルの管理</span><span class="sxs-lookup"><span data-stu-id="627c0-216">Sensitivity label management</span></span>

<span data-ttu-id="627c0-217">サイトとグループに対して構成されている秘密度ラベルを作成、変更、または削除する場合は、次のガイダンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="627c0-217">Use the following guidance for when you create, modify, or delete sensitivity labels that are configured for sites and groups.</span></span>

### <a name="creating-and-publishing-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="627c0-218">サイトとグループに対して構成されているラベルを作成して発行する</span><span class="sxs-lookup"><span data-stu-id="627c0-218">Creating and publishing labels that are configured for sites and groups</span></span>

<span data-ttu-id="627c0-219">新しい機密ラベルを作成して公開すると、チーム、グループ、およびサイトでユーザーには、1 時間以内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="627c0-219">When a new sensitivity label is created and published, it's visible for users in teams, groups, and sites within one hour.</span></span> <span data-ttu-id="627c0-220">ただし、既存のラベルを変更する場合は、最大で 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="627c0-220">However, if you modify an existing label, allow up to 24 hours.</span></span> <span data-ttu-id="627c0-221">このラベルがサイトおよびグループの設定に対して構成されている場合、次のガイダンスを使用して、ユーザーのラベルを発行します。</span><span class="sxs-lookup"><span data-stu-id="627c0-221">Use the following guidance to publish a label for your users when that label is configured for site and group settings:</span></span>

1. <span data-ttu-id="627c0-222">秘密度ラベルを作成し構成したら、少数のテスト ユーザーにのみ適用されるラベル ポリシーにこのラベルを追加します。</span><span class="sxs-lookup"><span data-stu-id="627c0-222">After you create and configure the sensitivity label, add this label to a label policy that applies to just a few test users.</span></span>

2. <span data-ttu-id="627c0-223">変更がレプリケートされるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="627c0-223">Wait for the change to replicate:</span></span>

   - <span data-ttu-id="627c0-224">新規ラベル: 1 時間待機します。</span><span class="sxs-lookup"><span data-stu-id="627c0-224">New label: Wait for one hour.</span></span>
   - <span data-ttu-id="627c0-225">既存のラベル: 24 時間待機します。</span><span class="sxs-lookup"><span data-stu-id="627c0-225">Existing label: Wait for 24 hours.</span></span>

3. <span data-ttu-id="627c0-226">この待ち時間の後、テスト ユーザー アカウントのいずれかを使用して、手順 1 で作成したラベルを持つチーム、Microsoft 365 グループ、または SharePoint サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="627c0-226">After this wait period, use one of the test user accounts to create a team, Microsoft 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="627c0-227">この作成操作中にエラーが発生しなかった場合、テナント内のすべてのユーザーに安全にラベルを発行できます。</span><span class="sxs-lookup"><span data-stu-id="627c0-227">If there are no errors during this creation operation, you know it's safe to publish the label to all users in your tenant.</span></span>

### <a name="modifying-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="627c0-228">サイトとグループに対して構成されている発行済みのラベルを変更する</span><span class="sxs-lookup"><span data-stu-id="627c0-228">Modifying published labels that are configured for sites and groups</span></span>

<span data-ttu-id="627c0-229">ベスト プラクティスとして、秘密度ラベルを複数のチーム、グループ、またはサイトに適用した後に、ラベルのサイトとグループの設定を変更しないようにします。</span><span class="sxs-lookup"><span data-stu-id="627c0-229">As a best practice, don't change the site and group settings for a sensitivity label after the label has been applied to teams, groups, or sites.</span></span> <span data-ttu-id="627c0-230">この場合、ラベルが適用されているすべてのコンテナーに変更を複製されるまで 24 時間待機することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="627c0-230">If you do, remember to wait for 24 hours for the changes to replicate to all containers that have the label applied.</span></span>

<span data-ttu-id="627c0-231">また、**外部ユーザーのアクセス** 設定を含む変更は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="627c0-231">In addition, if your changes include the **External users access** setting:</span></span>

- <span data-ttu-id="627c0-p126">新しい設定は新しいユーザーに適用されますが、既存のユーザーには適用されません。たとえば、この設定は以前に選択されていて、その結果、ゲスト ユーザーがサイトにアクセスした場合、この設定をラベル構成で解除した後も、これらのゲスト ユーザーはサイトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="627c0-p126">The new setting applies to new users but not to existing users. For example, if this setting was previously selected and as a result, guest users accessed the site, these guest users can still access the site after this setting is cleared in the label configuration.</span></span>

- <span data-ttu-id="627c0-234">HiddenMembership および roleEnabled グループ プロパティのプライバシー設定は更新されません。</span><span class="sxs-lookup"><span data-stu-id="627c0-234">The privacy settings for the group properties hiddenMembership and roleEnabled aren't updated.</span></span>

### <a name="deleting-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="627c0-235">サイトとグループに対して構成されている発行済みラベルを削除する</span><span class="sxs-lookup"><span data-stu-id="627c0-235">Deleting published labels that are configured for sites and groups</span></span>

<span data-ttu-id="627c0-p127">サイトとグループの設定を有効にして秘密度ラベルの削除を行い、そのラベルが 1 つ以上のラベル ポリシーに含まれている場合、新しいチーム、グループ、サイトの作成に失敗してしまう可能性があります。この状況を回避するには、次のガイダンスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="627c0-p127">If you delete a sensitivity label that has the site and group settings enabled, and that label is included in one or more label policies, this action can result in creation failures for new teams, groups, and sites. To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="627c0-238">ラベルを含むすべてのラベル ポリシーから、機密ラベルを削除します。</span><span class="sxs-lookup"><span data-stu-id="627c0-238">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="627c0-239">1 時間待機します。</span><span class="sxs-lookup"><span data-stu-id="627c0-239">Wait for one hour.</span></span>

3. <span data-ttu-id="627c0-240">この待ち時間の後、チーム、グループ、またはサイトを作成し、ラベルが表示されなくなったことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="627c0-240">After this wait period, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="627c0-241">秘密度ラベルが表示されていない場合は、ラベルを安全に削除できます。</span><span class="sxs-lookup"><span data-stu-id="627c0-241">If the sensitivity label isn't visible, you can now safely delete the label.</span></span>

## <a name="how-to-apply-sensitivity-labels-to-containers"></a><span data-ttu-id="627c0-242">コンテナーに秘密度ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="627c0-242">How to apply sensitivity labels to containers</span></span>

<span data-ttu-id="627c0-243">これで、１つまたは複数の秘密度ラベルを次のようなコンテナーに適用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="627c0-243">You're now ready to apply the sensitivity label or labels to the following containers:</span></span>

- [<span data-ttu-id="627c0-244">Azure AD の Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="627c0-244">Microsoft 365 group in Azure AD</span></span>](#apply-sensitivity-labels-to-microsoft-365-groups)
- [<span data-ttu-id="627c0-245">Microsoft Teams のチーム サイト</span><span class="sxs-lookup"><span data-stu-id="627c0-245">Microsoft Teams team site</span></span>](#apply-a-sensitivity-label-to-a-new-team)
- [<span data-ttu-id="627c0-246">Outlook on the web の Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="627c0-246">Microsoft 365 group in Outlook on the web</span></span>](#apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web)
- [<span data-ttu-id="627c0-247">SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="627c0-247">SharePoint site</span></span>](#apply-a-sensitivity-label-to-a-new-site)

<span data-ttu-id="627c0-248">[複数のサイトに秘密度ラベルを適用する](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites) 必要がある場合、PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="627c0-248">You can use PowerShell if you need to [apply a sensitivity label to multiple sites](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites).</span></span>

### <a name="apply-sensitivity-labels-to-microsoft-365-groups"></a><span data-ttu-id="627c0-249">Microsoft 365 グループに秘密度ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="627c0-249">Apply sensitivity labels to Microsoft 365 groups</span></span>

<span data-ttu-id="627c0-250">これで、1 つまたは複数の秘密度ラベルを Microsoft 365 グループに適用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="627c0-250">You're now ready to apply the sensitivity label or labels to Microsoft 365 groups.</span></span> <span data-ttu-id="627c0-251">手順については、Azure AD のドキュメントに戻ります。</span><span class="sxs-lookup"><span data-stu-id="627c0-251">Return to the Azure AD documentation for instructions:</span></span>

- <span data-ttu-id="627c0-252">「[Assign a label to a new group in Azure portal (Azure ポータルの新しいグループにラベルを割り当てる)](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)」</span><span class="sxs-lookup"><span data-stu-id="627c0-252">[Assign a label to a new group in Azure portal](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)</span></span>

- [<span data-ttu-id="627c0-253">Assign a label to an existing group in Azure portal (Azure ポータルの既存のグループにラベルを割り当てる)</span><span class="sxs-lookup"><span data-stu-id="627c0-253">Assign a label to an existing group in Azure portal</span></span>](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

- <span data-ttu-id="627c0-254">「[Remove a label from an existing group in Azure portal (Azure ポータルの既存のグループからラベルを削除する)](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).」</span><span class="sxs-lookup"><span data-stu-id="627c0-254">[Remove a label from an existing group in Azure portal](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="627c0-255">新しいチームに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="627c0-255">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="627c0-256">ユーザーは、Microsoft Teams で新しいチームを作成する際に機密ラベルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="627c0-256">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="627c0-257">**[秘密度]** ドロップダウンからラベルを選択すると、プライバシー設定によってラベル構成が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="627c0-257">When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration.</span></span> <span data-ttu-id="627c0-258">ラベルに対し選択した外部ユーザーのアクセス設定に応じて、ユーザーは組織外のユーザーをチームに追加することができたり、できなかったりします。</span><span class="sxs-lookup"><span data-stu-id="627c0-258">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="627c0-259">Teams の機密ラベルの詳細について</span><span class="sxs-lookup"><span data-stu-id="627c0-259">Learn more about sensitivity labels for Teams</span></span>](/microsoftteams/sensitivity-labels)

![新しいチームを作成する際のプライバシー設定](../media/privacy-setting-new-team.png)

<span data-ttu-id="627c0-261">チームを作成すると、すべてのチャネルの右上隅に機密ラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="627c0-261">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![チームに表示される機密ラベル](../media/privacy-setting-teams.png)

<span data-ttu-id="627c0-263">このサービスは、Microsoft 365 グループおよび接続された SharePoint チーム サイトに対して同じ秘密度ラベルを自動的に適用します。</span><span class="sxs-lookup"><span data-stu-id="627c0-263">The service automatically applies the same sensitivity label to the Microsoft 365 group and the connected SharePoint team site.</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="627c0-264">Outlook on the web の新しいグループに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="627c0-264">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="627c0-265">Outlook on the web では、新しいグループを作成するときに、公開されたラベルの [**機密**] オプションを選択または変更できます。</span><span class="sxs-lookup"><span data-stu-id="627c0-265">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![グループを作成し、[機密] 下でオプションを選択する](../media/sensitivity-label-new-group.png)

### <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="627c0-267">新しいサイトに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="627c0-267">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="627c0-268">管理者およびエンド ユーザーは、[最新のチーム サイトやコミュニケーション サイトを作成する](/sharepoint/create-site-collection)際に秘密度ラベルを選択し、以下のような **詳細設定** を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="627c0-268">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection), and expand **Advanced settings**:</span></span>

![サイトを作成し、[秘密度] 下でオプションを選択する](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="627c0-270">ドロップダウン ボックスには選択したラベル名が表示され、ヘルプ アイコンにはすべてのラベル名とヒントが表示されます。これにより、ユーザーは適用するラベルを正しく選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="627c0-270">The dropdown box displays the label names for the selection, and the help icon displays all the label names with their tooltip, which can help users determine the correct label to apply.</span></span>

<span data-ttu-id="627c0-271">ラベルが適用され、ユーザーがサイトを参照すると、ラベルの名前および適用されているポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="627c0-271">When the label is applied, and users browse to the site, they see the name of the label and applied policies.</span></span> <span data-ttu-id="627c0-272">たとえば、以下のサイトでは、**秘密** のラベル付けがされており、プライバシー設定は **プライベート** になっています。</span><span class="sxs-lookup"><span data-stu-id="627c0-272">For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span></span>

![機密ラベルが適用されているサイト](../media/sensitivity-label-site.png)

### <a name="use-powershell-to-apply-a-sensitivity-label-to-multiple-sites"></a><span data-ttu-id="627c0-274">PowerShell を使用して、複数のサイトに秘密度ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="627c0-274">Use PowerShell to apply a sensitivity label to multiple sites</span></span>

<span data-ttu-id="627c0-275">[Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) と [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) コマンドレットを使用して、現在の [SharePoint Online 管理シェル](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)の *SensitivityLabel* パラメーターによって、多くのサイトに秘密度ラベルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="627c0-275">You can use the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) and [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) cmdlet with the *SensitivityLabel* parameter from the current [SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) to apply a sensitivity label to many sites.</span></span> <span data-ttu-id="627c0-276">サイトには、任意の SharePoint サイトコレクション、または OneDrive サイトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="627c0-276">The sites can be any SharePoint site collection, or a OneDrive site.</span></span>

<span data-ttu-id="627c0-277">SharePoint Online 管理シェルのバージョン16.0.19418.12000 以降があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="627c0-277">Make sure you have version 16.0.19418.12000 or later of the SharePoint Online Management Shell.</span></span>

1. <span data-ttu-id="627c0-278">**[管理者として実行]** オプションを使用して PowerShell セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="627c0-278">Open a PowerShell session with the **Run as Administrator** option.</span></span>

2. <span data-ttu-id="627c0-279">ラベルの GUID がわからない場合、[セキュリティ/コンプライアンス センターの PowerShellに接続し](/powershell/exchange/connect-to-scc-powershell)、秘密度ラベルとそれらの GUID のリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="627c0-279">If you don't know your label GUID: [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and get the list of sensitivity labels and their GUIDs.</span></span>

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. <span data-ttu-id="627c0-280">ここでは、[SharePoint Online PowerShellに接続して](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)、ラベルの GUID を変数として保存します。</span><span class="sxs-lookup"><span data-stu-id="627c0-280">Now [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and store your label GUID as a variable.</span></span> <span data-ttu-id="627c0-281">例:</span><span class="sxs-lookup"><span data-stu-id="627c0-281">For example:</span></span>

   ```powershell
   $Id = [GUID]("e48058ea-98e8-4940-8db0-ba1310fd955e")
   ```

4. <span data-ttu-id="627c0-p133">URL に共通の識別文字列が含まれる複数のサイトを特定する新しい変数を作成します。例:</span><span class="sxs-lookup"><span data-stu-id="627c0-p133">Create a new variable that identifies multiple sites that have an identifying string in common in their URL. For example:</span></span>

   ```powershell
   $sites = Get-SPOSite -IncludePersonalSite $true -Limit all -Filter "Url -like 'documents"
   ```

5. <span data-ttu-id="627c0-p134">これらのサイトにラベルを適用するには、次のコマンドを実行します。例:</span><span class="sxs-lookup"><span data-stu-id="627c0-p134">Run the following command to apply the label to these sites. Using our examples:</span></span>

   ```powershell
   $sites | ForEach-Object {Set-SPOTenant $_.url -SensitivityLabel $Id}
   ```

<span data-ttu-id="627c0-286">この一連のコマンドを使用すると、テナント全体の複数のサイトに同じ秘密度ラベルを付けることができます。そのため、サイトごとの構成用の Set-SPOSite コマンドレットではなく、Set-SPOTenant コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="627c0-286">This series of commands lets you label multiple sites across your tenant with the same sensitivity label, which is why you use the Set-SPOTenant cmdlet, rather than the Set-SPOSite cmdlet that's for per-site configuration.</span></span> <span data-ttu-id="627c0-287">ただし、特定のサイトに異なるラベルを適用する必要がある場合は、サイトごとに次のコマンドを繰り返して、Set-SPOSite コマンドレットを使用します。`Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span><span class="sxs-lookup"><span data-stu-id="627c0-287">However, use the Set-SPOSite cmdlet when you need to apply a different label to specific sites by repeating the following command for each of these sites: `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span></span>

## <a name="view-and-manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="627c0-288">SharePoint 管理センターで秘密度ラベルを表示し管理する</span><span class="sxs-lookup"><span data-stu-id="627c0-288">View and manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="627c0-289">適用された秘密度ラベルを表示、並べ替え、および検索するには、新しい SharePoint 管理センターの [**アクティブなサイト**] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="627c0-289">To view, sort, and search the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="627c0-290">最初に、[**機密**] 列を追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="627c0-290">You might need to first add the **Sensitivity** column:</span></span>

![[アクティブなサイト] ページの [機密] 列](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="627c0-292">列を追加する方法など、[アクティブなサイト] ページからサイトを管理する方法の詳細については、「[新しい SharePoint 管理センターでサイトを管理する](/sharepoint/manage-sites-in-new-admin-center)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="627c0-292">For more information about managing sites from the Active sites page, including how to add a column, see [Manage sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

<span data-ttu-id="627c0-293">このページからラベルを変更して適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="627c0-293">You can also change and apply a label from this page:</span></span>

1. <span data-ttu-id="627c0-294">[詳細] ウィンドウを開くには、サイト名を選択します。</span><span class="sxs-lookup"><span data-stu-id="627c0-294">Select the site name to open the details pane.</span></span>

2. <span data-ttu-id="627c0-295">[**ポリシー**] タブを選択し、**秘密度** の設定で [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="627c0-295">Select the **Policies** tab, and then select **Edit** for the **Sensitivity** setting.</span></span>

3. <span data-ttu-id="627c0-296">[**秘密度の設定の編集**] ウィンドウで、サイトに適用する秘密度ラベルを選び、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="627c0-296">From the **Edit sensitivity setting** pane, select the sensitivity label you want to apply to the site, and then select **Save**.</span></span>

## <a name="support-for-sensitivity-labels"></a><span data-ttu-id="627c0-297">秘密度ラベルのサポート</span><span class="sxs-lookup"><span data-stu-id="627c0-297">Support for sensitivity labels</span></span>

<span data-ttu-id="627c0-298">次のアプリとサービスで、サイトとグループの設定用に構成した秘密度ラベルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="627c0-298">The following apps and services support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="627c0-299">管理センター:</span><span class="sxs-lookup"><span data-stu-id="627c0-299">Admin centers:</span></span>

  - <span data-ttu-id="627c0-300">SharePoint 管理センター</span><span class="sxs-lookup"><span data-stu-id="627c0-300">SharePoint admin center</span></span>
  - <span data-ttu-id="627c0-301">Azure Active Directory ポータル</span><span class="sxs-lookup"><span data-stu-id="627c0-301">Azure Active Directory portal</span></span>
  - <span data-ttu-id="627c0-302">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="627c0-302">Microsoft 365 admin center</span></span>
  - <span data-ttu-id="627c0-303">Microsoft 365 コンプライアンス センター、Microsoft 365 セキュリティ センター、セキュリティ/コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="627c0-303">Microsoft 365 compliance center, Microsoft 365 security center, Security & Compliance Center</span></span>

- <span data-ttu-id="627c0-304">ユーザーのアプリとサービス:</span><span class="sxs-lookup"><span data-stu-id="627c0-304">User apps and services:</span></span>

  - <span data-ttu-id="627c0-305">SharePoint</span><span class="sxs-lookup"><span data-stu-id="627c0-305">SharePoint</span></span>
  - <span data-ttu-id="627c0-306">Teams</span><span class="sxs-lookup"><span data-stu-id="627c0-306">Teams</span></span>
  - <span data-ttu-id="627c0-307">Outlook on the web、Outlook for Windows、MacOS、iOS、Android</span><span class="sxs-lookup"><span data-stu-id="627c0-307">Outlook on the web and for Windows, macOS, iOS, and Android</span></span>
  - <span data-ttu-id="627c0-308">フォーム</span><span class="sxs-lookup"><span data-stu-id="627c0-308">Forms</span></span>
  - <span data-ttu-id="627c0-309">Stream</span><span class="sxs-lookup"><span data-stu-id="627c0-309">Stream</span></span>
  - <span data-ttu-id="627c0-310">Planner</span><span class="sxs-lookup"><span data-stu-id="627c0-310">Planner</span></span> 

<span data-ttu-id="627c0-311">次のアプリとサービスで、サイトとグループの設定用に構成した秘密度ラベルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="627c0-311">The following apps and services don't currently support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="627c0-312">管理センター:</span><span class="sxs-lookup"><span data-stu-id="627c0-312">Admin centers:</span></span>

  - <span data-ttu-id="627c0-313">Teams 管理センター</span><span class="sxs-lookup"><span data-stu-id="627c0-313">Teams admin center</span></span>
  - <span data-ttu-id="627c0-314">Exchange 管理センター</span><span class="sxs-lookup"><span data-stu-id="627c0-314">Exchange admin center</span></span>

- <span data-ttu-id="627c0-315">ユーザーのアプリとサービス:</span><span class="sxs-lookup"><span data-stu-id="627c0-315">User apps and services:</span></span>

  - <span data-ttu-id="627c0-316">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="627c0-316">Dynamics 365</span></span>
  - <span data-ttu-id="627c0-317">Yammer</span><span class="sxs-lookup"><span data-stu-id="627c0-317">Yammer</span></span>
  - <span data-ttu-id="627c0-318">Project</span><span class="sxs-lookup"><span data-stu-id="627c0-318">Project</span></span>
  - <span data-ttu-id="627c0-319">Power BI</span><span class="sxs-lookup"><span data-stu-id="627c0-319">Power BI</span></span>

## <a name="classic-azure-ad-group-classification"></a><span data-ttu-id="627c0-320">従来の Azure AD グループの分類</span><span class="sxs-lookup"><span data-stu-id="627c0-320">Classic Azure AD group classification</span></span>

<span data-ttu-id="627c0-321">コンテナーの秘密度ラベルを有効にすると、Microsoft 365 は新しい Microsoft 365 のグループおよび SharePoint サイト向けに古い分類をサポートしなくなります。</span><span class="sxs-lookup"><span data-stu-id="627c0-321">Microsoft 365 no longer supports the old classifications for new Microsoft 365 groups and SharePoint sites after you enable sensitivity labels for containers.</span></span> <span data-ttu-id="627c0-322">ただし、秘密度ラベルをサポートしている既存のグループおよびサイトには、秘密度ラベルを使用するように変換しない限り、古い分類値が引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="627c0-322">However, existing groups and sites that support sensitivity labels still display the old classification values until you convert them to use sensitivity labels.</span></span>

<span data-ttu-id="627c0-323">SharePoint の古いグループ分類を使用した場合の例として、「[SharePoint の "モダン" サイトの分類」](/sharepoint/dev/solution-guidance/modern-experience-site-classification)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="627c0-323">As an example of how you might have used the old group classification for SharePoint, see [SharePoint "modern" sites classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="627c0-324">これらの分類は、Azure AD PowerShell または PnP コア ライブラリを使用し、`ClassificationList` 設定に値を定義することによって構成されています。</span><span class="sxs-lookup"><span data-stu-id="627c0-324">These classifications were configured by using Azure AD PowerShell or the PnP Core library and defining values for the `ClassificationList` setting.</span></span> <span data-ttu-id="627c0-325">テナントに分類値が定義されている場合は、[AzureADPreview PowerShell モジュール](https://www.powershellgallery.com/packages/AzureADPreview)から次のコマンドを実行すると、それらが表示されます。</span><span class="sxs-lookup"><span data-stu-id="627c0-325">If your tenant has classification values defined, they are shown when you run the following command from the [AzureADPreview PowerShell module](https://www.powershellgallery.com/packages/AzureADPreview):</span></span>

```powershell
($setting["ClassificationList"])
```

<span data-ttu-id="627c0-326">古い分類を機密ラベルに変換するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="627c0-326">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="627c0-327">既存のラベルを使用: 既に公開されている既存の機密ラベルを編集して、サイトおよびグループに必要なラベル設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="627c0-327">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="627c0-328">新しいラベルの作成: 既存の分類と同じ名前を持つ新しい機密ラベルを作成および公開して、サイトおよびグループに必要なラベル設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="627c0-328">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="627c0-329">その後で以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="627c0-329">Then:</span></span>

1. <span data-ttu-id="627c0-p139">PowerShell を使用し、既存の Microsoft 365 グループおよび SharePoint サイトに名前のマッピングを使用して秘密度ラベルを適用します。手順については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="627c0-p139">Use PowerShell to apply the sensitivity labels to existing Microsoft 365 groups and SharePoint sites by using name mapping. See the next section for instructions.</span></span>

2. <span data-ttu-id="627c0-332">既存のグループおよびサイトから古い分類を削除します。</span><span class="sxs-lookup"><span data-stu-id="627c0-332">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="627c0-333">機密ラベルをまだサポートしていないアプリやサービスでユーザーが新しいグループを作成できないようにすることはできませんが、定期的な PowerShell スクリプトを実行して、ユーザーが古い分類で作成した新しいグループを探し、機密ラベルを使用するようにそれらを変換することができます。</span><span class="sxs-lookup"><span data-stu-id="627c0-333">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span>

<span data-ttu-id="627c0-334">サイトとグループの秘密度ラベルと Azure AD の分類の共存を管理する方法については、「[Microsoft 365 グループの Azure Active Directory の分類と秘密度ラベル](migrate-aad-classification-sensitivity-labels.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="627c0-334">To help you manage the coexistence of sensitivity labels and Azure AD classifications for sites and groups, see [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](migrate-aad-classification-sensitivity-labels.md).</span></span>

### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a><span data-ttu-id="627c0-335">PowerShell を使用して Microsoft 365 グループの分類を秘密度ラベルに変換する</span><span class="sxs-lookup"><span data-stu-id="627c0-335">Use PowerShell to convert classifications for Microsoft 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="627c0-336">まず、[セキュリティ/コンプライアンス センターの PowerShell に接続します](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="627c0-336">First, [connect to Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="627c0-337">たとえば、管理者として実行している PowerShell セッションで、グローバル管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="627c0-337">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>

2. <span data-ttu-id="627c0-338">[Get-Label](/powershell/module/exchange/get-label) コマンドレットを使用して、機密ラベルおよびその GUID のリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="627c0-338">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](/powershell/module/exchange/get-label) cmdlet:</span></span>

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. <span data-ttu-id="627c0-339">Microsoft 365 グループに適用する秘密度ラベルの GUID をメモします。</span><span class="sxs-lookup"><span data-stu-id="627c0-339">Make a note of the GUIDs for the sensitivity labels you want to apply to your Microsoft 365 groups.</span></span>

4. <span data-ttu-id="627c0-340">ここでは、別の Windows PowerShell ウィンドウで [Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="627c0-340">Now [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a separate Windows PowerShell window.</span></span>

5. <span data-ttu-id="627c0-341">次のコマンドを例として使用して、現在 "一般" の分類を持つグループのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="627c0-341">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="627c0-p140">グループごとに、新しい機密ラベル GUID を追加します。例:</span><span class="sxs-lookup"><span data-stu-id="627c0-p140">For each group, add the new sensitivity label GUID. For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. <span data-ttu-id="627c0-344">残りのグループ分類について、手順 5 と 6 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="627c0-344">Repeat steps 5 and 6 for your remaining group classifications.</span></span>

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="627c0-345">機密ラベル アクティビティの監査</span><span class="sxs-lookup"><span data-stu-id="627c0-345">Auditing sensitivity label activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="627c0-346">コンテナを保護するラベルの **[グループとサイト]** スコープのみを選択してラベル分離を使用する場合: このセクションで説明する **検出されたドキュメントの機密性の不一致** の監査イベントとメールのため、**ファイルとメール** のスコープを持つラベルの前に [これらのラベルの順序付け](sensitivity-labels.md#label-priority-order-matters)を検討してください。</span><span class="sxs-lookup"><span data-stu-id="627c0-346">If you use label separation by selecting just the **Groups & sites** scope for labels that protect containers: Because of the **Detected document sensitivity mismatch** audit event and email described in this section, consider [ordering these labels](sensitivity-labels.md#label-priority-order-matters) before labels that have a scope for **Files & emails**.</span></span> 

<span data-ttu-id="627c0-347">誰かが機密ラベルで保護されているサイトにドキュメントをアップロードし、そのドキュメントの機密ラベルが、サイトに適用されている機密ラベルよりも[優先度が高く](sensitivity-labels.md#label-priority-order-matters)なっている場合、このアクションはブロックされません。</span><span class="sxs-lookup"><span data-stu-id="627c0-347">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="627c0-348">たとえば、「**一般**」ラベルを SharePoint サイトに適用し、誰かがこのサイトに「**社外秘**」というラベルの付けられたドキュメントをアップロードしたとします。</span><span class="sxs-lookup"><span data-stu-id="627c0-348">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="627c0-349">優先度の高い機密ラベルは、優先順位の低いコンテンツよりも機密性の高いコンテンツを識別するため、この状況はセキュリティ上の懸念になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="627c0-349">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="627c0-350">アクションはブロックされていませんが、監査され、既定で、ドキュメントをアップロードした人とサイト管理者にメールが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="627c0-350">Although the action isn't blocked, it is audited and by default, automatically generates an email to the person who uploaded the document and the site administrator.</span></span> <span data-ttu-id="627c0-351">結果として、ユーザーと管理者の両方が、この不適切なラベルの優先順位を設定し、必要に書類を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="627c0-351">As a result, both the user and administrators can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="627c0-352">たとえば、アップロードされたドキュメントをサイトから削除または移動します。</span><span class="sxs-lookup"><span data-stu-id="627c0-352">For example, delete or move the uploaded document from the site.</span></span>

<span data-ttu-id="627c0-353">ドキュメントの機密ラベルが、サイトに適用されている機密ラベルよりも優先度が低い場合、セキュリティ上の懸念にはなりません。</span><span class="sxs-lookup"><span data-stu-id="627c0-353">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="627c0-354">たとえば、「**一般**」というラベルの付いたドキュメントが、「**社外秘**」というラベルの付いたサイトにアップロードされている場合です。</span><span class="sxs-lookup"><span data-stu-id="627c0-354">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="627c0-355">このシナリオでは、監査イベントとメールが生成されません。</span><span class="sxs-lookup"><span data-stu-id="627c0-355">In this scenario, an auditing event and email aren't generated.</span></span>

<span data-ttu-id="627c0-356">このイベントの監査ログを検索するには、[**ファイルとページのアクティビティ**] カテゴリから [**検出されたドキュメントの機密度の不一致**] を探します。</span><span class="sxs-lookup"><span data-stu-id="627c0-356">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span>

<span data-ttu-id="627c0-357">自動生成されたメールには、サブジェクト **の互換性がない秘密度ラベルが検出されました** とメールメッセージは、アップロードされたドキュメントとサイトへのリンクとのラベルの不一致を説明します。</span><span class="sxs-lookup"><span data-stu-id="627c0-357">The automatically generated email has the subject **Incompatible sensitivity label detected** and the email message explains the labeling mismatch with a link to the uploaded document and site.</span></span> <span data-ttu-id="627c0-358">ユーザーが感度ラベルを変更できるようにするドキュメントリンクも含まれています。</span><span class="sxs-lookup"><span data-stu-id="627c0-358">It also contains a documentation link that explains how users can change the sensitivity label.</span></span> <span data-ttu-id="627c0-359">これらの自動メールはカスタマイズできませんが、[Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) から次の PowerShell コマンドを使用すると、送信されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="627c0-359">These automated emails cannot be customized but you can prevent them from being sent when you use the following PowerShell command from [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant):</span></span>

```PowerShell
Set-SPOTenant -BlockSendLabelMismatchEmail $True
```

<span data-ttu-id="627c0-360">サイトまたはグループに対して、または、ある人が機密ラベルを追加または削除する場合、これらのアクティビティも監査されますが、メールは自動的に生成されません。</span><span class="sxs-lookup"><span data-stu-id="627c0-360">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited but without automatically generating an email.</span></span>

<span data-ttu-id="627c0-361">これらの監査イベントはすべて、[秘密ラベルのアクティビティ](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) カテゴリに記載されています。</span><span class="sxs-lookup"><span data-stu-id="627c0-361">All these auditing events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> <span data-ttu-id="627c0-362">監査ログを検索する手順については、「[セキュリティ/コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="627c0-362">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="how-to-disable-sensitivity-labels-for-containers"></a><span data-ttu-id="627c0-363">コンテナーの秘密度ラベルを無効にする方法</span><span class="sxs-lookup"><span data-stu-id="627c0-363">How to disable sensitivity labels for containers</span></span>

<span data-ttu-id="627c0-364">「[PowerShell で秘密度ラベルのサポートを有効にする](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell)」と同じ手順で、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトの秘密度ラベルをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="627c0-364">You can turn off sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="627c0-365">ただし、この機能を無効にするには、手順5で `$setting["EnableMIPLabels"] = "False"`を指定します。</span><span class="sxs-lookup"><span data-stu-id="627c0-365">However, to disable the feature, in step 5, specify `$setting["EnableMIPLabels"] = "False"`.</span></span>

<span data-ttu-id="627c0-366">秘密度ラベルを作成または編集するときに、グループおよびサイトですべての設定を使用できないようにすることに加えて、この操作では、コンテナーが構成に使用するプロパティは元に戻ります。</span><span class="sxs-lookup"><span data-stu-id="627c0-366">In addition to making all the settings unavailable for groups and sites when you create or edit sensitivity labels, this action reverts which property the containers use for their configuration.</span></span> <span data-ttu-id="627c0-367">Microsoft Teams、Microsoft 365 グループ、SharePoint サイトで秘密度ラベルを有効にすると、**分類** ([Azure AD グループの分類](#classic-azure-ad-group-classification) に使用) に使用されているプロパティが **秘密度** に切り替わります。</span><span class="sxs-lookup"><span data-stu-id="627c0-367">Enabling sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites switches the property used from **Classification** (used for [Azure AD group classification](#classic-azure-ad-group-classification)) to **Sensitivity**.</span></span> <span data-ttu-id="627c0-368">コンテナーの秘密度ラベルを無効にすると、コンテナーは秘密度プロパティを無視して、もう一度分類プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="627c0-368">When you disable sensitivity labels for containers, the containers ignore the Sensitivity property and use the Classification property again.</span></span>

<span data-ttu-id="627c0-369">つまり、以前コンテナーに適用されたサイトとグループのラベル設定が適用されなくなり、コンテナーにはラベルが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="627c0-369">This means that any label settings from sites and groups previously applied to containers won't be enforced, and containers no longer display the labels.</span></span>

<span data-ttu-id="627c0-370">これらのコンテナーに Azure AD 分類値が適用されている場合、コンテナーは再び分類を使用します。</span><span class="sxs-lookup"><span data-stu-id="627c0-370">If these containers have Azure AD classification values applied to them, the containers revert to using the classifications again.</span></span> <span data-ttu-id="627c0-371">この機能を有効にした後に作成された新しいサイトやグループにはラベルが表示されず、分類もされないので注意してください。</span><span class="sxs-lookup"><span data-stu-id="627c0-371">Be aware that any new sites or groups that were created after enabling the feature won't display a label or have a classification.</span></span> <span data-ttu-id="627c0-372">これらのコンテナー、および新しいコンテナーの場合、分類値を適用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="627c0-372">For these containers, and any new containers, you can now apply classification values.</span></span> <span data-ttu-id="627c0-373">詳細については、「[SharePoint の 「最新の」 サイト分類](/sharepoint/dev/solution-guidance/modern-experience-site-classification)」 および 「[組織の Office グループの分類を作成する](../enterprise/manage-microsoft-365-groups-with-powershell.md)」 を参照してください。。</span><span class="sxs-lookup"><span data-stu-id="627c0-373">For more information, see [SharePoint "modern" sites classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) and [Create classifications for Office groups in your organization](../enterprise/manage-microsoft-365-groups-with-powershell.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="627c0-374">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="627c0-374">Additional resources</span></span>

<span data-ttu-id="627c0-375">[Microsoft Teams、O365 グループおよび SharePoint Online サイトでの秘密度ラベルの使用](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380)については、ウェビナーのレコーディングと回答をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="627c0-375">See the webinar recording and answered questions for [Using Sensitivity labels with Microsoft Teams, O365 Groups and SharePoint Online sites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span></span>

<span data-ttu-id="627c0-376">このウェビナーは、当該機能がまだプレビューに含まれているときに記録されているので、UI にいくつかの矛盾が見つかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="627c0-376">This webinar was recorded when the feature was still in preview, so you might notice some discrepancies in the UI.</span></span> <span data-ttu-id="627c0-377">ただし、このページに記載されている新しい機能があれば、この機能の情報は正確です。</span><span class="sxs-lookup"><span data-stu-id="627c0-377">However, the information for this feature is still accurate, with any new capabilities documented on this page.</span></span>