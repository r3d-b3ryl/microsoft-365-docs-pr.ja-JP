---
title: バルク メール業者の差出人セーフ リストを管理する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: '差出人セーフ リストを使用する場合は、Exchange Online Protection (EOP) と Outlook で処理が異なることを認識しておく必要があります。サービスでは RFC 5321.MailFrom アドレスと RFC 5322.From アドレスを検査することによって信頼できる差出人とドメインを尊重するのに対して、Outlook では RFC 5322.From アドレスをユーザーの差出人セーフ リストに追加します (注 : サービスは、ブロックする差出人とドメインについては、5321.MailFrom アドレスと 5322.From アドレスの両方を検査します)。'
ms.openlocfilehash: 2dcfd73cc987290bbc8ca8111580a374216a843e
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970303"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="2f42c-105">バルク メーラーの差出人セーフ リストを管理する</span><span class="sxs-lookup"><span data-stu-id="2f42c-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="2f42c-106">差出人セーフリストを使用する場合は、Exchange Online Protection (EOP) と Outlook が異なる方法で処理することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2f42c-106">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently.</span></span> <span data-ttu-id="2f42c-107">Office 365 サービスは、 `RFC 5321.MailFrom`アドレスと`RFC 5322.From`アドレスを調べて、安全な送信者とドメインを尊重します`RFC 5322.From`が、Outlook はユーザーの差出人セーフリストにアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="2f42c-107">The Office 365 service respects safe senders and domains by inspecting the `RFC 5321.MailFrom` address and the `RFC 5322.From` address, while Outlook adds the `RFC 5322.From` address to a user's safe sender list.</span></span> <span data-ttu-id="2f42c-108">(注: サービスは、ブロックさ`5321.MailFrom`れた`5322.From`送信者とドメインのアドレスとアドレスの両方を調べます。)</span><span class="sxs-lookup"><span data-stu-id="2f42c-108">(Note: The service inspects both the `5321.MailFrom` address and `5322.From` address for blocked senders and domains.)</span></span>

<span data-ttu-id="2f42c-109">と`SMTP MAIL FROM` `RFC 5321.MailFrom address`いうアドレスは、SPF チェックの実行に使用される電子メールアドレス、およびメールを配信できない場合は、バウンスメッセージが配信されるパスのことです。</span><span class="sxs-lookup"><span data-stu-id="2f42c-109">The `SMTP MAIL FROM` address, otherwise known as the `RFC 5321.MailFrom address`, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered.</span></span> <span data-ttu-id="2f42c-110">この電子メールアドレスは、 `Return-Path`既定でメッセージヘッダーに配置されていますが、送信者は別`Return-Path`のアドレスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2f42c-110">It's this email address that is placed into the `Return-Path` in the message headers by default, though it's possible for the sender to designate a different `Return-Path` address.</span></span>

<span data-ttu-id="2f42c-111">メッセージ`From:`ヘッダー内のアドレス ( `RFC 5322.From`アドレスとも呼ばれます) は、Outlook などのメールクライアントに表示される電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="2f42c-111">The `From:` address in the message headers, otherwise known as the `RFC 5322.From` address, is the email address that is displayed in the mail client such as Outlook.</span></span>

<span data-ttu-id="2f42c-112">多くの時間、 `5321.MailFrom`および`5322.From`アドレスは同じです。</span><span class="sxs-lookup"><span data-stu-id="2f42c-112">Much of the time, the `5321.MailFrom` and `5322.From` addresses are the same.</span></span> <span data-ttu-id="2f42c-113">このことは、人間同士のコミュニケーションではよく見られることです。</span><span class="sxs-lookup"><span data-stu-id="2f42c-113">This is typical for person-to-person communication.</span></span> <span data-ttu-id="2f42c-114">ただし、他のユーザーに代わって電子メールが送信される場合は、これらのアドレスが異なるのが普通です。</span><span class="sxs-lookup"><span data-stu-id="2f42c-114">However, when email is sent on behalf of someone else, the addresses are frequently different.</span></span> <span data-ttu-id="2f42c-115">大部分のバルク メール メッセージでは、ほとんどの場合にそのようになります。</span><span class="sxs-lookup"><span data-stu-id="2f42c-115">This usually happens most often for bulk email messages.</span></span>

<span data-ttu-id="2f42c-116">たとえば、青色の Yonder 航空が、青木社長の旅行を採用して、電子メール広告を送信しているとします。</span><span class="sxs-lookup"><span data-stu-id="2f42c-116">For example, suppose that Blue Yonder Airlines has hired Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="2f42c-117">受信トレイに入るメッセージの差出人は blueyonder@news.blueyonderairlines.com です。</span><span class="sxs-lookup"><span data-stu-id="2f42c-117">You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com.</span></span> <span data-ttu-id="2f42c-118">この例では次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="2f42c-118">In this example:</span></span>

- <span data-ttu-id="2f42c-119">`5321.MailFrom`アドレスは blueyonder.airlines@margiestravel.com です。</span><span class="sxs-lookup"><span data-stu-id="2f42c-119">The `5321.MailFrom` address is blueyonder.airlines@margiestravel.com.</span></span>

- <span data-ttu-id="2f42c-120">`5322.From`アドレスは blueyonder@news.blueyonderairlines.com で、Outlook に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f42c-120">The `5322.From` address is blueyonder@news.blueyonderairlines.com, which is what you'll see in Outlook.</span></span>

<span data-ttu-id="2f42c-121">このメッセージがフィルター処理されないようにするには、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="2f42c-121">To prevent this message from being filtered, you can:</span></span>

- <span data-ttu-id="2f42c-122">[**ユーザーとして**] `RFC 5322.From` : アドレスを Outlook の信頼できる差出人として追加します。</span><span class="sxs-lookup"><span data-stu-id="2f42c-122">**As a user**: Add the `RFC 5322.From` address as a Safe Sender in Outlook.</span></span>

- <span data-ttu-id="2f42c-123">**管理者として**:[メールフロールール](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365)(トランスポートルールとも呼ばれます) を設定します。</span><span class="sxs-lookup"><span data-stu-id="2f42c-123">**As an admin**: Set up a [mail flow rule](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (also known as a transport rule).</span></span>
