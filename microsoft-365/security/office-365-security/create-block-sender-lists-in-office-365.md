---
title: Office 365 でブロックされる送信者のリストを作成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: 管理者は、Office 365 および EOP で使用可能なオプションについて学び、受信メッセージをブロックすることができます。
ms.openlocfilehash: 0bfab3024bc781e53600092ebc88fae25c5f4afc
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033424"
---
# <a name="create-blocked-sender-lists-in-office-365"></a><span data-ttu-id="fc6f7-103">Office 365 でブロックされる送信者のリストを作成する</span><span class="sxs-lookup"><span data-stu-id="fc6f7-103">Create blocked sender lists in Office 365</span></span>

<span data-ttu-id="fc6f7-104">Exchange Online または exchange online メールボックスを持たないスタンドアロンの Exchange Online Protection (EOP) 顧客のメールボックスを使用している Office 365 お客様の場合、EOP は、不要な送信者からの電子メールをブロックする複数の方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP offers multiple ways of blocking email from unwanted senders.</span></span> <span data-ttu-id="fc6f7-105">これらのオプションには、Outlook のブロックされた送信者、ブロックされる送信者リストまたは禁止されたドメインリスト、スパム対策ポリシー、Exchange メールフロールール (トランスポートルールとも呼ばれる)、IP 禁止一覧 (接続フィルター) などがあります。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-105">These options include Outlook Blocked Senders, blocked sender lists or blocked domain lists in anti-spam policies, Exchange mail flow rules (also known as transport rules), and the IP Block List (connection filtering).</span></span> <span data-ttu-id="fc6f7-106">これらのオプションは、ブロックされる_送信者リスト_と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-106">Collectively, you can think of these options as _blocked sender lists_.</span></span>

<span data-ttu-id="fc6f7-107">送信者をブロックする最善の方法は、影響の範囲によって異なります。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-107">The best method to block senders varies on the scope of impact.</span></span> <span data-ttu-id="fc6f7-108">1人のユーザーの場合、適切なソリューションは、Outlook のブロックされた送信者になることがあります。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-108">For a single user, the right solution could be Outlook Blocked Senders.</span></span> <span data-ttu-id="fc6f7-109">多くのユーザーにとって、他のオプションのいずれかが適しています。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-109">For many users, one of the other options would be more appropriate.</span></span> <span data-ttu-id="fc6f7-110">次のオプションは、影響範囲と幅広さの両方によってランク付けされます。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-110">The following options are ranked by both impact scope and breadth.</span></span> <span data-ttu-id="fc6f7-111">リストは狭い範囲から広くなりますが、詳細については、 *「詳細*」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-111">The list goes from narrow to broad, but *read the specifics* for full recommendations.</span></span>

1. <span data-ttu-id="fc6f7-112">Outlook の受信拒否リスト (各メールボックスに格納されている受信拒否リスト)</span><span class="sxs-lookup"><span data-stu-id="fc6f7-112">Outlook Blocked Senders (the Blocked Senders list that's stored in each mailbox)</span></span>

2. <span data-ttu-id="fc6f7-113">ブロックされる送信者の一覧または禁止されたドメインリスト (スパム対策ポリシー)</span><span class="sxs-lookup"><span data-stu-id="fc6f7-113">Blocked sender lists or blocked domain lists (anti-spam policies)</span></span>

3. <span data-ttu-id="fc6f7-114">メール フロー ルール</span><span class="sxs-lookup"><span data-stu-id="fc6f7-114">Mail flow rules</span></span>

4. <span data-ttu-id="fc6f7-115">IP 禁止一覧 (接続フィルター)</span><span class="sxs-lookup"><span data-stu-id="fc6f7-115">The IP Block List (connection filtering)</span></span>

> [!NOTE]
> <span data-ttu-id="fc6f7-116">誤検知を解決するために、組織全体のブロック設定を使用することはできますが (迷惑メールは失われます)、それらのメッセージを分析のために Microsoft に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-116">While you can use organization-wide block settings to address false negatives (missed spam), you should also submit those messages to Microsoft for analysis.</span></span> <span data-ttu-id="fc6f7-117">ブロックリストを使用して誤検知を管理すると、管理オーバーヘッドが大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-117">Managing false negatives by using block lists significantly increases your administrative overhead.</span></span> <span data-ttu-id="fc6f7-118">ブロックリストを使用して、不在時のスパムを切り替えるする場合は、準備完了時に、トピック[レポートのメッセージとファイルを Microsoft に](report-junk-email-messages-to-microsoft.md)保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-118">If you use block lists to deflect missed spam, you need to keep the topic [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md) at the ready.</span></span>

<span data-ttu-id="fc6f7-119">一方、[_差出人セーフリスト_] を使用して特定の送信元からの電子メールを常に許可するには、いくつかのオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-119">In contrast, you also have several options to always allow email from specific sources using _safe sender lists_.</span></span> <span data-ttu-id="fc6f7-120">詳細については、「 [Office の信頼できる差出人のリストを作成する 365](create-safe-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-120">For more information, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="use-outlook-blocked-senders"></a><span data-ttu-id="fc6f7-121">Outlook の受信拒否リストを使用する</span><span class="sxs-lookup"><span data-stu-id="fc6f7-121">Use Outlook Blocked Senders</span></span>

<span data-ttu-id="fc6f7-122">少数のユーザーのみが不要なメールを受信した場合、ユーザーまたは管理者はメールボックスの受信拒否リストに送信者の電子メールアドレスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-122">When only a small number of users received unwanted email, users or admins can add the sender email addresses to the Blocked Senders list in the mailbox.</span></span> <span data-ttu-id="fc6f7-123">手順については、「 [Office 365 の Exchange Online メールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-123">For instructions, see [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

<span data-ttu-id="fc6f7-124">ユーザーの受信拒否リストによってメッセージが正常にブロックされると、**スパム対策**ヘッダーフィールドに値`SFV:BLK`が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-124">When messages are successfully blocked due to a user's Blocked Senders list, the **X-Forefront-Antispam-Report** header field will contain the value `SFV:BLK`.</span></span>

> [!NOTE]
> <span data-ttu-id="fc6f7-125">不要なメッセージがよく知られ認識可能なソースからのニュースレターである場合は、電子メールからの登録を中止して、ユーザーがメッセージを受信できないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-125">If the unwanted messages are newsletters from a reputable and recognizable source, unsubscribing from the email is another option to stop the user from receiving the messages.</span></span>

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a><span data-ttu-id="fc6f7-126">ブロックする送信者リストまたは禁止ドメインリストを使用する</span><span class="sxs-lookup"><span data-stu-id="fc6f7-126">Use blocked sender lists or blocked domain lists</span></span>

<span data-ttu-id="fc6f7-127">複数のユーザーが影響を受ける場合、範囲は広くなるため、次の最適なオプションは、[迷惑メール対策] ポリシーの [送信者リストまたはブロックされたドメインリスト] に制限されます。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-127">When multiple users are affected, the scope is wider, so the next best option is blocked sender lists or blocked domain lists in anti-spam policies.</span></span> <span data-ttu-id="fc6f7-128">リストの送信者からのメッセージが**スパム**としてマークされ、**スパム**フィルター verdict に対して構成したアクションがメッセージに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-128">Messages from senders on the lists are marked as **Spam**, and the action that you've configured for the **Spam** filter verdict is taken on the message.</span></span> <span data-ttu-id="fc6f7-129">詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-129">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="fc6f7-130">これらのリストの最大数は、約1000エントリです。ただし、ポータルには30個のエントリしか入力できません。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-130">The maximum limit for these lists is approximately 1000 entries; although, you will only be able to enter 30 entries into the portal.</span></span> <span data-ttu-id="fc6f7-131">30個を超えるエントリを追加するには、PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-131">You need to use PowerShell to add more than 30 entries.</span></span>

## <a name="use-mail-flow-rules"></a><span data-ttu-id="fc6f7-132">メールフロールールを使用する</span><span class="sxs-lookup"><span data-stu-id="fc6f7-132">Use mail flow rules</span></span>

<span data-ttu-id="fc6f7-133">特定のユーザーまたは組織全体で送信されるメッセージをブロックする必要がある場合は、メールフロールールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-133">If you need to block messages that are sent to specific users or across the entire organization, you can use mail flow rules.</span></span> <span data-ttu-id="fc6f7-134">メールフロールールは、不要なメッセージ内のキーワードまたはその他のプロパティを検索することができるので、受信者のリストまたは受信拒否リストをブロックするよりも柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-134">Mail flow rules are more flexible than block sender lists or blocked sender domain lists because they can also look for keywords or other properties in the unwanted messages.</span></span>

<span data-ttu-id="fc6f7-135">メッセージを識別するために使用する条件または例外に関係なく、メッセージのスパム信頼レベル (SCL) を9に設定するアクションを構成して、メッセージに**信頼度の高いスパム**をマークします。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-135">Regardless of the conditions or exceptions that you use to identify the messages, you configure the action to set the spam confidence level (SCL) of the message to 9, which marks the message a **High confidence spam**.</span></span> <span data-ttu-id="fc6f7-136">詳細については、「[メールフロールールを使用したメッセージでの SCL の設定」を](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-136">For more information, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc6f7-137">*過剰*なルールを作成するのは簡単であるため、特定の条件を使用してブロックするメッセージのみを特定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-137">It's easy to create rules that are *overly* aggressive, so it's important that you identify only the messages you want to block using using very specific criteria.</span></span> <span data-ttu-id="fc6f7-138">また、すべてが予期したとおりに動作するように、ルールの監査を有効にして、ルールの結果をテストしてください。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-138">Also, be sure to enable auditing on the rule and test the results of the rule to ensure everything works as expected.</span></span>

## <a name="use-the-ip-block-list"></a><span data-ttu-id="fc6f7-139">IP 禁止一覧を使用する</span><span class="sxs-lookup"><span data-stu-id="fc6f7-139">Use the IP Block List</span></span>

<span data-ttu-id="fc6f7-140">他のオプションのいずれかを使用して送信者をブロックすることができない場合は、接続フィルターポリシーで IP 禁止一覧を使用*する必要が*あります。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-140">When it's not possible to use one of the other options to block a sender, *only then* should you use the IP Block List in the connection filter policy.</span></span> <span data-ttu-id="fc6f7-141">詳細については、「[接続フィルター ポリシーを構成する](configure-the-connection-filter-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-141">For more information, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> <span data-ttu-id="fc6f7-142">ブロックされている ip の数を最小限に抑えることが重要なので、IP アドレス範囲全体をブロックすることはお勧めし*ません*。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-142">It's important to keep the number of blocked IPs to a minimum, so blocking entire IP address ranges is *not* recommended.</span></span>

<span data-ttu-id="fc6f7-143">*特*に、コンシューマーサービス (たとえば、outlook.com) や共有インフラストラクチャに属する ip アドレス範囲の追加を避ける必要があります。また、定期的なメンテナンスの一環として、ブロックされる ip アドレスの一覧を確認してください。</span><span class="sxs-lookup"><span data-stu-id="fc6f7-143">You should *especially* avoid adding IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures, and also ensure that you review the list of blocked IP addresses as part of regular maintenance.</span></span>
