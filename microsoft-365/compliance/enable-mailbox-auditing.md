---
title: メールボックスの監査を管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
ms.custom: seo-marvel-apr2020
description: メールボックス監査ログは、Microsoft 365 では既定で有効になっています (既定では既定のメールボックス監査またはメールボックス監査とも呼ばれています)。 つまり、メールボックスの所有者、代理人、および管理者が実行した特定の操作は、メールボックス監査ログに自動的に記録され、メールボックスで実行されたアクティビティを検索できます。
ms.openlocfilehash: 8b199f2fe63f0304e705f32bab8191a966e63fce
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682548"
---
# <a name="manage-mailbox-auditing"></a><span data-ttu-id="c2db6-104">メールボックスの監査を管理する</span><span class="sxs-lookup"><span data-stu-id="c2db6-104">Manage mailbox auditing</span></span>

<span data-ttu-id="c2db6-105">2019 年 1 月から、Microsoft は、すべての組織のメールボックス監査ログを既定で有効にしています。</span><span class="sxs-lookup"><span data-stu-id="c2db6-105">Starting in January 2019, Microsoft is turning on mailbox audit logging by default for all organizations.</span></span> <span data-ttu-id="c2db6-106">つまり、メールボックスの所有者、代理人、および管理者が実行する特定の操作は自動的にログに記録され、メールボックス監査ログでメールボックス監査レコードを検索すると、対応するメールボックス監査レコードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-106">This means that certain actions performed by mailbox owners, delegates, and admins are automatically logged, and the corresponding mailbox audit records will be available when you search for them in the mailbox audit log.</span></span> <span data-ttu-id="c2db6-107">メールボックス監査を既定で有効にする前に、組織内のすべてのユーザー メールボックスに対して手動で有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2db6-107">Before mailbox auditing was turned on by default, you had to manually enable it for every user mailbox in your organization.</span></span>

<span data-ttu-id="c2db6-108">メールボックス監査の既定の利点を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-108">Here are some benefits of mailbox auditing on by default:</span></span>

- <span data-ttu-id="c2db6-109">新しいメールボックスを作成すると、監査が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="c2db6-109">Auditing is automatically enabled when you create a new mailbox.</span></span> <span data-ttu-id="c2db6-110">新しいユーザーに対して手動で有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-110">You don't need to manually enable it for new users.</span></span>

- <span data-ttu-id="c2db6-111">監査されるメールボックスアクションを管理する必要はない。</span><span class="sxs-lookup"><span data-stu-id="c2db6-111">You don't need to manage the mailbox actions that are audited.</span></span> <span data-ttu-id="c2db6-112">既定では、定義済みのメールボックス操作のセットがログオンの種類 (管理者、代理人、所有者) ごとに監査されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-112">A predefined set of mailbox actions are audited by default for each logon type (Admin, Delegate, and Owner).</span></span>

- <span data-ttu-id="c2db6-113">Microsoft が新しいメールボックス アクションをリリースすると、既定で監査されるメールボックスアクションの一覧にアクションが自動的に追加される場合があります (適切なライセンスを持つユーザーが対象となります)。</span><span class="sxs-lookup"><span data-stu-id="c2db6-113">When Microsoft releases a new mailbox action, the action might be automatically added to the list of mailbox actions that are audited by default (subject to the user having the appropriate license).</span></span> <span data-ttu-id="c2db6-114">つまり、メールボックスに対する新しいアクションの追加を監視する必要がなされません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-114">This means you don't need to monitor add new actions on mailboxes.</span></span>

- <span data-ttu-id="c2db6-115">組織全体で一貫したメールボックス監査ポリシーを使用している (すべてのメールボックスに対して同じアクションを監査しているから)。</span><span class="sxs-lookup"><span data-stu-id="c2db6-115">You have a consistent mailbox auditing policy across your organization (because you're auditing the same actions for all mailboxes).</span></span>

> [!NOTE]
>* <span data-ttu-id="c2db6-116">既定でメールボックス監査がリリースされた場合に覚えておく必要がある重要な点は、メールボックス監査を管理するために何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-116">The important thing to remember about the release of mailbox auditing on by default is: you don't need to do anything to manage mailbox auditing.</span></span> <span data-ttu-id="c2db6-117">ただし、詳細については、既定の設定からメールボックス監査をカスタマイズするか、完全にオフにしてください。このトピックは役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-117">However, to learn more, customize mailbox auditing from the default settings, or turn it off altogether, this topic can help you.</span></span>
>- <span data-ttu-id="c2db6-118">既定では、E5 ユーザーのメールボックス監査イベントのみを、セキュリティ & コンプライアンス センターまたは Office 365 管理アクティビティ API 経由で監査ログ検索で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-118">By default, only mailbox audit events for E5 users are available in audit log searches in the Security & Compliance Center or via the Office 365 Management Activity API.</span></span> <span data-ttu-id="c2db6-119">詳細については、このトピックの「 [詳細」](#more-information) セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2db6-119">For more information, see the [More information](#more-information) section in this topic.</span></span>

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a><span data-ttu-id="c2db6-120">既定によるメールボックス監査の有効化がオンになっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="c2db6-120">Verify mailbox auditing on by default is turned on</span></span>

<span data-ttu-id="c2db6-121">組織でメールボックス監査が既定で有効になっていることを確認するには [、Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-121">To verify that mailbox auditing on by default is turned on for your organization, run the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

<span data-ttu-id="c2db6-122">値 **False** は、メールボックス監査が既定で組織に対して有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-122">The value **False** indicates that mailbox auditing on by default is enabled for the organization.</span></span> <span data-ttu-id="c2db6-123">これは、既定で組織の値が特定のメールボックスのメールボックス監査設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="c2db6-123">This on by default organizational value overrides the mailbox auditing setting on specific mailboxes.</span></span> <span data-ttu-id="c2db6-124">たとえば、メールボックスのメールボックス監査が無効になっている場合 (メールボックスの *AuditEnabled* プロパティが **False)、** 既定でメールボックス監査が組織に対して有効になっているため、メールボックスの既定のメールボックス操作は引き続き監査されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-124">For example, if mailbox auditing is disabled for a mailbox (the *AuditEnabled* property is **False** on the mailbox), the default mailbox actions will still be audited for the mailbox, because mailbox auditing on by default is enabled for the organization.</span></span>

<span data-ttu-id="c2db6-125">特定のメールボックスに対してメールボックス監査を無効に維持するには、メールボックス所有者およびメールボックスへのアクセスを委任された他のユーザーに対してメールボックス監査バイパスを構成します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-125">To keep mailbox auditing disabled for specific mailboxes, you configure mailbox auditing bypass for the mailbox owner and other users who have been delegated access to the mailbox.</span></span> <span data-ttu-id="c2db6-126">詳細については、このトピックの「 [メールボックス監査ログの](#bypass-mailbox-audit-logging) バイパス」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2db6-126">For more information, see the [Bypass mailbox audit logging](#bypass-mailbox-audit-logging) section in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="c2db6-127">組織でメールボックス監査が既定で有効になっている場合、影響を受けるメールボックスの *AuditEnabled* プロパティは False から **True** に変更 **されません**。</span><span class="sxs-lookup"><span data-stu-id="c2db6-127">When mailbox auditing on by default is turned on for the organization, the *AuditEnabled* property for affected mailboxes won't be changed from **False** to **True**.</span></span> <span data-ttu-id="c2db6-128">つまり、メールボックスの監査は既定でメールボックスの *AuditEnabled* プロパティを無視します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-128">In other words, mailbox auditing on by default ignores the *AuditEnabled* property on mailboxes.</span></span>

## <a name="supported-mailbox-types"></a><span data-ttu-id="c2db6-129">サポートされるメールボックスの種類</span><span class="sxs-lookup"><span data-stu-id="c2db6-129">Supported mailbox types</span></span>

<span data-ttu-id="c2db6-130">次の表に、既定でメールボックス監査で現在サポートされているメールボックスの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-130">The following table shows the mailbox types that are currently supported by mailbox auditing on by default:</span></span>

|<span data-ttu-id="c2db6-131">**メールボックスの種類**</span><span class="sxs-lookup"><span data-stu-id="c2db6-131">**Mailbox type**</span></span>|<span data-ttu-id="c2db6-132">**サポートされている**</span><span class="sxs-lookup"><span data-stu-id="c2db6-132">**Supported**</span></span>|<span data-ttu-id="c2db6-133">**サポートされていない**</span><span class="sxs-lookup"><span data-stu-id="c2db6-133">**Not supported**</span></span>|
|:---------|:---------:|:---------:|
|<span data-ttu-id="c2db6-134">ユーザー メールボックス</span><span class="sxs-lookup"><span data-stu-id="c2db6-134">User mailboxes</span></span>|![チェック マーク](../media/checkmark.png)||
|<span data-ttu-id="c2db6-136">共有メールボックス</span><span class="sxs-lookup"><span data-stu-id="c2db6-136">Shared mailboxes</span></span>|![チェック マーク](../media/checkmark.png)||
|<span data-ttu-id="c2db6-138">Microsoft 365 グループ メールボックス</span><span class="sxs-lookup"><span data-stu-id="c2db6-138">Microsoft 365 Group mailboxes</span></span>|![チェック マーク](../media/checkmark.png)||
|<span data-ttu-id="c2db6-140">リソース メールボックス</span><span class="sxs-lookup"><span data-stu-id="c2db6-140">Resource mailboxes</span></span>||![チェック マーク](../media/checkmark.png)|
|<span data-ttu-id="c2db6-142">パブリック フォルダー メールボックス</span><span class="sxs-lookup"><span data-stu-id="c2db6-142">Public folder mailboxes</span></span>||![チェック マーク](../media/checkmark.png)|

## <a name="logon-types-and-mailbox-actions"></a><span data-ttu-id="c2db6-144">ログオンの種類とメールボックスの操作</span><span class="sxs-lookup"><span data-stu-id="c2db6-144">Logon types and mailbox actions</span></span>

<span data-ttu-id="c2db6-145">ログオンの種類は、メールボックスで監査されたアクションを実行したユーザーを分類します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-145">Logon types classify the user that did the audited actions on the mailbox.</span></span> <span data-ttu-id="c2db6-146">次の一覧では、メールボックス監査ログで使用されるログオンの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-146">The following list describes the logon types that are used in mailbox audit logging:</span></span>

- <span data-ttu-id="c2db6-147">**所有者**: メールボックスの所有者 (メールボックスに関連付けられているアカウント)。</span><span class="sxs-lookup"><span data-stu-id="c2db6-147">**Owner**: The mailbox owner (the account that's associated with the mailbox).</span></span>

- <span data-ttu-id="c2db6-148">**デリゲート**:</span><span class="sxs-lookup"><span data-stu-id="c2db6-148">**Delegate**:</span></span>

  - <span data-ttu-id="c2db6-149">別のメールボックスに対する SendAs、SendOnBehalf、または FullAccess のアクセス許可が割り当てられているユーザー。</span><span class="sxs-lookup"><span data-stu-id="c2db6-149">A user who's been assigned the SendAs, SendOnBehalf, or FullAccess permission to another mailbox.</span></span>

  - <span data-ttu-id="c2db6-150">ユーザーのメールボックスに対する FullAccess アクセス許可が割り当てられている管理者。</span><span class="sxs-lookup"><span data-stu-id="c2db6-150">An admin who's been assigned the FullAccess permission to a user's mailbox.</span></span>

- <span data-ttu-id="c2db6-151">**管理者**:</span><span class="sxs-lookup"><span data-stu-id="c2db6-151">**Admin**:</span></span>

  - <span data-ttu-id="c2db6-152">メールボックスは、次の Microsoft 電子情報開示ツールのいずれかを使用して検索されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-152">The mailbox is searched with one of the following Microsoft eDiscovery tools:</span></span>

    - <span data-ttu-id="c2db6-153">コンプライアンス センターのコンテンツ検索。</span><span class="sxs-lookup"><span data-stu-id="c2db6-153">Content Search in the Compliance center.</span></span>

    - <span data-ttu-id="c2db6-154">コンプライアンス センターの電子情報開示または Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="c2db6-154">eDiscovery or Advanced eDiscovery in the Compliance center.</span></span>

    - <span data-ttu-id="c2db6-155">In-Place Exchange Online の電子情報開示。</span><span class="sxs-lookup"><span data-stu-id="c2db6-155">In-Place eDiscovery in Exchange Online.</span></span>

  - <span data-ttu-id="c2db6-156">メールボックスにアクセスするには、MAPI エディターのMicrosoft Exchange Server使用します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-156">The mailbox is accessed by using the Microsoft Exchange Server MAPI Editor.</span></span>

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a><span data-ttu-id="c2db6-157">ユーザー メールボックスと共有メールボックスのメールボックスアクション</span><span class="sxs-lookup"><span data-stu-id="c2db6-157">Mailbox actions for user mailboxes and shared mailboxes</span></span>

<span data-ttu-id="c2db6-158">次の表では、ユーザー メールボックスと共有メールボックスのメールボックス監査ログで使用できるメールボックスの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-158">The following table describes the mailbox actions that are available in mailbox audit logging for user mailboxes and shared mailboxes.</span></span>

- <span data-ttu-id="c2db6-159">チェック マーク (</span><span class="sxs-lookup"><span data-stu-id="c2db6-159">A check mark (</span></span> ![チェック マーク](../media/checkmark.png)<span data-ttu-id="c2db6-161">) は、ログオンの種類に対してメールボックスアクションをログに記録できる (すべての種類のログオンで使用可能なアクションではない) を示します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-161">) indicates the mailbox action can be logged for the logon type (not all actions are available for all logon types).</span></span>

- <span data-ttu-id="c2db6-162">チェック マークの後にアスタリスク ( ) が付いている場合は、ログオンの種類に対してメールボックスの操作が既定 <sup>\*</sup> で記録されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-162">An asterisk ( <sup>\*</sup> ) after the check mark indicates the mailbox action is logged by default for the logon type.</span></span>

- <span data-ttu-id="c2db6-163">メールボックスへのフル アクセスのアクセス許可を持つ管理者は代理人と見なされます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-163">Remember, an admin with Full Access permission to a mailbox is considered a delegate.</span></span>

|<span data-ttu-id="c2db6-164">**メールボックスの操作**</span><span class="sxs-lookup"><span data-stu-id="c2db6-164">**Mailbox action**</span></span>|<span data-ttu-id="c2db6-165">**説明**</span><span class="sxs-lookup"><span data-stu-id="c2db6-165">**Description**</span></span>|<span data-ttu-id="c2db6-166">**管理者**</span><span class="sxs-lookup"><span data-stu-id="c2db6-166">**Admin**</span></span>|<span data-ttu-id="c2db6-167">**代理人**</span><span class="sxs-lookup"><span data-stu-id="c2db6-167">**Delegate**</span></span>|<span data-ttu-id="c2db6-168">**所有者**</span><span class="sxs-lookup"><span data-stu-id="c2db6-168">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="c2db6-169">**AddFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="c2db6-169">**AddFolderPermissions**</span></span>|<span data-ttu-id="c2db6-170">**注**: この値はメールボックス アクションとして受け入れ可能ですが **、UpdateFolderPermissions** アクションには既に含まれており、個別に監査されません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-170">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="c2db6-171">つまり、この値は使用しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2db6-171">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="c2db6-172">**ApplyRecord**</span><span class="sxs-lookup"><span data-stu-id="c2db6-172">**ApplyRecord**</span></span>|<span data-ttu-id="c2db6-173">アイテムはレコードとしてラベル付けされます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-173">An item is labeled as a record.</span></span>|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|
|<span data-ttu-id="c2db6-177">**コピーする**</span><span class="sxs-lookup"><span data-stu-id="c2db6-177">**Copy**</span></span>|<span data-ttu-id="c2db6-178">メッセージが別のフォルダーにコピーされました。</span><span class="sxs-lookup"><span data-stu-id="c2db6-178">A message was copied to another folder.</span></span>|![チェック マーク](../media/checkmark.png)|||
|<span data-ttu-id="c2db6-180">**Create**</span><span class="sxs-lookup"><span data-stu-id="c2db6-180">**Create**</span></span>|<span data-ttu-id="c2db6-181">メールボックスの予定表、連絡先、メモ、またはタスク フォルダーにアイテムが作成されました (たとえば、新しい会議出席依頼が作成されます)。</span><span class="sxs-lookup"><span data-stu-id="c2db6-181">An item was created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox (for example, a new meeting request is created).</span></span> <span data-ttu-id="c2db6-182">メッセージの作成、送信、または受信は監査されません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-182">Creating, sending, or receiving a message isn't audited.</span></span> <span data-ttu-id="c2db6-183">また、メールボックス フォルダーの作成も監査されません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-183">Also, creating a mailbox folder is not audited.</span></span>|<span data-ttu-id="c2db6-184">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-184">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-185">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-185">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|![チェック マーク](../media/checkmark.png)|
|<span data-ttu-id="c2db6-187">**Default**</span><span class="sxs-lookup"><span data-stu-id="c2db6-187">**Default**</span></span>||![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|
|<span data-ttu-id="c2db6-191">**FolderBind**</span><span class="sxs-lookup"><span data-stu-id="c2db6-191">**FolderBind**</span></span>|<span data-ttu-id="c2db6-p114">メールボックス フォルダーがアクセスされました。この操作は、管理者または委任されたユーザーがメールボックスを開いたときにも記録されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-p114">A mailbox folder was accessed. This action is also logged when the admin or delegate opens the mailbox. </span></span><br/><br/> <span data-ttu-id="c2db6-194">**注**: 代理人によって実行されたフォルダー バインド操作の監査レコードは統合されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-194">**Note**: Audit records for folder bind actions performed by delegates are consolidated.</span></span> <span data-ttu-id="c2db6-195">24 時間以内に個々のフォルダー アクセスに対して 1 つの監査レコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-195">One audit record is generated for individual folder access within a 24-hour period.</span></span>|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|<span data-ttu-id="c2db6-198">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="c2db6-198">**HardDelete**</span></span>|<span data-ttu-id="c2db6-199">メッセージが [回復可能なアイテム] フォルダーから削除されました。</span><span class="sxs-lookup"><span data-stu-id="c2db6-199">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="c2db6-200">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-200">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-201">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-201">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-202">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-202">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="c2db6-203">**MailItemsAccessed**</span><span class="sxs-lookup"><span data-stu-id="c2db6-203">**MailItemsAccessed**</span></span>|<span data-ttu-id="c2db6-204">メール データには、メール プロトコルとクライアントがアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c2db6-204">Mail data is accessed by mail protocols and clients.</span></span> <span data-ttu-id="c2db6-205">この値は、E5 または E5 コンプライアンス アドオン サブスクリプション のユーザーにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-205">This value is only available for E5 or E5 Compliance add-on subscription users.</span></span> <span data-ttu-id="c2db6-206">詳細については、「調査のための [重要なイベントへのアクセス」を参照してください](advanced-audit.md#access-to-crucial-events-for-investigations)。</span><span class="sxs-lookup"><span data-stu-id="c2db6-206">For details, see [Access to crucial events for investigations](advanced-audit.md#access-to-crucial-events-for-investigations).</span></span>|<span data-ttu-id="c2db6-207">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-207">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-208">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-208">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-209">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-209">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="c2db6-210">**MailboxLogin**</span><span class="sxs-lookup"><span data-stu-id="c2db6-210">**MailboxLogin**</span></span>|<span data-ttu-id="c2db6-211">ユーザーが自分のメールボックスにサインインしました。</span><span class="sxs-lookup"><span data-stu-id="c2db6-211">The user signed into their mailbox.</span></span> |||![チェック マーク](../media/checkmark.png)|
|<span data-ttu-id="c2db6-213">**MessageBind**</span><span class="sxs-lookup"><span data-stu-id="c2db6-213">**MessageBind**</span></span>|<span data-ttu-id="c2db6-214">メッセージがプレビュー ウィンドウで表示されたか、管理者によって開かされました。 **注**: この値はメールボックスアクションとして受け入れ可能ですが、これらのアクションはログに記録されません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-214">A message was viewed in the preview pane or opened by an admin. **Note**: Although this value is accepted as a mailbox action, these actions are no longer logged.</span></span>|![チェック マーク](../media/checkmark.png)|||
|<span data-ttu-id="c2db6-216">**ModifyFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="c2db6-216">**ModifyFolderPermissions**</span></span>|<span data-ttu-id="c2db6-217">**注**: この値はメールボックス アクションとして受け入れ可能ですが **、UpdateFolderPermissions** アクションには既に含まれており、個別に監査されません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-217">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="c2db6-218">つまり、この値は使用しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2db6-218">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="c2db6-219">**移動する**</span><span class="sxs-lookup"><span data-stu-id="c2db6-219">**Move**</span></span>|<span data-ttu-id="c2db6-220">メッセージが別のフォルダーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="c2db6-220">A message was moved to another folder.</span></span>|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|
|<span data-ttu-id="c2db6-224">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="c2db6-224">**MoveToDeletedItems**</span></span>|<span data-ttu-id="c2db6-225">メッセージが削除され、[削除済みアイテム] フォルダーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="c2db6-225">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="c2db6-226">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-226">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-227">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-227">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-228">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-228">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="c2db6-229">**RecordDelete**</span><span class="sxs-lookup"><span data-stu-id="c2db6-229">**RecordDelete**</span></span>|<span data-ttu-id="c2db6-230">レコードとしてラベル付けされたアイテムが回復可能な削除によって削除された (回復可能なアイテム フォルダーに移動された)。</span><span class="sxs-lookup"><span data-stu-id="c2db6-230">An item that's labeled as a record was soft-deleted (moved to the Recoverable Items folder).</span></span> <span data-ttu-id="c2db6-231">レコードとしてラベル付けされたアイテムを完全に削除することはできません (回復可能なアイテム フォルダーから削除されます)。</span><span class="sxs-lookup"><span data-stu-id="c2db6-231">Items labeled as records can't be permanently deleted (purged from the Recoverable Items folder).</span></span>|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|
|<span data-ttu-id="c2db6-235">**RemoveFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="c2db6-235">**RemoveFolderPermissions**</span></span>|<span data-ttu-id="c2db6-236">**注**: この値はメールボックス アクションとして受け入れ可能ですが **、UpdateFolderPermissions** アクションには既に含まれており、個別に監査されません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-236">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="c2db6-237">つまり、この値は使用しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2db6-237">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="c2db6-238">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="c2db6-238">**SendAs**</span></span>|<span data-ttu-id="c2db6-p120">SendAs アクセス許可を使用してメッセージが送信されました (他のユーザーがこのメールボックスの所有者を装ってメッセージを送信しました)。</span><span class="sxs-lookup"><span data-stu-id="c2db6-p120">A message was sent using the SendAs permission. This means another user sent the message as though it came from the mailbox owner.</span></span>|<span data-ttu-id="c2db6-241">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-241">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-242">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-242">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="c2db6-243">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="c2db6-243">**SendOnBehalf**</span></span>|<span data-ttu-id="c2db6-p121">SendOnBehalf アクセス許可を使用してメッセージが送信されました (他のユーザーがこのメールボックスの所有者の代理人としてメッセージを送信しました)。この場合は、メッセージの名目上の送信者と実際の送信者が受信者に示されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-p121">A message was sent using the SendOnBehalf permission. This means another user sent the message on behalf of the mailbox owner. The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.</span></span>|<span data-ttu-id="c2db6-247">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-247">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-248">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-248">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="c2db6-249">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="c2db6-249">**SoftDelete**</span></span>|<span data-ttu-id="c2db6-p122">メッセージが完全に削除された、つまり [削除済みアイテム] フォルダーから削除されました。削除済み (回復可能) アイテムは、回復可能なアイテム フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-p122">A message was permanently deleted or deleted from the Deleted Items folder. Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="c2db6-252">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-252">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-253">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-253">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-254">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-254">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="c2db6-255">**更新**</span><span class="sxs-lookup"><span data-stu-id="c2db6-255">**Update**</span></span>|<span data-ttu-id="c2db6-256">メッセージまたはそのプロパティが変更されました。</span><span class="sxs-lookup"><span data-stu-id="c2db6-256">A message or its properties was changed.</span></span>|<span data-ttu-id="c2db6-257">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-257">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-258">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-258">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-259">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-259">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="c2db6-260">**UpdateCalendarDelegation**</span><span class="sxs-lookup"><span data-stu-id="c2db6-260">**UpdateCalendarDelegation**</span></span>|<span data-ttu-id="c2db6-p123">メールボックスに予定表の委任が割り当てられました。予定表の委任により、同じ組織の他のユーザーに、メールボックス所有者の予定表を管理する権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-p123">A calendar delegation was assigned to a mailbox. Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.</span></span>|<span data-ttu-id="c2db6-263">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-263">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||<span data-ttu-id="c2db6-264">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-264">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="c2db6-265">**UpdateComplianceTag**</span><span class="sxs-lookup"><span data-stu-id="c2db6-265">**UpdateComplianceTag**</span></span>|<span data-ttu-id="c2db6-266">別の保持ラベルがメール アイテムに適用されます (アイテムに割り当て可能な保持ラベルは 1 つのみです)。</span><span class="sxs-lookup"><span data-stu-id="c2db6-266">A different retention label is applied to a mail item (an item can only have one retention label assigned to it).</span></span>|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|
|<span data-ttu-id="c2db6-270">**UpdateFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="c2db6-270">**UpdateFolderPermissions**</span></span>|<span data-ttu-id="c2db6-271">フォルダーのアクセス許可が変更されました。</span><span class="sxs-lookup"><span data-stu-id="c2db6-271">A folder permission was changed.</span></span> <span data-ttu-id="c2db6-272">フォルダーのアクセス許可では、メールボックス内のフォルダーとそれらのフォルダーに格納されているメッセージにアクセスできる組織内のユーザーを制限します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-272">Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.</span></span>|<span data-ttu-id="c2db6-273">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-273">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-274">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-274">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-275">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-275">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="c2db6-276">**UpdateInboxRules**</span><span class="sxs-lookup"><span data-stu-id="c2db6-276">**UpdateInboxRules**</span></span>|<span data-ttu-id="c2db6-277">受信トレイ ルールが追加、削除、または変更されました。</span><span class="sxs-lookup"><span data-stu-id="c2db6-277">An inbox rule was added, removed, or changed.</span></span> <span data-ttu-id="c2db6-278">受信トレイ ルールは、指定した条件に基づいてユーザーの受信トレイ内のメッセージを処理し、指定したフォルダーへのメッセージの移動やメッセージの削除など、ルールの条件が満たされた場合にアクションを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-278">Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.</span></span>|<span data-ttu-id="c2db6-279">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-279">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-280">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-280">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-281">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-281">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|

> [!IMPORTANT]
> <span data-ttu-id="c2db6-282">組織で既定でメールボックス監査を有効にする前に、ログオンの種類を監査するようにメールボックスの操作をカスタマイズした場合、カスタマイズされた設定はメールボックスに保持され、このセクションで説明するように既定のメールボックス操作によって上書きされることはありません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-282">If you customized the mailbox actions to audit for any logon type *before* mailbox auditing on by default was enabled in your organization, the customized settings are preserved on the mailbox and aren't overwritten by the default mailbox actions as described in this section.</span></span> <span data-ttu-id="c2db6-283">監査メールボックスの操作を既定値に戻すには (いつでも実行できます)、このトピックの「既定[](#restore-the-default-mailbox-actions)のメールボックス操作を復元する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2db6-283">To revert the audit mailbox actions to their default values (which you can do at any time), see the [Restore the default mailbox actions](#restore-the-default-mailbox-actions) section later in this topic.</span></span>

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a><span data-ttu-id="c2db6-284">Microsoft 365 グループ メールボックスのメールボックスアクション</span><span class="sxs-lookup"><span data-stu-id="c2db6-284">Mailbox actions for Microsoft 365 Group mailboxes</span></span>

<span data-ttu-id="c2db6-285">メールボックス監査は既定で Microsoft 365 グループメールボックスにメールボックス監査ログを表示しますが、記録される項目をカスタマイズすることはできません (ログオンの種類に対してログに記録されるメールボックス操作を追加または削除することはできません)。</span><span class="sxs-lookup"><span data-stu-id="c2db6-285">Mailbox auditing on by default brings mailbox audit logging to Microsoft 365 Group mailboxes, but you can't customize what's being logged (you can't add or remove mailbox actions that are logged for any logon type).</span></span>

<span data-ttu-id="c2db6-286">次の表では、ログオンの種類ごとに Microsoft 365 グループ のメールボックスに既定で記録されるメールボックスの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-286">The following table describes the mailbox actions that are logged by default on Microsoft 365 Group mailboxes for each logon type.</span></span>

<span data-ttu-id="c2db6-287">Microsoft 365 グループ メールボックスへのフル アクセス許可を持つ管理者は代理人と見なされます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-287">Remember, an admin with Full Access permission to an Microsoft 365 Group mailbox is considered a delegate.</span></span>

|<span data-ttu-id="c2db6-288">**メールボックスの操作**</span><span class="sxs-lookup"><span data-stu-id="c2db6-288">**Mailbox action**</span></span>|<span data-ttu-id="c2db6-289">**説明**</span><span class="sxs-lookup"><span data-stu-id="c2db6-289">**Description**</span></span>|<span data-ttu-id="c2db6-290">**管理者**</span><span class="sxs-lookup"><span data-stu-id="c2db6-290">**Admin**</span></span>|<span data-ttu-id="c2db6-291">**代理人**</span><span class="sxs-lookup"><span data-stu-id="c2db6-291">**Delegate**</span></span>|<span data-ttu-id="c2db6-292">**所有者**</span><span class="sxs-lookup"><span data-stu-id="c2db6-292">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="c2db6-293">**Create**</span><span class="sxs-lookup"><span data-stu-id="c2db6-293">**Create**</span></span>|<span data-ttu-id="c2db6-294">予定表アイテムの作成。</span><span class="sxs-lookup"><span data-stu-id="c2db6-294">Creation of a calendar Item.</span></span> <span data-ttu-id="c2db6-295">メッセージの作成、送信、または受信は監査されません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-295">Creating, sending, or receiving a message isn't audited.</span></span>|<span data-ttu-id="c2db6-296">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-296">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-297">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-297">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="c2db6-298">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="c2db6-298">**HardDelete**</span></span>|<span data-ttu-id="c2db6-299">メッセージが [回復可能なアイテム] フォルダーから削除されました。</span><span class="sxs-lookup"><span data-stu-id="c2db6-299">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="c2db6-300">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-300">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-301">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-301">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-302">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-302">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="c2db6-303">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="c2db6-303">**MoveToDeletedItems**</span></span>|<span data-ttu-id="c2db6-304">メッセージが削除され、[削除済みアイテム] フォルダーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="c2db6-304">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="c2db6-305">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-305">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-306">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-306">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-307">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-307">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="c2db6-308">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="c2db6-308">**SendAs**</span></span>|<span data-ttu-id="c2db6-309">SendAs アクセス許可を使用してメッセージが送信されました。</span><span class="sxs-lookup"><span data-stu-id="c2db6-309">A message was sent using the SendAs permission.</span></span>|<span data-ttu-id="c2db6-310">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-310">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-311">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-311">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="c2db6-312">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="c2db6-312">**SendOnBehalf**</span></span>|<span data-ttu-id="c2db6-313">SendOnBehalf アクセス許可を使用してメッセージが送信されました。</span><span class="sxs-lookup"><span data-stu-id="c2db6-313">A message was sent using the SendOnBehalf permission.</span></span> |<span data-ttu-id="c2db6-314">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-314">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-315">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-315">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="c2db6-316">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="c2db6-316">**SoftDelete**</span></span>|<span data-ttu-id="c2db6-p128">メッセージが完全に削除された、つまり [削除済みアイテム] フォルダーから削除されました。削除済み (回復可能) アイテムは、回復可能なアイテム フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-p128">A message was permanently deleted or deleted from the Deleted Items folder. Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="c2db6-319">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-319">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-320">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-320">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-321">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-321">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="c2db6-322">**更新**</span><span class="sxs-lookup"><span data-stu-id="c2db6-322">**Update**</span></span>|<span data-ttu-id="c2db6-323">メッセージまたはそのプロパティが変更されました。</span><span class="sxs-lookup"><span data-stu-id="c2db6-323">A message or its properties was changed.</span></span>|<span data-ttu-id="c2db6-324">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-324">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-325">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-325">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="c2db6-326">![チェック マーク](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c2db6-326">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a><span data-ttu-id="c2db6-327">ログオンの種類ごとに既定のメールボックスアクションがログに記録されるのを確認する</span><span class="sxs-lookup"><span data-stu-id="c2db6-327">Verify that default mailbox actions are being logged for each logon type</span></span>

<span data-ttu-id="c2db6-328">既定では、メールボックス監査は新しい *DefaultAuditSet* プロパティをすべてのメールボックスに追加します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-328">Mailbox auditing on by defaults adds a new *DefaultAuditSet* property to all mailboxes.</span></span> <span data-ttu-id="c2db6-329">このプロパティの値は、(Microsoft によって管理される) 既定のメールボックスアクションがメールボックスで監査されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-329">The value of this property indicates whether the default mailbox actions (managed by Microsoft) are being audited on the mailbox.</span></span>

<span data-ttu-id="c2db6-330">ユーザー メールボックスまたは共有メールボックスの値を表示するには、メールボックスの名前、エイリアス、電子メール アドレス、またはユーザー プリンシパル名 (ユーザー名) に置き換え、Exchange Online PowerShell で次のコマンドを実行します \<MailboxIdentity\> 。</span><span class="sxs-lookup"><span data-stu-id="c2db6-330">To display the value on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox and run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

<span data-ttu-id="c2db6-331">Microsoft 365 グループ メールボックスの値を表示するには、共有メールボックスの名前、エイリアス、または電子メール アドレスに置き換え、Exchange Online PowerShell で次のコマンドを \<MailboxIdentity\> 実行します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-331">To display the value on Microsoft 365 group mailboxes, replace \<MailboxIdentity\> with the name, alias, or email address of the shared mailbox and run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

<span data-ttu-id="c2db6-332">値は `Admin, Delegate, Owner` 次を示します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-332">The value `Admin, Delegate, Owner` indicates:</span></span>

- <span data-ttu-id="c2db6-333">3 種類すべてのログオンに対する既定のメールボックスアクションが監査されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-333">The default mailbox actions for all three logon types are being audited.</span></span> <span data-ttu-id="c2db6-334">これは、Microsoft 365 グループ メールボックスに表示される唯一の値です。</span><span class="sxs-lookup"><span data-stu-id="c2db6-334">This is the only value you'll see on Microsoft 365 Group mailboxes.</span></span>

- <span data-ttu-id="c2db6-335">管理者が *、ユーザー* メールボックスまたは共有メールボックスのログオンの種類に対する監査メールボックスアクションを変更していない。</span><span class="sxs-lookup"><span data-stu-id="c2db6-335">An admin *has not* changed the audited mailbox actions for any logon type on a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="c2db6-336">これは、既定でメールボックス監査が組織で有効になった後の既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="c2db6-336">Note this is the default state after mailbox auditing on by default is initially turned on in your organization.</span></span>

<span data-ttu-id="c2db6-337">管理者がログオンの種類 **(Set-Mailbox** コマンドレットで *AuditAdmin、AuditDelegate、* または *AuditOwner* パラメーターを使用して) 監査されるメールボックスアクションを変更した場合、プロパティ値は異なります。</span><span class="sxs-lookup"><span data-stu-id="c2db6-337">If an admin has ever changed the mailbox actions that are audited for a logon type (by using the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet), the property value will be different.</span></span>

<span data-ttu-id="c2db6-338">たとえば、ユーザー メールボックス `Owner` または共有メールボックスの *DefaultAuditSet* プロパティの値は、次の値を示します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-338">For example, the value `Owner` for the *DefaultAuditSet* property on a user mailbox or shared mailbox indicates:</span></span>

- <span data-ttu-id="c2db6-339">メールボックス所有者の既定のメールボックスアクションは監査中です。</span><span class="sxs-lookup"><span data-stu-id="c2db6-339">The default mailbox actions for the mailbox owner are being audited.</span></span>

- <span data-ttu-id="c2db6-340">監査されるメールボックスの操作とログオン `Delegate` の種類 `Admin` は、既定のアクションから変更されています。</span><span class="sxs-lookup"><span data-stu-id="c2db6-340">The audited mailbox actions for the `Delegate` and `Admin` logon types have been changed from the default actions.</span></span>

<span data-ttu-id="c2db6-341">*DefaultAuditSet* プロパティの空白値は、ユーザー メールボックスまたは共有メールボックスで、3 種類すべてのログオンのメールボックスアクションが変更されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-341">A blank value for the *DefaultAuditSet* property indicates the mailbox actions for all three logon types have been changed on the user mailbox or a shared mailbox.</span></span>

<span data-ttu-id="c2db6-342">詳細については、このトピックの「既定で記録されるメールボックス操作の [変更](#change-or-restore-mailbox-actions-logged-by-default) または復元」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2db6-342">For more information, see the [Change or restore mailbox actions logged by default](#change-or-restore-mailbox-actions-logged-by-default) section in this topic</span></span>

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a><span data-ttu-id="c2db6-343">ログオンしているメールボックスの操作を表示する</span><span class="sxs-lookup"><span data-stu-id="c2db6-343">Display the mailbox actions that are being logged on mailboxes</span></span>

<span data-ttu-id="c2db6-344">ユーザー メールボックスまたは共有メールボックスで現在ログオンしているメールボックスアクションを表示するには、メールボックスの名前、エイリアス、電子メール アドレス、またはユーザー プリンシパル名 (ユーザー名) に置き換え、Exchange Online PowerShell で次のコマンドを 1 つ以上実行します。 \<MailboxIdentity\></span><span class="sxs-lookup"><span data-stu-id="c2db6-344">To see the mailbox actions that are currently being logged on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox, and run one or more of the following commands in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="c2db6-345">Microsoft 365 グループ メールボックス用の次の Get-Mailbox コマンドにスイッチを追加することもできますが、返される値は `-GroupMailbox` 見なされません。 </span><span class="sxs-lookup"><span data-stu-id="c2db6-345">Although you can add the `-GroupMailbox` switch to the following **Get-Mailbox** commands for Microsoft 365 Group mailboxes, don't believe the values that are returned.</span></span> <span data-ttu-id="c2db6-346">Microsoft 365 グループ メールボックスに対して監査される既定の静的メールボックスアクションについては、このトピックの [「Microsoft 365 グループ](#mailbox-actions-for-microsoft-365-group-mailboxes) メールボックスのメールボックスアクション」セクションで説明しました。</span><span class="sxs-lookup"><span data-stu-id="c2db6-346">The default and static mailbox actions that are audited for Microsoft 365 Group mailboxes are described in the [Mailbox actions for Microsoft 365 Group mailboxes](#mailbox-actions-for-microsoft-365-group-mailboxes) section earlier in this topic.</span></span>

#### <a name="owner-actions"></a><span data-ttu-id="c2db6-347">所有者の操作</span><span class="sxs-lookup"><span data-stu-id="c2db6-347">Owner actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a><span data-ttu-id="c2db6-348">委任アクション</span><span class="sxs-lookup"><span data-stu-id="c2db6-348">Delegate actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a><span data-ttu-id="c2db6-349">管理者アクション</span><span class="sxs-lookup"><span data-stu-id="c2db6-349">Admin actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a><span data-ttu-id="c2db6-350">既定でログに記録されるメールボックスの操作を変更または復元する</span><span class="sxs-lookup"><span data-stu-id="c2db6-350">Change or restore mailbox actions logged by default</span></span>

<span data-ttu-id="c2db6-351">前に説明したように、メールボックス監査を既定で有効にする主な利点の 1 つは、監査されるメールボックスの操作を管理する必要がなさいという利点です。</span><span class="sxs-lookup"><span data-stu-id="c2db6-351">As previously explained, one of the key benefits of having mailbox auditing on by default is: you don't need to manage the mailboxes actions that are audited.</span></span> <span data-ttu-id="c2db6-352">Microsoft がこれを行い、新しいメールボックス アクションがリリースされると、既定で監査される新しいメールボックス アクションが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-352">Microsoft does this for you and we'll automatically add new mailbox actions to be audited by default as they're released.</span></span>

<span data-ttu-id="c2db6-353">ただし、組織では、ユーザー メールボックスと共有メールボックスに対して異なるメールボックス操作のセットを監査する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="c2db6-353">However, your organization might be required to audit a different set of mailbox actions for user mailboxes and shared mailboxes.</span></span> <span data-ttu-id="c2db6-354">このセクションの手順では、ログオンの種類ごとに監査されるメールボックスアクションを変更する方法と、Microsoft が管理する既定のアクションに戻す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-354">The procedures in this section show you how to change the mailbox actions that are audited for each logon type, and how to revert back to the Microsoft-managed default actions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2db6-355">次の手順を使用して、ユーザー メールボックスまたは共有メールボックスにログオンしているメールボックス操作をカスタマイズした場合、Microsoft によってリリースされた新しい既定のメールボックスアクションは、それらのメールボックスに対して自動的に監査されません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-355">If you use the following procedures to customize the mailbox actions that are logged on user mailboxes or shared mailboxes, any new default mailbox actions released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="c2db6-356">新しいメールボックス アクションをカスタマイズしたアクションの一覧に手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2db6-356">You'll need to manually add any new mailbox actions to your customized list of actions.</span></span>

### <a name="change-the-mailbox-actions-to-audit"></a><span data-ttu-id="c2db6-357">監査するメールボックスアクションを変更する</span><span class="sxs-lookup"><span data-stu-id="c2db6-357">Change the mailbox actions to audit</span></span>

<span data-ttu-id="c2db6-358">**Set-Mailbox** コマンドレットで *AuditAdmin、AuditDelegate、* または *AuditOwner* パラメーターを使用して、ユーザー メールボックスと共有メールボックスに対して監査されるメールボックスアクションを変更できます (Microsoft 365 グループ メールボックスの監査アクションはカスタマイズできません)。 </span><span class="sxs-lookup"><span data-stu-id="c2db6-358">You can use the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet to change the mailbox actions that are audited for user mailboxes and shared mailboxes (audited actions for Microsoft 365 group mailboxes can't be customized).</span></span>

<span data-ttu-id="c2db6-359">次の 2 つの異なる方法を使用して、メールボックスの操作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-359">You can use two different methods to specify the mailbox actions:</span></span>

- <span data-ttu-id="c2db6-360">*次の* 構文を使用して、既存のメールボックスアクションを置換 (上書き) します `action1,action2,...actionN` 。</span><span class="sxs-lookup"><span data-stu-id="c2db6-360">*Replace* (overwrite) the existing mailbox actions by using this syntax: `action1,action2,...actionN`.</span></span>

- <span data-ttu-id="c2db6-361">*次の構文を使用* して、他の既存の値に影響を与えることなく、メールボックスの操作を追加または `@{Add="action1","action2",..."actionN"}` 削除します `@{Remove="action1","action2",..."actionN"}` 。</span><span class="sxs-lookup"><span data-stu-id="c2db6-361">*Add or remove* mailbox actions without affecting other existing values by using this syntax: `@{Add="action1","action2",..."actionN"}` or `@{Remove="action1","action2",..."actionN"}`.</span></span>

<span data-ttu-id="c2db6-362">この例では、SoftDelete と HardDelete を使用して既定のアクションを上書きして、"Gabriela Laureano" という名前のメールボックスの管理メールボックスアクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-362">This example changes the admin mailbox actions for the mailbox named "Gabriela Laureano" by overwriting the default actions with SoftDelete and HardDelete.</span></span>

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

<span data-ttu-id="c2db6-363">この例では、MailboxLogin 所有者のアクションをメールボックス フォルダーにlaura@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="c2db6-363">This example adds the MailboxLogin owner action to the mailbox laura@contoso.onmicrosoft.com.</span></span>

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

<span data-ttu-id="c2db6-364">この例では、チーム ディスカッション メールボックスの MoveToDeletedItems 委任アクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-364">This example removes the MoveToDeletedItems delegate action for the Team Discussion mailbox.</span></span>

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

<span data-ttu-id="c2db6-365">使用する方法に関係なく、ユーザー メールボックスまたは共有メールボックスで監査メールボックスアクションをカスタマイズすると、次の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-365">Regardless of the method you use, customizing the audited mailbox actions on user mailboxes or shared mailboxes has the following results:</span></span>

- <span data-ttu-id="c2db6-366">カスタマイズしたログオンの種類では、監査されるメールボックスアクションは Microsoft によって管理されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c2db6-366">For the logon type that you customized, the audited mailbox actions are no longer managed by Microsoft.</span></span>

- <span data-ttu-id="c2db6-367">カスタマイズしたログオンの種類は、前に説明したように、メールボックスの *DefaultAuditSet* プロパティ値 [に表示されなくなりました](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)。</span><span class="sxs-lookup"><span data-stu-id="c2db6-367">The logon type that you customized is no longer displayed in the *DefaultAuditSet* property value for the mailbox as [previously described](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).</span></span>

### <a name="restore-the-default-mailbox-actions"></a><span data-ttu-id="c2db6-368">既定のメールボックス操作を復元する</span><span class="sxs-lookup"><span data-stu-id="c2db6-368">Restore the default mailbox actions</span></span>

<span data-ttu-id="c2db6-369">ユーザー メールボックスまたは共有メールボックスで監査されるメールボックスアクションをカスタマイズした場合は、次の構文を使用して、1 つ以上のログオンの種類の既定のメールボックスアクションを復元できます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-369">If you customized the mailbox actions that are audited on a user mailbox or a shared mailbox, you can restore the default mailbox actions for one or all logon types by using this syntax:</span></span>

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

<span data-ttu-id="c2db6-370">複数の *DefaultAuditSet 値をコンマ* で区切って指定できます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-370">You can specify multiple *DefaultAuditSet* values separated by commas</span></span>

<span data-ttu-id="c2db6-371">**注**: 次の手順は、Microsoft 365 グループ メールボックスには適用されません (ここで説明する既定の操作に限定 [されます](#mailbox-actions-for-microsoft-365-group-mailboxes))。</span><span class="sxs-lookup"><span data-stu-id="c2db6-371">**Note**: The following procedures don't apply to Microsoft 365 Group mailboxes (they're limited to the default actions as described [here](#mailbox-actions-for-microsoft-365-group-mailboxes)).</span></span>

<span data-ttu-id="c2db6-372">この例では、メールボックス サーバー上のすべてのログオンの種類に対する既定の監査メールボックスアクションをmark@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="c2db6-372">This example restores the default audited mailbox actions for all logon types on the mailbox mark@contoso.onmicrosoft.com.</span></span>

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

<span data-ttu-id="c2db6-373">この例では、メールボックス chris@contoso.onmicrosoft.com の Admin ログオンの種類に対する既定の監査メールボックス アクションを復元しますが、委任ログオンの種類と所有者ログオンの種類に合わせてカスタマイズされた監査メールボックスアクションは残します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-373">This example restores the default audited mailbox actions for the Admin logon type on the mailbox chris@contoso.onmicrosoft.com, but leaves the customized audited mailbox actions for the Delegate and Owner logon types.</span></span>

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

<span data-ttu-id="c2db6-374">ログオンの種類に対する既定の監査メールボックス操作を復元すると、次の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-374">Restoring he default audited mailbox actions for a logon type has the following results:</span></span>

- <span data-ttu-id="c2db6-375">メールボックスアクションの現在のリストは、ログオンの種類の既定のメールボックスアクションに置き換えられる。</span><span class="sxs-lookup"><span data-stu-id="c2db6-375">The current list of mailbox actions is replaced with the default mailbox actions for the logon type.</span></span>

- <span data-ttu-id="c2db6-376">Microsoft によってリリースされた新しいメールボックスアクションは、ログオンの種類の監査済みアクションの一覧に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-376">Any new mailbox actions that are released by Microsoft are automatically added to the list of audited actions for the logon type.</span></span>

- <span data-ttu-id="c2db6-377">メールボックス *の DefaultAuditSet* プロパティの値が更新され、復元されたログオンの種類が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-377">The *DefaultAuditSet* property value for the mailbox is updated to include the restored logon type.</span></span>

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a><span data-ttu-id="c2db6-378">組織のメールボックス監査を既定で有効にする</span><span class="sxs-lookup"><span data-stu-id="c2db6-378">Turn off mailbox auditing on by default for your organization</span></span>

<span data-ttu-id="c2db6-379">Exchange Online PowerShell で次のコマンドを実行すると、組織全体のメールボックス監査を既定で無効にできます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-379">You can turn off mailbox auditing on by default for your entire organization by running the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

<span data-ttu-id="c2db6-380">メールボックスの監査を既定で無効にした場合、次の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-380">Turning off mailbox auditing on by default has the following results:</span></span>

- <span data-ttu-id="c2db6-381">組織のメールボックス監査は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="c2db6-381">Mailbox auditing is disabled for your organization.</span></span>

- <span data-ttu-id="c2db6-382">既定でメールボックス監査を無効にした時間から、メールボックスで監査が有効になっている場合でも、メールボックスの操作は監査されません (メールボックスの *AuditEnabled* プロパティは **True** です)。</span><span class="sxs-lookup"><span data-stu-id="c2db6-382">From the time you disabled mailbox auditing on by default, no mailbox actions are audited, even if auditing is enabled on a mailbox (the *AuditEnabled* property on the mailbox is **True**).</span></span>

- <span data-ttu-id="c2db6-383">新しいメールボックスに対してメールボックス監査が有効になっていない場合、新規または既存のメールボックスの *AuditEnabled* プロパティを **True** に設定しても無視されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-383">Mailbox auditing is not enabled for new mailboxes and setting the *AuditEnabled* property on a new or existing mailbox to **True** will be ignored.</span></span>

- <span data-ttu-id="c2db6-384">メールボックス監査バイパスの関連付け設定 **(Set-MailboxAuditBypassAssociation** コマンドレットを使用して構成) は無視されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-384">Any mailbox audit bypass association settings (configured by using the **Set-MailboxAuditBypassAssociation** cmdlet) are ignored.</span></span>

- <span data-ttu-id="c2db6-385">既存のメールボックス監査レコードは、レコードの監査ログの有効期限が切れるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-385">Existing mailbox audit records are retained until the audit log age limit for the record expires.</span></span>

### <a name="turn-on-mailbox-auditing-on-by-default"></a><span data-ttu-id="c2db6-386">既定でメールボックス監査を有効にする</span><span class="sxs-lookup"><span data-stu-id="c2db6-386">Turn on mailbox auditing on by default</span></span>

<span data-ttu-id="c2db6-387">組織のメールボックス監査を有効に戻すには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-387">To turn mailbox auditing back on for your organization, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a><span data-ttu-id="c2db6-388">メールボックス監査ログをバイパスする</span><span class="sxs-lookup"><span data-stu-id="c2db6-388">Bypass mailbox audit logging</span></span>

<span data-ttu-id="c2db6-389">現時点では、既定によるメールボックス監査の有効化が組織でオンになっている場合は、特定のメールボックスでメールボックス監査を無効にできません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-389">Currently, you can't disable mailbox auditing for specific mailboxes when mailbox auditing on by default is turned on in your organization.</span></span> <span data-ttu-id="c2db6-390">たとえば *、AuditEnabled メールボックス プロパティを* **False** に設定しても無視されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-390">For example, setting the *AuditEnabled* mailbox property to **False** is ignored.</span></span>

<span data-ttu-id="c2db6-391">ただし、Exchange Online PowerShell で **Set-MailboxAuditBypassAssociation** コマンドレットを引き続き使用して、アクションが発生した場所に関係なく、指定したユーザーによるすべてのメールボックス操作がログに記録されるのを防ぐことが可能です。</span><span class="sxs-lookup"><span data-stu-id="c2db6-391">However, you can still use the **Set-MailboxAuditBypassAssociation** cmdlet in Exchange Online PowerShell to prevent *any and all* mailbox actions by the specified users from being logged, regardless where the actions occur.</span></span> <span data-ttu-id="c2db6-392">例:</span><span class="sxs-lookup"><span data-stu-id="c2db6-392">For example:</span></span>

- <span data-ttu-id="c2db6-393">バイパスされたユーザーによって実行されたメールボックス所有者の操作はログに記録されません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-393">Mailbox owner actions performed by the bypassed users aren't logged.</span></span>

- <span data-ttu-id="c2db6-394">他のユーザーのメールボックス (共有メールボックスを含む) でバイパスされたユーザーによって実行された委任アクションはログに記録されません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-394">Delegate actions performed by the bypassed users on other users' mailboxes (including shared mailboxes) aren't logged.</span></span>

- <span data-ttu-id="c2db6-395">バイパスされたユーザーによって実行された管理者の操作はログに記録されません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-395">Admin actions performed by the bypassed users aren't logged.</span></span>

<span data-ttu-id="c2db6-396">特定のユーザーのメールボックス監査ログをバイパスするには、ユーザーの名前、電子メール アドレス、エイリアス、またはユーザー プリンシパル名 (ユーザー名) に置き換え、次のコマンド \<MailboxIdentity\> を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-396">To bypass mailbox audit logging for a specific user, replace \<MailboxIdentity\> with the name, email address, alias, or user principal name (username) of the user and run the following command:</span></span>

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

<span data-ttu-id="c2db6-397">特定のユーザーについて監査がバイパスされていることを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-397">To verify that auditing is bypassed for the specified user, run the following command:</span></span>

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

<span data-ttu-id="c2db6-398">値 **True** は、メールボックス監査ログがユーザーに対してバイパスされるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-398">The value **True** indicates that mailbox audit logging is bypassed for the user.</span></span>

## <a name="more-information"></a><span data-ttu-id="c2db6-399">詳細</span><span class="sxs-lookup"><span data-stu-id="c2db6-399">More information</span></span>

- <span data-ttu-id="c2db6-400">メールボックス監査ログは、すべての組織で既定で有効になっていますが、E5 ライセンスを持つユーザーだけが、既定でセキュリティ [&](search-the-audit-log-in-security-and-compliance.md) コンプライアンス センターまたは [Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)管理アクティビティ API を介して監査ログ検索でメールボックス監査ログ イベントを **返** します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-400">Although mailbox audit logging on by default is enabled for all organizations, only users with E5 licenses will return mailbox audit log events in [audit log searches in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md) or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) **by default**.</span></span>

  <span data-ttu-id="c2db6-401">E5 ライセンスのないユーザーのメールボックス監査ログ エントリを取得するには、次の方法があります。</span><span class="sxs-lookup"><span data-stu-id="c2db6-401">To retrieve mailbox audit log entries for users without E5 licenses, you can:</span></span>

  - <span data-ttu-id="c2db6-402">個々のメールボックスでメールボックス監査を手動で有効にします (コマンドを実行します `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` )。</span><span class="sxs-lookup"><span data-stu-id="c2db6-402">Manually enable mailbox auditing on individual mailboxes (run the command, `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true`).</span></span> <span data-ttu-id="c2db6-403">この操作を行 &った後は、セキュリティ/コンプライアンス センターまたは Office 365 管理アクティビティ API を介して、監査ログ検索を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-403">After you do this, you can use audit log searches in the Security & Compliance Center or via the Office 365 Management Activity API.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="c2db6-404">メールボックスの監査がメールボックスで既に有効になっていると思うが、検索で結果が返されない場合は _、AuditEnabled_ パラメーターの値を次の値に変更してから、その値に戻 `$false` ります `$true` 。</span><span class="sxs-lookup"><span data-stu-id="c2db6-404">If mailbox auditing already appears to be enabled on the mailbox, but your searches return no results, change the value of the _AuditEnabled_ parameter to `$false` and then back to `$true`.</span></span>
  
  - <span data-ttu-id="c2db6-405">Exchange Online PowerShell で次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-405">Use the following cmdlets in Exchange Online PowerShell:</span></span>

    - <span data-ttu-id="c2db6-406">[Search-MailboxAuditLog を使用](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) して、特定のユーザーのメールボックス監査ログを検索します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-406">[Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) to search the mailbox audit log for specific users.</span></span>

    - <span data-ttu-id="c2db6-407">[New-MailboxAuditLogSearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxauditlogsearch) は、メールボックス監査ログで特定のユーザーを検索し、その結果を電子メールで指定された受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-407">[New-MailboxAuditLogSearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxauditlogsearch) to search the mailbox audit log for specific users and to have the results sent via email to specified recipients.</span></span>

  - <span data-ttu-id="c2db6-408">Exchange Online の Exchange 管理センター (EAC) を使用して、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-408">Use the Exchange admin center (EAC) in Exchange Online to do the following actions:</span></span>

    - [<span data-ttu-id="c2db6-409">メールボックス監査ログのエクスポート</span><span class="sxs-lookup"><span data-stu-id="c2db6-409">Export mailbox audit logs</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [<span data-ttu-id="c2db6-410">所有者以外のメールボックス アクセスのレポートを実行する</span><span class="sxs-lookup"><span data-stu-id="c2db6-410">Run a non-owner mailbox access report</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- <span data-ttu-id="c2db6-411">既定では、メールボックス監査ログ レコードは削除される前に 90 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-411">By default, mailbox audit log records are retained for 90 days before they're deleted.</span></span> <span data-ttu-id="c2db6-412">Exchange Online PowerShell の **Set-Mailbox** コマンドレットの *AuditLogAgeLimit* パラメーターを使用して、監査ログ レコードの保存期限を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-412">You can change the age limit for audit log records by using the *AuditLogAgeLimit* parameter on the **Set-Mailbox** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="c2db6-413">ただし、この値を大きくしても、監査ログで 90 日以上前のイベントを検索できない。</span><span class="sxs-lookup"><span data-stu-id="c2db6-413">However, increasing this value doesn't allow you to search for events that are older than 90 days in the audit log.</span></span>

  <span data-ttu-id="c2db6-414">保存期間を増やす場合は、Exchange Online PowerShell で [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) コマンドレットを使用して、90 日より古いレコードについてユーザーのメールボックス監査ログを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2db6-414">If you increase the age limit, you need to use the [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) cmdlet in Exchange Online PowerShell to search the user's mailbox audit log for records that are older than 90 days.</span></span>

- <span data-ttu-id="c2db6-415">組織のメールボックス監査が既定で有効にされる前に、メールボックスの *AuditLogAgeLimit* プロパティを変更した場合、メールボックスの既存の監査ログの保存期限は変更されません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-415">If you've changed the *AuditLogAgeLimit* property for a mailbox prior to mailbox auditing on by default being turned on for organization, the mailbox's existing audit log age limit isn't changed.</span></span> <span data-ttu-id="c2db6-416">つまり、既定のメールボックス監査は、メールボックス監査レコードの現在の保存時間制限に影響を与えるという意味です。</span><span class="sxs-lookup"><span data-stu-id="c2db6-416">In other words, mailbox auditing on by default doesn't affect the current age limit for mailbox audit records.</span></span>

- <span data-ttu-id="c2db6-417">Microsoft 365 グループ メールボックスの *AuditLogAgeLimit* 値を変更するには、スイッチを `-GroupMailbox` **Set-Mailbox コマンドに含める必要** があります。</span><span class="sxs-lookup"><span data-stu-id="c2db6-417">To change the *AuditLogAgeLimit* value on an Microsoft 365 Group mailbox, you need to include the `-GroupMailbox` switch in the **Set-Mailbox** command.</span></span>

- <span data-ttu-id="c2db6-418">メールボックス監査ログ レコードは、各ユーザーのメールボックスの [回復可能なアイテム] フォルダー内のサブフォルダー *(Audits* という名前) に格納されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-418">Mailbox audit log records are stored in a subfolder (named *Audits*) in the Recoverable Items folder in each user's mailbox.</span></span> <span data-ttu-id="c2db6-419">メールボックス監査レコードと回復可能なアイテム フォルダーについては、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c2db6-419">Keep the following things in mind about mailbox audit records and the Recoverable Items folder:</span></span>

  - <span data-ttu-id="c2db6-420">メールボックス監査レコードは、回復可能なアイテム フォルダーの記憶域クォータ (既定では 30 GB) にカウントされます (警告クォータは 20 GB です)。</span><span class="sxs-lookup"><span data-stu-id="c2db6-420">Mailbox audit records count against the storage quota of the Recoverable Items folder, which is 30GB by default (the warning quota is 20 GB).</span></span> <span data-ttu-id="c2db6-421">記憶域クォータは、次の場合に自動的に 100 GB に増加します (警告クォータは 90 GB です)。</span><span class="sxs-lookup"><span data-stu-id="c2db6-421">The storage quota is automatically increased to 100 GB (with a 90 GB warning quota) when:</span></span>

    - <span data-ttu-id="c2db6-422">メールボックスにホールドが適用されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-422">A hold is placed on a mailbox.</span></span>

    - <span data-ttu-id="c2db6-423">メールボックスは、コンプライアンス センターのアイテム保持ポリシーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-423">The mailbox is assigned to a retention policy in the Compliance Center.</span></span>

  - <span data-ttu-id="c2db6-424">メールボックス監査レコードは、回復可能なアイテム [フォルダーのフォルダー制限にもカウントされます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)。</span><span class="sxs-lookup"><span data-stu-id="c2db6-424">Mailbox audit records also count against the [folder limit for the Recoverable Items folder](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits).</span></span> <span data-ttu-id="c2db6-425">最大 300 万アイテム (監査レコード) を Audits サブフォルダーに格納できます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-425">A maximum of 3 million items (audit records) can be stored in the Audits subfolder.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c2db6-426">メールボックス監査が既定で記憶域クォータまたは回復可能なアイテム フォルダーのフォルダー制限に影響を与える可能性は低い。</span><span class="sxs-lookup"><span data-stu-id="c2db6-426">It's unlikely that mailbox auditing on by default will impact the storage quota or the folder limit for the Recoverable Items folder.</span></span>

    - <span data-ttu-id="c2db6-427">Exchange Online PowerShell で次のコマンドを実行すると、回復可能なアイテム フォルダーの Audits サブフォルダー内のアイテムのサイズと数を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-427">You can run the following command in Exchange Online PowerShell to display the size and number of items in the Audits subfolder in the Recoverable Items folder:</span></span>

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - <span data-ttu-id="c2db6-428">[回復可能なアイテム] フォルダー内の監査ログ レコードに直接アクセスすることはできません。代わりに **、Search-MailboxAuditLog** コマンドレットを使用するか、監査ログを検索してメールボックス監査レコードを検索して表示します。</span><span class="sxs-lookup"><span data-stu-id="c2db6-428">You can't directly access an audit log record in the Recoverable Items folder; instead, you use the **Search-MailboxAuditLog** cmdlet or search the audit log to find and view mailbox audit records.</span></span>

- <span data-ttu-id="c2db6-429">メールボックスが保留にされている場合、またはコンプライアンス センターのアイテム保持ポリシーに割り当てられている場合、監査ログ レコードは、メールボックスの *AuditLogAgeLimit* プロパティで定義されている期間 (既定では 90 日間) 保持されます。</span><span class="sxs-lookup"><span data-stu-id="c2db6-429">If a mailbox is placed on hold or assigned to a retention policy in the Compliance Center, audit log records are still retained for the duration that's defined by the mailbox's *AuditLogAgeLimit* property (90 days by default).</span></span> <span data-ttu-id="c2db6-430">保持中のメールボックスの監査ログ レコードを長く保持するには、メールボックスの *AuditLogAgeLimit* 値を増やす必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2db6-430">To retain audit log records longer for mailboxes on hold, you need to increase mailbox's *AuditLogAgeLimit* value.</span></span>

- <span data-ttu-id="c2db6-431">複数地域環境では、複数地域のメールボックスの監査はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-431">In a multi-geo environment, cross-geo mailbox auditing is not supported.</span></span> <span data-ttu-id="c2db6-432">たとえば、異なる地理的位置にある共有メールボックスにアクセスする権限がユーザーに割り当てられている場合、そのユーザーが実行したメールボックス操作は、共有メールボックスのメールボックス監査ログに記録されません。</span><span class="sxs-lookup"><span data-stu-id="c2db6-432">For example, if a user is assigned permissions to access a shared mailbox in a different geo location, mailbox actions performed by that user are not logged in the mailbox audit log of the shared mailbox.</span></span>
