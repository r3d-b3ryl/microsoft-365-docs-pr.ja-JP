---
title: 分析のためにメッセージを Microsoft に手動で送信する
f1.keywords:
- NOCSH
ms.author: siosulli
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
description: 管理者とエンド ユーザーは、分析のためにメッセージ (悪いメールまたは悪いメールとしてマークされた良いメールが許可されている) を Microsoft に電子メールで送信する方法を学習できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe8e3c5ed44c7578764ed0bf19408f4db16e3740
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751561"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="ff093-103">分析のためにメッセージを Microsoft に手動で送信する</span><span class="sxs-lookup"><span data-stu-id="ff093-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="ff093-104">Exchange Online メールボックスを使用している組織の管理者である場合は、セキュリティ/コンプライアンス センターの提出ポータル&勧めします。</span><span class="sxs-lookup"><span data-stu-id="ff093-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="ff093-105">詳細については、「管理者送信を使用して、疑わしいスパム、 [フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff093-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="ff093-106">組織内のユーザーが受信トレイで迷惑メール メッセージ (スパム) またはフィッシング メッセージを受信した場合や、正当な電子メール メッセージが迷惑メールとしてマークされたため受信しない場合は、不満が生じます。</span><span class="sxs-lookup"><span data-stu-id="ff093-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="ff093-107">スパム フィルターをより正確に調整するために、弊社では常に微調整を行っています。</span><span class="sxs-lookup"><span data-stu-id="ff093-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="ff093-108">お客様とユーザーは、誤検知 (良いメールが悪いとマークされている)、偽陰性 (不正メールの許可) メッセージ、フィッシング メッセージを分析のために Microsoft に送信することで、このプロセスを支援できます。</span><span class="sxs-lookup"><span data-stu-id="ff093-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="ff093-109">受信する提出の量が多いので、分析要求の一部に回答できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ff093-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="ff093-110">偽陰性を Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="ff093-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="ff093-111">次の手順を使用して検出検出を報告する代わりに、Outlook および Web 上の Outlook (旧 Outlook Web App) のユーザーは、Microsoft Outlook 用のレポート メッセージ アドインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ff093-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="ff093-112">このツールをインストールして使用する方法については、「レポート メッセージ アドインを有効にする」 [を参照してください](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="ff093-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="ff093-113">スパム フィルターを通過してスパムまたはフィッシングとして識別されるメッセージを受信した場合は、必要に応じて Microsoft スパム分析チームと Microsoft Phishing Analysis チームにメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="ff093-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="ff093-114">アナリストはメッセージを確認し、分類条件を満たす場合はサービス全体のフィルターに追加します。</span><span class="sxs-lookup"><span data-stu-id="ff093-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="ff093-115">次のいずれかの受信者を含む新しい空の電子メール メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="ff093-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="ff093-116">**迷惑メール**: `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="ff093-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="ff093-117">**フィッシング :**`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="ff093-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="ff093-118">迷惑メールまたはフィッシングメッセージを新しいメッセージにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="ff093-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="ff093-119">これにより、迷惑メールメッセージまたはフィッシング メッセージが新しいメッセージの添付ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="ff093-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="ff093-120">メッセージの内容をコピーして貼り付け、メッセージを転送したりしません (メッセージ ヘッダーを検査するには元のメッセージが必要です)。</span><span class="sxs-lookup"><span data-stu-id="ff093-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="ff093-121">新しいメッセージに複数のメッセージを添付できます。</span><span class="sxs-lookup"><span data-stu-id="ff093-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="ff093-122">すべてのメッセージがフィッシング メッセージと迷惑メール メッセージの種類が同じことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ff093-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="ff093-123">新しいメッセージの本文は空のままにします。</span><span class="sxs-lookup"><span data-stu-id="ff093-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="ff093-124">添付メッセージに .msg (既定の Outlook 形式) または .eml (既定の Web 上の Outlook 形式) 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="ff093-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="ff093-125">完了したら、[送信] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="ff093-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="ff093-126">管理者は、スパムとして誤って特定されている特定のメッセージをブロックするさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="ff093-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="ff093-127">詳細については [、「EOP で受信拒否リストを作成する」を参照してください](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="ff093-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="ff093-128">誤検知を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="ff093-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="ff093-129">Outlook および Outlook on the web のユーザーは、次の手順を使用して誤検知を報告する代わりに、Microsoft Outlook のメッセージ報告アドインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ff093-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="ff093-130">このツールをインストールして使用する方法については、「レポート メッセージ アドインを有効にする」 [を参照してください](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="ff093-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="ff093-131">メッセージが誤ってスパムとして識別された場合は、そのメッセージを Microsoft スパム分析チームに送信できます。</span><span class="sxs-lookup"><span data-stu-id="ff093-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="ff093-132">アナリストはメッセージを評価し、(分析の結果に応じて) サービス全体のフィルターを調整してメッセージを許可できます。</span><span class="sxs-lookup"><span data-stu-id="ff093-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="ff093-133">受信者として新しい空の電子メール `not_junk@office365.microsoft.com` メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="ff093-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="ff093-134">誤って特定されたメッセージを新しいメッセージにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="ff093-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="ff093-135">これにより、誤って特定されたメッセージが新しいメッセージの添付ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="ff093-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="ff093-136">メッセージの内容をコピーして貼り付け、メッセージを転送したりしません (メッセージ ヘッダーを検査するために元のメッセージが必要です)。</span><span class="sxs-lookup"><span data-stu-id="ff093-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="ff093-137">新しいメッセージに複数のメッセージを添付できます。</span><span class="sxs-lookup"><span data-stu-id="ff093-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="ff093-138">すべてのメッセージがフィッシング メッセージと迷惑メール メッセージの種類が同じことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ff093-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="ff093-139">新しいメッセージの本文は空のままにします。</span><span class="sxs-lookup"><span data-stu-id="ff093-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="ff093-140">添付メッセージに .msg (既定の Outlook 形式) または .eml (既定の Web 上の Outlook 形式) 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="ff093-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="ff093-141">完了したら、[送信] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="ff093-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="ff093-142">管理者は、特定のメッセージがスパム フィルター処理をスキップできるさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="ff093-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="ff093-143">詳細については [、「EOP で差出人セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="ff093-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="ff093-144">Microsoft への提出からのデータはどこに保存されますか?</span><span class="sxs-lookup"><span data-stu-id="ff093-144">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="ff093-145">データは、北米のデータ センター Office 365 コンプライアンス境界に存在します。</span><span class="sxs-lookup"><span data-stu-id="ff093-145">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="ff093-146">データは、フィルターの有効性を向上させるために、エンジニアリング チームのアナリストによってレビューされます。</span><span class="sxs-lookup"><span data-stu-id="ff093-146">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="ff093-147">Microsoft に報告されたメッセージのコピーを受信するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="ff093-147">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="ff093-148">手順については、「メール フロー ルール [を使用して、ユーザーが Microsoft に報告している情報を確認する」を参照してください](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="ff093-148">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
