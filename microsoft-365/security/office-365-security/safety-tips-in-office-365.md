---
title: Office 365 でのメール メッセージの安全性に関するヒント
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
description: EOP および Office 365 スパムフィルターによってフィルター処理された電子メールメッセージの安全のヒントを紹介します。
ms.openlocfilehash: 3e4e645c6ac0285d9d6fff43b301f1f5c61a90e3
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032818"
---
# <a name="safety-tips-in-email-messages-in-office-365"></a><span data-ttu-id="e74d6-103">Office 365 でのメール メッセージの安全性に関するヒント</span><span class="sxs-lookup"><span data-stu-id="e74d6-103">Safety tips in email messages in Office 365</span></span>

<span data-ttu-id="e74d6-104">Exchange Online Protection (EOP) と Office 365 は、スパム、フィッシング、マルウェアの防止を強化します。</span><span class="sxs-lookup"><span data-stu-id="e74d6-104">Exchange Online Protection (EOP) and Office 365 protect you with spam, phishing, and malware prevention.</span></span> <span data-ttu-id="e74d6-105">今日では、これらの攻撃の一部は正当なものであることがよく細工されています。</span><span class="sxs-lookup"><span data-stu-id="e74d6-105">Today, some of these attacks are so well crafted that they look legitimate.</span></span> <span data-ttu-id="e74d6-106">[迷惑メール] フォルダーにメッセージを送信するだけでは不十分なわけではありません。</span><span class="sxs-lookup"><span data-stu-id="e74d6-106">Sending messages to the Junk Email folder isn't always enough.</span></span> <span data-ttu-id="e74d6-107">これで、Outlook または web 上の Outlook で電子メールを確認すると、EOP は自動的に送信者をチェックし、安全のヒントを電子メールの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="e74d6-107">Now, when you check your email in Outlook or Outlook on the web, EOP automatically checks the sender and adds a safety tip to the top of the email.</span></span>

<span data-ttu-id="e74d6-108">安全性に関するヒント (色分けされたメッセージ) は、潜在的に有害なメッセージに関する警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="e74d6-108">The safety tip—a color-coded message—will warn you about potentially harmful messages.</span></span> <span data-ttu-id="e74d6-109">受信トレイ内のほとんどのメッセージには安全なヒントがありません。</span><span class="sxs-lookup"><span data-stu-id="e74d6-109">Most messages in your inbox won't have a safety tip.</span></span> <span data-ttu-id="e74d6-110">スパム、フィッシング、およびマルウェア攻撃を防ぐために必要な情報が EOP および Office 365 にある場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="e74d6-110">You'll only see them when EOP and Office 365 has information you need to help prevent spam, phishing, and malware attacks.</span></span> <span data-ttu-id="e74d6-111">受信トレイに安全のヒントが表示される場合は、次の例を使用して、安全に関するヒントの種類について詳しく調べることができます。</span><span class="sxs-lookup"><span data-stu-id="e74d6-111">If safety tips do show up on in your inbox, you can use the following examples to learn more about each type of safety tip.</span></span>

- <span data-ttu-id="e74d6-112">疑わしいメール (赤安全ヒント)。</span><span class="sxs-lookup"><span data-stu-id="e74d6-112">Suspicious mail (red safety tip).</span></span>

    ![赤の安全ヒントを示すスクリーンショット。](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    <span data-ttu-id="e74d6-114">電子メールの赤の安全ヒントは、受信したメッセージに疑わしいものが含まれていることを意味します (フィッシング詐欺など)。</span><span class="sxs-lookup"><span data-stu-id="e74d6-114">A red safety tip in an email means that the message you received contains something suspicious, such as a phishing scam.</span></span> <span data-ttu-id="e74d6-115">この種類の電子メールメッセージは、受信トレイからは開かずに削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e74d6-115">We recommend that you delete this kind of email message from your inbox without opening it.</span></span>

- <span data-ttu-id="e74d6-116">スパム (黄色の安全性ヒント)。</span><span class="sxs-lookup"><span data-stu-id="e74d6-116">Spam (yellow safety tip).</span></span>

    ![黄色の安全性ヒントを示すスクリーンショット。](../../media/793c9265-ea44-48fd-a98f-804fadd4163b.png)

    <span data-ttu-id="e74d6-118">電子メールの黄色の安全ヒントは、メッセージがスパムとしてマークされていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e74d6-118">A yellow safety tip in an email means that the message has been marked as spam.</span></span> <span data-ttu-id="e74d6-119">メッセージの送信者を認識して信頼していない場合は、添付ファイルや画像をダウンロードしないで、メッセージ内のリンクをクリックしないでください。</span><span class="sxs-lookup"><span data-stu-id="e74d6-119">If you don't recognize and trust the sender of the message, don't download any attachments or pictures and don't click any links in the message.</span></span> <span data-ttu-id="e74d6-120">Outlook on the web では、迷惑メールアイテムの黄色のバーにある [**スパムではない**] をクリックして、メッセージを受信トレイに移動できます。</span><span class="sxs-lookup"><span data-stu-id="e74d6-120">In Outlook on the web, you can click **It's not spam** in the yellow bar of a junk mail item to move the message to your inbox.</span></span> <span data-ttu-id="e74d6-121">受信トレイに配信されたメッセージに黄色の安全ヒントが表示される場合は、迷惑メールフォルダーへのスパムの移動を無効にしている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e74d6-121">If the yellow safety tip appears on a message that was delivered to your inbox, it's probably there because you've disabled moving spam to your Junk Email folder.</span></span>

- <span data-ttu-id="e74d6-122">安全なメール (緑色の安全ヒント)。</span><span class="sxs-lookup"><span data-stu-id="e74d6-122">Safe mail (green safety tip).</span></span>

    ![緑の安全ヒントを示すスクリーンショット。](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    <span data-ttu-id="e74d6-124">安全でないメッセージに加えて、信頼できる送信者からの有効なメッセージについても、緑色の安全ヒントを示しています。</span><span class="sxs-lookup"><span data-stu-id="e74d6-124">In addition to unsafe messages, we'll also tell you about valid messages from senders we trust with a green safety tip.</span></span> <span data-ttu-id="e74d6-125">電子メールのグリーンセーフヒントは、メッセージの送信者を確認し、安全であることを確認したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e74d6-125">A green safety tip in an email means that we checked the sender of the message and verified that it's safe.</span></span> <span data-ttu-id="e74d6-126">Microsoft では、多くの場合、頻繁にスプーフィングまたは偽装される金融機関やその他の信頼できる差出人のリストを保持しています。</span><span class="sxs-lookup"><span data-stu-id="e74d6-126">Microsoft maintains this list of trusted senders which includes financial organizations and others that are frequently spoofed or impersonated.</span></span>

- <span data-ttu-id="e74d6-127">フィルター処理なしのメール (灰色の安全ヒント)。</span><span class="sxs-lookup"><span data-stu-id="e74d6-127">Unfiltered mail (gray safety tip).</span></span>

    ![灰色の安全なヒントを示すスクリーンショット。](../../media/c4d0cf8f-08e9-4c84-beee-1d9e0b022e0a.png)

    <span data-ttu-id="e74d6-129">また、差出人セーフリストにある送信者からのメールの確認や、フィルターをバイパスするメールフロールールがある場合にも、メールのチェックをスキップしたことについてもお知らせします。</span><span class="sxs-lookup"><span data-stu-id="e74d6-129">We'll also tell you when we skipped checking a mail because it's from a sender you trust on your Safe Senders list or if a mail flow rule exists to bypass filtering.</span></span>

    <span data-ttu-id="e74d6-130">また、外部画像がブロックされている場合、つまりメッセージが受信トレイにあり、スパムではないが、ダウンロードしていない外部画像が含まれている場合にも、灰色の安全なヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e74d6-130">The gray safety tip also shows up when external images are blocked, that is, the message is in your inbox and doesn't appear to be spam, but contains external images that you haven't opted to download.</span></span>

## <a name="working-with-safety-tips"></a><span data-ttu-id="e74d6-131">安全に関するヒントの使用</span><span class="sxs-lookup"><span data-stu-id="e74d6-131">Working with safety tips</span></span>

<span data-ttu-id="e74d6-132">セキュリティヒントは、すべてのメッセージが受信するわけではありませんが、Outlook on the web では常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="e74d6-132">Safety tips are always enabled for Outlook on the web, even though not every message will receive one.</span></span> <span data-ttu-id="e74d6-133">Office 365 管理者は、Outlook などの他の電子メールクライアントに対して安全のヒントを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e74d6-133">Office 365 admins can turn safety tips off for other email clients such as Outlook.</span></span> <span data-ttu-id="e74d6-134">詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e74d6-134">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="e74d6-135">EOP がメッセージを分類した方法 (つまり、メッセージがスパムではないか、またはスパムとしてマークされている必要がある) に同意しない場合は、Microsoft にメッセージを送信して、快適な操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e74d6-135">If you disagree with how EOP categorized a message (that is, the message is not spam or it should have been marked as spam), you can submit the messages to Microsoft for analysis to help make your experience better.</span></span> <span data-ttu-id="e74d6-136">手順については、「 [Microsoft にメッセージとファイルを報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e74d6-136">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="e74d6-137">また、安全性ヒントの [フィードバック] リンクをクリックして、ご意見を Microsoft に直接送信し、改善を支援することもできます。</span><span class="sxs-lookup"><span data-stu-id="e74d6-137">You can also click on the Feedback link in the safety tip to submit comments directly to Microsoft to help us improve.</span></span>
