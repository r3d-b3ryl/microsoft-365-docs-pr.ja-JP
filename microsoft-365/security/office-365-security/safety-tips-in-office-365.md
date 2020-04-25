---
title: メール メッセージの安全性に関するヒント
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/6/2016
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: EOP およびスパムフィルターによってフィルター処理された電子メールメッセージの安全のヒントを紹介します。
ms.openlocfilehash: c7d7e6819e1374fd941d6eeb992ecf63726d4127
ms.sourcegitcommit: 481fb95d8b80cf2102a9c73b21e7effa79e594e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2020
ms.locfileid: "43809021"
---
# <a name="safety-tips-in-email-messages"></a><span data-ttu-id="41cc4-103">メール メッセージの安全性に関するヒント</span><span class="sxs-lookup"><span data-stu-id="41cc4-103">Safety tips in email messages</span></span>

<span data-ttu-id="41cc4-104">Exchange Online Protection (EOP) と Microsoft 365 は、スパム、フィッシング、マルウェアの防止を強化します。</span><span class="sxs-lookup"><span data-stu-id="41cc4-104">Exchange Online Protection (EOP) and Microsoft 365 protect you with spam, phishing, and malware prevention.</span></span> <span data-ttu-id="41cc4-105">今日では、これらの攻撃の一部は正当なものであることがよく細工されています。</span><span class="sxs-lookup"><span data-stu-id="41cc4-105">Today, some of these attacks are so well crafted that they look legitimate.</span></span> <span data-ttu-id="41cc4-106">[迷惑メール] フォルダーにメッセージを送信するだけでは不十分なわけではありません。</span><span class="sxs-lookup"><span data-stu-id="41cc4-106">Sending messages to the Junk Email folder isn't always enough.</span></span> <span data-ttu-id="41cc4-107">これで、Outlook または web 上の Outlook または電子メールクライアントで電子メールを確認すると、EOP によって送信者が自動的に確認され、安全なヒントが電子メールの上部に追加されます。</span><span class="sxs-lookup"><span data-stu-id="41cc4-107">Now, when you check your email in Outlook or Outlook on the web or any email client, EOP automatically checks the sender and adds a safety tip to the top of the email.</span></span>

<span data-ttu-id="41cc4-108">Outlook の安全のヒントは、安全のヒントが開かれ、メッセージ本文に直接挿入されるため、使用している Outlook のバージョンには依存しません。</span><span class="sxs-lookup"><span data-stu-id="41cc4-108">Safety tips in Outlook do not depend on what version of Outlook you're using because the safety tip is cracked open and inserted directly into the message body.</span></span> <span data-ttu-id="41cc4-109">これは、使用しているすべての電子メールクライアントに安全なヒントが表示されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="41cc4-109">This means that the safety tip will show up in whatever email client you're using.</span></span> <span data-ttu-id="41cc4-110">これは電子メールフィルターレベルで行われ、メールクライアントレベルでは表示されないので、どのバージョンの Outlook でも表示されるだけでなく、どのような電子メールクライアントにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="41cc4-110">It's done at the email filter level and not rendered at the mail client level, so not only does it show up in any version of Outlook, it also shows up in any email client.</span></span>

<span data-ttu-id="41cc4-111">安全性に関するヒント (色分けされたメッセージ) は、潜在的に有害なメッセージに関する警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="41cc4-111">The safety tip—a color-coded message—will warn you about potentially harmful messages.</span></span> <span data-ttu-id="41cc4-112">受信トレイ内のほとんどのメッセージには安全なヒントがありません。</span><span class="sxs-lookup"><span data-stu-id="41cc4-112">Most messages in your inbox won't have a safety tip.</span></span> <span data-ttu-id="41cc4-113">スパム、フィッシング、およびマルウェア攻撃を防止するために必要な情報が EOP と Microsoft 365 にある場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="41cc4-113">You'll only see them when EOP and Microsoft 365 have information you need to help prevent spam, phishing, and malware attacks.</span></span> <span data-ttu-id="41cc4-114">受信トレイに安全のヒントが表示される場合は、次の例を使用して、安全に関するヒントの種類について詳しく調べることができます。</span><span class="sxs-lookup"><span data-stu-id="41cc4-114">If safety tips do show up on in your inbox, you can use the following examples to learn more about each type of safety tip.</span></span>

- <span data-ttu-id="41cc4-115">疑わしいメール (赤安全ヒント)。</span><span class="sxs-lookup"><span data-stu-id="41cc4-115">Suspicious mail (red safety tip).</span></span>

    ![赤の安全ヒントを示すスクリーンショット。](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    <span data-ttu-id="41cc4-117">電子メールの赤の安全ヒントは、受信したメッセージに疑わしいものが含まれていることを意味します (フィッシング詐欺など)。</span><span class="sxs-lookup"><span data-stu-id="41cc4-117">A red safety tip in an email means that the message you received contains something suspicious, such as a phishing scam.</span></span> <span data-ttu-id="41cc4-118">この種類の電子メールメッセージは、受信トレイからは開かずに削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="41cc4-118">We recommend that you delete this kind of email message from your inbox without opening it.</span></span>

- <span data-ttu-id="41cc4-119">スパム (黄色の安全性ヒント)。</span><span class="sxs-lookup"><span data-stu-id="41cc4-119">Spam (yellow safety tip).</span></span>

    ![黄色の安全性ヒントを示すスクリーンショット。](../../media/793c9265-ea44-48fd-a98f-804fadd4163b.png)

    <span data-ttu-id="41cc4-121">電子メールの黄色の安全ヒントは、メッセージがスパムとしてマークされていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="41cc4-121">A yellow safety tip in an email means that the message has been marked as spam.</span></span> <span data-ttu-id="41cc4-122">メッセージの送信者を認識して信頼していない場合は、添付ファイルや画像をダウンロードしないで、メッセージ内のリンクをクリックしないでください。</span><span class="sxs-lookup"><span data-stu-id="41cc4-122">If you don't recognize and trust the sender of the message, don't download any attachments or pictures and don't click any links in the message.</span></span> <span data-ttu-id="41cc4-123">Outlook on the web では、迷惑メールアイテムの黄色のバーにある [**スパムではない**] をクリックして、メッセージを受信トレイに移動できます。</span><span class="sxs-lookup"><span data-stu-id="41cc4-123">In Outlook on the web, you can click **It's not spam** in the yellow bar of a junk mail item to move the message to your inbox.</span></span> <span data-ttu-id="41cc4-124">受信トレイに配信されたメッセージに黄色の安全ヒントが表示される場合は、迷惑メールフォルダーへのスパムの移動を無効にしている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="41cc4-124">If the yellow safety tip appears on a message that was delivered to your inbox, it's probably there because you've disabled moving spam to your Junk Email folder.</span></span>

- <span data-ttu-id="41cc4-125">安全なメール (緑色の安全ヒント)。</span><span class="sxs-lookup"><span data-stu-id="41cc4-125">Safe mail (green safety tip).</span></span>

    ![緑の安全ヒントを示すスクリーンショット。](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    <span data-ttu-id="41cc4-127">安全でないメッセージに加えて、信頼できる送信者からの有効なメッセージについても、緑色の安全ヒントを示しています。</span><span class="sxs-lookup"><span data-stu-id="41cc4-127">In addition to unsafe messages, we'll also tell you about valid messages from senders we trust with a green safety tip.</span></span> <span data-ttu-id="41cc4-128">電子メールのグリーンセーフヒントは、メッセージの送信者を確認し、安全であることを確認したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="41cc4-128">A green safety tip in an email means that we checked the sender of the message and verified that it's safe.</span></span> <span data-ttu-id="41cc4-129">Microsoft では、多くの場合、頻繁にスプーフィングまたは偽装される金融機関やその他の信頼できる差出人のリストを保持しています。</span><span class="sxs-lookup"><span data-stu-id="41cc4-129">Microsoft maintains this list of trusted senders which includes financial organizations and others that are frequently spoofed or impersonated.</span></span>

- <span data-ttu-id="41cc4-130">フィルター処理なしのメール (灰色の安全ヒント)。</span><span class="sxs-lookup"><span data-stu-id="41cc4-130">Unfiltered mail (gray safety tip).</span></span>

    ![灰色の安全なヒントを示すスクリーンショット。](../../media/c4d0cf8f-08e9-4c84-beee-1d9e0b022e0a.png)

    <span data-ttu-id="41cc4-132">また、差出人セーフリストにある送信者からのメールの確認や、フィルターをバイパスするメールフロールールがある場合にも、メールのチェックをスキップしたことについてもお知らせします。</span><span class="sxs-lookup"><span data-stu-id="41cc4-132">We'll also tell you when we skipped checking a mail because it's from a sender you trust on your Safe Senders list or if a mail flow rule exists to bypass filtering.</span></span>

    <span data-ttu-id="41cc4-133">また、外部画像がブロックされている場合、つまりメッセージが受信トレイにあり、スパムではないが、ダウンロードしていない外部画像が含まれている場合にも、灰色の安全なヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41cc4-133">The gray safety tip also shows up when external images are blocked, that is, the message is in your inbox and doesn't appear to be spam, but contains external images that you haven't opted to download.</span></span>
    

## <a name="working-with-safety-tips"></a><span data-ttu-id="41cc4-134">安全に関するヒントの使用</span><span class="sxs-lookup"><span data-stu-id="41cc4-134">Working with safety tips</span></span>

<span data-ttu-id="41cc4-135">セキュリティヒントは、すべてのメッセージが受信するわけではありませんが、Outlook on the web では常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="41cc4-135">Safety tips are always enabled for Outlook on the web, even though not every message will receive one.</span></span> <span data-ttu-id="41cc4-136">管理者は、Outlook などの他の電子メールクライアントに対して安全のヒントを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="41cc4-136">Admins can turn safety tips off for other email clients such as Outlook.</span></span> <span data-ttu-id="41cc4-137">詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41cc4-137">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="41cc4-138">EOP がメッセージを分類した方法 (つまり、メッセージがスパムではないか、またはスパムとしてマークされている必要がある) に同意しない場合は、Microsoft にメッセージを送信して、快適な操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="41cc4-138">If you disagree with how EOP categorized a message (that is, the message is not spam or it should have been marked as spam), you can submit the messages to Microsoft for analysis to help make your experience better.</span></span> <span data-ttu-id="41cc4-139">手順については、「 [Microsoft にメッセージとファイルを報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41cc4-139">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="41cc4-140">また、安全性ヒントの [フィードバック] リンクをクリックして、ご意見を Microsoft に直接送信し、改善を支援することもできます。</span><span class="sxs-lookup"><span data-stu-id="41cc4-140">You can also click on the Feedback link in the safety tip to submit comments directly to Microsoft to help us improve.</span></span>
