---
title: PowerShell Microsoft 365グループを管理する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: この記事では、PowerShell のグループに対して一般的な管理Microsoft 365する方法について説明します。
ms.openlocfilehash: adf796ad2f2ee7a304c578cd42c700f2b44e7a5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911052"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="b6d86-103">PowerShell Microsoft 365グループを管理する</span><span class="sxs-lookup"><span data-stu-id="b6d86-103">Manage Microsoft 365 Groups with PowerShell</span></span>

<span data-ttu-id="b6d86-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="b6d86-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b6d86-105">この記事では、Microsoft PowerShell でグループの一般的な管理タスクを行うための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="b6d86-106">また、グループの PowerShell コマンドレットを示します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="b6d86-107">SharePoint サイトを管理する方法の詳細については、「[PowerShell を使用して SharePoint Online サイトを管理する](/sharepoint/manage-team-and-communication-sites-in-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6d86-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="b6d86-108">グループの使用Microsoft 365へのリンク</span><span class="sxs-lookup"><span data-stu-id="b6d86-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="b6d86-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="b6d86-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="b6d86-110">ユーザーが [Outlook でグループを作成または編集](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)するときに、組織での使用に関するガイドラインへのリンクをそのユーザーに表示することができます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="b6d86-111">たとえば、グループ名に特定のプレフィックスまたはサフィックスを追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6d86-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>

<span data-ttu-id="b6d86-112">ユーザーをAzure Active Directory (Azure AD) PowerShell を使用して、ユーザーが組織のグループの使用ガイドラインをMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="b6d86-113">「[グループの設定を構成するための Azure Active Directory コマンドレット](/azure/active-directory/enterprise-users/groups-settings-cmdlets)」の「**ディレクトリ レベルでの設定の作成**」の手順に従って、使用ガイドラインのハイパーリンクを定義します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-113">Check out [Azure Active Directory cmdlets for configuring group settings](/azure/active-directory/enterprise-users/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="b6d86-114">AAD コマンドレットを実行すると、ユーザーが Outlook でグループを作成または編集するときに、ガイドラインへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-114">Once you run the AAD cmdlet, user's will see the link to your guidelines when they create or edit a group in Outlook.</span></span>

![使用ガイドラインのリンクがある新しいグループを作成する](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![グループ使用ガイドラインをクリックして、組織の Office 365 グループのガイドラインを参照する](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="b6d86-117">ユーザーがグループとして送信Microsoft 365する</span><span class="sxs-lookup"><span data-stu-id="b6d86-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="b6d86-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="b6d86-118"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="b6d86-119">グループを "送信者" にMicrosoft 365する場合は[、Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission)コマンドレットと[Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission)コマンドレットを使用してこれを構成します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) and [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) cmdlets to configure this.</span></span> <span data-ttu-id="b6d86-120">この設定を有効にすると、Microsoft 365 グループ ユーザーは web 上の Outlook または Outlook を使用して、電子メールを送信し、電子メールに返信Microsoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="b6d86-121">ユーザーはグループに移動し、新しいメールを作成して、「メールボックス所有者として送信する」フィールドをグループのメール アドレスに変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span>

<span data-ttu-id="b6d86-122">([Exchange 管理センターでもこれを行うことができます](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)。)</span><span class="sxs-lookup"><span data-stu-id="b6d86-122">([You can also do this in the Exchange Admin Center](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>

<span data-ttu-id="b6d86-123">次のスクリプトを使用して、更新するグループのエイリアスと、アクセス許可を付与するユーザーのエイリアスに *\<GroupAlias\>* *\<UserAlias\>* 置き換える。</span><span class="sxs-lookup"><span data-stu-id="b6d86-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="b6d86-124">[Exchange Online PowerShell に接続し](/powershell/exchange/connect-to-exchange-online-powershell)、このスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-124">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="b6d86-125">コマンドレットが実行されると、**From** フィールドにグループ メール アドレスを追加することにより、ユーザーが Outlook または Outlook on the web に移動して、グループとして送信することができます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span>

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a><span data-ttu-id="b6d86-126">組織内のグループMicrosoft 365分類を作成する</span><span class="sxs-lookup"><span data-stu-id="b6d86-126">Create classifications for Microsoft 365 Groups in your organization</span></span>

<span data-ttu-id="b6d86-127">組織内のユーザーがグループを作成するときに設定できる感度ラベルをMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="b6d86-128">グループを分類する場合は、以前のグループ分類機能ではなく、感度ラベルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b6d86-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="b6d86-129">感度ラベルの使用の詳細については、「感度ラベルを使用して、Microsoft Teams、Microsoft 365、およびサイトのコンテンツを保護する」[をSharePointしてください](../compliance/sensitivity-labels-teams-groups-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="b6d86-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6d86-130">現在分類ラベルを使用している場合、感度ラベルが有効になると、グループを作成するユーザーは使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b6d86-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="b6d86-131">以前のグループ分類機能は引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="b6d86-132">組織のユーザーがグループを作成するときに設定できる分類をMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-132">You can create classifications that the users in your organization can set when they create an Microsoft 365 Group.</span></span> <span data-ttu-id="b6d86-133">たとえば、作成するグループにユーザーが「標準」、「機密」、「極秘」といった分類を設定できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="b6d86-134">グループの分類は既定では設定されていないので、ユーザーに分類を設定させるには、分類を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6d86-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="b6d86-135">PowerShell Azure Active Directoryを使用して、ユーザーに組織のグループの使用ガイドラインをMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Microsoft 365 Groups.</span></span>

<span data-ttu-id="b6d86-136">グループ設定[Azure Active Directoryする](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)コマンドレットを確認し、「ディレクトリ レベルで設定を作成する」の手順に従って、グループグループのMicrosoft 365してください。</span><span class="sxs-lookup"><span data-stu-id="b6d86-136">Check out [Azure Active Directory cmdlets for configuring group settings](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Microsoft 365 Groups.</span></span>

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="b6d86-137">各分類に説明を関連付けるために、定義する設定属性 *ClassificationDescriptions* を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="b6d86-138">ここで、Classification は ClassificationList の文字列と一致します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="b6d86-139">例:</span><span class="sxs-lookup"><span data-stu-id="b6d86-139">Example:</span></span>

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="b6d86-140">上の Azure Active Directory コマンドレットを実行して分類を設定した後、特定のグループに分類を設定する場合は、[Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span>

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

<span data-ttu-id="b6d86-141">または、分類を使用して新しいグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-141">Or create a new group with a classification.</span></span>

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

<span data-ttu-id="b6d86-142">Exchange Online PowerShell の使用の詳細については、「[Exchange Online による PowerShell の使用](/powershell/exchange/exchange-online-powershell)」および「[Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6d86-142">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span>

<span data-ttu-id="b6d86-143">これらの設定を有効にした後、グループの所有者は、Outlook on the web および Outlook​​ のドロップダウン メニューから分類を選択し、[**編集**] グループ ページから分類を保存できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b6d86-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span>

![[グループMicrosoft 365選択]](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a><span data-ttu-id="b6d86-145">グローバル アドレスMicrosoft 365グループを非表示にする。</span><span class="sxs-lookup"><span data-stu-id="b6d86-145">Hide Microsoft 365 Groups from the global address list.</span></span>
<span data-ttu-id="b6d86-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="b6d86-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="b6d86-147">組織のグローバル アドレス一Microsoft 365 (GAL) および他のリストにグループを表示するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-147">You can specify whether a Microsoft 365 Group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="b6d86-148">たとえば、住所一覧に表示しない法務部門グループがある場合は、そのグループが GAL に表示されるのを停止できます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in the GAL.</span></span> <span data-ttu-id="b6d86-149">次のようにSet-Unifiedグループコマンドレットを実行して、グループをアドレス一覧から非表示にします。</span><span class="sxs-lookup"><span data-stu-id="b6d86-149">Run the Set-Unified Group cmdlet to hide the group from the address list like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a><span data-ttu-id="b6d86-150">内部ユーザーだけがグループにメッセージを送信Microsoft 365する</span><span class="sxs-lookup"><span data-stu-id="b6d86-150">Allow only internal users to send message to Microsoft 365 Groups</span></span>
<span data-ttu-id="b6d86-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="b6d86-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="b6d86-152">他の組織のユーザーがグループにメールを送信Microsoft 365場合は、そのグループの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-152">If you don't want users from other organizations to send emails to a Microsoft 365 Group, you can change the settings for that group.</span></span> <span data-ttu-id="b6d86-153">これにより、内部のユーザーのみがグループにメールを送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b6d86-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="b6d86-154">外部ユーザーがメッセージをそのグループに送信しようとすると、そのメッセージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-154">If an external user tries to send a message to that group, it will be rejected.</span></span>

<span data-ttu-id="b6d86-155">この設定を更新するには、次のように Set-UnifiedGroup コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a><span data-ttu-id="b6d86-156">メール ヒントをグループにMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="b6d86-156">Add MailTips to Microsoft 365 Groups</span></span>
<span data-ttu-id="b6d86-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="b6d86-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="b6d86-158">送信者がグループに電子メールを送信Microsoft 365、メール ヒントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-158">Whenever a sender tries to send an email to a Microsoft 365 Group, a MailTip can be shown to them.</span></span>

<span data-ttu-id="b6d86-159">グループにメール ヒントを追加するには、Set-UnifiedGroup コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="b6d86-160">メール ヒントと共に、MailTipTranslations を設定することもできます。これは、メール ヒントの追加言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="b6d86-161">スペイン語の翻訳を追加するとします。この場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a><span data-ttu-id="b6d86-162">グループの表示名をMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="b6d86-162">Change the display name of the Microsoft 365 Group</span></span>

<span data-ttu-id="b6d86-163">表示名は、グループの名前Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-163">The display name specifies the name of the Microsoft 365 Group.</span></span> <span data-ttu-id="b6d86-164">この名前は、Exchange 管理センターまたは管理センター Microsoft 365確認できます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="b6d86-165">次のコマンドを実行して、グループの表示名を編集したり、既存のグループに表示Microsoft 365割り当Set-UnifiedGroupできます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-165">You can edit the display name of the group or assign a display name to an existing Microsoft 365 Group by running the Set-UnifiedGroup command:</span></span>

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="b6d86-166">グループのグループの既定Microsoft 365を [パブリックOutlookプライベート] に変更する</span><span class="sxs-lookup"><span data-stu-id="b6d86-166">Change the default setting of Microsoft 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="b6d86-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="b6d86-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="b6d86-168">Microsoft 365既定では、Outlookグループは Private として作成されます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-168">Microsoft 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="b6d86-169">組織で既定で Microsoft 365として作成する (またはプライベートに戻す) 場合は、次の PowerShell コマンドレット構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-169">If your organization wants Microsoft 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

<span data-ttu-id="b6d86-170">非公開に設定するには:</span><span class="sxs-lookup"><span data-stu-id="b6d86-170">To set to Private:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

<span data-ttu-id="b6d86-171">設定を確認するには:</span><span class="sxs-lookup"><span data-stu-id="b6d86-171">To verify the setting:</span></span>

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

<span data-ttu-id="b6d86-172">詳細については、「[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)」および「[Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6d86-172">To learn more, see [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig).</span></span>

## <a name="microsoft-365-groups-cmdlets"></a><span data-ttu-id="b6d86-173">Microsoft 365グループコマンドレット</span><span class="sxs-lookup"><span data-stu-id="b6d86-173">Microsoft 365 Groups cmdlets</span></span>

<span data-ttu-id="b6d86-174">次のコマンドレットは、グループとMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-174">The following cmdlets can be used with Microsoft 365 Groups.</span></span>

|<span data-ttu-id="b6d86-175">**コマンドレット名**</span><span class="sxs-lookup"><span data-stu-id="b6d86-175">**Cmdlet name**</span></span>|<span data-ttu-id="b6d86-176">**Description**</span><span class="sxs-lookup"><span data-stu-id="b6d86-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b6d86-177">Get-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="b6d86-177">Get-UnifiedGroup</span></span>](/powershell/module/exchange/get-unifiedgroup) <br/> |<span data-ttu-id="b6d86-178">このコマンドレットを使用して、グループの既存Microsoft 365を参照し、グループ オブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-178">Use this cmdlet to look up existing Microsoft 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="b6d86-179">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="b6d86-179">Set-UnifiedGroup</span></span>](/powershell/module/exchange/set-unifiedgroup) <br/> |<span data-ttu-id="b6d86-180">特定のグループのプロパティをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="b6d86-180">Update the properties of a specific Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="b6d86-181">New-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="b6d86-181">New-UnifiedGroup</span></span>](/powershell/module/exchange/new-unifiedgroup) <br/> |<span data-ttu-id="b6d86-182">グループに新しいMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-182">Create a new Microsoft 365 Group.</span></span> <span data-ttu-id="b6d86-183">このコマンドレットは、最小限のパラメーター セットを提供します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-183">This cmdlet provides a minimal set of parameters.</span></span> <span data-ttu-id="b6d86-184">拡張プロパティの値を設定するには、新しいSet-UnifiedGroup後にプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-184">To set values for extended properties, use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="b6d86-185">Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="b6d86-185">Remove-UnifiedGroup</span></span>](/powershell/module/exchange/remove-unifiedgroup) <br/> |<span data-ttu-id="b6d86-186">既存のグループをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="b6d86-186">Delete an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="b6d86-187">Get-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="b6d86-187">Get-UnifiedGroupLinks</span></span>](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |<span data-ttu-id="b6d86-188">グループのメンバーシップと所有者情報をMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="b6d86-188">Retrieve membership and owner information for a Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="b6d86-189">Add-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="b6d86-189">Add-UnifiedGroupLinks</span></span>](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |<span data-ttu-id="b6d86-190">メンバー、所有者、およびサブスクライバーを既存のグループにMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="b6d86-190">Add members, owners, and subscribers to an existing Microsoft 365 Group</span></span> <br/> |
|[<span data-ttu-id="b6d86-191">Remove-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="b6d86-191">Remove-UnifiedGroupLinks</span></span>](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |<span data-ttu-id="b6d86-192">既存のグループから所有者とメンバーをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="b6d86-192">Remove owners and members from an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="b6d86-193">Get-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="b6d86-193">Get-UserPhoto</span></span>](/powershell/module/exchange/get-userphoto) <br/> |<span data-ttu-id="b6d86-194">アカウントと関連付けられたユーザーの写真について情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-194">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="b6d86-195">パスワードは Active Directory に格納されます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-195">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="b6d86-196">Set-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="b6d86-196">Set-UserPhoto</span></span>](/powershell/module/exchange/set-userphoto) <br/> |<span data-ttu-id="b6d86-197">ユーザーの写真をアカウントに関連付けるために使用します。</span><span class="sxs-lookup"><span data-stu-id="b6d86-197">Used to associate a user photo with an account.</span></span> <span data-ttu-id="b6d86-198">パスワードは Active Directory に格納されます。</span><span class="sxs-lookup"><span data-stu-id="b6d86-198">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="b6d86-199">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="b6d86-199">Remove-UserPhoto</span></span>](/powershell/module/exchange/remove-userphoto) <br/> |<span data-ttu-id="b6d86-200">グループの写真をMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="b6d86-200">Remove the photo for an Microsoft 365 Group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="b6d86-201">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6d86-201">Related topics</span></span>

[<span data-ttu-id="b6d86-202">配布リストをグループにMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="b6d86-202">Upgrade distribution lists to Microsoft 365 Groups</span></span>](/office365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="b6d86-203">Microsoft 365 グループを作成できるユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="b6d86-203">Manage who can create Microsoft 365 Groups</span></span>](/office365/admin/create-groups/manage-creation-of-groups)

[<span data-ttu-id="b6d86-204">グループへのゲスト アクセスMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="b6d86-204">Manage guest access to Microsoft 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="b6d86-205">静的なグループメンバーシップを動的に変更する</span><span class="sxs-lookup"><span data-stu-id="b6d86-205">Change static group membership to dynamic in</span></span>](/azure/active-directory/users-groups-roles/groups-change-type)