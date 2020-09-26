---
title: 高度な電子情報開示での電子メールスレッド
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
description: 高度な電子情報開示分析を実行するとき、電子メールスレッドは電子メール会話を解析し、各メッセージを異なるカテゴリに分割します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285563"
---
# <a name="email-threading-in-advanced-ediscovery"></a><span data-ttu-id="7d16c-103">高度な電子情報開示での電子メールスレッド</span><span class="sxs-lookup"><span data-stu-id="7d16c-103">Email threading in Advanced eDiscovery</span></span>

<span data-ttu-id="7d16c-104">しばらくの間、電子メールでの会話を検討してください。</span><span class="sxs-lookup"><span data-stu-id="7d16c-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="7d16c-105">ほとんどの場合、スレッドの最後のメールには、先行するすべてのメールの内容が含まれます。最後のメールを確認すると、スレッドで発生した会話のコンテキストが完全にわかります。</span><span class="sxs-lookup"><span data-stu-id="7d16c-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="7d16c-106">電子メールスレッドでは、このような電子メールを識別して、校閲者が収集されたドキュメントの一部をコンテキストを失わずに確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7d16c-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="7d16c-107">電子メールスレッド処理の機能</span><span class="sxs-lookup"><span data-stu-id="7d16c-107">What does email threading do?</span></span>

<span data-ttu-id="7d16c-108">電子メールスレッドは各電子メールを解析し、個々のメッセージに deconstructs します。各電子メールは、個々のメッセージのチェインです。</span><span class="sxs-lookup"><span data-stu-id="7d16c-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="7d16c-109">次に、確認セット内のすべてのメールを分析して、電子メールに固有のコンテンツがあるかどうか、またはチェーンが完全に別の電子メールに含まれているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="7d16c-109">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="7d16c-110">エンドメールは、次の4つのカテゴリに分かれています。</span><span class="sxs-lookup"><span data-stu-id="7d16c-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="7d16c-111">**包括的**:電子メールの最後のメッセージには固有のコンテンツがあります。そしてこの電子メールには、他の電子メールに含まれていたすべての添付ファイルが含まれています。いわゆる、電子メールの完全なコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d16c-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="7d16c-112">**包括的なマイナス**:電子メールの最後のメッセージには一意のコンテンツがあります。ただ、この電子メールにはメールに含まれていた添付ファイルの一部がメールに含まれていません。いわゆる、電子メールの完全なコンテンツが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="7d16c-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="7d16c-113">**包括的コピー**：包括的/包括的マイナスの電子メールの完全なコピー</span><span class="sxs-lookup"><span data-stu-id="7d16c-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="7d16c-114">**なし**: この電子メールの内容は、包括的/包括的マイナスとしてマークされた少なくとも1つのメールに完全に含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d16c-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="7d16c-115">Outlook の会話とどのように異なるのですか?</span><span class="sxs-lookup"><span data-stu-id="7d16c-115">How is it different from conversations in Outlook?</span></span>

<span data-ttu-id="7d16c-116">Outlook の会話グループに似ていますが、このようなことがわかります。</span><span class="sxs-lookup"><span data-stu-id="7d16c-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="7d16c-117">ただし、いくつかの重要な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="7d16c-117">However, there are some important distinctions.</span></span> <span data-ttu-id="7d16c-118">2つの会話に fork した電子メールの会話を考えてみましょう。たとえば、会話の最後の2通の電子メールにはそれぞれ固有のコンテンツがあるため、会話の最新の電子メールには応答していないユーザーがいます。</span><span class="sxs-lookup"><span data-stu-id="7d16c-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="7d16c-119">Outlook は、電子メールを1つの会話にグループ化します。最後の電子メールのみを読み取ると、2番目から最後の電子メールのコンテキストが失われることになります。これには、一意のコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d16c-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="7d16c-120">電子メールスレッドは各電子メールを個別のコンポーネントに分解してそれらを比較するので、電子メールスレッドは最後の2つの電子メールの両方を包括的なものとしてマークするので、すべての電子メールを包括的にマークされている限り、コンテキストが見逃されることはありません。</span><span class="sxs-lookup"><span data-stu-id="7d16c-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
