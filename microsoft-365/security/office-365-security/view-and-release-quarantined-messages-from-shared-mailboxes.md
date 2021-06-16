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
description: ユーザーは、アクセス許可を持つ共有メールボックスに送信された検疫済みメッセージを表示および処理する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4b958bb07660f4e0c93865300e190c713148a21d
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933057"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="6c170-103">共有メールボックスから検疫済みメッセージを表示および解放する</span><span class="sxs-lookup"><span data-stu-id="6c170-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="6c170-104">この記事で説明する機能は、現在プレビュー中であり、すべてのユーザーが利用できる機能ではなく、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c170-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="6c170-105">ユーザーは [、「EOP](find-and-release-quarantined-messages-as-a-user.md)で検疫済みメッセージをユーザーとして検索して解放する」の説明に従って、検疫済みメッセージを受信者の 1 つとして管理できます。</span><span class="sxs-lookup"><span data-stu-id="6c170-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="6c170-106">しかし、「共有 **メールボックス**」の説明に従って、ユーザーがフル アクセスおよび Send As または Send on Behalf のアクセス許可を持つ共有メールボックス [については](/exchange/collaboration-exo/shared-mailboxes)、Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="6c170-106">But what about **shared mailboxes** where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="6c170-107">以前は、ユーザーが共有メールボックスに送信された検疫済みメッセージを管理するには、管理者が共有メールボックスの自動マッピングを有効のままにする必要がありました (管理者がユーザーに別のメールボックスへのアクセス権を与える場合、既定で有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="6c170-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="6c170-108">ただし、ユーザーがアクセスできるメールボックスのサイズと数に応じて、Outlook がユーザーがアクセスできるすべてのメールボックスを開くしようとすると、パフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c170-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="6c170-109">このため、多くの管理者が共有メールボックス [の自動マップを削除する選択をします](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="6c170-109">For this reason, many admins choose to [remove automapping for shared mailboxes](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="6c170-110">これで、ユーザーが共有メールボックスに送信された検疫済みメッセージを管理するために、自動マッピングは不要になります。</span><span class="sxs-lookup"><span data-stu-id="6c170-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="6c170-111">動作します。</span><span class="sxs-lookup"><span data-stu-id="6c170-111">It just works.</span></span> <span data-ttu-id="6c170-112">共有メールボックスに送信された検疫済みメッセージにアクセスするには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="6c170-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="6c170-113">管理者がスパム対策[](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)ポリシーでエンド ユーザースパム通知を有効にしている場合、共有メールボックス内のエンド ユーザースパム通知にアクセスできるユーザーは、通知の [確認] ボタンをクリックして、Microsoft 365 Defender ポータルで検疫に移動できます。</span><span class="sxs-lookup"><span data-stu-id="6c170-113">If the admin has [enabled end-user spam notifications in anti-spam policies](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="6c170-114">この方法では、ユーザーが共有メールボックスに送信された検疫済みメッセージのみを管理できます。</span><span class="sxs-lookup"><span data-stu-id="6c170-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="6c170-115">ユーザーは、このコンテキストで独自の検疫メッセージを管理できません。</span><span class="sxs-lookup"><span data-stu-id="6c170-115">Users can't manage their own quarantine messages in this context.</span></span>
- <span data-ttu-id="6c170-116">ユーザーは[、Defender ポータルの検疫にMicrosoft 365できます](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="6c170-116">The user can [go to the quarantine in the Microsoft 365 Defender portal](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="6c170-117">既定では、ユーザーに送信されたメッセージだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c170-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="6c170-118">ただし、ユーザーは[結果の並べ替え] (既定では [メッセージ **ID]** ボタン) を [受信者の電子メール アドレス] に変更し、共有メールボックスの電子メール アドレスを入力し、[更新] をクリックして、共有メールボックスに送信された検疫済みメッセージを確認できます。 </span><span class="sxs-lookup"><span data-stu-id="6c170-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![検疫済みメッセージを受信者の電子メール アドレスで並べ替える。](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="6c170-120">方法に関係なく、ユーザーは検疫済みメッセージの **[受信者** ] 列を含め、混乱を回避できます。</span><span class="sxs-lookup"><span data-stu-id="6c170-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="6c170-121">表示する列の最大数は 7 なので、ユーザーは [列の変更] をクリックし、既存の列 (ポリシーの種類など) を削除し、[受信者] を選択し、[保存] または [既定で保存] をクリックする必要があります。 </span><span class="sxs-lookup"><span data-stu-id="6c170-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![[ポリシーの種類] 列を削除し、[受信者] 列を検疫に追加します。](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="6c170-123">留意すべき点</span><span class="sxs-lookup"><span data-stu-id="6c170-123">Things to keep in mind</span></span>

- <span data-ttu-id="6c170-124">検疫済みメッセージに対して最初に行動するユーザーは、共有メールボックスを使用するすべてのユーザーに対するメッセージの運命を決定します。</span><span class="sxs-lookup"><span data-stu-id="6c170-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="6c170-125">たとえば、共有メールボックスに 10 人のユーザーがアクセスし、ユーザーが検疫メッセージを削除する場合、メッセージは 10 人のユーザー全員に対して削除されます。</span><span class="sxs-lookup"><span data-stu-id="6c170-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="6c170-126">同様に、ユーザーがメッセージを解放すると判断した場合は、共有メールボックスに解放され、共有メールボックスの他のすべてのユーザーがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6c170-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="6c170-127">現在、[**送信者のブロック]** ボタンは、共有メールボックスに送信された検疫済みメッセージの詳細フライアウトでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="6c170-127">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="6c170-128">共有メールボックスの検疫操作について、入れ子になったセキュリティ グループを使用して共有メールボックスへのアクセスを許可する場合は、入れ子になったグループのレベルを 2 つ以下にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6c170-128">Regarding quarantine operations for shared mailboxes, if you use nested security groups to grant access to a shared mailbox, we recommend no more than two levels of nested groups.</span></span> <span data-ttu-id="6c170-129">たとえば、グループ A はグループ B のメンバーで、グループ C のメンバーです。共有メールボックスにアクセス許可を割り当てるには、ユーザーをグループ A に追加してから、グループ C を共有メールボックスに割り当てない。</span><span class="sxs-lookup"><span data-stu-id="6c170-129">For example, Group A is a member of Group B, which is a member of Group C. To assign permissions to a shared mailbox, don't add the user to Group A and then assign Group C to the shared mailbox.</span></span>  

- <span data-ttu-id="6c170-130">[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)で共有メールボックスの検疫済みメッセージを管理するには、エンド ユーザーが _RecipientAddress_ パラメーターの値に対して共有メールボックスの電子メール アドレスを持つ [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)コマンドレットを使用してメッセージを識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c170-130">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="6c170-131">例:</span><span class="sxs-lookup"><span data-stu-id="6c170-131">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="6c170-132">次に、エンド ユーザーは、リストから検疫済みメッセージを選択して、表示またはアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6c170-132">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="6c170-133">この例では、共有メールボックスに送信された検疫済みメッセージのすべてが表示され、リスト内の最初のメッセージが検疫から解放されます (リストの最初のメッセージは 0、2 番目は 1 など)。</span><span class="sxs-lookup"><span data-stu-id="6c170-133">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="6c170-134">構文およびパラメーターの詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c170-134">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="6c170-135">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="6c170-135">Get-QuarantineMessage</span></span>](/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="6c170-136">Get-QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="6c170-136">Get-QuarantineMessageHeader</span></span>](/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="6c170-137">Preview-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="6c170-137">Preview-QuarantineMessage</span></span>](/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="6c170-138">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="6c170-138">Release-QuarantineMessage</span></span>](/powershell/module/exchange/release-quarantinemessage)
