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
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスを作成したら、電子メール転送や自動返信など、ユーザーに対していくつかの設定を構成する必要があります。 後で、メールボックス名やメンバーなどの他の設定を変更することもできます。
ms.openlocfilehash: 01d5aaa686e1d64c9ea7d89913d8208f779dcfd1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52243974"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="abf8f-104">共有メールボックスの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="abf8f-104">Configure shared mailbox settings</span></span>

<span data-ttu-id="abf8f-105">共有メールボックス [を作成したら](create-a-shared-mailbox.md)、電子メールの転送や自動返信など、メールボックス ユーザーに対していくつかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="abf8f-106">後で、メールボックス名、メンバー、またはメンバーのアクセス許可など、他の設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="abf8f-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="abf8f-107">共有メールボックスの名前またはメール エイリアスを変更するか、プライマリ メール アドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="abf8f-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

1. <span data-ttu-id="abf8f-108">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="abf8f-109">編集する共有メールボックスを選択し、[名前]、[メール]、[メール エイリアス] の横にある [編集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf8f-109">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="abf8f-110">新しい名前を入力するか、別のエイリアスを追加します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-110">Enter a new name, or add another alias.</span></span> <span data-ttu-id="abf8f-111">プライマリ メール アドレスを変更する場合は、メールボックスに複数のメール エイリアスが必要です。</span><span class="sxs-lookup"><span data-stu-id="abf8f-111">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="abf8f-112">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-112">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="abf8f-113">共有メールボックスに送信されたメールを転送する</span><span class="sxs-lookup"><span data-stu-id="abf8f-113">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="abf8f-114">共有メールボックスに送信されるメールを転送するために、共有メールボックスにライセンスを割り当てる必要はない。</span><span class="sxs-lookup"><span data-stu-id="abf8f-114">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="abf8f-115">メッセージは、有効な電子メール アドレスまたは配布リストに転送できます。</span><span class="sxs-lookup"><span data-stu-id="abf8f-115">You can forward the messages to any valid email address or distribution list.</span></span>

1. <span data-ttu-id="abf8f-116">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-116">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="abf8f-117">編集する共有メールボックスを選択し、[メール転送の編集 **] を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf8f-117">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="abf8f-118">トグルを [ **オン] に設定** し、メッセージを転送するメール アドレスを 1 つ入力します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-118">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="abf8f-119">有効な電子メール アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="abf8f-119">It can be any valid email address.</span></span> <span data-ttu-id="abf8f-120">複数のアドレスに転送するには、アドレスの[](/office365/admin/setup/create-distribution-lists)配布グループを作成し、このボックスにグループの名前を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf8f-120">To forward to multiple addresses, you need to [create a distribution group](/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="abf8f-121">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-121">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="abf8f-122">共有メールボックスから自動応答を送信する</span><span class="sxs-lookup"><span data-stu-id="abf8f-122">Send automatic replies from a shared mailbox</span></span>

1. <span data-ttu-id="abf8f-123">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-123">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="abf8f-124">編集する共有メールボックスを選択し、[自動返信の編集 **] を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf8f-124">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="abf8f-125">トグルを **[オン] に** 設定し、組織内または組織外のユーザーに返信を送信するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-125">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="abf8f-p106">組織内部のユーザーに送信する返信を入力します。画像は追加できません。テキストのみを入力できます。</span><span class="sxs-lookup"><span data-stu-id="abf8f-p106">Enter the reply you want to send to people inside your organization. You can't add images, only text.</span></span>

5. <span data-ttu-id="abf8f-128">組織外のユーザー *にも* 返信を送信する場合は、チェック ボックスをオンにして、返信を取得するユーザーを選択し、テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-128">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="abf8f-129">組織内のユーザーには送信せず、組織外のユーザーにのみ送信する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="abf8f-129">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="abf8f-130">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-130">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="abf8f-131">送信済みメール (返信) の表示を全員に許可する</span><span class="sxs-lookup"><span data-stu-id="abf8f-131">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="abf8f-p108">既定では、共有メールボックスから送信されたメッセージは、共有メールボックスの [送信済みアイテム] フォルダーには保存されません。代わりに、メッセージを送信したユーザーの [送信済みアイテム] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="abf8f-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="abf8f-134">すべてのユーザーに送信メールの表示を許可する場合は、管理センターで共有メールボックス設定を編集し、[送信されたアイテムの編集] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf8f-134">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="abf8f-135">共有メールボックスが Microsoft メールへのアクセスに使用できるアプリを選択する</span><span class="sxs-lookup"><span data-stu-id="abf8f-135">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

1. <span data-ttu-id="abf8f-136">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-136">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="abf8f-137">編集する共有メールボックスを選択し、[メール アプリの編集] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf8f-137">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="abf8f-138">メンバーが共有 **メールボックスに** アクセスするために使用できるすべてのアプリのトグルを [オン] に設定します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-138">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="abf8f-139">使用しないアプリのトグルを **[オフ** ] に設定します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-139">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="abf8f-140">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-140">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="abf8f-141">訴訟ホールドに共有メールボックスを置く</span><span class="sxs-lookup"><span data-stu-id="abf8f-141">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="abf8f-142">訴訟ホールドの詳細については、「訴訟ホールドの [作成」を参照してください](../../compliance/create-a-litigation-hold.md)。</span><span class="sxs-lookup"><span data-stu-id="abf8f-142">To learn more about litigation hold, see [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span></span>

1. <span data-ttu-id="abf8f-143">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-143">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="abf8f-144">編集する共有メールボックスを選択し、[訴訟ホールドの編集 **] を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf8f-144">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="abf8f-145">トグルを On に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="abf8f-145">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="abf8f-146">必要に応じて、期間、保留に関するメモ、および詳細を示す URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-146">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="abf8f-147">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-147">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="abf8f-148">メンバーの追加または削除</span><span class="sxs-lookup"><span data-stu-id="abf8f-148">Add or remove members</span></span>

1. <span data-ttu-id="abf8f-149">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-149">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="abf8f-150">編集する共有メールボックスを選択し、[メンバーの編集] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf8f-150">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="abf8f-151">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="abf8f-151">Do one of the following:</span></span>
   - <span data-ttu-id="abf8f-152">メンバーを追加するには、[メンバーの **追加] を** 選択し、追加するメンバーを検索または選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf8f-152">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="abf8f-153">メンバーを削除するには、[検索] ボックスを使用して必要に応じてメンバーを検索し、メンバーの名前の横にある **[X]** を選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf8f-153">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="abf8f-154">[保存 **] を再度** 選択します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-154">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="abf8f-155">メンバーのアクセス許可を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="abf8f-155">Add or remove permissions of members</span></span>

1. <span data-ttu-id="abf8f-156">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-156">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="abf8f-157">編集する共有メールボックスを選択し、[メンバーのカスタマイズ] \> **アクセス許可を選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf8f-157">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="abf8f-158">メンバー **に対** して変更するアクセス許可の横にある [編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-158">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="abf8f-159">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="abf8f-159">Do one of the following:</span></span>
   - <span data-ttu-id="abf8f-160">そのアクセス許可を追加のメンバーに付与するには、[アクセス許可の追加] **を選択し**、追加するメンバーを検索または選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf8f-160">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="abf8f-161">メンバーからアクセス許可を削除するには、[検索] ボックスを使用して必要に応じてメンバーを検索し、メンバーの名前の横にある **[X]** を選択し、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="abf8f-161">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="abf8f-162">[保存 **] を再度** 選択します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-162">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="abf8f-163">グローバル アドレス一覧で共有メールボックスを表示または非表示にする</span><span class="sxs-lookup"><span data-stu-id="abf8f-163">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="abf8f-164">共有メールボックスをグローバル アドレス一覧に表示しない場合、メールボックスは組織のアドレス一覧には表示されませんが、送信された電子メールは引き続き受信されます。</span><span class="sxs-lookup"><span data-stu-id="abf8f-164">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

1. <span data-ttu-id="abf8f-165">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-165">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="abf8f-166">編集する共有メールボックスを選択し、[グローバル アドレス一覧に表示する]**を選択** \> **します。**</span><span class="sxs-lookup"><span data-stu-id="abf8f-166">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="abf8f-167">トグルを [オン] または **[オフ] に\*\*\*\*設定します**。</span><span class="sxs-lookup"><span data-stu-id="abf8f-167">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="abf8f-168">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="abf8f-168">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="abf8f-169">共有メールボックスをアドレス一覧から非表示にすると、新しい共有メールボックスメンバーが、共有メールボックスがアドレス一覧に再び表示されるまで、非表示のメールボックスを Outlook プロファイルに追加できません。</span><span class="sxs-lookup"><span data-stu-id="abf8f-169">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-content"></a><span data-ttu-id="abf8f-170">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="abf8f-170">Related content</span></span>

<span data-ttu-id="abf8f-171">[共有メールボックスについて](about-shared-mailboxes.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="abf8f-171">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>

<span data-ttu-id="abf8f-172">[共有メールボックスの作成](create-a-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="abf8f-172">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="abf8f-173">[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="abf8f-173">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="abf8f-174">[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="abf8f-174">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="abf8f-175">[共有メールボックスの問題を解決する](resolve-issues-with-shared-mailboxes.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="abf8f-175">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>