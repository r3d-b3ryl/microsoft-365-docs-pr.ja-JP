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
ms.openlocfilehash: e3cd36fe6a7f075516d7778094ff5dd29480bfd9
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794129"
---
# <a name="learn-about-retention-for-microsoft-teams"></a><span data-ttu-id="4c1b0-103">Microsoft Teams の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="4c1b0-103">Learn about retention for Microsoft Teams</span></span>

><span data-ttu-id="4c1b0-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="4c1b0-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="4c1b0-105">この記事の情報は[保持の詳細](retention.md)に関する記事を補足するもので、Microsoft Teams メッセージに固有の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-105">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Microsoft Teams messages.</span></span>

<span data-ttu-id="4c1b0-106">その他のワークロードについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-106">For other workloads, see:</span></span>

- [<span data-ttu-id="4c1b0-107">SharePoint と OneDrive の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="4c1b0-107">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="4c1b0-108">Yammerの保持の詳細</span><span class="sxs-lookup"><span data-stu-id="4c1b0-108">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)
- [<span data-ttu-id="4c1b0-109">Exchange の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="4c1b0-109">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="4c1b0-110">保持と削除の対象となる機能</span><span class="sxs-lookup"><span data-stu-id="4c1b0-110">What's included for retention and deletion</span></span>

<span data-ttu-id="4c1b0-111">次の Teams アイテムは、Teams のアイテム保持ポリシーを使用して保持および削除できます: 埋め込みの画像、テーブル、ハイパーテキスト リンク、および他の Teams メッセージやファイルへのリンクを含む、チャット メッセージとチャネル メッセージ。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-111">The following Teams items can be retained and deleted by using retention policies for Teams: Chat messages and channel messages, including embedded images, tables, hypertext links and links to other Teams messages and files.</span></span> <span data-ttu-id="4c1b0-112">チャット メッセージには、チャット内のすべてのユーザーの名前が含まれ、チャネル メッセージにはチーム名とメッセージの件名 (提供されている場合) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-112">Chat messages include all the names of the people in the chat, and channel messages include the team name and the message title (if supplied).</span></span> 

<span data-ttu-id="4c1b0-113">プライベート チャネルの Teams メッセージは含まれません。また、他のユーザーからの絵文字での応答は含まれません。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-113">Teams messages in private channels are not included, and reactions from others in the form of emoticons are not included.</span></span>

<span data-ttu-id="4c1b0-114">Teams で使用するメールとファイルは、Teams のアイテム保持ポリシーに含まれていません。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-114">Emails and files that you use with Teams aren't included in retention policies for Teams.</span></span> <span data-ttu-id="4c1b0-115">これらのアイテムには、独自のアイテム保持ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-115">These items have their own retention policies.</span></span>

## <a name="how-retention-works-with-microsoft-teams"></a><span data-ttu-id="4c1b0-116">Microsoft Teams での保持のしくみ</span><span class="sxs-lookup"><span data-stu-id="4c1b0-116">How retention works with Microsoft Teams</span></span>

<span data-ttu-id="4c1b0-117">アイテム保持ポリシーを使用して、Teams 内のチャットとチャネル メッセージからデータを保持できます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-117">You can use a retention policy to retain data from chats and channel messages in Teams.</span></span> <span data-ttu-id="4c1b0-118">Teams のチャットからのデータは、チャットに含まれる各ユーザーのメールボックス内の隠しフォルダーに保存されます。また、Teams のチャネル メッセージからのデータは、チーム用のグループ メールボックス内の同様の隠しフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-118">Data from Teams chats is stored in a hidden folder in the mailbox of each user included in the chat, and data from Teams channel messages is stored in a similar hidden folder in the group mailbox for the team.</span></span>

<span data-ttu-id="4c1b0-119">Azure を利用したチャット サービスでもこのデータが保存されますが、Teams でもこのサービスを使用していることを理解することが重要です。既定では、このサービスはデータを無期限に保存します。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-119">It's important to understand that Teams uses an Azure-powered chat service that also stores this data, and by default this service stores the data indefinitely.</span></span> <span data-ttu-id="4c1b0-120">このため、この Teams データを保持および削除する場合は、Teams の場所を使用する保持ポリシーを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-120">For this reason, we recommend that you create a retention policy that uses the Teams locations to retain and delete this Teams data.</span></span> <span data-ttu-id="4c1b0-121">この保持ポリシーでは、Exchange メールボックスとその基になる Azure を利用したチャット サービスの両方から完全にこのデータが削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-121">This retention policy can permanently delete this data from both the Exchange mailboxes and the underlying Azure-powered chat service.</span></span> <span data-ttu-id="4c1b0-122">詳細については、「[Microsoft Teams のセキュリティとコンプライアンス](https://go.microsoft.com/fwlink/?linkid=871258)」、特に「[情報保護アーキテクチャ](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-122">For more information, see [Security and compliance in Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258) and specifically, the [Information Protection Architecture](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture) section.</span></span>

<span data-ttu-id="4c1b0-123">Teams のチャットとチャネル メッセージは、ユーザーまたはグループのメールボックスに対して構成されているアイテム保持ポリシーの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-123">Teams chats and channel messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="4c1b0-124">Teams のチャットとチャネル メッセージは Exchange に保存されますが、この Teams のデータは、**Teams のチャネル メッセージ** と **Teams のチャット** の場所に対して構成されているアイテム保持ポリシーによってのみ含まれます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-124">Even though Teams chats and channel messages are stored in Exchange, this Teams data is included only by a retention policy that's configured for the **Teams channel messages** and **Teams chats** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="4c1b0-125">ユーザーが Teams データを保持するアクティブなアイテム保持ポリシーに含まれている場合、このポリシーに含まれるユーザーのメールボックスを削除すると、Teams のデータを保持するためにメールボックスは[非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)に変換されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-125">If a user is included in an active retention policy that retains Teams data and you a delete a mailbox of a user who is included in this policy, to retain the Teams data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="4c1b0-126">ユーザーのこの Teams のデータを保持する必要がない場合は、メールボックスを削除する前に、アイテム保持ポリシーからそのユーザー アカウントを除外します。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-126">If you don't need to retain this Teams data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="4c1b0-127">チャット メッセージとチャネル メッセージのアイテム保持ポリシーが構成されると、Exchange サービスのタイマー ジョブが、これらの Teams メッセージが保存されている隠しフォルダ内のアイテムを定期的に評価します。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-127">After a retention policy is configured for chat and channel messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Teams messages are stored.</span></span> <span data-ttu-id="4c1b0-128">このタイマー ジョブを実行するには、最大 7 日間かかります。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-128">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="4c1b0-129">アイテムの保持期間が満了すると、これらのアイテムは SubstrateHolds フォルダに移動されます。これは、すべてのユーザーまたはグループのメールボックスにある別の隠しフォルダで、「論理的に削除済み」アイテムが完全に削除される前に保存するためのものです。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-129">When these items have expired their retention period, they are moved to the SubstrateHolds folder—another hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

<span data-ttu-id="4c1b0-130">アイテム保持ポリシーがチャット メッセージとチャネル メッセージに対して構成された後のコンテンツのパスは、アイテム保持ポリシーの保持後に削除、保持のみ、あるいは削除のみのどれであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-130">After a retention policy is configured for chat and channel messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="4c1b0-131">アイテム保持ポリシーが保持されてから削除される場合</span><span class="sxs-lookup"><span data-stu-id="4c1b0-131">When the retention policy is to retain and then delete:</span></span>

![Teams チャットとチャネル メッセージの保持フローの図](../media/teamsretentionlifecycle.png)

<span data-ttu-id="4c1b0-133">図内の 2 つのパスの場合:</span><span class="sxs-lookup"><span data-stu-id="4c1b0-133">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="4c1b0-134">**保持期間中にチャット メッセージまたはチャネル メッセージがユーザーによって編集または削除された場合**、元のメッセージは 21 日以内に SubstrateHolds フォルダーにコピー (編集の場合) または移動 (削除の場合) されてます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-134">**If a chat or channel message is edited or deleted** by the user during the retention period, the original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder within 21 days.</span></span> <span data-ttu-id="4c1b0-135">メッセージは保存期間が終了するまで保存され、その後 24 時間以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-135">The message is stored there until the retention period expires and then the message is permanently deleted within 24 hours.</span></span>

2. <span data-ttu-id="4c1b0-136">**チャット メッセージまたはチャネル メッセージが削除されない場合**、および編集した後の現在のメッセージの場合は、保持期間満了後にメッセージは SubstructateHolds フォルダに移動されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-136">**If a chat or channel message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="4c1b0-137">このアクションを実行するには、有効期限の最大で 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-137">This action takes up to 7 days from the expiry date.</span></span> <span data-ttu-id="4c1b0-138">メッセージが SubstrateHolds フォルダにある場合は、24 時間以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-138">When the message is in the SubstrateHolds folder, it is then permanently deleted within 24 hours.</span></span> 

> [!NOTE]
> <span data-ttu-id="4c1b0-139">SubstrateHolds フォルダー内のメッセージは、電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-139">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="4c1b0-140">メッセージは SubstituteHolds フォルダ内から完全に削除されるまで、メッセージは電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-140">Until messages are permanently deleted from this SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="4c1b0-141">アイテム保持ポリシーが保持のみ、または削除のみの場合、コンテンツ パスは保持か削除かで異なります。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-141">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="4c1b0-142">アイテム保持ポリシーが保持のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="4c1b0-142">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="4c1b0-143">**チャット メッセージまたはチャネルのメッセージが編集または削除された場合**、元のメッセージのコピーは 21 日以内に SubstrateHolds フォルダに作成され、保持期間が満了するまでそこに保持されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-143">**If a chat or channel message is edited or deleted**: A copy of the original message is created in the SubstrateHolds folder within 21 days, and retained there until the retention period expires.</span></span> <span data-ttu-id="4c1b0-144">メッセージは、SubstrateHolds フォルダから 24 時間以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-144">Then the message is permanently deleted from the SubstrateHolds folder within 24 hours.</span></span>

2. <span data-ttu-id="4c1b0-145">**アイテムが変更または削除されていない場合**、および保持期間中に編集した後の現在のメッセージの場合は、保持期間の前後には何も起こらず、メッセージは元の場所に残ります。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-145">**If the item is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="4c1b0-146">アイテム保持ポリシーが削除のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="4c1b0-146">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="4c1b0-147">保持期間中に **メッセージが削除されない場合**、保持期間の終了時にメッセージは SubstrateHolds フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-147">**If the message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="4c1b0-148">このアクションを実行するには、有効期限の最大で 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-148">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="4c1b0-149">メッセージは、SubstrateHolds フォルダから 24 時間以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-149">Then the message is permanently deleted from the SubstrateHolds folder within 24 hours.</span></span>

2. <span data-ttu-id="4c1b0-150">期間中にユーザーがアイテムを **削除した場合**、アイテムは 21 日以内に SubstrateHolds フォルダーに移動され、24 時間以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-150">**If the item is deleted by the user** during the period, the item is moved to the SubstrateHolds folder within 21 days where it is then permanently deleted within 24 hours.</span></span>


## <a name="skype-for-business-and-teams-interop-chats"></a><span data-ttu-id="4c1b0-151">Skype for Business および Teams の相互運用チャット</span><span class="sxs-lookup"><span data-stu-id="4c1b0-151">Skype for Business and Teams interop chats</span></span>

<span data-ttu-id="4c1b0-152">Skype for Business のチャットが Teams に届くと、Teams のチャット スレッドのメッセージとなり、適切なメールボックスに取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-152">When a Skype for Business chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="4c1b0-153">Teams のアイテム保持ポリシーは、これらのメッセージに Teams のスレッドから適用されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-153">Teams retention policies will apply to these messages from the Teams thread.</span></span> 

<span data-ttu-id="4c1b0-154">ただし、Skype for Business に対して会話履歴がオンになっていて、Skype for Business のクライアント側からその履歴がメールボックスに保存されている場合、このチャット データは Teams のアイテム保持ポリシーでは処理されません。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-154">However, if conversation history is turned on for Skype for Business and from the Skype for Business client side that history is being saved into a mailbox, that chat data isn't handled by a Teams retention policy.</span></span> <span data-ttu-id="4c1b0-155">このコンテンツには、Skype for Business に構成されているアイテム保持ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-155">For this content, use a retention policy that's configured for Skype for Business.</span></span>

## <a name="meetings-and-external-users"></a><span data-ttu-id="4c1b0-156">会議と外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="4c1b0-156">Meetings and external users</span></span>

<span data-ttu-id="4c1b0-157">チャネル会議メッセージはチャネル メッセージと同じ方法で保存されるため、このデータについては、アイテム保持ポリシーを構成するときに、**Teams チャネル メッセージ** の場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-157">Channel meeting messages are stored the same way as channel messages, so for this data, select the **Teams channel messages** location when you configure your retention policy.</span></span>

<span data-ttu-id="4c1b0-158">一時的な会議メッセージはグループ チャット メッセージと同じ方法で保存されるため、このデータについては、アイテム保持ポリシーを構成するときに、**Teams チャット** の場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-158">Impromptu meeting messages are stored in the same way as group chat messages, so for this data, select the **Teams chats** location when you configure your retention policy.</span></span>

<span data-ttu-id="4c1b0-159">組織が主催する会議に外部ユーザーが含まれる場合:</span><span class="sxs-lookup"><span data-stu-id="4c1b0-159">When external users are included in a meeting that your organization hosts:</span></span>

- <span data-ttu-id="4c1b0-160">外部ユーザーがテナントのゲスト アカウントを使用して参加する場合、このユーザーには、組織の Teams のアイテム保持ポリシーの対象となるシャドウ メールボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-160">If an external user joins by using a guest account in your tenant, this user has a shadow mailbox that can be subject to your organization's retention policy for Teams.</span></span> <span data-ttu-id="4c1b0-161">会議からのメッセージはすべて、ユーザーのメールボックスとシャドウ メールボックスの両方に保存されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-161">Any messages from the meeting are stored in both your users' mailbox and the shadow mailbox.</span></span> 

- <span data-ttu-id="4c1b0-162">外部ユーザーが別の Microsoft 365 組織のアカウントを使用して参加した場合、そのユーザーのメッセージは別のテナントのメールボックスに保存されるため、削除できません。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-162">If an external user joins by using an account from another Microsoft 365 organization, your retention policies can't delete messages for this user because they are stored in that user's mailbox in another tenant.</span></span> <span data-ttu-id="4c1b0-163">ただし、同じ会議の場合、アイテム保持ポリシーによりユーザーのメッセージが削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-163">For the same meeting however, your retention policies can delete messages for your users.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="4c1b0-164">ユーザーが組織を離れる場合</span><span class="sxs-lookup"><span data-stu-id="4c1b0-164">When a user leaves the organization</span></span> 

<span data-ttu-id="4c1b0-165">Exchange Online のメールボックスを持っているユーザーが組織を離れ、そのユーザーの Microsoft 365 アカウントが削除された場合、保持の対象となるチャット メッセージは、非アクティブなメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-165">If a user who has a mailbox in Exchange Online leaves your organization and their Microsoft 365 account is deleted, their chat messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="4c1b0-166">チャット メッセージは、引き続きメールボックスが非アクティブになる前にユーザーに配置されたアイテム保持ポリシーの適用対象となり、電子情報開示の検索が可能です。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-166">The chat messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="4c1b0-167">詳細については、「[Exchange Online の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-167">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="4c1b0-168">ユーザーが Teams にファイルを保存している場合は、SharePoint と OneDrive の[同等のセクション](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-168">If the user stored any files in Teams, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="4c1b0-169">制限事項</span><span class="sxs-lookup"><span data-stu-id="4c1b0-169">Limitations</span></span>

<span data-ttu-id="4c1b0-170">Teams の保持機能の最適化に継続的に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-170">We're continuously working on optimizing retention functionality in Teams.</span></span> <span data-ttu-id="4c1b0-171">それまでの間、Teams のチャネル メッセージとチャットで保持を使用する場合は、次の制限事項に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-171">In the meantime, here are a few limitations to be aware of when you use retention for Teams channel messages and chats:</span></span>

- <span data-ttu-id="4c1b0-172">**Outlook での誤った表示の問題**。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-172">**Incorrect display issue in Outlook**.</span></span> <span data-ttu-id="4c1b0-173">Skype または Teams の場所用にアイテム保持ポリシーを作成する場合、ユーザーが Outlook デスクトップ クライアントでメールボックス フォルダーのプロパティを表示すると、これらのポリシーの 1 つが既定のフォルダーポリシーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-173">If you create retention policies for Skype or Teams locations, one of those policies is shown as the default folder policy when a user views the properties of a mailbox folder in the Outlook desktop client.</span></span> <span data-ttu-id="4c1b0-174">これは、Outlook の誤表示の問題であり、[既知の問題](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)です。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-174">This is an incorrect display issue in Outlook and [a known issue](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies).</span></span> <span data-ttu-id="4c1b0-175">既定のフォルダー ポリシーとして表示されるのは、フォルダーに適用されるメールボックス保持ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-175">What should be displayed as the default folder policy is the mailbox retention policy that's applied to the folder.</span></span> <span data-ttu-id="4c1b0-176">Skype または Teams の保持ポリシーは、ユーザーのメールボックスには適用されません。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-176">The Skype or Teams retention policy is not applied to the user's mailbox.</span></span>

- <span data-ttu-id="4c1b0-177">**構成の問題**:</span><span class="sxs-lookup"><span data-stu-id="4c1b0-177">**Configuration issues**:</span></span> 
    - <span data-ttu-id="4c1b0-178">**[Teams のチャネル メッセージ]** の場所にある **[チームの選択]** を選択した場合、チームではない Microsoft 365 グループが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-178">When you select **Choose teams** for the **Teams channel messages** location, you might see Microsoft 365 groups that aren't also teams.</span></span> <span data-ttu-id="4c1b0-179">これらのグループは選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-179">Don't select these groups.</span></span>
    
    - <span data-ttu-id="4c1b0-180">**[Teams のチャット]** の場所にある **[ユーザーの選択]** を選択した場合、ゲストや、メールボックスのユーザーではないユーザーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-180">When you select **Choose users** for the **Teams chats** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="4c1b0-181">アイテム保持ポリシーはこれらのユーザー向けに設計されていないため、選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-181">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="4c1b0-182">構成ガイダンス</span><span class="sxs-lookup"><span data-stu-id="4c1b0-182">Configuration guidance</span></span>

<span data-ttu-id="4c1b0-183">Microsoft 365 で保持を構成するのが初めての場合は、「[アイテム保持ポリシーと保持ラベルの使用を開始する](get-started-with-retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-183">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="4c1b0-184">Teams 用のアイテム保持ポリシーを構成する準備ができた場合は、「[アイテム保持ポリシーを作成して構成する](create-retention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c1b0-184">If you're ready to configure a retention policy for Teams, see [Create and configure retention policies](create-retention-policies.md).</span></span>
