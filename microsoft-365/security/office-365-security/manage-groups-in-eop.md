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
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: スタンドアロンの Exchange Online Protection (EOP) 組織の管理者は、Exchange 管理センター (EAC) およびスタンドアロンの Exchange Online Protection (EOP) PowerShell で配布グループとメールが有効なセキュリティ グループを作成、変更、削除する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3b97e3fac0840753edada964252875a6e3a4fa04
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926834"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="2f822-103">EOP でグループを管理する</span><span class="sxs-lookup"><span data-stu-id="2f822-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2f822-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="2f822-104">**Applies to**</span></span>
-  [<span data-ttu-id="2f822-105">Exchange Online Protection スタンドアロン</span><span class="sxs-lookup"><span data-stu-id="2f822-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="2f822-106">Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、次の種類のグループを作成、変更、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="2f822-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="2f822-107">**配布グループ**: メール ユーザーまたは他の配布グループのコレクション。</span><span class="sxs-lookup"><span data-stu-id="2f822-107">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="2f822-108">たとえば、関心のある共通領域で電子メールを受信または送信する必要があるチームや他のアドホック グループ。</span><span class="sxs-lookup"><span data-stu-id="2f822-108">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="2f822-109">配布グループは、電子メール メッセージの配布専用であり、セキュリティ プリンシパルではありません (アクセス許可を割り当てすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="2f822-109">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="2f822-110">**メールが有効なセキュリティ グループ**: 管理者ロールのアクセス許可を必要とするメール ユーザーと他のセキュリティ グループのコレクション。</span><span class="sxs-lookup"><span data-stu-id="2f822-110">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="2f822-111">たとえば、スパム対策とマルウェア対策の設定を構成できるよう、特定のグループのユーザーに管理者アクセス許可を与える場合があります。</span><span class="sxs-lookup"><span data-stu-id="2f822-111">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="2f822-112">既定では、新しいメールが有効なセキュリティ グループは、外部 (認証されていない) 送信者からのメッセージを拒否します。</span><span class="sxs-lookup"><span data-stu-id="2f822-112">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="2f822-113">メールが有効なセキュリティ グループに配布グループを追加しない。</span><span class="sxs-lookup"><span data-stu-id="2f822-113">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="2f822-114">Exchange 管理センター (EAC) とスタンドアロン EOP PowerShell でグループを管理できます。</span><span class="sxs-lookup"><span data-stu-id="2f822-114">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2f822-115">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="2f822-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2f822-116">Exchange 管理センターを開く方法については、「 [スタンドアロン EOP の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="2f822-116">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="2f822-117">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f822-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2f822-118">スタンドアロン EOP PowerShell でグループを管理すると、調整が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f822-118">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="2f822-119">この記事の PowerShell プロシージャでは、バッチ処理メソッドを使用して、コマンドの結果が表示される数分前に伝達遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="2f822-119">The PowerShell procedures in this article use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="2f822-120">この記事の手順を実行するには、Exchange Online Protection でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f822-120">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="2f822-121">具体的には、既定で組織の **管理役割グループ** と受信者管理役割グループに割り当てられている配布 **グループの役割** が必要です。</span><span class="sxs-lookup"><span data-stu-id="2f822-121">Specifically, you need the **Distribution Groups** role, which is assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="2f822-122">詳細については、「スタンドアロン [EOP のアクセス](feature-permissions-in-eop.md) 許可」および「役割グループのメンバーの一覧を [変更する EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)を使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f822-122">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="2f822-123">この記事の手順に適用されるキーボード ショートカットの詳細については、「Exchange Online の Exchange 管理センターのキーボード ショートカット」 [を参照してください](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="2f822-123">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="2f822-124">問題が発生する場合</span><span class="sxs-lookup"><span data-stu-id="2f822-124">Having problems?</span></span> <span data-ttu-id="2f822-125">[Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) フォーラムでサポートをご依頼ください。</span><span class="sxs-lookup"><span data-stu-id="2f822-125">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="2f822-126">Exchange 管理センターを使用して配布グループを管理する</span><span class="sxs-lookup"><span data-stu-id="2f822-126">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="2f822-127">EAC を使用してグループを作成する</span><span class="sxs-lookup"><span data-stu-id="2f822-127">Use the EAC to create groups</span></span>

1. <span data-ttu-id="2f822-128">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="2f822-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="2f822-129">[ **新しい** ![ 新規] アイコン ](../../media/ITPro-EAC-AddIcon.png) をクリックし、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="2f822-129">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="2f822-130">**配布グループ**</span><span class="sxs-lookup"><span data-stu-id="2f822-130">**Distribution group**</span></span>

   - <span data-ttu-id="2f822-131">**メールが有効なセキュリティ グループ**</span><span class="sxs-lookup"><span data-stu-id="2f822-131">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="2f822-132">開く新しいグループ ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="2f822-132">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="2f822-133">マークが付いた設定 <sup>\*</sup> が必要です。</span><span class="sxs-lookup"><span data-stu-id="2f822-133">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="2f822-134"><sup>\*</sup>**表示名**: この名前は、組織のアドレス帳、このグループに電子メールが送信される場合は To: 行、EAC の [グループ] リストに表示されます。 </span><span class="sxs-lookup"><span data-stu-id="2f822-134"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="2f822-135">表示名は必須であり、一意である必要があります。また、ユーザーがそれが何かを認識するように、ユーザーフレンドリーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f822-135">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="2f822-136"><sup>\*</sup>**Alias**: このボックスを使用して、グループのエイリアスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2f822-136"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="2f822-137">エイリアスは 64 文字を超えることはできません。一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f822-137">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="2f822-138">ユーザーが電子メール メッセージの [To] 行にエイリアスを入力すると、グループの表示名に解決されます。</span><span class="sxs-lookup"><span data-stu-id="2f822-138">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="2f822-139"><sup>\*</sup>**電子メール** アドレス : 電子メール アドレスは、at (@) 記号の左側のエイリアスと、右側のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="2f822-139"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="2f822-140">既定では、エイリアスの値は **エイリアス** 値に使用されますが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="2f822-140">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="2f822-141">ドメイン値の場合は、ドロップダウンをクリックし、組織内のドメインを選択して承諾します。</span><span class="sxs-lookup"><span data-stu-id="2f822-141">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="2f822-142">**説明**: この説明は、アドレス帳と EAC の [詳細] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f822-142">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="2f822-143"><sup>\*</sup>**所有者**: グループ所有者はグループ メンバーシップを管理できます。</span><span class="sxs-lookup"><span data-stu-id="2f822-143"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="2f822-144">既定では、グループを作成するユーザーがグループの所有者になります。</span><span class="sxs-lookup"><span data-stu-id="2f822-144">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="2f822-145">グループには、最低 1 人の所有者が必要です。</span><span class="sxs-lookup"><span data-stu-id="2f822-145">All groups must have at least one owner.</span></span>

     <span data-ttu-id="2f822-146">所有者を追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="2f822-146">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="2f822-147">表示されるダイアログで、受信者またはグループを検索して選択し、[->] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2f822-147">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="2f822-148">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="2f822-148">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="2f822-149">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f822-149">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="2f822-150">所有者を削除するには、所有者を選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="2f822-150">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="2f822-151">**メンバー**: グループ メンバーを追加および削除します。</span><span class="sxs-lookup"><span data-stu-id="2f822-151">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="2f822-152">メンバーを追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="2f822-152">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="2f822-153">表示されるダイアログで、受信者またはグループを検索して選択し、[->] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2f822-153">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="2f822-154">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="2f822-154">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="2f822-155">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f822-155">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="2f822-156">メンバーを削除するには、メンバーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="2f822-156">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="2f822-157">完了したら、[保存] をクリック **して** 配布グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f822-157">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="2f822-158">EAC を使用して配布グループを変更する</span><span class="sxs-lookup"><span data-stu-id="2f822-158">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="2f822-159">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="2f822-159">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="2f822-160">グループの一覧で、変更する配布グループまたはメールが有効なセキュリティ グループを選択し、[編集] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="2f822-160">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="2f822-161">開く配布グループのプロパティ ページで、次のいずれかのタブをクリックしてプロパティを表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="2f822-161">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="2f822-162">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f822-162">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="2f822-163">全般</span><span class="sxs-lookup"><span data-stu-id="2f822-163">General</span></span>

<span data-ttu-id="2f822-164">このタブを使用して、グループに関する基本情報を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="2f822-164">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="2f822-165">**表示名**: この名前は、アドレス帳、このグループに電子メールが送信される場合の [To] 行、および [グループ] リストに **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="2f822-165">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="2f822-166">表示名は必須であり、ユーザーが内容を認識できるようにわかりやすい名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f822-166">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="2f822-167">また、表示名は、ドメイン内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f822-167">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="2f822-168">グループの名前付けポリシーを実装している場合、表示名は、ポリシーで定義されている名前付け形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f822-168">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="2f822-169">**エイリアス**: これは、at (@) 記号の左側に表示される電子メール アドレスの部分です。</span><span class="sxs-lookup"><span data-stu-id="2f822-169">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="2f822-170">エイリアスを変更すると、グループのプライマリ SMTP アドレスも変更され、新しいエイリアスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f822-170">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="2f822-171">また、以前のエイリアスが含まれている電子メール アドレスは、グループのプロキシ アドレスとして保持されます。</span><span class="sxs-lookup"><span data-stu-id="2f822-171">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="2f822-172">**電子メール** アドレス : 電子メール アドレスは、at (@) 記号の左側のエイリアスと、右側のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="2f822-172">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="2f822-173">既定では、エイリアスの値は **エイリアス** 値に使用されますが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="2f822-173">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="2f822-174">ドメイン値の場合は、ドロップダウンをクリックし、組織内のドメインを選択して承諾します。</span><span class="sxs-lookup"><span data-stu-id="2f822-174">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="2f822-175">**説明**: この説明は、アドレス帳と EAC の [詳細] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f822-175">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="2f822-176">Ownership</span><span class="sxs-lookup"><span data-stu-id="2f822-176">Ownership</span></span>

<span data-ttu-id="2f822-177">グループ所有者を割り当てるには、このタブを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f822-177">Use this tab to assign group owners.</span></span> <span data-ttu-id="2f822-178">グループ所有者は、グループ メンバーシップを管理できます。</span><span class="sxs-lookup"><span data-stu-id="2f822-178">A group owner can manage group membership.</span></span> <span data-ttu-id="2f822-179">既定では、グループを作成するユーザーがグループの所有者になります。</span><span class="sxs-lookup"><span data-stu-id="2f822-179">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="2f822-180">グループには、最低 1 人の所有者が必要です。</span><span class="sxs-lookup"><span data-stu-id="2f822-180">All groups must have at least one owner.</span></span>

<span data-ttu-id="2f822-181">所有者を追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="2f822-181">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="2f822-182">表示されるダイアログで、受信者を検索して選択し、[->] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2f822-182">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="2f822-183">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="2f822-183">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="2f822-184">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f822-184">When you're finished, click **OK**.</span></span>

<span data-ttu-id="2f822-185">所有者を削除するには、所有者を選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="2f822-185">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="2f822-186">メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="2f822-186">Membership</span></span>

<span data-ttu-id="2f822-187">グループ メンバーを追加または削除するには、このタブを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f822-187">Use this tab to add or remove group members.</span></span> <span data-ttu-id="2f822-188">グループの所有者は、グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f822-188">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="2f822-189">メンバーを追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="2f822-189">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="2f822-190">表示されるダイアログで、受信者またはグループを検索して選択し、[->] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2f822-190">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="2f822-191">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="2f822-191">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="2f822-192">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f822-192">When you're finished, click **OK**.</span></span>

<span data-ttu-id="2f822-193">メンバーを削除するには、メンバーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="2f822-193">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="2f822-194">EAC を使用してグループを削除する</span><span class="sxs-lookup"><span data-stu-id="2f822-194">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="2f822-195">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="2f822-195">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="2f822-196">グループの一覧で、削除する配布グループを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="2f822-196">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="2f822-197">PowerShell を使用してグループを管理する</span><span class="sxs-lookup"><span data-stu-id="2f822-197">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="2f822-198">スタンドアロン EOP PowerShell を使用してグループを表示する</span><span class="sxs-lookup"><span data-stu-id="2f822-198">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="2f822-199">スタンドアロン EOP PowerShell のすべての配布グループとメールが有効なセキュリティ グループの概要リストを取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2f822-199">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="2f822-200">グループ メンバーの一覧を取得するには、グループの名前、エイリアス、または電子メール アドレスに置き換え、 \<GroupIdentity\> 次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2f822-200">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="2f822-201">構文とパラメーターの詳細については [、「Get-Recipient」](/powershell/module/exchange/get-recipient) および [「Get-DistributionGroupMember」を参照してください](/powershell/module/exchange/get-distributiongroupmember)。</span><span class="sxs-lookup"><span data-stu-id="2f822-201">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="2f822-202">スタンドアロン EOP PowerShell を使用してグループを作成する</span><span class="sxs-lookup"><span data-stu-id="2f822-202">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="2f822-203">スタンドアロン EOP PowerShell で配布グループまたはメールが有効なセキュリティ グループを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="2f822-203">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="2f822-204">**注**:</span><span class="sxs-lookup"><span data-stu-id="2f822-204">**Notes**:</span></span>

- <span data-ttu-id="2f822-205">_Name パラメーター_ は必須で、最大長は 64 文字で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f822-205">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="2f822-206">DisplayName パラメーターを使用しない場合は _、Name_ パラメーターの値が表示名に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f822-206">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="2f822-207">Alias パラメーターを使用しない場合は、 _エイリアス_ 値に _Name_ パラメーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f822-207">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="2f822-208">スペースは削除されます。サポートされていない文字は疑問符 (?) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="2f822-208">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="2f822-209">_PrimarySmtpAddress_ パラメーターを使用しない場合は _、PrimarySmtpAddress_ パラメーターでエイリアス値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f822-209">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="2f822-210">Type パラメーターを使用しない場合 _、既定値_ は Distribution です。</span><span class="sxs-lookup"><span data-stu-id="2f822-210">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="2f822-211">次の使用例は、指定したプロパティを持つ IT Administrators という名前の配布グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f822-211">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="2f822-212">構文とパラメーターの詳細については [、「New-EOPDistributionGroup」を参照してください](/powershell/module/exchange/New-EOPDistributionGroup)。</span><span class="sxs-lookup"><span data-stu-id="2f822-212">For detailed syntax and parameter information, see [New-EOPDistributionGroup](/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="2f822-213">スタンドアロン EOP PowerShell を使用してグループを変更する</span><span class="sxs-lookup"><span data-stu-id="2f822-213">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="2f822-214">スタンドアロン EOP PowerShell のグループを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="2f822-214">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="2f822-215">この例では、Seattle Employees グループのプライマリ SMTP アドレス (返信アドレスとも呼ばれる) を変更して、sea.employees@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="2f822-215">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="2f822-216">この例では、セキュリティ チーム グループの現在のメンバーを Kitty Petersen および Tyson Fawcett に置き換える。</span><span class="sxs-lookup"><span data-stu-id="2f822-216">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="2f822-217">この例では、グループの現在のメンバーを保持しながら、Tyson Fawcett という名前の新しいユーザーを Security Team という名前のグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="2f822-217">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="2f822-218">構文とパラメーターの詳細については [、「Set-EOPDistributionGroup」](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) および [「Update-EOPDistributionGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)。</span><span class="sxs-lookup"><span data-stu-id="2f822-218">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="2f822-219">リモート サーバーを使用してグループを削除Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f822-219">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="2f822-220">この例では、IT 管理者という名前の配布グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="2f822-220">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="2f822-221">構文とパラメーターの詳細については [、「Remove-EOPDistributionGroup」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)。</span><span class="sxs-lookup"><span data-stu-id="2f822-221">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="2f822-222">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="2f822-222">How do you know these procedures worked?</span></span>

<span data-ttu-id="2f822-223">配布グループまたはメールが有効なセキュリティ グループを正常に作成、変更、または削除されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2f822-223">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="2f822-224">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="2f822-224">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="2f822-225">グループが一覧表示 (またはリストされていない) を確認し、[グループの種類] の値 **を確認** します。</span><span class="sxs-lookup"><span data-stu-id="2f822-225">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="2f822-226">グループを選択し、[詳細] ウィンドウで情報を表示するか、[ **編集]** アイコンをクリックして設定 ![ ](../../media/ITPro-EAC-AddIcon.png) を表示します。</span><span class="sxs-lookup"><span data-stu-id="2f822-226">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="2f822-227">スタンドアロンの EOP PowerShell で、次のコマンドを実行して、グループが一覧表示 (または一覧に表示されていない) を確認します。</span><span class="sxs-lookup"><span data-stu-id="2f822-227">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="2f822-228">グループの名前、エイリアス、または電子メール アドレスに置き換え、次のコマンドを実行して設定 \<GroupIdentity\> を確認します。</span><span class="sxs-lookup"><span data-stu-id="2f822-228">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="2f822-229">グループ メンバーを表示するには、グループの名前、エイリアス、または電子メール アドレスに置き換え、 \<GroupIdentity\> 次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2f822-229">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```