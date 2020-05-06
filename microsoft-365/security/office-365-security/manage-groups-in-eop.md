---
title: EOP でグループを管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: この記事では、exchange Online Protection (EOP) で Exchange 組織のメールが有効なグループを作成および管理する方法について説明します。
ms.openlocfilehash: 37825175e3332e975065a3807c6ed9d5096b1a7f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034404"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="5a0c5-103">EOP でグループを管理する</span><span class="sxs-lookup"><span data-stu-id="5a0c5-103">Manage groups in EOP</span></span>

 <span data-ttu-id="5a0c5-p101">Exchange Online Protection (EOP) を使用すれば、Exchange 組織のメールが有効なグループを作成できます。また、EOP を使用してメンバーシップ、電子メール アドレス、グループのその他の側面を指定するグループのプロパティを定義または更新することもできます。必要に応じて配布グループとセキュリティ グループを作成できます。これらのグループは、Exchange 管理センター (EAC) を使用するか、リモートの Windows PowerShell を介して作成できます。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-p101">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization. You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups. You can create distribution groups and security groups, depending on your needs. These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span>

## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="5a0c5-108">メールが有効なグループの種類</span><span class="sxs-lookup"><span data-stu-id="5a0c5-108">Types of mail-enabled groups</span></span>

<span data-ttu-id="5a0c5-109">Exchange 組織では、2 種類のグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-109">You can create two types of groups for your Exchange organization:</span></span>

- <span data-ttu-id="5a0c5-110">配布グループは、チームやその他の臨時のグループなど、一般的な興味分野に関するメールを受信または送信する必要がある電子メールユーザーのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-110">Distribution groups are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest.</span></span> <span data-ttu-id="5a0c5-111">配布グループは電子メール メッセージの配布専用です。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-111">Distribution groups are exclusively for distributing email messages.</span></span> <span data-ttu-id="5a0c5-112">EOP では、配布グループは、セキュリティに関連するかどうかにかかわらず、すべてのメールが有効なグループを意味します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-112">In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>

- <span data-ttu-id="5a0c5-113">セキュリティグループは、管理者ロールのアクセス許可を必要とする電子メールユーザーのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-113">Security groups are collections of email users who need access permissions for Admin roles.</span></span> <span data-ttu-id="5a0c5-114">たとえば、特定のユーザー グループに管理者役割アクセス許可を付与して、スパム対策設定とマルウェア対策設定を構成できるようにする場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-114">For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a0c5-p104">既定では、メールが有効なすべての新しいセキュリティ グループで、すべての送信者を認証する必要があります。これにより、外部の送信者はメールが有効なセキュリティ グループに対してメッセージを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-p104">By default, all new mail-enabled security groups require that all senders be authenticated. This prevents external senders from sending messages to mail-enabled security groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5a0c5-117">開始する前に</span><span class="sxs-lookup"><span data-stu-id="5a0c5-117">Before you begin</span></span>

- <span data-ttu-id="5a0c5-p105">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「配布グループとセキュリティ グループ」。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="5a0c5-120">Exchange 管理センターを開くには、「exchange [Online Protection の exchange 管理センター](exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-120">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="5a0c5-121">Exchange Online Protection の PowerShell コマンドレットを使用してグループを作成および管理する場合は、調整が発生する可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-121">Be aware that when creating and managing groups by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="5a0c5-122">このトピックの PowerShell の手順では、コマンドの結果が表示されるまでに数分の遅延が発生するバッチ処理方式を使用しています。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-122">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="5a0c5-123">Windows PowerShell を使用して Exchange Online Protection に接続する方法については、「[Exchange Online Protection の PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-123">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="5a0c5-124">このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-124">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="5a0c5-125">問題がある場合は、</span><span class="sxs-lookup"><span data-stu-id="5a0c5-125">Having problems?</span></span> <span data-ttu-id="5a0c5-126">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)フォーラムでヘルプを要求します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-126">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="5a0c5-127">EAC でグループを作成する</span><span class="sxs-lookup"><span data-stu-id="5a0c5-127">Create a group in the EAC</span></span>

1. <span data-ttu-id="5a0c5-128">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="5a0c5-129">必要**New** ![に応じて](../../media/ITPro-EAC-AddIcon.gif)、[新規追加] アイコンをクリックし、[**配布グループ**] または [**セキュリティグループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-129">Click **New** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs.</span></span>

3. <span data-ttu-id="5a0c5-130">[**新しい配布グループ**] ページまたは [**新しいセキュリティグループ**] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-130">On the **New distribution group** or **New security group** page, configure the following settings:</span></span>

   - <span data-ttu-id="5a0c5-131">[**表示名**]: 組織に固有で、EOP ユーザーにとって意味のある表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-131">**Display name**: Type a display name that's unique to your organization and meaningful to EOP users.</span></span> <span data-ttu-id="5a0c5-132">表示名は必須です。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-132">The display name is required.</span></span>

   - <span data-ttu-id="5a0c5-133">**エイリアス**: 組織に固有の最大64文字のグループエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-133">**Alias**: Type a group alias of up to 64 characters that's unique to your organization.</span></span> <span data-ttu-id="5a0c5-134">EOP ユーザーが電子メール メッセージの宛先行にエイリアスを入力すると、グループの表示名に解読されます。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-134">EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name.</span></span> <span data-ttu-id="5a0c5-135">エイリアスを変更すると、グループのプライマリ SMTP アドレスも変更され、新しいエイリアスが追加されます。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-135">If you change the alias, the primary SMTP address for the group also changes and will contain the new alias.</span></span> <span data-ttu-id="5a0c5-136">エイリアスは必須です。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-136">The alias is required.</span></span>

   - <span data-ttu-id="5a0c5-137">[**説明**]: グループの説明を入力します。これにより、ユーザーはグループの目的を知ることができます。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-137">**Description**: Type a description of the group so that people will know the purpose of the group.</span></span>

   - <span data-ttu-id="5a0c5-138">**所有者**: 既定では、グループを作成したユーザーが所有者になります。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-138">**Owners**: By default, the person who creates the group is the owner.</span></span> <span data-ttu-id="5a0c5-139">所有者を追加するには、[追加]](../../media/ITPro-EAC-AddIcon.gif) **[追加] アイコンを選択** ![します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-139">You can add an owner by choosing **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="5a0c5-140">グループには、最低 1 人の所有者が必要です。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-140">All groups must have at least one owner.</span></span>

     > [!NOTE]
     > <span data-ttu-id="5a0c5-141">所有者はグループのメンバーである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-141">Owners don't have to be members of the group.</span></span>

   - <span data-ttu-id="5a0c5-142">**メンバー**: グループメンバーを追加し、グループに参加または脱退するために承認が必要かどうかを指定するには、このセクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-142">**Members**: Use this section to add group members and to specify whether approval is required for people to join or leave the group.</span></span> <span data-ttu-id="5a0c5-143">グループにメンバーを追加するには、[追加](../../media/ITPro-EAC-AddIcon.gif)] アイコン**をクリックし** ![ます。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-143">To add members to the group, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span>

4. <span data-ttu-id="5a0c5-144">**[OK]** をクリックして元のページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-144">Click **OK** to return to the original page.</span></span>

5. <span data-ttu-id="5a0c5-p111">完了したら、 **[保存]** をクリックしてグループを作成します。新しいグループがグループの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-p111">When you've finished, click **Save** to create the group. The new group should appear in the list of groups.</span></span>

## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="5a0c5-147">EAC でグループを編集または削除する</span><span class="sxs-lookup"><span data-stu-id="5a0c5-147">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="5a0c5-148">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-148">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="5a0c5-149">次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-149">Do one of the following steps:</span></span>

   - <span data-ttu-id="5a0c5-150">グループを編集するには、グループの一覧で、表示または変更するグループをクリックし、[編集アイコン**Edit** ![](../../media/ITPro-EAC-EditIcon.gif)の編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-150">To edit a group: In the list of groups, click the group that you want to view or change, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="5a0c5-151">全般設定の更新、グループの所有者の追加または削除、および必要に応じてグループメンバーの追加または削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-151">You can update general settings, add or remove group owners, and add or remove group members as needed.</span></span>

   - <span data-ttu-id="5a0c5-152">グループを削除するには、グループを選択し、[](../../media/ITPro-EAC-RemoveIcon.gif)削除 **] [** ![削除] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-152">To remove a group: Select the group and click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="5a0c5-153">変更が完了したら、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-153">When you're finished making your changes, click **Save**.</span></span>

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="5a0c5-154">リモートの Windows PowerShell を使用してグループを作成、編集、または削除する</span><span class="sxs-lookup"><span data-stu-id="5a0c5-154">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="5a0c5-155">このセクションでは、グループを作成し、Exchange Online Protection の PowerShell でそのプロパティを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-155">This section provides information about creating groups and changing their properties in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="5a0c5-156">また、既存のグループを削除する方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-156">It also shows how to remove an existing group.</span></span>

### <a name="create-a-group-using-remote-windows-powershell"></a><span data-ttu-id="5a0c5-157">リモートの Windows PowerShell を使用してグループを作成する</span><span class="sxs-lookup"><span data-stu-id="5a0c5-157">Create a group using remote Windows PowerShell</span></span>

<span data-ttu-id="5a0c5-p114">この例では、コマンドレット [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) を使用して、エイリアスが「itadmin」、名前が「IT Administrators」の配布グループを作成します。また、ユーザーをグループのメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-p114">This example uses the [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators. It also adds users as members of the group.</span></span>

```PowerShell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

<span data-ttu-id="5a0c5-160">**注**: 配布グループではなくセキュリティグループを作成するには、 `Security` *Type*パラメーターの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-160">**Note**: To create a security group instead of a distribution group, use the value `Security` for the *Type* parameter.</span></span>

<span data-ttu-id="5a0c5-161">IT 管理者グループが正常に作成されたことを確認するには、次のコマンドを実行して、新しいグループに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-161">To verify that you've successfully created the IT Administrators group, run the following command to display information about the new group:</span></span>

```PowerShell
Get-Recipient "IT Administrators" | Format-List
```

<span data-ttu-id="5a0c5-162">構文およびパラメーターの詳細については、「 [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-162">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span></span>

<span data-ttu-id="5a0c5-163">グループ内のメンバーの一覧を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-163">To get a list of members in the group, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "IT Administrators"
```

<span data-ttu-id="5a0c5-164">構文およびパラメーターの詳細については、「 [get-distributiongroupmember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-164">For detailed syntax and parameter information, see [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

<span data-ttu-id="5a0c5-165">すべてのグループの完全な一覧を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-165">To get a full list of all your groups, run the following command:</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a><span data-ttu-id="5a0c5-166">リモート Windows PowerShell を使用してグループのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="5a0c5-166">Change the properties of a group using remote Windows PowerShell</span></span>

<span data-ttu-id="5a0c5-167">EAC の代わりに PowerShell を使用する利点は、複数のグループのプロパティを変更できることです。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-167">An advantage of using PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span>

<span data-ttu-id="5a0c5-168">Exchange Online Protection PowerShell を使用してグループのプロパティを変更する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-168">Here are some examples of using Exchange Online Protection PowerShell to change group properties.</span></span>

<span data-ttu-id="5a0c5-169">この例では、シアトルの従業員グループのプライマリ SMTP アドレス (返信アドレスとも呼ばれます) を sea.employees@contoso.com に変更します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-169">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="5a0c5-170">構文およびパラメーターの詳細については、「 [Set-Eop/グループ](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-170">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span></span>

<span data-ttu-id="5a0c5-171">グループのプロパティが正常に変更されたことを確認するには、次のコマンドを実行して新しい値を確認します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-171">To verify that you've successfully changed the properties for the group, run the following command to verify the new value:</span></span>

```PowerShell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

<span data-ttu-id="5a0c5-172">この例では、シアトルの従業員グループのすべてのメンバーを更新します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-172">This example updates all the members of the Seattle Employees group.</span></span> <span data-ttu-id="5a0c5-173">全メンバーをコンマを使用して区切ります。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-173">Use a comma to separate all members.</span></span>

```PowerShell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

<span data-ttu-id="5a0c5-174">構文およびパラメーターの詳細については、「 [update-eopdistributiongroupmember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-174">For detailed syntax and parameter information, see [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

<span data-ttu-id="5a0c5-175">シアトルの従業員グループのすべてのメンバーの一覧を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-175">To get the list of all the members in the group Seattle Employees, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="5a0c5-176">リモートの Windows PowerShell を使用してグループを削除する</span><span class="sxs-lookup"><span data-stu-id="5a0c5-176">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="5a0c5-177">この例では、IT 管理者という名前の配布グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-177">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="5a0c5-178">構文およびパラメーターの詳細については、「[削除-Eop/グループ](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-178">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

<span data-ttu-id="5a0c5-179">グループが削除されたことを確認するには、次のコマンドを実行し、グループ (この場合は「It Administrators」) が削除されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a0c5-179">To verify that the group was removed, run the following command, and confirm that the group (in this case "It Administrators") was deleted.</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
