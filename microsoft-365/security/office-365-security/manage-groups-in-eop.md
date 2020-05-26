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
description: Standalone Exchange Online Protection (EOP) 組織内の管理者は、Exchange 管理センター (EAC) とスタンドアロン Exchange Online Protection (EOP) PowerShell で、配布グループとメールが有効なセキュリティグループを作成、変更、および削除する方法を学習できます。
ms.openlocfilehash: 4f1dbdb503f8baf02b7dd763dbf7fc6acdf5771a
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352193"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="1f858-103">EOP でグループを管理する</span><span class="sxs-lookup"><span data-stu-id="1f858-103">Manage groups in EOP</span></span>

<span data-ttu-id="1f858-104">Exchange Online メールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) 組織では、次の種類のグループを作成、変更、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="1f858-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="1f858-105">**配布グループ**: メールユーザーまたは他の配布グループのコレクション。</span><span class="sxs-lookup"><span data-stu-id="1f858-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="1f858-106">たとえば、関係する共通領域で電子メールを送受信する必要がある teams やその他の臨時グループがあります。</span><span class="sxs-lookup"><span data-stu-id="1f858-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="1f858-107">配布グループは、電子メールメッセージの配布専用であり、セキュリティプリンシパルではありません (アクセス許可を割り当てることはできません)。</span><span class="sxs-lookup"><span data-stu-id="1f858-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="1f858-108">**メールが有効なセキュリティグループ**: 管理者の役割に対するアクセス許可を必要とする、メールユーザーおよびその他のセキュリティグループのコレクション。</span><span class="sxs-lookup"><span data-stu-id="1f858-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="1f858-109">たとえば、特定のユーザーグループに管理者アクセス許可を付与して、スパム対策とマルウェア対策設定を構成できるようにする場合があります。</span><span class="sxs-lookup"><span data-stu-id="1f858-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <ul><li><span data-ttu-id="1f858-110">既定では、新しいメールが有効なセキュリティグループは、外部 (認証されていない) 送信者からのメッセージを拒否します。</span><span class="sxs-lookup"><span data-stu-id="1f858-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span></li><li><span data-ttu-id="1f858-111">メールが有効なセキュリティグループに配布グループを追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="1f858-111">Don't add distribution groups to mail-enabled security groups.</span></span></li></ul><span data-ttu-id="1f858-112">.</span><span class="sxs-lookup"><span data-stu-id="1f858-112">.</span></span>

<span data-ttu-id="1f858-113">グループを管理するには、Exchange 管理センター (EAC) とスタンドアロン EOP PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f858-113">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1f858-114">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="1f858-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1f858-115">Exchange 管理センターを開くには、「 [exchange admin center in STANDALONE EOP](exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f858-115">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="1f858-116">スタンドアロンの EOP PowerShell に接続するには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f858-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1f858-117">スタンドアロンの EOP PowerShell でグループを管理する場合、調整が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1f858-117">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="1f858-118">このトピックの PowerShell の手順では、コマンドの結果が表示されるまでに数分の遅延が発生するバッチ処理方式を使用しています。</span><span class="sxs-lookup"><span data-stu-id="1f858-118">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="1f858-119">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f858-119">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="1f858-120">具体的には、既定では、組織の管理 (グローバル管理者) および受信者管理役割グループに割り当てられている配布グループの役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="1f858-120">Specifically, you need the Distribution Groups role, which is assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="1f858-121">詳細については、「 [Permissions in STANDALONE EOP](feature-permissions-in-eop.md) 」を参照して、EAC を使用して、[役割グループのメンバーの一覧を変更](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)します。</span><span class="sxs-lookup"><span data-stu-id="1f858-121">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="1f858-122">このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f858-122">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="1f858-123">問題がある場合は、</span><span class="sxs-lookup"><span data-stu-id="1f858-123">Having problems?</span></span> <span data-ttu-id="1f858-124">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)フォーラムでヘルプを要求します。</span><span class="sxs-lookup"><span data-stu-id="1f858-124">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="1f858-125">Exchange 管理センターを使用して配布グループを管理する</span><span class="sxs-lookup"><span data-stu-id="1f858-125">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="1f858-126">EAC を使用してグループを作成する</span><span class="sxs-lookup"><span data-stu-id="1f858-126">Use the EAC to create groups</span></span>

1. <span data-ttu-id="1f858-127">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1f858-127">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="1f858-128">[**新しい** ![ 新規作成] アイコンをクリックし、 ](../../media/ITPro-EAC-AddIcon.png) 次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f858-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="1f858-129">**配布グループ**</span><span class="sxs-lookup"><span data-stu-id="1f858-129">**Distribution group**</span></span>

   - <span data-ttu-id="1f858-130">**メールが有効なセキュリティ グループ**</span><span class="sxs-lookup"><span data-stu-id="1f858-130">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="1f858-131">開いた [新しいグループ] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1f858-131">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="1f858-132">でマークされた設定 <sup>\*</sup> は必須です。</span><span class="sxs-lookup"><span data-stu-id="1f858-132">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="1f858-133"><sup>\*</sup>[**表示名**]: この名前は、組織のアドレス帳、このグループに電子メールが送信されるときの宛先行、EAC の [**グループ**] リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f858-133"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="1f858-134">表示名は必須であり、一意である必要があります。わかりやすい名前にする必要があります。ユーザーがわかるようにします。</span><span class="sxs-lookup"><span data-stu-id="1f858-134">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="1f858-135"><sup>\*</sup>**エイリアス**: このボックスを使用して、グループのエイリアス名を入力します。</span><span class="sxs-lookup"><span data-stu-id="1f858-135"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="1f858-136">エイリアスは64文字を超えることはできず、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f858-136">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="1f858-137">ユーザーが電子メールメッセージの [宛先] 行にエイリアスを入力すると、グループの表示名に解決されます。</span><span class="sxs-lookup"><span data-stu-id="1f858-137">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="1f858-138"><sup>\*</sup>**メールアドレス**: メールアドレスは、アットマーク記号 (@) の左側にあるエイリアスと、右側のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="1f858-138"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="1f858-139">既定では、エイリアスの値がエイリアスの値に使用**されます**が、これは変更できます。</span><span class="sxs-lookup"><span data-stu-id="1f858-139">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="1f858-140">[ドメイン] の値に対して、ドロップダウンをクリックして、組織内のドメインを選択して承認します。</span><span class="sxs-lookup"><span data-stu-id="1f858-140">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="1f858-141">**説明**: この説明は、アドレス帳と EAC の詳細ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f858-141">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="1f858-142"><sup>\*</sup>**所有者**: グループの所有者は、グループのメンバーシップを管理できます。</span><span class="sxs-lookup"><span data-stu-id="1f858-142"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="1f858-143">既定では、グループを作成するユーザーがグループの所有者になります。</span><span class="sxs-lookup"><span data-stu-id="1f858-143">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="1f858-144">グループには、最低 1 人の所有者が必要です。</span><span class="sxs-lookup"><span data-stu-id="1f858-144">All groups must have at least one owner.</span></span>

     <span data-ttu-id="1f858-145">所有者を追加するには \*\*、[追加\*\* ![ ] アイコンをクリックし ](../../media/ITPro-EAC-AddIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="1f858-145">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="1f858-146">表示されるダイアログで、受信者またはグループを見つけて選択し、[ **>**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f858-146">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="1f858-147">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1f858-147">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="1f858-148">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f858-148">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="1f858-149">所有者を削除するには、所有者を選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="1f858-149">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="1f858-150">**Members**: グループメンバーを追加および削除します。</span><span class="sxs-lookup"><span data-stu-id="1f858-150">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="1f858-151">メンバーを追加するには \*\*、[追加\*\* ![ ] アイコンをクリックし ](../../media/ITPro-EAC-AddIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="1f858-151">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="1f858-152">表示されるダイアログで、受信者またはグループを見つけて選択し、[ **>**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f858-152">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="1f858-153">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1f858-153">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="1f858-154">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f858-154">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="1f858-155">メンバーを削除するには、メンバーを選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="1f858-155">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="1f858-156">完了したら、[**保存**] をクリックして配布グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f858-156">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="1f858-157">EAC を使用して配布グループを変更する</span><span class="sxs-lookup"><span data-stu-id="1f858-157">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="1f858-158">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1f858-158">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="1f858-159">グループの一覧で、変更する配布グループまたはメールが有効なセキュリティグループを選択し、[編集] 編集アイコン**をクリックし** ![ ](../../media/ITPro-EAC-AddIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="1f858-159">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="1f858-160">開いた配布グループのプロパティページで、次のタブのいずれかをクリックして、プロパティを表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="1f858-160">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="1f858-161">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f858-161">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="1f858-162">全般</span><span class="sxs-lookup"><span data-stu-id="1f858-162">General</span></span>

<span data-ttu-id="1f858-163">このタブを使用して、グループに関する基本情報を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="1f858-163">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="1f858-164">[**表示名**]: この名前はアドレス帳、このグループに電子メールを送信するときの [宛先] 行、および [**グループ] リスト**に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f858-164">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="1f858-165">表示名は必須であり、ユーザーが内容を認識できるようにわかりやすい名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f858-165">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="1f858-166">また、表示名は、ドメイン内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f858-166">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="1f858-167">グループの名前付けポリシーを実装している場合、表示名は、ポリシーで定義されている名前付け形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f858-167">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="1f858-168">**エイリアス**: これは、電子メールアドレスの @ 記号の左に表示される部分です。</span><span class="sxs-lookup"><span data-stu-id="1f858-168">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="1f858-169">エイリアスを変更すると、グループのプライマリ SMTP アドレスも変更され、新しいエイリアスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1f858-169">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="1f858-170">また、以前のエイリアスが含まれている電子メール アドレスは、グループのプロキシ アドレスとして保持されます。</span><span class="sxs-lookup"><span data-stu-id="1f858-170">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="1f858-171">**メールアドレス**: メールアドレスは、アットマーク記号 (@) の左側にあるエイリアスと、右側のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="1f858-171">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="1f858-172">既定では、エイリアスの値がエイリアスの値に使用**されます**が、これは変更できます。</span><span class="sxs-lookup"><span data-stu-id="1f858-172">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="1f858-173">[ドメイン] の値に対して、ドロップダウンをクリックして、組織内のドメインを選択して承認します。</span><span class="sxs-lookup"><span data-stu-id="1f858-173">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="1f858-174">**説明**: この説明は、アドレス帳と EAC の詳細ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f858-174">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="1f858-175">Ownership</span><span class="sxs-lookup"><span data-stu-id="1f858-175">Ownership</span></span>

<span data-ttu-id="1f858-176">このタブを使用して、グループの所有者を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1f858-176">Use this tab to assign group owners.</span></span> <span data-ttu-id="1f858-177">グループの所有者は、グループのメンバーシップを管理できます。</span><span class="sxs-lookup"><span data-stu-id="1f858-177">A group owner can manage group membership.</span></span> <span data-ttu-id="1f858-178">既定では、グループを作成するユーザーがグループの所有者になります。</span><span class="sxs-lookup"><span data-stu-id="1f858-178">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="1f858-179">グループには、最低 1 人の所有者が必要です。</span><span class="sxs-lookup"><span data-stu-id="1f858-179">All groups must have at least one owner.</span></span>

<span data-ttu-id="1f858-180">所有者を追加するには \*\*、[追加\*\* ![ ] アイコンをクリックし ](../../media/ITPro-EAC-AddIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="1f858-180">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="1f858-181">表示されるダイアログで、受信者を検索して選択し、[追加] をクリックし **>** します。</span><span class="sxs-lookup"><span data-stu-id="1f858-181">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="1f858-182">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1f858-182">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="1f858-183">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f858-183">When you're finished, click **OK**.</span></span>

<span data-ttu-id="1f858-184">所有者を削除するには、所有者を選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="1f858-184">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="1f858-185">メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="1f858-185">Membership</span></span>

<span data-ttu-id="1f858-186">グループ メンバーを追加または削除するには、このタブを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f858-186">Use this tab to add or remove group members.</span></span> <span data-ttu-id="1f858-187">グループの所有者は、グループのメンバーである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1f858-187">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="1f858-188">メンバーを追加するには \*\*、[追加\*\* ![ ] アイコンをクリックし ](../../media/ITPro-EAC-AddIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="1f858-188">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="1f858-189">表示されるダイアログで、受信者またはグループを見つけて選択し、[ **>**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f858-189">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="1f858-190">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1f858-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="1f858-191">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f858-191">When you're finished, click **OK**.</span></span>

<span data-ttu-id="1f858-192">メンバーを削除するには、メンバーを選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="1f858-192">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="1f858-193">EAC を使用してグループを削除する</span><span class="sxs-lookup"><span data-stu-id="1f858-193">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="1f858-194">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1f858-194">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="1f858-195">グループの一覧で、削除する配布グループを選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="1f858-195">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="1f858-196">PowerShell を使用してグループを管理する</span><span class="sxs-lookup"><span data-stu-id="1f858-196">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="1f858-197">スタンドアロンの EOP PowerShell を使用してグループを表示する</span><span class="sxs-lookup"><span data-stu-id="1f858-197">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="1f858-198">スタンドアロン EOP PowerShell のすべての配布グループとメールが有効なセキュリティグループの要約リストを返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1f858-198">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="1f858-199">グループメンバーの一覧を取得するには、 \< groupidentity を \> グループの名前、エイリアス、または電子メールアドレスに置き換えて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1f858-199">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="1f858-200">構文およびパラメーターの詳細については、「 [get-distributiongroupmember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember) [」を参照して](https://docs.microsoft.com/powershell/module/exchange/get-recipient)ください。</span><span class="sxs-lookup"><span data-stu-id="1f858-200">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="1f858-201">スタンドアロンの EOP PowerShell を使用してグループを作成する</span><span class="sxs-lookup"><span data-stu-id="1f858-201">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="1f858-202">スタンドアロン EOP PowerShell で配布グループまたはメールが有効なセキュリティグループを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f858-202">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="1f858-203">**注**:</span><span class="sxs-lookup"><span data-stu-id="1f858-203">**Notes**:</span></span>

- <span data-ttu-id="1f858-204">_Name_パラメーターは必須で、最大長は64文字で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f858-204">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="1f858-205">_DisplayName_パラメーターを使用しない場合、 _name_パラメーターの値が表示名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f858-205">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="1f858-206">_Alias_パラメーターを使用しない場合、 _Name_パラメーターはエイリアスの値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f858-206">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="1f858-207">スペースは削除されます。サポートされていない文字は疑問符 (?) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="1f858-207">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="1f858-208">_Primarysmtpaddress_パラメーターを使用しない場合、エイリアスの値は_primarysmtpaddress_パラメーターで使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f858-208">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="1f858-209">_Type_パラメーターを使用しない場合、既定値は Distribution になります。</span><span class="sxs-lookup"><span data-stu-id="1f858-209">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="1f858-210">この例では、指定されたプロパティを使用して、IT 管理者という名前の配布グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f858-210">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="1f858-211">構文およびパラメーターの詳細については、「 [New-Eop/グループ](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f858-211">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="1f858-212">スタンドアロンの EOP PowerShell を使用してグループを変更する</span><span class="sxs-lookup"><span data-stu-id="1f858-212">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="1f858-213">スタンドアロン EOP PowerShell でグループを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f858-213">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="1f858-214">この例では、シアトルの従業員グループのプライマリ SMTP アドレス (返信アドレスとも呼ばれます) を sea.employees@contoso.com に変更します。</span><span class="sxs-lookup"><span data-stu-id="1f858-214">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="1f858-215">この例では、セキュリティチームグループの現在のメンバーを、キティー Petersen Tyson Fawcett と置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1f858-215">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="1f858-216">この例では、グループの現在のメンバーを保持しながら、Tyson Fawcett という名前の新しいユーザーをセキュリティチームという名前のグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="1f858-216">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="1f858-217">構文およびパラメーターの詳細については、「 [update-eopdistributiongroupmember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)」[を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup)。</span><span class="sxs-lookup"><span data-stu-id="1f858-217">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="1f858-218">リモートの Windows PowerShell を使用してグループを削除する</span><span class="sxs-lookup"><span data-stu-id="1f858-218">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="1f858-219">この例では、IT 管理者という名前の配布グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="1f858-219">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="1f858-220">構文およびパラメーターの詳細については、「[削除-Eop/グループ](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f858-220">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="1f858-221">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="1f858-221">How do you know these procedures worked?</span></span>

<span data-ttu-id="1f858-222">配布グループまたはメールが有効なセキュリティグループの作成、変更、または削除が正常に行われたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1f858-222">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="1f858-223">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1f858-223">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="1f858-224">グループが表示されている (またはリストされていない) ことを確認し、**グループの種類**の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="1f858-224">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="1f858-225">グループを選択して、詳細ウィンドウに情報を表示するか、[編集アイコンの**編集**] をクリックして ![ 設定を表示し ](../../media/ITPro-EAC-AddIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="1f858-225">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="1f858-226">スタンドアロン EOP PowerShell で次のコマンドを実行して、グループが一覧に表示されている (または一覧に表示されていない) ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f858-226">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="1f858-227">\<Groupidentity を \> グループの名前、エイリアス、または電子メールアドレスに置き換え、次のコマンドを実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="1f858-227">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="1f858-228">グループメンバーを表示するには、 \< groupidentity を \> グループの名前、エイリアス、または電子メールアドレスに置き換えて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1f858-228">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
