---
title: Microsoft 365 グループおよび Microsoft Teams の組織およびライフサイクルのガバナンスを計画する
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
description: Microsoft 365 のコラボレーションツールに関するリーンライフサイクルガバナンスオプション
ms.openlocfilehash: 4d779701d241fc7178ab759063be1b8cdf2e960c
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613022"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="21e03-103">Microsoft 365 グループおよび Microsoft Teams の組織およびライフサイクルのガバナンスを計画する</span><span class="sxs-lookup"><span data-stu-id="21e03-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="21e03-104">Microsoft 365 グループには、組織で必要とされるガバナンス機能を実装するための豊富なツールセットがあります。</span><span class="sxs-lookup"><span data-stu-id="21e03-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="21e03-105">次のセクションでは、機能について説明し、ベストプラクティスを推奨し、ガバナンスの要件を決定するための適切な質問とそれらを満たす方法についてのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="21e03-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="21e03-106">Microsoft 365 グループを作成できるユーザーを制御する</span><span class="sxs-lookup"><span data-stu-id="21e03-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="21e03-107">エンドユーザーは、Outlook、SharePoint、Teams、その他の環境を含む複数のエンドポイントからグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="21e03-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![画像の説明](../media/04.png)

<span data-ttu-id="21e03-109">グループの所有者を強化し、ユーザーが作業をより簡単に実行できるようにするには、セルフサービスを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="21e03-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="21e03-110">グループとチームの作成を制限すると、多くの Microsoft 365 サービスでは、サービスを機能させるためにグループを作成する必要があるため、ユーザーの生産性が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21e03-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="21e03-111">グループを作成するには、次のガバナンスオプションを考慮します。</span><span class="sxs-lookup"><span data-stu-id="21e03-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="21e03-112">グループの拡散を制限するには、グループの [有効期限ポリシー](microsoft-365-groups-expiration-policy.md) を使用して、使用されていないグループを自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="21e03-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="21e03-113">グループの作成をセキュリティグループのメンバーに制限します。たとえば、すべてのフルタイムの従業員を含む [動的メンバーシップを使用](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) します。</span><span class="sxs-lookup"><span data-stu-id="21e03-113">Limit group creation to members of a [security groups with dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="21e03-114">グループの作成をセキュリティグループに制限し、ユーザーがセキュリティグループのメンバーになるためには、組織のグループ使用ポリシーのトレーニングを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21e03-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="21e03-115">グループを作成できるユーザーを制限する場合は、これを構成する方法については、「 [Microsoft 365 グループを作成できるユーザーを管理](manage-creation-of-groups.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21e03-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="21e03-116">グループの削除、復元、およびアーカイブ</span><span class="sxs-lookup"><span data-stu-id="21e03-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="21e03-117">Microsoft 365 グループが削除されると、既定では30日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="21e03-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="21e03-118">グループを引き続き復元できるため、この 30 日の期間は "論理的な削除" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="21e03-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="21e03-119">30 日後、グループおよび関連付けられているコンテンツは完全に削除され、復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="21e03-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="21e03-120">保持ポリシーが設定されている場合、チャット、ファイル、またはメールを保持するには、グループを削除した後に、それらのアイテムを保持します。</span><span class="sxs-lookup"><span data-stu-id="21e03-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="21e03-121">詳細については、「 [アイテム保持ポリシーについ](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21e03-121">See [Learn about retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) for details.</span></span>

<span data-ttu-id="21e03-122">グループを削除するが、グループに接続された1つ以上のサービスのコンテンツを保持する場合は、「 [Archive groups, teams, And Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21e03-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="21e03-123">グループの名前付けポリシー</span><span class="sxs-lookup"><span data-stu-id="21e03-123">Group naming policy</span></span>

<span data-ttu-id="21e03-124">グループの名前付けポリシーは、次の2つの方法でグループを管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="21e03-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="21e03-125">プレフィックス/サフィックスの名前付けポリシーを使用すると、グループ名とそれに関連付けられた電子メールアドレスの先頭または末尾に、固定文字列または Azure AD 属性を強制することができます。</span><span class="sxs-lookup"><span data-stu-id="21e03-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="21e03-126">これにより、たとえば、部署名や地域をグループ名に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="21e03-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="21e03-127">ブロックされた単語のポリシーを使用すると、役職者の名前など、特定の単語がグループ名で使用されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="21e03-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="21e03-128">グループに接続されたサービスからグループを作成すると、名前付けポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="21e03-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="21e03-129">グループの名前付けポリシーの使用を決定した場合は、「 [Microsoft 365 groups ネーミング policy](groups-naming-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21e03-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="21e03-130">グループの有効期限ポリシー</span><span class="sxs-lookup"><span data-stu-id="21e03-130">Group expiration policy</span></span>

<span data-ttu-id="21e03-131">有効期限を指定して、その期間の終わりに到達し、更新されていないすべてのグループを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="21e03-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="21e03-132">有効期限は、グループが作成された時点、または最後に更新された日付から始まります。</span><span class="sxs-lookup"><span data-stu-id="21e03-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="21e03-133">グループの有効期限を設定すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="21e03-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="21e03-134">グループの所有者は、有効期限が近づくにつれてグループを更新するように通知されます。</span><span class="sxs-lookup"><span data-stu-id="21e03-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="21e03-135">アクティブなグループは自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="21e03-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="21e03-136">更新されていないグループは削除されます。</span><span class="sxs-lookup"><span data-stu-id="21e03-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="21e03-137">削除されたグループは、グループの所有者または管理者が30日以内に復元できます。</span><span class="sxs-lookup"><span data-stu-id="21e03-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="21e03-138">有効期限ポリシーは、使用されなくなったグループが削除されるようにすることで、グループの拡散を制限するのに適した方法です。</span><span class="sxs-lookup"><span data-stu-id="21e03-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="21e03-139">グループの有効期限ポリシーを作成する場合は、「 [Microsoft 365 グループの有効期限](microsoft-365-groups-expiration-policy.md)ポリシー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21e03-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="21e03-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="21e03-140">Related topics</span></span>

[<span data-ttu-id="21e03-141">コラボレーションガバナンスの計画のステップバイステップ</span><span class="sxs-lookup"><span data-stu-id="21e03-141">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="21e03-142">コラボレーションのガバナンス計画を作成する</span><span class="sxs-lookup"><span data-stu-id="21e03-142">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)
