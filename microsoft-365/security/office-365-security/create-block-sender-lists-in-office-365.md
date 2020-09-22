---
title: ブロックする差出人リストを作成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: 管理者は、Exchange Online Protection (EOP) で受信メッセージをブロックするための使用可能なオプションと優先するオプションについて学ぶことができます。
ms.openlocfilehash: 7894a6cfe665539fa8c00f5911c4a588b9cf7ebc
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203193"
---
# <a name="create-blocked-sender-lists-in-eop"></a><span data-ttu-id="95be4-103">EOP でブロックされる送信者リストを作成する</span><span class="sxs-lookup"><span data-stu-id="95be4-103">Create blocked sender lists in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="95be4-104">Exchange online メールボックスを使用しない exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織内にメールボックスを持つ Microsoft 365 組織では、EOP は、不要な送信者からの電子メールをブロックする複数の方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="95be4-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers multiple ways of blocking email from unwanted senders.</span></span> <span data-ttu-id="95be4-105">これらのオプションには、Outlook のブロックされた送信者、ブロックされる送信者リストまたは禁止されたドメインリスト、スパム対策ポリシー、Exchange メールフロールール (トランスポートルールとも呼ばれる)、IP 禁止一覧 (接続フィルター) などがあります。</span><span class="sxs-lookup"><span data-stu-id="95be4-105">These options include Outlook Blocked Senders, blocked sender lists or blocked domain lists in anti-spam policies, Exchange mail flow rules (also known as transport rules), and the IP Block List (connection filtering).</span></span> <span data-ttu-id="95be4-106">これらのオプションは、ブロックされる _送信者リスト_と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="95be4-106">Collectively, you can think of these options as _blocked sender lists_.</span></span>

<span data-ttu-id="95be4-107">送信者をブロックする最善の方法は、影響の範囲によって異なります。</span><span class="sxs-lookup"><span data-stu-id="95be4-107">The best method to block senders varies on the scope of impact.</span></span> <span data-ttu-id="95be4-108">1人のユーザーの場合、適切なソリューションは、Outlook のブロックされた送信者になることがあります。</span><span class="sxs-lookup"><span data-stu-id="95be4-108">For a single user, the right solution could be Outlook Blocked Senders.</span></span> <span data-ttu-id="95be4-109">多くのユーザーにとって、他のオプションのいずれかが適しています。</span><span class="sxs-lookup"><span data-stu-id="95be4-109">For many users, one of the other options would be more appropriate.</span></span> <span data-ttu-id="95be4-110">次のオプションは、影響範囲と幅広さの両方によってランク付けされます。</span><span class="sxs-lookup"><span data-stu-id="95be4-110">The following options are ranked by both impact scope and breadth.</span></span> <span data-ttu-id="95be4-111">リストは狭い範囲から広くなりますが、詳細については、 *「詳細* 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95be4-111">The list goes from narrow to broad, but *read the specifics* for full recommendations.</span></span>

1. <span data-ttu-id="95be4-112">Outlook の受信拒否リスト (各メールボックスに格納されている受信拒否リスト)</span><span class="sxs-lookup"><span data-stu-id="95be4-112">Outlook Blocked Senders (the Blocked Senders list that's stored in each mailbox)</span></span>

2. <span data-ttu-id="95be4-113">ブロックされる送信者の一覧または禁止されたドメインリスト (スパム対策ポリシー)</span><span class="sxs-lookup"><span data-stu-id="95be4-113">Blocked sender lists or blocked domain lists (anti-spam policies)</span></span>

3. <span data-ttu-id="95be4-114">メール フロー ルール</span><span class="sxs-lookup"><span data-stu-id="95be4-114">Mail flow rules</span></span>

4. <span data-ttu-id="95be4-115">IP 禁止一覧 (接続フィルター)</span><span class="sxs-lookup"><span data-stu-id="95be4-115">The IP Block List (connection filtering)</span></span>

> [!NOTE]
> <span data-ttu-id="95be4-116">誤検知を解決するために、組織全体のブロック設定を使用することはできますが (迷惑メールは失われます)、それらのメッセージを分析のために Microsoft に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95be4-116">While you can use organization-wide block settings to address false negatives (missed spam), you should also submit those messages to Microsoft for analysis.</span></span> <span data-ttu-id="95be4-117">ブロックリストを使用して誤検知を管理すると、管理オーバーヘッドが大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="95be4-117">Managing false negatives by using block lists significantly increases your administrative overhead.</span></span> <span data-ttu-id="95be4-118">ブロックリストを使用して、不在時のスパムを切り替えるする場合は、準備完了時に、トピック [レポートのメッセージとファイルを Microsoft に](report-junk-email-messages-to-microsoft.md) 保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95be4-118">If you use block lists to deflect missed spam, you need to keep the topic [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md) at the ready.</span></span>

<span data-ttu-id="95be4-119">一方、[ _差出人セーフリスト_] を使用して特定の送信元からの電子メールを常に許可するには、いくつかのオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="95be4-119">In contrast, you also have several options to always allow email from specific sources using _safe sender lists_.</span></span> <span data-ttu-id="95be4-120">詳細については、「[信頼できる差出人リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95be4-120">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="email-message-basics"></a><span data-ttu-id="95be4-121">電子メールメッセージの基本</span><span class="sxs-lookup"><span data-stu-id="95be4-121">Email message basics</span></span>

<span data-ttu-id="95be4-122">標準的な SMTP 電子メール メッセージは、*メッセージ エンベロープ*とメッセージのコンテンツで構成されます。</span><span class="sxs-lookup"><span data-stu-id="95be4-122">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="95be4-123">メッセージエンベロープには、SMTP サーバー間でメッセージを送信および配信するために必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="95be4-123">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="95be4-124">メッセージのコンテンツには、総称して "*メッセージ ヘッダー*" と呼ばれるメッセージ ヘッダー フィールドと、メッセージ本文があります。</span><span class="sxs-lookup"><span data-stu-id="95be4-124">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="95be4-125">メッセージエンベロープは RFC 5321 で説明されており、メッセージヘッダーについては RFC 5322 で説明されています。</span><span class="sxs-lookup"><span data-stu-id="95be4-125">The message envelope is described in RFC 5321, and the message header is described in RFC 5322.</span></span> <span data-ttu-id="95be4-126">メッセージの送信プロセスによって生成されたメッセージエンベロープがメッセージの一部ではないため、受信者に実際のメッセージエンベロープが表示されることはありません。</span><span class="sxs-lookup"><span data-stu-id="95be4-126">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="95be4-127">`5321.MailFrom`アドレス ( **MAIL FROM** address、P1 sender、または envelope sender とも呼ばれます) は、メッセージの SMTP 送信で使用される電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="95be4-127">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="95be4-128">通常、この電子メールアドレスは、メッセージヘッダーの **リターンパス** ヘッダーフィールドに記録されます (ただし、送信者は別の **リターンパス** 電子メールアドレスを指定することもできます)。</span><span class="sxs-lookup"><span data-stu-id="95be4-128">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span> <span data-ttu-id="95be4-129">メッセージを配信できない場合は、配信不能レポート (NDR またはバウンスメッセージとも呼ばれます) の受信者です。</span><span class="sxs-lookup"><span data-stu-id="95be4-129">If the message can't be delivered, it's the recipient for the non-delivery report (also known as an NDR or bounce message).</span></span>

- <span data-ttu-id="95be4-130">`5322.From`( **From**アドレスまたは P2 送信者とも呼ばれる) は、[送信**元**アドレス] フィールドの電子メールアドレスであり、電子メールクライアントに表示される送信者の電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="95be4-130">The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span>

<span data-ttu-id="95be4-131">多くの場合、 `5321.MailFrom` と `5322.From` アドレスは同じです (個人間通信)。</span><span class="sxs-lookup"><span data-stu-id="95be4-131">Frequently, the `5321.MailFrom` and `5322.From` addresses are the same (person-to-person communication).</span></span> <span data-ttu-id="95be4-132">ただし、他のユーザーの代理として電子メールを送信する場合、アドレスは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="95be4-132">However, when email is sent on behalf of someone else, the addresses can be different.</span></span>

<span data-ttu-id="95be4-133">EOP のスパム対策ポリシーでブロックされる送信者リストと禁止ドメインリストは、との両方の `5321.MailFrom` アドレスを検査し `5322.From` ます。</span><span class="sxs-lookup"><span data-stu-id="95be4-133">Blocked sender lists and blocked domain lists in anti-spam policies in EOP inspect both the `5321.MailFrom` and `5322.From` addresses.</span></span> <span data-ttu-id="95be4-134">Outlook の受信拒否リストは、アドレスのみを使用 `5322.From` します。</span><span class="sxs-lookup"><span data-stu-id="95be4-134">Outlook Blocked Senders only uses the `5322.From` address.</span></span>

## <a name="use-outlook-blocked-senders"></a><span data-ttu-id="95be4-135">Outlook の受信拒否リストを使用する</span><span class="sxs-lookup"><span data-stu-id="95be4-135">Use Outlook Blocked Senders</span></span>

<span data-ttu-id="95be4-136">少数のユーザーのみが不要なメールを受信した場合、ユーザーまたは管理者はメールボックスの受信拒否リストに送信者の電子メールアドレスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="95be4-136">When only a small number of users received unwanted email, users or admins can add the sender email addresses to the Blocked Senders list in the mailbox.</span></span> <span data-ttu-id="95be4-137">手順については、「 [Exchange Online メールボックスで迷惑メールの設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95be4-137">For instructions, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

<span data-ttu-id="95be4-138">ユーザーの受信拒否リストによってメッセージが正常にブロックされると、 **スパム対策** ヘッダーフィールドに値が含まれ `SFV:BLK` ます。</span><span class="sxs-lookup"><span data-stu-id="95be4-138">When messages are successfully blocked due to a user's Blocked Senders list, the **X-Forefront-Antispam-Report** header field will contain the value `SFV:BLK`.</span></span>

> [!NOTE]
> <span data-ttu-id="95be4-139">不要なメッセージがよく知られ認識可能なソースからのニュースレターである場合は、電子メールからの登録を中止して、ユーザーがメッセージを受信できないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="95be4-139">If the unwanted messages are newsletters from a reputable and recognizable source, unsubscribing from the email is another option to stop the user from receiving the messages.</span></span>

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a><span data-ttu-id="95be4-140">ブロックする送信者リストまたは禁止ドメインリストを使用する</span><span class="sxs-lookup"><span data-stu-id="95be4-140">Use blocked sender lists or blocked domain lists</span></span>

<span data-ttu-id="95be4-141">複数のユーザーが影響を受ける場合、範囲は広くなるため、次の最適なオプションは、[迷惑メール対策] ポリシーの [送信者リストまたはブロックされたドメインリスト] に制限されます。</span><span class="sxs-lookup"><span data-stu-id="95be4-141">When multiple users are affected, the scope is wider, so the next best option is blocked sender lists or blocked domain lists in anti-spam policies.</span></span> <span data-ttu-id="95be4-142">リストの送信者からのメッセージが **スパム**としてマークされ、 **スパム** フィルター verdict に対して構成したアクションがメッセージに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="95be4-142">Messages from senders on the lists are marked as **Spam**, and the action that you've configured for the **Spam** filter verdict is taken on the message.</span></span> <span data-ttu-id="95be4-143">詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95be4-143">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="95be4-144">これらのリストの最大数は、約1000エントリです。</span><span class="sxs-lookup"><span data-stu-id="95be4-144">The maximum limit for these lists is approximately 1000 entries.</span></span>

## <a name="use-mail-flow-rules"></a><span data-ttu-id="95be4-145">メールフロールールを使用する</span><span class="sxs-lookup"><span data-stu-id="95be4-145">Use mail flow rules</span></span>

<span data-ttu-id="95be4-146">特定のユーザーまたは組織全体で送信されるメッセージをブロックする必要がある場合は、メールフロールールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="95be4-146">If you need to block messages that are sent to specific users or across the entire organization, you can use mail flow rules.</span></span> <span data-ttu-id="95be4-147">メールフロールールは、不要なメッセージ内のキーワードまたはその他のプロパティを検索することができるので、受信者のリストまたは受信拒否リストをブロックするよりも柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="95be4-147">Mail flow rules are more flexible than block sender lists or blocked sender domain lists because they can also look for keywords or other properties in the unwanted messages.</span></span>

<span data-ttu-id="95be4-148">メッセージを識別するために使用する条件または例外に関係なく、メッセージのスパム信頼レベル (SCL) を9に設定するアクションを構成して、メッセージに **信頼度の高いスパム**をマークします。</span><span class="sxs-lookup"><span data-stu-id="95be4-148">Regardless of the conditions or exceptions that you use to identify the messages, you configure the action to set the spam confidence level (SCL) of the message to 9, which marks the message a **High confidence spam**.</span></span> <span data-ttu-id="95be4-149">詳細については、「 [メールフロールールを使用したメッセージでの SCL の設定」を](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="95be4-149">For more information, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95be4-150">*過剰*なルールを作成するのは簡単であるため、特定の条件を使用してブロックするメッセージのみを特定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="95be4-150">It's easy to create rules that are *overly* aggressive, so it's important that you identify only the messages you want to block using using very specific criteria.</span></span> <span data-ttu-id="95be4-151">また、すべてが予期したとおりに動作するように、ルールの監査を有効にして、ルールの結果をテストしてください。</span><span class="sxs-lookup"><span data-stu-id="95be4-151">Also, be sure to enable auditing on the rule and test the results of the rule to ensure everything works as expected.</span></span>

## <a name="use-the-ip-block-list"></a><span data-ttu-id="95be4-152">IP 禁止一覧を使用する</span><span class="sxs-lookup"><span data-stu-id="95be4-152">Use the IP Block List</span></span>

<span data-ttu-id="95be4-153">他のオプションのいずれかを使用して送信者をブロックすることができない場合は、接続フィルターポリシーで IP 禁止一覧を使用 *する必要が* あります。</span><span class="sxs-lookup"><span data-stu-id="95be4-153">When it's not possible to use one of the other options to block a sender, *only then* should you use the IP Block List in the connection filter policy.</span></span> <span data-ttu-id="95be4-154">詳細については、「[接続フィルター ポリシーを構成する](configure-the-connection-filter-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95be4-154">For more information, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> <span data-ttu-id="95be4-155">ブロックされている ip の数を最小限に抑えることが重要なので、IP アドレス範囲全体をブロックすることはお勧めし *ません* 。</span><span class="sxs-lookup"><span data-stu-id="95be4-155">It's important to keep the number of blocked IPs to a minimum, so blocking entire IP address ranges is *not* recommended.</span></span>

<span data-ttu-id="95be4-156">*特*に、コンシューマーサービス (たとえば、outlook.com) や共有インフラストラクチャに属する ip アドレス範囲の追加を避ける必要があります。また、定期的なメンテナンスの一環として、ブロックされる ip アドレスの一覧を確認してください。</span><span class="sxs-lookup"><span data-stu-id="95be4-156">You should *especially* avoid adding IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures, and also ensure that you review the list of blocked IP addresses as part of regular maintenance.</span></span>
