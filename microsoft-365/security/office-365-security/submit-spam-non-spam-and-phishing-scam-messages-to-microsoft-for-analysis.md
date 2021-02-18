---
title: 分析のためにメッセージを Microsoft に手動で送信する
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 管理者とエンド ユーザーは、分析のためにメッセージ (悪いメールまたは悪いメールとしてマークされた良いメールが許可されている) を Microsoft に電子メールで送信する方法を学習できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 98964d17c41222fa708bdf0059c0e67151582ef1
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290371"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="1f01b-103">分析のためにメッセージを Microsoft に手動で送信する</span><span class="sxs-lookup"><span data-stu-id="1f01b-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1f01b-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="1f01b-104">**Applies to**</span></span>
- [<span data-ttu-id="1f01b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1f01b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1f01b-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="1f01b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="1f01b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f01b-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> <span data-ttu-id="1f01b-108">Exchange Online メールボックスを使用している組織の管理者である場合は、セキュリティ/コンプライアンス センターの提出ポータル&勧めします。</span><span class="sxs-lookup"><span data-stu-id="1f01b-108">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="1f01b-109">詳細については、「管理者送信を使用して、疑わしいスパム、 [フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f01b-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="1f01b-110">組織内のユーザーが受信トレイで迷惑メール メッセージ (スパム) またはフィッシング メッセージを受信した場合や、正当なメール メッセージが迷惑メールとしてマークされたため受信しない場合は、不満を感じます。</span><span class="sxs-lookup"><span data-stu-id="1f01b-110">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="1f01b-111">スパム フィルターをより正確に調整するために、弊社では常に微調整を行っています。</span><span class="sxs-lookup"><span data-stu-id="1f01b-111">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="1f01b-112">お客様とユーザーは、誤検知 (良いメールが悪いとマークされている)、偽陰性 (不正メールの許可) メッセージ、フィッシング メッセージを分析のために Microsoft に送信することで、このプロセスを支援できます。</span><span class="sxs-lookup"><span data-stu-id="1f01b-112">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="1f01b-113">受信する提出の量が多いので、分析要求の一部に回答できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1f01b-113">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="1f01b-114">偽陰性を Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="1f01b-114">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="1f01b-115">次の手順を使用して検出検出を報告する代わりに、Outlook および Web 上の Outlook (以前の Outlook Web App) のユーザーは、レポート メッセージ アドインまたは Report Phishing アドインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1f01b-115">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="1f01b-116">これらのツールをインストールして使用する方法については、「メッセージ報告[](enable-the-report-message-add-in.md)アドインを有効にする」および「フィッシング報告アドインを有効にする」を[参照してください](enable-the-report-phish-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="1f01b-116">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="1f01b-117">スパム フィルターを通過してスパムまたはフィッシングとして識別されるメッセージを受信した場合は、必要に応じて Microsoft スパム分析チームと Microsoft Phishing Analysis チームにメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="1f01b-117">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="1f01b-118">アナリストはメッセージを確認し、分類条件を満たす場合はサービス全体のフィルターに追加します。</span><span class="sxs-lookup"><span data-stu-id="1f01b-118">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="1f01b-119">次のいずれかの受信者を含む新しい空の電子メール メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f01b-119">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="1f01b-120">**迷惑メール**: `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="1f01b-120">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="1f01b-121">**フィッシング :**`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="1f01b-121">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="1f01b-122">迷惑メールまたはフィッシングメッセージを新しいメッセージにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="1f01b-122">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="1f01b-123">これにより、迷惑メールメッセージまたはフィッシング メッセージが新しいメッセージの添付ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="1f01b-123">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="1f01b-124">メッセージの内容をコピーして貼り付け、メッセージを転送したりしません (メッセージ ヘッダーを検査するために元のメッセージが必要です)。</span><span class="sxs-lookup"><span data-stu-id="1f01b-124">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="1f01b-125">新しいメッセージに複数のメッセージを添付できます。</span><span class="sxs-lookup"><span data-stu-id="1f01b-125">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="1f01b-126">すべてのメッセージがフィッシング メッセージと迷惑メール メッセージの種類が同じことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f01b-126">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="1f01b-127">新しいメッセージの本文は空のままにします。</span><span class="sxs-lookup"><span data-stu-id="1f01b-127">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="1f01b-128">添付メッセージに .msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web 形式) 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f01b-128">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="1f01b-129">完了したら、[送信] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="1f01b-129">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="1f01b-130">管理者は、スパムとして誤って特定されている特定のメッセージをブロックするさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="1f01b-130">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="1f01b-131">詳細については [、「EOP で受信拒否リストを作成する」を参照してください](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="1f01b-131">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="1f01b-132">誤検知を Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="1f01b-132">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="1f01b-133">次の手順を使用して誤検知を報告する代わりに、Outlook および Web 上の Outlook (旧称 Outlook Web App) のユーザーは、レポート メッセージ アドインまたは Report Phishing アドインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1f01b-133">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="1f01b-134">これらのツールをインストールして使用する方法については、「メッセージ報告[](enable-the-report-message-add-in.md)アドインを有効にする」および「フィッシング報告アドインを有効にする」を[参照してください](enable-the-report-phish-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="1f01b-134">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>


<span data-ttu-id="1f01b-135">メッセージが誤ってスパムとして識別された場合は、そのメッセージを Microsoft スパム分析チームに送信できます。</span><span class="sxs-lookup"><span data-stu-id="1f01b-135">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="1f01b-136">アナリストはメッセージを評価し、(分析の結果に応じて) サービス全体のフィルターを調整してメッセージを許可できます。</span><span class="sxs-lookup"><span data-stu-id="1f01b-136">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="1f01b-137">受信者として新しい空の電子メール `not_junk@office365.microsoft.com` メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f01b-137">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="1f01b-138">誤って特定されたメッセージを新しいメッセージにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="1f01b-138">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="1f01b-139">これにより、誤って特定されたメッセージが新しいメッセージの添付ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="1f01b-139">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="1f01b-140">メッセージの内容をコピーして貼り付け、メッセージを転送したりしません (メッセージ ヘッダーを検査するために元のメッセージが必要です)。</span><span class="sxs-lookup"><span data-stu-id="1f01b-140">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="1f01b-141">新しいメッセージに複数のメッセージを添付できます。</span><span class="sxs-lookup"><span data-stu-id="1f01b-141">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="1f01b-142">すべてのメッセージがフィッシング メッセージと迷惑メール メッセージの種類が同じことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f01b-142">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="1f01b-143">新しいメッセージの本文は空のままにします。</span><span class="sxs-lookup"><span data-stu-id="1f01b-143">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="1f01b-144">添付メッセージに .msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web 形式) 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f01b-144">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="1f01b-145">完了したら、[送信] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="1f01b-145">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="1f01b-146">管理者は、特定のメッセージがスパム フィルター処理をスキップできるさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="1f01b-146">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="1f01b-147">詳細については [、「EOP で差出人セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="1f01b-147">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="1f01b-148">Microsoft への提出からのデータはどこに保存されますか?</span><span class="sxs-lookup"><span data-stu-id="1f01b-148">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="1f01b-149">データは、北米のデータ センター Office 365 コンプライアンス境界に存在します。</span><span class="sxs-lookup"><span data-stu-id="1f01b-149">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="1f01b-150">データは、フィルターの有効性を向上させるために、エンジニアリング チームのアナリストによってレビューされます。</span><span class="sxs-lookup"><span data-stu-id="1f01b-150">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="1f01b-151">Microsoft に報告されたメッセージのコピーを受信するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="1f01b-151">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="1f01b-152">手順については、「メール フロー ルール [を使用して、ユーザーが Microsoft に報告している情報を確認する」を参照してください](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="1f01b-152">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
