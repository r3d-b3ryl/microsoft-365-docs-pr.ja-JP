---
title: Exchange のアイテム保持の詳細
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
description: Exchange の保持のしくみについて説明します。
ms.openlocfilehash: efb95b22355bff292ef63c77fb77fb5a15d66722
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861133"
---
# <a name="learn-about-retention-for-exchange"></a><span data-ttu-id="9088a-103">Exchange の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="9088a-103">Learn about retention for Exchange</span></span>

<span data-ttu-id="9088a-104">この記事の情報は[保持の詳細](retention.md)に関する記事を補足するもので、Exchange に固有の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9088a-104">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Exchange.</span></span>  <span data-ttu-id="9088a-105">その他のワークロードについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9088a-105">For other workloads, see:</span></span>

- [<span data-ttu-id="9088a-106">SharePoint と OneDrive の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="9088a-106">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="9088a-107">Microsoft Teams の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="9088a-107">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="9088a-108">Yammerの保持の詳細</span><span class="sxs-lookup"><span data-stu-id="9088a-108">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="9088a-109">保持と削除の対象となる機能</span><span class="sxs-lookup"><span data-stu-id="9088a-109">What's included for retention and deletion</span></span>

<span data-ttu-id="9088a-110">添付ファイル付きのメール メッセージ (下書きを含む)、終了日がある場合のタスク、およびメモの Exchange アイテムは、アイテム保持ポリシーと保持ラベルを使用して保持および削除できます。</span><span class="sxs-lookup"><span data-stu-id="9088a-110">The following Exchange items can be retained and deleted by using retention policies and retention labels: Mail messages (includes drafts) with any attachments, tasks when they have an end date, and notes.</span></span> 

<span data-ttu-id="9088a-111">終了日がある予定表アイテムはアイテム保持ポリシーでサポートされていますが、保持ラベルではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9088a-111">Calendar items that have an end date are supported for retention policies but aren't supported for retention labels.</span></span>

<span data-ttu-id="9088a-112">連絡先、および終了日が設定されていないタスクおよび予定表アイテムはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="9088a-112">Contacts, and any tasks and calendar items that don't have an end date are not supported.</span></span>

<span data-ttu-id="9088a-p102">Skype や Teams メッセージなど、メールボックスに保存されているその他のアイテムは、Exchange のアイテム保持ポリシーやラベルには含まれません。これらのアイテムには独自のアイテム保持ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="9088a-p102">Other items stored in a mailbox, such as Skype and Teams messages, aren't included in retention policies or labels for Exchange. These items have their own retention policies.</span></span>

## <a name="how-retention-works-for-exchange"></a><span data-ttu-id="9088a-115">Exchange の保持のしくみ</span><span class="sxs-lookup"><span data-stu-id="9088a-115">How retention works for Exchange</span></span>

<span data-ttu-id="9088a-116">メールボックスとパブリック フォルダーの両方とも、アイテムを保持するために、[[回復可能なアイテム] フォルダー](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) を使用します。</span><span class="sxs-lookup"><span data-stu-id="9088a-116">Both a mailbox and a public folder use the [Recoverable Items folder](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) to retain items.</span></span> <span data-ttu-id="9088a-117">電子情報開示のアクセス許可を割り当てられているユーザーだけが、他のユーザーの [回復可能なアイテム] フォルダーのアイテムを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9088a-117">Only people who have been assigned eDiscovery permissions can view items in another user's Recoverable Items folder.</span></span>
  
<span data-ttu-id="9088a-p104">ユーザーが [削除済みアイテム] フォルダー以外のフォルダー内のメッセージを削除すると、既定では、そのメッセージは [削除済みアイテム] フォルダーに移動されます。ユーザーが [削除済みアイテム] フォルダー内のアイテムを削除すると、そのメッセージは [回復可能なアイテム] フォルダーに移動されます。ただし、ユーザーは任意のフォルダー内のアイテムを論理的に削除できます (Shift+Del)。この操作により、アイテムは [削除済みアイテム] フォルダーをバイパスして、[回復可能なアイテム] フォルダーに直接移動されます。</span><span class="sxs-lookup"><span data-stu-id="9088a-p104">When a person deletes a message in a folder other than the Deleted Items folder, by default, the message moves to the Deleted Items folder. When a person deletes an item in the Deleted Items folder, the message is moved to the Recoverable Items folder. However, a user can soft delete an item (Shift+Delete) in any folder, which bypasses the Deleted Items folder and moves the item directly to the Recoverable Items folder.</span></span>
  
<span data-ttu-id="9088a-121">Exchange データに保持設定を適用すると、[回復可能なアイテム] フォルダー内のアイテムがタイマー ジョブによって定期的に評価されます。</span><span class="sxs-lookup"><span data-stu-id="9088a-121">When you apply retention settings to Exchange data, a timer job periodically evaluates items in the Recoverable Items folder.</span></span> <span data-ttu-id="9088a-122">アイテムが、アイテムを保持するために少なくとも 1 つのアイテム保持ポリシーまたは保持ラベルのルールと一致しない場合、そのアイテムは [回復可能なアイテム] フォルダーから完全に削除されます (物理的な削除とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="9088a-122">If an item doesn't match the rules of at least one retention policy or retention label to retain the item, it is permanently deleted (also called hard deleted) from the Recoverable Items folder.</span></span>

> [!NOTE]
> <span data-ttu-id="9088a-123">[データ保持の第 1 原則により](retention.md#the-principles-of-retention-or-what-takes-precedence)、別のアイテム保持ポリシーまたは保持ラベルのために同じアイテムを保持する必要がある場合、または法的、調査上の理由から電子情報開示の保留リストにある場合、完全な削除は常に中断されます。</span><span class="sxs-lookup"><span data-stu-id="9088a-123">Because of the [first principle of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), permanent deletion is always suspended if the same item must be retained because of another retention policy or retention label, or it is under eDiscovery holds for legal or investigative reasons.</span></span>

<span data-ttu-id="9088a-124">タイマー ジョブの実行には最大 7 日かかる場合があり、Exchange の場所には少なくとも 10 MB が必要です。</span><span class="sxs-lookup"><span data-stu-id="9088a-124">The timer job can take up to seven days to run and the Exchange location must contain at least 10 MB.</span></span>
  
<span data-ttu-id="9088a-p106">ユーザーがメールボックス アイテムのプロパティ (件名、本文、添付ファイル、送信者と受信者、メッセージの送信日や受信日など) を変更しようとすると、変更がコミットされる前に、元のアイテムのコピーが [回復可能なアイテム] フォルダーに保存されます。この処理は、それ以降の変更のたびに実行されます。[回復可能なアイテム] フォルダー内のコピーは、保持期間の期限に達すると、完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="9088a-p106">When a user attempts to change properties of a mailbox item—such as the subject, body, attachments, senders and recipients, or date sent or received for a message—a copy of the original item is saved to the Recoverable Items folder before the change is committed. This action happens for each subsequent change. At the end of the retention period, copies in the Recoverable Items folder are permanently deleted.</span></span>

<span data-ttu-id="9088a-128">保持設定が Exchange のコンテンツに適用された後のコンテンツのパスは、保持設定が保持および削除、保持のみ、あるいは削除のみのどれであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9088a-128">After retention settings are applied to Exchange content, the paths the content takes depend on whether the retention settings are to retain and delete, to retain only, or delete only.</span></span>

<span data-ttu-id="9088a-129">保持設定が保持および削除の場合</span><span class="sxs-lookup"><span data-stu-id="9088a-129">When the retention settings are to retain and delete:</span></span>

![メールおよびパブリック フォルダーの保持フローの図](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. <span data-ttu-id="9088a-131">**保持期間中、ユーザーがアイテムを変更または完全に削除した場合** (この操作は Shift キーと Delete キーを押すか、[削除済みアイテム] から削除して行います): アイテムは [回復可能なアイテム] フォルダーに移動 (編集する場合はコピー) されます。</span><span class="sxs-lookup"><span data-stu-id="9088a-131">**If the item is modified or permanently deleted** by the user (either SHIFT+DELETE or deleted from Deleted Items) during the retention period: The item is moved (or copied, in the case of edit) to the Recoverable Items folder.</span></span> <span data-ttu-id="9088a-132">ここで、タイマー ジョブが定期的に実行され、アイテム保持ポリシーの有効期間が過ぎたアイテムを特定します。このようなアイテムは、保持期間の最終日から 14 日以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="9088a-132">There, a timer job runs periodically and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="9088a-133">既定の設定は 14 日間ですが、最長 30 日間まで設定できます。</span><span class="sxs-lookup"><span data-stu-id="9088a-133">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span>

2. <span data-ttu-id="9088a-p108">保持期間中に **アイテムが変更または削除されていない場合は**、同じプロセスがメールボックス内のすべてのフォルダーに対して定期的に実行され、アイテム保持期間を過ぎたアイテムを特定します。これに該当するアイテムは、保持期間の最終日から 14 日以内に完全に削除されます。既定の設定は 14 日間ですが、最長 30 日間まで設定できます。</span><span class="sxs-lookup"><span data-stu-id="9088a-p108">**If the item is not modified or deleted** during the retention period: The same process runs periodically on all folders in the mailbox and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period. Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span> 

<span data-ttu-id="9088a-136">保持設定が保持のみ、または削除のみの場合、コンテンツ パスは保持か削除かで異なります。</span><span class="sxs-lookup"><span data-stu-id="9088a-136">When the retention settings are retain-only, or delete-only, the contents paths are variations of retain and delete:</span></span>

### <a name="content-paths-for-retain-only-retention-settings"></a><span data-ttu-id="9088a-137">保持設定が保持のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="9088a-137">Content paths for retain-only retention settings</span></span>

1. <span data-ttu-id="9088a-138">保持期間中に、**アイテムが変更または削除された場合**、元のアイテムのコピーが [回復可能なアイテム] フォルダーに作成され、保持期間の終了まで保持されます。保持期間が終了すると、[回復可能なアイテム] フォルダー内のコピーは、アイテムの有効期限が切れてから 14 日以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="9088a-138">**If the item is modified or deleted** during the retention period: A copy of the original item is created in the Recoverable Items folder and retained until the end of the retention period, when the copy in the Recoverable Items folder is permanently deleted within 14 days after the item expires.</span></span> 

2. <span data-ttu-id="9088a-139">保持期間中に **アイテムが変更または削除されてない場合**、保持期間の前後には何も起こりません。アイテムは、元の場所に残ります。</span><span class="sxs-lookup"><span data-stu-id="9088a-139">**If the item is not modified or deleted** during the retention period: Nothing happens before and after the retention period; the item remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-settings"></a><span data-ttu-id="9088a-140">保持設定が削除のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="9088a-140">Content paths for delete-only retention settings</span></span>

1. <span data-ttu-id="9088a-141">設定した期間中に **アイテムが削除されない場合**: アイテム保持ポリシーで構成された期間の最後に、アイテムは [回復可能なアイテム] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="9088a-141">**If the item is not deleted** during the configured period: At the end of the configured period in the retention policy, the item is moved to the Recoverable Items folder.</span></span> 

2. <span data-ttu-id="9088a-142">設定した期間中に **アイテムが削除された場合**: アイテムはすぐに [回復可能なアイテム] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="9088a-142">**If the item is deleted** during the configured period: The item is immediately moved to the Recoverable Items folder.</span></span> <span data-ttu-id="9088a-143">ユーザーが [回復可能なアイテム] フォルダーからアイテムを削除するかフォルダーを空にすると、そのアイテムは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="9088a-143">If a user deletes the item from there or empties the Recoverable Items folder, the item is permanently deleted.</span></span> <span data-ttu-id="9088a-144">それ以外の場合、14 日が経過すると、アイテムは [回復可能なアイテム] フォルダーから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="9088a-144">Otherwise, the item is permanently deleted after being in the Recoverable Items folder for 14 days.</span></span> 

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="9088a-145">ユーザーが組織を離れる場合</span><span class="sxs-lookup"><span data-stu-id="9088a-145">When a user leaves the organization</span></span> 

<span data-ttu-id="9088a-146">ユーザーが組織を離れるときに、ユーザーのメールボックスがアイテム保持ポリシーに含まれていると、ユーザーの Microsoft 365 アカウントが削除されるときにメールボックスは非アクティブなメールボックスになります。</span><span class="sxs-lookup"><span data-stu-id="9088a-146">If a user leaves your organization and the user's mailbox is included in a retention policy, the mailbox becomes an inactive mailbox when the user's Microsoft 365 account is deleted.</span></span> <span data-ttu-id="9088a-147">非アクティブなメールボックスのコンテンツは、メールボックスが非アクティブになる前に配置されたアイテム保持ポリシーがあれば、引き続きその適用対象となり、電子情報開示の検索が可能です。</span><span class="sxs-lookup"><span data-stu-id="9088a-147">The contents of an inactive mailbox are still subject to any retention policy that was placed on the mailbox before it was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="9088a-148">詳細については、「[Exchange Online の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9088a-148">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="9088a-149">構成ガイダンス</span><span class="sxs-lookup"><span data-stu-id="9088a-149">Configuration guidance</span></span>

<span data-ttu-id="9088a-150">Microsoft 365 で保持を構成するのが初めての場合は、「[アイテム保持ポリシーと保持ラベルの使用を開始する](get-started-with-retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9088a-150">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="9088a-151">Exchange のアイテム保持ポリシーまたは保持ラベルを構成する準備ができたら、以下の手順をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9088a-151">If you're ready to configure a retention policy or retention label for Exchange, see the following instructions:</span></span>
- [<span data-ttu-id="9088a-152">アイテム保持ポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="9088a-152">Create and configure retention policies</span></span>](create-retention-policies.md)
- [<span data-ttu-id="9088a-153">アイテム保持ラベルを作成してアプリに適用する</span><span class="sxs-lookup"><span data-stu-id="9088a-153">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="9088a-154">保持ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="9088a-154">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)