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
ms.openlocfilehash: e12f46b68feb4b64ade14cfb046061d89e1a607c
ms.sourcegitcommit: 916fa2dacbc13287b49823176375259d7af03f86
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "47394714"
---
# <a name="learn-about-retention-for-exchange"></a><span data-ttu-id="ff002-103">Exchange の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="ff002-103">Learn about retention for Exchange</span></span>

<span data-ttu-id="ff002-104">この記事の情報は[保持の詳細](retention.md)に関する記事を補足するもので、Exchange に固有の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ff002-104">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Exchange.</span></span>

## <a name="how-retention-works-for-exchange"></a><span data-ttu-id="ff002-105">Exchange の保持のしくみ</span><span class="sxs-lookup"><span data-stu-id="ff002-105">How retention works for Exchange</span></span>

<span data-ttu-id="ff002-106">メールボックスとパブリック フォルダーの両方とも、アイテムを保持するために、[[回復可能なアイテム] フォルダー](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) を使用します。</span><span class="sxs-lookup"><span data-stu-id="ff002-106">Both a mailbox and a public folder use the [Recoverable Items folder](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) to retain items.</span></span> <span data-ttu-id="ff002-107">電子情報開示のアクセス許可を割り当てられているユーザーだけが、他のユーザーの [回復可能なアイテム] フォルダーのアイテムを表示できます。</span><span class="sxs-lookup"><span data-stu-id="ff002-107">Only people who have been assigned eDiscovery permissions can view items in another user's Recoverable Items folder.</span></span>
  
<span data-ttu-id="ff002-108">既定では、削除済みアイテム フォルダー以外のフォルダーからメッセージを削除すると、そのメッセージは削除済みアイテム フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="ff002-108">When a person deletes a message in a folder other than the Deleted Items folder, by default, the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="ff002-109">ユーザーが [削除済みアイテム] フォルダー内のアイテムを削除すると、メッセージは [回復可能なアイテム] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="ff002-109">When a person deletes an item in the Deleted Items folder, the message is moved to the Recoverable Items folder.</span></span> <span data-ttu-id="ff002-110">ただし、ユーザーは、任意のフォルダー内のアイテムを論理的な削除 (Shift + Delete) ができます。これにより、削除済みアイテム フォルダーがバイパスされ、アイテムが回復可能なアイテム フォルダーに直接移動します。</span><span class="sxs-lookup"><span data-stu-id="ff002-110">However, a user can soft delete an item (Shift+Delete) in any folder, which bypasses the Deleted Items folder and moves the item directly to the Recoverable Items folder.</span></span>
  
<span data-ttu-id="ff002-111">Exchange データに保持設定を適用すると、[回復可能なアイテム] フォルダー内のアイテムがタイマー ジョブによって定期的に評価されます。</span><span class="sxs-lookup"><span data-stu-id="ff002-111">When you apply retention settings to Exchange data, a timer job periodically evaluates items in the Recoverable Items folder.</span></span> <span data-ttu-id="ff002-112">アイテムが少なくとも 1 つのアイテム保持ポリシーまたは保持ラベルと一致しない場合、そのアイテムは [回復可能なアイテム] フォルダーから完全に削除されます (物理的な削除とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="ff002-112">If an item doesn't match the rules of at least one retention policy or retention label, the item is permanently deleted (also called hard deleted) from the Recoverable Items folder.</span></span>

<span data-ttu-id="ff002-113">タイマー ジョブの実行には最大 7 日かかる場合があり、Exchange の場所には少なくとも 10 MB が必要です。</span><span class="sxs-lookup"><span data-stu-id="ff002-113">The timer job can take up to seven days to run and the Exchange location must contain at least 10 MB.</span></span>
  
<span data-ttu-id="ff002-114">ユーザーがメールボックスのアイテムのプロパティ (件名、本文、添付ファイル、送信者と受信者、メッセージの送受信日付など) を変更しようとすると、変更が確定される前に元のアイテムのコピーが [回復可能なアイテム] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="ff002-114">When a user attempts to change properties of a mailbox item—such as the subject, body, attachments, senders and recipients, or date sent or received for a message—a copy of the original item is saved to the Recoverable Items folder before the change is committed.</span></span> <span data-ttu-id="ff002-115">2 番目以降の変更ごとに、この操作が繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="ff002-115">This action happens for each subsequent change.</span></span> <span data-ttu-id="ff002-116">保持期間が終了すると、[回復可能なアイテム] フォルダー内のコピーは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ff002-116">At the end of the retention period, copies in the Recoverable Items folder are permanently deleted.</span></span>

<span data-ttu-id="ff002-117">保持設定が Exchange のコンテンツに適用された後のコンテンツのパスは、保持設定が保持および削除、保持のみ、あるいは削除のみのどれであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ff002-117">After retention settings are applied to Exchange content, the paths the content takes depend on whether the retention settings are to retain and delete, to retain only, or delete only.</span></span>

<span data-ttu-id="ff002-118">保持設定が保持および削除の場合</span><span class="sxs-lookup"><span data-stu-id="ff002-118">When the retention settings are to retain and delete:</span></span>

![メールおよびパブリック フォルダーの保持フローの図](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. <span data-ttu-id="ff002-120">**保持期間中、ユーザーがアイテムを変更または完全に削除した場合** (この操作は Shift キーと Delete キーを押すか、[削除済みアイテム] から削除して行います): アイテムは [回復可能なアイテム] フォルダーに移動 (編集する場合はコピー) されます。</span><span class="sxs-lookup"><span data-stu-id="ff002-120">**If the item is modified or permanently deleted** by the user (either SHIFT+DELETE or deleted from Deleted Items) during the retention period: The item is moved (or copied, in the case of edit) to the Recoverable Items folder.</span></span> <span data-ttu-id="ff002-121">ここで、タイマー ジョブが定期的に実行され、アイテム保持ポリシーの有効期間が過ぎたアイテムを特定します。このようなアイテムは、保持期間の最終日から 14 日以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ff002-121">There, a timer job runs periodically and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="ff002-122">既定の設定は 14 日間ですが、最長 30 日間まで設定できます。</span><span class="sxs-lookup"><span data-stu-id="ff002-122">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span>

2. <span data-ttu-id="ff002-123">保存期間中に**アイテムが変更または削除されない場合**: メールボックス内のすべてのフォルダーで同じプロセスが定期的に実行され、保持期間が終了したアイテムを識別します。これらのアイテムは保持期間の終了後 14 日以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ff002-123">**If the item is not modified or deleted** during the retention period: The same process runs periodically on all folders in the mailbox and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="ff002-124">既定の設定は 14 日間ですが、最長 30 日間まで設定できます。</span><span class="sxs-lookup"><span data-stu-id="ff002-124">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span> 

<span data-ttu-id="ff002-125">保持設定が保持のみ、または削除のみの場合、コンテンツ パスは保持か削除かで異なります。</span><span class="sxs-lookup"><span data-stu-id="ff002-125">When the retention settings are retain-only, or delete-only, the contents paths are variations of retain and delete:</span></span>

### <a name="content-paths-for-retain-only-retention-settings"></a><span data-ttu-id="ff002-126">保持設定が保持のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="ff002-126">Content paths for retain-only retention settings</span></span>

1. <span data-ttu-id="ff002-127">保持期間中に、**アイテムが変更または削除された場合**、元のアイテムのコピーが [回復可能なアイテム] フォルダーに作成され、保持期間の終了まで保持されます。保持期間が終了すると、[回復可能なアイテム] フォルダー内のコピーは、アイテムの有効期限が切れてから 14 日以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ff002-127">**If the item is modified or deleted** during the retention period: A copy of the original item is created in the Recoverable Items folder and retained until the end of the retention period, when the copy in the Recoverable Items folder is permanently deleted within 14 days after the item expires.</span></span> 

2. <span data-ttu-id="ff002-128">保持期間中に**アイテムが変更または削除されてない場合**、保持期間の前後には何も起こりません。アイテムは、元の場所に残ります。</span><span class="sxs-lookup"><span data-stu-id="ff002-128">**If the item is not modified or deleted** during the retention period: Nothing happens before and after the retention period; the item remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-settings"></a><span data-ttu-id="ff002-129">保持設定が削除のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="ff002-129">Content paths for delete-only retention settings</span></span>

1. <span data-ttu-id="ff002-130">設定した期間中に**アイテムが削除されない場合**: アイテム保持ポリシーで構成された期間の最後に、アイテムは [回復可能なアイテム] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="ff002-130">**If the item is not deleted** during the configured period: At the end of the configured period in the retention policy, the item is moved to the Recoverable Items folder.</span></span> 

2. <span data-ttu-id="ff002-131">設定した期間中に**アイテムが削除された場合**: アイテムはすぐに [回復可能なアイテム] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="ff002-131">**If the item is deleted** during the configured period: The item is immediately moved to the Recoverable Items folder.</span></span> <span data-ttu-id="ff002-132">ユーザーが [回復可能なアイテム] フォルダーからアイテムを削除するかフォルダーを空にすると、そのアイテムは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ff002-132">If a user deletes the item from there or empties the Recoverable Items folder, the item is permanently deleted.</span></span> <span data-ttu-id="ff002-133">それ以外の場合、14 日が経過すると、アイテムは [回復可能なアイテム] フォルダーから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ff002-133">Otherwise, the item is permanently deleted after being in the Recoverable Items folder for 14 days.</span></span> 

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="ff002-134">ユーザーが組織を離れる場合</span><span class="sxs-lookup"><span data-stu-id="ff002-134">When a user leaves the organization</span></span> 

<span data-ttu-id="ff002-135">ユーザーが組織を離れるときに、ユーザーのメールボックスがアイテム保持ポリシーに含まれていると、ユーザーの Microsoft 365 アカウントが削除されるときにメールボックスは非アクティブなメールボックスになります。</span><span class="sxs-lookup"><span data-stu-id="ff002-135">If a user leaves your organization and the user's mailbox is included in a retention policy, the mailbox becomes an inactive mailbox when the user's Microsoft 365 account is deleted.</span></span> <span data-ttu-id="ff002-136">非アクティブなメールボックスのコンテンツは、メールボックスが非アクティブになる前に配置されたアイテム保持ポリシーがあれば、引き続きその適用対象となり、電子情報開示の検索が可能です。</span><span class="sxs-lookup"><span data-stu-id="ff002-136">The contents of an inactive mailbox are still subject to any retention policy that was placed on the mailbox before it was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="ff002-137">詳細については、「[Exchange Online の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff002-137">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="ff002-138">構成ガイダンス</span><span class="sxs-lookup"><span data-stu-id="ff002-138">Configuration guidance</span></span>

<span data-ttu-id="ff002-139">Microsoft 365 で保持を構成するのが初めての場合は、「[アイテム保持ポリシーと保持ラベルの使用を開始する](get-started-with-retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff002-139">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="ff002-140">Exchange のアイテム保持ポリシーまたは保持ラベルを構成する準備ができたら、以下の手順をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ff002-140">If you're ready to configure a retention policy or retention label for Exchange, see the following instructions:</span></span>
- [<span data-ttu-id="ff002-141">アイテム保持ポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="ff002-141">Create and configure retention policies</span></span>](create-retention-policies.md)
- [<span data-ttu-id="ff002-142">アイテム保持ラベルを作成してアプリに適用する</span><span class="sxs-lookup"><span data-stu-id="ff002-142">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="ff002-143">保持ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="ff002-143">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)