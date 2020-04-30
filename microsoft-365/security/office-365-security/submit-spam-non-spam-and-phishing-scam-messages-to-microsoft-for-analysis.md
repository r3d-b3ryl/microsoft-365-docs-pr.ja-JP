---
title: 分析のためにメッセージを手動で Microsoft に送信する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'ユーザーは、誤検出および誤検知のスパムメッセージを分析のために Microsoft に送信することができます。 '
ms.openlocfilehash: 928809a8d00e082bf3150abb27dc493c2b82c070
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939429"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="70c6b-103">分析のためにメッセージを手動で Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="70c6b-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="70c6b-104">Microsoft 365 組織の Exchange Online メールボックスを使用している管理者の場合は、セキュリティ & コンプライアンスセンターで送信ポータルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="70c6b-104">If you're an admin in an Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="70c6b-105">詳細については、「[管理者による送信を使用して疑わしいスパム、フィッシング、url、およびファイルを Microsoft に送信する](admin-submission.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70c6b-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="70c6b-106">組織内のユーザーが迷惑メール (スパム) またはフィッシングメッセージを受信トレイで受信する場合や、迷惑メールとしてマークされているために正当な電子メールメッセージを受信しない場合は、ストレスがかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="70c6b-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="70c6b-107">より正確になるように、スパムフィルターを常に微調整しています。</span><span class="sxs-lookup"><span data-stu-id="70c6b-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="70c6b-108">この処理を支援するには、誤検知 (不良としてマークされた良好な電子メール)、誤検知 (無効なメールが許可されている)、および Microsoft に対するフィッシングメッセージを分析用に送信します。</span><span class="sxs-lookup"><span data-stu-id="70c6b-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="70c6b-109">大量の送信が送信されるため、分析のすべての要求に応答できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="70c6b-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="70c6b-110">誤検知を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="70c6b-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="70c6b-111">次の手順を使用して誤検知を報告する代わりに、Outlook および web 上の Outlook (旧称 Outlook Web App) のユーザーは Microsoft Outlook 用のレポートメッセージアドインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="70c6b-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="70c6b-112">このツールをインストールして使用する方法については、「[レポートメッセージアドインを有効](enable-the-report-message-add-in.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70c6b-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="70c6b-113">スパムまたはフィッシングとして識別されたスパムフィルタリングを通過したメッセージを受信した場合は、そのメッセージを Microsoft スパム分析および Microsoft フィッシング分析チームに適宜送信することができます。</span><span class="sxs-lookup"><span data-stu-id="70c6b-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="70c6b-114">アナリストはメッセージを確認し、分類基準を満たす場合は、サービス全体のフィルターに追加します。</span><span class="sxs-lookup"><span data-stu-id="70c6b-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="70c6b-115">次のいずれかの受信者を使用して、新しい空の電子メールメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="70c6b-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="70c6b-116">**迷惑メール**:`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="70c6b-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="70c6b-117">**フィッシング**:`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="70c6b-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="70c6b-118">迷惑メールまたはフィッシングメッセージを新しいメッセージにドラッグアンドドロップします。</span><span class="sxs-lookup"><span data-stu-id="70c6b-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="70c6b-119">これにより、迷惑メールまたはフィッシングメッセージは新しいメッセージの添付ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="70c6b-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="70c6b-120">メッセージの内容をコピーして貼り付けたり、メッセージを転送したりしないでください (メッセージヘッダーを検査できるように、元のメッセージが必要です)。</span><span class="sxs-lookup"><span data-stu-id="70c6b-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="70c6b-121">新しいメッセージに複数のメッセージを添付することができます。</span><span class="sxs-lookup"><span data-stu-id="70c6b-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="70c6b-122">すべてのメッセージが同じ種類であることを確認してください。フィッシング詐欺メッセージまたは迷惑メールメッセージのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="70c6b-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="70c6b-123">新しいメッセージの本文は空のままにします。</span><span class="sxs-lookup"><span data-stu-id="70c6b-123">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="70c6b-124">添付されたメッセージについては、.msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web format) の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="70c6b-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="70c6b-125">完了したら、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70c6b-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="70c6b-126">管理者は、スパムとして misidentified されている特定のメッセージをブロックするいくつかの方法を用意しています。</span><span class="sxs-lookup"><span data-stu-id="70c6b-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="70c6b-127">詳細については、「 [Office 365 でブロックされる送信者のリストを作成する](create-block-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70c6b-127">For details, see [Create blocked sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="70c6b-128">誤検知を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="70c6b-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="70c6b-129">次の手順を使用して誤検知を報告するのではなく、Outlook および web 上の Outlook のユーザーは Microsoft Outlook 用のレポートメッセージアドインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="70c6b-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="70c6b-130">このツールをインストールして使用する方法については、「[レポートメッセージアドインを有効](enable-the-report-message-add-in.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70c6b-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="70c6b-131">メッセージが誤ってスパムとして識別された場合は、メッセージを Microsoft スパム分析チームに送信できます。</span><span class="sxs-lookup"><span data-stu-id="70c6b-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="70c6b-132">アナリストはメッセージを評価し、(分析の結果に応じて) サービス全体のフィルターを調整して、メッセージを通過できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="70c6b-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="70c6b-133">受信者としての`not_junk@office365.microsoft.com`新しい空の電子メールメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="70c6b-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="70c6b-134">Misidentified メッセージを新しいメッセージにドラッグアンドドロップします。</span><span class="sxs-lookup"><span data-stu-id="70c6b-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="70c6b-135">これにより、misidentified メッセージは新しいメッセージの添付ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="70c6b-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="70c6b-136">メッセージの内容をコピーして貼り付けたり、メッセージを転送したりしないでください (メッセージヘッダーを検査できるように、元のメッセージが必要です)。</span><span class="sxs-lookup"><span data-stu-id="70c6b-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="70c6b-137">新しいメッセージに複数のメッセージを添付することができます。</span><span class="sxs-lookup"><span data-stu-id="70c6b-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="70c6b-138">すべてのメッセージの種類が同一であることを確認してください。フィッシングメッセージと迷惑メールメッセージのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="70c6b-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span></li><li><span data-ttu-id="70c6b-139">新しいメッセージの本文は空のままにします。</span><span class="sxs-lookup"><span data-stu-id="70c6b-139">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="70c6b-140">添付されたメッセージについては、.msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web format) の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="70c6b-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="70c6b-141">完了したら、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70c6b-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="70c6b-142">管理者は、特定のメッセージがスパムフィルタリングをスキップできるようにするいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="70c6b-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="70c6b-143">詳細については、「 [Office の信頼できる差出人のリストを作成する 365](create-safe-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70c6b-143">For details, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="70c6b-144">Microsoft に報告されたメッセージのコピーを受信するためのメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="70c6b-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="70c6b-145">手順については、「[メールフロールールを使用して、ユーザーが Microsoft に報告する内容を確認する」を](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="70c6b-145">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
