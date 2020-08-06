---
title: グループの有効期限ポリシー
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 グループの有効期限ポリシーについて説明します。
ms.openlocfilehash: bda4bfbbef4e0d145c55b2a49b4d1203c6a7b1f0
ms.sourcegitcommit: 4f82fa7270e7ec6c6dd80329f28612e1f3289b22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "46572141"
---
# <a name="microsoft-365-group-expiration-policy"></a><span data-ttu-id="e7f20-103">Microsoft 365 グループの有効期限ポリシー</span><span class="sxs-lookup"><span data-stu-id="e7f20-103">Microsoft 365 group expiration policy</span></span>

<span data-ttu-id="e7f20-104">Microsoft 365 グループの使用が増加したことで、管理者とユーザーは、使用されていないグループをクリーンアップする方法が必要になります。</span><span class="sxs-lookup"><span data-stu-id="e7f20-104">With the increase in usage of Microsoft 365 groups, administrators and users need a way to clean up unused groups.</span></span> <span data-ttu-id="e7f20-105">有効期限ポリシーは、非アクティブなグループをシステムから削除して、クリーナーを作成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-105">Expiration policies can help remove inactive groups from the system and make things cleaner.</span></span>

<span data-ttu-id="e7f20-106">グループの有効期限が切れると、関連付けられているすべてのサービス (メールボックス、プランナー、SharePoint サイト、チームなど) も削除されます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-106">When a group expires, all of its associated services (the mailbox, Planner, SharePoint site, team, etc.) are also deleted.</span></span>

<span data-ttu-id="e7f20-107">グループの有効期限が切れた場合、"削除済み" となることを意味します。これは、最大30日間復旧できます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-107">When a group expires it is "soft-deleted" which means it can still be recovered for up to 30 days.</span></span>

<span data-ttu-id="e7f20-108">管理者は、有効期限を指定して、その期間の最後に到達し、更新されていないアクティブなグループを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-108">Administrators can specify an expiration period and any inactive group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="e7f20-109">有効期限は、グループが作成された時点、または最後に更新された日付から始まります。</span><span class="sxs-lookup"><span data-stu-id="e7f20-109">The expiration period begins when the group is created, or on the date it was last renewed.</span></span> <span data-ttu-id="e7f20-110">グループの所有者は、有効期限が切れる前に、別の有効期限が切れるまでグループを更新できるように、メールを自動的に送信します。</span><span class="sxs-lookup"><span data-stu-id="e7f20-110">Group owners will automatically be sent an email before the expiration that allows them to renew the group for another expiration interval.</span></span> <span data-ttu-id="e7f20-111">Teams ユーザーには、Teams で永続的な通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-111">Teams users will see persistent notifications in Teams.</span></span>

<span data-ttu-id="e7f20-112">アクティブに使用されているグループは自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-112">Groups that are actively in use are renewed automatically.</span></span> <span data-ttu-id="e7f20-113">次のいずれかのアクションを実行すると、グループが自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-113">Any of the following actions will auto-renew a group:</span></span>
- <span data-ttu-id="e7f20-114">SharePoint-ファイルの表示、編集、ダウンロード、移動、共有、またはアップロードを行います。</span><span class="sxs-lookup"><span data-stu-id="e7f20-114">SharePoint - view, edit, download, move, share, or upload files.</span></span>
- <span data-ttu-id="e7f20-115">Outlook-グループのメッセージと同じように、グループからのメッセージの読み取りまたは書き込み。メッセージ (web 上の Outlook)。</span><span class="sxs-lookup"><span data-stu-id="e7f20-115">Outlook - join group, read or write group message from the group, and like a message (Outlook on the web).</span></span>
- <span data-ttu-id="e7f20-116">Teams チャネルを訪れます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-116">Teams - visiting a teams channel.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7f20-p104">有効期限ポリシーを変更すると、サービスによって各グループの有効期限が再計算されます。常にグループの作成日からカウントされます。その後で新しい有効期限ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-p104">When you change the expiration policy, the service recalculates the expiration date for each group. It always starts counting from the date when the group was created, and then applies the new expiration policy.</span></span>

<span data-ttu-id="e7f20-119">既定では、有効期限はオフになっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e7f20-119">It's important to know that expiration is turned off by default.</span></span> <span data-ttu-id="e7f20-120">管理者は、組織で使用する必要がある場合に、そのユーザーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7f20-120">Administrators will have to enable it for their organization if they want to use it.</span></span>

> [!NOTE]
> <span data-ttu-id="e7f20-121">Microsoft 365 グループの有効期限ポリシーを構成して使用するには、その有効期限ポリシーが適用されているすべてのグループのメンバーに対して、必ずしも Azure AD Premium ライセンスを割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e7f20-121">Configuring and using the expiration policy for Microsoft 365 groups requires you to possess but not necessarily assign Azure AD Premium licenses for the members of all groups to which the expiration policy is applied.</span></span> <span data-ttu-id="e7f20-122">詳細については、「 [Azure Active Directory Premium の](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7f20-122">For more information see [Getting started with Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).</span></span>

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a><span data-ttu-id="e7f20-123">Microsoft 365 グループの有効期限ポリシーを構成および使用できるユーザー</span><span class="sxs-lookup"><span data-stu-id="e7f20-123">Who can configure and use the Microsoft 365 groups expiration policy?</span></span>

|<span data-ttu-id="e7f20-124">役割</span><span class="sxs-lookup"><span data-stu-id="e7f20-124">Role</span></span>|<span data-ttu-id="e7f20-125">できること</span><span class="sxs-lookup"><span data-stu-id="e7f20-125">What they can do</span></span>|
|---------|---------|
|<span data-ttu-id="e7f20-126">グローバル管理者 (Azure、会社の管理者)、ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="e7f20-126">Global admin (in Azure, the Company administrator), User administrator</span></span>|<span data-ttu-id="e7f20-127">Microsoft 365 グループの有効期限ポリシーの設定を作成、読み取り、更新、または削除します。</span><span class="sxs-lookup"><span data-stu-id="e7f20-127">Create, read, update, or delete the Microsoft 365 groups expiration policy settings.</span></span>|
|<span data-ttu-id="e7f20-128">ユーザー</span><span class="sxs-lookup"><span data-stu-id="e7f20-128">User</span></span>|<span data-ttu-id="e7f20-129">自分が所有する Microsoft 365 グループを更新または[復元](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)する</span><span class="sxs-lookup"><span data-stu-id="e7f20-129">Renew or [restore](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) a Microsoft 365 group that they own</span></span>|

## <a name="how-to-set-the-expiration-policy"></a><span data-ttu-id="e7f20-130">有効期限ポリシーを設定する方法</span><span class="sxs-lookup"><span data-stu-id="e7f20-130">How to set the expiration policy</span></span>

<span data-ttu-id="e7f20-131">前述したように、有効期限は既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="e7f20-131">As noted above, expiry is turned off by default.</span></span> <span data-ttu-id="e7f20-132">管理者は有効期限ポリシーを有効にして、そのプロパティを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7f20-132">An administrator will have to enable the expiration policy and set the properties for it to take effect.</span></span> <span data-ttu-id="e7f20-133">これを有効にするには、 **Azure Active Directory (AAD)**  >  **グループ**の  >  **有効期限が切れる**ようにします。</span><span class="sxs-lookup"><span data-stu-id="e7f20-133">To enable it go to **Azure Active Directory (AAD)** > **Groups** > **Expiration**.</span></span> <span data-ttu-id="e7f20-134">ここでは、既定のグループの有効期間を設定して、最初と2番目の有効期限の通知がグループの所有者に移動するまでの時間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-134">Here you can set the default group lifetime and specify how far in advance you want the first and second expiration notifications to go to the group owner.</span></span>

<span data-ttu-id="e7f20-135">グループの有効期間は日単位で指定し、180、365、または指定したカスタム値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-135">The group lifetime is specified in days and can be set to 180, 365 or to a custom value that you specify.</span></span> <span data-ttu-id="e7f20-136">カスタム値は、少なくとも30日である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7f20-136">The custom value has to be at least 30 days.</span></span>

<span data-ttu-id="e7f20-137">グループに所有者がいない場合、有効期限メールは指定された管理者に送られます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-137">If the group does not have an owner, the expiration emails will go to a specified administrator.</span></span>

<span data-ttu-id="e7f20-138">すべてのグループに対してポリシーを設定するか、選択したグループのみを設定するか、または **[なし**] を選択して完全にオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-138">You can set the policy for all of your groups, only selected groups, or turn it off completely by selecting **None**.</span></span> <span data-ttu-id="e7f20-139">現在、グループごとに異なるポリシーを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e7f20-139">Note that currently you can't have different policies for different groups.</span></span>

![Azure Active Directory でのグループの有効期限設定のスクリーンショット](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiration-and-renewal-work"></a><span data-ttu-id="e7f20-141">有効期限と更新のしくみ</span><span class="sxs-lookup"><span data-stu-id="e7f20-141">How expiration and renewal work</span></span>

<span data-ttu-id="e7f20-142">有効期限ポリシーは次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="e7f20-142">The expiration policy works as follows:</span></span> 

- <span data-ttu-id="e7f20-143">有効期限の1か月前に、グループが作成されてから、または現在の更新サイクルの開始以降にグループのアクティビティがあるかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-143">About a month before expiration, the system will check to see if there has been any group activity since the group was created or since the beginning of the current renewal cycle.</span></span>

- <span data-ttu-id="e7f20-144">以前の動作が検出された場合、有効期限は、有効期限ポリシーで指定された日数でその時点で進められます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-144">If prior activity is detected, then the expiration date is advanced at that time by the number of days specified in the expiration policy.</span></span>

- <span data-ttu-id="e7f20-145">以前の動作が検出されない場合、システムは有効期限が切れるまで引き続きアクティビティを監視します。</span><span class="sxs-lookup"><span data-stu-id="e7f20-145">If prior activity is not detected, the system will continue to watch for activity until the expiration date.</span></span> <span data-ttu-id="e7f20-146">アクティビティが検出された場合、システムはその時点で、指定された金額だけ有効期限を繰り上げます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-146">If activity is detected, the system will advance the expiration date by the specified amount at that time.</span></span>

<span data-ttu-id="e7f20-147">グループの有効期限が切れるまで30日間、グループの所有者 (または所有者がいないグループに対して指定したメールアドレス) は、グループを簡単に更新できる電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="e7f20-147">30 days before the group expires, the group owners (or the email addresses that you specified for groups that don't have an owner) will receive an email allowing them to easily renew the group.</span></span> <span data-ttu-id="e7f20-148">更新されていない場合は、有効期限が切れるまで15日後にもう一度更新メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="e7f20-148">If they don't renew it, they'll receive another renewal email 15 days before expiration.</span></span> <span data-ttu-id="e7f20-149">まだ更新していない場合は、有効期限が切れる前に1日に1回のメール通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="e7f20-149">If they still haven't renewed it, they will receive one more email notification the day before expiration.</span></span> <span data-ttu-id="e7f20-150">(グループが更新されると、新しい有効期限が切れるまで30日前まで電子メール通知は送信されません)。</span><span class="sxs-lookup"><span data-stu-id="e7f20-150">(Once the group has been renewed, no further email reminders are sent until 30 days before the new expiration date.)</span></span>

<span data-ttu-id="e7f20-151">グループの所有者には、電子メールで通知されます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-151">Group owners will be notified via email.</span></span> <span data-ttu-id="e7f20-152">このグループが Planner、SharePoint、またはその他のアプリによって作成された場合、有効期限通知は常に電子メール経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-152">If the group was created via Planner, SharePoint, or any other app, the expiration notifications will always come via email.</span></span> <span data-ttu-id="e7f20-153">グループが Teams によって作成された場合、グループの所有者は [activity] セクションを通じて更新する通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="e7f20-153">If the group was created via Teams, the group owner will receive a notification to renew through the activity section.</span></span> <span data-ttu-id="e7f20-154">グループの所有者が有効な電子メールアドレスを持っていない場合は、グループの有効期限を有効にすることはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="e7f20-154">It's not recommended that you enable expiration on a group if your group owner doesn't have a valid email address.</span></span>

<span data-ttu-id="e7f20-155">何らかの理由で所有者または管理者がグループを更新せずに期限切れになった場合、自動更新が行われないと、グループが自動的に更新される要件を満たしていないため、管理者は有効期限が切れてから30日後までグループを復元することができます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-155">If for some reason none of the owners or admins renew the group before it expires, and automatic renewal does not occur due to the group not meeting the requirements to be automatically renewed, the admin can still restore the group for up to 30 days after expiration.</span></span> <span data-ttu-id="e7f20-156">詳細については[、「削除された Microsoft 365 グループを復元する](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7f20-156">For details see: [Restore a deleted Microsoft 365 group](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

## <a name="how-expiry-works-with-retention-policies"></a><span data-ttu-id="e7f20-157">保持ポリシーを使用した有効期限のしくみ</span><span class="sxs-lookup"><span data-stu-id="e7f20-157">How expiry works with retention policies</span></span>

<span data-ttu-id="e7f20-158">グループの [セキュリティとコンプライアンスセンター] でアイテム保持ポリシーをセットアップした場合、有効期限ポリシーは保持ポリシーとシームレスに連動します。</span><span class="sxs-lookup"><span data-stu-id="e7f20-158">If you have setup retention policy in Security and Compliance center for groups, expiration policy works seamlessly with retention policy.</span></span> <span data-ttu-id="e7f20-159">グループの有効期限が切れると、グループサイト内のグループの会話は、アイテム保持ポリシーで定義されている特定の日数だけ、保持コンテナーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="e7f20-159">When a group expires, the group's conversations in mail box and files in the group site are retained in the retention container for the specific number of days defined in the retention policy.</span></span> <span data-ttu-id="e7f20-160">ただし、有効期限が切れた後は、グループまたはそのコンテンツは表示されません。</span><span class="sxs-lookup"><span data-stu-id="e7f20-160">Users will not see the group, or its content, after expiration however.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e7f20-161">関連記事</span><span class="sxs-lookup"><span data-stu-id="e7f20-161">Related articles</span></span>

[<span data-ttu-id="e7f20-162">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="e7f20-162">Overview of retention policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

[<span data-ttu-id="e7f20-163">孤立グループに新しい所有者を割り当てる</span><span class="sxs-lookup"><span data-stu-id="e7f20-163">Assign a new owner to an orphaned group</span></span>](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

[<span data-ttu-id="e7f20-164">Microsoft 365 グループの有効期限を構成する</span><span class="sxs-lookup"><span data-stu-id="e7f20-164">Configure Microsoft 365 groups expiration</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)

[<span data-ttu-id="e7f20-165">アクティビティベースの自動更新</span><span class="sxs-lookup"><span data-stu-id="e7f20-165">Activity-based automatic renewal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)
