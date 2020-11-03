---
title: PowerShell を使用して Microsoft 365 グループを管理する
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
description: この記事では、PowerShell での Microsoft 365 グループの一般的な管理タスクの実行方法について説明します。
ms.openlocfilehash: 1cad2aa39a6b106cbb4dbfbafa995899b2442ed1
ms.sourcegitcommit: 9d1351ea6d9942550b52132817f9f9693ddef2fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2020
ms.locfileid: "48830617"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="aa7e3-103">PowerShell を使用して Microsoft 365 グループを管理する</span><span class="sxs-lookup"><span data-stu-id="aa7e3-103">Manage Microsoft 365 Groups with PowerShell</span></span>

<span data-ttu-id="aa7e3-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="aa7e3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="aa7e3-105">この記事では、Microsoft PowerShell でグループの一般的な管理タスクを行うための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="aa7e3-106">また、グループの PowerShell コマンドレットを示します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="aa7e3-107">SharePoint サイトを管理する方法の詳細については、「[PowerShell を使用して SharePoint Online サイトを管理する](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="aa7e3-108">Microsoft 365 グループの使用ガイドラインへのリンク</span><span class="sxs-lookup"><span data-stu-id="aa7e3-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="aa7e3-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="aa7e3-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="aa7e3-110">ユーザーが [Outlook でグループを作成または編集](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)するときに、組織での使用に関するガイドラインへのリンクをそのユーザーに表示することができます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="aa7e3-111">たとえば、グループ名に特定のプレフィックスまたはサフィックスを追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>

<span data-ttu-id="aa7e3-112">Azure Active Directory (Azure AD) PowerShell を使用して、Microsoft 365 グループの組織の使用ガイドラインをユーザーに示します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="aa7e3-113">「 [グループの設定を構成するための Azure Active Directory コマンドレット](https://go.microsoft.com/fwlink/?LinkID=827484)」の「 **ディレクトリ レベルでの設定の作成** 」の手順に従って、使用ガイドラインのハイパーリンクを定義します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-113">Check out [Azure Active Directory cmdlets for configuring group settings](https://go.microsoft.com/fwlink/?LinkID=827484) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="aa7e3-114">AAD コマンドレットを実行すると、ユーザーが Outlook でグループを作成または編集するときに、ガイドラインへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-114">Once you run the AAD cmdlet, user's will see the link to your guidelines when they create or edit a group in Outlook.</span></span>

![使用ガイドラインのリンクがある新しいグループを作成する](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![グループ使用ガイドラインをクリックして、組織の Office 365 グループのガイドラインを参照する](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="aa7e3-117">ユーザーが Microsoft 365 グループとして送信できるようにする</span><span class="sxs-lookup"><span data-stu-id="aa7e3-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="aa7e3-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="aa7e3-118"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="aa7e3-119">Microsoft 365 グループを "送信元" にできるようにする場合は、この機能を構成するために、 [アドインのアクセス許可](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) と [受信者アクセス許可](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) and [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) cmdlets to configure this.</span></span> <span data-ttu-id="aa7e3-120">この設定を有効にすると、Microsoft 365 グループのユーザーは、Outlook または web 上の Outlook を使用して、Microsoft 365 グループとして電子メールを送信および返信できます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="aa7e3-121">ユーザーはグループに移動し、新しいメールを作成して、「メールボックス所有者として送信する」フィールドをグループのメール アドレスに変更することができます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span>

<span data-ttu-id="aa7e3-122">([Exchange 管理センターでもこれを行うことができます](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)。)</span><span class="sxs-lookup"><span data-stu-id="aa7e3-122">([You can also do this in the Exchange Admin Center](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>

<span data-ttu-id="aa7e3-123">次のスクリプトを使用して、 *\<GroupAlias\>* 更新するグループのエイリアスと、 *\<UserAlias\>* アクセス許可を付与するユーザーのエイリアスを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="aa7e3-124">[Exchange Online PowerShell に接続し](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)、このスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-124">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="aa7e3-125">コマンドレットが実行されると、 **From** フィールドにグループ メール アドレスを追加することにより、ユーザーが Outlook または Outlook on the web に移動して、グループとして送信することができます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span>

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a><span data-ttu-id="aa7e3-126">組織内の Microsoft 365 グループの分類を作成する</span><span class="sxs-lookup"><span data-stu-id="aa7e3-126">Create classifications for Microsoft 365 Groups in your organization</span></span>

<span data-ttu-id="aa7e3-127">組織内のユーザーが Microsoft 365 グループを作成するときに設定できる機密ラベルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="aa7e3-128">グループを分類する場合は、前のグループ分類機能ではなく、機密ラベルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="aa7e3-129">機密ラベルの使用方法については、「 [Microsoft Teams、microsoft 365 グループ、および SharePoint サイトのコンテンツを保護するための機密情報を使用する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa7e3-130">現在、分類ラベルを使用している場合、グループを作成するユーザーは、機密ラベルが有効になっていても使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="aa7e3-131">以前のグループ分類機能を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="aa7e3-132">組織内のユーザーが Microsoft 365 グループを作成するときに設定できる分類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-132">You can create classifications that the users in your organization can set when they create an Microsoft 365 Group.</span></span> <span data-ttu-id="aa7e3-133">たとえば、作成するグループにユーザーが「標準」、「機密」、「極秘」といった分類を設定できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="aa7e3-134">グループの分類は既定では設定されていないので、ユーザーに分類を設定させるには、分類を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="aa7e3-135">Azure Active Directory PowerShell を使用して、Microsoft 365 グループの組織の使用ガイドラインをユーザーに示します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Microsoft 365 Groups.</span></span>

<span data-ttu-id="aa7e3-136">[グループ設定を構成するための Azure Active Directory コマンドレット](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)をチェックアウトし、「 **ディレクトリレベルで設定を作成** する」の手順に従って、Microsoft 365 グループの分類を定義します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-136">Check out [Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Microsoft 365 Groups.</span></span>

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="aa7e3-137">各分類に説明を関連付けるために、定義する設定属性 *ClassificationDescriptions* を使用できます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="aa7e3-138">ここで、Classification は ClassificationList の文字列と一致します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="aa7e3-139">例:</span><span class="sxs-lookup"><span data-stu-id="aa7e3-139">Example:</span></span>

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="aa7e3-140">上の Azure Active Directory コマンドレットを実行して分類を設定した後、特定のグループに分類を設定する場合は、[Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span>

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

<span data-ttu-id="aa7e3-141">または、分類を使用して新しいグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-141">Or create a new group with a classification.</span></span>

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

<span data-ttu-id="aa7e3-142">Exchange Online PowerShell の使用の詳細については、「[Exchange Online による PowerShell の使用](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)」および「[Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-142">Check out [Using PowerShell with Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span>

<span data-ttu-id="aa7e3-143">これらの設定を有効にした後、グループの所有者は、Outlook on the web および Outlook​​ のドロップダウン メニューから分類を選択し、[ **編集** ] グループ ページから分類を保存できるようになります。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span>

![Microsoft 365 グループの分類を選択する](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a><span data-ttu-id="aa7e3-145">Microsoft 365 グループをグローバルアドレス一覧から非表示にします。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-145">Hide Microsoft 365 Groups from the global address list.</span></span>
<span data-ttu-id="aa7e3-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="aa7e3-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="aa7e3-147">Microsoft 365 グループを、組織内のグローバルアドレス一覧 (GAL) およびその他のリストに表示するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-147">You can specify whether a Microsoft 365 Group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="aa7e3-148">たとえば、アドレス一覧に表示したくない法務部門のグループがある場合は、そのグループが GAL に表示されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in the GAL.</span></span> <span data-ttu-id="aa7e3-149">Set-Unified Group コマンドレットを実行して、次のようにアドレス一覧からグループを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-149">Run the Set-Unified Group cmdlet to hide the group from the address list like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a><span data-ttu-id="aa7e3-150">内部ユーザーのみに Microsoft 365 グループへのメッセージの送信を許可する</span><span class="sxs-lookup"><span data-stu-id="aa7e3-150">Allow only internal users to send message to Microsoft 365 Groups</span></span>
<span data-ttu-id="aa7e3-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="aa7e3-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="aa7e3-152">他の組織のユーザーが Microsoft 365 グループに電子メールを送信できないようにするには、そのグループの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-152">If you don't want users from other organizations to send emails to a Microsoft 365 Group, you can change the settings for that group.</span></span> <span data-ttu-id="aa7e3-153">これにより、内部のユーザーのみがグループにメールを送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="aa7e3-154">外部ユーザーがそのグループにメッセージを送信しようとすると、そのグループは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-154">If an external user tries to send a message to that group, it will be rejected.</span></span>

<span data-ttu-id="aa7e3-155">この設定を更新するには、次のように Set-UnifiedGroup コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a><span data-ttu-id="aa7e3-156">Microsoft 365 グループへのメールヒントの追加</span><span class="sxs-lookup"><span data-stu-id="aa7e3-156">Add MailTips to Microsoft 365 Groups</span></span>
<span data-ttu-id="aa7e3-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="aa7e3-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="aa7e3-158">送信者が Microsoft 365 グループに電子メールを送信しようとするたびに、メールヒントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-158">Whenever a sender tries to send an email to a Microsoft 365 Group, a MailTip can be shown to them.</span></span>

<span data-ttu-id="aa7e3-159">グループにメール ヒントを追加するには、Set-UnifiedGroup コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="aa7e3-160">メール ヒントと共に、MailTipTranslations を設定することもできます。これは、メール ヒントの追加言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="aa7e3-161">スペイン語の翻訳を追加するとします。この場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a><span data-ttu-id="aa7e3-162">Microsoft 365 グループの表示名を変更する</span><span class="sxs-lookup"><span data-stu-id="aa7e3-162">Change the display name of the Microsoft 365 Group</span></span>

<span data-ttu-id="aa7e3-163">[表示名] には、Microsoft 365 グループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-163">The display name specifies the name of the Microsoft 365 Group.</span></span> <span data-ttu-id="aa7e3-164">この名前は、exchange 管理センターまたは Microsoft 365 管理センターで確認できます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="aa7e3-165">Set-UnifiedGroup コマンドを実行すると、グループの表示名を編集したり、既存の Microsoft 365 グループに表示名を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-165">You can edit the display name of the group or assign a display name to an existing Microsoft 365 Group by running the Set-UnifiedGroup command:</span></span>

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="aa7e3-166">Outlook の Microsoft 365 グループの既定の設定をパブリックまたはプライベートに変更する</span><span class="sxs-lookup"><span data-stu-id="aa7e3-166">Change the default setting of Microsoft 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="aa7e3-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="aa7e3-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="aa7e3-168">既定では、Outlook の Microsoft 365 グループはプライベートとして作成されます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-168">Microsoft 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="aa7e3-169">組織で Microsoft 365 グループを既定でパブリックとして作成する (またはプライベートに戻す) 場合は、次の PowerShell コマンドレット構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-169">If your organization wants Microsoft 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

<span data-ttu-id="aa7e3-170">非公開に設定するには:</span><span class="sxs-lookup"><span data-stu-id="aa7e3-170">To set to Private:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

<span data-ttu-id="aa7e3-171">設定を確認するには:</span><span class="sxs-lookup"><span data-stu-id="aa7e3-171">To verify the setting:</span></span>

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

<span data-ttu-id="aa7e3-172">詳細については、「[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)」および「[Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-172">To learn more, see [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).</span></span>

## <a name="microsoft-365-groups-cmdlets"></a><span data-ttu-id="aa7e3-173">Microsoft 365 グループのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="aa7e3-173">Microsoft 365 Groups cmdlets</span></span>

<span data-ttu-id="aa7e3-174">次のコマンドレットは、Microsoft 365 グループで使用できます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-174">The following cmdlets can be used with Microsoft 365 Groups.</span></span>

|<span data-ttu-id="aa7e3-175">**コマンドレット名**</span><span class="sxs-lookup"><span data-stu-id="aa7e3-175">**Cmdlet name**</span></span>|<span data-ttu-id="aa7e3-176">**Description**</span><span class="sxs-lookup"><span data-stu-id="aa7e3-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="aa7e3-177">Get-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="aa7e3-177">Get-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |<span data-ttu-id="aa7e3-178">このコマンドレットを使用して、既存の Microsoft 365 グループを検索し、グループオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-178">Use this cmdlet to look up existing Microsoft 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="aa7e3-179">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="aa7e3-179">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |<span data-ttu-id="aa7e3-180">特定の Microsoft 365 グループのプロパティを更新する</span><span class="sxs-lookup"><span data-stu-id="aa7e3-180">Update the properties of a specific Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="aa7e3-181">New-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="aa7e3-181">New-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |<span data-ttu-id="aa7e3-182">新しい Microsoft 365 グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-182">Create a new Microsoft 365 Group.</span></span> <span data-ttu-id="aa7e3-183">このコマンドレットは、最小限のパラメーターセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-183">This cmdlet provides a minimal set of parameters.</span></span> <span data-ttu-id="aa7e3-184">拡張プロパティの値を設定するには、新しいグループを作成した後に Set-UnifiedGroup を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-184">To set values for extended properties, use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="aa7e3-185">Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="aa7e3-185">Remove-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |<span data-ttu-id="aa7e3-186">既存の Microsoft 365 グループを削除する</span><span class="sxs-lookup"><span data-stu-id="aa7e3-186">Delete an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="aa7e3-187">Get-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="aa7e3-187">Get-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |<span data-ttu-id="aa7e3-188">Microsoft 365 グループのメンバーシップと所有者の情報を取得する</span><span class="sxs-lookup"><span data-stu-id="aa7e3-188">Retrieve membership and owner information for a Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="aa7e3-189">Add-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="aa7e3-189">Add-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |<span data-ttu-id="aa7e3-190">既存の Microsoft 365 グループにメンバー、所有者、およびサブスクライバーを追加する</span><span class="sxs-lookup"><span data-stu-id="aa7e3-190">Add members, owners, and subscribers to an existing Microsoft 365 Group</span></span> <br/> |
|[<span data-ttu-id="aa7e3-191">Remove-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="aa7e3-191">Remove-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |<span data-ttu-id="aa7e3-192">既存の Microsoft 365 グループから所有者とメンバーを削除する</span><span class="sxs-lookup"><span data-stu-id="aa7e3-192">Remove owners and members from an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="aa7e3-193">Get-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="aa7e3-193">Get-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |<span data-ttu-id="aa7e3-194">アカウントと関連付けられたユーザーの写真について情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-194">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="aa7e3-195">パスワードは Active Directory に格納されます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-195">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="aa7e3-196">Set-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="aa7e3-196">Set-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |<span data-ttu-id="aa7e3-197">ユーザーの写真をアカウントに関連付けるために使用します。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-197">Used to associate a user photo with an account.</span></span> <span data-ttu-id="aa7e3-198">パスワードは Active Directory に格納されます。</span><span class="sxs-lookup"><span data-stu-id="aa7e3-198">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="aa7e3-199">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="aa7e3-199">Remove-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |<span data-ttu-id="aa7e3-200">Microsoft 365 グループの写真を削除する</span><span class="sxs-lookup"><span data-stu-id="aa7e3-200">Remove the photo for an Microsoft 365 Group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="aa7e3-201">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa7e3-201">Related topics</span></span>

[<span data-ttu-id="aa7e3-202">配布リストを Microsoft 365 グループにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="aa7e3-202">Upgrade distribution lists to Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="aa7e3-203">Microsoft 365 グループを作成できるユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="aa7e3-203">Manage who can create Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[<span data-ttu-id="aa7e3-204">Microsoft 365 グループへのゲストアクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="aa7e3-204">Manage guest access to Microsoft 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="aa7e3-205">静的なグループメンバーシップを動的に変更する</span><span class="sxs-lookup"><span data-stu-id="aa7e3-205">Change static group membership to dynamic in</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
