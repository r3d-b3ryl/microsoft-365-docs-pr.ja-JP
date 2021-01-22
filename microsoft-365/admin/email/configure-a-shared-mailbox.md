---
title: 共有メールボックスの設定を構成する
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスを作成したら、メールの転送や自動返信など、ユーザーに対していくつかの設定を構成する必要があります。 後で、メールボックス名やメンバーなど、他の設定を変更することもできます。
ms.openlocfilehash: fe5d35be556b8edf5456bc2c0b820dc0ce77e323
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926608"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="df8d4-104">共有メールボックスの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="df8d4-104">Configure shared mailbox settings</span></span>

<span data-ttu-id="df8d4-105">共有メールボックス [を作成したら](create-a-shared-mailbox.md)、メールの転送や自動応答など、メールボックス ユーザーに対していくつかの設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df8d4-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="df8d4-106">後で、メールボックス名、メンバー、メンバーのアクセス許可など、他の設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="df8d4-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="df8d4-107">共有メールボックスの名前または電子メール エイリアスを変更するか、プライマリ メール アドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="df8d4-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="df8d4-108">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="df8d4-109"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-109">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="df8d4-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-110">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="df8d4-111">編集する共有メールボックスを選択し、[名前、電子メール、電子メール エイリアス] の横にある [編集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="df8d4-111">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="df8d4-112">新しい名前を入力するか、別のエイリアスを追加します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-112">Enter a new name, or add another alias.</span></span> <span data-ttu-id="df8d4-113">プライマリ メール アドレスを変更する場合は、メールボックスに複数の電子メール エイリアスが必要です。</span><span class="sxs-lookup"><span data-stu-id="df8d4-113">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="df8d4-114">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-114">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="df8d4-115">共有メールボックスに送信されたメールを転送する</span><span class="sxs-lookup"><span data-stu-id="df8d4-115">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="df8d4-116">送信されたメールを転送するために、共有メールボックスにライセンスを割り当てる必要はない。</span><span class="sxs-lookup"><span data-stu-id="df8d4-116">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="df8d4-117">メッセージは、有効な電子メール アドレスまたは配布リストに転送できます。</span><span class="sxs-lookup"><span data-stu-id="df8d4-117">You can forward the messages to any valid email address or distribution list.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="df8d4-118">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-118">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="df8d4-119"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="df8d4-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="df8d4-121">編集する共有メールボックスを選択し、[電子メール転送の編集] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="df8d4-121">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="df8d4-122">トグルを **[オン] に設定** し、メッセージの転送先のメール アドレスを 1 つ入力します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-122">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="df8d4-123">任意の有効な電子メール アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="df8d4-123">It can be any valid email address.</span></span> <span data-ttu-id="df8d4-124">複数のアドレスに転送するには、アドレスの[](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists)配布グループを作成し、このボックスにグループの名前を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df8d4-124">To forward to multiple addresses, you need to [create a distribution group](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="df8d4-125">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-125">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="df8d4-126">共有メールボックスから自動応答を送信する</span><span class="sxs-lookup"><span data-stu-id="df8d4-126">Send automatic replies from a shared mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="df8d4-127">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-127">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="df8d4-128"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="df8d4-129"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-129">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="df8d4-130">編集する共有メールボックスを選択し、[自動返信の編集 **] を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="df8d4-130">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="df8d4-131">トグルを **[オン**] に設定し、組織内のユーザーまたは組織外のユーザーに返信を送信するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="df8d4-132">組織内のユーザーに送信する返信を入力します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-132">Enter the reply you want to send to people inside your organization.</span></span> <span data-ttu-id="df8d4-133">画像を追加できるのは、テキストのみです。</span><span class="sxs-lookup"><span data-stu-id="df8d4-133">You can't add images, only text.</span></span>

5. <span data-ttu-id="df8d4-134">組織外 *のユーザーにも* 返信を送信する場合は、返信を受け取るユーザーのチェック ボックスをオンにして、テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-134">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="df8d4-135">組織内のユーザーには送信せず、組織外のユーザーにのみ送信する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="df8d4-135">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="df8d4-136">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-136">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="df8d4-137">送信済みメール (返信) の表示を全員に許可する</span><span class="sxs-lookup"><span data-stu-id="df8d4-137">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="df8d4-p108">既定では、共有メールボックスから送信されたメッセージは、共有メールボックスの [送信済みアイテム] フォルダーには保存されません。代わりに、メッセージを送信したユーザーの [送信済みアイテム] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="df8d4-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="df8d4-140">送信されたメールの表示をすべてのユーザーに許可する場合は、管理センターで共有メールボックスの設定を編集し、[送信されたアイテムの編集] **を選択** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="df8d4-140">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="df8d4-141">共有メールボックスが Microsoft メールへのアクセスに使用できるアプリを選択する</span><span class="sxs-lookup"><span data-stu-id="df8d4-141">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="df8d4-142">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="df8d4-143"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-143">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="df8d4-144"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-144">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="df8d4-145">編集する共有メールボックスを選択し、[メール アプリの編集] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="df8d4-145">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="df8d4-146">メンバーが共有 **メールボックス** にアクセスするために使用できるすべてのアプリのトグルを [オン] に設定します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-146">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="df8d4-147">使用しないアプリのトグルを **[オフ** ] に設定します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-147">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="df8d4-148">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-148">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="df8d4-149">共有メールボックスを訴訟ホールドの対象に設定する</span><span class="sxs-lookup"><span data-stu-id="df8d4-149">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="df8d4-150">訴訟ホールドの詳細については、「訴訟ホールドの作成 [」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)。</span><span class="sxs-lookup"><span data-stu-id="df8d4-150">To learn more about litigation hold, see [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="df8d4-151">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-151">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="df8d4-152"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-152">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="df8d4-153"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="df8d4-154">編集する共有メールボックスを選択し、[訴訟ホールドの編集 **] を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="df8d4-154">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="df8d4-155">トグルをオンに **設定します**。</span><span class="sxs-lookup"><span data-stu-id="df8d4-155">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="df8d4-156">必要に応じて、期間、保留に関するメモ、および詳細を含む URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-156">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="df8d4-157">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-157">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="df8d4-158">メンバーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="df8d4-158">Add or remove members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="df8d4-159">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="df8d4-160"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-160">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="df8d4-161"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-161">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="df8d4-162">編集する共有メールボックスを選択し、[メンバーの編集] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="df8d4-162">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="df8d4-163">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="df8d4-163">Do one of the following:</span></span>
   - <span data-ttu-id="df8d4-164">メンバーを追加するには、[メンバーの追加 **] を** 選択し、追加するメンバーを検索または選択して、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="df8d4-164">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="df8d4-165">メンバーを削除するには、[検索] ボックスを使用して必要に応じてメンバーを検索し、メンバーの名前の横にある **[X]** を選択して、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="df8d4-165">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="df8d4-166">[保存 **] を再び** 選択します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-166">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="df8d4-167">メンバーのアクセス許可を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="df8d4-167">Add or remove permissions of members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="df8d4-168">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-168">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="df8d4-169"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="df8d4-170"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="df8d4-171">編集する共有メールボックスを選択し、[メンバーのカスタマイズ] アクセス **許可** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="df8d4-171">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="df8d4-172">メンバー **に対** して変更するアクセス許可の横にある [編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-172">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="df8d4-173">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="df8d4-173">Do one of the following:</span></span>
   - <span data-ttu-id="df8d4-174">追加のメンバーにアクセス許可を付与するには、[アクセス許可の追加] **を選択し**、追加するメンバーを検索または選択して、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="df8d4-174">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="df8d4-175">メンバーからアクセス許可を削除するには、[検索] ボックスを使用して必要に応じてメンバーを検索し、メンバーの名前の横にある **[X]** を選択して、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="df8d4-175">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="df8d4-176">[保存 **] を再び** 選択します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-176">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="df8d4-177">グローバル アドレス一覧で共有メールボックスを表示または非表示にする</span><span class="sxs-lookup"><span data-stu-id="df8d4-177">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="df8d4-178">共有メールボックスをグローバル アドレス一覧に表示しない場合、メールボックスは組織のアドレス一覧に表示されませんが、そのメールボックスに送信された電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-178">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="df8d4-179">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-179">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="df8d4-180"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-180">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="df8d4-181"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-181">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="df8d4-182">編集する共有メールボックスを選択し、[グローバル アドレス一覧に **表示する** 編集] を \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="df8d4-182">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="df8d4-183">トグルをオンまたは **オフに\*\*\*\*設定します**。</span><span class="sxs-lookup"><span data-stu-id="df8d4-183">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="df8d4-184">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df8d4-184">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="df8d4-185">共有メールボックスをアドレス一覧から非表示にすると、共有メールボックスがアドレス一覧に再び表示されるまで、新しい共有メールボックスメンバーが非表示のメールボックスを Outlook プロファイルに追加することは不可能になります。</span><span class="sxs-lookup"><span data-stu-id="df8d4-185">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="df8d4-186">関連記事</span><span class="sxs-lookup"><span data-stu-id="df8d4-186">Related articles</span></span>

[<span data-ttu-id="df8d4-187">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="df8d4-187">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="df8d4-188">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="df8d4-188">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="df8d4-189">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="df8d4-189">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="df8d4-190">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="df8d4-190">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="df8d4-191">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="df8d4-191">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
