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
ms.openlocfilehash: d55cc7fff939cb07ae2eba92de411e8f0d088885
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613656"
---
# <a name="microsoft-365-group-expiration-policy"></a><span data-ttu-id="18e6b-103">Microsoft 365 グループの有効期限ポリシー</span><span class="sxs-lookup"><span data-stu-id="18e6b-103">Microsoft 365 group expiration policy</span></span>

<span data-ttu-id="18e6b-104">Microsoft 365 グループと Microsoft Teams の使用率が向上したことで、管理者とユーザーは、使用されていないグループと teams をクリーンアップする方法が必要になります。</span><span class="sxs-lookup"><span data-stu-id="18e6b-104">With the increase in usage of Microsoft 365 groups and Microsoft Teams, administrators and users need a way to clean up unused groups and teams.</span></span> <span data-ttu-id="18e6b-105">Microsoft 365 グループの有効期限ポリシーは、非アクティブなグループをシステムから削除して、クリーナーを作成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-105">A Microsoft 365 groups expiration policy can help remove inactive groups from the system and make things cleaner.</span></span>

<span data-ttu-id="18e6b-106">グループの有効期限が切れると、関連付けられているすべてのサービス (メールボックス、プランナー、SharePoint サイト、チームなど) も削除されます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-106">When a group expires, all of its associated services (the mailbox, Planner, SharePoint site, team, etc.) are also deleted.</span></span>

<span data-ttu-id="18e6b-107">グループの有効期限が切れた場合、"削除済み" となることを意味します。これは、最大30日間復旧できます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-107">When a group expires it is "soft-deleted" which means it can still be recovered for up to 30 days.</span></span>

<span data-ttu-id="18e6b-108">管理者は、有効期限を指定して、その期間の最後に到達し、更新されていないアクティブなグループを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-108">Administrators can specify an expiration period and any inactive group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="18e6b-109">(アーカイブされたチームが含まれます)。有効期限は、グループが作成された時点、または最後に更新された日付から始まります。</span><span class="sxs-lookup"><span data-stu-id="18e6b-109">(This includes archived teams.) The expiration period begins when the group is created, or on the date it was last renewed.</span></span> <span data-ttu-id="18e6b-110">グループの所有者は、有効期限が切れる前に、別の有効期限が切れるまでグループを更新できるように、メールを自動的に送信します。</span><span class="sxs-lookup"><span data-stu-id="18e6b-110">Group owners will automatically be sent an email before the expiration that allows them to renew the group for another expiration interval.</span></span> <span data-ttu-id="18e6b-111">Teams ユーザーには、Teams で永続的な通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-111">Teams users will see persistent notifications in Teams.</span></span>

<span data-ttu-id="18e6b-112">アクティブに使用されているグループは自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-112">Groups that are actively in use are renewed automatically.</span></span> <span data-ttu-id="18e6b-113">次のいずれかのアクションを実行すると、グループが自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-113">Any of the following actions will auto-renew a group:</span></span>
- <span data-ttu-id="18e6b-114">SharePoint-ファイルの表示、編集、ダウンロード、移動、共有、またはアップロードを行います。</span><span class="sxs-lookup"><span data-stu-id="18e6b-114">SharePoint - view, edit, download, move, share, or upload files.</span></span> <span data-ttu-id="18e6b-115">(SharePoint ページを表示すると、自動更新のアクションとしてカウントされません)。</span><span class="sxs-lookup"><span data-stu-id="18e6b-115">(Viewing a SharePoint page does not count as an action for automatic renewal.)</span></span>
- <span data-ttu-id="18e6b-116">Outlook-グループのメッセージと同じように、グループからのメッセージの読み取りまたは書き込み。メッセージ (web 上の Outlook)。</span><span class="sxs-lookup"><span data-stu-id="18e6b-116">Outlook - join group, read or write group message from the group, and like a message (Outlook on the web).</span></span>
- <span data-ttu-id="18e6b-117">Teams チャネルを訪れます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-117">Teams - visiting a teams channel.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18e6b-p105">有効期限ポリシーを変更すると、サービスによって各グループの有効期限が再計算されます。常にグループの作成日からカウントされます。その後で新しい有効期限ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-p105">When you change the expiration policy, the service recalculates the expiration date for each group. It always starts counting from the date when the group was created, and then applies the new expiration policy.</span></span>

<span data-ttu-id="18e6b-120">既定では、有効期限はオフになっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="18e6b-120">It's important to know that expiration is turned off by default.</span></span> <span data-ttu-id="18e6b-121">管理者は、組織で使用する必要がある場合は、それを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="18e6b-121">Administrators have to enable it for their organization if they want to use it.</span></span>

> [!NOTE]
> <span data-ttu-id="18e6b-122">Microsoft 365 グループの有効期限ポリシーを構成して使用するには、その有効期限ポリシーが適用されているすべてのグループのメンバーに対して、必ずしも Azure AD Premium ライセンスを割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="18e6b-122">Configuring and using the expiration policy for Microsoft 365 groups requires you to possess but not necessarily assign Azure AD Premium licenses for the members of all groups to which the expiration policy is applied.</span></span> <span data-ttu-id="18e6b-123">詳細については、「 [Azure Active Directory Premium の](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18e6b-123">For more information see [Getting started with Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).</span></span>

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a><span data-ttu-id="18e6b-124">Microsoft 365 グループの有効期限ポリシーを構成および使用できるユーザー</span><span class="sxs-lookup"><span data-stu-id="18e6b-124">Who can configure and use the Microsoft 365 groups expiration policy?</span></span>

|<span data-ttu-id="18e6b-125">Role</span><span class="sxs-lookup"><span data-stu-id="18e6b-125">Role</span></span>|<span data-ttu-id="18e6b-126">できること</span><span class="sxs-lookup"><span data-stu-id="18e6b-126">What they can do</span></span>|
|---------|---------|
|<span data-ttu-id="18e6b-127">Office 365 のグローバル管理者 (Azure、会社の管理者の場合)、ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="18e6b-127">Office 365 global admin (in Azure, the Company administrator), User administrator</span></span>|<span data-ttu-id="18e6b-128">Microsoft 365 グループの有効期限ポリシーの設定を作成、読み取り、更新、または削除します。</span><span class="sxs-lookup"><span data-stu-id="18e6b-128">Create, read, update, or delete the Microsoft 365 groups expiration policy settings.</span></span>|
|<span data-ttu-id="18e6b-129">ユーザー</span><span class="sxs-lookup"><span data-stu-id="18e6b-129">User</span></span>|<span data-ttu-id="18e6b-130">自分が所有する Microsoft 365 グループを更新または [復元](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) する</span><span class="sxs-lookup"><span data-stu-id="18e6b-130">Renew or [restore](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) a Microsoft 365 group that they own</span></span>|

## <a name="how-to-set-the-expiration-policy"></a><span data-ttu-id="18e6b-131">有効期限ポリシーを設定する方法</span><span class="sxs-lookup"><span data-stu-id="18e6b-131">How to set the expiration policy</span></span>

<span data-ttu-id="18e6b-132">前述したように、有効期限は既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="18e6b-132">As noted above, expiry is turned off by default.</span></span> <span data-ttu-id="18e6b-133">管理者は有効期限ポリシーを有効にして、そのプロパティを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="18e6b-133">An administrator will have to enable the expiration policy and set the properties for it to take effect.</span></span> <span data-ttu-id="18e6b-134">これを有効にするには、[ **Azure Active Directory**  >  **グループ** の  >  **有効期限**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="18e6b-134">To enable it, go to **Azure Active Directory** > **Groups** > **Expiration**.</span></span> <span data-ttu-id="18e6b-135">ここでは、既定のグループの有効期間を設定して、最初と2番目の有効期限の通知がグループの所有者に移動するまでの時間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-135">Here you can set the default group lifetime and specify how far in advance you want the first and second expiration notifications to go to the group owner.</span></span>

<span data-ttu-id="18e6b-136">グループの有効期間は日単位で指定し、180、365、または指定したカスタム値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-136">The group lifetime is specified in days and can be set to 180, 365 or to a custom value that you specify.</span></span> <span data-ttu-id="18e6b-137">カスタム値は、少なくとも30日である必要があります。</span><span class="sxs-lookup"><span data-stu-id="18e6b-137">The custom value has to be at least 30 days.</span></span>

<span data-ttu-id="18e6b-138">グループに所有者がいない場合、有効期限メールは指定された管理者に送られます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-138">If the group does not have an owner, the expiration emails will go to the specified administrator.</span></span>

<span data-ttu-id="18e6b-139">すべてのグループに対してポリシーを設定するか、選択したグループのみを設定するか、または **[なし**] を選択して完全にオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-139">You can set the policy for all of your groups, only selected groups, or turn it off completely by selecting **None**.</span></span> <span data-ttu-id="18e6b-140">現在、グループごとに異なるポリシーを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="18e6b-140">Note that currently you can't have different policies for different groups.</span></span>

![Azure Active Directory でのグループの有効期限設定のスクリーンショット](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a><span data-ttu-id="18e6b-142">保持ポリシーを使用した有効期限のしくみ</span><span class="sxs-lookup"><span data-stu-id="18e6b-142">How expiry works with the retention policy</span></span>

<span data-ttu-id="18e6b-143">セキュリティ/コンプライアンスセンターでグループのアイテム保持ポリシーを設定している場合、有効期限ポリシーは保持ポリシーとシームレスに連動します。</span><span class="sxs-lookup"><span data-stu-id="18e6b-143">If you have set up a retention policy for groups in the Security and Compliance center, the expiration policy works seamlessly with retention policy.</span></span> <span data-ttu-id="18e6b-144">グループの有効期限が切れると、グループのメールボックスの会話とグループサイト内のファイルは、アイテム保持ポリシーで定義されている特定の日数だけ、保持コンテナーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-144">When a group expires, the group's mailbox conversations and files in the group site are retained in the retention container for the specific number of days defined in the retention policy.</span></span> <span data-ttu-id="18e6b-145">ただし、有効期限が切れた後は、グループまたはそのコンテンツは表示されません。</span><span class="sxs-lookup"><span data-stu-id="18e6b-145">Users will not see the group, or its content, after expiration however.</span></span>

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a><span data-ttu-id="18e6b-146">グループの有効期限が切れるかどうかをグループの所有者が学習する方法とタイミング</span><span class="sxs-lookup"><span data-stu-id="18e6b-146">How and when a group owner learns if their groups are going to expire</span></span>

<span data-ttu-id="18e6b-147">グループの所有者には、電子メールを介してのみ通知されます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-147">Group owners will only be notified via email.</span></span> <span data-ttu-id="18e6b-148">このグループが Planner、SharePoint、またはその他のアプリによって作成された場合、有効期限通知は常に電子メール経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-148">If the group was created via Planner, SharePoint, or any other app, the expiration notifications will always come via email.</span></span> <span data-ttu-id="18e6b-149">グループが Teams によって作成された場合、グループの所有者は [activity] セクションを通じて更新する通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="18e6b-149">If the group was created via Teams, the group owner will receive a notification to renew through the activity section.</span></span> <span data-ttu-id="18e6b-150">グループの所有者が有効な電子メールアドレスを持っていない場合は、グループの有効期限を有効にすることはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="18e6b-150">It's not recommended that you enable expiration on a group if your group owner doesn't have a valid email address.</span></span>

<span data-ttu-id="18e6b-151">グループの有効期限が切れるまで30日間、グループの所有者 (または所有者がいないグループに対して指定したメールアドレス) は、グループを簡単に更新できる電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="18e6b-151">Thirty days before the group expires, the group owners (or the email addresses that you specified for groups that don't have an owner) will receive an email allowing them to easily renew the group.</span></span> <span data-ttu-id="18e6b-152">更新されていない場合は、有効期限が切れるまで15日後にもう一度更新メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="18e6b-152">If they don't renew it, they'll receive another renewal email 15 days before expiration.</span></span> <span data-ttu-id="18e6b-153">まだ更新していない場合は、有効期限が切れる前に1日に1回のメール通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="18e6b-153">If they still haven't renewed it, they will receive one more email notification the day before expiration.</span></span>

<span data-ttu-id="18e6b-154">何らかの理由で、所有者または管理者が期限切れになる前にグループを更新しない場合でも、管理者は有効期限が切れてから30日以内にグループを復元することができます。</span><span class="sxs-lookup"><span data-stu-id="18e6b-154">If for some reason none of the owners or admins renew the group before it expires, the admin can still restore the group for up to 30 days after expiration.</span></span> <span data-ttu-id="18e6b-155">詳細については [、「削除された Microsoft 365 グループを復元する](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18e6b-155">For details see: [Restore a deleted Microsoft 365 group](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).</span></span>

## <a name="archiving-group-contents"></a><span data-ttu-id="18e6b-156">グループのコンテンツをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="18e6b-156">Archiving group contents</span></span>

<span data-ttu-id="18e6b-157">使用を計画していないものの、そのコンテンツを保持する必要があるグループがある場合は、「 [Archive groups, teams, And Yammer](end-life-cycle-groups-teams-sites-yammer.md) 」を参照して、さまざまなグループサービスから情報をエクスポートする方法に関する情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18e6b-157">If you have a group that you no longer plan to use, but you want to retain its content, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information about how to export information from the different groups services.</span></span>

## <a name="related-topics"></a><span data-ttu-id="18e6b-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="18e6b-158">Related topics</span></span>

[<span data-ttu-id="18e6b-159">コラボレーションガバナンスの計画のステップバイステップ</span><span class="sxs-lookup"><span data-stu-id="18e6b-159">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="18e6b-160">コラボレーションのガバナンス計画を作成する</span><span class="sxs-lookup"><span data-stu-id="18e6b-160">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="18e6b-161">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="18e6b-161">Overview of retention policies</span></span>](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[<span data-ttu-id="18e6b-162">孤立グループに新しい所有者を割り当てる</span><span class="sxs-lookup"><span data-stu-id="18e6b-162">Assign a new owner to an orphaned group</span></span>](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[<span data-ttu-id="18e6b-163">Microsoft 365 グループの有効期限を構成する</span><span class="sxs-lookup"><span data-stu-id="18e6b-163">Configure Microsoft 365 groups expiration</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
