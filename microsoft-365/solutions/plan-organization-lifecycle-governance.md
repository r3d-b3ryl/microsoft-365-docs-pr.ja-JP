---
title: グループとグループの組織とライフサイクルのガバナンスMicrosoft 365計画Microsoft Teams
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: グループ内のコラボレーション ツールのライフサイクル ガバナンス オプションに関するMicrosoft 365
ms.openlocfilehash: ff3a3a60ce49c423410b51dc6fee2137ebf8952a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907930"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="32eb8-103">グループとグループの組織とライフサイクルのガバナンスMicrosoft 365計画Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="32eb8-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="32eb8-104">Microsoft 365グループには、組織が必要とするガバナンス機能を実装するための豊富なツールセットがあります。</span><span class="sxs-lookup"><span data-stu-id="32eb8-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="32eb8-105">次のセクションでは、機能について説明し、ベスト プラクティスを推奨し、ガバナンスの要件とそれらを満たす方法を決定するための適切な質問をするためのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="32eb8-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="32eb8-106">グループを作成できるユーザー Microsoft 365する</span><span class="sxs-lookup"><span data-stu-id="32eb8-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="32eb8-107">グループは、エンド ユーザーが複数のエンド ポイント (Outlook、SharePoint、Teamsなど) から作成できます。</span><span class="sxs-lookup"><span data-stu-id="32eb8-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![画像の説明](../media/04.png)

<span data-ttu-id="32eb8-109">グループの所有者に権限を与え、ユーザーが作業を簡単に行えるのを助けるために、セルフサービスを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="32eb8-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="32eb8-110">グループとチームの作成を制限すると、サービスが機能するために多Microsoft 365グループを作成する必要が生じ、ユーザーの生産性が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="32eb8-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="32eb8-111">グループの作成には、次のガバナンス オプションを検討してください。</span><span class="sxs-lookup"><span data-stu-id="32eb8-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="32eb8-112">グループのスプロールを制限するには、グループ有効期限ポリシーを [使用](microsoft-365-groups-expiration-policy.md) して、使用されていないグループを自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="32eb8-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="32eb8-113">グループの作成を、すべての正[](/azure/active-directory/users-groups-roles/groups-create-rule)社員など、動的メンバーシップを持つセキュリティ グループのメンバーに制限します。</span><span class="sxs-lookup"><span data-stu-id="32eb8-113">Limit group creation to members of a [security groups with dynamic membership](/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="32eb8-114">グループの作成をセキュリティ グループに制限し、ユーザーがセキュリティ グループのメンバーになるために組織のグループ使用ポリシーのトレーニングを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32eb8-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="32eb8-115">グループを作成できるユーザーを制限する場合は、「[](manage-creation-of-groups.md)グループを作成できるユーザー Microsoft 365を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32eb8-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="32eb8-116">グループの削除、復元、およびアーカイブ</span><span class="sxs-lookup"><span data-stu-id="32eb8-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="32eb8-117">ユーザー グループMicrosoft 365削除された場合、既定では 30 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="32eb8-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="32eb8-118">グループを引き続き復元できるため、この 30 日の期間は "論理的な削除" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="32eb8-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="32eb8-119">30 日後、グループおよび関連付けられているコンテンツは完全に削除され、復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="32eb8-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="32eb8-120">チャット、ファイル、またはメールを保持するための保持ポリシーが設定されている場合、それらのアイテムはグループが削除された後も保持されます。</span><span class="sxs-lookup"><span data-stu-id="32eb8-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="32eb8-121">詳細については [、「アイテム保持ポリシーについて」](../compliance/retention.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32eb8-121">See [Learn about retention policies](../compliance/retention.md) for details.</span></span>

<span data-ttu-id="32eb8-122">グループを削除するが、1 つ以上のグループに接続されたサービスからコンテンツを保持する場合は、「グループ[、](end-life-cycle-groups-teams-sites-yammer.md)チーム、およびグループのアーカイブ」を参照Yammerを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32eb8-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="32eb8-123">グループの名前付けポリシー</span><span class="sxs-lookup"><span data-stu-id="32eb8-123">Group naming policy</span></span>

<span data-ttu-id="32eb8-124">グループの名前付けポリシーは、次の 2 つの方法でグループを管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="32eb8-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="32eb8-125">プレフィックス/サフィックスの名前付けポリシーを使用して、グループ名とその関連付けられた電子メール アドレスの先頭または末尾に固定文字列または Azure AD 属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="32eb8-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="32eb8-126">これにより、部署名や地域をグループ名に含めることが可能です。</span><span class="sxs-lookup"><span data-stu-id="32eb8-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="32eb8-127">ブロックされた単語ポリシーは、役員の名前など、特定の単語がグループ名で使用されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="32eb8-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="32eb8-128">名前付けポリシーは、グループに接続されたサービスからグループが作成される場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="32eb8-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="32eb8-129">グループに名前付けポリシーを使用する場合は、「グループ[の名前付けMicrosoft 365」を参照してください](groups-naming-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="32eb8-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="32eb8-130">グループの有効期限ポリシー</span><span class="sxs-lookup"><span data-stu-id="32eb8-130">Group expiration policy</span></span>

<span data-ttu-id="32eb8-131">有効期限を指定すると、その期間の終わりに達し、更新されないグループは削除されます。</span><span class="sxs-lookup"><span data-stu-id="32eb8-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="32eb8-132">有効期限は、グループが作成された日、または最後に更新された日付から始まります。</span><span class="sxs-lookup"><span data-stu-id="32eb8-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="32eb8-133">グループの有効期限を設定したら、次の条件を実行します。</span><span class="sxs-lookup"><span data-stu-id="32eb8-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="32eb8-134">グループの所有者は、有効期限が近付く間にグループを更新する通知を受け取る。</span><span class="sxs-lookup"><span data-stu-id="32eb8-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="32eb8-135">アクティブ なグループは自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="32eb8-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="32eb8-136">更新されていないグループは削除されます。</span><span class="sxs-lookup"><span data-stu-id="32eb8-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="32eb8-137">削除されたグループは、グループの所有者または管理者が 30 日以内に復元できます。</span><span class="sxs-lookup"><span data-stu-id="32eb8-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="32eb8-138">有効期限ポリシーは、使用されなくなったグループを確実に削除することで、グループのスプロールを制限する優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="32eb8-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="32eb8-139">グループ有効期限ポリシーを作成する場合は、「グループ有効期限ポリシー Microsoft 365[を参照してください](microsoft-365-groups-expiration-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="32eb8-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="32eb8-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="32eb8-140">Related topics</span></span>

[<span data-ttu-id="32eb8-141">コラボレーション ガバナンス計画のステップ バイ ステップ</span><span class="sxs-lookup"><span data-stu-id="32eb8-141">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="32eb8-142">コラボレーション ガバナンス 計画の作成</span><span class="sxs-lookup"><span data-stu-id="32eb8-142">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)