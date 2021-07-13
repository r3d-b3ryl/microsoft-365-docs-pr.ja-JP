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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスを作成し、電子メール転送や自動返信など、ユーザーの設定を構成します。
ms.openlocfilehash: e69d1bbde5784339f3973bf456eca1ded72840af
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393993"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="d574f-103">共有メールボックスの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="d574f-103">Configure shared mailbox settings</span></span>

<span data-ttu-id="d574f-104">共有メールボックス [を作成したら](create-a-shared-mailbox.md)、電子メールの転送や自動返信など、メールボックス ユーザーに対していくつかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d574f-104">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="d574f-105">後で、メールボックス名、メンバー、またはメンバーのアクセス許可など、他の設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="d574f-105">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="d574f-106">共有メールボックスの名前またはメール エイリアスを変更するか、プライマリ メール アドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="d574f-106">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

1. <span data-ttu-id="d574f-107">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d574f-107">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="d574f-108">編集する共有メールボックスを選択し、[名前]、[メール]、[メール エイリアス] の横にある [編集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d574f-108">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="d574f-109">新しい名前を入力するか、別のエイリアスを追加します。</span><span class="sxs-lookup"><span data-stu-id="d574f-109">Enter a new name, or add another alias.</span></span> <span data-ttu-id="d574f-110">プライマリ メール アドレスを変更する場合は、メールボックスに複数のメール エイリアスが必要です。</span><span class="sxs-lookup"><span data-stu-id="d574f-110">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="d574f-111">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d574f-111">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="d574f-112">共有メールボックスに送信されたメールを転送する</span><span class="sxs-lookup"><span data-stu-id="d574f-112">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="d574f-113">共有メールボックスに送信されるメールを転送するために、共有メールボックスにライセンスを割り当てる必要はない。</span><span class="sxs-lookup"><span data-stu-id="d574f-113">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="d574f-114">メッセージは、有効な電子メール アドレスまたは配布リストに転送できます。</span><span class="sxs-lookup"><span data-stu-id="d574f-114">You can forward the messages to any valid email address or distribution list.</span></span>

1. <span data-ttu-id="d574f-115">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d574f-115">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="d574f-116">編集する共有メールボックスを選択し、[メール転送の編集 **] を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d574f-116">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="d574f-117">トグルを [ **オン] に設定** し、メッセージを転送するメール アドレスを 1 つ入力します。</span><span class="sxs-lookup"><span data-stu-id="d574f-117">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="d574f-118">有効な電子メール アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d574f-118">It can be any valid email address.</span></span> <span data-ttu-id="d574f-119">複数のアドレスに転送するには、アドレスの[](/office365/admin/setup/create-distribution-lists)配布グループを作成し、このボックスにグループの名前を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d574f-119">To forward to multiple addresses, you need to [create a distribution group](/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="d574f-120">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d574f-120">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="d574f-121">共有メールボックスから自動応答を送信する</span><span class="sxs-lookup"><span data-stu-id="d574f-121">Send automatic replies from a shared mailbox</span></span>

1. <span data-ttu-id="d574f-122">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d574f-122">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="d574f-123">編集する共有メールボックスを選択し、[自動返信の編集 **] を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d574f-123">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="d574f-124">トグルを **[オン] に** 設定し、組織内または組織外のユーザーに返信を送信するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="d574f-124">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="d574f-p105">組織内部のユーザーに送信する返信を入力します。画像は追加できません。テキストのみを入力できます。</span><span class="sxs-lookup"><span data-stu-id="d574f-p105">Enter the reply you want to send to people inside your organization. You can't add images, only text.</span></span>

5. <span data-ttu-id="d574f-127">組織外のユーザー *にも* 返信を送信する場合は、チェック ボックスをオンにして、返信を取得するユーザーを選択し、テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="d574f-127">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="d574f-128">組織内のユーザーには送信せず、組織外のユーザーにのみ送信する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="d574f-128">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="d574f-129">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d574f-129">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="d574f-130">送信済みメール (返信) の表示を全員に許可する</span><span class="sxs-lookup"><span data-stu-id="d574f-130">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="d574f-p107">既定では、共有メールボックスから送信されたメッセージは、共有メールボックスの [送信済みアイテム] フォルダーには保存されません。代わりに、メッセージを送信したユーザーの [送信済みアイテム] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d574f-p107">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="d574f-133">すべてのユーザーに送信メールの表示を許可する場合は、管理センターで共有メールボックス設定を編集し、[送信されたアイテムの編集] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d574f-133">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="d574f-134">共有メールボックスが Microsoft メールへのアクセスに使用できるアプリを選択する</span><span class="sxs-lookup"><span data-stu-id="d574f-134">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

1. <span data-ttu-id="d574f-135">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d574f-135">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="d574f-136">編集する共有メールボックスを選択し、[メール アプリの編集] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d574f-136">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="d574f-137">メンバーが共有 **メールボックスに** アクセスするために使用できるすべてのアプリのトグルを [オン] に設定します。</span><span class="sxs-lookup"><span data-stu-id="d574f-137">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="d574f-138">使用しないアプリのトグルを **[オフ** ] に設定します。</span><span class="sxs-lookup"><span data-stu-id="d574f-138">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="d574f-139">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d574f-139">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="d574f-140">訴訟ホールドに共有メールボックスを置く</span><span class="sxs-lookup"><span data-stu-id="d574f-140">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="d574f-141">訴訟ホールドの詳細については、「訴訟ホールドの [作成」を参照してください](../../compliance/create-a-litigation-hold.md)。</span><span class="sxs-lookup"><span data-stu-id="d574f-141">To learn more about litigation hold, see [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span></span>

1. <span data-ttu-id="d574f-142">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d574f-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="d574f-143">編集する共有メールボックスを選択し、[訴訟ホールドの編集 **] を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d574f-143">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="d574f-144">トグルを On に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="d574f-144">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="d574f-145">必要に応じて、期間、保留に関するメモ、および詳細を示す URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d574f-145">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="d574f-146">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d574f-146">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="d574f-147">メンバーの追加または削除</span><span class="sxs-lookup"><span data-stu-id="d574f-147">Add or remove members</span></span>

1. <span data-ttu-id="d574f-148">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d574f-148">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="d574f-149">編集する共有メールボックスを選択し、[メンバーの編集] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d574f-149">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="d574f-150">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d574f-150">Do one of the following:</span></span>
   - <span data-ttu-id="d574f-151">メンバーを追加するには、[メンバーの **追加] を** 選択し、追加するメンバーを検索または選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d574f-151">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="d574f-152">メンバーを削除するには、[検索] ボックスを使用して必要に応じてメンバーを検索し、メンバーの名前の横にある **[X]** を選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d574f-152">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="d574f-153">[保存 **] を再度** 選択します。</span><span class="sxs-lookup"><span data-stu-id="d574f-153">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="d574f-154">メンバーのアクセス許可を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="d574f-154">Add or remove permissions of members</span></span>

1. <span data-ttu-id="d574f-155">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d574f-155">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="d574f-156">編集する共有メールボックスを選択し、[メンバーのカスタマイズ] \> **アクセス許可を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d574f-156">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="d574f-157">メンバー **に対** して変更するアクセス許可の横にある [編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d574f-157">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="d574f-158">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d574f-158">Do one of the following:</span></span>
   - <span data-ttu-id="d574f-159">そのアクセス許可を追加のメンバーに付与するには、[アクセス許可の追加] **を選択し**、追加するメンバーを検索または選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d574f-159">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="d574f-160">メンバーからアクセス許可を削除するには、[検索] ボックスを使用して必要に応じてメンバーを検索し、メンバーの名前の横にある **[X]** を選択し、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="d574f-160">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="d574f-161">[保存 **] を再度** 選択します。</span><span class="sxs-lookup"><span data-stu-id="d574f-161">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="d574f-162">グローバル アドレス一覧で共有メールボックスを表示または非表示にする</span><span class="sxs-lookup"><span data-stu-id="d574f-162">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="d574f-163">共有メールボックスをグローバル アドレス一覧に表示しない場合、メールボックスは組織のアドレス一覧には表示されませんが、送信された電子メールは引き続き受信されます。</span><span class="sxs-lookup"><span data-stu-id="d574f-163">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

1. <span data-ttu-id="d574f-164">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d574f-164">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="d574f-165">編集する共有メールボックスを選択し、[グローバル アドレス一覧に表示する]**を選択** \> **します。**</span><span class="sxs-lookup"><span data-stu-id="d574f-165">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="d574f-166">トグルを [オン] または **[オフ] に\*\*\*\*設定します**。</span><span class="sxs-lookup"><span data-stu-id="d574f-166">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="d574f-167">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d574f-167">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d574f-168">共有メールボックスをアドレス一覧から非表示にすると、新しい共有メールボックスメンバーが、共有メールボックスがアドレス一覧に再び表示されるまで、非表示のメールボックスを Outlook プロファイルに追加できません。</span><span class="sxs-lookup"><span data-stu-id="d574f-168">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-content"></a><span data-ttu-id="d574f-169">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="d574f-169">Related content</span></span>

<span data-ttu-id="d574f-170">[共有メールボックスについて](about-shared-mailboxes.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="d574f-170">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="d574f-171">[共有メールボックスの作成](create-a-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="d574f-171">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="d574f-172">[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="d574f-172">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="d574f-173">[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="d574f-173">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="d574f-174">[共有メールボックスに関する問題を解決する](resolve-issues-with-shared-mailboxes.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="d574f-174">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>