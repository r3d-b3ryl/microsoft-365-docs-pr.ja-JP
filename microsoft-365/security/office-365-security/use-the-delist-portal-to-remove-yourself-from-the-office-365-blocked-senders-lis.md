---
title: 受信拒否リストから自分自身を削除する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: この記事では、リストから除外ポータルを使用して、Microsoft 365 の受信拒否リストから自分自身を削除する方法について説明します。
ms.openlocfilehash: 0c87d467db004a50502402b05eb0fa3283aa46c5
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614764"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="82d6a-103">無効化ポータルを使って、受信拒否リストから自分自身を削除する</span><span class="sxs-lookup"><span data-stu-id="82d6a-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="82d6a-104">Microsoft 365 に電子メールアドレスがある受信者に電子メールを送信しようとすると、エラーメッセージが表示されますか。</span><span class="sxs-lookup"><span data-stu-id="82d6a-104">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="82d6a-105">エラーメッセージを受信しないようにする必要がある場合は、リストから除外ポータルを使用して、受信拒否リストから自分自身を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="82d6a-105">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="82d6a-106">受信拒否リストとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="82d6a-106">What is the blocked senders list?</span></span>

<span data-ttu-id="82d6a-107">Microsoft は、受信拒否リストを使って、スパム、スプーフィング、フィッシング攻撃からお客様を保護しています。</span><span class="sxs-lookup"><span data-stu-id="82d6a-107">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="82d6a-108">メールサーバーの IP アドレス (メールサーバーがインターネット上で自分自身を識別するために使用するアドレス) は、さまざまな理由の1つとして、Microsoft 365 に対する潜在的な脅威としてタグ付けされました。</span><span class="sxs-lookup"><span data-stu-id="82d6a-108">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="82d6a-109">Microsoft 365 によって IP アドレスが一覧に追加されると、その ip アドレスとお客様との間のすべての通信がデータセンターによって妨げられます。</span><span class="sxs-lookup"><span data-stu-id="82d6a-109">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="82d6a-110">メール メッセージに対して、次のようなエラーが含まれた応答を受信する場合、お客様は受信拒否リストに追加されています。</span><span class="sxs-lookup"><span data-stu-id="82d6a-110">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="82d6a-111">550 5.7.606-649 アクセス拒否、禁止された送信 IP [_ip address_]、このリストからの削除を要求するには、にアクセスして <https://sender.office.com/> 、指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="82d6a-111">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit <https://sender.office.com/> and follow the directions.</span></span> <span data-ttu-id="82d6a-112">詳細については、「 [Exchange Online のメール配信不能レポート](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82d6a-112">For more information see [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="82d6a-113">ここで、 _IP address_ は、メール サーバーを稼働しているコンピューターの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="82d6a-113">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="82d6a-114">リストから除外ポータルを使用して、受信拒否リストから自分自身を削除するには</span><span class="sxs-lookup"><span data-stu-id="82d6a-114">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="82d6a-115">Web ブラウザーで、<https://sender.office.com> に移動します。</span><span class="sxs-lookup"><span data-stu-id="82d6a-115">In a web browser, go to <https://sender.office.com>.</span></span>

2. <span data-ttu-id="82d6a-p104">ページ上の指示に従います。エラー メッセージを受信したメール アドレス、エラー メッセージで特定されている IP アドレスを使っていることを確認してください。1 回のアクセスにつき、1 つのメール アドレス、1 つの IP アドレスのみ入力できます。</span><span class="sxs-lookup"><span data-stu-id="82d6a-p104">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="82d6a-119">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82d6a-119">Click **Submit**.</span></span>

    <span data-ttu-id="82d6a-120">ポータルは、指定したメール アドレスにメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="82d6a-120">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="82d6a-121">電子メールは次のようになります。リストから除外 ![ ポータルを通じて要求を送信したときに受信された電子メールのスクリーンショット](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="82d6a-121">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="82d6a-122">リストから除外のポータルから受信したメールの中にある確認のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="82d6a-122">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="82d6a-123">これで、リストから除外のポータルに戻ります。</span><span class="sxs-lookup"><span data-stu-id="82d6a-123">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="82d6a-124">リストから除外のポータルで **[IP をリストから除外]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82d6a-124">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="82d6a-125">受信拒否リストから IP アドレスが削除されると、その IP アドレスからの電子メールメッセージは、Microsoft 365 を使用している受信者に配信されます。</span><span class="sxs-lookup"><span data-stu-id="82d6a-125">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="82d6a-126">そのため、その IP アドレスから送信された電子メールが不適切または悪意のあるものにならないようにしてください。それ以外の場合は、IP アドレスが再度ブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="82d6a-126">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="82d6a-127">最大24時間かかる場合があります。制限が削除されるまでに、結果が大幅に異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="82d6a-127">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="82d6a-128">IP がブロックされないようにするには、「 [Create safe sender lists IN EOP](create-safe-sender-lists-in-office-365.md) and [Outbound SPAM protection in EOP](outbound-spam-controls.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82d6a-128">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span></span>
