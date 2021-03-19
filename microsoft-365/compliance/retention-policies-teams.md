---
title: Teams の保持の詳細
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
description: Microsoft Teams に適用されるアイテム保持ポリシーについて説明します。
ms.openlocfilehash: ec4ca9a79ee3b5674e1837d14cea4ee504cb57d5
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838212"
---
# <a name="learn-about-retention-for-microsoft-teams"></a><span data-ttu-id="b5f8f-103">Microsoft Teams の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="b5f8f-103">Learn about retention for Microsoft Teams</span></span>

><span data-ttu-id="b5f8f-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="b5f8f-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

> [!NOTE]
> <span data-ttu-id="b5f8f-105">チャットまたはメッセージが保持ポリシーによって削除されたというメッセージが Teams に表示されている場合は、「[アイテム保持ポリシーに関する Teams メッセージ](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-105">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="b5f8f-106">このページの情報は、これらのアイテム保持ポリシーを管理する IT 管理者向けです。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-106">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="b5f8f-107">この記事の情報は[保持の詳細](retention.md)に関する記事を補足するもので、Microsoft Teams メッセージに固有の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-107">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Microsoft Teams messages.</span></span>

<span data-ttu-id="b5f8f-108">その他のワークロードについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-108">For other workloads, see:</span></span>

- [<span data-ttu-id="b5f8f-109">SharePoint と OneDrive の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="b5f8f-109">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="b5f8f-110">Yammerの保持の詳細</span><span class="sxs-lookup"><span data-stu-id="b5f8f-110">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)
- [<span data-ttu-id="b5f8f-111">Exchange の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="b5f8f-111">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="b5f8f-112">保持と削除の対象となる機能</span><span class="sxs-lookup"><span data-stu-id="b5f8f-112">What's included for retention and deletion</span></span>

<span data-ttu-id="b5f8f-113">次の Teams アイテムは、Teams のアイテム保持ポリシーを使用して保持および削除できます: 埋め込みの画像、テーブル、ハイパーテキスト リンク、および他の Teams メッセージ、ファイル、[カード コンテンツ](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)へのリンクを含む、チャット メッセージとチャネル メッセージ。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-113">The following Teams items can be retained and deleted by using retention policies for Teams: Chat messages and channel messages, including embedded images, tables, hypertext links and links to other Teams messages and files, and [card content](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards).</span></span> <span data-ttu-id="b5f8f-114">チャット メッセージには、チャット内のすべてのユーザーの名前が含まれ、チャネル メッセージにはチーム名とメッセージの件名 (提供されている場合) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-114">Chat messages include all the names of the people in the chat, and channel messages include the team name and the message title (if supplied).</span></span> 

> [!NOTE]
> <span data-ttu-id="b5f8f-115">カード コンテンツに関する機能は最近追加され、現在はテナントに完全にロール アウトされています。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-115">Including card content is a recent addition and now fully rolled out to tenants.</span></span> <span data-ttu-id="b5f8f-116">詳細については、「[Microsoft 365 compliance capabilities for Adaptive Card content through apps in Teams now available (Teams 内のアプリケーションを使用したアダプティブ カード コンテンツのコンプライアンスに関する Microsoft 365 の機能が利用可能になりました)](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-116">For more information, see [Microsoft 365 compliance capabilities for Adaptive Card content through apps in Teams now available](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869).</span></span>

<span data-ttu-id="b5f8f-117">プライベート チャネルの Teams メッセージは、現在、保持ポリシーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-117">Teams messages in private channels are currently not supported for retention policies.</span></span> <span data-ttu-id="b5f8f-118">Teams のアイテム保持ポリシーを使用する場合、コード スニペット、Teams モバイル クライアントからの録音されたボイスメモ、サムネイル、お知らせ画像、および絵文字の形式での他のユーザーからの反応は含まれません。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-118">Code snippets, recorded voice memos from the Teams mobile client, thumbnails, announcement images, and reactions from others in the form of emoticons are not included when you use retention policies for Teams.</span></span>

<span data-ttu-id="b5f8f-119">Teams で使用するメールとファイルは、Teams のアイテム保持ポリシーに含まれていません。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-119">Emails and files that you use with Teams aren't included in retention policies for Teams.</span></span> <span data-ttu-id="b5f8f-120">これらのアイテムには、独自のアイテム保持ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-120">These items have their own retention policies.</span></span>

## <a name="how-retention-works-with-microsoft-teams"></a><span data-ttu-id="b5f8f-121">Microsoft Teams での保持のしくみ</span><span class="sxs-lookup"><span data-stu-id="b5f8f-121">How retention works with Microsoft Teams</span></span>

<span data-ttu-id="b5f8f-122">アイテム保持ポリシーを使用して、Teams 内のチャットとチャネル メッセージからデータを保持および削除できます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-122">You can use a retention policy to retain and delete data from chats and channel messages in Teams.</span></span> <span data-ttu-id="b5f8f-123">バックグラウンドでは、Exchange メールボックスを使用してこれらのメッセージを保存します。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-123">Behind the scenes, Exchange mailboxes are used to store these messages.</span></span> <span data-ttu-id="b5f8f-124">Teams チャットのデータは、チャットに含まれる各ユーザーのメールボックスの隠しフォルダーに保存され、グループ メールボックスの同様の隠しフォルダーが Teams チャネル メッセージに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-124">Data from Teams chats is stored in a hidden folder in the mailbox of each user included in the chat, and a similar hidden folder in a group mailbox is used for Teams channel messages.</span></span>

<span data-ttu-id="b5f8f-125">これらのメールボックスは、RecipientTypeDetails 属性で一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-125">These mailboxes are, listed by their RecipientTypeDetails attribute:</span></span>

- <span data-ttu-id="b5f8f-126">**MailUser**: これらのメールボックスには、クラウドベースの Teams ユーザーのメッセージが保存されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-126">**MailUser**: These mailboxes store messages for cloud-based Teams users.</span></span>
- <span data-ttu-id="b5f8f-127">**UserMailbox**: これらのメールボックスには、[オンプレミスの Teams ユーザー](search-cloud-based-mailboxes-for-on-premises-users.md)のメッセージが保存されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-127">**UserMailbox**: These mailboxes store messages for [on-premises Teams users](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>
- <span data-ttu-id="b5f8f-128">**GroupMailbox**: これらのメールボックスは Teams チャネルのメッセージを保存します。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-128">**GroupMailbox**: These mailboxes store messages for Teams channels.</span></span>

<span data-ttu-id="b5f8f-129">Teams 会議室に使用される RoomMailbox などの他のメールボックスの種類は、Teams 保持ポリシーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-129">Other mailbox types, such as RoomMailbox that is used for Teams conference rooms, are not supported for Teams retention policies.</span></span>

<span data-ttu-id="b5f8f-130">Azure を利用したチャット サービスでもこのデータが保存されますが、Teams でもこのサービスを使用していることを理解することが重要です。既定では、このサービスはデータを無期限に保存します。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-130">It's important to understand that Teams uses an Azure-powered chat service that also stores this data, and by default this service stores the data indefinitely.</span></span> <span data-ttu-id="b5f8f-131">このため、コンプライアンス上の理由で Teams メッセージを削除する必要がある場合は、Exchange メールボックスと基盤となる Azure ベースのチャット サービスの両方からこのデータを完全に削除できる Teams の保持ポリシーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-131">For this reason, if you need to delete Teams messages for compliance reasons, we recommend that you use retention policies for Teams that can permanently delete this data from both the Exchange mailboxes and the underlying Azure-powered chat service.</span></span> <span data-ttu-id="b5f8f-132">基盤となるアーキテクチャの詳細については、「[Microsoft Teams のセキュリティとコンプライアンス](https://go.microsoft.com/fwlink/?linkid=871258)」、特に「[情報保護アーキテクチャ](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-132">For more information about the underlying architecture, see [Security and compliance in Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258) and specifically, the [Information Protection Architecture](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture) section.</span></span>

<span data-ttu-id="b5f8f-133">Teams のチャットとチャネル メッセージはメールボックスに保存されますが、この Teams のデータは、**Teams のチャネル メッセージ** と **Teams のチャット** の場所に対して構成されているアイテム保持ポリシーによってのみ含まれます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-133">Although Teams chats and channel messages are stored in mailboxes, this Teams data is included only by a retention policy that's configured for the **Teams channel messages** and **Teams chats** locations.</span></span> <span data-ttu-id="b5f8f-134">Teams のチャットとチャネル メッセージは、Exchange ユーザーまたはグループのメールボックスに対して構成されているアイテム保持ポリシーの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-134">Teams chats and channel messages are not affected by retention policies that are configured for Exchange user or group mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="b5f8f-135">ユーザーが Teams データを保持するアクティブなアイテム保持ポリシーに含まれている場合、このポリシーに含まれるユーザーのメールボックスを削除すると、Teams のデータを保持するためにメールボックスは[非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)に変換されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-135">If a user is included in an active retention policy that retains Teams data and you a delete a mailbox of a user who is included in this policy, to retain the Teams data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="b5f8f-136">ユーザーのこの Teams のデータを保持する必要がない場合は、メールボックスを削除する前に、アイテム保持ポリシーからそのユーザー アカウントを除外します。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-136">If you don't need to retain this Teams data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="b5f8f-137">チャット メッセージとチャネル メッセージのアイテム保持ポリシーが構成されると、Exchange サービスのタイマー ジョブが、これらの Teams メッセージが保存されている隠しフォルダ内のアイテムを定期的に評価します。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-137">After a retention policy is configured for chat and channel messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Teams messages are stored.</span></span> <span data-ttu-id="b5f8f-138">このタイマー ジョブを実行するには、最大 7 日間かかります。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-138">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="b5f8f-139">アイテムの保持期間が満了すると、これらのアイテムは SubstrateHolds フォルダに移動されます。これは、すべてのユーザーまたはグループのメールボックスにある別の隠しフォルダで、「論理的に削除済み」アイテムが完全に削除される前に保存するためのものです。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-139">When these items have expired their retention period, they are moved to the SubstrateHolds folder—another hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

<span data-ttu-id="b5f8f-140">アイテム保持ポリシーがチャット メッセージとチャネル メッセージに対して構成された後のコンテンツのパスは、アイテム保持ポリシーの保持後に削除、保持のみ、あるいは削除のみのどれであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-140">After a retention policy is configured for chat and channel messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="b5f8f-141">アイテム保持ポリシーが保持されてから削除される場合</span><span class="sxs-lookup"><span data-stu-id="b5f8f-141">When the retention policy is to retain and then delete:</span></span>

![Teams チャットとチャネル メッセージの保持フローの図](../media/teamsretentionlifecycle.png)

<span data-ttu-id="b5f8f-143">図内の 2 つのパスの場合:</span><span class="sxs-lookup"><span data-stu-id="b5f8f-143">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="b5f8f-144">**保持期間中にチャット メッセージまたはチャネル メッセージがユーザーによって編集または削除された場合**、元のメッセージは 21 日以内に SubstrateHolds フォルダーにコピー (編集の場合) または移動 (削除の場合) されてます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-144">**If a chat or channel message is edited or deleted** by the user during the retention period, the original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder within 21 days.</span></span> <span data-ttu-id="b5f8f-145">メッセージは保存期間が終了するまで保存され、その後 24 時間以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-145">The message is stored there until the retention period expires and then the message is permanently deleted within 24 hours.</span></span>

2. <span data-ttu-id="b5f8f-146">**チャット メッセージまたはチャネル メッセージが削除されない場合**、および編集した後の現在のメッセージの場合は、保持期間満了後にメッセージは SubstructateHolds フォルダに移動されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-146">**If a chat or channel message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="b5f8f-147">このアクションを実行するには、有効期限の最大で 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-147">This action takes up to 7 days from the expiry date.</span></span> <span data-ttu-id="b5f8f-148">メッセージが SubstrateHolds フォルダにある場合は、24 時間以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-148">When the message is in the SubstrateHolds folder, it is then permanently deleted within 24 hours.</span></span> 

> [!NOTE]
> <span data-ttu-id="b5f8f-149">SubstrateHolds フォルダー内のメッセージは、電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-149">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="b5f8f-150">メッセージは SubstituteHolds フォルダ内から完全に削除されるまで、メッセージは電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-150">Until messages are permanently deleted from this SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="b5f8f-151">アイテム保持ポリシーが保持のみ、または削除のみの場合、コンテンツ パスは保持か削除かで異なります。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-151">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="b5f8f-152">アイテム保持ポリシーが保持のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="b5f8f-152">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="b5f8f-153">**チャット メッセージまたはチャネルのメッセージが編集または削除された場合**、元のメッセージのコピーは 21 日以内に SubstrateHolds フォルダに作成され、保持期間が満了するまでそこに保持されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-153">**If a chat or channel message is edited or deleted**: A copy of the original message is created in the SubstrateHolds folder within 21 days, and retained there until the retention period expires.</span></span> <span data-ttu-id="b5f8f-154">メッセージは、SubstrateHolds フォルダから 24 時間以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-154">Then the message is permanently deleted from the SubstrateHolds folder within 24 hours.</span></span>

2. <span data-ttu-id="b5f8f-155">**アイテムが変更または削除されていない場合**、および保持期間中に編集した後の現在のメッセージの場合は、保持期間の前後には何も起こらず、メッセージは元の場所に残ります。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-155">**If the item is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="b5f8f-156">アイテム保持ポリシーが削除のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="b5f8f-156">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="b5f8f-157">保持期間中に **メッセージが削除されない場合**、保持期間の終了時にメッセージは SubstrateHolds フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-157">**If the message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="b5f8f-158">このアクションを実行するには、有効期限の最大で 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-158">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="b5f8f-159">メッセージは、SubstrateHolds フォルダから 24 時間以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-159">Then the message is permanently deleted from the SubstrateHolds folder within 24 hours.</span></span>

2. <span data-ttu-id="b5f8f-160">期間中にユーザーがアイテムを **削除した場合**、アイテムは 21 日以内に SubstrateHolds フォルダーに移動され、24 時間以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-160">**If the item is deleted by the user** during the period, the item is moved to the SubstrateHolds folder within 21 days where it is then permanently deleted within 24 hours.</span></span>


## <a name="skype-for-business-and-teams-interop-chats"></a><span data-ttu-id="b5f8f-161">Skype for Business および Teams の相互運用チャット</span><span class="sxs-lookup"><span data-stu-id="b5f8f-161">Skype for Business and Teams interop chats</span></span>

<span data-ttu-id="b5f8f-162">Skype for Business のチャットが Teams に届くと、Teams のチャット スレッドのメッセージとなり、適切なメールボックスに取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-162">When a Skype for Business chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="b5f8f-163">Teams のアイテム保持ポリシーは、これらのメッセージに Teams のスレッドから適用されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-163">Teams retention policies will apply to these messages from the Teams thread.</span></span> 

<span data-ttu-id="b5f8f-164">ただし、Skype for Business に対して会話履歴がオンになっていて、Skype for Business のクライアント側からその履歴がメールボックスに保存されている場合、このチャット データは Teams のアイテム保持ポリシーでは処理されません。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-164">However, if conversation history is turned on for Skype for Business and from the Skype for Business client side that history is being saved into a mailbox, that chat data isn't handled by a Teams retention policy.</span></span> <span data-ttu-id="b5f8f-165">このコンテンツには、Skype for Business に構成されているアイテム保持ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-165">For this content, use a retention policy that's configured for Skype for Business.</span></span>

## <a name="meetings-and-external-users"></a><span data-ttu-id="b5f8f-166">会議と外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="b5f8f-166">Meetings and external users</span></span>

<span data-ttu-id="b5f8f-167">チャネル会議メッセージはチャネル メッセージと同じ方法で保存されるため、このデータについては、アイテム保持ポリシーを構成するときに、**Teams チャネル メッセージ** の場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-167">Channel meeting messages are stored the same way as channel messages, so for this data, select the **Teams channel messages** location when you configure your retention policy.</span></span>

<span data-ttu-id="b5f8f-168">緊急会議のメッセージも予定された会議のメッセージもグループ チャット メッセージと同じ方法で保存されるため、このデータについては、アイテム保持ポリシーを構成するときに、**Teams チャット** の場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-168">Impromptu and scheduled meeting messages are stored in the same way as group chat messages, so for this data, select the **Teams chats** location when you configure your retention policy.</span></span>

<span data-ttu-id="b5f8f-169">組織が主催する会議に外部ユーザーが含まれる場合:</span><span class="sxs-lookup"><span data-stu-id="b5f8f-169">When external users are included in a meeting that your organization hosts:</span></span>

- <span data-ttu-id="b5f8f-170">外部ユーザーがテナントのゲスト アカウントを使用して参加する場合、このユーザーには、組織の Teams のアイテム保持ポリシーの対象となるシャドウ メールボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-170">If an external user joins by using a guest account in your tenant, this user has a shadow mailbox that can be subject to your organization's retention policy for Teams.</span></span> <span data-ttu-id="b5f8f-171">会議からのメッセージはすべて、ユーザーのメールボックスとシャドウ メールボックスの両方に保存されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-171">Any messages from the meeting are stored in both your users' mailbox and the shadow mailbox.</span></span> 

- <span data-ttu-id="b5f8f-172">外部ユーザーが別の Microsoft 365 組織のアカウントを使用して参加した場合、そのユーザーのメッセージは別のテナントのメールボックスに保存されるため、削除できません。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-172">If an external user joins by using an account from another Microsoft 365 organization, your retention policies can't delete messages for this user because they are stored in that user's mailbox in another tenant.</span></span> <span data-ttu-id="b5f8f-173">ただし、同じ会議の場合、アイテム保持ポリシーによりユーザーのメッセージが削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-173">For the same meeting however, your retention policies can delete messages for your users.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="b5f8f-174">ユーザーが組織を離れる場合</span><span class="sxs-lookup"><span data-stu-id="b5f8f-174">When a user leaves the organization</span></span> 

<span data-ttu-id="b5f8f-175">Exchange Online のメールボックスを持っているユーザーが組織を離れ、そのユーザーの Microsoft 365 アカウントが削除された場合、保持の対象となるチャット メッセージは、非アクティブなメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-175">If a user who has a mailbox in Exchange Online leaves your organization and their Microsoft 365 account is deleted, their chat messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="b5f8f-176">チャット メッセージは、引き続きメールボックスが非アクティブになる前にユーザーに配置されたアイテム保持ポリシーの適用対象となり、電子情報開示の検索が可能です。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-176">The chat messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="b5f8f-177">詳細については、「[Exchange Online の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-177">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="b5f8f-178">ユーザーが Teams にファイルを保存している場合は、SharePoint と OneDrive の[同等のセクション](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-178">If the user stored any files in Teams, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="b5f8f-179">制限事項</span><span class="sxs-lookup"><span data-stu-id="b5f8f-179">Limitations</span></span>

<span data-ttu-id="b5f8f-180">Teams の保持機能の最適化に継続的に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-180">We're continuously working on optimizing retention functionality in Teams.</span></span> <span data-ttu-id="b5f8f-181">それまでの間、Teams のチャネル メッセージとチャットで保持を使用する場合は、次の制限事項に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-181">In the meantime, here are a few limitations to be aware of when you use retention for Teams channel messages and chats:</span></span>

- <span data-ttu-id="b5f8f-182">**Outlook での誤った表示の問題**。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-182">**Incorrect display issue in Outlook**.</span></span> <span data-ttu-id="b5f8f-183">Skype または Teams の場所用にアイテム保持ポリシーを作成する場合、ユーザーが Outlook デスクトップ クライアントでメールボックス フォルダーのプロパティを表示すると、これらのポリシーの 1 つが既定のフォルダーポリシーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-183">If you create retention policies for Skype or Teams locations, one of those policies is shown as the default folder policy when a user views the properties of a mailbox folder in the Outlook desktop client.</span></span> <span data-ttu-id="b5f8f-184">これは、Outlook の誤表示の問題であり、[既知の問題](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)です。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-184">This is an incorrect display issue in Outlook and [a known issue](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies).</span></span> <span data-ttu-id="b5f8f-185">既定のフォルダー ポリシーとして表示されるのは、フォルダーに適用されるメールボックス保持ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-185">What should be displayed as the default folder policy is the mailbox retention policy that's applied to the folder.</span></span> <span data-ttu-id="b5f8f-186">Skype または Teams の保持ポリシーは、ユーザーのメールボックスには適用されません。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-186">The Skype or Teams retention policy is not applied to the user's mailbox.</span></span>

- <span data-ttu-id="b5f8f-187">**構成の問題**:</span><span class="sxs-lookup"><span data-stu-id="b5f8f-187">**Configuration issues**:</span></span> 
    - <span data-ttu-id="b5f8f-188">**[Teams のチャネル メッセージ]** の場所にある **[チームの選択]** を選択した場合、チームではない Microsoft 365 グループが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-188">When you select **Choose teams** for the **Teams channel messages** location, you might see Microsoft 365 groups that aren't also teams.</span></span> <span data-ttu-id="b5f8f-189">これらのグループは選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-189">Don't select these groups.</span></span>
    
    - <span data-ttu-id="b5f8f-190">**[Teams のチャット]** の場所にある **[ユーザーの選択]** を選択した場合、ゲストや、メールボックスのユーザーではないユーザーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-190">When you select **Choose users** for the **Teams chats** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="b5f8f-191">アイテム保持ポリシーはこれらのユーザー向けに設計されていないため、選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-191">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="b5f8f-192">構成ガイダンス</span><span class="sxs-lookup"><span data-stu-id="b5f8f-192">Configuration guidance</span></span>

<span data-ttu-id="b5f8f-193">Microsoft 365 で保持を構成するのが初めての場合は、「[アイテム保持ポリシーと保持ラベルの使用を開始する](get-started-with-retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-193">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="b5f8f-194">Teams 用のアイテム保持ポリシーを構成する準備ができた場合は、「[アイテム保持ポリシーを作成して構成する](create-retention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5f8f-194">If you're ready to configure a retention policy for Teams, see [Create and configure retention policies](create-retention-policies.md).</span></span>
