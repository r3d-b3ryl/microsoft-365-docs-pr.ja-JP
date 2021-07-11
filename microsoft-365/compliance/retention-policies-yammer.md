---
title: Yammer の保持の詳細
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Yammer に適用されるアイテム保持ポリシーについて説明します。
ms.openlocfilehash: 1398bf385631967d92de760924ef94e2b3c16441
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362296"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="b3a7e-103">Yammer の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="b3a7e-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="b3a7e-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="b3a7e-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="b3a7e-105">この機能は現在プレビュー段階であり、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-105">This feature is in preview and subject to change.</span></span>

<span data-ttu-id="b3a7e-106">この記事の情報は[保持の詳細](retention.md)に関する記事を補足するもので、Yammer に固有の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-106">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="b3a7e-107">その他のワークロードについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-107">For other workloads, see:</span></span>

- [<span data-ttu-id="b3a7e-108">SharePoint と OneDrive の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="b3a7e-108">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="b3a7e-109">Microsoft Teams の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="b3a7e-109">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="b3a7e-110">Exchange の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="b3a7e-110">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="b3a7e-111">保持と削除の対象となる機能</span><span class="sxs-lookup"><span data-stu-id="b3a7e-111">What's included for retention and deletion</span></span>

<span data-ttu-id="b3a7e-112">コミュニティ メッセージとユーザー メッセージの Yammer アイテムは、Yammer のアイテム保持ポリシーを使用して保持および削除できます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-112">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and user messages.</span></span>

<span data-ttu-id="b3a7e-113">絵文字の形で他人からの反応はこれらのメッセージに含まれていません。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-113">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="b3a7e-114">Yammer での保持のしくみ</span><span class="sxs-lookup"><span data-stu-id="b3a7e-114">How retention works with Yammer</span></span>

<span data-ttu-id="b3a7e-115">このセクションを使用して、コンプライアンス要件がバックエンド ストレージとプロセスによってどのように満たされているかを説明します。現在、Yammer アプリに表示されているメッセージではなく、電子情報開示ツールで確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-115">Use this section to understand how your compliance requirements are met by backend storage and processes, and should be verified by eDiscovery tools rather than by messages that are currently visible in the Yammer app.</span></span>

<span data-ttu-id="b3a7e-116">アイテム保持ポリシーを使用して、Yammer のコミュニティ メッセージとユーザー メッセージのデータを保持し、これらのメッセージを削除できます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-116">You can use a retention policy to retain data from community messages and user messages in Yammer, and delete these messages.</span></span> <span data-ttu-id="b3a7e-117">バックグラウンドでは、Exchange メールボックスを使用してこれらのメッセージからコピーされたデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-117">Behind the scenes, Exchange mailboxes are used to store data copied from these messages.</span></span> <span data-ttu-id="b3a7e-118">Yammer ユーザーのメッセージのデータは、ユーザー メッセージに含まれる各ユーザーのメールボックスの隠しフォルダーに保存され、グループ メールボックスの同様の隠しフォルダーがコミュニティ メッセージに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-118">Data from Yammer user messages is stored in a hidden folder in the mailbox of each user included in the user message, and a similar hidden folder in a group mailbox is used for community messages.</span></span>

<span data-ttu-id="b3a7e-119">コミュニティ メッセージのコピーは、ユーザーに @メンションしたり、ユーザーに返信を通知したりするときに、ユーザー メールボックスの隠しフォルダーに保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-119">Copies of community messages can also be stored in the hidden folder of user mailboxes when they @ mention users or notify the user of a reply.</span></span> <span data-ttu-id="b3a7e-120">これらのメッセージはコミュニティ メッセージとして発信されますが、Yammer ユーザーのメッセージのアイテム保持ポリシーには、コミュニティ メッセージのコピーが含まれることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-120">Although these messages originate as a community message, a retention policy for Yammer user messages will often include copies of community messages.</span></span>

<span data-ttu-id="b3a7e-121">これらの隠しフォルダーは、ユーザーまたは管理者が直接アクセスできるようには設計されていませんが、代わりに、コンプライアンス管理者が電子情報開示ツールで検索できるデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-121">These hidden folders are not designed to be directly accessible to users or administrators, but instead, store data that compliance administrators can search with eDiscovery tools.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3a7e-122">コミュニティ メッセージのコピーはユーザー メールボックスにも保存できるため、Yammer ユーザーのメッセージの削除アクションを含むアイテム保持ポリシーにより、元のコミュニティ メッセージが Yammer アプリのユーザーに表示されなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-122">Because copies of community messages can also be stored in user mailboxes, a retention policy with a delete action for Yammer user messages can result in the original community message no longer visible to users in the Yammer app.</span></span>
> 
> <span data-ttu-id="b3a7e-123">ただし、元のメッセージのコピーは、コミュニティ グループ メールボックスの隠しフォルダーに引き続き存在し、コンプライアンスの目的で電子情報開示検索を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-123">However, a copy of the original message is still available in the hidden folder of the community group mailbox, and accessible with eDiscovery searches for compliance purposes.</span></span>

<span data-ttu-id="b3a7e-124">Yammer のメッセージは、Exchange メールボックスに対して構成されているアイテム保持ポリシーの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-124">Yammer messages are not affected by retention policies that are configured for Exchange mailboxes.</span></span> <span data-ttu-id="b3a7e-125">Yammer のメッセージは Exchange に保存されますが、この Yammer のデータは、**Yammer コミュニティのメッセージ** と **Yammer ユーザーのメッセージ** の場所に対して構成されているアイテム保持ポリシーによってのみ含まれます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-125">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer user messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="b3a7e-126">ユーザーが Yammer のデータを保持するアクティブなアイテム保持ポリシーに含まれている場合、このポリシーに含まれるユーザーのメールボックスを削除すると、Yammer のデータを保持するためにメールボックスは[非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)に変換されます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-126">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="b3a7e-127">ユーザーのこの Yammer データを保持する必要がない場合は、メールボックスを削除する前に、アイテム保持ポリシーからそのユーザー アカウントを除外します。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-127">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="b3a7e-128">Yammer メッセージのアイテム保持ポリシーが構成されると、Exchange サービスのタイマー ジョブが、これらの Yammer メッセージが保存されている隠しフォルダ内のアイテムを定期的に評価します。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-128">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="b3a7e-129">このタイマー ジョブを実行するには、最大 7 日間かかります。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-129">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="b3a7e-130">アイテムの保持期間が満了すると、これらのアイテムは SubstrateHolds フォルダに移動されます。これは、すべてのユーザーまたはグループのメールボックスにある隠しフォルダで、アイテムが完全に削除される前の "論理的に削除済み" のアイテムが保存されます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-130">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="b3a7e-131">[データ保持の第 1 原則により](retention.md#the-principles-of-retention-or-what-takes-precedence)、別のアイテム保持ポリシーのために同じアイテムを保持する必要がある場合、または法的、調査上の理由から電子情報開示の保留リストにある場合、完全な削除は常に中断されます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-131">Because of the [first principle of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), permanent deletion is always suspended if the same item must be retained because of another retention policy, or it is under eDiscovery holds for legal or investigative reasons.</span></span>

<span data-ttu-id="b3a7e-132">アイテム保持ポリシーが Yammer メッセージに対して構成された後のコンテンツのパスは、アイテム保持ポリシーの保持後に削除、保持のみ、あるいは削除のみのどれであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-132">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="b3a7e-133">アイテム保持ポリシーが保持されてから削除される場合</span><span class="sxs-lookup"><span data-stu-id="b3a7e-133">When the retention policy is to retain and then delete:</span></span>

![Yammer メッセージの保持フローの図](../media/yammerretentionlifecycle.png)

<span data-ttu-id="b3a7e-135">図内の 2 つのパスの場合:</span><span class="sxs-lookup"><span data-stu-id="b3a7e-135">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="b3a7e-136">保持期間中にユーザーによって **Yammer メッセージが編集または削除された場合**、元のメッセージは直ちに SubstrateHolds フォルダーにコピー (編集の場合) または移動 (削除の場合) されてます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-136">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="b3a7e-137">メッセージは保存期間が終了するまで保存され、その後直ちに完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-137">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="b3a7e-138">**Yammer メッセージが削除されない場合**、および編集した後の現在のメッセージの場合は、保持期間満了後にメッセージは SubstructateHolds フォルダに移動されます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-138">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="b3a7e-139">このアクションには、有効期限から最大で 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-139">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="b3a7e-140">メッセージが SubstrateHolds フォルダにある場合は、直ちに完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-140">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="b3a7e-141">SubstrateHolds フォルダー内のメッセージは、電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-141">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="b3a7e-142">メッセージは完全に削除されるまで（SubstituteHolds フォルダ内）、メッセージは電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-142">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="b3a7e-143">アイテム保持ポリシーが保持のみ、または削除のみの場合、コンテンツ パスは保持か削除かで異なります。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-143">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="b3a7e-144">アイテム保持ポリシーが保持のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="b3a7e-144">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="b3a7e-145">**Yammer メッセージが編集または削除された場合**、元のメッセージのコピーは直ちに SubstrateHolds フォルダに作成され、保持期間が満了するまでそこに保持されます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-145">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="b3a7e-146">その後直ちに、メッセージは SubstrateHolds フォルダから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-146">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="b3a7e-147">**Yammer メッセージが変更または削除されていない場合**、および保持期間中に編集した後の現在のメッセージの場合は、保持期間の前後には何も起こらず、メッセージは元の場所に残ります。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-147">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="b3a7e-148">アイテム保持ポリシーが削除のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="b3a7e-148">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="b3a7e-149">保持期間中に **Yammer メッセージが削除されない場合**、保持期間の終了時にメッセージは SubstrateHolds フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-149">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="b3a7e-150">このアクションには、有効期限から最大で 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-150">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="b3a7e-151">その後直ちに、メッセージは SubstrateHolds フォルダから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-151">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="b3a7e-152">期間中に **ユーザーが Yammer メッセージを削除した場合**、そのアイテムは直ちに SubstrateHolds フォルダーに移動され、完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-152">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="b3a7e-153">メッセージと外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="b3a7e-153">Messages and external users</span></span>

<span data-ttu-id="b3a7e-154">既定では、Yammer ユーザーのメッセージのアイテム保持ポリシーは、組織内のすべてのユーザーに適用され、外部ユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-154">By default, a retention policy for Yammer user messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="b3a7e-155">含まれているユーザーに対して **[編集]** オプションを使用して、アカウントを指定することで、外部ユーザーにアイテム保持ポリシーを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-155">You can apply a retention policy to external users if you use the **Edit** option for users included, and specify their account.</span></span>

<span data-ttu-id="b3a7e-156">現時点では、Azure B2B ゲストユーザーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-156">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="b3a7e-157">ユーザーが組織を離れる場合</span><span class="sxs-lookup"><span data-stu-id="b3a7e-157">When a user leaves the organization</span></span> 

<span data-ttu-id="b3a7e-158">ユーザーが組織を離れ、そのユーザーの Microsoft 365 アカウントが削除された場合、保持の対象となる Yammer ユーザーのメッセージは、非アクティブなメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-158">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer user messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="b3a7e-159">これらのメッセージは、引き続きメールボックスが非アクティブになる前にユーザーに配置されたアイテム保持ポリシーの適用対象となり、電子情報開示の検索が可能です。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-159">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="b3a7e-160">詳細については、「[Exchange Online の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-160">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="b3a7e-161">ユーザーが Yammer にファイルを保存している場合は、SharePoint と OneDrive の「[同等のセクション](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-161">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="b3a7e-162">制限事項</span><span class="sxs-lookup"><span data-stu-id="b3a7e-162">Limitations</span></span>

<span data-ttu-id="b3a7e-163">現在、Yammer のアイテム保持ポリシーはプレビュー中であり、継続的に保持機能の最適化に努めています。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-163">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="b3a7e-164">当面は、Yammer のコミュニティ メッセージとユーザー メッセージで保持を使用する場合は、次の制限に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-164">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and user messages:</span></span>

- <span data-ttu-id="b3a7e-165">**Yammer ユーザーのメッセージ** の場所にある **[編集]** を選択した場合、ゲストや、メールボックス ユーザー以外のユーザーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-165">When you select **Edit** for the **Yammer user messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="b3a7e-166">アイテム保持ポリシーはこれらのユーザー向けに設計されていないため、選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-166">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="b3a7e-167">構成ガイダンス</span><span class="sxs-lookup"><span data-stu-id="b3a7e-167">Configuration guidance</span></span>

<span data-ttu-id="b3a7e-168">Microsoft 365 で保持を構成するのが初めての場合は、「[アイテム保持ポリシーと保持ラベルの使用を開始する](get-started-with-retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-168">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="b3a7e-169">Yammer 用のアイテム保持ポリシーを構成する準備ができた場合は、「[アイテム保持ポリシーを作成して構成する](create-retention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a7e-169">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>