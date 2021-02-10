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
description: スタンドアロンの Exchange Online Protection (EOP) 組織の管理者は、Exchange 管理センター (EAC) とスタンドアロンの Exchange Online Protection (EOP) PowerShell で配布グループとメールが有効なセキュリティ グループを作成、変更、削除する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01fe5c6ab1555749d38f9c092b05aca9befb67fe
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166965"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="301bd-103">EOP でグループを管理する</span><span class="sxs-lookup"><span data-stu-id="301bd-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="301bd-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="301bd-104">**Applies to**</span></span>
-  [<span data-ttu-id="301bd-105">Exchange Online Protection スタンドアロン</span><span class="sxs-lookup"><span data-stu-id="301bd-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="301bd-106">Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、次の種類のグループを作成、変更、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="301bd-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="301bd-107">**配布グループ**: メール ユーザーまたは他の配布グループのコレクション。</span><span class="sxs-lookup"><span data-stu-id="301bd-107">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="301bd-108">たとえば、関心のある共通領域でメールを受信または送信する必要があるチームや他の臨時グループなどです。</span><span class="sxs-lookup"><span data-stu-id="301bd-108">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="301bd-109">配布グループは電子メール メッセージの配布専用であり、セキュリティ プリンシパルではありません (アクセス許可を割り当てすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="301bd-109">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="301bd-110">**メールが有効なセキュリティ グループ**: 管理者ロールのアクセス許可を必要とするメール ユーザーおよび他のセキュリティ グループのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="301bd-110">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="301bd-111">たとえば、特定のユーザー グループに管理者アクセス許可を付与して、スパム対策とマルウェア対策の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="301bd-111">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="301bd-112">既定では、新しいメールが有効なセキュリティ グループは、外部 (認証されていない) 送信者からのメッセージを拒否します。</span><span class="sxs-lookup"><span data-stu-id="301bd-112">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="301bd-113">メールが有効なセキュリティ グループには配布グループを追加しません。</span><span class="sxs-lookup"><span data-stu-id="301bd-113">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="301bd-114">グループは、Exchange 管理センター (EAC) とスタンドアロンの EOP PowerShell で管理できます。</span><span class="sxs-lookup"><span data-stu-id="301bd-114">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="301bd-115">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="301bd-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="301bd-116">Exchange 管理センターを開く方法については、 [スタンドアロン EOP の Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="301bd-116">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="301bd-117">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="301bd-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="301bd-118">スタンドアロンの EOP PowerShell でグループを管理すると、調整が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="301bd-118">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="301bd-119">この記事の PowerShell の手順では、コマンドの結果が表示される数分前に伝達遅延が発生するバッチ処理方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="301bd-119">The PowerShell procedures in this article use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="301bd-120">この記事の手順を実行する前に、Exchange Online Protection でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="301bd-120">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="301bd-121">具体的には、"Organization **Management/** 組織の管理" 役割グループと **"Recipient Management/** 受信者の管理" 役割グループに既定で割り当てられる **"Distribution Groups/** 配布グループ" 役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="301bd-121">Specifically, you need the **Distribution Groups** role, which is assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="301bd-122">詳細については、「スタンドアロン [EOP のアクセス許可](feature-permissions-in-eop.md) 」および「EAC を使用して役割グループのメンバーの一覧 [を変更する」を参照してください](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="301bd-122">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="301bd-123">この記事の手順に適用できるキーボード ショートカットの詳細については [、Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)の Exchange 管理センターのキーボード ショートカットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="301bd-123">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="301bd-124">問題が発生する場合</span><span class="sxs-lookup"><span data-stu-id="301bd-124">Having problems?</span></span> <span data-ttu-id="301bd-125">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) フォーラムでサポートをご依頼ください。</span><span class="sxs-lookup"><span data-stu-id="301bd-125">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="301bd-126">Exchange 管理センターを使用して配布グループを管理する</span><span class="sxs-lookup"><span data-stu-id="301bd-126">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="301bd-127">EAC を使用してグループを作成する</span><span class="sxs-lookup"><span data-stu-id="301bd-127">Use the EAC to create groups</span></span>

1. <span data-ttu-id="301bd-128">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="301bd-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="301bd-129">[ **新しい新規** ![ ] ](../../media/ITPro-EAC-AddIcon.png) アイコンをクリックし、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="301bd-129">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="301bd-130">**配布グループ**</span><span class="sxs-lookup"><span data-stu-id="301bd-130">**Distribution group**</span></span>

   - <span data-ttu-id="301bd-131">**メールが有効なセキュリティ グループ**</span><span class="sxs-lookup"><span data-stu-id="301bd-131">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="301bd-132">開く新しいグループ ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="301bd-132">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="301bd-133">an が付いている設定 <sup>\*</sup> は必須です。</span><span class="sxs-lookup"><span data-stu-id="301bd-133">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="301bd-134"><sup>\*</sup>**表示名**: この名前は、組織のアドレス帳、このグループに電子メールが送信される際の [To:] 行、および EAC の **[グループ** ] リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="301bd-134"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="301bd-135">表示名は必須であり、一意である必要があります。また、ユーザーが何を認識しているかはユーザーに分かっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="301bd-135">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="301bd-136"><sup>\*</sup>**[エイリアス**]: このボックスを使用して、グループのエイリアスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="301bd-136"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="301bd-137">エイリアスは 64 文字以内で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="301bd-137">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="301bd-138">ユーザーが電子メール メッセージの [To] 行にエイリアスを入力すると、グループの表示名に解決されます。</span><span class="sxs-lookup"><span data-stu-id="301bd-138">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="301bd-139"><sup>\*</sup>**電子メール** アドレス : 電子メール アドレスは、at (@) 記号の左側のエイリアスと右側のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="301bd-139"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="301bd-140">既定では、エイリアス **の値は** エイリアス値に使用されますが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="301bd-140">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="301bd-141">ドメイン値の場合は、ドロップダウンをクリックし、組織内のドメインを選択して承認します。</span><span class="sxs-lookup"><span data-stu-id="301bd-141">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="301bd-142">**説明**: この説明は、アドレス帳と EAC の [詳細] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="301bd-142">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="301bd-143"><sup>\*</sup>**所有者**: グループ所有者はグループ メンバーシップを管理できます。</span><span class="sxs-lookup"><span data-stu-id="301bd-143"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="301bd-144">既定では、グループを作成するユーザーがグループの所有者になります。</span><span class="sxs-lookup"><span data-stu-id="301bd-144">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="301bd-145">グループには、最低 1 人の所有者が必要です。</span><span class="sxs-lookup"><span data-stu-id="301bd-145">All groups must have at least one owner.</span></span>

     <span data-ttu-id="301bd-146">所有者を追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="301bd-146">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="301bd-147">表示されるダイアログで、受信者またはグループを検索して選択し、[追加] **->。**</span><span class="sxs-lookup"><span data-stu-id="301bd-147">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="301bd-148">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="301bd-148">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="301bd-149">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="301bd-149">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="301bd-150">所有者を削除するには、所有者を選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="301bd-150">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="301bd-151">**メンバー**: グループ メンバーを追加および削除します。</span><span class="sxs-lookup"><span data-stu-id="301bd-151">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="301bd-152">メンバーを追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="301bd-152">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="301bd-153">表示されるダイアログで、受信者またはグループを検索して選択し、[追加] **->。**</span><span class="sxs-lookup"><span data-stu-id="301bd-153">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="301bd-154">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="301bd-154">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="301bd-155">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="301bd-155">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="301bd-156">メンバーを削除するには、メンバーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="301bd-156">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="301bd-157">完了したら、[保存] をクリック **して** 配布グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="301bd-157">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="301bd-158">EAC を使用して配布グループを変更する</span><span class="sxs-lookup"><span data-stu-id="301bd-158">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="301bd-159">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="301bd-159">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="301bd-160">グループの一覧で、変更する配布グループまたはメールが有効なセキュリティ グループを選択し、[編集] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="301bd-160">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="301bd-161">表示された配布グループのプロパティ ページで、次のいずれかのタブをクリックしてプロパティを表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="301bd-161">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="301bd-162">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="301bd-162">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="301bd-163">全般</span><span class="sxs-lookup"><span data-stu-id="301bd-163">General</span></span>

<span data-ttu-id="301bd-164">このタブを使用して、グループに関する基本情報を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="301bd-164">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="301bd-165">**表示名**: この名前は、アドレス帳、このグループにメールが送信される際の [To] 行、および [グループ] リストに **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="301bd-165">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="301bd-166">表示名は必須であり、ユーザーが内容を認識できるようにわかりやすい名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="301bd-166">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="301bd-167">また、表示名は、ドメイン内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="301bd-167">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="301bd-168">グループの名前付けポリシーを実装している場合、表示名は、ポリシーで定義されている名前付け形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="301bd-168">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="301bd-169">**エイリアス**: 電子メール アドレスの @ 記号の左側に表示される部分です。</span><span class="sxs-lookup"><span data-stu-id="301bd-169">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="301bd-170">エイリアスを変更すると、グループのプライマリ SMTP アドレスも変更され、新しいエイリアスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="301bd-170">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="301bd-171">また、以前のエイリアスが含まれている電子メール アドレスは、グループのプロキシ アドレスとして保持されます。</span><span class="sxs-lookup"><span data-stu-id="301bd-171">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="301bd-172">**電子メール** アドレス : 電子メール アドレスは、at (@) 記号の左側のエイリアスと右側のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="301bd-172">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="301bd-173">既定では、エイリアス **の値は** エイリアス値に使用されますが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="301bd-173">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="301bd-174">ドメイン値の場合は、ドロップダウンをクリックし、組織内のドメインを選択して承認します。</span><span class="sxs-lookup"><span data-stu-id="301bd-174">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="301bd-175">**説明**: この説明は、アドレス帳と EAC の [詳細] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="301bd-175">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="301bd-176">Ownership</span><span class="sxs-lookup"><span data-stu-id="301bd-176">Ownership</span></span>

<span data-ttu-id="301bd-177">グループの所有者を割り当てるには、このタブを使用します。</span><span class="sxs-lookup"><span data-stu-id="301bd-177">Use this tab to assign group owners.</span></span> <span data-ttu-id="301bd-178">グループ所有者はグループ メンバーシップを管理できます。</span><span class="sxs-lookup"><span data-stu-id="301bd-178">A group owner can manage group membership.</span></span> <span data-ttu-id="301bd-179">既定では、グループを作成するユーザーがグループの所有者になります。</span><span class="sxs-lookup"><span data-stu-id="301bd-179">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="301bd-180">グループには、最低 1 人の所有者が必要です。</span><span class="sxs-lookup"><span data-stu-id="301bd-180">All groups must have at least one owner.</span></span>

<span data-ttu-id="301bd-181">所有者を追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="301bd-181">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="301bd-182">表示されるダイアログで、受信者を見つけて選択し、[追加] **->。**</span><span class="sxs-lookup"><span data-stu-id="301bd-182">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="301bd-183">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="301bd-183">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="301bd-184">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="301bd-184">When you're finished, click **OK**.</span></span>

<span data-ttu-id="301bd-185">所有者を削除するには、所有者を選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="301bd-185">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="301bd-186">メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="301bd-186">Membership</span></span>

<span data-ttu-id="301bd-187">グループ メンバーを追加または削除するには、このタブを使用します。</span><span class="sxs-lookup"><span data-stu-id="301bd-187">Use this tab to add or remove group members.</span></span> <span data-ttu-id="301bd-188">グループの所有者は、グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="301bd-188">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="301bd-189">メンバーを追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="301bd-189">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="301bd-190">表示されるダイアログで、受信者またはグループを検索して選択し、[追加] **->。**</span><span class="sxs-lookup"><span data-stu-id="301bd-190">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="301bd-191">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="301bd-191">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="301bd-192">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="301bd-192">When you're finished, click **OK**.</span></span>

<span data-ttu-id="301bd-193">メンバーを削除するには、メンバーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="301bd-193">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="301bd-194">EAC を使用してグループを削除する</span><span class="sxs-lookup"><span data-stu-id="301bd-194">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="301bd-195">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="301bd-195">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="301bd-196">グループの一覧で、削除する配布グループを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="301bd-196">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="301bd-197">PowerShell を使用してグループを管理する</span><span class="sxs-lookup"><span data-stu-id="301bd-197">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="301bd-198">スタンドアロンの EOP PowerShell を使用してグループを表示する</span><span class="sxs-lookup"><span data-stu-id="301bd-198">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="301bd-199">スタンドアロンの EOP PowerShell ですべての配布グループとメールが有効なセキュリティ グループの要約リストを返す場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="301bd-199">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="301bd-200">グループ メンバーの一覧を返す場合は、グループの名前、エイリアス、または電子メール アドレスに置き換え、次の \<GroupIdentity\> コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="301bd-200">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="301bd-201">構文およびパラメーターの詳細については [、「Get-Recipient」](https://docs.microsoft.com/powershell/module/exchange/get-recipient) および [「Get-DistributionGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)。</span><span class="sxs-lookup"><span data-stu-id="301bd-201">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="301bd-202">スタンドアロンの EOP PowerShell を使用してグループを作成する</span><span class="sxs-lookup"><span data-stu-id="301bd-202">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="301bd-203">スタンドアロンの EOP PowerShell で配布グループまたはメールが有効なセキュリティ グループを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="301bd-203">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="301bd-204">**注**:</span><span class="sxs-lookup"><span data-stu-id="301bd-204">**Notes**:</span></span>

- <span data-ttu-id="301bd-205">_Name パラメーター_ は必須で、最大長は 64 文字で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="301bd-205">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="301bd-206">_DisplayName_ パラメーターを使用しない場合 _、Name_ パラメーターの値が表示名に使用されます。</span><span class="sxs-lookup"><span data-stu-id="301bd-206">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="301bd-207">Alias パラメーターを使用しない場合は、 _エイリアス_ 値に _Name_ パラメーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="301bd-207">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="301bd-208">スペースは削除されます。サポートされていない文字は疑問符 (?) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="301bd-208">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="301bd-209">_PrimarySmtpAddress_ パラメーターを使用しない場合は _、PrimarySmtpAddress_ パラメーターでエイリアス値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="301bd-209">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="301bd-210">_Type_ パラメーターを使用しない場合、既定値は Distribution です。</span><span class="sxs-lookup"><span data-stu-id="301bd-210">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="301bd-211">この例では、指定されたプロパティを持つ IT Administrators という名前の配布グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="301bd-211">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="301bd-212">構文およびパラメーターの詳細については [、「New-EOPDistributionGroup」を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)。</span><span class="sxs-lookup"><span data-stu-id="301bd-212">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="301bd-213">スタンドアロンの EOP PowerShell を使用してグループを変更する</span><span class="sxs-lookup"><span data-stu-id="301bd-213">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="301bd-214">スタンドアロンの EOP PowerShell でグループを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="301bd-214">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="301bd-215">この例では、Seattle Employees グループのプライマリ SMTP アドレス (返信アドレスとも呼ばれる) を使用して、sea.employees@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="301bd-215">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="301bd-216">この例では、Security Team グループの現在のメンバーを Kitty Petersen と Tyson Fawcett に置き換える。</span><span class="sxs-lookup"><span data-stu-id="301bd-216">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="301bd-217">この例では、グループの現在のメンバーを保持しながら、Tyson Fawcett という名前の新しいユーザーを Security Team という名前のグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="301bd-217">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="301bd-218">構文およびパラメーターの詳細については[、「Set-EOPDistributionGroup」および](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup)[「Update-EOPDistributionGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)。</span><span class="sxs-lookup"><span data-stu-id="301bd-218">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="301bd-219">リモート デバイスを使用してグループを削除Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="301bd-219">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="301bd-220">この例では、IT Administrators という名前の配布グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="301bd-220">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="301bd-221">構文およびパラメーターの詳細については [、「Remove-EOPDistributionGroup」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)。</span><span class="sxs-lookup"><span data-stu-id="301bd-221">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="301bd-222">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="301bd-222">How do you know these procedures worked?</span></span>

<span data-ttu-id="301bd-223">配布グループまたはメールが有効なセキュリティ グループが正常に作成、変更、または削除されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="301bd-223">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="301bd-224">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="301bd-224">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="301bd-225">グループが一覧に表示されている (または一覧に表示されていない) か確認し、グループの種類の **値を確認** します。</span><span class="sxs-lookup"><span data-stu-id="301bd-225">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="301bd-226">グループを選択して詳細ウィンドウに情報を表示するか、[編集]アイコンをクリックして ![ ](../../media/ITPro-EAC-AddIcon.png) 設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="301bd-226">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="301bd-227">スタンドアロンの EOP PowerShell で、次のコマンドを実行して、グループが一覧に表示されている (または一覧に表示されていない) か確認します。</span><span class="sxs-lookup"><span data-stu-id="301bd-227">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="301bd-228">グループの名前、エイリアス、または電子メール アドレスに置き換え、次のコマンドを実行して \<GroupIdentity\> 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="301bd-228">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="301bd-229">グループ メンバーを表示するには、グループの名前、エイリアス、または電子メール アドレスに置き換え、次 \<GroupIdentity\> のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="301bd-229">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
