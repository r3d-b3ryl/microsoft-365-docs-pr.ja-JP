---
title: 管理者向け Microsoft 365 グループの概要
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 グループについて説明します。
ms.openlocfilehash: b3bc0c30f4ac292da7af46678fc742854984db12
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925352"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a><span data-ttu-id="0de7c-103">管理者向け Microsoft 365 グループの概要</span><span class="sxs-lookup"><span data-stu-id="0de7c-103">Overview of Microsoft 365 Groups for administrators</span></span>

<span data-ttu-id="0de7c-104">Microsoft 365 グループは、Microsoft 365 全体のチームワークを促進する基盤のメンバーシップ サービスです。</span><span class="sxs-lookup"><span data-stu-id="0de7c-104">Microsoft 365 Groups is the foundational membership service that drives all teamwork across Microsoft 365.</span></span> <span data-ttu-id="0de7c-105">Microsoft 365 グループを使用すると、ユーザーのグループに共有リソースのコレクションへのアクセス権を与えます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-105">With Microsoft 365 Groups, you can give a group of people access to a collection of shared resources.</span></span> <span data-ttu-id="0de7c-106">これらのリソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0de7c-106">These resources include:</span></span>

- <span data-ttu-id="0de7c-107">共有の Outlook 受信トレイ</span><span class="sxs-lookup"><span data-stu-id="0de7c-107">A shared Outlook inbox</span></span>
- <span data-ttu-id="0de7c-108">共有の予定表</span><span class="sxs-lookup"><span data-stu-id="0de7c-108">A shared calendar</span></span>
- <span data-ttu-id="0de7c-109">SharePoint 文書ライブラリ</span><span class="sxs-lookup"><span data-stu-id="0de7c-109">A SharePoint document library</span></span>
- <span data-ttu-id="0de7c-110">Planner</span><span class="sxs-lookup"><span data-stu-id="0de7c-110">A Planner</span></span>
- <span data-ttu-id="0de7c-111">OneNote ノートブック</span><span class="sxs-lookup"><span data-stu-id="0de7c-111">A OneNote notebook</span></span>
- <span data-ttu-id="0de7c-112">Power BI</span><span class="sxs-lookup"><span data-stu-id="0de7c-112">Power BI</span></span>
- <span data-ttu-id="0de7c-113">Yammer (グループが Yammer から作成された場合)</span><span class="sxs-lookup"><span data-stu-id="0de7c-113">Yammer (if the group was created from Yammer)</span></span>
- <span data-ttu-id="0de7c-114">チーム (グループが Teams から作成された場合)</span><span class="sxs-lookup"><span data-stu-id="0de7c-114">A Team (if the group was created from Teams)</span></span>
- <span data-ttu-id="0de7c-115">ロードマップ (Project for the web を使用している場合)</span><span class="sxs-lookup"><span data-stu-id="0de7c-115">Roadmap (if you have Project for the web)</span></span>

<span data-ttu-id="0de7c-116">Microsoft 365 グループでは、これらのリソースごとにアクセス許可を手動で割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0de7c-116">With a Microsoft 365 group, you don't have to manually assign permissions to each of these resources.</span></span> <span data-ttu-id="0de7c-117">グループにユーザーを追加すると、必要なアクセス許可が自動的に付与されます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-117">Adding people to the group automatically gives them the permissions they need.</span></span>

<span data-ttu-id="0de7c-118">グループの作成を特定のユーザー のセットに制限しない限り、すべてのユーザー [がグループを作成できます](manage-creation-of-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="0de7c-118">Any user can create a group unless you [limit group creation to a specific set of people](manage-creation-of-groups.md).</span></span> <span data-ttu-id="0de7c-119">グループの作成を制限すると、グループを作成できないユーザーは SharePoint サイト、プランナー、またはチームを作成できません。</span><span class="sxs-lookup"><span data-stu-id="0de7c-119">If you limit group creation, users who cannot create groups will not be able to create SharePoint sites, Planners, or teams.</span></span> <span data-ttu-id="0de7c-120">これらのサービスでは、グループを作成するユーザーがグループを作成できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0de7c-120">These services require the people creating them to be able to create a group.</span></span> <span data-ttu-id="0de7c-121">ユーザーは、グループのメンバーである場合、Planner でのタスクの作成や Teams チャットの使用などのグループ アクティビティに引き続き参加できます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-121">Users can still participate in group activities, such as creating tasks in Planner or using Teams chat, provided they are a member of the group.</span></span>

<span data-ttu-id="0de7c-122">グループの役割は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0de7c-122">Groups have the following roles:</span></span>

- <span data-ttu-id="0de7c-123">**所有者** - グループ所有者は、メンバーを追加または削除できます。また、共有受信トレイから会話を削除する機能や、グループに関するさまざまな設定を変更する機能など、独自のアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="0de7c-123">**Owners** - Group owners can add or remove members and have unique permissions like the ability to delete conversations from the shared inbox or change different settings about the group.</span></span> <span data-ttu-id="0de7c-124">グループ所有者は、グループ名の変更、説明や画像などの更新を行えます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-124">Group owners can rename the group, update the description or picture and more.</span></span>
- <span data-ttu-id="0de7c-125">**メンバー** - メンバーはグループ内のすべてのデータにアクセスできますが、グループの設定は変更できません。</span><span class="sxs-lookup"><span data-stu-id="0de7c-125">**Members** - Members can access everything in the group, but can't change group settings.</span></span> <span data-ttu-id="0de7c-126">既定では、グループ メンバーはゲストを招待してグループに参加させることができますが、[その設定は制御](manage-guest-access-in-groups.md)できます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-126">By default group members can invite guests to join your group, though you can [control that setting](manage-guest-access-in-groups.md).</span></span>
- <span data-ttu-id="0de7c-127">**ゲスト** - グループ ゲストは、組織外のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="0de7c-127">**Guests** - Group guests are members who are from outside your organization.</span></span>

<span data-ttu-id="0de7c-128">Microsoft 365 管理センターでグループを作成および管理できるのは、グローバル管理者、ユーザー管理者、およびグループ管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="0de7c-128">Only global admins, user admins, and groups admins can create and manage groups in the Microsoft 365 admin center.</span></span> <span data-ttu-id="0de7c-129">代理管理者 (たとえば、代理の管理者であるコンサルタント) になることはできません。</span><span class="sxs-lookup"><span data-stu-id="0de7c-129">You can't be a delegated admin (for example, a consultant who is an admin on behalf of).</span></span>

<span data-ttu-id="0de7c-130">管理者は次のことが可能です。</span><span class="sxs-lookup"><span data-stu-id="0de7c-130">As an administrator, you can:</span></span>

- [<span data-ttu-id="0de7c-131">グループを作成できるユーザーの指定</span><span class="sxs-lookup"><span data-stu-id="0de7c-131">Specify who can create groups</span></span>](manage-creation-of-groups.md)
- [<span data-ttu-id="0de7c-132">組織内のグループの名前付けポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="0de7c-132">Create a naming policy for groups in your organization</span></span>](groups-naming-policy.md)
- [<span data-ttu-id="0de7c-133">グループを作成するときに使用するドメインの選択</span><span class="sxs-lookup"><span data-stu-id="0de7c-133">Choose which domain to use when creating a group</span></span>](choose-domain-to-create-groups.md)
- [<span data-ttu-id="0de7c-134">グループへのゲスト アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="0de7c-134">Manage guest access to groups</span></span>](manage-guest-access-in-groups.md)
- <span data-ttu-id="0de7c-135">[削除したグループの復元](restore-deleted-group.md) (削除から 30 日以内)</span><span class="sxs-lookup"><span data-stu-id="0de7c-135">[Recover a deleted group](restore-deleted-group.md) (within 30 days of deletion)</span></span>

<span data-ttu-id="0de7c-136">Microsoft 365 グループのライフサイクルを管理するより自動化された方法が必要な場合は、有効期限ポリシーを使用して、特定の時間間隔でグループを期限切れにできます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-136">If you prefer a more automated way to manage the lifecycle of your Microsoft 365 groups, you can use expiration policies to expire groups at a specific time interval.</span></span> <span data-ttu-id="0de7c-137">グループの所有者は、グループの有効期限の 30 日、15 日前にメールを受け取り、必要に応じてグループを更新できます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-137">The group's owners will get an email 30, 15, and 1 day before the group expiration that allows them to renew the group if it's still needed.</span></span> <span data-ttu-id="0de7c-138">参照: [Microsoft 365 グループの有効期限ポリシー](office-365-groups-expiration-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="0de7c-138">See: [Microsoft 365 group Expiration Policy](office-365-groups-expiration-policy.md).</span></span>

<span data-ttu-id="0de7c-139">グループは、Microsoft 365 管理センターから、または [PowerShell を使用](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershel)して管理できます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-139">You can administer your groups from the Microsoft 365 admin center or [by using PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershel).</span></span>

<span data-ttu-id="0de7c-140">大企業や企業など、多数のユーザーが含む場合は、さまざまな目的でグループを作成するユーザーが多い場合があります。</span><span class="sxs-lookup"><span data-stu-id="0de7c-140">If you have many users, such as in a large corporation or enterprise, you may have many users who create groups for various purposes.</span></span> <span data-ttu-id="0de7c-141">ベスト プラクティスについては [、「Microsoft 365](plan-for-groups-governance.md) グループでのガバナンスの計画」を確認することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0de7c-141">We highly recommend that you review [Plan for governance in Microsoft 365 groups](plan-for-groups-governance.md) for best practices.</span></span>

## <a name="group-limits"></a><span data-ttu-id="0de7c-142">グループの制限</span><span class="sxs-lookup"><span data-stu-id="0de7c-142">Group limits</span></span>

<span data-ttu-id="0de7c-143">Microsoft 365 グループには、次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-143">The following limits apply to Microsoft 365 Groups:</span></span>

|<span data-ttu-id="0de7c-144">最大...</span><span class="sxs-lookup"><span data-stu-id="0de7c-144">Maximum...</span></span>|<span data-ttu-id="0de7c-145">値</span><span class="sxs-lookup"><span data-stu-id="0de7c-145">Value</span></span>|
|:---------|:----|
|<span data-ttu-id="0de7c-146">1 つのグループの所有者</span><span class="sxs-lookup"><span data-stu-id="0de7c-146">Owners per group</span></span>|<span data-ttu-id="0de7c-147">100</span><span class="sxs-lookup"><span data-stu-id="0de7c-147">100</span></span>|
|<span data-ttu-id="0de7c-148">ユーザーが作成できるグループ</span><span class="sxs-lookup"><span data-stu-id="0de7c-148">Groups a user can create</span></span>|<span data-ttu-id="0de7c-149">250</span><span class="sxs-lookup"><span data-stu-id="0de7c-149">250</span></span>|
|<span data-ttu-id="0de7c-150">管理者が作成できるグループ</span><span class="sxs-lookup"><span data-stu-id="0de7c-150">Groups an admin can create</span></span>|<span data-ttu-id="0de7c-151">最大 500 K の既定のテナント制限</span><span class="sxs-lookup"><span data-stu-id="0de7c-151">Up to default tenant limit of 500 K</span></span>|
|<span data-ttu-id="0de7c-152">メンバー数 </span><span class="sxs-lookup"><span data-stu-id="0de7c-152">Number of members</span></span>|<span data-ttu-id="0de7c-153">1,000 人を超えます。ただし、グループ会話に同時にアクセスできるのは 1,000 人のみです。</span><span class="sxs-lookup"><span data-stu-id="0de7c-153">More than 1,000, though only 1,000 can access the Group conversations concurrently.</span></span> <br><span data-ttu-id="0de7c-154">ユーザーは、Outlook の大規模なグループの予定表や会話にアクセスするときに遅延に気付く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0de7c-154">Users might notice delays when accessing the calendar and conversations in large groups in Outlook.</span></span>|
|<span data-ttu-id="0de7c-155">ユーザーがメンバーになれるグループの数</span><span class="sxs-lookup"><span data-stu-id="0de7c-155">Number of Groups a user can be a member of</span></span>|<span data-ttu-id="0de7c-156">7,000</span><span class="sxs-lookup"><span data-stu-id="0de7c-156">7,000</span></span>|
|<span data-ttu-id="0de7c-157">ファイルの記憶域</span><span class="sxs-lookup"><span data-stu-id="0de7c-157">File storage</span></span>|<span data-ttu-id="0de7c-158">サブスクライブしているユーザーごとに 1 テラバイト + 10 GB + 購入したその他のストレージ。</span><span class="sxs-lookup"><span data-stu-id="0de7c-158">1 Terabyte + 10 GB per subscribed user + any other storage purchased.</span></span> <span data-ttu-id="0de7c-159">追加の記憶域を無制限に購入できます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-159">You can purchase an unlimited amount of extra storage.</span></span>|
|<span data-ttu-id="0de7c-160">グループ メールボックスのサイズ</span><span class="sxs-lookup"><span data-stu-id="0de7c-160">Group Mailbox size</span></span>|<span data-ttu-id="0de7c-161">50 GB</span><span class="sxs-lookup"><span data-stu-id="0de7c-161">50 GB</span></span>|

<span data-ttu-id="0de7c-162">組織が持つ Microsoft 365 グループの既定の最大数は 500,000 です。</span><span class="sxs-lookup"><span data-stu-id="0de7c-162">The default maximum number of Microsoft 365 groups that an organization can have is 500,000.</span></span> <span data-ttu-id="0de7c-163">既定の制限を超える場合は、Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="0de7c-163">To go beyond the default limit, you must contact Microsoft Support.</span></span> <span data-ttu-id="0de7c-164">Microsoft 365 グループの制限の詳細については [、Microsoft 365 グループ -](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)管理者向けヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0de7c-164">For more information on Microsoft 365 Groups limits, see [Microsoft 365 Groups - Admin help](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span></span>

<span data-ttu-id="0de7c-165">グループの使用状況に関する操作可能な情報がある場合は、Microsoft 365 グループの管理が効果的です。</span><span class="sxs-lookup"><span data-stu-id="0de7c-165">Managing your Microsoft 365 groups is more effective when you have actionable information about groups usage.</span></span> <span data-ttu-id="0de7c-166">Microsoft 365 管理センターには、記憶域の使用、アクティブなグループの数、ユーザーがグループを使用している方法を確認できるレポート ツールがあります。</span><span class="sxs-lookup"><span data-stu-id="0de7c-166">The Microsoft 365 admin center has a reporting tool that lets you see storage use, how many active groups you have, and how users are using the groups.</span></span> <span data-ttu-id="0de7c-167">詳細については [、管理センターの Microsoft 365 レポート](../activity-reports/office-365-groups.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0de7c-167">See: [Microsoft 365 Reports in the admin center](../activity-reports/office-365-groups.md) for more information.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="0de7c-168">秘密度ラベル</span><span class="sxs-lookup"><span data-stu-id="0de7c-168">Sensitivity labels</span></span>

<span data-ttu-id="0de7c-169">組織内のユーザーが Microsoft 365 グループを作成するときに設定できる、感度ラベルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-169">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 group.</span></span> <span data-ttu-id="0de7c-170">感度ラベルを使用すると、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-170">With sensitivity labels, you can configure:</span></span> 

- <span data-ttu-id="0de7c-171">プライバシー (パブリックまたはプライベート)</span><span class="sxs-lookup"><span data-stu-id="0de7c-171">Privacy (public or private)</span></span>
- <span data-ttu-id="0de7c-172">外部ユーザーのアクセス</span><span class="sxs-lookup"><span data-stu-id="0de7c-172">External users access</span></span>
- <span data-ttu-id="0de7c-173">管理されていないデバイスへのアクセス</span><span class="sxs-lookup"><span data-stu-id="0de7c-173">Unmanaged device access</span></span>

<span data-ttu-id="0de7c-174">たとえば、高機密というラベルを作成し、このラベルで作成されたグループをプライベートにし、外部ユーザーを許可しないという指定を行います。</span><span class="sxs-lookup"><span data-stu-id="0de7c-174">For example, you can create a label called *Highly Confidential* and specify that any group created with this label will be private and not allow external users.</span></span> <span data-ttu-id="0de7c-175">組織内のユーザーがグループの作成時にこのラベルを選択すると、グループはプライベートに設定され、グループメンバーはグループに外部ユーザーを追加できない。</span><span class="sxs-lookup"><span data-stu-id="0de7c-175">When users in your organization select this label during group creation, the group will be set to private and group members will not be allowed to add external users to the group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0de7c-176">現在分類ラベルを使用している場合、そのラベルは、グループを作成するユーザーは、そのラベルを使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0de7c-176">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span> 

<span data-ttu-id="0de7c-177">区別ラベルの作成、管理、および使用の詳細については、「Microsoft [Teams、Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)グループ、および SharePoint サイトのコンテンツを保護するために、感度ラベルを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0de7c-177">For information about creating, managing, and using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="which-microsoft-365-plans-include-groups"></a><span data-ttu-id="0de7c-178">グループが含まれる Microsoft 365 プランは何ですか?</span><span class="sxs-lookup"><span data-stu-id="0de7c-178">Which Microsoft 365 plans include groups?</span></span>

<span data-ttu-id="0de7c-179">Exchange Online と SharePoint Online を持つ Microsoft 365 サブスクリプションは、グループをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0de7c-179">Any Microsoft 365 subscription that has Exchange Online and SharePoint Online will support groups.</span></span> <span data-ttu-id="0de7c-180">これには、Business Essentials プランと Business Premium プラン、Enterprise E1、E3、および E5 プランが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-180">That includes the Business Essentials and Business Premium plans, and the Enterprise E1, E3, and E5 plans.</span></span> <span data-ttu-id="0de7c-181">グループは、グループを作成したユーザー (グループの "開催者" とも呼ばれる) のライセンスを引き受けます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-181">The group takes on the licensing of the person who creates the group (also known as the "organizer" of the group).</span></span> <span data-ttu-id="0de7c-182">開催者がグループに必要な機能に対して適切なライセンスを持っている限り、そのライセンスはグループに伝達されます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-182">As long as the organizer has the proper license for whatever features you want the group to have, that license will convey to the group.</span></span>

> [!NOTE]
> <span data-ttu-id="0de7c-183">Microsoft 365 サービス ファミリとプランの詳細については [、Microsoft 365 プランのオプションを参照してください](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)。</span><span class="sxs-lookup"><span data-stu-id="0de7c-183">For more details about Microsoft 365 service families and plans, see [Microsoft 365 plan options](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).</span></span>

<span data-ttu-id="0de7c-184">Exchange 専用プランを使用している場合でも、Outlook のグループの共有受信トレイ機能と共有予定表機能を取得できますが、ドキュメント ライブラリ、Planner、その他の機能は取得できません。</span><span class="sxs-lookup"><span data-stu-id="0de7c-184">If you have an Exchange-only plan you can still get the shared inbox and shared calendar features of groups in Outlook but you won't get the document library, Planner or any of the other capabilities.</span></span>

<span data-ttu-id="0de7c-185">Microsoft 365 グループは Azure Active Directory で動作します。</span><span class="sxs-lookup"><span data-stu-id="0de7c-185">Microsoft 365 groups work with Azure Active Directory.</span></span> <span data-ttu-id="0de7c-186">取得するグループ機能は、使用している Azure Active Directory サブスクリプション、およびグループの開催者に割り当てられるライセンスによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0de7c-186">The groups features you get depends on which Azure Active Directory subscription you have, and what licenses are assigned to the organizer of the group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0de7c-187">すべてのグループ機能について、Azure AD Premium サブスクリプションを持っている場合、ユーザーは AAD P1 ライセンスが割り当てられているかどうかに関わるかどうかに関してグループに参加できます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-187">For all the groups features, if you have an Azure AD Premium subscription, users can join the group whether or not they have an AAD P1 license assigned to them.</span></span> <span data-ttu-id="0de7c-188">ライセンスは適用されません。</span><span class="sxs-lookup"><span data-stu-id="0de7c-188">Licensing isn't enforced.</span></span>
> <span data-ttu-id="0de7c-189">Microsoft では、定期的に利用状況レポートを生成し、ライセンスのないユーザーと、ライセンス要件に準拠するためにそのユーザーにライセンスを割り当てる必要があることをお知らせします。</span><span class="sxs-lookup"><span data-stu-id="0de7c-189">Periodically we will generate usage reports that tell you which users are missing a license, and need one assigned to them to be compliant with the licensing requirements.</span></span> <span data-ttu-id="0de7c-190">たとえば、ユーザーがライセンスを持っておらず、名前付けポリシーが適用されているグループに追加されるとします。</span><span class="sxs-lookup"><span data-stu-id="0de7c-190">For example, let's say a user doesn't have a license and they are added to a group where the naming policy is enforced.</span></span> <span data-ttu-id="0de7c-191">この場合、そのユーザーにライセンスが必要であることを示すフラグがレポートで設定されます。</span><span class="sxs-lookup"><span data-stu-id="0de7c-191">The report will flag for you that they need a license.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0de7c-192">関連記事</span><span class="sxs-lookup"><span data-stu-id="0de7c-192">Related articles</span></span>

[<span data-ttu-id="0de7c-193">Microsoft 365 グループについて</span><span class="sxs-lookup"><span data-stu-id="0de7c-193">Learn about Microsoft 365 Groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="0de7c-194">配布リストを Microsoft 365 グループにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="0de7c-194">Upgrade distribution lists to Microsoft 365 Groups</span></span>](../manage/upgrade-distribution-lists.md)

[<span data-ttu-id="0de7c-195">PowerShell を使用して Microsoft 365 グループを管理する</span><span class="sxs-lookup"><span data-stu-id="0de7c-195">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[<span data-ttu-id="0de7c-196">SharePoint Online の制限</span><span class="sxs-lookup"><span data-stu-id="0de7c-196">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
