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
ms.openlocfilehash: b7bc84307f0db580995e039618cb01d25d6ecd66
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932860"
---
# <a name="learn-about-retention-for-microsoft-teams"></a><span data-ttu-id="59b50-103">Microsoft Teams の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="59b50-103">Learn about retention for Microsoft Teams</span></span>

><span data-ttu-id="59b50-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="59b50-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="59b50-105">チャットまたはメッセージが保持ポリシーによって削除されたというメッセージが Teams に表示されている場合は、「[アイテム保持ポリシーに関する Teams メッセージ](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59b50-105">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="59b50-106">このページの情報は、これらのアイテム保持ポリシーを管理する IT 管理者向けです。</span><span class="sxs-lookup"><span data-stu-id="59b50-106">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="59b50-107">この記事の情報は[保持の詳細](retention.md)に関する記事を補足するもので、Microsoft Teams メッセージに固有の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="59b50-107">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Microsoft Teams messages.</span></span>

<span data-ttu-id="59b50-108">その他のワークロードについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59b50-108">For other workloads, see:</span></span>

- [<span data-ttu-id="59b50-109">SharePoint と OneDrive の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="59b50-109">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="59b50-110">Yammerの保持の詳細</span><span class="sxs-lookup"><span data-stu-id="59b50-110">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)
- [<span data-ttu-id="59b50-111">Exchange の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="59b50-111">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="59b50-112">保持と削除の対象となる機能</span><span class="sxs-lookup"><span data-stu-id="59b50-112">What's included for retention and deletion</span></span>

<span data-ttu-id="59b50-113">Teams のチャット メッセージとチャネル メッセージは、Teams のアイテム保持ポリシーを使用して削除できます。また、メッセージ内のテキストに加えて、コンプライアンス上の理由により、埋め込み画像、表、ハイパーテキスト リンク、他の Teams メッセージやファイルへのリンク、および[カード コンテンツ](/microsoftteams/platform/task-modules-and-cards/what-are-cards)を保持することができます。</span><span class="sxs-lookup"><span data-stu-id="59b50-113">Teams chats messages and channel messages can be deleted by using retention policies for Teams, and in addition to the text in the messages, the following items can be retained for compliance reasons: Embedded images, tables, hypertext links, links to other Teams messages and files, and [card content](/microsoftteams/platform/task-modules-and-cards/what-are-cards).</span></span> <span data-ttu-id="59b50-114">チャット メッセージには、チャット内のすべてのユーザーの名前が含まれ、チャネル メッセージにはチーム名とメッセージの件名 (提供されている場合) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="59b50-114">Chat messages include all the names of the people in the chat, and channel messages include the team name and the message title (if supplied).</span></span> 

> [!NOTE]
> <span data-ttu-id="59b50-115">Teams のアイテム保持ポリシーにカード コンテンツを含めることは、ごく最近の追加です。</span><span class="sxs-lookup"><span data-stu-id="59b50-115">Including card content in a retention policy for Teams is a fairly recent addition.</span></span> <span data-ttu-id="59b50-116">詳細については、「[Microsoft 365 compliance capabilities for Adaptive Card content through apps in Teams now available (Teams 内のアプリケーションを使用したアダプティブ カード コンテンツのコンプライアンスに関する Microsoft 365 の機能が利用可能になりました)](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59b50-116">For more information, see [Microsoft 365 compliance capabilities for Adaptive Card content through apps in Teams now available](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869).</span></span>

<span data-ttu-id="59b50-p103">プライベート チャネルの Teams メッセージは、現在、アイテム保持ポリシーではサポートされていません。Teams のアイテム保持ポリシーを使用する場合、コード スニペット、Teams モバイル クライアントからの録音されたボイス メモ、サムネイル、お知らせ画像、および絵文字の形式での他のユーザーからの反応は保持されません。</span><span class="sxs-lookup"><span data-stu-id="59b50-p103">Teams messages in private channels are currently not supported for retention policies. Code snippets, recorded voice memos from the Teams mobile client, thumbnails, announcement images, and reactions from others in the form of emoticons are not retained when you use retention policies for Teams.</span></span>

<span data-ttu-id="59b50-p104">Teams で使用するメールとファイルは、Teams のアイテム保持ポリシーに含まれていません。これらのアイテムには、独自のアイテム保持ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="59b50-p104">Emails and files that you use with Teams aren't included in retention policies for Teams. These items have their own retention policies.</span></span>

## <a name="how-retention-works-with-microsoft-teams"></a><span data-ttu-id="59b50-121">Microsoft Teams での保持のしくみ</span><span class="sxs-lookup"><span data-stu-id="59b50-121">How retention works with Microsoft Teams</span></span>

<span data-ttu-id="59b50-122">このセクションを使用して、コンプライアンス要件がバックエンド ストレージとプロセスによってどのように満たされているかを説明します。現在、Teams アプリに表示されているメッセージではなく、電子情報開示ツールで確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59b50-122">Use this section to understand how your compliance requirements are met by backend storage and processes, and should be verified by eDiscovery tools rather than by messages that are currently visible in the Teams app.</span></span>

<span data-ttu-id="59b50-123">アイテム保持ポリシーを使用して、Teams 内のチャットとチャネル メッセージからデータを保持することができ、それらを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="59b50-123">You can use a retention policy to retain data from chats and channel messages in Teams, and delete these chats and messages.</span></span> <span data-ttu-id="59b50-124">バックグラウンドでは、Exchange メールボックスを使用してこれらのメッセージからコピーされたデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="59b50-124">Behind the scenes, Exchange mailboxes are used to store data copied from these messages.</span></span> <span data-ttu-id="59b50-125">Teams チャットのデータは、チャットに含まれる各ユーザーのメールボックスの隠しフォルダーに保存され、グループ メールボックスの同様の隠しフォルダーが Teams チャネル メッセージに使用されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-125">Data from Teams chats is stored in a hidden folder in the mailbox of each user included in the chat, and a similar hidden folder in a group mailbox is used for Teams channel messages.</span></span> <span data-ttu-id="59b50-126">これらの隠しフォルダーは、ユーザーまたは管理者が直接アクセスできるようには設計されていませんが、代わりに、コンプライアンス管理者が電子情報開示ツールで検索できるデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="59b50-126">These hidden folders are not designed to be directly accessible to users or administrators, but instead, store data that compliance administrators can search with eDiscovery tools.</span></span>

<span data-ttu-id="59b50-127">これらのメールボックスは、RecipientTypeDetails 属性で一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-127">These mailboxes are, listed by their RecipientTypeDetails attribute:</span></span>

- <span data-ttu-id="59b50-128">**UserMailbox**: これらのメールボックスには、クラウドベースの Teams ユーザーのメッセージ データが保存されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-128">**UserMailbox**: These mailboxes store message data for cloud-based Teams users.</span></span>
- <span data-ttu-id="59b50-129">**MailUser**: これらのメールボックスには、[オンプレミスの Teams ユーザー](search-cloud-based-mailboxes-for-on-premises-users.md)のメッセージ データが保存されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-129">**MailUser**: These mailboxes store message data for [on-premises Teams users](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>
- <span data-ttu-id="59b50-130">**GroupMailbox**: これらのメールボックスは Teams チャネルのメッセージ データを保存します。</span><span class="sxs-lookup"><span data-stu-id="59b50-130">**GroupMailbox**: These mailboxes store message data for Teams channels.</span></span>

<span data-ttu-id="59b50-131">Teams 会議室に使用される RoomMailbox などの他のメールボックスの種類は、Teams 保持ポリシーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="59b50-131">Other mailbox types, such as RoomMailbox that is used for Teams conference rooms, are not supported for Teams retention policies.</span></span>

<span data-ttu-id="59b50-132">Teams では、すべてのメッセージ (チャットおよびチャネル メッセージ) のプライマリ ストレージとして Azure を利用したチャット サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="59b50-132">Teams uses an Azure-powered chat service as its primary storage for all messages (chats and channel messages).</span></span> <span data-ttu-id="59b50-133">コンプライアンス上の理由で Teams メッセージを削除する必要がある場合は、Teams のアイテム保持ポリシーは、メッセージが作成された日に基づいて、特定の期間の後にメッセージを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="59b50-133">If you need to delete Teams messages for compliance reasons, retention policies for Teams can delete messages after a specified period, based on when they were created.</span></span> <span data-ttu-id="59b50-134">その後、メッセージは、コンプライアンス操作のために保存された Exchange メールボックスと、基盤となる Azure を利用したチャット サービスによって使用されるプライマリ ストレージの両方から完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-134">Messages are then permanently deleted from both the Exchange mailboxes where they stored for compliance operations, and from the primary storage used by the underlying Azure-powered chat service.</span></span> <span data-ttu-id="59b50-135">基盤となるアーキテクチャの詳細については、「[Microsoft Teams のセキュリティとコンプライアンス](/MicrosoftTeams/security-compliance-overview)」、特に「[情報保護アーキテクチャ](/MicrosoftTeams/security-compliance-overview#information-protection-architecture)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59b50-135">For more information about the underlying architecture, see [Security and compliance in Microsoft Teams](/MicrosoftTeams/security-compliance-overview) and specifically, the [Information Protection Architecture](/MicrosoftTeams/security-compliance-overview#information-protection-architecture) section.</span></span>

<span data-ttu-id="59b50-136">Teams のチャットとチャネル メッセージからのこのデータはメールボックスに保存されますが、**Teams のチャネル メッセージ** と **Teams のチャット** の場所のアイテム保持ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59b50-136">Although this data from Teams chats and channel messages are stored in mailboxes, you must configure a retention policy for the **Teams channel messages** and **Teams chats** locations.</span></span> <span data-ttu-id="59b50-137">Teams のチャットとチャネル メッセージは、Exchange ユーザーまたはグループのメールボックスに対して構成されているアイテム保持ポリシーには含まれていません。</span><span class="sxs-lookup"><span data-stu-id="59b50-137">Teams chats and channel messages are not included in retention policies that are configured for Exchange user or group mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="59b50-138">ユーザーが Teams メッセージを保持するアクティブなアイテム保持ポリシーに含まれている場合、このポリシーに含まれるユーザーのメールボックスを削除すると、Teams のデータを保持するためにメールボックスは[非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)に変換されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-138">If a user is included in an active retention policy that retains Teams messages and you a delete a mailbox of a user who is included in this policy, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md) to retain the Teams data.</span></span> <span data-ttu-id="59b50-139">ユーザーのこの Teams のデータを保持する必要がない場合は、メールボックスを削除する前に、アイテム保持ポリシーからそのユーザー アカウントを除外します。</span><span class="sxs-lookup"><span data-stu-id="59b50-139">If you don't need to retain this Teams data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="59b50-140">チャット メッセージとチャネル メッセージのアイテム保持ポリシーが構成されると、Exchange サービスのタイマー ジョブが、これらの Teams メッセージが保存されている隠しフォルダ内のアイテムを定期的に評価します。</span><span class="sxs-lookup"><span data-stu-id="59b50-140">After a retention policy is configured for chat and channel messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Teams messages are stored.</span></span> <span data-ttu-id="59b50-141">タイマー ジョブの実行には、通常 1 - 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="59b50-141">The timer job typically takes 1-7 days to run.</span></span> <span data-ttu-id="59b50-142">アイテムの保持期間が満了すると、これらのアイテムは SubstrateHolds フォルダに移動されます。これは、すべてのユーザーまたはグループのメールボックスにある別の隠しフォルダで、「論理的に削除済み」アイテムが完全に削除される前に保存するためのものです。</span><span class="sxs-lookup"><span data-stu-id="59b50-142">When these items have expired their retention period, they are moved to the SubstrateHolds folder—another hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span> 

<span data-ttu-id="59b50-143">メッセージは SubstrateHolds フォルダーに少なくとも 1 日間残り、削除の対象となる場合、タイマー ジョブは次回の実行時にメッセージを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="59b50-143">Messages remain in the SubstrateHolds folder for at least 1 day, and then if they are eligible for deletion, the timer job permanently deletes them the next time it runs.</span></span>

<span data-ttu-id="59b50-144">アイテム保持ポリシーがチャット メッセージとチャネル メッセージに対して構成された後のコンテンツのパスは、アイテム保持ポリシーの保持後に削除、保持のみ、あるいは削除のみのどれであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="59b50-144">After a retention policy is configured for chat and channel messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="59b50-145">アイテム保持ポリシーが保持されてから削除される場合</span><span class="sxs-lookup"><span data-stu-id="59b50-145">When the retention policy is to retain and then delete:</span></span>

![Teams チャットとチャネル メッセージの保持フローの図](../media/teamsretentionlifecycle.png)

<span data-ttu-id="59b50-147">図内の 2 つのパスの場合:</span><span class="sxs-lookup"><span data-stu-id="59b50-147">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="59b50-148">**保持期間中にチャット メッセージまたはチャネル メッセージがユーザーによって編集または削除された場合**、元のメッセージは SubstrateHolds フォルダーにコピー (編集の場合) または移動 (削除の場合) されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-148">**If a chat or channel message is edited or deleted** by a user during the retention period, the original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="59b50-149">メッセージは少なくとも 1 日間そこに保存されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-149">The message is stored there for at least 1 day.</span></span> <span data-ttu-id="59b50-150">保持期間が終了すると、次回タイマー ジョブが実行されたときにメッセージが完全に削除されます (通常は 1 - 7日)。</span><span class="sxs-lookup"><span data-stu-id="59b50-150">When the retention period expires, the message is permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span>

2. <span data-ttu-id="59b50-151">**チャット メッセージまたはチャネル メッセージがユーザーによって削除されない場合**、および編集した後の現在のメッセージの場合は、保持期間満了後にメッセージは SubstructateHolds フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-151">**If a chat or channel message is not deleted** by a user and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="59b50-152">このアクションは通常、期間満了から 1 - 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="59b50-152">This action typically takes between 1-7 days from the expiry date.</span></span> <span data-ttu-id="59b50-153">メッセージが SubstrateHolds フォルダーにある場合、メッセージは少なくとも 1 日間そこに保存され、次回タイマー ジョブが実行されたとき (通常は 1 - 7 日) にメッセージは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-153">When the message is in the SubstrateHolds folder, it is stored there for at least 1 day, and then the message is permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span> 

> [!NOTE]
> <span data-ttu-id="59b50-154">隠しフォルダーを含むメールボックスに保存されているメッセージは、電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="59b50-154">Messages stored in mailboxes, including the hidden folders, are searchable by eDiscovery tools.</span></span> <span data-ttu-id="59b50-155">メッセージは SubstituteHolds フォルダー内から完全に削除されるまで、電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="59b50-155">Until messages are permanently deleted from the SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="59b50-156">メッセージが SubstrateHolds フォルダーから完全に削除されると、削除操作がバックエンドの Azure チャット サービスに伝達され、その後、同じ操作が Teams クライアント アプリに中継されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-156">When messages are permanently deleted from the SubstrateHolds folder, a delete operation is communicated to the backend Azure chat service, that then relays the same operation to the Teams client app.</span></span> <span data-ttu-id="59b50-157">この通信またはキャッシュの遅延により、ユーザーが Teams アプリにこれらのメッセージを短期間表示しても、電子情報開示検索でこれらのメッセージのデータが返されない理由を説明できます。</span><span class="sxs-lookup"><span data-stu-id="59b50-157">Delays in this communication or caching can explain why, for a short period of time, users might still see these messages in their Teams app, but data from these messages isn't returned in eDiscovery searches.</span></span> <span data-ttu-id="59b50-158">Teams アプリに表示されるメッセージは、コンプライアンス要件のために保持されるか完全に削除されるかを正確に反映していません。</span><span class="sxs-lookup"><span data-stu-id="59b50-158">Messages visible in the Teams app are not an accurate reflection of whether they are retained or permanently deleted for compliance requirements.</span></span>

<span data-ttu-id="59b50-159">アイテム保持ポリシーが保持のみ、または削除のみの場合、コンテンツ パスは保持か削除かで異なります。</span><span class="sxs-lookup"><span data-stu-id="59b50-159">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="59b50-160">アイテム保持ポリシーが保持のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="59b50-160">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="59b50-161">**保持期間中にチャット メッセージまたはチャネル メッセージがユーザーによって編集または削除された場合**: 元のメッセージは SubstrateHolds フォルダーにコピー (編集の場合) または移動 (削除の場合) され、少なくとも 1 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-161">**If a chat or channel message is edited or deleted** by a user during the retention period: The original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder, and retained there for at least 1 day.</span></span> <span data-ttu-id="59b50-162">アイテム保持ポリシーが無期限に保持するように構成されている場合、アイテムはそこに残ります。</span><span class="sxs-lookup"><span data-stu-id="59b50-162">If the retention policy is configured to retain forever, the item remains there.</span></span> <span data-ttu-id="59b50-163">アイテム保持ポリシーに保持期間の終了日があり、有効期限が切れている場合、次回タイマー ジョブが実行されたときにメッセージが完全に削除されます (通常は 1 - 7日)。</span><span class="sxs-lookup"><span data-stu-id="59b50-163">If the retention policy has an end date for the retention period and it expires, the message is permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span>

2. <span data-ttu-id="59b50-164">**チャット メッセージまたはチャネル メッセージがユーザーによって変更または削除されていない場合**、および保持期間中に編集した後の現在のメッセージの場合: 保持期間の前後には何も起こらず、メッセージは元の場所に残ります。</span><span class="sxs-lookup"><span data-stu-id="59b50-164">**If the chat or channel message is not modified or deleted** by a user and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="59b50-165">アイテム保持ポリシーが削除のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="59b50-165">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="59b50-166">**保持期間中にチャット メッセージまたはチャネル メッセージがユーザーによって編集または削除された場合**: 元のメッセージは SubstrateHolds フォルダーにコピー (編集の場合) または移動 (削除の場合) されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-166">**If the chat or channel message is edited or deleted** by a user during the retention period: The original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="59b50-167">メッセージは少なくとも 1 日間そこに保持され、次回タイマー ジョブが実行されたときに完全に削除されます (通常は 1 - 7日)。</span><span class="sxs-lookup"><span data-stu-id="59b50-167">The message is retained there for at least 1 day and permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span>

2. <span data-ttu-id="59b50-168">**保持期間中にチャット メッセージまたはチャネル メッセージがユーザーによって削除されない場合**: 保持期間の終了時にメッセージは SubstrateHolds フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-168">**If a chat or channel message is not deleted** by a user during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="59b50-169">このアクションは通常、期間満了から 1 - 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="59b50-169">This action typically takes between 1-7 days from the expiry date.</span></span> <span data-ttu-id="59b50-170">メッセージは少なくとも 1 日間そこに保持され、次回タイマー ジョブが実行されたときに完全に削除されます (通常は 1 - 7日)。</span><span class="sxs-lookup"><span data-stu-id="59b50-170">The message is retained there for at least 1 day and then permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span>

#### <a name="example-flows-and-timings-for-retention-policies"></a><span data-ttu-id="59b50-171">アイテム保持ポリシーのフローとタイミングの例</span><span class="sxs-lookup"><span data-stu-id="59b50-171">Example flows and timings for retention policies</span></span>

<span data-ttu-id="59b50-172">次の例を使用して、前のセクションで説明したプロセスとタイミングが、次の構成を持つアイテム保持ポリシーにどのように適用されるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="59b50-172">Use the following examples to see how the processes and timings explained in the previous sections apply to retention policies that have the following configurations:</span></span>

- [<span data-ttu-id="59b50-173">例 1: 7 年間保持のみ</span><span class="sxs-lookup"><span data-stu-id="59b50-173">Example 1: Retain-only for 7 years</span></span>](#example-1-retain-only-for-7-years)
- [<span data-ttu-id="59b50-174">例 2: 30 日間保持してから、削除する</span><span class="sxs-lookup"><span data-stu-id="59b50-174">Example 2: Retain for 30 days and then delete</span></span>](#example-2-retain-for-30-days-and-then-delete)
- [<span data-ttu-id="59b50-175">例 3: 1 日後削除のみ</span><span class="sxs-lookup"><span data-stu-id="59b50-175">Example 3: Delete-only after 1 day</span></span>](#example-3-delete-only-after-1-day)

<span data-ttu-id="59b50-176">完全な削除を参照するすべての例では、[保持の原則](retention.md#the-principles-of-retention-or-what-takes-precedence)により、メッセージがアイテムを保持するための別のアイテム保持ポリシーの対象であるか、電子情報開示の保持の対象である場合、このアクションは一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-176">For all examples that refer to permanent deletion, because of the [principles of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), this action is suspended if the message is subject to another retention policy to retain the item or it is subject to an eDiscovery hold.</span></span>

##### <a name="example-1-retain-only-for-7-years"></a><span data-ttu-id="59b50-177">例 1: 7 年間保持のみ</span><span class="sxs-lookup"><span data-stu-id="59b50-177">Example 1: Retain-only for 7 years</span></span>

<span data-ttu-id="59b50-178">1 日目に、ユーザーはチャット メッセージまたはチャネル メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="59b50-178">On day 1, a user creates a chat or channel message.</span></span>

<span data-ttu-id="59b50-179">5 日目に、ユーザーはそのメッセージを編集します。</span><span class="sxs-lookup"><span data-stu-id="59b50-179">On day 5, the user edits that message.</span></span>

<span data-ttu-id="59b50-180">30 日目に、ユーザーは現在のメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="59b50-180">On day 30, the user deletes the current message.</span></span>

<span data-ttu-id="59b50-181">保持の結果:</span><span class="sxs-lookup"><span data-stu-id="59b50-181">Retention outcomes:</span></span>

- <span data-ttu-id="59b50-182">元のメッセージの場合:</span><span class="sxs-lookup"><span data-stu-id="59b50-182">For the original message:</span></span>
    - <span data-ttu-id="59b50-183">5 日目に、メッセージは SubstrateHolds フォルダーにコピーされ、1 日目 (保持期間) から最低 7 年間、電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="59b50-183">On day 5, the message is copied to the SubstrateHolds folder where it can still be searched with eDiscovery tools for a minimum of 7 years from day 1 (the retention period).</span></span>

- <span data-ttu-id="59b50-184">現在の (編集済み) メッセージの場合:</span><span class="sxs-lookup"><span data-stu-id="59b50-184">For the current (edited) message:</span></span>
    - <span data-ttu-id="59b50-185">30 日目に、メッセージは SubstrateHolds フォルダーに移動され、1 日目 (保持期間) から最低 7 年間、電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="59b50-185">On day 30, the message moves to the SubstrateHolds folder where it can still be searched with eDiscovery tools for a minimum of 7 years from day 1 (the retention period).</span></span>

<span data-ttu-id="59b50-186">ユーザーが保持期間内ではなく、指定された保持期間後に現在のメッセージを削除した場合でも、メッセージは SubstrateHolds フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-186">If the user had deleted the current message after the specified retention period, instead of within the retention period, the message would still be moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="59b50-187">ただし、保持期間が終了すると、メッセージは最低 1 日後、通常は 1 - 7 日以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-187">However, now the retention period has expired, the message would be permanently deleted after the minimum of 1 day and then typically within 1-7 days.</span></span>

##### <a name="example-2-retain-for-30-days-and-then-delete"></a><span data-ttu-id="59b50-188">例 2: 30 日間保持してから、削除する</span><span class="sxs-lookup"><span data-stu-id="59b50-188">Example 2: Retain for 30 days and then delete</span></span>

<span data-ttu-id="59b50-189">1 日目に、ユーザーはチャット メッセージまたはチャネル メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="59b50-189">On day 1, a user creates a chat or channel message.</span></span>

<span data-ttu-id="59b50-190">10 日目に、ユーザーはそのメッセージを編集します。</span><span class="sxs-lookup"><span data-stu-id="59b50-190">On day 10, the user edits that message.</span></span>

<span data-ttu-id="59b50-191">ユーザーはそれ以上の編集を行わず、メッセージを削除しません。</span><span class="sxs-lookup"><span data-stu-id="59b50-191">The user doesn't make further edits and doesn't delete the message.</span></span>

<span data-ttu-id="59b50-192">保持の結果:</span><span class="sxs-lookup"><span data-stu-id="59b50-192">Retention outcomes:</span></span>

- <span data-ttu-id="59b50-193">元のメッセージの場合:</span><span class="sxs-lookup"><span data-stu-id="59b50-193">For the original message:</span></span>
    - <span data-ttu-id="59b50-194">10 日目に、メッセージは SubstrateHolds フォルダーにコピーされ、電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="59b50-194">On day 10, the message is copied to the SubstrateHolds folder, where it can still be searched with eDiscovery tools.</span></span>
    - <span data-ttu-id="59b50-195">保持期間の終了時 (1 日目から 30 日)、メッセージは通常、最低 1 日後 1 - 7 日以内に完全に削除され、電子情報開示検索では返されません。</span><span class="sxs-lookup"><span data-stu-id="59b50-195">At the end of the retention period (30 days from day 1), the message is permanently deleted typically within 1-7 days after the minimum of 1 day, and then won't be returned with eDiscovery searches.</span></span>

- <span data-ttu-id="59b50-196">現在の (編集済み) メッセージの場合:</span><span class="sxs-lookup"><span data-stu-id="59b50-196">For the current (edited) message:</span></span>
    - <span data-ttu-id="59b50-197">保持期間の終了時 (1 日目から 30 日)、メッセージは通常 1 - 7 日以内に SubstrateHolds フォルダーに移動され、電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="59b50-197">At the end of the retention period (30 days from day 1), the message moves to the SubstrateHolds folder typically within 1-7 days, where it can still be searched with eDiscovery tools.</span></span>
    - <span data-ttu-id="59b50-198">その後、メッセージは通常、最低 1 日後 1 - 7 日以内に完全に削除され、電子情報開示検索では返されません。</span><span class="sxs-lookup"><span data-stu-id="59b50-198">The message is then permanently deleted typically within 1-7 days after the minimum of 1 day, and then won't be returned with eDiscovery searches.</span></span>

##### <a name="example-3-delete-only-after-1-day"></a><span data-ttu-id="59b50-199">例 3: 1 日後削除のみ</span><span class="sxs-lookup"><span data-stu-id="59b50-199">Example 3: Delete-only after 1 day</span></span>

> [!NOTE]
> <span data-ttu-id="59b50-200">1 - 7 日の期間内に動作するこの構成および保持プロセスの期間は 1 日と短いため、このセクションでは、一般的な時間範囲内のタイミングの例を示します。</span><span class="sxs-lookup"><span data-stu-id="59b50-200">Because of the short one-day duration of this configuration and retention processes that operate within a time period of 1-7 days, this section shows example timings that are within the typical time ranges.</span></span>

<span data-ttu-id="59b50-201">1 日目に、ユーザーはチャット メッセージまたはチャネル メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="59b50-201">On day 1, a user creates a chat or channel message.</span></span>

<span data-ttu-id="59b50-202">ユーザーがメッセージを編集または削除しない場合の保持結果の例:</span><span class="sxs-lookup"><span data-stu-id="59b50-202">Example retention outcome if the user doesn't edit or delete the message:</span></span>

- <span data-ttu-id="59b50-203">5 日目 (通常、3 日目の保持期間の開始後 1 - 7 日):</span><span class="sxs-lookup"><span data-stu-id="59b50-203">Day 5 (typically 1-7 days after the start of the retention period on day 3):</span></span>
    - <span data-ttu-id="59b50-204">メッセージは SubstrateHolds フォルダーに移動し、少なくとも 1 日間そこに残り、電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="59b50-204">The message moves to the SubstrateHolds folder and remains there for at least 1 day where it can still be searched with eDiscovery tools.</span></span>

- <span data-ttu-id="59b50-205">9 日目 (通常、SubstrateHolds フォルダー内の最低 1 日後 1 - 7 日):</span><span class="sxs-lookup"><span data-stu-id="59b50-205">Day 9 (typically 1-7 days after a minimum of 1 day in the SubstrateHolds folder):</span></span>
    - <span data-ttu-id="59b50-206">メッセージは完全に削除され、電子情報開示検索では返されません。</span><span class="sxs-lookup"><span data-stu-id="59b50-206">The message is permanently deleted and then won't be returned with eDiscovery searches.</span></span>

<span data-ttu-id="59b50-207">この例が示すように、アイテム保持ポリシーを構成して 1 日後にメッセージを削除することはできますが、サービスは複数のプロセスを経て、ポリシーに準拠した削除を行います。</span><span class="sxs-lookup"><span data-stu-id="59b50-207">As this example shows, although you can configure a retention policy to delete messages after just one day, the service undergoes multiple processes to ensure a compliant deletion.</span></span> <span data-ttu-id="59b50-208">その結果、1 日後の削除アクションは、メッセージが完全に削除されるまでに 18 日かかる可能性があり、メッセージは電子情報開示検索で返されなくなります。</span><span class="sxs-lookup"><span data-stu-id="59b50-208">As a result, a delete action after 1 day could take 18 days before the message is permanently deleted so that it's no longer returned in eDiscovery searches.</span></span>

## <a name="skype-for-business-and-teams-interop-chats"></a><span data-ttu-id="59b50-209">Skype for Business および Teams の相互運用チャット</span><span class="sxs-lookup"><span data-stu-id="59b50-209">Skype for Business and Teams interop chats</span></span>

<span data-ttu-id="59b50-210">Skype for Business のチャットが Teams に届くと、Teams のチャット スレッドのメッセージとなり、適切なメールボックスに取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="59b50-210">When a Skype for Business chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="59b50-211">Teams のアイテム保持ポリシーは、これらのメッセージに Teams のスレッドから適用されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-211">Teams retention policies will apply to these messages from the Teams thread.</span></span> 

<span data-ttu-id="59b50-p120">ただし、Skype for Business に対して会話履歴がオンになっていて、Skype for Business のクライアント側からその履歴がメールボックスに保存されている場合、このチャット データは Teams のアイテム保持ポリシーでは処理されません。このコンテンツには、Skype for Business 用に構成されたアイテム保持ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="59b50-p120">However, if conversation history is turned on for Skype for Business and from the Skype for Business client side that history is being saved into a mailbox, that chat data isn't handled by a Teams retention policy. For this content, use a retention policy that's configured for Skype for Business.</span></span>

## <a name="meetings-and-external-users"></a><span data-ttu-id="59b50-214">会議と外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="59b50-214">Meetings and external users</span></span>

<span data-ttu-id="59b50-215">チャネル会議メッセージはチャネル メッセージと同じ方法で保存されるため、このデータについては、アイテム保持ポリシーを構成するときに、**Teams チャネル メッセージ** の場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="59b50-215">Channel meeting messages are stored the same way as channel messages, so for this data, select the **Teams channel messages** location when you configure your retention policy.</span></span>

<span data-ttu-id="59b50-216">緊急会議のメッセージも予定された会議のメッセージもグループ チャット メッセージと同じ方法で保存されるため、このデータについては、アイテム保持ポリシーを構成するときに、**Teams チャット** の場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="59b50-216">Impromptu and scheduled meeting messages are stored in the same way as group chat messages, so for this data, select the **Teams chats** location when you configure your retention policy.</span></span>

<span data-ttu-id="59b50-217">組織が主催する会議に外部ユーザーが含まれる場合:</span><span class="sxs-lookup"><span data-stu-id="59b50-217">When external users are included in a meeting that your organization hosts:</span></span>

- <span data-ttu-id="59b50-218">外部ユーザーがテナントのゲスト アカウントを使用して参加する場合、このユーザーには、組織の Teams のアイテム保持ポリシーの対象となるシャドウ メールボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="59b50-218">If an external user joins by using a guest account in your tenant, this user has a shadow mailbox that can be subject to your organization's retention policy for Teams.</span></span> <span data-ttu-id="59b50-219">会議からのメッセージはすべて、ユーザーのメールボックスとシャドウ メールボックスの両方に保存されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-219">Any messages from the meeting are stored in both your users' mailbox and the shadow mailbox.</span></span> 

- <span data-ttu-id="59b50-p122">外部ユーザーが別の Microsoft 365 組織のアカウントを使用して参加した場合、そのユーザーのメッセージは別のテナントのメールボックスに保存されるため、削除できません。ただし、同じ会議の場合、アイテム保持ポリシーによってユーザーへのメッセージが削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="59b50-p122">If an external user joins by using an account from another Microsoft 365 organization, your retention policies can't delete messages for this user because they are stored in that user's mailbox in another tenant. For the same meeting however, your retention policies can delete messages for your users.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="59b50-222">ユーザーが組織を離れる場合</span><span class="sxs-lookup"><span data-stu-id="59b50-222">When a user leaves the organization</span></span> 

<span data-ttu-id="59b50-223">Exchange Online のメールボックスを持っているユーザーが組織を離れ、そのユーザーの Microsoft 365 アカウントが削除された場合、保持の対象となるチャット メッセージは、非アクティブなメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-223">If a user who has a mailbox in Exchange Online leaves your organization and their Microsoft 365 account is deleted, their chat messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="59b50-224">チャット メッセージは、引き続きメールボックスが非アクティブになる前にユーザーに配置されたアイテム保持ポリシーの適用対象となり、電子情報開示の検索が可能です。</span><span class="sxs-lookup"><span data-stu-id="59b50-224">The chat messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="59b50-225">詳細については、「[Exchange Online の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59b50-225">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="59b50-226">ユーザーが Teams にファイルを保存している場合は、SharePoint と OneDrive の[同等のセクション](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59b50-226">If the user stored any files in Teams, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="59b50-227">制限事項</span><span class="sxs-lookup"><span data-stu-id="59b50-227">Limitations</span></span>

<span data-ttu-id="59b50-228">Teams の保持機能の最適化に継続的に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="59b50-228">We're continuously working on optimizing retention functionality in Teams.</span></span> <span data-ttu-id="59b50-229">当面は、Teams チャネル メッセージとチャットにアイテム保持ポリシーを使用する場合、次の制限に注意してください。</span><span class="sxs-lookup"><span data-stu-id="59b50-229">In the meantime, be aware of the following limitation when you use retention policies for Teams channel messages and chats:</span></span>

- <span data-ttu-id="59b50-230">**Outlook での誤った表示の問題**。</span><span class="sxs-lookup"><span data-stu-id="59b50-230">**Incorrect display issue in Outlook**.</span></span> <span data-ttu-id="59b50-231">Skype または Teams の場所用にアイテム保持ポリシーを作成する場合、ユーザーが Outlook デスクトップ クライアントでメールボックス フォルダーのプロパティを表示すると、これらのポリシーの 1 つが既定のフォルダーポリシーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-231">If you create retention policies for Skype or Teams locations, one of those policies is shown as the default folder policy when a user views the properties of a mailbox folder in the Outlook desktop client.</span></span> <span data-ttu-id="59b50-232">これは、Outlook の誤表示の問題であり、[既知の問題](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)です。</span><span class="sxs-lookup"><span data-stu-id="59b50-232">This is an incorrect display issue in Outlook and [a known issue](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies).</span></span> <span data-ttu-id="59b50-233">代わりに、フォルダーに適用されているメールボックスの保持ポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="59b50-233">Instead, you should see the mailbox retention policy that's applied to the folder.</span></span> <span data-ttu-id="59b50-234">Skype または Teams の保持ポリシーは、ユーザーのメールボックスには適用されません。</span><span class="sxs-lookup"><span data-stu-id="59b50-234">The Skype or Teams retention policy is not applied to the user's mailbox.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="59b50-235">構成ガイダンス</span><span class="sxs-lookup"><span data-stu-id="59b50-235">Configuration guidance</span></span>

<span data-ttu-id="59b50-236">Microsoft 365 で保持を構成するのが初めての場合は、「[アイテム保持ポリシーと保持ラベルの使用を開始する](get-started-with-retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59b50-236">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="59b50-237">Teams 用のアイテム保持ポリシーを構成する準備ができた場合は、「[アイテム保持ポリシーを作成して構成する](create-retention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59b50-237">If you're ready to configure a retention policy for Teams, see [Create and configure retention policies](create-retention-policies.md).</span></span>