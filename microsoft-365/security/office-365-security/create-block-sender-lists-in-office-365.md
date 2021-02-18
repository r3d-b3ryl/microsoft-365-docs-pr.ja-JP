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
localization_priority: Normal
search.appverid:
- MET150s
description: 管理者は、Exchange Online Protection (EOP) で受信メッセージをブロックするための利用可能なオプションと優先オプションについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5c95b49db811807a0cb46dce5363b8ae2dbe5602
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287283"
---
# <a name="create-blocked-sender-lists-in-eop"></a><span data-ttu-id="06e73-103">EOP で受信拒否リストを作成する</span><span class="sxs-lookup"><span data-stu-id="06e73-103">Create blocked sender lists in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="06e73-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="06e73-104">**Applies to**</span></span>
- [<span data-ttu-id="06e73-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="06e73-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="06e73-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="06e73-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="06e73-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="06e73-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="06e73-108">Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない Microsoft 365 組織では、EOP は不要な送信者からの電子メールをブロックする複数の方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="06e73-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers multiple ways of blocking email from unwanted senders.</span></span> <span data-ttu-id="06e73-109">これらのオプションには、Outlook の受信拒否リスト、スパム対策ポリシー内の受信拒否リストまたは禁止ドメイン 一覧、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる)、IP 禁止一覧 (接続フィルター) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="06e73-109">These options include Outlook Blocked Senders, blocked sender lists or blocked domain lists in anti-spam policies, Exchange mail flow rules (also known as transport rules), and the IP Block List (connection filtering).</span></span> <span data-ttu-id="06e73-110">まとめて、これらのオプションは受信拒否リスト _と考えてもかかっています_。</span><span class="sxs-lookup"><span data-stu-id="06e73-110">Collectively, you can think of these options as _blocked sender lists_.</span></span>

<span data-ttu-id="06e73-111">送信者をブロックする最適な方法は、影響の範囲によって異なります。</span><span class="sxs-lookup"><span data-stu-id="06e73-111">The best method to block senders varies on the scope of impact.</span></span> <span data-ttu-id="06e73-112">1 人のユーザーの場合、適切なソリューションは Outlook の受信拒否リストである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="06e73-112">For a single user, the right solution could be Outlook Blocked Senders.</span></span> <span data-ttu-id="06e73-113">多くのユーザーの場合、他のオプションの 1 つが適しています。</span><span class="sxs-lookup"><span data-stu-id="06e73-113">For many users, one of the other options would be more appropriate.</span></span> <span data-ttu-id="06e73-114">次のオプションは、影響範囲と幅の両方によってランク付けされます。</span><span class="sxs-lookup"><span data-stu-id="06e73-114">The following options are ranked by both impact scope and breadth.</span></span> <span data-ttu-id="06e73-115">一覧は狭い範囲から幅広い範囲に表示されますが、 *推奨事項* の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06e73-115">The list goes from narrow to broad, but *read the specifics* for full recommendations.</span></span>

1. <span data-ttu-id="06e73-116">Outlook の受信拒否リスト (各メールボックスに保存されている受信拒否リスト)</span><span class="sxs-lookup"><span data-stu-id="06e73-116">Outlook Blocked Senders (the Blocked Senders list that's stored in each mailbox)</span></span>

2. <span data-ttu-id="06e73-117">受信拒否リストまたは禁止ドメイン一覧 (スパム対策ポリシー)</span><span class="sxs-lookup"><span data-stu-id="06e73-117">Blocked sender lists or blocked domain lists (anti-spam policies)</span></span>

3. <span data-ttu-id="06e73-118">メール フロー ルール</span><span class="sxs-lookup"><span data-stu-id="06e73-118">Mail flow rules</span></span>

4. <span data-ttu-id="06e73-119">IP ブロック リスト (接続フィルター)</span><span class="sxs-lookup"><span data-stu-id="06e73-119">The IP Block List (connection filtering)</span></span>

> [!NOTE]
> <span data-ttu-id="06e73-120">組織全体のブロック設定を使用して検出検出 (スパムの見逃し) に対処することもできますが、分析のためにそれらのメッセージを Microsoft に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06e73-120">While you can use organization-wide block settings to address false negatives (missed spam), you should also submit those messages to Microsoft for analysis.</span></span> <span data-ttu-id="06e73-121">ブロック リストを使用して検出検出を管理すると、管理オーバーヘッドが大幅に増加します。</span><span class="sxs-lookup"><span data-stu-id="06e73-121">Managing false negatives by using block lists significantly increases your administrative overhead.</span></span> <span data-ttu-id="06e73-122">ブロック リストを使用して、見つからないスパムを取り除く場合は、トピック [「](report-junk-email-messages-to-microsoft.md) メッセージとファイルを Microsoft に報告する」の準備を整える必要があります。</span><span class="sxs-lookup"><span data-stu-id="06e73-122">If you use block lists to deflect missed spam, you need to keep the topic [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md) at the ready.</span></span>

<span data-ttu-id="06e73-123">これに対し、差出人セーフ リストを使用して特定のソースからのメールを常に許可するオプション _もいくつか用意されています_。</span><span class="sxs-lookup"><span data-stu-id="06e73-123">In contrast, you also have several options to always allow email from specific sources using _safe sender lists_.</span></span> <span data-ttu-id="06e73-124">詳細については、「[信頼できる差出人リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06e73-124">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="email-message-basics"></a><span data-ttu-id="06e73-125">電子メール メッセージの基本</span><span class="sxs-lookup"><span data-stu-id="06e73-125">Email message basics</span></span>

<span data-ttu-id="06e73-126">標準的な SMTP 電子メール メッセージは、*メッセージ エンベロープ* とメッセージのコンテンツで構成されます。</span><span class="sxs-lookup"><span data-stu-id="06e73-126">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="06e73-127">メッセージ エンベロープには、SMTP サーバー間でメッセージを送信および配信するために必要な情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="06e73-127">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="06e73-128">メッセージのコンテンツには、総称して "*メッセージ ヘッダー*" と呼ばれるメッセージ ヘッダー フィールドと、メッセージ本文があります。</span><span class="sxs-lookup"><span data-stu-id="06e73-128">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="06e73-129">メッセージ エンベロープは RFC 5321 で記述され、メッセージ ヘッダーは RFC 5322 で記述されています。</span><span class="sxs-lookup"><span data-stu-id="06e73-129">The message envelope is described in RFC 5321, and the message header is described in RFC 5322.</span></span> <span data-ttu-id="06e73-130">実際のメッセージ エンベロープはメッセージ送信プロセスによって生成され、実際にはメッセージの一部ではないので、受信者には表示されません。</span><span class="sxs-lookup"><span data-stu-id="06e73-130">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="06e73-131">アドレス (MAIL FROM アドレス、P1 送信者、またはエンベロープ送信者とも呼ばれる) は、メッセージの SMTP 送信で使用される電子メール `5321.MailFrom` アドレスです。 </span><span class="sxs-lookup"><span data-stu-id="06e73-131">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="06e73-132">この電子メール アドレスは、通常、メッセージ ヘッダーの **Return-Path** ヘッダー フィールドに記録されます (ただし、送信者が別の **Return-Path** 電子メール アドレスを指定することもできます)。</span><span class="sxs-lookup"><span data-stu-id="06e73-132">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span> <span data-ttu-id="06e73-133">メッセージを配信できない場合は、配信不可レポート (NDR またはバウンス メッセージとも呼ばれる) の受信者です。</span><span class="sxs-lookup"><span data-stu-id="06e73-133">If the message can't be delivered, it's the recipient for the non-delivery report (also known as an NDR or bounce message).</span></span>

- <span data-ttu-id="06e73-134">The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span><span class="sxs-lookup"><span data-stu-id="06e73-134">The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span>

<span data-ttu-id="06e73-135">多くの場合、 `5321.MailFrom` 住所 `5322.From` は同じです (人と人のコミュニケーション)。</span><span class="sxs-lookup"><span data-stu-id="06e73-135">Frequently, the `5321.MailFrom` and `5322.From` addresses are the same (person-to-person communication).</span></span> <span data-ttu-id="06e73-136">ただし、メールが他のユーザーの代わりに送信される場合、アドレスは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="06e73-136">However, when email is sent on behalf of someone else, the addresses can be different.</span></span>

<span data-ttu-id="06e73-137">EOP のスパム対策ポリシーの受信拒否リストと禁止ドメイン 一覧は、両方のアドレスを `5321.MailFrom` 検査 `5322.From` します。</span><span class="sxs-lookup"><span data-stu-id="06e73-137">Blocked sender lists and blocked domain lists in anti-spam policies in EOP inspect both the `5321.MailFrom` and `5322.From` addresses.</span></span> <span data-ttu-id="06e73-138">Outlook の受信拒否リストはアドレスのみを使用 `5322.From` します。</span><span class="sxs-lookup"><span data-stu-id="06e73-138">Outlook Blocked Senders only uses the `5322.From` address.</span></span>

## <a name="use-outlook-blocked-senders"></a><span data-ttu-id="06e73-139">Outlook の受信拒否リストを使用する</span><span class="sxs-lookup"><span data-stu-id="06e73-139">Use Outlook Blocked Senders</span></span>

<span data-ttu-id="06e73-140">不要な電子メールを受信したユーザーが少ない場合、ユーザーまたは管理者は送信者の電子メール アドレスをメールボックスの受信拒否リストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="06e73-140">When only a small number of users received unwanted email, users or admins can add the sender email addresses to the Blocked Senders list in the mailbox.</span></span> <span data-ttu-id="06e73-141">手順については [、「Exchange Online メールボックスで迷惑メール設定を構成する」を参照してください](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="06e73-141">For instructions, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

<span data-ttu-id="06e73-142">ユーザーの受信拒否リストが原因でメッセージが正常にブロックされると **、X-Forefront-Antispam-Report** ヘッダー フィールドに値が含まれます `SFV:BLK` 。</span><span class="sxs-lookup"><span data-stu-id="06e73-142">When messages are successfully blocked due to a user's Blocked Senders list, the **X-Forefront-Antispam-Report** header field will contain the value `SFV:BLK`.</span></span>

> [!NOTE]
> <span data-ttu-id="06e73-143">望ましくないメッセージが、評判が良く、認識可能なソースからのニュースレターである場合は、電子メールからの登録解除も、ユーザーがメッセージを受信することを停止する別のオプションです。</span><span class="sxs-lookup"><span data-stu-id="06e73-143">If the unwanted messages are newsletters from a reputable and recognizable source, unsubscribing from the email is another option to stop the user from receiving the messages.</span></span>

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a><span data-ttu-id="06e73-144">受信拒否リストまたはブロックするドメイン 一覧を使用する</span><span class="sxs-lookup"><span data-stu-id="06e73-144">Use blocked sender lists or blocked domain lists</span></span>

<span data-ttu-id="06e73-145">複数のユーザーが影響を受ける場合、スコープは広くなります。そのため、次の最適なオプションは、スパム対策ポリシーの受信拒否リストまたはブロックされたドメイン 一覧です。</span><span class="sxs-lookup"><span data-stu-id="06e73-145">When multiple users are affected, the scope is wider, so the next best option is blocked sender lists or blocked domain lists in anti-spam policies.</span></span> <span data-ttu-id="06e73-146">リストの送信者からのメッセージはスパムとしてマークされ、スパム フィルターの条件に対して構成したアクションがメッセージに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="06e73-146">Messages from senders on the lists are marked as **Spam**, and the action that you've configured for the **Spam** filter verdict is taken on the message.</span></span> <span data-ttu-id="06e73-147">詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06e73-147">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="06e73-148">これらのリストの最大数は、約 1000 エントリです。</span><span class="sxs-lookup"><span data-stu-id="06e73-148">The maximum limit for these lists is approximately 1000 entries.</span></span>

## <a name="use-mail-flow-rules"></a><span data-ttu-id="06e73-149">メール フロー ルールを使用する</span><span class="sxs-lookup"><span data-stu-id="06e73-149">Use mail flow rules</span></span>

<span data-ttu-id="06e73-150">特定のユーザーまたは組織全体に送信されるメッセージをブロックする必要がある場合は、メール フロー ルールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="06e73-150">If you need to block messages that are sent to specific users or across the entire organization, you can use mail flow rules.</span></span> <span data-ttu-id="06e73-151">メール フロー ルールは、望ましくないメッセージ内のキーワードや他のプロパティも検索できるので、受信拒否リストや受信拒否リストよりも柔軟です。</span><span class="sxs-lookup"><span data-stu-id="06e73-151">Mail flow rules are more flexible than block sender lists or blocked sender domain lists because they can also look for keywords or other properties in the unwanted messages.</span></span>

<span data-ttu-id="06e73-152">メッセージの識別に使用する条件や例外に関係なく、メッセージの SCL (Spam Confidence Level) を 9 に設定するアクションを構成して、メッセージを **信頼** 度の高いスパムとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="06e73-152">Regardless of the conditions or exceptions that you use to identify the messages, you configure the action to set the spam confidence level (SCL) of the message to 9, which marks the message a **High confidence spam**.</span></span> <span data-ttu-id="06e73-153">詳細については、「メール フロー ルール [を使用してメッセージの SCL を設定する」を参照してください](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="06e73-153">For more information, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06e73-154">非常に積極的なルールを作成するのは簡単なので、非常に具体的な条件を使用してブロックするメッセージのみを識別することが重要です。</span><span class="sxs-lookup"><span data-stu-id="06e73-154">It's easy to create rules that are *overly* aggressive, so it's important that you identify only the messages you want to block using using very specific criteria.</span></span> <span data-ttu-id="06e73-155">また、ルールの監査を有効にし、ルールの結果をテストして、すべてが期待通り動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06e73-155">Also, be sure to enable auditing on the rule and test the results of the rule to ensure everything works as expected.</span></span>

## <a name="use-the-ip-block-list"></a><span data-ttu-id="06e73-156">IP ブロック リストを使用する</span><span class="sxs-lookup"><span data-stu-id="06e73-156">Use the IP Block List</span></span>

<span data-ttu-id="06e73-157">他のオプションの 1 つを使用して送信者をブロックできない場合にのみ、接続フィルター ポリシーで IP ブロック一覧を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06e73-157">When it's not possible to use one of the other options to block a sender, *only then* should you use the IP Block List in the connection filter policy.</span></span> <span data-ttu-id="06e73-158">詳細については、「[接続フィルター ポリシーを構成する](configure-the-connection-filter-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06e73-158">For more information, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> <span data-ttu-id="06e73-159">ブロックする IP の数を最小限に抑え、IP アドレス範囲全体をブロックすることが *推奨* されません。</span><span class="sxs-lookup"><span data-stu-id="06e73-159">It's important to keep the number of blocked IPs to a minimum, so blocking entire IP address ranges is *not* recommended.</span></span>

<span data-ttu-id="06e73-160">コンシューマーサービス (outlook.com など) または共有インフラストラクチャに属する IP アドレス範囲を追加しないようにし、定期的なメンテナンスの一環として、ブロックする IP アドレスの一覧を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06e73-160">You should *especially* avoid adding IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures, and also ensure that you review the list of blocked IP addresses as part of regular maintenance.</span></span>
