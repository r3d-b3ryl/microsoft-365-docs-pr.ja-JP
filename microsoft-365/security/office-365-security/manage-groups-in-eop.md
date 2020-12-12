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
description: スタンドアロンの Exchange Online Protection (EOP) 組織の管理者は、Exchange 管理センター (EAC) とスタンドアロンの Exchange Online Protection (EOP) PowerShell で配布グループとメールが有効なセキュリティ グループを作成、変更、削除する方法について説明します。
ms.openlocfilehash: 5ff7c61d51ded039b06d1faa98ba6390939b3413
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658847"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="50d13-103">EOP でグループを管理する</span><span class="sxs-lookup"><span data-stu-id="50d13-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="50d13-104">Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、次の種類のグループを作成、変更、削除できます。</span><span class="sxs-lookup"><span data-stu-id="50d13-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="50d13-105">**配布グループ**: メール ユーザーまたは他の配布グループのコレクション。</span><span class="sxs-lookup"><span data-stu-id="50d13-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="50d13-106">たとえば、関心のある共通領域でメールを受信または送信する必要があるチームや他の臨時グループ。</span><span class="sxs-lookup"><span data-stu-id="50d13-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="50d13-107">配布グループは電子メール メッセージの配布専用であり、セキュリティ プリンシパルではありません (アクセス許可を割り当てすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="50d13-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="50d13-108">**メールが有効なセキュリティ グループ**: 管理者ロールのアクセス許可を必要とするメール ユーザーおよび他のセキュリティ グループのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="50d13-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="50d13-109">たとえば、特定のユーザー グループに管理者アクセス許可を付与して、スパム対策とマルウェア対策の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="50d13-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="50d13-110">既定では、新しいメールが有効なセキュリティ グループは、外部 (認証されていない) 送信者からのメッセージを拒否します。</span><span class="sxs-lookup"><span data-stu-id="50d13-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="50d13-111">メールが有効なセキュリティ グループには配布グループを追加しません。</span><span class="sxs-lookup"><span data-stu-id="50d13-111">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="50d13-112">グループは、Exchange 管理センター (EAC) とスタンドアロンの EOP PowerShell で管理できます。</span><span class="sxs-lookup"><span data-stu-id="50d13-112">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="50d13-113">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="50d13-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="50d13-114">Exchange 管理センターを開く方法については、 [スタンドアロン EOP の Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="50d13-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="50d13-115">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50d13-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="50d13-116">スタンドアロンの EOP PowerShell でグループを管理すると、調整が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="50d13-116">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="50d13-117">この記事の PowerShell の手順では、バッチ処理方法を使用します。この方法では、コマンドの結果が表示される数分前に伝達遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="50d13-117">The PowerShell procedures in this article use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="50d13-118">この記事の手順を実行する前に、Exchange Online Protection でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d13-118">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="50d13-119">具体的には、"Organization **Management/** 組織の管理" 役割グループと **"Recipient Management/** 受信者の管理" 役割グループに既定で割り当てられる **"Distribution Groups/** 配布グループ" 役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="50d13-119">Specifically, you need the **Distribution Groups** role, which is assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="50d13-120">詳細については、「スタンドアロン [EOP のアクセス](feature-permissions-in-eop.md) 許可」および「EAC を使用して役割グループのメンバーの一覧 [を変更する」を参照してください](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="50d13-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="50d13-121">この記事の手順に適用できるキーボード ショートカットの詳細については [、Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)の Exchange 管理センターのキーボード ショートカットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="50d13-121">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="50d13-122">問題が発生する場合</span><span class="sxs-lookup"><span data-stu-id="50d13-122">Having problems?</span></span> <span data-ttu-id="50d13-123">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) フォーラムでサポートをご依頼ください。</span><span class="sxs-lookup"><span data-stu-id="50d13-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="50d13-124">Exchange 管理センターを使用して配布グループを管理する</span><span class="sxs-lookup"><span data-stu-id="50d13-124">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="50d13-125">EAC を使用してグループを作成する</span><span class="sxs-lookup"><span data-stu-id="50d13-125">Use the EAC to create groups</span></span>

1. <span data-ttu-id="50d13-126">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="50d13-126">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="50d13-127">[ **新しい新規** ![ ] ](../../media/ITPro-EAC-AddIcon.png) アイコンをクリックし、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="50d13-127">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="50d13-128">**配布グループ**</span><span class="sxs-lookup"><span data-stu-id="50d13-128">**Distribution group**</span></span>

   - <span data-ttu-id="50d13-129">**メールが有効なセキュリティ グループ**</span><span class="sxs-lookup"><span data-stu-id="50d13-129">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="50d13-130">開く新しいグループ ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="50d13-130">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="50d13-131">an が付いている設定 <sup>\*</sup> は必須です。</span><span class="sxs-lookup"><span data-stu-id="50d13-131">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="50d13-132"><sup>\*</sup>**表示名**: この名前は、組織のアドレス帳、このグループに電子メールが送信される際の [To:] 行、および EAC の **[グループ** ] リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="50d13-132"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="50d13-133">表示名は必須であり、一意である必要があります。また、ユーザーが何を認識しているかはユーザーに分かっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d13-133">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="50d13-134"><sup>\*</sup>**[エイリアス**]: このボックスを使用して、グループのエイリアスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="50d13-134"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="50d13-135">エイリアスは 64 文字以内で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d13-135">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="50d13-136">ユーザーが電子メール メッセージの [To] 行にエイリアスを入力すると、グループの表示名に解決されます。</span><span class="sxs-lookup"><span data-stu-id="50d13-136">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="50d13-137"><sup>\*</sup>**電子メール** アドレス : 電子メール アドレスは、at (@) 記号の左側のエイリアスと右側のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="50d13-137"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="50d13-138">既定では、エイリアス **の値は** エイリアス値に使用されますが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="50d13-138">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="50d13-139">ドメイン値の場合は、ドロップダウンをクリックし、組織内のドメインを選択して承認します。</span><span class="sxs-lookup"><span data-stu-id="50d13-139">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="50d13-140">**説明**: この説明は、アドレス帳と EAC の [詳細] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="50d13-140">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="50d13-141"><sup>\*</sup>**所有者**: グループ所有者はグループ メンバーシップを管理できます。</span><span class="sxs-lookup"><span data-stu-id="50d13-141"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="50d13-142">既定では、グループを作成するユーザーがグループの所有者になります。</span><span class="sxs-lookup"><span data-stu-id="50d13-142">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="50d13-143">グループには、最低 1 人の所有者が必要です。</span><span class="sxs-lookup"><span data-stu-id="50d13-143">All groups must have at least one owner.</span></span>

     <span data-ttu-id="50d13-144">所有者を追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="50d13-144">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="50d13-145">表示されるダイアログで、受信者またはグループを検索して選択し、[追加] **->。**</span><span class="sxs-lookup"><span data-stu-id="50d13-145">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="50d13-146">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="50d13-146">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="50d13-147">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50d13-147">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="50d13-148">所有者を削除するには、所有者を選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="50d13-148">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="50d13-149">**メンバー**: グループ メンバーを追加および削除します。</span><span class="sxs-lookup"><span data-stu-id="50d13-149">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="50d13-150">メンバーを追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="50d13-150">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="50d13-151">表示されるダイアログで、受信者またはグループを検索して選択し、[追加] **->。**</span><span class="sxs-lookup"><span data-stu-id="50d13-151">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="50d13-152">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="50d13-152">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="50d13-153">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50d13-153">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="50d13-154">メンバーを削除するには、メンバーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="50d13-154">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="50d13-155">完了したら、[保存] をクリック **して** 配布グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="50d13-155">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="50d13-156">EAC を使用して配布グループを変更する</span><span class="sxs-lookup"><span data-stu-id="50d13-156">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="50d13-157">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="50d13-157">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="50d13-158">グループの一覧で、変更する配布グループまたはメールが有効なセキュリティ グループを選択し、[編集] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="50d13-158">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="50d13-159">表示された配布グループのプロパティ ページで、次のいずれかのタブをクリックしてプロパティを表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="50d13-159">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="50d13-160">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50d13-160">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="50d13-161">全般</span><span class="sxs-lookup"><span data-stu-id="50d13-161">General</span></span>

<span data-ttu-id="50d13-162">このタブを使用して、グループに関する基本情報を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="50d13-162">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="50d13-163">**表示名**: この名前は、アドレス帳、このグループにメールが送信される際の [To] 行、および [グループ] リストに **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="50d13-163">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="50d13-164">表示名は必須であり、ユーザーが内容を認識できるようにわかりやすい名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d13-164">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="50d13-165">また、表示名は、ドメイン内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d13-165">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="50d13-166">グループの名前付けポリシーを実装している場合、表示名は、ポリシーで定義されている名前付け形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d13-166">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="50d13-167">**エイリアス**: 電子メール アドレスの @ 記号の左側に表示される部分です。</span><span class="sxs-lookup"><span data-stu-id="50d13-167">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="50d13-168">エイリアスを変更すると、グループのプライマリ SMTP アドレスも変更され、新しいエイリアスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="50d13-168">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="50d13-169">また、以前のエイリアスが含まれている電子メール アドレスは、グループのプロキシ アドレスとして保持されます。</span><span class="sxs-lookup"><span data-stu-id="50d13-169">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="50d13-170">**電子メール** アドレス : 電子メール アドレスは、at (@) 記号の左側のエイリアスと右側のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="50d13-170">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="50d13-171">既定では、エイリアス **の値は** エイリアス値に使用されますが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="50d13-171">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="50d13-172">ドメイン値の場合は、ドロップダウンをクリックし、組織内のドメインを選択して承認します。</span><span class="sxs-lookup"><span data-stu-id="50d13-172">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="50d13-173">**説明**: この説明は、アドレス帳と EAC の [詳細] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="50d13-173">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="50d13-174">Ownership</span><span class="sxs-lookup"><span data-stu-id="50d13-174">Ownership</span></span>

<span data-ttu-id="50d13-175">グループの所有者を割り当てるには、このタブを使用します。</span><span class="sxs-lookup"><span data-stu-id="50d13-175">Use this tab to assign group owners.</span></span> <span data-ttu-id="50d13-176">グループ所有者はグループ メンバーシップを管理できます。</span><span class="sxs-lookup"><span data-stu-id="50d13-176">A group owner can manage group membership.</span></span> <span data-ttu-id="50d13-177">既定では、グループを作成するユーザーがグループの所有者になります。</span><span class="sxs-lookup"><span data-stu-id="50d13-177">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="50d13-178">グループには、最低 1 人の所有者が必要です。</span><span class="sxs-lookup"><span data-stu-id="50d13-178">All groups must have at least one owner.</span></span>

<span data-ttu-id="50d13-179">所有者を追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="50d13-179">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="50d13-180">表示されるダイアログで、受信者を見つけて選択し、[追加] **->。**</span><span class="sxs-lookup"><span data-stu-id="50d13-180">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="50d13-181">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="50d13-181">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="50d13-182">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50d13-182">When you're finished, click **OK**.</span></span>

<span data-ttu-id="50d13-183">所有者を削除するには、所有者を選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="50d13-183">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="50d13-184">メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="50d13-184">Membership</span></span>

<span data-ttu-id="50d13-185">グループ メンバーを追加または削除するには、このタブを使用します。</span><span class="sxs-lookup"><span data-stu-id="50d13-185">Use this tab to add or remove group members.</span></span> <span data-ttu-id="50d13-186">グループの所有者は、グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d13-186">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="50d13-187">メンバーを追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="50d13-187">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="50d13-188">表示されるダイアログで、受信者またはグループを検索して選択し、[追加] **->。**</span><span class="sxs-lookup"><span data-stu-id="50d13-188">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="50d13-189">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="50d13-189">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="50d13-190">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50d13-190">When you're finished, click **OK**.</span></span>

<span data-ttu-id="50d13-191">メンバーを削除するには、メンバーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="50d13-191">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="50d13-192">EAC を使用してグループを削除する</span><span class="sxs-lookup"><span data-stu-id="50d13-192">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="50d13-193">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="50d13-193">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="50d13-194">グループの一覧で、削除する配布グループを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="50d13-194">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="50d13-195">PowerShell を使用してグループを管理する</span><span class="sxs-lookup"><span data-stu-id="50d13-195">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="50d13-196">スタンドアロンの EOP PowerShell を使用してグループを表示する</span><span class="sxs-lookup"><span data-stu-id="50d13-196">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="50d13-197">スタンドアロンの EOP PowerShell ですべての配布グループとメールが有効なセキュリティ グループの要約リストを返す場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="50d13-197">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="50d13-198">グループ メンバーの一覧を返す場合は、グループの名前、エイリアス、または電子メール アドレスに置き換え、次の \<GroupIdentity\> コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="50d13-198">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="50d13-199">構文およびパラメーターの詳細については [、「Get-Recipient」](https://docs.microsoft.com/powershell/module/exchange/get-recipient) および [「Get-DistributionGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)。</span><span class="sxs-lookup"><span data-stu-id="50d13-199">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="50d13-200">スタンドアロンの EOP PowerShell を使用してグループを作成する</span><span class="sxs-lookup"><span data-stu-id="50d13-200">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="50d13-201">スタンドアロンの EOP PowerShell で配布グループまたはメールが有効なセキュリティ グループを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="50d13-201">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="50d13-202">**注**:</span><span class="sxs-lookup"><span data-stu-id="50d13-202">**Notes**:</span></span>

- <span data-ttu-id="50d13-203">Name _パラメーター_ は必須で、最大長は 64 文字で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d13-203">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="50d13-204">_DisplayName_ パラメーターを使用しない場合 _、Name_ パラメーターの値が表示名に使用されます。</span><span class="sxs-lookup"><span data-stu-id="50d13-204">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="50d13-205">_Alias_ パラメーターを使用しない場合は、エイリアス値に _Name_ パラメーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="50d13-205">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="50d13-206">スペースは削除されます。サポートされていない文字は疑問符 (?) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="50d13-206">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="50d13-207">_PrimarySmtpAddress_ パラメーターを使用しない場合は _、PrimarySmtpAddress_ パラメーターでエイリアス値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="50d13-207">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="50d13-208">_Type_ パラメーターを使用しない場合、既定値は Distribution です。</span><span class="sxs-lookup"><span data-stu-id="50d13-208">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="50d13-209">この例では、指定したプロパティを持つ IT Administrators という名前の配布グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="50d13-209">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="50d13-210">構文およびパラメーターの詳細については [、「New-EOPDistributionGroup」を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)。</span><span class="sxs-lookup"><span data-stu-id="50d13-210">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="50d13-211">スタンドアロンの EOP PowerShell を使用してグループを変更する</span><span class="sxs-lookup"><span data-stu-id="50d13-211">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="50d13-212">スタンドアロンの EOP PowerShell でグループを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="50d13-212">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="50d13-213">この例では、Seattle Employees グループのプライマリ SMTP アドレス (返信アドレスとも呼ばれる) を使用して、sea.employees@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="50d13-213">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="50d13-214">この例では、Security Team グループの現在のメンバーを Kitty Petersen と Tyson Fawcett に置き換える。</span><span class="sxs-lookup"><span data-stu-id="50d13-214">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="50d13-215">この例では、グループの現在のメンバーを保持しながら、Tyson Fawcett という名前の新しいユーザーを Security Team という名前のグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="50d13-215">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="50d13-216">構文およびパラメーターの詳細については[、「Set-EOPDistributionGroup」および](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup)[「Update-EOPDistributionGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)。</span><span class="sxs-lookup"><span data-stu-id="50d13-216">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="50d13-217">リモート デバイスを使用してグループを削除Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="50d13-217">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="50d13-218">この例では、IT Administrators という名前の配布グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="50d13-218">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="50d13-219">構文およびパラメーターの詳細については [、「Remove-EOPDistributionGroup」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)。</span><span class="sxs-lookup"><span data-stu-id="50d13-219">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="50d13-220">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="50d13-220">How do you know these procedures worked?</span></span>

<span data-ttu-id="50d13-221">配布グループまたはメールが有効なセキュリティ グループが正常に作成、変更、または削除されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="50d13-221">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="50d13-222">EAC で、 **[受信者]** \> **[グループ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="50d13-222">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="50d13-223">グループが一覧に表示されている (または一覧に表示されていない) か確認し、グループの種類の **値を確認** します。</span><span class="sxs-lookup"><span data-stu-id="50d13-223">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="50d13-224">グループを選択し、[詳細] ウィンドウに情報を表示するか、[編集] アイコンをクリックして ![ ](../../media/ITPro-EAC-AddIcon.png) 設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="50d13-224">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="50d13-225">スタンドアロンの EOP PowerShell で、次のコマンドを実行して、グループが一覧に表示されている (または一覧に表示されていない) か確認します。</span><span class="sxs-lookup"><span data-stu-id="50d13-225">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="50d13-226">グループの名前、エイリアス、または電子メール アドレスに置き換え、次のコマンドを実行して \<GroupIdentity\> 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="50d13-226">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="50d13-227">グループ メンバーを表示するには、グループの名前、エイリアス、または電子メール アドレスに置き換え、次 \<GroupIdentity\> のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="50d13-227">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
