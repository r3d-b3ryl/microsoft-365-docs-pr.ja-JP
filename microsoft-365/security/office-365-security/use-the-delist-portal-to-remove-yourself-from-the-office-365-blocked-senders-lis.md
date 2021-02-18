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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: この記事では、リストから削除ポータルを使用して、Microsoft 365 の受信拒否リストから自分自身を削除する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c11fced30ef52315ecb44dda51e6825d36b57c7e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287523"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="54fb5-103">無効化ポータルを使って、受信拒否リストから自分自身を削除する</span><span class="sxs-lookup"><span data-stu-id="54fb5-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="54fb5-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="54fb5-104">**Applies to**</span></span>
- [<span data-ttu-id="54fb5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="54fb5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="54fb5-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="54fb5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="54fb5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54fb5-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="54fb5-108">Microsoft 365 のメール アドレスを持つ受信者に電子メールを送信しようとするときにエラー メッセージが表示される場合</span><span class="sxs-lookup"><span data-stu-id="54fb5-108">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="54fb5-109">エラー メッセージを受け取る必要はないと思う場合は、リストから削除ポータルを使用して、受信拒否リストから自分自身を削除できます。</span><span class="sxs-lookup"><span data-stu-id="54fb5-109">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="54fb5-110">受信拒否リストとは</span><span class="sxs-lookup"><span data-stu-id="54fb5-110">What is the blocked senders list?</span></span>

<span data-ttu-id="54fb5-111">Microsoft は、受信拒否リストを使って、スパム、スプーフィング、フィッシング攻撃からお客様を保護しています。</span><span class="sxs-lookup"><span data-stu-id="54fb5-111">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="54fb5-112">メール サーバーの IP アドレス、つまり、メール サーバーがインターネット上で自身を識別するために使用するアドレスは、さまざまな理由から Microsoft 365 に対する潜在的な脅威としてタグ付けされています。</span><span class="sxs-lookup"><span data-stu-id="54fb5-112">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="54fb5-113">Microsoft 365 が IP アドレスをリストに追加すると、データセンターを通じて IP アドレスとすべてのお客様との間のすべての通信が防止されます。</span><span class="sxs-lookup"><span data-stu-id="54fb5-113">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="54fb5-114">メール メッセージに対して、次のようなエラーが含まれた応答を受信する場合、お客様は受信拒否リストに追加されています。</span><span class="sxs-lookup"><span data-stu-id="54fb5-114">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="54fb5-115">550 5.7.606-649 アクセスが拒否され、IP [ IP アドレス] の送信 _が禁止_ されました。この一覧からの削除を要求するには、指示に従 <https://sender.office.com/> ってアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="54fb5-115">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit <https://sender.office.com/> and follow the directions.</span></span> <span data-ttu-id="54fb5-116">詳細については [、「Exchange Online のメール配信不可レポート」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="54fb5-116">For more information see [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="54fb5-117">ここで、 _IP address_ は、メール サーバーを稼働しているコンピューターの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="54fb5-117">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="54fb5-118">リストから削除ポータルを使用して、受信拒否リストから自分自身を削除するには</span><span class="sxs-lookup"><span data-stu-id="54fb5-118">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="54fb5-119">Web ブラウザーで、<https://sender.office.com> に移動します。</span><span class="sxs-lookup"><span data-stu-id="54fb5-119">In a web browser, go to <https://sender.office.com>.</span></span>

2. <span data-ttu-id="54fb5-p104">ページ上の指示に従います。エラー メッセージを受信したメール アドレス、エラー メッセージで特定されている IP アドレスを使っていることを確認してください。1 回のアクセスにつき、1 つのメール アドレス、1 つの IP アドレスのみ入力できます。</span><span class="sxs-lookup"><span data-stu-id="54fb5-p104">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="54fb5-123">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54fb5-123">Click **Submit**.</span></span>

    <span data-ttu-id="54fb5-124">ポータルは、指定したメール アドレスにメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="54fb5-124">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="54fb5-125">メールは次のようになります:リストから要求を送信すると受信したメールの ![ スクリーンショット](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="54fb5-125">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="54fb5-126">リストから除外のポータルから受信したメールの中にある確認のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="54fb5-126">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="54fb5-127">これで、リストから除外のポータルに戻ります。</span><span class="sxs-lookup"><span data-stu-id="54fb5-127">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="54fb5-128">リストから除外のポータルで **[IP をリストから除外]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54fb5-128">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="54fb5-129">IP アドレスが受信拒否リストから削除されると、その IP アドレスからの電子メール メッセージは、Microsoft 365 を使用する受信者に配信されます。</span><span class="sxs-lookup"><span data-stu-id="54fb5-129">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="54fb5-130">そのため、その IP アドレスから送信された電子メールが不正または悪意のあるものにならないと確信してください。そうしないと、IP アドレスが再度ブロックされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="54fb5-130">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="54fb5-131">最大 24 時間かかる場合や、制限が解除される前に結果が大きく異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="54fb5-131">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="54fb5-132">IP [がブロックされるのを防ぐには、「EOP](create-safe-sender-lists-in-office-365.md) で差出人セーフ リストを作成する」および [「EOP](outbound-spam-controls.md) での送信スパム保護」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54fb5-132">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span></span>
