---
title: Microsoft Teams、Office 365 グループ、SharePoint サイトで機密ラベルを使用する (パブリック プレビュー)
ms.author: krowley
author: cabailey
manager: laurawi
ms.date: 12/13/2019
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
ms.openlocfilehash: edaa13a21d5eb9069c6e4dce509c13456dec3d89
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802880"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="0b696-103">Microsoft Teams、Office 365 グループ、SharePoint サイトで機密ラベルを使用する (パブリック プレビュー)</span><span class="sxs-lookup"><span data-stu-id="0b696-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="0b696-104">[Microsoft 365 コンプライアンス センター](https://protection.office.com/)で機密ラベルを作成する場合、Microsoft Teams、Office 365 グループ、SharePoint サイトへと適用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0b696-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="0b696-105">ポリシーをラベルに関連付けることで、以下を制御できます。</span><span class="sxs-lookup"><span data-stu-id="0b696-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="0b696-106">パブリック/プライベート設定</span><span class="sxs-lookup"><span data-stu-id="0b696-106">Public/private settings</span></span>
- <span data-ttu-id="0b696-107">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="0b696-107">Guest access</span></span>
- <span data-ttu-id="0b696-108">非管理対象デバイスからのアクセス</span><span class="sxs-lookup"><span data-stu-id="0b696-108">Access from unmanaged devices</span></span>

<span data-ttu-id="0b696-109">ラベルをチームまたはグループに適用すると、ラベルは接続された SharePoint チーム サイトに自動的に適用され、その逆の場合にも同様に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0b696-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="0b696-110">また、SharePoint および OneDrive で Office ファイルの機密ラベルを有効にできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0b696-110">You can now also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="0b696-111">詳細については、「[SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする (パブリック プレビュー)](sensitivity-labels-sharepoint-onedrive-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b696-111">[Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md)</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="0b696-112">Microsoft Teams、Office 365 グループ、および SharePoint サイトのパブリック プレビューについて</span><span class="sxs-lookup"><span data-stu-id="0b696-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="0b696-113">Microsoft Teams、Office 365 グループ、および SharePoint サイト向けの機密ラベルは徐々にテナントへと展開され、最終リリース前に変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0b696-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites are gradually rolling out to tenants and might change before final release.</span></span>

<span data-ttu-id="0b696-114">このパブリック プレビューは、Office 365 コンテンツ配信ネットワーク (CDN) では機能しません。</span><span class="sxs-lookup"><span data-stu-id="0b696-114">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="overview"></a><span data-ttu-id="0b696-115">概要</span><span class="sxs-lookup"><span data-stu-id="0b696-115">Overview</span></span>

<span data-ttu-id="0b696-116">機密ラベルを発行すると、Office 365 全体のユーザーが同じラベルのリストにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0b696-116">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="0b696-117">これらの画像は以下について示しています。</span><span class="sxs-lookup"><span data-stu-id="0b696-117">These images show:</span></span>

- <span data-ttu-id="0b696-118">SharePoint から新しいチーム サイトを作成する際のリストの表示内容</span><span class="sxs-lookup"><span data-stu-id="0b696-118">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="0b696-119">Word でリストを表示する場合</span><span class="sxs-lookup"><span data-stu-id="0b696-119">When you view the list in Word</span></span>

<span data-ttu-id="0b696-120">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0b696-120">For example:</span></span>

![SharePoint でチーム サイトを作成するときの機密ラベル](media/sensitivity-label-new-team-site.png)

![Word デスクトップ アプリに表示される機密ラベル](media/sensitivity-label-word.png)

## <a name="enable-this-preview"></a><span data-ttu-id="0b696-123">このプレビューを有効にする</span><span class="sxs-lookup"><span data-stu-id="0b696-123">Enable this preview</span></span>

<span data-ttu-id="0b696-124">Microsoft Teams、Office 365 グループ、および SharePoint サイトで機密ラベルのこのプレビューを有効にするには、[Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) (モジュール名 **AzureADPreview**) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b696-124">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) (module name **AzureADPreview**) to enable this preview of sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites:</span></span>

- <span data-ttu-id="0b696-125">以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Installing the Azure AD Module (Azure AD モジュールのインストール)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="0b696-125">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="0b696-126">Azure AD PowerShell モジュール (AzureAD) の 2.0 一般提供バージョンをインストールしている場合には、PowerShell セッションで`Uninstall-Module AzureAD`を実行してアンインストールし、`Install-Module AzureADPreview`を実行してプレビュー バージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b696-126">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="0b696-127">プレビュー バージョンを既にインストールしている場合には、`Install-Module AzureADPreview`を実行しそれがこのモジュールの最新バージョンであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b696-127">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="0b696-128">これで Microsoft Teams、Office 365 グループ、および SharePoint サイトで機密ラベルのプレビューを有効にする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="0b696-128">You're now ready to enable the preview of sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites:</span></span>

1. <span data-ttu-id="0b696-129">PowerShell セッションで、グローバル管理者特権を持つ職場または学校のアカウントを使用して Azure Active Directory に接続します。</span><span class="sxs-lookup"><span data-stu-id="0b696-129">In a PowerShell session, using a work or school account that has global admin privileges, connect to Azure Active Directory.</span></span> <span data-ttu-id="0b696-130">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="0b696-130">For example, run:</span></span>
    
        Connect-AzureAD
    
    <span data-ttu-id="0b696-131">詳しい手順については、「[Azure AD への接続](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b696-131">For full instructions, see [Connect to Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad).</span></span>

2. <span data-ttu-id="0b696-132">以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b696-132">Run the following commands:</span></span>
    
    ```powershell
    $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
    if ($setting -eq $null)
    {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
    }
    else
    {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
    }
    ```
    
    > [!NOTE]
    > <span data-ttu-id="0b696-133">このプレビューを有効にすると、Office 365 は新しいグループおよび SharePoint サイトに古い分類を使用しなくなります。</span><span class="sxs-lookup"><span data-stu-id="0b696-133">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="0b696-134">[Azure AD サイト分類](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]) を使用した場合には、既存のグループおよびサイトには古い分類が引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b696-134">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="0b696-135">新しい分類を表示するには、それらを変換します。</span><span class="sxs-lookup"><span data-stu-id="0b696-135">To display the new classifications, convert them.</span></span> <span data-ttu-id="0b696-136">変換する方法については、「[If you used classic Azure AD site classification (従来の Azure AD サイト分類を使用した場合)](#if-you-used-classic-azure-ad-site-classification)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b696-136">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span> 

3. <span data-ttu-id="0b696-137">同じ PowerShell セッションで、グローバル管理者特権を持つ職場または学校のアカウントを使用して、セキュリティ/コンプライアンス センターに接続します。</span><span class="sxs-lookup"><span data-stu-id="0b696-137">In the same PowerShell session, now connect to the Security & Compliance Center by using a work or school account that has global admin privileges.</span></span> <span data-ttu-id="0b696-138">手順については、「[Office 365 セキュリティ/コンプライアンス センターの PowerShell への接続](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b696-138">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

4. <span data-ttu-id="0b696-139">以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b696-139">Run the following commands:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```
## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="0b696-140">機密ラベルを作成または編集する際に、サイトおよびグループの設定を行う</span><span class="sxs-lookup"><span data-stu-id="0b696-140">Set site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="0b696-141">プレビューを有効にしたら、以下の手順を使用して機密ラベルを作成または編集します。</span><span class="sxs-lookup"><span data-stu-id="0b696-141">After you enable the preview, use the following steps to create or edit sensitivity labels.</span></span> <span data-ttu-id="0b696-142">すでに定義されたラベルがある場合でも、新しい機密ラベルをサイトおよびグループで機能させるにはこれらの手順を完了させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b696-142">You must complete these steps for the new sensitivity labels to work with sites and groups, even if you already have labels defined.</span></span> <span data-ttu-id="0b696-143">これらの設定変更は、同期に最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0b696-143">Changes to these settings might take up to 24 hours to synchronize.</span></span>

1. <span data-ttu-id="0b696-144">Microsoft 365 コンプライアンス センターで [**分類**] >  [**機密ラベル**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0b696-144">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="0b696-145">[**ラベルを作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b696-145">Click **Create a label**.</span></span> <span data-ttu-id="0b696-146">ラベルが既にある場合には、次の手順へと進みます。</span><span class="sxs-lookup"><span data-stu-id="0b696-146">If you already have a label, skip to the next step.</span></span>

3. <span data-ttu-id="0b696-147">必要なオプションを選択し、[**サイトとグループの設定**] タブで以下を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b696-147">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>
    
    - <span data-ttu-id="0b696-148">プライバシー (パブリック/プライベート): プライベートとは、組織内の承認されたメンバーのみがグループ内のコンテンツを閲覧できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="0b696-148">Privacy (Public/Private): Private means that only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="0b696-149">組織内の他のユーザーは、グループの内容を見ることができません。</span><span class="sxs-lookup"><span data-stu-id="0b696-149">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="0b696-150">詳細情報</span><span class="sxs-lookup"><span data-stu-id="0b696-150">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="0b696-151">ゲストアクセス: ゲストをグループに追加できるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="0b696-151">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="0b696-152">Office 365 グループでのゲスト アクセスの管理について</span><span class="sxs-lookup"><span data-stu-id="0b696-152">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="0b696-153">管理されていないデバイス: この設定により、ハイブリッド AD に参加していないデバイスまたは Intune に準拠していないデバイスからの SharePoint コンテンツへのアクセスをブロックまたは制限することができます。</span><span class="sxs-lookup"><span data-stu-id="0b696-153">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="0b696-154">非管理対象デバイスを選択した場合、Azure AD にアクセスしてポリシーのセットアップを完了させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b696-154">If you select Unmanaged devices, you must go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="0b696-155">詳細については、「[非管理対象デバイスからのアクセスを制御する](/sharepoint/control-access-from-unmanaged-devices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b696-155">For more information, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>
    
    ![[サイトとグループの設定] タブ](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="0b696-157">チーム、グループ、またはサイトにラベルを適用すると、サイトとグループの設定のみが有効になります。</span><span class="sxs-lookup"><span data-stu-id="0b696-157">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="0b696-158">暗号化やコンテンツ マーキングなどのその他の設定は、チーム、グループ、またはサイト内のすべてのコンテンツに適用されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="0b696-158">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="0b696-159">同様に、ラベルを作成しサイトとグループの設定をオンにしない場合には、ユーザーがチーム、グループ、およびサイトを作成するときにラベルは引き続き使用できますが、いかなる設定も適用せずに分類します。</span><span class="sxs-lookup"><span data-stu-id="0b696-159">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it will classify without applying any settings.</span></span>

[<span data-ttu-id="0b696-160">機密ラベルの発行の詳細について</span><span class="sxs-lookup"><span data-stu-id="0b696-160">Learn more about publishing sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="sensitivity-label-management"></a><span data-ttu-id="0b696-161">機密ラベルの管理</span><span class="sxs-lookup"><span data-stu-id="0b696-161">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="0b696-162">Microsoft Teams、Office 365 グループ、および SharePoint サイトに使用する機密ラベルを作成、変更、および削除するには、ラベル ポリシーをユーザーに発行する際に慎重な調整が必要です。</span><span class="sxs-lookup"><span data-stu-id="0b696-162">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Office 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="0b696-163">以下のガイダンスを使用して、すべてのユーザーに影響を与える可能性のあるサイトおよびグループの作成エラーを回避します。</span><span class="sxs-lookup"><span data-stu-id="0b696-163">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="0b696-164">**ラベルの作成と発行:**</span><span class="sxs-lookup"><span data-stu-id="0b696-164">**Creating and publishing sensitivity labels to classify content.**</span></span>

<span data-ttu-id="0b696-165">機密ラベルを作成して公開した後、チーム、グループ、およびサイトでユーザーがラベルを表示できるようになるまでに最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0b696-165">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="0b696-166">以下の手順を使用して、テナント内のすべてのユーザーにラベルを発行します:</span><span class="sxs-lookup"><span data-stu-id="0b696-166">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="0b696-167">機密ラベルを作成し、テナント内の少数のユーザー アカウントに対してのみ発行します。</span><span class="sxs-lookup"><span data-stu-id="0b696-167">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="0b696-168">24 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="0b696-168">Wait for 24 hours.</span></span>

3. <span data-ttu-id="0b696-169">この 24 時間の待ち時間の後、手順 1 で指定したユーザー アカウントのいずれかを使用して、手順 1 で作成したラベルを持つチーム、Office 365 グループ、または SharePoint サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0b696-169">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Office 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="0b696-170">手順 3 の作成操作中にエラーが発生しなかった場合、テナント内のすべてのユーザーにラベルを発行します。</span><span class="sxs-lookup"><span data-stu-id="0b696-170">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="0b696-171">エラーがある場合には、Microsoft サポートへお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="0b696-171">If there are errors, contact Microsoft Support.</span></span>

<span data-ttu-id="0b696-172">**発行済みラベルの変更および削除:**</span><span class="sxs-lookup"><span data-stu-id="0b696-172">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="0b696-173">1 つ以上のラベル ポリシーに含まれる機密ラベルを変更または削除すると、これらのアクションによりすべてのチーム、グループ、およびサイトの作成が失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0b696-173">If you modify or delete a sensitivity label that is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="0b696-174">この状況を回避するには、以下のガイダンスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="0b696-174">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="0b696-175">ラベルを含むすべてのラベル ポリシーから、機密ラベルを削除します。</span><span class="sxs-lookup"><span data-stu-id="0b696-175">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="0b696-176">48 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="0b696-176">Wait for 48 hours.</span></span>

3. <span data-ttu-id="0b696-177">48 時間待ってからチーム、グループ、またはサイトを作成し、ラベルが表示されなくなったことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0b696-177">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="0b696-178">機密ラベルが表示されていない場合は、ラベルを安全に変更または削除できます。</span><span class="sxs-lookup"><span data-stu-id="0b696-178">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="0b696-179">ラベルがまだ表示されている場合には、Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="0b696-179">If the label is still visible, contact Microsoft Support.</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="0b696-180">機密ラベルの展開のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0b696-180">Troubleshoot sensitivity label deployment</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="0b696-181">発行後にラベルが表示されない</span><span class="sxs-lookup"><span data-stu-id="0b696-181">Labels not visible after publishing</span></span>
<span data-ttu-id="0b696-182">これらの設定を有効にした後、または機密ラベルの説明を変更した後でチームまたは Office 365 グループを作成する際に問題が発生した場合には、ラベルを保存し、数時間待ってからチームまたはグループの作成を再試行してみてください。</span><span class="sxs-lookup"><span data-stu-id="0b696-182">If you experience issues when you create a team or Office 365 group after you enable these settings or modify a sensitivity label's description, save the label, wait a few hours, and then try to create the team or group again.</span></span> <span data-ttu-id="0b696-183">詳細については、「[Schedule roll-out after you create or change a sensitivity label (機密ラベルを作成または変更した後にロールアウトをスケジュールする)](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b696-183">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="0b696-184">それでも SharePoint Online から新しい機密ラベルを表示できない場合には、Microsoft サポートへお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="0b696-184">If you are still not able to see the new sensitivity label from SharePoint Online, contact Microsoft Support.</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="0b696-185">チーム、グループ、または SharePoint サイトの作成エラー</span><span class="sxs-lookup"><span data-stu-id="0b696-185">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="0b696-186">パブリック プレビュー中に作成エラーが発生した場合、2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0b696-186">If you experience creation errors during the public preview, you have two options:</span></span>

- <span data-ttu-id="0b696-187">どのユーザーに対しても機密ラベルが必須ではないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0b696-187">Ensure that sensitivity labels are not mandatory for any user.</span></span>

- <span data-ttu-id="0b696-188">このページの [[このプレビューを有効にする](#enable-this-preview)] セクションと同じ手順を使用することで、Microsoft Teams、Office 365 グループ、および SharePoint サイトの機密ラベルをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="0b696-188">You can turn off sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites by using the same instructions from the [Enable this preview](#enable-this-preview) section on this page.</span></span> <span data-ttu-id="0b696-189">ただし、プレビューを無効にするには、`$setting["EnableMIPLabels"] = "True"`行を検索し、**True** 値を **False** に変更します。</span><span class="sxs-lookup"><span data-stu-id="0b696-189">However, to disable the preview, search for the line `$setting["EnableMIPLabels"] = "True"`, and change the **True** value to **False**.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="0b696-190">新しいチームに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="0b696-190">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="0b696-191">ユーザーは、Microsoft Teams で新しいチームを作成する際に機密ラベルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0b696-191">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="0b696-192">ユーザーが機密レベルを選択すると、必要に応じてプライバシー設定が変更されます。</span><span class="sxs-lookup"><span data-stu-id="0b696-192">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="0b696-193">ラベルに対し選択したゲスト アクセス設定に応じて、ユーザーは組織外のユーザーをチームに追加することができたり、できなかったりします。</span><span class="sxs-lookup"><span data-stu-id="0b696-193">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="0b696-194">Teams の機密ラベルの詳細について</span><span class="sxs-lookup"><span data-stu-id="0b696-194">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![新しいチームを作成する際のプライバシー設定](media/privacy-setting-new-team.png)

<span data-ttu-id="0b696-196">チームを作成すると、すべてのチャネルの右上隅に機密ラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b696-196">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![チームに表示される機密ラベル](media/privacy-setting-teams.png)

<span data-ttu-id="0b696-198">このサービスは、Office 365 グループおよび接続された SharePoint チーム サイトに対して同じ機密ラベルを自動的に適用します。</span><span class="sxs-lookup"><span data-stu-id="0b696-198">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="0b696-199">新しいグループに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="0b696-199">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="0b696-200">Outlook on the web では、新しい [**機密**] ボックスに発行されたラベルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0b696-200">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="0b696-201">ユーザーが詳細を知りたい場合には、[ヘルプ] アイコンをクリックすると使用できるラベルおよび関連ポリシーに関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b696-201">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![グループを作成し、[機密] 下でオプションを選択する](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="0b696-203">新しいサイトに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="0b696-203">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="0b696-204">管理者およびエンド ユーザーは、最新のチーム サイトやコミュニケーション サイトを作成する際に機密ラベルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0b696-204">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

[<span data-ttu-id="0b696-205">新しい SharePoint 管理センターでサイトを作成する方法について</span><span class="sxs-lookup"><span data-stu-id="0b696-205">Learn how to create a site in the new SharePoint admin center</span></span>](/sharepoint/create-site-collection)

<span data-ttu-id="0b696-206">ユーザーが最新のチームおよびコミュニケーション サイトを作成すると、規定で機密ラベルがすでに選択されています。</span><span class="sxs-lookup"><span data-stu-id="0b696-206">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="0b696-207">ユーザーは [ヘルプ] アイコンを選択し、ラベルの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0b696-207">Users can select the help icon to learn more about the labels.</span></span>

![サイトを作成し、[機密] 下でオプションを選択する](media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="0b696-209">ユーザーがサイトを参照すると、ラベルの名前および適用されているポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b696-209">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![機密ラベルが適用されているサイト](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="0b696-211">SharePoint 管理センターで機密ラベルを管理する</span><span class="sxs-lookup"><span data-stu-id="0b696-211">Manage sites in the SharePoint admin center</span></span>

<span data-ttu-id="0b696-212">ラベルを表示および編集するには、新しい SharePoint 管理センターの [アクティブなサイト] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b696-212">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

![[アクティブなサイト] ページの [機密] 列](media/manage-site-sensitivity-labels.png)

<span data-ttu-id="0b696-214">[新しい SharePoint 管理センターでのサイト管理の詳細をご覧ください](/sharepoint/manage-sites-in-new-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="0b696-214">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="0b696-215">ラベル向けのサイトとグループの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="0b696-215">Change site and group settings for a label</span></span>

<span data-ttu-id="0b696-216">ベスト プラクティスとして、複数のチーム、グループ、またはサイトにラベルを適用した後に設定を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="0b696-216">As a best practice, don't change settings after you've applied a label to several teams, groups, or sites.</span></span> <span data-ttu-id="0b696-217">変更が必要な場合には、Azure AD PowerShell スクリプトを使用して更新を手動で適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b696-217">If you must make a change, you need to use an Azure AD PowerShell script to manually apply updates.</span></span> <span data-ttu-id="0b696-218">この方法により、既存のすべてのチーム、サイト、およびグループに新しい設定が適用されることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="0b696-218">This method ensures that all existing teams, sites, and groups enforce the new setting.</span></span>

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="0b696-219">新しい機密ラベルのサポート</span><span class="sxs-lookup"><span data-stu-id="0b696-219">Support for the new sensitivity labels</span></span>

<span data-ttu-id="0b696-220">以下のアプリおよびサービスは、このプレビューの機密ラベルをサポートしています:</span><span class="sxs-lookup"><span data-stu-id="0b696-220">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="0b696-221">Microsoft 365 コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="0b696-221">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="0b696-222">SharePoint</span><span class="sxs-lookup"><span data-stu-id="0b696-222">SharePoint</span></span>
- <span data-ttu-id="0b696-223">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="0b696-223">Outlook on the web</span></span>
- <span data-ttu-id="0b696-224">Teams</span><span class="sxs-lookup"><span data-stu-id="0b696-224">Teams</span></span>
- <span data-ttu-id="0b696-225">SharePoint 管理センター</span><span class="sxs-lookup"><span data-stu-id="0b696-225">SharePoint admin center</span></span>
- <span data-ttu-id="0b696-226">Azure AD 管理センター</span><span class="sxs-lookup"><span data-stu-id="0b696-226">Use Azure portal or Azure AD admin center</span></span>

<span data-ttu-id="0b696-227">以下のアプリおよびサービスを使用して、新しい機密ラベルを用いた Office 365 グループを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="0b696-227">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="0b696-228">Outlook for the Mac</span><span class="sxs-lookup"><span data-stu-id="0b696-228">Outlook for Mac</span></span>
- <span data-ttu-id="0b696-229">Outlook モバイル</span><span class="sxs-lookup"><span data-stu-id="0b696-229">Outlook Mobile</span></span>  
- <span data-ttu-id="0b696-230">Outlook デスクトップ for Windows</span><span class="sxs-lookup"><span data-stu-id="0b696-230">Outlook for Windows</span></span>
- <span data-ttu-id="0b696-231">Forms</span><span class="sxs-lookup"><span data-stu-id="0b696-231">Forms</span></span>  
- <span data-ttu-id="0b696-232">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="0b696-232">Dynamics 365</span></span>  
- <span data-ttu-id="0b696-233">Yammer</span><span class="sxs-lookup"><span data-stu-id="0b696-233">Yammer</span></span>  
- <span data-ttu-id="0b696-234">Stream</span><span class="sxs-lookup"><span data-stu-id="0b696-234">Stream</span></span>  
- <span data-ttu-id="0b696-235">Planner</span><span class="sxs-lookup"><span data-stu-id="0b696-235">Planner</span></span>  
- <span data-ttu-id="0b696-236">Project</span><span class="sxs-lookup"><span data-stu-id="0b696-236">Project</span></span>  
- <span data-ttu-id="0b696-237">PowerBI</span><span class="sxs-lookup"><span data-stu-id="0b696-237">PowerBI</span></span>  
- <span data-ttu-id="0b696-238">Teams 管理センター</span><span class="sxs-lookup"><span data-stu-id="0b696-238">Microsoft Teams admin center</span></span>  
- <span data-ttu-id="0b696-239">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="0b696-239">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="0b696-240">Exchange 管理センター</span><span class="sxs-lookup"><span data-stu-id="0b696-240">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="0b696-241">従来の Azure AD サイト分類を使用した場合</span><span class="sxs-lookup"><span data-stu-id="0b696-241">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="0b696-242">このプレビューを有効にすると、Office 365 は新しいグループおよび SharePoint サイト向けに古い分類をサポートしなくなります。</span><span class="sxs-lookup"><span data-stu-id="0b696-242">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="0b696-243">ただし、既存のグループおよびサイトには変換しない限り古い分類が引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b696-243">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="0b696-244">古い分類には、おそらく Azure AD PowerShell または PnP コア ライブラリを介して設定した、`ClassificationList`設定用の値を定義した "モダンな" サイト分類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0b696-244">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="0b696-245">たとえば、PowerShell の場合には以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="0b696-245">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="0b696-246">古い分類方法の詳細については、「[SharePoint の "モダン" サイトの分類](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b696-246">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="0b696-247">現在の展開に基づき、古い分類を新しい分類に変換するための 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0b696-247">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="0b696-248">ファイルおよびメールに機密ラベル (統合 Microsoft Information Protection ラベル) を使用したことがない場合</span><span class="sxs-lookup"><span data-stu-id="0b696-248">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="0b696-249">以下のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0b696-249">We recommend that you:</span></span>

1. <span data-ttu-id="0b696-250">Microsoft 365 コンプライアンス センターで、既存の分類と同じ名前の新しい機密ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="0b696-250">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="0b696-251">PowerShell を使用して、既存の Office 365 グループおよび名前のマッピングを使用する SharePoint サイトに新しいラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="0b696-251">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="0b696-252">古い分類を削除します。</span><span class="sxs-lookup"><span data-stu-id="0b696-252">Delete the old classifications.</span></span>

<span data-ttu-id="0b696-253">新しい機密ラベルをサポートするアプリおよびサービスは、それらを表示します。</span><span class="sxs-lookup"><span data-stu-id="0b696-253">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="0b696-254">新しいラベルを使用して新しいチーム、グループ、およびサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0b696-254">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="0b696-255">ユーザーは引き続き、新しいラベルをサポートしていないアプリおよびサービスからグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0b696-255">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="0b696-256">ただし、ユーザーはこれらのグループにラベルを適用できません。</span><span class="sxs-lookup"><span data-stu-id="0b696-256">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="0b696-257">PowerShell を使用して、これらのグループに新しい機密ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="0b696-257">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="0b696-258">古い分類は保持可能です。ただし、PowerShell を使用してこれらのグループに新しい機密ラベルを適用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0b696-258">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="0b696-259">新しい機密ラベルをサポートするアプリおよびサービスは、新しいラベルで作成されます。</span><span class="sxs-lookup"><span data-stu-id="0b696-259">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="0b696-260">ユーザーが新しいラベルをサポートしないアプリおよびサービスからグループを作成する場合、ユーザーは分類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0b696-260">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="0b696-261">ファイルおよびメールに機密ラベル (統合 Microsoft Information Protection ラベル) を使用する場合</span><span class="sxs-lookup"><span data-stu-id="0b696-261">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="0b696-262">このプレビューを有効にしたら Microsoft 365 コンプライアンス センター内の各ラベルに移動し、サイトおよびグループに必要なポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="0b696-262">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="0b696-263">ユーザーは、サイトおよびグループで利用可能な既存のラベルの表示を開始します。</span><span class="sxs-lookup"><span data-stu-id="0b696-263">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="0b696-264">Office 365 グループのラベルを付け直す前に、SharePoint Online 管理シェルを準備する</span><span class="sxs-lookup"><span data-stu-id="0b696-264">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="0b696-265">新しいラベルを適用する前に、最新の SharePoint Online 管理シェルを実行していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0b696-265">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="0b696-266">既に最新バージョンをお持ちの場合には、先に進み [Office 365 グループに新しい機密ラベルを付け直してください](#relabel-office-365-groups-with-new-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="0b696-266">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="0b696-267">プレビューのために SharePoint Online 管理シェルを準備するには:</span><span class="sxs-lookup"><span data-stu-id="0b696-267">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="0b696-268">SharePoint Online 管理シェルの以前のバージョンがインストールされている場合には、[**プログラムの追加と削除**] に移動して “SharePoint Online 管理シェル“ をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="0b696-268">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall “SharePoint Online Management Shell.”</span></span>

2. <span data-ttu-id="0b696-269">Web ブラウザーで [ダウンロード センター] ページへと移動し、[最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="0b696-269">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="0b696-270">言語を選択し、[**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b696-270">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="0b696-271">x64 および x86 の .msi ファイルのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="0b696-271">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="0b696-272">Windows の 64 ビット版を実行している場合には x64 ファイルを、32 ビット版を実行している場合には x86 ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="0b696-272">Download the x64 file if you’re running the 64-bit version of Windows or the x86 file if you’re running the 32-bit version.</span></span> <span data-ttu-id="0b696-273">不明な場合には、「[実行している Windows オペレーティング システムの確認方法](https://support.microsoft.com/help/13443/windows-which-operating-system)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b696-273">If you don’t know, see [Which version of Windows am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="0b696-274">ファイルをダウンロードしたら、そのファイルを実行し、セットアップ ウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0b696-274">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="0b696-275">新しい機密ラベルで Office 365 グループにラベルを付け直します</span><span class="sxs-lookup"><span data-stu-id="0b696-275">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="0b696-276">SharePoint Online 管理シェルの最新バージョンを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0b696-276">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="0b696-277">手順については、「[Office 365 グループのラベルを付け直す前に、SharePoint Online 管理シェルを準備する](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b696-277">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="0b696-278">Office 365 のグローバル管理者または SharePoint 管理者権限を持つ職場または学校のアカウントを使用して、SharePoint Online 管理シェルへと接続します。</span><span class="sxs-lookup"><span data-stu-id="0b696-278">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="0b696-279">方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b696-279">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="0b696-280">以下のコマンドを実行し、機密ラベルおよびその GUID のリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="0b696-280">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="0b696-281">上書きするラベルの GUID をメモします。</span><span class="sxs-lookup"><span data-stu-id="0b696-281">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="0b696-282">たとえば、"一般" ラベル。</span><span class="sxs-lookup"><span data-stu-id="0b696-282">For example, the "General" label.</span></span>

5. <span data-ttu-id="0b696-283">以下のコマンドを使用して、"一般" 分類を持つグループのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="0b696-283">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="0b696-284">このコマンドを実行すると Exchange Online PowerShell へと接続し、Get-UnifiedGroup コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b696-284">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="0b696-285">グループごとに、新しい機密ラベル GUID を追加します。</span><span class="sxs-lookup"><span data-stu-id="0b696-285">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
