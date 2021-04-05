---
title: Microsoft 365 グループの有効期限ポリシー
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
description: Microsoft 365 グループの有効期限ポリシーについて説明します。
ms.openlocfilehash: fdef06918ec2c35547c084e5f431aa7bef8d6a8c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587625"
---
# <a name="microsoft-365-group-expiration-policy"></a><span data-ttu-id="a4ba1-103">Microsoft 365 グループの有効期限ポリシー</span><span class="sxs-lookup"><span data-stu-id="a4ba1-103">Microsoft 365 group expiration policy</span></span>

<span data-ttu-id="a4ba1-104">Microsoft 365 グループと Microsoft Teams の使用が増加する中、管理者とユーザーは未使用のグループとチームをクリーンアップする方法が必要です。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-104">With the increase in usage of Microsoft 365 groups and Microsoft Teams, administrators and users need a way to clean up unused groups and teams.</span></span> <span data-ttu-id="a4ba1-105">Microsoft 365 グループの有効期限ポリシーは、非アクティブなグループをシステムから削除し、よりクリーンな状態にするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-105">A Microsoft 365 groups expiration policy can help remove inactive groups from the system and make things cleaner.</span></span>

<span data-ttu-id="a4ba1-106">グループの有効期限が切れると、関連付けられているすべてのサービス (メールボックス、Planner、SharePoint サイト、チームなど) も削除されます。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-106">When a group expires, all of its associated services (the mailbox, Planner, SharePoint site, team, etc.) are also deleted.</span></span>

<span data-ttu-id="a4ba1-107">グループの有効期限が切れると、"soft-deleted" になります。つまり、最大 30 日間回復できます。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-107">When a group expires it is "soft-deleted" which means it can still be recovered for up to 30 days.</span></span>

<span data-ttu-id="a4ba1-108">管理者は有効期限を指定し、その期間の終わりに達し、更新されない非アクティブなグループは削除されます。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-108">Administrators can specify an expiration period and any inactive group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="a4ba1-109">(これには、アーカイブされたチームが含まれます)。有効期限は、グループが作成された日、または最後に更新された日付から始まります。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-109">(This includes archived teams.) The expiration period begins when the group is created, or on the date it was last renewed.</span></span> <span data-ttu-id="a4ba1-110">グループの所有者は、有効期限の前にメールが自動的に送信され、グループを別の有効期限の間隔で更新できます。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-110">Group owners will automatically be sent an email before the expiration that allows them to renew the group for another expiration interval.</span></span> <span data-ttu-id="a4ba1-111">Teams ユーザーは Teams に永続的な通知を表示します。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-111">Teams users will see persistent notifications in Teams.</span></span>

<span data-ttu-id="a4ba1-112">アクティブに使用されているグループは自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-112">Groups that are actively in use are renewed automatically.</span></span> <span data-ttu-id="a4ba1-113">次のアクションは、グループを自動更新します。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-113">Any of the following actions will auto-renew a group:</span></span>
- <span data-ttu-id="a4ba1-114">SharePoint - ファイルの表示、編集、ダウンロード、移動、共有、またはアップロードを行います。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-114">SharePoint - view, edit, download, move, share, or upload files.</span></span> <span data-ttu-id="a4ba1-115">(SharePoint ページを表示しても、自動更新のアクションとしてカウントされません)。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-115">(Viewing a SharePoint page does not count as an action for automatic renewal.)</span></span>
- <span data-ttu-id="a4ba1-116">Outlook - グループへの参加、グループからのグループ メッセージの読み取りまたは書き込み、メッセージ (Outlook on the web) など。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-116">Outlook - join group, read or write group message from the group, and like a message (Outlook on the web).</span></span>
- <span data-ttu-id="a4ba1-117">Teams - チーム チャネルを訪問します。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-117">Teams - visiting a teams channel.</span></span>

<span data-ttu-id="a4ba1-118">グループの自動更新をYammerする唯一のアクティビティは、コミュニティ内の SharePoint へのドキュメントのアップロードです。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-118">Note that the only Yammer activity which will trigger an automatic group renewal is the upload of a document to SharePoint within the community.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4ba1-p105">有効期限ポリシーを変更すると、サービスによって各グループの有効期限が再計算されます。常にグループの作成日からカウントされます。その後で新しい有効期限ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-p105">When you change the expiration policy, the service recalculates the expiration date for each group. It always starts counting from the date when the group was created, and then applies the new expiration policy.</span></span>

<span data-ttu-id="a4ba1-121">有効期限が既定でオフになっていることを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-121">It's important to know that expiration is turned off by default.</span></span> <span data-ttu-id="a4ba1-122">管理者が使用する場合は、組織で有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-122">Administrators have to enable it for their organization if they want to use it.</span></span>

> [!NOTE]
> <span data-ttu-id="a4ba1-123">Microsoft 365 グループの有効期限ポリシーを構成して使用するには、有効期限ポリシーが適用されるすべてのグループのメンバーに Azure AD Premium ライセンスを割り当てる必要がありますが、必ずしも割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-123">Configuring and using the expiration policy for Microsoft 365 groups requires you to possess but not necessarily assign Azure AD Premium licenses for the members of all groups to which the expiration policy is applied.</span></span> <span data-ttu-id="a4ba1-124">詳細については、「Azure Active Directory Premium [の使用を開始する」を参照してください](/azure/active-directory/active-directory-get-started-premium)。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-124">For more information see [Getting started with Azure Active Directory Premium](/azure/active-directory/active-directory-get-started-premium).</span></span>

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a><span data-ttu-id="a4ba1-125">Microsoft 365 グループの有効期限ポリシーを構成して使用できるユーザー</span><span class="sxs-lookup"><span data-stu-id="a4ba1-125">Who can configure and use the Microsoft 365 groups expiration policy?</span></span>

|<span data-ttu-id="a4ba1-126">Role</span><span class="sxs-lookup"><span data-stu-id="a4ba1-126">Role</span></span>|<span data-ttu-id="a4ba1-127">実行できる操作</span><span class="sxs-lookup"><span data-stu-id="a4ba1-127">What they can do</span></span>|
|---------|---------|
|<span data-ttu-id="a4ba1-128">Office 365 グローバル管理者 (Azure、会社管理者)、ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="a4ba1-128">Office 365 global admin (in Azure, the Company administrator), User administrator</span></span>|<span data-ttu-id="a4ba1-129">Microsoft 365 グループの有効期限ポリシー設定を作成、読み取り、更新、または削除します。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-129">Create, read, update, or delete the Microsoft 365 groups expiration policy settings.</span></span>|
|<span data-ttu-id="a4ba1-130">User</span><span class="sxs-lookup"><span data-stu-id="a4ba1-130">User</span></span>|<span data-ttu-id="a4ba1-131">所有している[](/azure/active-directory/users-groups-roles/groups-restore-deleted) Microsoft 365 グループを更新または復元する</span><span class="sxs-lookup"><span data-stu-id="a4ba1-131">Renew or [restore](/azure/active-directory/users-groups-roles/groups-restore-deleted) a Microsoft 365 group that they own</span></span>|

## <a name="how-to-set-the-expiration-policy"></a><span data-ttu-id="a4ba1-132">有効期限ポリシーを設定する方法</span><span class="sxs-lookup"><span data-stu-id="a4ba1-132">How to set the expiration policy</span></span>

<span data-ttu-id="a4ba1-133">上記のように、有効期限は既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-133">As noted above, expiry is turned off by default.</span></span> <span data-ttu-id="a4ba1-134">管理者は、有効期限ポリシーを有効にして、有効にするプロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-134">An administrator will have to enable the expiration policy and set the properties for it to take effect.</span></span> <span data-ttu-id="a4ba1-135">有効にするには **、[Azure Active Directory グループの有効期限]**  >  **に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-135">To enable it, go to **Azure Active Directory** > **Groups** > **Expiration**.</span></span> <span data-ttu-id="a4ba1-136">ここでは、既定のグループの有効期間を設定し、最初と 2 番目の有効期限通知をグループ所有者に移動する事前の期間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-136">Here you can set the default group lifetime and specify how far in advance you want the first and second expiration notifications to go to the group owner.</span></span>

<span data-ttu-id="a4ba1-137">グループの有効期間は日数で指定され、180、365、または指定したカスタム値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-137">The group lifetime is specified in days and can be set to 180, 365 or to a custom value that you specify.</span></span> <span data-ttu-id="a4ba1-138">カスタム値は、少なくとも 30 日間である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-138">The custom value has to be at least 30 days.</span></span>

<span data-ttu-id="a4ba1-139">グループに所有者が存在しない場合、有効期限の電子メールは指定された管理者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-139">If the group does not have an owner, the expiration emails will go to the specified administrator.</span></span>

<span data-ttu-id="a4ba1-140">すべてのグループにポリシーを設定するか、選択したグループ (最大 500) のみを設定するか、[なし] を選択して完全にオフ **にできます**。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-140">You can set the policy for all of your groups, only selected groups (up to 500), or turn it off completely by selecting **None**.</span></span> <span data-ttu-id="a4ba1-141">現時点では、グループごとに異なるポリシーを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-141">Note that currently you can't have different policies for different groups.</span></span>

![Azure Active Directory のグループの有効期限設定のスクリーンショット](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a><span data-ttu-id="a4ba1-143">保持ポリシーでの有効期限の動作</span><span class="sxs-lookup"><span data-stu-id="a4ba1-143">How expiry works with the retention policy</span></span>

<span data-ttu-id="a4ba1-144">セキュリティ とコンプライアンス センターでグループの保持ポリシーを設定している場合、有効期限ポリシーは保持ポリシーとシームレスに動作します。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-144">If you have set up a retention policy for groups in the Security and Compliance center, the expiration policy works seamlessly with retention policy.</span></span> <span data-ttu-id="a4ba1-145">グループの有効期限が切れると、グループ サイト内のグループのメールボックスの会話とファイルは、保持ポリシーで定義された特定の日数保持コンテナーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-145">When a group expires, the group's mailbox conversations and files in the group site are retained in the retention container for the specific number of days defined in the retention policy.</span></span> <span data-ttu-id="a4ba1-146">ただし、有効期限が過ぎた後、ユーザーにはグループまたはコンテンツは表示されない。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-146">Users will not see the group, or its content, after expiration however.</span></span>

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a><span data-ttu-id="a4ba1-147">グループの所有者がグループの有効期限が切れるか確認する方法と時間</span><span class="sxs-lookup"><span data-stu-id="a4ba1-147">How and when a group owner learns if their groups are going to expire</span></span>

<span data-ttu-id="a4ba1-148">グループの所有者には、電子メールによる通知のみ受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-148">Group owners will only be notified via email.</span></span> <span data-ttu-id="a4ba1-149">グループが Planner、SharePoint、または他のアプリを介して作成された場合、有効期限通知は常に電子メールで送信されます。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-149">If the group was created via Planner, SharePoint, or any other app, the expiration notifications will always come via email.</span></span> <span data-ttu-id="a4ba1-150">グループが Teams 経由で作成された場合、グループ所有者はアクティビティ セクションを通じて更新する通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-150">If the group was created via Teams, the group owner will receive a notification to renew through the activity section.</span></span> <span data-ttu-id="a4ba1-151">グループの所有者に有効なメール アドレスが設定されていない場合は、グループの有効期限を有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-151">It's not recommended that you enable expiration on a group if your group owner doesn't have a valid email address.</span></span>

<span data-ttu-id="a4ba1-152">グループの有効期限が切れる 30 日前に、グループの所有者 (または所有者を持つグループに指定した電子メール アドレス) は、グループを簡単に更新できる電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-152">Thirty days before the group expires, the group owners (or the email addresses that you specified for groups that don't have an owner) will receive an email allowing them to easily renew the group.</span></span> <span data-ttu-id="a4ba1-153">更新しない場合は、有効期限の 15 日前に別の更新メールが届きます。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-153">If they don't renew it, they'll receive another renewal email 15 days before expiration.</span></span> <span data-ttu-id="a4ba1-154">まだ更新していない場合は、有効期限の前にもう 1 回メール通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-154">If they still haven't renewed it, they will receive one more email notification the day before expiration.</span></span>

<span data-ttu-id="a4ba1-155">何らかの理由で、有効期限が切れる前に所有者または管理者がグループを更新しない場合、管理者は有効期限が切れた後、最大 30 日間グループを復元できます。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-155">If for some reason none of the owners or admins renew the group before it expires, the admin can still restore the group for up to 30 days after expiration.</span></span> <span data-ttu-id="a4ba1-156">詳細については、「削除された [Microsoft 365 グループを復元する」を参照してください](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-156">For details see: [Restore a deleted Microsoft 365 group](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).</span></span>

## <a name="archiving-group-contents"></a><span data-ttu-id="a4ba1-157">グループの内容のアーカイブ</span><span class="sxs-lookup"><span data-stu-id="a4ba1-157">Archiving group contents</span></span>

<span data-ttu-id="a4ba1-158">使用する予定がないグループがあるが、そのコンテンツを保持する場合は、「アーカイブ グループ、チーム、 [および Yammer」](end-life-cycle-groups-teams-sites-yammer.md) を参照して、さまざまなグループ サービスから情報をエクスポートする方法について確認してください。</span><span class="sxs-lookup"><span data-stu-id="a4ba1-158">If you have a group that you no longer plan to use, but you want to retain its content, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information about how to export information from the different groups services.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a4ba1-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4ba1-159">Related topics</span></span>

[<span data-ttu-id="a4ba1-160">コラボレーション ガバナンス計画のステップ バイ ステップ</span><span class="sxs-lookup"><span data-stu-id="a4ba1-160">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="a4ba1-161">コラボレーション ガバナンス 計画の作成</span><span class="sxs-lookup"><span data-stu-id="a4ba1-161">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="a4ba1-162">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="a4ba1-162">Overview of retention policies</span></span>](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[<span data-ttu-id="a4ba1-163">孤立グループに新しい所有者を割り当てる</span><span class="sxs-lookup"><span data-stu-id="a4ba1-163">Assign a new owner to an orphaned group</span></span>](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[<span data-ttu-id="a4ba1-164">Microsoft 365 グループの有効期限を構成する</span><span class="sxs-lookup"><span data-stu-id="a4ba1-164">Configure Microsoft 365 groups expiration</span></span>](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
