---
title: 電子メール メッセージの安全性に関するヒント
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: EOP と Office 365 が、電子メールの上部に安全ヒントを追加して、スパム、フィッシング、マルウェア対策で保護する方法について学習します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 659a83c73b4fef9097aa317332c9951d53b09a33
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994987"
---
# <a name="safety-tips-in-email-messages"></a><span data-ttu-id="33735-103">電子メール メッセージの安全性に関するヒント</span><span class="sxs-lookup"><span data-stu-id="33735-103">Safety tips in email messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="33735-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="33735-104">**Applies to**</span></span>
- [<span data-ttu-id="33735-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="33735-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="33735-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="33735-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="33735-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33735-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="33735-108">Exchange Online Protection (EOP) と Microsoft 365 は、スパム、フィッシング、マルウェア防止でユーザーを保護します。</span><span class="sxs-lookup"><span data-stu-id="33735-108">Exchange Online Protection (EOP) and Microsoft 365 protect you with spam, phishing, and malware prevention.</span></span> <span data-ttu-id="33735-109">今日、これらの攻撃の中には、正当に見える程度に巧妙に作られたものがあります。</span><span class="sxs-lookup"><span data-stu-id="33735-109">Today, some of these attacks are so well crafted that they look legitimate.</span></span> <span data-ttu-id="33735-110">迷惑メール フォルダーにメッセージを送信すると、必ずしも十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="33735-110">Sending messages to the Junk Email folder isn't always enough.</span></span> <span data-ttu-id="33735-111">これで、Outlook または Outlook on the web または任意のメール クライアントでメールをチェックすると、EOP は送信者を自動的にチェックし、電子メールの上部に安全ヒントを追加します。</span><span class="sxs-lookup"><span data-stu-id="33735-111">Now, when you check your email in Outlook or Outlook on the web or any email client, EOP automatically checks the sender and adds a safety tip to the top of the email.</span></span>

<span data-ttu-id="33735-112">Outlook の安全ヒントは、安全ヒントが開いて、メッセージ本文に直接挿入されるので、使用している Outlook のバージョンに依存しない。</span><span class="sxs-lookup"><span data-stu-id="33735-112">Safety tips in Outlook do not depend on what version of Outlook you're using because the safety tip is cracked open and inserted directly into the message body.</span></span> <span data-ttu-id="33735-113">つまり、安全上のヒントは、使用しているメール クライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="33735-113">This means that the safety tip will show up in whatever email client you're using.</span></span> <span data-ttu-id="33735-114">これは、メール フィルター レベルで行われ、メール クライアント レベルではレンダリングされません。したがって、Outlook の任意のバージョンに表示されるだけでなく、すべての電子メール クライアントにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="33735-114">It's done at the email filter level and not rendered at the mail client level, so not only does it show up in any version of Outlook, it also shows up in any email client.</span></span>

<span data-ttu-id="33735-115">安全上のヒント (色分けされたメッセージ) は、潜在的に有害なメッセージについて警告します。</span><span class="sxs-lookup"><span data-stu-id="33735-115">The safety tip -- a color-coded message -- will warn you about potentially harmful messages.</span></span> <span data-ttu-id="33735-116">受信トレイ内のほとんどのメッセージには安全上のヒントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="33735-116">Most messages in your inbox won't have a safety tip.</span></span> <span data-ttu-id="33735-117">EOP と Microsoft 365 にスパム、フィッシング、マルウェア攻撃の防止に必要な情報がある場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="33735-117">You'll only see them when EOP and Microsoft 365 have information you need to help prevent spam, phishing, and malware attacks.</span></span> <span data-ttu-id="33735-118">安全に関するヒントが受信トレイに表示される場合は、次の例を使用して、各種類の安全ヒントの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="33735-118">If safety tips do show up on in your inbox, you can use the following examples to learn more about each type of safety tip.</span></span>

- <span data-ttu-id="33735-119">不審なメール (赤い安全ヒント)。</span><span class="sxs-lookup"><span data-stu-id="33735-119">Suspicious mail (red safety tip).</span></span>

    ![赤い安全ヒントを示すスクリーンショット。](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    <span data-ttu-id="33735-121">電子メールの赤い安全上のヒントは、受信したメッセージにフィッシング詐欺などの疑わしい情報が含まれていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="33735-121">A red safety tip in an email means that the message you received contains something suspicious, such as a phishing scam.</span></span> <span data-ttu-id="33735-122">この種類の電子メール メッセージは、受信トレイを開かなくても削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="33735-122">We recommend that you delete this kind of email message from your inbox without opening it.</span></span>

- <span data-ttu-id="33735-123">セーフ メール (緑色の安全ヒント)。</span><span class="sxs-lookup"><span data-stu-id="33735-123">Safe mail (green safety tip).</span></span>

    ![緑色の安全ヒントを示すスクリーンショット。](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    <span data-ttu-id="33735-125">安全でないメッセージに加えて、信頼できる送信者からの有効なメッセージについて、緑色の安全上のヒントも提供します。</span><span class="sxs-lookup"><span data-stu-id="33735-125">In addition to unsafe messages, we'll also tell you about valid messages from senders we trust with a green safety tip.</span></span> <span data-ttu-id="33735-126">メールの緑色の安全上のヒントは、メッセージの送信者を確認し、安全な状態を確認したという意味です。</span><span class="sxs-lookup"><span data-stu-id="33735-126">A green safety tip in an email means that we checked the sender of the message and verified that it's safe.</span></span> <span data-ttu-id="33735-127">Microsoft は、この信頼できる送信者の一覧を保持しています。これには、金融機関や、頻繁にスプーフィングや偽装が行われるその他の送信者が含まれます。</span><span class="sxs-lookup"><span data-stu-id="33735-127">Microsoft maintains this list of trusted senders which includes financial organizations and others that are frequently spoofed or impersonated.</span></span>

## <a name="working-with-safety-tips"></a><span data-ttu-id="33735-128">安全に関するヒントを操作する</span><span class="sxs-lookup"><span data-stu-id="33735-128">Working with safety tips</span></span>

<span data-ttu-id="33735-129">管理者は、スパム対策ポリシーで安全に関するヒントをオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="33735-129">Admins can turn safety tips on or off in anti-spam policies.</span></span> <span data-ttu-id="33735-130">詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33735-130">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="33735-131">EOP でメッセージを分類する方法 (つまり、メッセージがスパムではないか、スパムとしてマークされている必要がある) に同意しない場合は、分析のために Microsoft にメッセージを送信して、エクスペリエンスを向上できます。</span><span class="sxs-lookup"><span data-stu-id="33735-131">If you disagree with how EOP categorized a message (that is, the message is not spam or it should have been marked as spam), you can submit the messages to Microsoft for analysis to help make your experience better.</span></span> <span data-ttu-id="33735-132">手順については、「メッセージと [ファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="33735-132">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="33735-133">また、安全上のヒントにある [フィードバック] リンクをクリックして、Microsoft にコメントを直接送信して、改善を支援することもできます。</span><span class="sxs-lookup"><span data-stu-id="33735-133">You can also click on the Feedback link in the safety tip to submit comments directly to Microsoft to help us improve.</span></span>
