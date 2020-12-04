---
title: 共有メールボックスからの検疫済みメッセージの表示と解放
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: ユーザーがアクセス許可を持っている共有メールボックスに送信された検疫済みメッセージを表示し、操作する方法について説明します。
ms.openlocfilehash: 0c165395edc3a3032ece603cb8d9aac875443d7d
ms.sourcegitcommit: 26c2f01d6f88f6c288b04f9f08062d68dd1e67e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "49570963"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="c9336-103">共有メールボックスからの検疫済みメッセージの表示と解放</span><span class="sxs-lookup"><span data-stu-id="c9336-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="c9336-104">この記事で説明されている機能は現在プレビュー段階であり、すべてのユーザーが利用できるわけではありません。変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c9336-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="c9336-105">[EOP のユーザーとして検疫済みメッセージを検索して解放](find-and-release-quarantined-messages-as-a-user.md)する方法について説明されているように、ユーザーは検疫済みメッセージを管理できます。</span><span class="sxs-lookup"><span data-stu-id="c9336-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="c9336-106">しかし、 [Exchange Online の共有メール](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)ボックスに記載されているように、ユーザーがメールボックスへのフルアクセス権を持っている共有メールボックスについてはどうでしょうか。</span><span class="sxs-lookup"><span data-stu-id="c9336-106">But what about shared mailboxes where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="c9336-107">以前は、ユーザーが共有メールボックスに送信された検疫済みメッセージを管理する機能により、管理者が共有メールボックスに自動マッピングを有効にしておく必要がありました (管理者が別のメールボックスにユーザーアクセスを許可した場合、既定で有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="c9336-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="c9336-108">ただし、ユーザーがアクセスできるメールボックスのサイズと数によっては、ユーザーがアクセスできる *すべて* のメールボックスを開こうとすると、パフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c9336-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="c9336-109">このため、多くの管理者は、 [共有メールボックスの自動マッピングを削除](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)することを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9336-109">For this reason, many admins choose to [remove automapping for shared mailboxes](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="c9336-110">これで、ユーザーが共有メールボックスに送信された検疫済みメッセージを管理するために自動マッピングが不要になりました。</span><span class="sxs-lookup"><span data-stu-id="c9336-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="c9336-111">機能するだけです。</span><span class="sxs-lookup"><span data-stu-id="c9336-111">It just works.</span></span> <span data-ttu-id="c9336-112">共有メールボックスに送信された検疫済みメッセージにアクセスするには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="c9336-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="c9336-113">管理者がスパム対策ポリシーで [エンドユーザーのスパム通知を有効](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) にしている場合、共有メールボックス内のエンドユーザーのスパム通知にアクセスできるユーザーは、通知の [ **確認** ] ボタンをクリックして、セキュリティ & コンプライアンスセンターの [検疫] に移動できます。</span><span class="sxs-lookup"><span data-stu-id="c9336-113">If the admin has [enabled end-user spam notifications](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) in anti-spam policies, any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="c9336-114">この方法では、ユーザーが共有メールボックスに送信された検疫済みメッセージのみを管理できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c9336-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="c9336-115">ユーザーがこのコンテキストで自分の検疫メッセージを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="c9336-115">Users can't manage their own quarantine messages in this context.</span></span>

- <span data-ttu-id="c9336-116">ユーザーは、 [セキュリティ & コンプライアンスセンターで検疫に移動](find-and-release-quarantined-messages-as-a-user.md)できます。</span><span class="sxs-lookup"><span data-stu-id="c9336-116">The user can [go to the quarantine in the Security & Compliance Center](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="c9336-117">既定では、ユーザーに送信されたメッセージのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9336-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="c9336-118">ただし、ユーザーは **並べ替えの結果** (既定では、[ **メッセージ ID] ボタン** ) を [ **受信者の電子メールアドレス**] に変更し、共有メールボックスの電子メールアドレスを入力してから、[ **更新** ] をクリックして、共有メールボックスに送信された検疫済みメッセージを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="c9336-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![受信者の電子メールアドレスでの検疫済みメッセージの並べ替え。](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="c9336-120">方法に関係なく、ユーザーは検疫済みメッセージの [ **受信者** ] 列を含めることによって混乱を避けることができます。</span><span class="sxs-lookup"><span data-stu-id="c9336-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="c9336-121">表示する列の最大数は7です。ユーザーは、[ **列の変更**] をクリックし、既存の列を削除 (たとえば、[ **ポリシーの種類**])、[ **受信者**] を選択して、[ **保存** ] または [ **既定値として保存**] をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9336-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![[ポリシーの種類] 列を削除し、[受信者] 列を [検疫] に追加します。](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="c9336-123">留意すべき点</span><span class="sxs-lookup"><span data-stu-id="c9336-123">Things to keep in mind</span></span>

- <span data-ttu-id="c9336-124">最初に検疫されたメッセージを操作するユーザーは、共有メールボックスを使用するすべてのユーザーに対してメッセージの運命を決定します。</span><span class="sxs-lookup"><span data-stu-id="c9336-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="c9336-125">たとえば、共有メールボックスに10人のユーザーがアクセスしていて、ユーザーが検疫メッセージを削除することを決定した場合、そのメッセージは10人のユーザー全員に対して削除されます。</span><span class="sxs-lookup"><span data-stu-id="c9336-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="c9336-126">同様に、ユーザーがメッセージを解放することを決定した場合は、共有メールボックスに解放され、共有メールボックスの他のすべてのユーザーがアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="c9336-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="c9336-127">現時点では、共有メールボックスに送信された複数の検疫済みメッセージをユーザーが選択すると、ユーザーが [**メッセージの解放**] をクリックするか、**バルクアクション** ポップアップで **メッセージを削除** すると、次のような誤ったエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="c9336-127">Currently, if a user selects multiple quarantined messages that were sent to the shared mailbox, the following misleading errors are returned when the user clicks **Release messages** or **Delete messages** in the **Bulk actions** flyout:</span></span>

  > <span data-ttu-id="c9336-128">選択したすべての検疫済みメッセージを解放する権限がありません。</span><span class="sxs-lookup"><span data-stu-id="c9336-128">You do not have permission to release all selected quarantined messages.</span></span>
  >
  > <span data-ttu-id="c9336-129">選択したすべての検疫済みメッセージを削除する権限がありません。</span><span class="sxs-lookup"><span data-stu-id="c9336-129">You do not have permission to delete all selected quarantined messages.</span></span>

  <span data-ttu-id="c9336-130">エラーに関係なく、アクションはメッセージに対して実行され、エラーは無視できます。</span><span class="sxs-lookup"><span data-stu-id="c9336-130">Regardless of the error, the action is taken on the messages, and the error can be ignored.</span></span>

  ![共有メールボックスに送信された検疫済みメッセージを一括で解放または削除すると、エラーが発生します。](../../media/quarantine-bulk-action-error.png)

- <span data-ttu-id="c9336-132">現時点では、共有メールボックスに送信された検疫済みメッセージの **詳細** ポップアップで [**送信者をブロック** する] ボタンを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c9336-132">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="c9336-133">[Exchange Online の PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)で共有メールボックスの検疫済みメッセージを管理するには、エンドユーザーは、メッセージを識別するために、_受信者アドレス_ パラメーターの値として [get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)コマンドレットを使用して、共有メールボックスの電子メールアドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9336-133">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="c9336-134">例:</span><span class="sxs-lookup"><span data-stu-id="c9336-134">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="c9336-135">その後、エンドユーザーは、リストから検疫済みメッセージを選択して、操作を表示または実行することができます。</span><span class="sxs-lookup"><span data-stu-id="c9336-135">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="c9336-136">この例では、共有メールボックスに送信されたすべての検疫済みメッセージを示してから、リスト内の最初のメッセージを検疫から解放します (リスト内の最初のメッセージは0、2番目は1のようになります)。</span><span class="sxs-lookup"><span data-stu-id="c9336-136">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="c9336-137">構文およびパラメーターの詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9336-137">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="c9336-138">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="c9336-138">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="c9336-139">QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="c9336-139">Get-QuarantineMessageHeader</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="c9336-140">プレビュー-Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="c9336-140">Preview-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="c9336-141">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="c9336-141">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
