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
ms.openlocfilehash: d4988eee419a38497d4fa35cdb3e2f7fec103688
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2021
ms.locfileid: "53052929"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="ab583-103">Yammer の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="ab583-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="ab583-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="ab583-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="ab583-105">この機能は現在プレビュー段階であり、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ab583-105">This feature is in preview and subject to change.</span></span>

<span data-ttu-id="ab583-106">この記事の情報は[保持の詳細](retention.md)に関する記事を補足するもので、Yammer に固有の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab583-106">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="ab583-107">その他のワークロードについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab583-107">For other workloads, see:</span></span>

- [<span data-ttu-id="ab583-108">SharePoint と OneDrive の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="ab583-108">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="ab583-109">Microsoft Teams の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="ab583-109">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="ab583-110">Exchange の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="ab583-110">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="ab583-111">保持と削除の対象となる機能</span><span class="sxs-lookup"><span data-stu-id="ab583-111">What's included for retention and deletion</span></span>

<span data-ttu-id="ab583-112">コミュニティ メッセージとプライベート メッセージの Yammer アイテムは、Yammer のアイテム保持ポリシーを使用して保持および削除できます。</span><span class="sxs-lookup"><span data-stu-id="ab583-112">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and private messages.</span></span>

<span data-ttu-id="ab583-113">絵文字の形で他人からの反応はこれらのメッセージに含まれていません。</span><span class="sxs-lookup"><span data-stu-id="ab583-113">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="ab583-114">Yammer での保持のしくみ</span><span class="sxs-lookup"><span data-stu-id="ab583-114">How retention works with Yammer</span></span>

<span data-ttu-id="ab583-115">アイテム保持ポリシーを使用して、Yammer でコミュニティ メッセージやプライベート メッセージを保持および削除できます。</span><span class="sxs-lookup"><span data-stu-id="ab583-115">You can use a retention policy to retain and delete community messages and private messages in Yammer.</span></span> <span data-ttu-id="ab583-116">プライベート メッセージは、メッセージに含まれる各ユーザーのメールボックス内の隠しフォルダーに保存されます。また、コミュニティ メッセージは、コミュニティ用のグループ メールボックス内の同様の隠しフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="ab583-116">Private messages are stored in a hidden folder in the mailbox of each user included in the message, and community messages are stored in a similar hidden folder in the group mailbox for the community.</span></span>

<span data-ttu-id="ab583-117">Yammer のメッセージは、ユーザーまたはグループのメールボックスに対して構成されているアイテム保持ポリシーの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="ab583-117">Yammer messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="ab583-118">Yammer のメッセージは Exchange に保存されますが、この Yammer のデータは、**Yammer コミュニティのメッセージ** と **Yammer ユーザーのメッセージ** の場所に対して構成されているアイテム保持ポリシーによってのみ含まれます。</span><span class="sxs-lookup"><span data-stu-id="ab583-118">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer user messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="ab583-119">ユーザーが Yammer のデータを保持するアクティブなアイテム保持ポリシーに含まれている場合、このポリシーに含まれるユーザーのメールボックスを削除すると、Yammer のデータを保持するためにメールボックスは[非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ab583-119">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="ab583-120">ユーザーのこの Yammer データを保持する必要がない場合は、メールボックスを削除する前に、アイテム保持ポリシーからそのユーザー アカウントを除外します。</span><span class="sxs-lookup"><span data-stu-id="ab583-120">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="ab583-121">Yammer メッセージのアイテム保持ポリシーが構成されると、Exchange サービスのタイマー ジョブが、これらの Yammer メッセージが保存されている隠しフォルダ内のアイテムを定期的に評価します。</span><span class="sxs-lookup"><span data-stu-id="ab583-121">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="ab583-122">このタイマー ジョブを実行するには、最大 7 日間かかります。</span><span class="sxs-lookup"><span data-stu-id="ab583-122">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="ab583-123">アイテムの保持期間が満了すると、これらのアイテムは SubstrateHolds フォルダに移動されます。これは、すべてのユーザーまたはグループのメールボックスにある隠しフォルダで、アイテムが完全に削除される前の "論理的に削除済み" のアイテムが保存されます。</span><span class="sxs-lookup"><span data-stu-id="ab583-123">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="ab583-124">[データ保持の第 1 原則により](retention.md#the-principles-of-retention-or-what-takes-precedence)、別のアイテム保持ポリシーのために同じアイテムを保持する必要がある場合、または法的、調査上の理由から電子情報開示の保留リストにある場合、完全な削除は常に中断されます。</span><span class="sxs-lookup"><span data-stu-id="ab583-124">Because of the [first principle of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), permanent deletion is always suspended if the same item must be retained because of another retention policy, or it is under eDiscovery holds for legal or investigative reasons.</span></span>

<span data-ttu-id="ab583-125">アイテム保持ポリシーが Yammer メッセージに対して構成された後のコンテンツのパスは、アイテム保持ポリシーの保持後に削除、保持のみ、あるいは削除のみのどれであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ab583-125">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="ab583-126">アイテム保持ポリシーが保持されてから削除される場合</span><span class="sxs-lookup"><span data-stu-id="ab583-126">When the retention policy is to retain and then delete:</span></span>

![Yammer メッセージの保持フローの図](../media/yammerretentionlifecycle.png)

<span data-ttu-id="ab583-128">図内の 2 つのパスの場合:</span><span class="sxs-lookup"><span data-stu-id="ab583-128">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="ab583-129">保持期間中にユーザーによって **Yammer メッセージが編集または削除された場合**、元のメッセージは直ちに SubstrateHolds フォルダーにコピー (編集の場合) または移動 (削除の場合) されてます。</span><span class="sxs-lookup"><span data-stu-id="ab583-129">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="ab583-130">メッセージは保存期間が終了するまで保存され、その後直ちに完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ab583-130">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="ab583-131">**Yammer メッセージが削除されない場合**、および編集した後の現在のメッセージの場合は、保持期間満了後にメッセージは SubstructateHolds フォルダに移動されます。</span><span class="sxs-lookup"><span data-stu-id="ab583-131">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="ab583-132">このアクションには、有効期限から最大で 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="ab583-132">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="ab583-133">メッセージが SubstrateHolds フォルダにある場合は、直ちに完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ab583-133">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="ab583-134">SubstrateHolds フォルダー内のメッセージは、電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="ab583-134">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="ab583-135">メッセージは完全に削除されるまで（SubstituteHolds フォルダ内）、メッセージは電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="ab583-135">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="ab583-136">アイテム保持ポリシーが保持のみ、または削除のみの場合、コンテンツ パスは保持か削除かで異なります。</span><span class="sxs-lookup"><span data-stu-id="ab583-136">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="ab583-137">アイテム保持ポリシーが保持のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="ab583-137">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="ab583-138">**Yammer メッセージが編集または削除された場合**、元のメッセージのコピーは直ちに SubstrateHolds フォルダに作成され、保持期間が満了するまでそこに保持されます。</span><span class="sxs-lookup"><span data-stu-id="ab583-138">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="ab583-139">その後直ちに、メッセージは SubstrateHolds フォルダから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ab583-139">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="ab583-140">**Yammer メッセージが変更または削除されていない場合**、および保持期間中に編集した後の現在のメッセージの場合は、保持期間の前後には何も起こらず、メッセージは元の場所に残ります。</span><span class="sxs-lookup"><span data-stu-id="ab583-140">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="ab583-141">アイテム保持ポリシーが削除のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="ab583-141">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="ab583-142">保持期間中に **Yammer メッセージが削除されない場合**、保持期間の終了時にメッセージは SubstrateHolds フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="ab583-142">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="ab583-143">このアクションには、有効期限から最大で 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="ab583-143">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="ab583-144">その後直ちに、メッセージは SubstrateHolds フォルダから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ab583-144">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="ab583-145">期間中に **ユーザーが Yammer メッセージを削除した場合**、そのアイテムは直ちに SubstrateHolds フォルダーに移動され、完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ab583-145">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="ab583-146">メッセージと外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="ab583-146">Messages and external users</span></span>

<span data-ttu-id="ab583-147">既定では、Yammer ユーザーのメッセージのアイテム保持ポリシーは、組織内のすべてのユーザーに適用され、外部ユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="ab583-147">By default, a retention policy for Yammer user messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="ab583-148">**[ユーザーの選択]** を使用して、アカウントを指定することで、外部ユーザーにアイテム保持ポリシーを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="ab583-148">You can apply a retention policy to external users if you use the **Choose user** and specify their account.</span></span> 

<span data-ttu-id="ab583-149">現時点では、Azure B2B ゲストユーザーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ab583-149">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="ab583-150">ユーザーが組織を離れる場合</span><span class="sxs-lookup"><span data-stu-id="ab583-150">When a user leaves the organization</span></span> 

<span data-ttu-id="ab583-151">ユーザーが組織を離れ、そのユーザーの Microsoft 365 アカウントが削除された場合、保持の対象となる Yammer ユーザーのメッセージは、非アクティブなメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="ab583-151">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer user messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="ab583-152">これらのメッセージは、引き続きメールボックスが非アクティブになる前にユーザーに配置されたアイテム保持ポリシーの適用対象となり、電子情報開示の検索が可能です。</span><span class="sxs-lookup"><span data-stu-id="ab583-152">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="ab583-153">詳細については、「[Exchange Online の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab583-153">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="ab583-154">ユーザーが Yammer にファイルを保存している場合は、SharePoint と OneDrive の「[同等のセクション](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab583-154">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="ab583-155">制限事項</span><span class="sxs-lookup"><span data-stu-id="ab583-155">Limitations</span></span>

<span data-ttu-id="ab583-156">現在、Yammer のアイテム保持ポリシーはプレビュー中であり、継続的に保持機能の最適化に努めています。</span><span class="sxs-lookup"><span data-stu-id="ab583-156">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="ab583-157">当面は、Yammer のコミュニティ メッセージとプライベート メッセージで保持を使用する場合は、次の制限に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ab583-157">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and private messages:</span></span>

- <span data-ttu-id="ab583-158">**Yammer ユーザーのメッセージ** の場所にある **[ユーザーの選択]** を選択した場合、ゲストや、メールボックス ユーザー以外のユーザーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ab583-158">When you select **Choose users** for the **Yammer user messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="ab583-159">アイテム保持ポリシーはこれらのユーザー向けに設計されていないため、選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="ab583-159">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="ab583-160">構成ガイダンス</span><span class="sxs-lookup"><span data-stu-id="ab583-160">Configuration guidance</span></span>

<span data-ttu-id="ab583-161">Microsoft 365 で保持を構成するのが初めての場合は、「[アイテム保持ポリシーと保持ラベルの使用を開始する](get-started-with-retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab583-161">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="ab583-162">Yammer 用のアイテム保持ポリシーを構成する準備ができた場合は、「[アイテム保持ポリシーを作成して構成する](create-retention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab583-162">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>