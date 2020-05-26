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
description: Exchange メールと Exchange パブリック フォルダーに特に適用される保持動作について説明します。
ms.openlocfilehash: db39ab0f1eca1cc03dd0bbb5ffb500658695247a
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292535"
---
# <a name="learn-about-retention-policies-for-exchange"></a><span data-ttu-id="9091a-103">Exchange のアイテム保持ポリシーの詳細</span><span class="sxs-lookup"><span data-stu-id="9091a-103">Learn about retention policies for Exchange</span></span>

<span data-ttu-id="9091a-104">この記事の情報は、Exchange に固有の情報が含まれているため、「[アイテム保持ポリシーの詳細](retention-policies.md)」を補足するものです。</span><span class="sxs-lookup"><span data-stu-id="9091a-104">The information in this article supplements [Learn about retention policies](retention-policies.md) because it has information that's specific to Exchange.</span></span>

## <a name="how-a-retention-policy-works-with-exchange-locations"></a><span data-ttu-id="9091a-105">アイテム保持ポリシーは Exchange に対してどのように作用するか</span><span class="sxs-lookup"><span data-stu-id="9091a-105">How a retention policy works with Exchange locations</span></span>

<span data-ttu-id="9091a-106">ユーザーのメール、予定表、その他のアイテムでは、アイテム保持ポリシーはメールボックス レベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="9091a-106">For a user's mail, calendar, and other items, a retention policy is applied at the level of a mailbox.</span></span>

<span data-ttu-id="9091a-107">パブリック フォルダーでは、アイテム保持ポリシーはメールボックス レベルではなく、フォルダー レベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="9091a-107">For a public folder, a retention policy is applied at the folder level, not the mailbox level.</span></span> 

<span data-ttu-id="9091a-108">メールボックスとパブリック フォルダーは、両方ともアイテムを保持するのに [回復可能なアイテム] フォルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="9091a-108">Both a mailbox and a public folder use the Recoverable Items folder to retain items.</span></span> <span data-ttu-id="9091a-109">電子情報開示のアクセス許可を割り当てられているユーザーだけが、他のユーザーの [回復可能なアイテム] フォルダーのアイテムを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9091a-109">Only people who have been assigned eDiscovery permissions can view items in another user's Recoverable Items folder.</span></span>
  
<span data-ttu-id="9091a-110">既定では、削除済みアイテム フォルダー以外のフォルダーからメッセージを削除すると、そのメッセージは削除済みアイテム フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="9091a-110">When a person deletes a message in a folder other than the Deleted Items folder, by default, the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="9091a-111">ユーザーが [削除済みアイテム] フォルダー内のアイテムを削除すると、メッセージは [回復可能なアイテム] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="9091a-111">When a person deletes an item in the Deleted Items folder, the message is moved to the Recoverable Items folder.</span></span> <span data-ttu-id="9091a-112">ただし、ユーザーは任意のフォルダー内のアイテムを論理的に削除 (Shift + Delete) できます。これにより、削除済みアイテム フォルダーがバイパスされ、アイテムが回復可能なアイテム フォルダーに直接移動します。</span><span class="sxs-lookup"><span data-stu-id="9091a-112">However, a user can soft-delete an item (SHIFT+DELETE) in any folder, which bypasses the Deleted Items folder and moves the item directly to the Recoverable Items folder.</span></span>
  
<span data-ttu-id="9091a-113">アイテム保持ポリシーを Exchange の場所に適用すると、タイマー ジョブが定期的に [回復可能なアイテム] フォルダー内のアイテムを評価します。</span><span class="sxs-lookup"><span data-stu-id="9091a-113">When you apply a retention policy to an Exchange location, a timer job periodically evaluates items in the Recoverable Items folder.</span></span> <span data-ttu-id="9091a-114">アイテムが少なくとも 1 つのアイテム保持ポリシーと一致しない場合、そのアイテムは [回復可能なアイテム] フォルダーから完全に削除されます (物理的な削除とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="9091a-114">If an item doesn't match the rules of at least one retention policy, the item is permanently deleted (also called hard deleted) from the Recoverable Items folder.</span></span>

<span data-ttu-id="9091a-115">タイマー ジョブの実行には最大 7 日かかる場合があり、Exchange の場所には少なくとも 10 MB が必要です。</span><span class="sxs-lookup"><span data-stu-id="9091a-115">The timer job can take up to 7 days to run and the Exchange location must contain at least 10 MB.</span></span>
  
<span data-ttu-id="9091a-116">ユーザーがメールボックスのアイテムのプロパティ (件名、本文、添付ファイル、送信者と受信者、メッセージの送受信日付など) を変更しようとすると、変更が確定される前に元のアイテムのコピーが [回復可能なアイテム] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="9091a-116">When a user attempts to change properties of a mailbox item—such as the subject, body, attachments, senders and recipients, or date sent or received for a message—a copy of the original item is saved to the Recoverable Items folder before the change is committed.</span></span> <span data-ttu-id="9091a-117">2 番目以降の変更ごとに、この操作が繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="9091a-117">This action happens for each subsequent change.</span></span> <span data-ttu-id="9091a-118">保持期間が終了すると、[回復可能なアイテム] フォルダー内のコピーは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="9091a-118">At the end of the retention period, copies in the Recoverable Items folder are permanently deleted.</span></span>

<span data-ttu-id="9091a-119">アイテム保持ポリシーがメールボックスまたはパブリック フォルダーに割り当てられた後のコンテンツのパスは、保持設定が保持および削除、保持のみ、あるいは削除のみのどれであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9091a-119">After a retention policy is assigned to a mailbox or public folder, the paths the content takes depend on whether the retention settings are to retain and delete, to retain only, or delete only.</span></span>

<span data-ttu-id="9091a-120">保持設定が保持および削除の場合</span><span class="sxs-lookup"><span data-stu-id="9091a-120">When the retention settings are to retain and delete:</span></span>

![メールおよびパブリック フォルダーの保持フローの図](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. <span data-ttu-id="9091a-122">**保持期間中、ユーザーがアイテムを変更または完全に削除した場合** (この操作は Shift キーと Delete キーを押すか、[削除済みアイテム] から削除して行います): アイテムは [回復可能なアイテム] フォルダーに移動 (編集する場合はコピー) されます。</span><span class="sxs-lookup"><span data-stu-id="9091a-122">**If the item is modified or permanently deleted** by the user (either SHIFT+DELETE or deleted from Deleted Items) during the retention period: The item is moved (or copied, in the case of edit) to the Recoverable Items folder.</span></span> <span data-ttu-id="9091a-123">ここで、タイマー ジョブが定期的に実行され、アイテム保持ポリシーの有効期間が過ぎたアイテムを特定します。このようなアイテムは、保持期間の最終日から 14 日以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="9091a-123">There, a timer job runs periodically and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="9091a-124">既定の設定は 14 日間ですが、最長 30 日間まで設定できます。</span><span class="sxs-lookup"><span data-stu-id="9091a-124">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span>
    
2. <span data-ttu-id="9091a-125">保存期間中に**アイテムが変更または削除されない場合**: メールボックス内のすべてのフォルダーで同じプロセスが定期的に実行され、保持期間が終了したアイテムを識別します。これらのアイテムは保持期間の終了後 14 日以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="9091a-125">**If the item is not modified or deleted** during the retention period: The same process runs periodically on all folders in the mailbox and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="9091a-126">既定の設定は 14 日間ですが、最長 30 日間まで設定できます。</span><span class="sxs-lookup"><span data-stu-id="9091a-126">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span> 

<span data-ttu-id="9091a-127">保持設定が保持のみ、または削除のみの場合、コンテンツ パスは保持か削除かで異なります。</span><span class="sxs-lookup"><span data-stu-id="9091a-127">When the retention settings are retain-only, or delete-only, the contents paths are variations of retain and delete:</span></span>

### <a name="content-paths-for-retain-only-retention-settings"></a><span data-ttu-id="9091a-128">保持設定が保持のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="9091a-128">Content paths for retain-only retention settings</span></span>

1. <span data-ttu-id="9091a-129">保持期間中に、**アイテムが変更または削除された場合**、元のアイテムのコピーが [回復可能なアイテム] フォルダーに作成され、保持期間の終了まで保持されます。保持期間が終了すると、[回復可能なアイテム] フォルダー内のコピーは、アイテムの有効期限が切れてから 14 日以内に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="9091a-129">**If the item is modified or deleted** during the retention period: A copy of the original item is created in the Recoverable Items folder and retained until the end of the retention period, when the copy in the Recoverable Items folder is permanently deleted within 14 days after the item expires.</span></span> 

2. <span data-ttu-id="9091a-130">保持期間中に**アイテムが変更または削除されてない場合**、保持期間の前後には何も起こりません。アイテムは、元の場所に残ります。</span><span class="sxs-lookup"><span data-stu-id="9091a-130">**If the item is not modified or deleted** during the retention period: Nothing happens before and after the retention period; the item remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-settings"></a><span data-ttu-id="9091a-131">保持設定が削除のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="9091a-131">Content paths for delete-only retention settings</span></span>

1. <span data-ttu-id="9091a-132">設定した期間中に**アイテムが削除されない場合**: アイテム保持ポリシーで構成された期間の最後に、アイテムは [回復可能なアイテム] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="9091a-132">**If the item is not deleted** during the configured period: At the end of the configured period in the retention policy, the item is moved to the Recoverable items folder.</span></span> 

2. <span data-ttu-id="9091a-133">設定した期間中に**アイテムが削除された場合**: アイテムはすぐに [回復可能なアイテム] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="9091a-133">**If the item is deleted** during the configured period: The item is immediately moved to the Recoverable items folder.</span></span> <span data-ttu-id="9091a-134">ユーザーが [回復可能なアイテム] フォルダーからアイテムを削除するかフォルダーを空にすると、そのアイテムは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="9091a-134">If a user deletes the item from there or empties the Recoverable items folder, the item is permanently deleted.</span></span> <span data-ttu-id="9091a-135">それ以外の場合、14 日が経過すると、アイテムは [回復可能なアイテム] フォルダーから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="9091a-135">Otherwise, the item is permanently deleted after being in the Recoverable items folder for 14 days.</span></span> 

## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a><span data-ttu-id="9091a-136">アイテム保持ポリシーから特定の種類の Exchange アイテムを除外する</span><span class="sxs-lookup"><span data-stu-id="9091a-136">Excluding specific types of Exchange items from a retention policy</span></span>

<span data-ttu-id="9091a-137">PowerShell を使用して、アイテム保持ポリシーから特定の種類の Exchange アイテムを除外することができます。</span><span class="sxs-lookup"><span data-stu-id="9091a-137">By using PowerShell, you can exclude specific types of Exchange items from a retention policy.</span></span> <span data-ttu-id="9091a-138">たとえば、メールボックスでボイスメール メッセージ、IM 会話、その他の Skype for Business Online のコンテンツを除外できます。</span><span class="sxs-lookup"><span data-stu-id="9091a-138">For example, you can exclude voicemail messages, IM conversations, and other Skype for Business Online content in mailboxes.</span></span> <span data-ttu-id="9091a-139">予定表、メモ、タスク アイテムを除外することもできます。</span><span class="sxs-lookup"><span data-stu-id="9091a-139">You can also exclude calendar, note, and task items.</span></span> <span data-ttu-id="9091a-140">この機能は、PowerShell を使用した場合にのみ使用できます。Microsoft 365 コンプライアンス センターのウィザードを使用してアイテム保持ポリシーを作成する場合は使用できません。</span><span class="sxs-lookup"><span data-stu-id="9091a-140">This capability is available only by using PowerShell; it's not available when you create a retention policy by using the wizard in the Microsoft 365 compliance center.</span></span>
  
<span data-ttu-id="9091a-141">アイテム保持ポリシーで Exchange アイテムに対して選択した種類を除外するには、`New-RetentionComplianceRule` および `Set-RetentionComplianceRule` コマンドレットで `ExcludedItemClasses` パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9091a-141">To exclude your selected types for Exchange items in a retention policy, use the  `ExcludedItemClasses` parameter with the  `New-RetentionComplianceRule` and  `Set-RetentionComplianceRule` cmdlets.</span></span>


### <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="9091a-142">ユーザーが組織を離れる場合</span><span class="sxs-lookup"><span data-stu-id="9091a-142">When a user leaves the organization</span></span> 

<span data-ttu-id="9091a-143">ユーザーが組織を離れるときに、ユーザーのメールボックスがアイテム保持ポリシーに含まれていると、ユーザーの Office 365 アカウントが削除されるときにメールボックスは非アクティブなメールボックスになります。</span><span class="sxs-lookup"><span data-stu-id="9091a-143">If a user leaves your organization and the user's mailbox is included in a retention policy, the mailbox becomes an inactive mailbox when the user's Office 365 account is deleted.</span></span> <span data-ttu-id="9091a-144">非アクティブなメールボックスのコンテンツは、メールボックスが非アクティブになる前に配置されたアイテム保持ポリシーがあれば、引き続きその適用対象となり、電子情報開示の検索が可能です。</span><span class="sxs-lookup"><span data-stu-id="9091a-144">The contents of an inactive mailbox are still subject to any retention policy that was placed on the mailbox before it was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="9091a-145">詳細については、「[Exchange Online の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9091a-145">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

## <a name="how-to-configure-a-retention-policy-for-exchange"></a><span data-ttu-id="9091a-146">Exchange のアイテム保持ポリシーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="9091a-146">How to configure a retention policy for Exchange</span></span>

<span data-ttu-id="9091a-147">「[アイテム保持ポリシーを作成して構成する](create-retention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9091a-147">See [Create and configure retention policies](create-retention-policies.md).</span></span>

<span data-ttu-id="9091a-148">ウィザードの [**場所の選択**] ページで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9091a-148">For the **Choose locations** page of the wizard, select one of the following options:</span></span>

- <span data-ttu-id="9091a-149">**Exchange メール、パブリック フォルダー、Office 365 グループ、OneDrive および SharePoint ドキュメントのコンテンツにのみポリシーを適用する**</span><span class="sxs-lookup"><span data-stu-id="9091a-149">**Apply policy only to content in Exchange email, public folders, Office 365 groups, OneDrive and SharePoint documents**</span></span>

- <span data-ttu-id="9091a-150">[**特定の場所を選択する**] > [**Exchange メール**] と [**Exchange パブリック フォルダー**]</span><span class="sxs-lookup"><span data-stu-id="9091a-150">**Let me choose specific locations** > **Exchange email** and **Exchange public folders**</span></span>

