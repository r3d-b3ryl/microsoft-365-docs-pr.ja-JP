---
title: 共有メールボックスを構成する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスを作成したら、電子メールの転送や自動応答など、ユーザーの設定を構成することができます。 後で、メールボックス名やメンバーなどのその他の設定を変更する必要がある場合があります。
ms.openlocfilehash: 7c88ffa3276f40ea983f9060658f4e4091e36280
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400150"
---
# <a name="configure-a-shared-mailbox"></a><span data-ttu-id="f91a0-104">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="f91a0-104">Configure a shared mailbox</span></span>

<span data-ttu-id="f91a0-105">[共有メールボックスを作成](create-a-shared-mailbox.md)した後で、メールの転送や自動応答などのメールボックスユーザーの設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f91a0-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="f91a0-106">後で、メールボックス名、メンバー、またはメンバのアクセス許可などのその他の設定を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f91a0-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="f91a0-107">共有メールボックスの名前または電子メールエイリアスを変更するか、プライマリ電子メールアドレスを変更します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f91a0-108">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="f91a0-109"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-109">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f91a0-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-110">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="f91a0-111">編集する共有メールボックスを選択し、[**名前、電子メール、メールエイリアス**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-111">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="f91a0-112">新しい名前を入力するか、別のエイリアスを追加します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-112">Enter a new name, or add another alias.</span></span> <span data-ttu-id="f91a0-113">プライマリ電子メールアドレスを変更する場合は、メールボックスに複数の電子メールエイリアスを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f91a0-113">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="f91a0-114">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-114">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="f91a0-115">共有メールボックスに送信されたメールを転送する</span><span class="sxs-lookup"><span data-stu-id="f91a0-115">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="f91a0-116">送信された電子メールを転送するために、共有メールボックスにライセンスを割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f91a0-116">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="f91a0-117">メッセージを任意の有効な電子メールアドレスまたは配布リストに転送できます。</span><span class="sxs-lookup"><span data-stu-id="f91a0-117">You can forward the messages to any valid email address or distribution list.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f91a0-118">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-118">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="f91a0-119"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f91a0-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="f91a0-121">編集する共有メールボックスを選択し、[**電子メール転送**編集] を選択し \> **Edit**ます。</span><span class="sxs-lookup"><span data-stu-id="f91a0-121">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="f91a0-122">**[オン**] に切り替え、メッセージを転送するメールアドレスを1つ入力します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-122">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="f91a0-123">任意の有効な電子メールアドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f91a0-123">It can be any valid email address.</span></span> <span data-ttu-id="f91a0-124">複数のアドレスに転送するには、アドレスの[配布グループを作成](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide)し、このボックスにグループの名前を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f91a0-124">To forward to multiple addresses, you need to [create a distribution group](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="f91a0-125">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-125">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="f91a0-126">共有メールボックスから自動応答を送信する</span><span class="sxs-lookup"><span data-stu-id="f91a0-126">Send automatic replies from a shared mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f91a0-127">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-127">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="f91a0-128"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f91a0-129"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-129">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="f91a0-130">編集する共有メールボックスを選択し、[**自動応答**の編集] を選択し \> **Edit**ます。</span><span class="sxs-lookup"><span data-stu-id="f91a0-130">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="f91a0-131">**[オン**] の切り替えを設定し、組織内または組織外のユーザーに返信を送信するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="f91a0-132">組織内のユーザーに送信する返信を入力します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-132">Enter the reply you want to send to people inside your organization.</span></span> <span data-ttu-id="f91a0-133">画像、テキストのみを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="f91a0-133">You can't add images, only text.</span></span>

5. <span data-ttu-id="f91a0-134">組織外のユーザーに*も*返信を送信する場合は、チェックボックスをオンにして返信を取得し、テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-134">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="f91a0-135">組織内のユーザーには送信せず、組織外のユーザーにのみ送信する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="f91a0-135">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="f91a0-136">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-136">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="f91a0-137">送信済みメール (返信) の表示を全員に許可する</span><span class="sxs-lookup"><span data-stu-id="f91a0-137">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="f91a0-p108">既定では、共有メールボックスから送信されたメッセージは、共有メールボックスの [送信済みアイテム] フォルダーには保存されません。代わりに、メッセージを送信したユーザーの [送信済みアイテム] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="f91a0-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="f91a0-140">すべてのユーザーに送信済みメールの表示を許可する場合は、管理センターで、共有メールボックスの設定を編集して、[**送信済みアイテム**の編集] を選択し \> **Edit**ます。</span><span class="sxs-lookup"><span data-stu-id="f91a0-140">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="f91a0-141">共有メールボックスが Microsoft メールへのアクセスに使用できるアプリを選択する</span><span class="sxs-lookup"><span data-stu-id="f91a0-141">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f91a0-142">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="f91a0-143"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-143">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f91a0-144"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-144">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="f91a0-145">編集する共有メールボックスを選択し、[**電子メールアプリ**の編集] を選択し \> **Edit**ます。</span><span class="sxs-lookup"><span data-stu-id="f91a0-145">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="f91a0-146">メンバーが共有メールボックスへのアクセスに使用できるようにするすべてのアプリのトグルを **[オン**にする。</span><span class="sxs-lookup"><span data-stu-id="f91a0-146">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="f91a0-147">使用しないアプリについては、[**オフ**にする (非表示) に設定します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-147">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="f91a0-148">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-148">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="f91a0-149">訴訟ホールドに共有メールボックスを配置する</span><span class="sxs-lookup"><span data-stu-id="f91a0-149">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="f91a0-150">訴訟ホールドの詳細については、「[訴訟ホールドを作成](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f91a0-150">To learn more about litigation hold, see [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f91a0-151">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-151">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="f91a0-152"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-152">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f91a0-153"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="f91a0-154">編集する共有メールボックスを選択して、[**訴訟ホールド**編集] を選択し \> **Edit**ます。</span><span class="sxs-lookup"><span data-stu-id="f91a0-154">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="f91a0-155">トグルを**オンに**設定します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-155">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="f91a0-156">必要に応じて、期間、s に関するメモ、および詳細情報を含む URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-156">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="f91a0-157">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-157">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="f91a0-158">メンバーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="f91a0-158">Add or remove members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f91a0-159">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="f91a0-160"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-160">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f91a0-161"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-161">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="f91a0-162">編集する共有メールボックスを選択し、[**メンバー**の編集] を選択し \> **Edit**ます。</span><span class="sxs-lookup"><span data-stu-id="f91a0-162">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="f91a0-163">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f91a0-163">Do one of the following:</span></span>
   - <span data-ttu-id="f91a0-164">メンバーを追加するには、[**メンバーの追加**] を選択し、追加するメンバーを検索または選択して、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-164">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="f91a0-165">メンバーを削除するには、検索ボックスを使用してメンバーを検索します。必要に応じて、メンバーの名前の横にある**X**を選択し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-165">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="f91a0-166">[**保存**] をもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-166">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="f91a0-167">メンバーの権限を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="f91a0-167">Add or remove permissions of members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f91a0-168">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-168">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="f91a0-169"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f91a0-170"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="f91a0-171">編集する共有メールボックスを選択し、[**メンバー** ] [ \> **アクセス許可のカスタマイズ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-171">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="f91a0-172">メンバーに対して変更する権限の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-172">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="f91a0-173">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f91a0-173">Do one of the following:</span></span>
   - <span data-ttu-id="f91a0-174">追加のメンバーにアクセス許可を付与するには、[**アクセス許可の追加**] を選択し、追加するメンバーを検索または選択して、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-174">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="f91a0-175">メンバーからアクセス許可を削除するには、検索ボックスを使用してメンバーを検索します。必要に応じて、メンバーの名前の横にある**X**を選択し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-175">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="f91a0-176">[**保存**] をもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-176">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="f91a0-177">グローバルアドレス一覧で共有メールボックスを表示または非表示にする</span><span class="sxs-lookup"><span data-stu-id="f91a0-177">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="f91a0-178">共有メールボックスをグローバルアドレス一覧に表示しないように選択した場合、そのメールボックスは組織のアドレス一覧に表示されませんが、送信されたメールは引き続き受信します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-178">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f91a0-179">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-179">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="f91a0-180"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-180">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f91a0-181"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-181">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="f91a0-182">編集する共有メールボックスを選択し、[**グローバルアドレス一覧の**編集] で [表示] を選択し \> **Edit**ます。</span><span class="sxs-lookup"><span data-stu-id="f91a0-182">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="f91a0-183">トグルを**オン**または**オフ**にします。</span><span class="sxs-lookup"><span data-stu-id="f91a0-183">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="f91a0-184">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f91a0-184">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="f91a0-185">共有メールボックスをアドレス一覧に表示しないようにすると、共有メールボックスがアドレス一覧に再び表示されるまで、新しい共有メールボックスのメンバーが非表示のメールボックスを Outlook プロファイルに追加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f91a0-185">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="f91a0-186">関連記事</span><span class="sxs-lookup"><span data-stu-id="f91a0-186">Related articles</span></span>

[<span data-ttu-id="f91a0-187">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="f91a0-187">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="f91a0-188">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="f91a0-188">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="f91a0-189">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="f91a0-189">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="f91a0-190">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="f91a0-190">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="f91a0-191">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="f91a0-191">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
