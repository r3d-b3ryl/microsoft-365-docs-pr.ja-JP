---
title: 管理者用 Office 365 グループの概要
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: v-teflor
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
description: Office 365 グループについて説明します。
ms.openlocfilehash: e7a65c41d4ecdbc91e163d9a84241ae549a2f9ec
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241314"
---
# <a name="overview-of-office-365-groups-for-administrators"></a><span data-ttu-id="14a25-103">管理者用 Office 365 グループの概要</span><span class="sxs-lookup"><span data-stu-id="14a25-103">Overview of Office 365 Groups for administrators</span></span>

<span data-ttu-id="14a25-104">Office 365 グループは、Microsoft 365 全体でチームワークを推進する基盤となるメンバーシップ サービスです。</span><span class="sxs-lookup"><span data-stu-id="14a25-104">Office 365 Groups is the foundational membership service that drives all teamwork across Microsoft 365.</span></span> <span data-ttu-id="14a25-105">Office 365 グループを使用すると、ユーザー グループに、共有するコラボレーション リソースのコレクションへのアクセス権を付与できます。</span><span class="sxs-lookup"><span data-stu-id="14a25-105">With Office 365 Groups, you can give a group of people access to a collection of collaboration resources for those people to share.</span></span> <span data-ttu-id="14a25-106">これらのリソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="14a25-106">These resources include:</span></span>

- <span data-ttu-id="14a25-107">共有の Outlook 受信トレイ</span><span class="sxs-lookup"><span data-stu-id="14a25-107">A shared Outlook inbox</span></span>
- <span data-ttu-id="14a25-108">共有の予定表</span><span class="sxs-lookup"><span data-stu-id="14a25-108">A shared calendar</span></span>
- <span data-ttu-id="14a25-109">SharePoint 文書ライブラリ</span><span class="sxs-lookup"><span data-stu-id="14a25-109">A SharePoint document library</span></span>
- <span data-ttu-id="14a25-110">Planner</span><span class="sxs-lookup"><span data-stu-id="14a25-110">A Planner</span></span>
- <span data-ttu-id="14a25-111">Power BI</span><span class="sxs-lookup"><span data-stu-id="14a25-111">Power BI</span></span>
- <span data-ttu-id="14a25-112">Yammer (グループが Yammer から作成された場合)</span><span class="sxs-lookup"><span data-stu-id="14a25-112">Yammer (if the group was created from Yammer)</span></span>
- <span data-ttu-id="14a25-113">チーム (グループが Teams から作成された場合)</span><span class="sxs-lookup"><span data-stu-id="14a25-113">A Team (if the group was created from Teams)</span></span>
- <span data-ttu-id="14a25-114">ロードマップ (Project for the web を所有している場合)</span><span class="sxs-lookup"><span data-stu-id="14a25-114">Roadmap (if you have Project for the web )</span></span>

<span data-ttu-id="14a25-115">Office 365 グループでは、グループにメンバーを追加すると、グループが提供するツールに必要なアクセス権が自動的に付与されるため、これら各リソースにアクセス権を手動で割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="14a25-115">With an Office 365 group, you don’t have to manually assign permissions to each of these resources, because adding members to the group automatically gives them the permissions they need to the tools that the group provides.</span></span>

<span data-ttu-id="14a25-116">[グループの作成を特定のユーザーに制限しない](manage-creation-of-groups.md)限り、Office 365 ユーザーはグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="14a25-116">Any Office 365 user can create a group unless you [limit group creation to a specific set of people](manage-creation-of-groups.md).</span></span> <span data-ttu-id="14a25-117">グループの作成を制限すると、グループを作成できないユーザーは、SharePoint サイト、Planners、またはチームを作成できなくなります。</span><span class="sxs-lookup"><span data-stu-id="14a25-117">Note that if you limit group creation, users who cannot create groups will not be able to create SharePoint sites, Planners, or teams.</span></span> <span data-ttu-id="14a25-118">これらのサービスでは、ユーザー コンテキストを使用してグループを作成できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="14a25-118">These services need to be able to create a group using the user context.</span></span> <span data-ttu-id="14a25-119">ユーザーは、グループのメンバーである限り、Planner でのタスクの作成や Outlook での会話への応答などのグループ アクティビティに参加できます。</span><span class="sxs-lookup"><span data-stu-id="14a25-119">Users can still participate in group activities, such as creating tasks in Planner or responding to conversations in Outlook, provided they are a member of the group.</span></span>

<span data-ttu-id="14a25-120">グループの役割は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="14a25-120">Groups have the following roles:</span></span>

- <span data-ttu-id="14a25-121">**所有者** - グループ所有者は、メンバーを追加または削除できます。また、共有受信トレイから会話を削除する機能や、グループに関するさまざまな設定を変更する機能など、独自のアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="14a25-121">**Owners** - Group owners can add or remove members and have unique permissions like the ability to delete conversations from the shared inbox or change different settings about the group.</span></span> <span data-ttu-id="14a25-122">グループ所有者は、グループ名の変更、説明や画像などの更新を行えます。</span><span class="sxs-lookup"><span data-stu-id="14a25-122">Group owners can rename the group, update the description or picture and more.</span></span>
- <span data-ttu-id="14a25-123">**メンバー** - メンバーはグループ内のすべてのデータにアクセスできますが、グループの設定は変更できません。</span><span class="sxs-lookup"><span data-stu-id="14a25-123">**Members** - Members can access everything in the group, but can't change group settings.</span></span>
- <span data-ttu-id="14a25-124">**ゲスト** - グループ ゲストは、組織外のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="14a25-124">**Guests** - Group guests are members who are from outside your organization.</span></span> <span data-ttu-id="14a25-125">既定では、グループ メンバーはゲストを招待してグループに参加させることができますが、[その設定は制御](manage-guest-access-in-groups.md)できます。</span><span class="sxs-lookup"><span data-stu-id="14a25-125">By default group members can invite guests to join your group, though you can [control that setting](manage-guest-access-in-groups.md).</span></span>

<span data-ttu-id="14a25-126">管理センターでグループを作成して管理できるのは、全体管理者とユーザー管理の管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="14a25-126">Only global admins and user management admins can create and manage groups in the admin center.</span></span> <span data-ttu-id="14a25-127">代理管理者 (たとえば、代理の管理者であるコンサルタント) になることはできません。</span><span class="sxs-lookup"><span data-stu-id="14a25-127">You can't be a delegated admin (for example, a consultant who is an admin on behalf of).</span></span>

<span data-ttu-id="14a25-128">管理者は次のことが可能です。</span><span class="sxs-lookup"><span data-stu-id="14a25-128">As an administrator, you can:</span></span>

- [<span data-ttu-id="14a25-129">グループを作成できるユーザーの指定</span><span class="sxs-lookup"><span data-stu-id="14a25-129">Specify who can create groups</span></span>](manage-creation-of-groups.md)
- [<span data-ttu-id="14a25-130">組織内のグループの名前付けポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="14a25-130">Create a naming policy for groups in your organization</span></span>](groups-naming-policy.md)
- [<span data-ttu-id="14a25-131">グループを作成するときに使用するドメインの選択</span><span class="sxs-lookup"><span data-stu-id="14a25-131">Choose which domain to use when creating a group</span></span>](choose-domain-to-create-groups.md)
- [<span data-ttu-id="14a25-132">グループへのゲスト アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="14a25-132">Manage guest access to groups</span></span>](manage-guest-access-in-groups.md)
- <span data-ttu-id="14a25-133">[削除したグループの復元](restore-deleted-group.md) (削除から 30 日以内)</span><span class="sxs-lookup"><span data-stu-id="14a25-133">[Recover a deleted group](restore-deleted-group.md) (within 30 days of deletion)</span></span>

<span data-ttu-id="14a25-134">より自動化された方法で Office 365 グループのライフサイクルを管理したい場合は、有効期限ポリシーを使用して特定の時間間隔でグループを期限切れにすることができます。</span><span class="sxs-lookup"><span data-stu-id="14a25-134">If you prefer a more automated way to manage the lifecycle of your Office 365 Groups you can use expiration policies to expire groups at a specific time interval.</span></span> <span data-ttu-id="14a25-135">グループの所有者は、グループが期限切れになる 30、15、1 日前に電子メールを受け取ります。これにより、グループがまだ必要な場合は、所有者は簡単に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="14a25-135">The group's owners will get an email 30, 15 and 1 day before the group expiration that allows them to easily renew the group if it's still needed.</span></span> <span data-ttu-id="14a25-136">「[Office 365 グループの有効期限ポリシー](office-365-groups-expiration-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14a25-136">See: [Office 365 Group Expiration Policy](office-365-groups-expiration-policy.md).</span></span>

<span data-ttu-id="14a25-137">グループは、Microsoft 365 管理センターから、または [PowerShell を使用](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)して管理できます。</span><span class="sxs-lookup"><span data-stu-id="14a25-137">You can administer your groups from the Microsoft 365 admin center or [by using PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).</span></span>

<span data-ttu-id="14a25-138">大規模企業など、多数のユーザーがいる場合は、さまざまな目的でグループを作成するユーザーが多数存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="14a25-138">If you have a lot of users, such as in a large corporation or enterprise, you may have many users who create groups for various purposes.</span></span> <span data-ttu-id="14a25-139">ベストプラクティスについては、「[Office 365 グループでのガバナンスを計画する](plan-for-groups-governance.md)」を参照することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="14a25-139">We highly recommend that you review [Plan for governance in Office 365 Groups](plan-for-groups-governance.md) for best practices.</span></span>

## <a name="group-limits"></a><span data-ttu-id="14a25-140">グループの制限</span><span class="sxs-lookup"><span data-stu-id="14a25-140">Group limits</span></span>

<span data-ttu-id="14a25-141">次の制限は Office 365 グループに適用されます。</span><span class="sxs-lookup"><span data-stu-id="14a25-141">The following limits apply to Office 365 Groups:</span></span>

|<span data-ttu-id="14a25-142">最大...</span><span class="sxs-lookup"><span data-stu-id="14a25-142">Maximum...</span></span>|<span data-ttu-id="14a25-143">値</span><span class="sxs-lookup"><span data-stu-id="14a25-143">Value</span></span>|
|:---------|:----|
|<span data-ttu-id="14a25-144">1 つのグループの所有者</span><span class="sxs-lookup"><span data-stu-id="14a25-144">Owners per group</span></span>|<span data-ttu-id="14a25-145">100</span><span class="sxs-lookup"><span data-stu-id="14a25-145">100</span></span>|
|<span data-ttu-id="14a25-146">ユーザーが作成できるグループ</span><span class="sxs-lookup"><span data-stu-id="14a25-146">Groups a user can create</span></span>|<span data-ttu-id="14a25-147">250</span><span class="sxs-lookup"><span data-stu-id="14a25-147">250</span></span>|
|<span data-ttu-id="14a25-148">管理者が作成できるグループ</span><span class="sxs-lookup"><span data-stu-id="14a25-148">Groups an admin can create</span></span>|<span data-ttu-id="14a25-149">既定のテナント数の上限は 500,000</span><span class="sxs-lookup"><span data-stu-id="14a25-149">Up to default tenant limit of 500K</span></span>|
|<span data-ttu-id="14a25-150">メンバー数 </span><span class="sxs-lookup"><span data-stu-id="14a25-150">Number of members</span></span>|<span data-ttu-id="14a25-151">1,000 人を超えます。ただし、グループ会話に同時にアクセスできるのは 1,000 人のみです。</span><span class="sxs-lookup"><span data-stu-id="14a25-151">More than 1,000, though only 1,000 can access the Group conversations concurrently.</span></span> <br><span data-ttu-id="14a25-152">Outlook で非常に大規模なグループの予定表や会話にアクセスする場合に、ユーザーが遅延を感じることがあります。</span><span class="sxs-lookup"><span data-stu-id="14a25-152">Users might notice delays when accessing the calendar and conversations in very large groups in Outlook.</span></span>|
|<span data-ttu-id="14a25-153">ユーザーがメンバーになれるグループの数</span><span class="sxs-lookup"><span data-stu-id="14a25-153">Number of Groups a user can be a member of</span></span>|<span data-ttu-id="14a25-154">1,000</span><span class="sxs-lookup"><span data-stu-id="14a25-154">1,000</span></span>|
|<span data-ttu-id="14a25-155">ファイルの記憶域</span><span class="sxs-lookup"><span data-stu-id="14a25-155">File storage</span></span>|<span data-ttu-id="14a25-156">各サブスクライブ ユーザーに 1 TB + 10 GB と、購入した追加記憶域。</span><span class="sxs-lookup"><span data-stu-id="14a25-156">1 Terabyte + 10 GB per subscribed user + any additional storage purchased.</span></span> <span data-ttu-id="14a25-157">追加の記憶域は無制限で購入できます。</span><span class="sxs-lookup"><span data-stu-id="14a25-157">You can purchase an unlimited amount of additional storage.</span></span>|
|<span data-ttu-id="14a25-158">グループ メールボックスのサイズ</span><span class="sxs-lookup"><span data-stu-id="14a25-158">Group Mailbox size</span></span>|<span data-ttu-id="14a25-159">50 GB</span><span class="sxs-lookup"><span data-stu-id="14a25-159">50 GB</span></span>|

<span data-ttu-id="14a25-160">現在、Office 365 組織が所有できる Office 365 グループの既定の最大数は 500,000 ですが、要求に応じて増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="14a25-160">The default maximum number of Office 365 Groups that an Office 365 organization can have is currently 500,000, but can be increased by request.</span></span> <span data-ttu-id="14a25-161">Office 365 グループの制限の詳細については、「[Office 365 グループ - 管理者向けヘルプ](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14a25-161">For more information on Office 365 Groups limits, see [Office 365 Groups - Admin help](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)</span></span>

<span data-ttu-id="14a25-162">グループの使用に関する実行可能な情報がある場合は、Office 365 グループを管理するとさらに効果的です。</span><span class="sxs-lookup"><span data-stu-id="14a25-162">Managing your Office 365 Groups is more effective when you have actionable information about Groups usage.</span></span> <span data-ttu-id="14a25-163"> Microsoft 管理センターには、ストレージの使用、所有しているアクティブなグループの数、グループを使用する方法なども表示できる報告ツールがあります。</span><span class="sxs-lookup"><span data-stu-id="14a25-163">The Microsoft 365 Admin Center has a reporting tool that can let you see things such as storage use, how many active Groups you have and even how your users are using the Groups.</span></span> <span data-ttu-id="14a25-164">詳細については、「[管理センターの Office 365 レポート](../activity-reports/office-365-groups.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14a25-164">See: [Office 365 Reports in the admin center](../activity-reports/office-365-groups.md) for more information.</span></span>

## <a name="which-office-365-plans-include-groups"></a><span data-ttu-id="14a25-165">グループを含む Office 365 のプラン</span><span class="sxs-lookup"><span data-stu-id="14a25-165">Which Office 365 plans include Groups?</span></span>

<span data-ttu-id="14a25-166">Exchange Online と SharePoint Online を備えた Office 365 サブスクリプションでは、グループをサポートします。</span><span class="sxs-lookup"><span data-stu-id="14a25-166">Any Office 365 subscription that has Exchange Online and SharePoint Online will support groups.</span></span> <span data-ttu-id="14a25-167">このサブスクリプションには、Business Essentials プランと Business Premium プラン、Enterprise E1、E3、E5 プランが含まれます。</span><span class="sxs-lookup"><span data-stu-id="14a25-167">That includes the Business Essentials and Business Premium plans, and the Enterprise E1, E3 and E5 plans.</span></span> <span data-ttu-id="14a25-168">グループは、グループを作成するユーザー (グループの「主催者」とも呼ばれる) のライセンスを引き受けます。</span><span class="sxs-lookup"><span data-stu-id="14a25-168">The Group takes on the licensing of the person who creates the Group (also known as the "organizer" of the Group).</span></span> <span data-ttu-id="14a25-169">主催者がグループが必要とする機能に対して適切なライセンスを持っている限り、そのライセンスはグループに送信されます。</span><span class="sxs-lookup"><span data-stu-id="14a25-169">As long as the organizer has the proper license for whatever features you want the Group to have, that license will convey to the Group.</span></span>

> [!NOTE]
> <span data-ttu-id="14a25-170">Office 365 サービスファミリおよびプランの詳細については、「 [office 365 プランのオプション](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="14a25-170">For more details about Office 365 service families and plans, please check [Office 365 plan options](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</span></span>

<span data-ttu-id="14a25-171">Exchange 専用プランを使用している場合、Outlook ではグループの共有の受信トレイ機能および共有の予定表機能は引き続き利用できますが、ドキュメント ライブラリやプランナーなど、その他の機能は利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="14a25-171">If you have an Exchange-only plan you can still get the shared Inbox and shared Calendar features of groups in Outlook but you won’t get the document library, Planner or any of the other capabilities.</span></span>

<span data-ttu-id="14a25-172">Office 365 グループは、Azure Active Directory (AAD) で動作します。</span><span class="sxs-lookup"><span data-stu-id="14a25-172">Office 365 Groups works with Azure Active Directory (AAD).</span></span> <span data-ttu-id="14a25-173">取得するグループ機能は、所有している Azure Active Directory サブスクリプションと、グループの主催者に割り当てられているライセンスによって異なります。</span><span class="sxs-lookup"><span data-stu-id="14a25-173">The Groups features you get depends on which Azure Active Directory subscription you have, and what license(s) is assigned to the organizer of the Group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14a25-174">すべてのグループ機能について、Azure AD Premium サブスクリプションがある場合、ユーザーは、AAD P1 ライセンスが割り当てられているかどうかに関係なく、グループに参加できます。</span><span class="sxs-lookup"><span data-stu-id="14a25-174">For all the Groups features, if you have an Azure AD Premium subscription, users can join the group whether or not they have an AAD P1 license assigned to them.</span></span> <span data-ttu-id="14a25-175">ライセンスは適用されません。</span><span class="sxs-lookup"><span data-stu-id="14a25-175">Licensing isn't enforced.</span></span>
> <span data-ttu-id="14a25-176">Microsoft では、定期的に利用状況レポートを生成し、ライセンスのないユーザーと、ライセンス要件に準拠するためにそのユーザーにライセンスを割り当てる必要があることをお知らせします。</span><span class="sxs-lookup"><span data-stu-id="14a25-176">Periodically we will generate usage reports that tell you which users are missing a license, and need one assigned to them to be compliant with the licensing requirements.</span></span> <span data-ttu-id="14a25-177">たとえば、ユーザーがライセンスを持っておらず、名前付けポリシーが適用されているグループに追加されるとします。</span><span class="sxs-lookup"><span data-stu-id="14a25-177">For example, let's say a user doesn't have a license and they are added to a group where the naming policy is enforced.</span></span> <span data-ttu-id="14a25-178">この場合、そのユーザーにライセンスが必要であることを示すフラグがレポートで設定されます。</span><span class="sxs-lookup"><span data-stu-id="14a25-178">The report will flag for you that they need a license.</span></span>

## <a name="related-articles"></a><span data-ttu-id="14a25-179">関連記事</span><span class="sxs-lookup"><span data-stu-id="14a25-179">Related articles</span></span>

[<span data-ttu-id="14a25-180">Office 365 グループの詳細</span><span class="sxs-lookup"><span data-stu-id="14a25-180">Learn about Office 365 Groups</span></span>](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="14a25-181">配布リストを Office 365 グループにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="14a25-181">Upgrade distribution lists to Office 365 Groups</span></span>](../manage/upgrade-distribution-lists.md)

[<span data-ttu-id="14a25-182">PowerShell で Office 365 グループを管理する</span><span class="sxs-lookup"><span data-stu-id="14a25-182">Manage Office 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[<span data-ttu-id="14a25-183">SharePoint Online の制限</span><span class="sxs-lookup"><span data-stu-id="14a25-183">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
