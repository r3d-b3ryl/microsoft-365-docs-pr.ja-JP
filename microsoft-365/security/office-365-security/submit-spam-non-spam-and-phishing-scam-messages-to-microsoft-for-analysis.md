---
title: 分析用に Microsoft に手動でメッセージを送信する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 管理者とエンド ユーザーは、Microsoft への分析を行う必要なメッセージ (不適切なメールや不適切なメールの受信のマーク) を確認できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94f00f8399164a84d2cb9dae0c4c416b73dfb0dc
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827811"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="a7505-103">分析用に Microsoft に手動でメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="a7505-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="a7505-104">Exchange Online メールボックスを持つ組織内の管理者は、セキュリティ/コンプライアンス センターの提出ポータルを&ことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a7505-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="a7505-105">詳細については、「管理者送信 [を使用して、スパム、フィッシング、URL、ファイルを Microsoft に送信する」を参照してください](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="a7505-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="a7505-106">組織のユーザーが受信トレイで迷惑メール メッセージ (スパム) やフィッシング メッセージを受信したり、当該電子メール メッセージが迷惑メールとしてマークされたため受信されなけない場合に、イライラする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a7505-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="a7505-107">迷惑メール フィルターは、いつも調整していくために、より高い結果が生じないでいい場合も当てはまりはありません。</span><span class="sxs-lookup"><span data-stu-id="a7505-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="a7505-108">組織とユーザーは、誤検知 (良いメールが悪いメール)、誤検知 (不正なメールの許可)、分析用に Microsoft にフィッシング メールを送信することで、このプロセスをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="a7505-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="a7505-109">弊回の送出量が多いため、分析を受けたすべての要求に回答できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7505-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="a7505-110">Microsoft に偽の漏れを送信する</span><span class="sxs-lookup"><span data-stu-id="a7505-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="a7505-111">次の手順を使用して誤検知を報告する代わりに、Outlook および Web 上の Outlook (Outlook Web App) のユーザーは Microsoft Outlook 用の報告メッセージ アドインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7505-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="a7505-112">このツールをインストールして使用する方法については、「レポート [メッセージ アドインを有効にする」を参照してください](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="a7505-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="a7505-113">スパム フィルター処理を通過したメッセージを受信し、スパムまたはフィッシングとして識別されるメッセージを受信した場合、そのメッセージを Microsoft スパム分析チームおよび Microsoft Phishing Analysis チームに送信できます。</span><span class="sxs-lookup"><span data-stu-id="a7505-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="a7505-114">アナリストはメッセージを確認し、分類条件に一致する場合はサービス全体のフィルターに追加します。</span><span class="sxs-lookup"><span data-stu-id="a7505-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="a7505-115">空の電子メール メッセージを作成し、次の受信者のいずれかを設定します。</span><span class="sxs-lookup"><span data-stu-id="a7505-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="a7505-116">**迷惑メール**: `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="a7505-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="a7505-117">**フィッシング**: `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="a7505-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="a7505-118">迷惑メールまたはフィッシング メール メッセージを新しいメッセージにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="a7505-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="a7505-119">これにより、迷惑メールまたはフィッシングのメッセージが新しいメッセージの添付ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="a7505-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="a7505-120">メッセージの内容をコピーして貼り付けたり、メッセージを転送したりしてはいけません (メッセージのヘッダーを検かけ出すには、元のメッセージが必要です)。</span><span class="sxs-lookup"><span data-stu-id="a7505-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="a7505-121">新しいメッセージ内の複数のメッセージを添付することができます。</span><span class="sxs-lookup"><span data-stu-id="a7505-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="a7505-122">すべてのメッセージの種類が同一であること (フィッシング メッセージか迷惑メール メッセージのどちらか) を確認します。</span><span class="sxs-lookup"><span data-stu-id="a7505-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="a7505-123">新しいメッセージの本文は空のままにします。</span><span class="sxs-lookup"><span data-stu-id="a7505-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="a7505-124">添付されたメッセージには, .msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web 形式) 形式のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="a7505-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="a7505-125">完了したら、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a7505-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="a7505-126">管理者は、スパムとして識別されていない特定のメッセージをブロックするためのいくつかの方法を利用できます。</span><span class="sxs-lookup"><span data-stu-id="a7505-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="a7505-127">詳細については、「EOP でブロック [する送信者リストを作成する」を参照してください](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a7505-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="a7505-128">誤検知を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="a7505-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="a7505-129">以下の手順を使用して誤検知を報告する代わりに、Outlook や Outlook on the web のユーザーは Microsoft Outlook のメッセージ報告アドインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7505-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="a7505-130">このツールをインストールして使用する方法については、「レポート [メッセージ アドインを有効にする」を参照してください](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="a7505-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="a7505-131">メッセージが誤ってスパムとして識別された場合は、Microsoft スパム分析チームに送信することができます。</span><span class="sxs-lookup"><span data-stu-id="a7505-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="a7505-132">アナリストはメッセージを評価し、このメッセージが許可される場合はサービス全体のフィルターを調整できます。</span><span class="sxs-lookup"><span data-stu-id="a7505-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="a7505-133">受信者として新しい空のメール メッセージ `not_junk@office365.microsoft.com` を作成します。</span><span class="sxs-lookup"><span data-stu-id="a7505-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="a7505-134">識別されていないメッセージを新しいメッセージにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="a7505-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="a7505-135">これにより、識別されていないメッセージが新しいメッセージの添付ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="a7505-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="a7505-136">メッセージの内容をコピーして貼り付けたり、メッセージを転送したりしてはいけません (メッセージのヘッダーを検かけ出すには、元のメッセージが必要です)。</span><span class="sxs-lookup"><span data-stu-id="a7505-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="a7505-137">新しいメッセージ内の複数のメッセージを添付することができます。</span><span class="sxs-lookup"><span data-stu-id="a7505-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="a7505-138">すべてのメッセージの種類が同一であること (フィッシング メッセージか迷惑メール メッセージのどちらか) を確認します。</span><span class="sxs-lookup"><span data-stu-id="a7505-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="a7505-139">新しいメッセージの本文は空のままにします。</span><span class="sxs-lookup"><span data-stu-id="a7505-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="a7505-140">添付されたメッセージには, .msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web 形式) 形式のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="a7505-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="a7505-141">完了したら、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a7505-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="a7505-142">管理者は、特定のメッセージにスパム フィルターをスキップするさまざまな方法を用いることができます。</span><span class="sxs-lookup"><span data-stu-id="a7505-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="a7505-143">詳細については、「EOP で差 [出人セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a7505-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="a7505-144">Microsoft に報告されたメッセージのコピーを受信するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="a7505-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="a7505-145">手順については、「メール フロー [ルールを使用して、ユーザーが Microsoft に報告する内容を参照する」を参照してください](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="a7505-145">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
