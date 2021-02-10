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
description: EOP と Office 365 が、電子メールの上部に安全のヒントを追加して、スパム、フィッシング、マルウェアの防止によってユーザーを保護する方法について学習します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c37eba07b306ff47e14640e494e468b63b358726
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166617"
---
# <a name="safety-tips-in-email-messages"></a><span data-ttu-id="ce624-103">電子メール メッセージの安全性に関するヒント</span><span class="sxs-lookup"><span data-stu-id="ce624-103">Safety tips in email messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ce624-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="ce624-104">**Applies to**</span></span>
- [<span data-ttu-id="ce624-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ce624-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="ce624-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="ce624-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="ce624-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ce624-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="ce624-108">Exchange Online Protection (EOP) と Microsoft 365 は、スパム、フィッシング、マルウェアの防止によってユーザーを保護します。</span><span class="sxs-lookup"><span data-stu-id="ce624-108">Exchange Online Protection (EOP) and Microsoft 365 protect you with spam, phishing, and malware prevention.</span></span> <span data-ttu-id="ce624-109">現在、これらの攻撃の一部は、正当に見える程度に十分に作成されています。</span><span class="sxs-lookup"><span data-stu-id="ce624-109">Today, some of these attacks are so well crafted that they look legitimate.</span></span> <span data-ttu-id="ce624-110">[迷惑メール] フォルダーへのメッセージの送信では、必ずしも十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="ce624-110">Sending messages to the Junk Email folder isn't always enough.</span></span> <span data-ttu-id="ce624-111">Outlook または Outlook on the web または任意の電子メール クライアントでメールを確認すると、EOP は自動的に送信者をチェックし、電子メールの上部に安全のヒントを追加します。</span><span class="sxs-lookup"><span data-stu-id="ce624-111">Now, when you check your email in Outlook or Outlook on the web or any email client, EOP automatically checks the sender and adds a safety tip to the top of the email.</span></span>

<span data-ttu-id="ce624-112">安全のヒントは、安全のヒントが開き、メッセージ本文に直接挿入されるので、使用している Outlook のバージョンには依存されません。</span><span class="sxs-lookup"><span data-stu-id="ce624-112">Safety tips in Outlook do not depend on what version of Outlook you're using because the safety tip is cracked open and inserted directly into the message body.</span></span> <span data-ttu-id="ce624-113">つまり、安全のヒントは、使用している電子メール クライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce624-113">This means that the safety tip will show up in whatever email client you're using.</span></span> <span data-ttu-id="ce624-114">これは電子メール フィルター レベルで実行され、メール クライアント レベルではレンダリングされないので、どのバージョンの Outlook でも表示されるだけでなく、すべての電子メール クライアントにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce624-114">It's done at the email filter level and not rendered at the mail client level, so not only does it show up in any version of Outlook, it also shows up in any email client.</span></span>

<span data-ttu-id="ce624-115">安全性のヒント (色分けされたメッセージ) は、有害な可能性のあるメッセージについて警告します。</span><span class="sxs-lookup"><span data-stu-id="ce624-115">The safety tip -- a color-coded message -- will warn you about potentially harmful messages.</span></span> <span data-ttu-id="ce624-116">受信トレイ内のほとんどのメッセージには、安全性に関するヒントが表示されません。</span><span class="sxs-lookup"><span data-stu-id="ce624-116">Most messages in your inbox won't have a safety tip.</span></span> <span data-ttu-id="ce624-117">EOP と Microsoft 365 にスパム、フィッシング、マルウェア攻撃の防止に必要な情報がある場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce624-117">You'll only see them when EOP and Microsoft 365 have information you need to help prevent spam, phishing, and malware attacks.</span></span> <span data-ttu-id="ce624-118">安全のヒントが受信トレイに表示される場合は、次の例を使用して、各種類の安全のヒントの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ce624-118">If safety tips do show up on in your inbox, you can use the following examples to learn more about each type of safety tip.</span></span>

- <span data-ttu-id="ce624-119">不審なメール (赤い安全性のヒント)。</span><span class="sxs-lookup"><span data-stu-id="ce624-119">Suspicious mail (red safety tip).</span></span>

    ![赤い安全性のヒントを示すスクリーンショット。](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    <span data-ttu-id="ce624-121">電子メールの赤い安全性のヒントは、受信したメッセージにフィッシング詐欺などの疑わしい情報が含まれていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ce624-121">A red safety tip in an email means that the message you received contains something suspicious, such as a phishing scam.</span></span> <span data-ttu-id="ce624-122">この種類のメール メッセージは、開かなくても受信トレイから削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ce624-122">We recommend that you delete this kind of email message from your inbox without opening it.</span></span>

- <span data-ttu-id="ce624-123">安全なメール (緑色の安全性のヒント)。</span><span class="sxs-lookup"><span data-stu-id="ce624-123">Safe mail (green safety tip).</span></span>

    ![緑色の安全性のヒントを示すスクリーンショット。](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    <span data-ttu-id="ce624-125">安全でないメッセージに加えて、信頼できる送信者からの有効なメッセージについて、緑色の安全のヒントも示します。</span><span class="sxs-lookup"><span data-stu-id="ce624-125">In addition to unsafe messages, we'll also tell you about valid messages from senders we trust with a green safety tip.</span></span> <span data-ttu-id="ce624-126">メールの緑色の安全性のヒントは、メッセージの送信者をチェックし、安全な状態を確認したという意味です。</span><span class="sxs-lookup"><span data-stu-id="ce624-126">A green safety tip in an email means that we checked the sender of the message and verified that it's safe.</span></span> <span data-ttu-id="ce624-127">Microsoft では、この信頼できる差出人の一覧を保持しています。これには、金融機関や、なりすましや偽装が頻繁に行われるその他の送信者が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce624-127">Microsoft maintains this list of trusted senders which includes financial organizations and others that are frequently spoofed or impersonated.</span></span>

## <a name="working-with-safety-tips"></a><span data-ttu-id="ce624-128">安全に関するヒントを操作する</span><span class="sxs-lookup"><span data-stu-id="ce624-128">Working with safety tips</span></span>

<span data-ttu-id="ce624-129">すべてのメッセージが Outlook on the web を受け取る場合でも、安全のヒントは常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="ce624-129">Safety tips are always enabled for Outlook on the web, even though not every message will receive one.</span></span> <span data-ttu-id="ce624-130">管理者は、Outlook などの他の電子メール クライアントの安全性のヒントをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="ce624-130">Admins can turn safety tips off for other email clients such as Outlook.</span></span> <span data-ttu-id="ce624-131">詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce624-131">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="ce624-132">EOP がメッセージを分類した方法 (つまり、メッセージがスパムではないか、スパムとしてマークされている必要がある) に同意しない場合は、分析のためにメッセージを Microsoft に送信して、エクスペリエンスを向上できます。</span><span class="sxs-lookup"><span data-stu-id="ce624-132">If you disagree with how EOP categorized a message (that is, the message is not spam or it should have been marked as spam), you can submit the messages to Microsoft for analysis to help make your experience better.</span></span> <span data-ttu-id="ce624-133">手順については、「メッセージとファイル [を Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="ce624-133">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="ce624-134">また、安全に関するヒントの [フィードバック] リンクをクリックして、改善に役立つコメントを直接 Microsoft に送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="ce624-134">You can also click on the Feedback link in the safety tip to submit comments directly to Microsoft to help us improve.</span></span>
