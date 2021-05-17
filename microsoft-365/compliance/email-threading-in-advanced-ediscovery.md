---
title: メール スレッド (Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 分析を実行Advanced eDiscovery、電子メール スレッドは電子メールの会話を解析し、各メッセージを異なるカテゴリに分割します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285563"
---
# <a name="email-threading-in-advanced-ediscovery"></a><span data-ttu-id="1fe37-103">メール スレッド (Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1fe37-103">Email threading in Advanced eDiscovery</span></span>

<span data-ttu-id="1fe37-104">しばらくの間続く電子メールの会話を検討してください。</span><span class="sxs-lookup"><span data-stu-id="1fe37-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="1fe37-105">ほとんどの場合、スレッドの最後のメールには、前のすべてのメールの内容が含まれます。最後のメールを確認すると、スレッドで発生した会話の完全なコンテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fe37-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="1fe37-106">電子メール スレッドは、このような電子メールを識別し、レビュー担当者はコンテキストを失わずに収集されたドキュメントの一部を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1fe37-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="1fe37-107">電子メールスレッドは何をしますか?</span><span class="sxs-lookup"><span data-stu-id="1fe37-107">What does email threading do?</span></span>

<span data-ttu-id="1fe37-108">電子メール スレッドは、各電子メールを解析し、個々のメッセージに分解します。各電子メールは、個々のメッセージのチェーンです。</span><span class="sxs-lookup"><span data-stu-id="1fe37-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="1fe37-109">次に、レビュー セット内のすべてのメールを分析して、電子メールに固有のコンテンツが含まれているか、チェーンが完全に別の電子メールに含まれているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="1fe37-109">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="1fe37-110">最後に、電子メールは次の 4 つのカテゴリに分けられます。</span><span class="sxs-lookup"><span data-stu-id="1fe37-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="1fe37-111">**包括的**:電子メールの最後のメッセージには固有のコンテンツがあります。そしてこの電子メールには、他の電子メールに含まれていたすべての添付ファイルが含まれています。いわゆる、電子メールの完全なコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1fe37-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="1fe37-112">**包括的なマイナス**:電子メールの最後のメッセージには一意のコンテンツがあります。ただ、この電子メールにはメールに含まれていた添付ファイルの一部がメールに含まれていません。いわゆる、電子メールの完全なコンテンツが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="1fe37-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="1fe37-113">**包括的コピー**：包括的/包括的マイナスの電子メールの完全なコピー</span><span class="sxs-lookup"><span data-stu-id="1fe37-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="1fe37-114">**なし**: この電子メールの内容は、包括的/包括的マイナスとしてマークされた少なくとも1つのメールに完全に含まれています。</span><span class="sxs-lookup"><span data-stu-id="1fe37-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="1fe37-115">会話とどのように違うのOutlook?</span><span class="sxs-lookup"><span data-stu-id="1fe37-115">How is it different from conversations in Outlook?</span></span>

<span data-ttu-id="1fe37-116">一目でわかると、これはユーザーの会話グループに似Outlook。</span><span class="sxs-lookup"><span data-stu-id="1fe37-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="1fe37-117">ただし、いくつかの重要な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="1fe37-117">However, there are some important distinctions.</span></span> <span data-ttu-id="1fe37-118">2 つの会話にフォークされた電子メールの会話を検討します。たとえば、誰かが会話の最新ではない電子メールに応答した場合、会話の最後の 2 つのメールの両方に一意のコンテンツがあります。</span><span class="sxs-lookup"><span data-stu-id="1fe37-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="1fe37-119">Outlookメールを 1 つの会話にグループ化します。最後の電子メールのみを読み取る場合は、2 番目から最後の電子メールのコンテキストが欠落し、一意のコンテンツも含まれるという意味です。</span><span class="sxs-lookup"><span data-stu-id="1fe37-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="1fe37-120">電子メール スレッドは各メールを個々のコンポーネントに解析して比較しますので、電子メール スレッドは、最後の 2 つのメールの両方を包括的としてマークし、包括的とマークされたメールを読む限り、コンテキストを見逃す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1fe37-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
