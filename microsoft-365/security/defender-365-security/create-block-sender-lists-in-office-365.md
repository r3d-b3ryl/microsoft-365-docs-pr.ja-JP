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
ms.openlocfilehash: a9ee0a026e33bf07bb929607b8eed9078d0b6e4c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065323"
---
# <a name="create-blocked-sender-lists-in-eop"></a><span data-ttu-id="a051d-103">EOP で受信拒否リストを作成する</span><span class="sxs-lookup"><span data-stu-id="a051d-103">Create blocked sender lists in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a051d-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="a051d-104">**Applies to**</span></span>
- [<span data-ttu-id="a051d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a051d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a051d-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="a051d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a051d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a051d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a051d-108">Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない Microsoft 365 組織では、EOP は不要な送信者からの電子メールをブロックする複数の方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="a051d-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers multiple ways of blocking email from unwanted senders.</span></span> <span data-ttu-id="a051d-109">これらのオプションには、スパム対策ポリシーの Outlook Blocked Senders、ブロックされた送信者リスト、またはブロックされたドメイン リスト、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる)、および IP 禁止一覧 (接続フィルター) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a051d-109">These options include Outlook Blocked Senders, blocked sender lists or blocked domain lists in anti-spam policies, Exchange mail flow rules (also known as transport rules), and the IP Block List (connection filtering).</span></span> <span data-ttu-id="a051d-110">まとめて、これらのオプションは、受信拒否リスト _と考えても良い。_</span><span class="sxs-lookup"><span data-stu-id="a051d-110">Collectively, you can think of these options as _blocked sender lists_.</span></span>

<span data-ttu-id="a051d-111">送信者をブロックする最適な方法は、影響の範囲によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a051d-111">The best method to block senders varies on the scope of impact.</span></span> <span data-ttu-id="a051d-112">1 人のユーザーの場合、適切なソリューションは Outlook の受信拒否送信者である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a051d-112">For a single user, the right solution could be Outlook Blocked Senders.</span></span> <span data-ttu-id="a051d-113">多くのユーザーの場合、他のオプションの 1 つが適切です。</span><span class="sxs-lookup"><span data-stu-id="a051d-113">For many users, one of the other options would be more appropriate.</span></span> <span data-ttu-id="a051d-114">次のオプションは、影響範囲と幅の両方でランク付けされます。</span><span class="sxs-lookup"><span data-stu-id="a051d-114">The following options are ranked by both impact scope and breadth.</span></span> <span data-ttu-id="a051d-115">リストは狭い範囲から広い範囲に行きますが、完全な推奨事項の *詳細* をお読みください。</span><span class="sxs-lookup"><span data-stu-id="a051d-115">The list goes from narrow to broad, but *read the specifics* for full recommendations.</span></span>

1. <span data-ttu-id="a051d-116">Outlook の受信拒否送信者 (各メールボックスに格納されている受信拒否リスト)</span><span class="sxs-lookup"><span data-stu-id="a051d-116">Outlook Blocked Senders (the Blocked Senders list that's stored in each mailbox)</span></span>

2. <span data-ttu-id="a051d-117">受信拒否リストまたはブロックされたドメイン リスト (スパム対策ポリシー)</span><span class="sxs-lookup"><span data-stu-id="a051d-117">Blocked sender lists or blocked domain lists (anti-spam policies)</span></span>

3. <span data-ttu-id="a051d-118">メール フロー ルール</span><span class="sxs-lookup"><span data-stu-id="a051d-118">Mail flow rules</span></span>

4. <span data-ttu-id="a051d-119">IP ブロック リスト (接続フィルター)</span><span class="sxs-lookup"><span data-stu-id="a051d-119">The IP Block List (connection filtering)</span></span>

> [!NOTE]
> <span data-ttu-id="a051d-120">組織全体のブロック設定を使用して誤検知 (スパムの見逃し) に対処することもできますが、分析のためにそれらのメッセージを Microsoft に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a051d-120">While you can use organization-wide block settings to address false negatives (missed spam), you should also submit those messages to Microsoft for analysis.</span></span> <span data-ttu-id="a051d-121">ブロック リストを使用して false negatives を管理すると、管理上のオーバーヘッドが大幅に増加します。</span><span class="sxs-lookup"><span data-stu-id="a051d-121">Managing false negatives by using block lists significantly increases your administrative overhead.</span></span> <span data-ttu-id="a051d-122">ブロック リストを使用して見逃したスパムをそらしている場合は、「メッセージとファイルを [Microsoft](report-junk-email-messages-to-microsoft.md) に報告する」を準備した状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="a051d-122">If you use block lists to deflect missed spam, you need to keep the topic [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md) at the ready.</span></span>

<span data-ttu-id="a051d-123">これに対し、差出人セーフ リストを使用して特定のソースからのメールを常に許可するオプション _もいくつか用意されています_。</span><span class="sxs-lookup"><span data-stu-id="a051d-123">In contrast, you also have several options to always allow email from specific sources using _safe sender lists_.</span></span> <span data-ttu-id="a051d-124">詳細については、「[信頼できる差出人リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a051d-124">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="email-message-basics"></a><span data-ttu-id="a051d-125">電子メール メッセージの基本</span><span class="sxs-lookup"><span data-stu-id="a051d-125">Email message basics</span></span>

<span data-ttu-id="a051d-126">標準的な SMTP 電子メール メッセージは、*メッセージ エンベロープ* とメッセージのコンテンツで構成されます。</span><span class="sxs-lookup"><span data-stu-id="a051d-126">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="a051d-127">メッセージ エンベロープには、SMTP サーバー間でメッセージを送信および配信するために必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a051d-127">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="a051d-128">メッセージのコンテンツには、総称して "*メッセージ ヘッダー*" と呼ばれるメッセージ ヘッダー フィールドと、メッセージ本文があります。</span><span class="sxs-lookup"><span data-stu-id="a051d-128">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="a051d-129">メッセージ エンベロープは RFC 5321 で説明され、メッセージ ヘッダーは RFC 5322 で説明されています。</span><span class="sxs-lookup"><span data-stu-id="a051d-129">The message envelope is described in RFC 5321, and the message header is described in RFC 5322.</span></span> <span data-ttu-id="a051d-130">受信者は、メッセージ送信プロセスによって生成され、実際にはメッセージの一部ではないので、実際のメッセージ エンベロープは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a051d-130">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="a051d-131">アドレス (MAIL FROM アドレス、P1 送信者、封筒送信者とも呼ばれる) は、メッセージの SMTP 送信で使用される電子メール `5321.MailFrom` アドレスです。 </span><span class="sxs-lookup"><span data-stu-id="a051d-131">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="a051d-132">この電子メール アドレスは、通常、メッセージ ヘッダーの **Return-Path** ヘッダー フィールドに記録されます (ただし、送信者が別の **Return-Path** 電子メール アドレスを指定することもできます)。</span><span class="sxs-lookup"><span data-stu-id="a051d-132">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span> <span data-ttu-id="a051d-133">メッセージを配信できない場合は、配信不可レポート (NDR またはバウンス メッセージとも呼ばれる) の受信者です。</span><span class="sxs-lookup"><span data-stu-id="a051d-133">If the message can't be delivered, it's the recipient for the non-delivery report (also known as an NDR or bounce message).</span></span>

- <span data-ttu-id="a051d-134">(From アドレスまたは P2 送信者とも呼ばれる) は、[差出人] ヘッダー フィールドの電子メール アドレスであり、電子メール クライアントに表示される送信者の電子メール アドレス `5322.From` です。  </span><span class="sxs-lookup"><span data-stu-id="a051d-134">The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span>

<span data-ttu-id="a051d-135">多くの場合、 `5321.MailFrom` アドレス `5322.From` とアドレスは同じです (対人通信)。</span><span class="sxs-lookup"><span data-stu-id="a051d-135">Frequently, the `5321.MailFrom` and `5322.From` addresses are the same (person-to-person communication).</span></span> <span data-ttu-id="a051d-136">ただし、他のユーザーに代わって電子メールが送信される場合、アドレスは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a051d-136">However, when email is sent on behalf of someone else, the addresses can be different.</span></span>

<span data-ttu-id="a051d-137">EOP のスパム対策ポリシーの送信者リストとブロックされたドメイン リストは、アドレスとアドレスの両方を `5321.MailFrom` 検査 `5322.From` します。</span><span class="sxs-lookup"><span data-stu-id="a051d-137">Blocked sender lists and blocked domain lists in anti-spam policies in EOP inspect both the `5321.MailFrom` and `5322.From` addresses.</span></span> <span data-ttu-id="a051d-138">Outlook の受信拒否送信者はアドレスのみを使用 `5322.From` します。</span><span class="sxs-lookup"><span data-stu-id="a051d-138">Outlook Blocked Senders only uses the `5322.From` address.</span></span>

## <a name="use-outlook-blocked-senders"></a><span data-ttu-id="a051d-139">Outlook の受信拒否の使用</span><span class="sxs-lookup"><span data-stu-id="a051d-139">Use Outlook Blocked Senders</span></span>

<span data-ttu-id="a051d-140">不要なメールを受信したユーザーが少ない場合、ユーザーまたは管理者はメールボックスの [送信者のブロック] リストに送信者の電子メール アドレスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="a051d-140">When only a small number of users received unwanted email, users or admins can add the sender email addresses to the Blocked Senders list in the mailbox.</span></span> <span data-ttu-id="a051d-141">手順については [、「Exchange Online メールボックスで迷惑メール設定を構成する」を参照してください](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="a051d-141">For instructions, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

<span data-ttu-id="a051d-142">ユーザーの [送信者のブロック] リストが原因でメッセージが正常にブロックされると **、X-Forefront-Antispam-Report** ヘッダー フィールドに値が含まれます `SFV:BLK` 。</span><span class="sxs-lookup"><span data-stu-id="a051d-142">When messages are successfully blocked due to a user's Blocked Senders list, the **X-Forefront-Antispam-Report** header field will contain the value `SFV:BLK`.</span></span>

> [!NOTE]
> <span data-ttu-id="a051d-143">望ましくないメッセージが評判の良い、認識可能なソースからのニュースレターである場合、電子メールからのサブスクリブ解除は、ユーザーがメッセージを受信することを停止する別のオプションです。</span><span class="sxs-lookup"><span data-stu-id="a051d-143">If the unwanted messages are newsletters from a reputable and recognizable source, unsubscribing from the email is another option to stop the user from receiving the messages.</span></span>

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a><span data-ttu-id="a051d-144">ブロックされた送信者リストまたはブロックされたドメイン リストを使用する</span><span class="sxs-lookup"><span data-stu-id="a051d-144">Use blocked sender lists or blocked domain lists</span></span>

<span data-ttu-id="a051d-145">複数のユーザーが影響を受ける場合、スコープが広くなるので、次の最適なオプションは、スパム対策ポリシーの送信者リストまたはブロックされたドメイン リストをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a051d-145">When multiple users are affected, the scope is wider, so the next best option is blocked sender lists or blocked domain lists in anti-spam policies.</span></span> <span data-ttu-id="a051d-146">リスト上の送信者からのメッセージはスパムとしてマークされ、スパム フィルターの評決用に構成したアクションがメッセージに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="a051d-146">Messages from senders on the lists are marked as **Spam**, and the action that you've configured for the **Spam** filter verdict is taken on the message.</span></span> <span data-ttu-id="a051d-147">詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a051d-147">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="a051d-148">これらのリストの最大制限は、約 1000 エントリです。</span><span class="sxs-lookup"><span data-stu-id="a051d-148">The maximum limit for these lists is approximately 1000 entries.</span></span>

## <a name="use-mail-flow-rules"></a><span data-ttu-id="a051d-149">メール フロー ルールの使用</span><span class="sxs-lookup"><span data-stu-id="a051d-149">Use mail flow rules</span></span>

<span data-ttu-id="a051d-150">特定のユーザーまたは組織全体に送信されるメッセージをブロックする必要がある場合は、メール フロー ルールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a051d-150">If you need to block messages that are sent to specific users or across the entire organization, you can use mail flow rules.</span></span> <span data-ttu-id="a051d-151">メール フロー ルールは、望ましくないメッセージ内のキーワードや他のプロパティも検索できるので、送信者リストのブロックや送信者ドメイン リストのブロックよりも柔軟です。</span><span class="sxs-lookup"><span data-stu-id="a051d-151">Mail flow rules are more flexible than block sender lists or blocked sender domain lists because they can also look for keywords or other properties in the unwanted messages.</span></span>

<span data-ttu-id="a051d-152">メッセージを識別するために使用する条件や例外に関係なく、メッセージのスパム信頼レベル (SCL) を 9 に設定するアクションを構成し、メッセージに高信頼スパムをマークします。</span><span class="sxs-lookup"><span data-stu-id="a051d-152">Regardless of the conditions or exceptions that you use to identify the messages, you configure the action to set the spam confidence level (SCL) of the message to 9, which marks the message a **High confidence spam**.</span></span> <span data-ttu-id="a051d-153">詳細については、「メール フロー ルール [を使用してメッセージの SCL を設定する」を参照してください](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="a051d-153">For more information, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a051d-154">ルールを作成するのは簡単なので、非常に具体的な条件を使用してブロックするメッセージのみを識別することが重要です。</span><span class="sxs-lookup"><span data-stu-id="a051d-154">It's easy to create rules that are *overly* aggressive, so it's important that you identify only the messages you want to block using using very specific criteria.</span></span> <span data-ttu-id="a051d-155">また、ルールの監査を有効にし、ルールの結果をテストして、すべてが期待通り動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a051d-155">Also, be sure to enable auditing on the rule and test the results of the rule to ensure everything works as expected.</span></span>

## <a name="use-the-ip-block-list"></a><span data-ttu-id="a051d-156">IP ブロック リストを使用する</span><span class="sxs-lookup"><span data-stu-id="a051d-156">Use the IP Block List</span></span>

<span data-ttu-id="a051d-157">他のオプションのいずれかを使用して送信者をブロックできない場合は、接続フィルター ポリシーでIP ブロック一覧を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a051d-157">When it's not possible to use one of the other options to block a sender, *only then* should you use the IP Block List in the connection filter policy.</span></span> <span data-ttu-id="a051d-158">詳細については、「[接続フィルター ポリシーを構成する](configure-the-connection-filter-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a051d-158">For more information, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> <span data-ttu-id="a051d-159">ブロックされた IP の数を最小限に抑え、IP アドレス範囲全体をブロックすることが *推奨* されません。</span><span class="sxs-lookup"><span data-stu-id="a051d-159">It's important to keep the number of blocked IPs to a minimum, so blocking entire IP address ranges is *not* recommended.</span></span>

<span data-ttu-id="a051d-160">特に、コンシューマー サービス (outlook.com など) や共有インフラストラクチャに属する IP アドレス範囲を追加しないようにし、定期的なメンテナンスの一環としてブロックされた IP アドレスの一覧を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a051d-160">You should *especially* avoid adding IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures, and also ensure that you review the list of blocked IP addresses as part of regular maintenance.</span></span>
