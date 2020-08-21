---
title: EOP でグループを管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: スタンドアロン Exchange Online Protection (EOP) 組織の管理者は、Exchange 管理センター (EAC) とスタンドアロン Exchange Online Protection (EOP) PowerShell で配布グループとメールが有効なセキュリティ グループを作成、変更、削除する方法を学習できます。
ms.openlocfilehash: e7b93b9d05fda7e4f5f8abea02fbe3f1c70a6c74
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826555"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="98fcb-103">EOP でグループを管理する</span><span class="sxs-lookup"><span data-stu-id="98fcb-103">Manage groups in EOP</span></span>

<span data-ttu-id="98fcb-104">Exchange Online メールボックスを持たないスタンドアロン Exchange Online Protection (EOP) 組織では、次の種類のグループを作成、変更、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="98fcb-105">**配布グループ**: メール ユーザーまたは他の配布グループのコレクション。</span><span class="sxs-lookup"><span data-stu-id="98fcb-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="98fcb-106">たとえば、共通の関心領域でメールを送受信する必要があるチームやその他のアドホック グループなどです。</span><span class="sxs-lookup"><span data-stu-id="98fcb-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="98fcb-107">配布グループは、電子メール メッセージの配布のみに使用すり、セキュリティ プリンシパルではありません (配布グループにはアクセス許可を割り当てられません)。</span><span class="sxs-lookup"><span data-stu-id="98fcb-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="98fcb-108">**メールが有効なセキュリティ グループ**: 管理者役割のアクセス許可が必要な、メール ユーザーとその他のセキュリティ グループのコレクション。</span><span class="sxs-lookup"><span data-stu-id="98fcb-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="98fcb-109">たとえば、特定のユーザー グループに管理者アクセス許可を付与して、スパム対策設定とマルウェア対策設定を構成できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="98fcb-110">既定では、新しいメールが有効なセキュリティ グループは外部 (認証されていない) 送信者からのメッセージを拒否します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="98fcb-111">メールが有効なセキュリティ グループには配布グループを追加しない。</span><span class="sxs-lookup"><span data-stu-id="98fcb-111">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="98fcb-112">グループは、Exchange 管理センター (EAC) とスタンドアロン EOP PowerShell で管理できます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-112">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="98fcb-113">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="98fcb-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="98fcb-114">Exchange 管理センターを開くには、「 [スタンドアロン EOP の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="98fcb-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="98fcb-115">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98fcb-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="98fcb-116">スタンドアロン EOP PowerShell でグループを管理しているときに、調整が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="98fcb-116">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="98fcb-117">このトピックの PowerShell 手順ではバッチ処理方法を使用します。このメソッドでは、コマンドの結果が表示されるまで数分の伝達遅延が出ます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-117">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="98fcb-118">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="98fcb-118">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="98fcb-119">具体的には、Distribution Groups 役割が必要です。既定では、OrganizationManagement (グローバル管理者) および RecipientManagement 役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-119">Specifically, you need the Distribution Groups role, which is assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="98fcb-120">詳細については、「スタンドアロン [EOP のアクセス許可」を参照し、EAC](feature-permissions-in-eop.md) [を使用して役割グループ内のメンバーの一覧を変更します](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="98fcb-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="98fcb-121">このトピックの手順で使用可能なキーボード ショートカットについては [、Exchange Online の Exchange 管理センターのキーボード ショートカットを参照してください](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="98fcb-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="98fcb-122">問題が発生する場合</span><span class="sxs-lookup"><span data-stu-id="98fcb-122">Having problems?</span></span> <span data-ttu-id="98fcb-123">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) フォーラムでサポートをご依頼ください。</span><span class="sxs-lookup"><span data-stu-id="98fcb-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="98fcb-124">Exchange 管理センターを使用して配布グループを管理する</span><span class="sxs-lookup"><span data-stu-id="98fcb-124">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="98fcb-125">EAC を使用してグループを作成する</span><span class="sxs-lookup"><span data-stu-id="98fcb-125">Use the EAC to create groups</span></span>

1. <span data-ttu-id="98fcb-126">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-126">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="98fcb-127">[ **新しい** ![ 新規作成] ](../../media/ITPro-EAC-AddIcon.png) アイコンをクリックし、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-127">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="98fcb-128">**配布グループ**</span><span class="sxs-lookup"><span data-stu-id="98fcb-128">**Distribution group**</span></span>

   - <span data-ttu-id="98fcb-129">**メールが有効なセキュリティ グループ**</span><span class="sxs-lookup"><span data-stu-id="98fcb-129">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="98fcb-130">開いた新しいグループ ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-130">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="98fcb-131">必須のマークが付いいい <sup>\*</sup> いの設定は、必須です。</span><span class="sxs-lookup"><span data-stu-id="98fcb-131">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="98fcb-132"><sup>\*</sup>**表示名**: この名前は組織のアドレス帳、電子メールがこのグループに送信されるときの電子メールの送信先行、EAC **の [グループ]** 一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-132"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="98fcb-133">表示名は必須で、一意である必要があります。表示名は、ユーザーが内容を認識できるようにわかりやすい名前にするものでなけたものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="98fcb-133">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="98fcb-134"><sup>\*</sup>**[エイリア**ス: このボックスに、グループのエイリアス名を入力します。]</span><span class="sxs-lookup"><span data-stu-id="98fcb-134"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="98fcb-135">エイリアスは 64 文字以内で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="98fcb-135">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="98fcb-136">ユーザーが電子メール メッセージの [出す] 行にエイリアスを入力すると、グループの表示名に解決されます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-136">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="98fcb-137"><sup>\*</sup>**Email address**: 電子メール アドレスは、アットマーク (@) の左に表示されるエイリアスと、右側のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-137"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="98fcb-138">既定では、Alias 値 **はエイリア** ス値に使用されますが、変更はできます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-138">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="98fcb-139">ドメイン値として、ドロップダウンをクリックして組織内のドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-139">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="98fcb-140">**Description**: この説明は、アドレス帳と EAC の [詳細] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-140">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="98fcb-141"><sup>\*</sup>**Owners**: グループの所有者がグループ メンバーシップを管理できます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-141"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="98fcb-142">既定では、グループを作成するユーザーがグループの所有者になります。</span><span class="sxs-lookup"><span data-stu-id="98fcb-142">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="98fcb-143">グループには、最低 1 人の所有者が必要です。</span><span class="sxs-lookup"><span data-stu-id="98fcb-143">All groups must have at least one owner.</span></span>

     <span data-ttu-id="98fcb-144">所有者を追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="98fcb-144">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="98fcb-145">表示されるダイアログで、受信者またはグループを検索して選択し、[追加 - **>**。</span><span class="sxs-lookup"><span data-stu-id="98fcb-145">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="98fcb-146">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-146">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="98fcb-147">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98fcb-147">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="98fcb-148">所有者を削除するには、所有者を選択して、[削除] **アイコンをクリック** ![ します ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="98fcb-148">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="98fcb-149">**メンバー**: グループ メンバーを追加および削除します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-149">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="98fcb-150">メンバーを追加するには、[追加] **アイコン** ![ をクリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="98fcb-150">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="98fcb-151">表示されるダイアログで、受信者またはグループを検索して選択し、[追加 - **>**。</span><span class="sxs-lookup"><span data-stu-id="98fcb-151">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="98fcb-152">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-152">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="98fcb-153">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98fcb-153">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="98fcb-154">メンバーを削除するには、メンバーを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="98fcb-154">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="98fcb-155">完了したら、[保存] をクリック **して配布** グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-155">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="98fcb-156">EAC を使用して配布グループを変更する</span><span class="sxs-lookup"><span data-stu-id="98fcb-156">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="98fcb-157">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-157">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="98fcb-158">グループの一覧で、変更する配布グループまたはメールが有効なセキュリティ グループを選択し、[編集] アイコン **をクリック** ![ します ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="98fcb-158">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="98fcb-159">開いた配布グループのプロパティ ページで、次のいずれかのタブをクリックして、プロパティを表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-159">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="98fcb-160">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98fcb-160">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="98fcb-161">全般</span><span class="sxs-lookup"><span data-stu-id="98fcb-161">General</span></span>

<span data-ttu-id="98fcb-162">このタブを使用して、グループに関する基本情報を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-162">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="98fcb-163">**表示名**: この名前はアドレス帳、電子メールがこのグループに送信されるときに [電子メール] 行、グループ一覧に **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="98fcb-163">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="98fcb-164">表示名は必須であり、ユーザーが内容を認識できるようにわかりやすい名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="98fcb-164">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="98fcb-165">また、表示名は、ドメイン内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="98fcb-165">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="98fcb-166">グループの名前付けポリシーを実装している場合、表示名は、ポリシーで定義されている名前付け形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="98fcb-166">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="98fcb-167">**Alias:** 電子メール アドレスの @ 記号の左に表示される部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-167">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="98fcb-168">エイリアスを変更すると、グループのプライマリ SMTP アドレスも変更され、新しいエイリアスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-168">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="98fcb-169">また、以前のエイリアスが含まれている電子メール アドレスは、グループのプロキシ アドレスとして保持されます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-169">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="98fcb-170">**Email address**: 電子メール アドレスは、アットマーク (@) の左に表示されるエイリアスと、右側のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-170">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="98fcb-171">既定では、Alias 値 **はエイリア** ス値に使用されますが、変更はできます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-171">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="98fcb-172">ドメイン値として、ドロップダウンをクリックして組織内のドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-172">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="98fcb-173">**Description**: この説明は、アドレス帳と EAC の [詳細] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-173">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="98fcb-174">Ownership</span><span class="sxs-lookup"><span data-stu-id="98fcb-174">Ownership</span></span>

<span data-ttu-id="98fcb-175">このタブを使用して、グループの所有者を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-175">Use this tab to assign group owners.</span></span> <span data-ttu-id="98fcb-176">グループ所有者はグループ メンバーシップを管理できます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-176">A group owner can manage group membership.</span></span> <span data-ttu-id="98fcb-177">既定では、グループを作成するユーザーがグループの所有者になります。</span><span class="sxs-lookup"><span data-stu-id="98fcb-177">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="98fcb-178">グループには、最低 1 人の所有者が必要です。</span><span class="sxs-lookup"><span data-stu-id="98fcb-178">All groups must have at least one owner.</span></span>

<span data-ttu-id="98fcb-179">所有者を追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="98fcb-179">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="98fcb-180">表示されるダイアログで、受信者を検索して選択し \*\*、[add ->] をクリック>。 \*\*</span><span class="sxs-lookup"><span data-stu-id="98fcb-180">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="98fcb-181">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-181">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="98fcb-182">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98fcb-182">When you're finished, click **OK**.</span></span>

<span data-ttu-id="98fcb-183">所有者を削除するには、所有者を選択して、[削除] **アイコンをクリック** ![ します ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="98fcb-183">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="98fcb-184">メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="98fcb-184">Membership</span></span>

<span data-ttu-id="98fcb-185">グループ メンバーを追加または削除するには、このタブを使用します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-185">Use this tab to add or remove group members.</span></span> <span data-ttu-id="98fcb-186">グループ所有者がグループのメンバーである必要はかりません。</span><span class="sxs-lookup"><span data-stu-id="98fcb-186">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="98fcb-187">メンバーを追加するには、[追加] **アイコン** ![ をクリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="98fcb-187">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="98fcb-188">表示されるダイアログで、受信者またはグループを検索して選択し、[追加 - **>**。</span><span class="sxs-lookup"><span data-stu-id="98fcb-188">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="98fcb-189">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-189">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="98fcb-190">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98fcb-190">When you're finished, click **OK**.</span></span>

<span data-ttu-id="98fcb-191">メンバーを削除するには、メンバーを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="98fcb-191">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="98fcb-192">EAC を使用してグループを削除する</span><span class="sxs-lookup"><span data-stu-id="98fcb-192">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="98fcb-193">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-193">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="98fcb-194">グループの一覧で、削除する配布グループを選択し、[削除] アイコン **をクリック** ![ します ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="98fcb-194">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="98fcb-195">PowerShell を使用してグループを管理する</span><span class="sxs-lookup"><span data-stu-id="98fcb-195">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="98fcb-196">スタンドアロン EOP PowerShell を使用してグループを表示する</span><span class="sxs-lookup"><span data-stu-id="98fcb-196">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="98fcb-197">スタンドアロン EOP PowerShell ですべての配布グループとメールが有効なセキュリティ グループの要約リストを返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-197">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="98fcb-198">グループ メンバーの一覧を返すには、グループ \<GroupIdentity\> の名前、エイリアス、またはメール アドレスに置き換え、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-198">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="98fcb-199">構文およびパラメーターの詳細については[、「Get-Recipient」と](https://docs.microsoft.com/powershell/module/exchange/get-recipient)[「Get-DistributionGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)。</span><span class="sxs-lookup"><span data-stu-id="98fcb-199">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="98fcb-200">スタンドアロン EOP PowerShell を使用してグループを作成する</span><span class="sxs-lookup"><span data-stu-id="98fcb-200">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="98fcb-201">スタンドアロン EOP PowerShell で配布グループまたはメールが有効なセキュリティ グループを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-201">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="98fcb-202">**注**:</span><span class="sxs-lookup"><span data-stu-id="98fcb-202">**Notes**:</span></span>

- <span data-ttu-id="98fcb-203">_Name パラメーターは_必須で、最大長は 64 文字で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="98fcb-203">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="98fcb-204">DisplayName パラメーターを使用し_なけら__、Name パラメーターの値_が表示名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-204">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="98fcb-205">Alias パラメーターを使用しない場合 _、エイリア_ ス値 _として Name_ パラメーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-205">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="98fcb-206">スペースは削除されます。サポートされていない文字は疑問符 (?) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-206">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="98fcb-207">PrimarySmtpAddress パラメーターを使用しない _場合は、PrimarySmtpAddress_ パラメーターでエイリアス値 _が使用_ されます。</span><span class="sxs-lookup"><span data-stu-id="98fcb-207">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="98fcb-208">_Type_パラメーターを使用しない場合、既定値は Distribution になります。</span><span class="sxs-lookup"><span data-stu-id="98fcb-208">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="98fcb-209">この例では、指定したプロパティを持つ IT Administrators という配布グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-209">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="98fcb-210">構文およびパラメーターの詳細については [、「New-EOPDistributionGroup」を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)。</span><span class="sxs-lookup"><span data-stu-id="98fcb-210">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="98fcb-211">スタンドアロン EOP PowerShell を使用してグループを変更する</span><span class="sxs-lookup"><span data-stu-id="98fcb-211">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="98fcb-212">スタンドアロン EOP PowerShell でグループを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-212">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="98fcb-213">この例では、シアトルの従業員グループのプライマリ SMTP アドレス (返信アドレスとも呼ばれる) を再割り当てにsea.employees@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="98fcb-213">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="98fcb-214">この例では、Security Team グループの現在のメンバーを Kitty Petersen と Tyson Fawcett で置き換えします。</span><span class="sxs-lookup"><span data-stu-id="98fcb-214">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="98fcb-215">この例では、Tyson Fawcett という名前の新しいユーザーを Security Team というグループに追加し、グループの現在のメンバーも保持します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-215">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="98fcb-216">構文およびパラメーターの詳細については[、「Set-EOPDistributionGroup」と](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup)[「Update-EOPDistributionGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)。</span><span class="sxs-lookup"><span data-stu-id="98fcb-216">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="98fcb-217">リモート デバイスを使用してグループを削除Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="98fcb-217">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="98fcb-218">この例では、「IT Administrators」という名前の配布グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-218">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="98fcb-219">構文およびパラメーターの詳細については [、「Remove-EOPDistributionGroup」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)。</span><span class="sxs-lookup"><span data-stu-id="98fcb-219">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="98fcb-220">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="98fcb-220">How do you know these procedures worked?</span></span>

<span data-ttu-id="98fcb-221">配布グループまたはメールが有効なセキュリティ グループの作成、変更、または削除が正常に行されたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-221">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="98fcb-222">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-222">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="98fcb-223">グループがリストに表示されている (または一覧にない) ことを確認し、グループの種類の値 **を確認** します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-223">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="98fcb-224">グループを選択して詳細ウィンドウに情報を表示するか、設定を \*\*表示するための [\*\* ![ 編集] アイコン ](../../media/ITPro-EAC-AddIcon.png) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98fcb-224">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="98fcb-225">スタンドアロン EOP PowerShell で、次のコマンドを実行して、グループがリストに表示されている (または一覧にない) ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-225">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="98fcb-226">グループ \<GroupIdentity\> の名前、エイリアス、または電子メール アドレスを置き換え、次のコマンドを実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-226">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="98fcb-227">グループ メンバーを表示するには、グループの \<GroupIdentity\> 名前、エイリアス、またはメール アドレスに置き換え、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="98fcb-227">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
