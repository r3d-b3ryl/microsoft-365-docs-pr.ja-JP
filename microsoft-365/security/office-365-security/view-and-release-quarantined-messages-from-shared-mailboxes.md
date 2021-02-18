---
title: 共有メールボックスから検疫済みメッセージを表示および解放する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: ユーザーは、アクセス許可を持つ共有メールボックスに送信された検疫済みメッセージを表示および処理する方法を学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 31fbf9c54c3f28e439f444dde872469918dc29d4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290143"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="4e59a-103">共有メールボックスから検疫済みメッセージを表示および解放する</span><span class="sxs-lookup"><span data-stu-id="4e59a-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="4e59a-104">この記事で説明する機能は現在プレビュー中であり、すべてのユーザーが利用できる機能ではありません。また、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4e59a-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="4e59a-105">ユーザーは、「EOP でユーザーとして検疫済みメッセージを検索して解放する」の説明に従って、受信者の 1 人である検疫済みメッセージ [を管理できます](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="4e59a-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="4e59a-106">しかし [、「Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)の共有メールボックス」の説明に従って、ユーザーがメールボックスに対するフル アクセスおよび [差出人を指定して送信] または [代理送信] のアクセス許可を持つ共有メールボックスについてはどうでしょうか。</span><span class="sxs-lookup"><span data-stu-id="4e59a-106">But what about shared mailboxes where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="4e59a-107">以前は、ユーザーが共有メールボックスに送信された検疫済みメッセージを管理する機能を使用するには、管理者が共有メールボックスに対して自動マッピングを有効のままにする必要がありました (管理者が別のメールボックスへのアクセスをユーザーに許可すると、既定で有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="4e59a-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="4e59a-108">ただし、ユーザーがアクセスできるメールボックスのサイズと数によっては、Outlook がユーザーがアクセスできるすべてのメールボックスを開けようとすると、パフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4e59a-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="4e59a-109">このため、多くの管理者は共有メールボックス [の自動マッピングを削除します](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="4e59a-109">For this reason, many admins choose to [remove automapping for shared mailboxes](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="4e59a-110">現在では、ユーザーが共有メールボックスに送信された検疫済みメッセージを管理するために、自動マッピングが必要なくなりました。</span><span class="sxs-lookup"><span data-stu-id="4e59a-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="4e59a-111">正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="4e59a-111">It just works.</span></span> <span data-ttu-id="4e59a-112">共有メールボックスに送信された検疫済みメッセージにアクセスするには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="4e59a-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="4e59a-113">管理者がスパム対策[](configure-your-spam-filter-policies.md)ポリシーでエンド ユーザーのスパム通知を有効にしている場合、共有メールボックス内のエンド ユーザーのスパム通知にアクセスできるユーザーは、通知の[確認] ボタンをクリックして、セキュリティ & コンプライアンス センターで検疫に移動できます。</span><span class="sxs-lookup"><span data-stu-id="4e59a-113">If the admin has [enabled end-user spam notifications](configure-your-spam-filter-policies.md) in anti-spam policies, any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="4e59a-114">この方法では、ユーザーが共有メールボックスに送信された検疫済みメッセージのみを管理できます。</span><span class="sxs-lookup"><span data-stu-id="4e59a-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="4e59a-115">ユーザーは、このコンテキストで自分の検疫メッセージを管理できません。</span><span class="sxs-lookup"><span data-stu-id="4e59a-115">Users can't manage their own quarantine messages in this context.</span></span>

- <span data-ttu-id="4e59a-116">ユーザーは、 [セキュリティ/コンプライアンス センターで検疫&移動できます](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="4e59a-116">The user can [go to the quarantine in the Security & Compliance Center](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="4e59a-117">既定では、ユーザーに送信されたメッセージだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e59a-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="4e59a-118">ただし、ユーザーは並べ替えの結果 **(既定** では [メッセージ **ID]** ボタン) を受信者の電子メール アドレスに変更し、共有メールボックスの電子メール アドレスを入力し、[最新の情報に更新] をクリックして、共有メールボックスに送信された検疫済みメッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4e59a-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![受信者の電子メール アドレスによる検疫済みメッセージの並べ替え。](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="4e59a-120">方法に関係なく、ユーザーは検疫済みメッセージの **[受信者** ] 列を含めて混乱を避ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4e59a-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="4e59a-121">表示する列の最大数は 7 なので、ユーザーは列の変更、既存の列の削除 (ポリシーの種類など)、受信者の選択、既定で [保存] または [保存] の順にクリックする必要 **があります。**  </span><span class="sxs-lookup"><span data-stu-id="4e59a-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![[ポリシーの種類] 列を削除し、[受信者] 列を検疫に追加します。](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="4e59a-123">留意すべき点</span><span class="sxs-lookup"><span data-stu-id="4e59a-123">Things to keep in mind</span></span>

- <span data-ttu-id="4e59a-124">検疫済みメッセージに対して最初に処理を行うユーザーは、共有メールボックスを使用しているすべてのユーザーのメッセージの形式を決定します。</span><span class="sxs-lookup"><span data-stu-id="4e59a-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="4e59a-125">たとえば、10 人のユーザーが共有メールボックスにアクセスし、ユーザーが検疫メッセージを削除する場合、メッセージは 10 人すべてのユーザーに対して削除されます。</span><span class="sxs-lookup"><span data-stu-id="4e59a-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="4e59a-126">同様に、ユーザーがメッセージを解放すると、そのメッセージは共有メールボックスに解放され、共有メールボックスの他のすべてのユーザーがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4e59a-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="4e59a-127">現在、[送信者 **のブロック]** ボタンは、共有メールボックスに送信された検疫済みメッセージの [詳細] フライアウトでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="4e59a-127">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="4e59a-128">[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)で共有メールボックスの検疫済みメッセージを管理するには、エンド ユーザーは _、RecipientAddress_ パラメーターの値に共有メールボックスの電子メール アドレスを指定して [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)コマンドレットを使用して、メッセージを識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e59a-128">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="4e59a-129">例:</span><span class="sxs-lookup"><span data-stu-id="4e59a-129">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="4e59a-130">その後、エンド ユーザーはリストから検疫済みメッセージを選択して、表示またはアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4e59a-130">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="4e59a-131">この例では、共有メールボックスに送信された検疫済みメッセージすべてが表示され、リスト内の最初のメッセージが検疫から解放されます (リスト内の最初のメッセージは 0、2 番目は 1 など)。</span><span class="sxs-lookup"><span data-stu-id="4e59a-131">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="4e59a-132">構文およびパラメーターの詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e59a-132">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="4e59a-133">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="4e59a-133">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="4e59a-134">Get-QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="4e59a-134">Get-QuarantineMessageHeader</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="4e59a-135">Preview-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="4e59a-135">Preview-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="4e59a-136">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="4e59a-136">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
