---
title: 分析のために Microsoft にメッセージを手動で送信する
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
description: 管理者とエンド ユーザーは、分析のために Microsoft にメッセージ (悪いメールまたは悪いメールとしてマークされた良いメール) を電子メールで送信する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e0a6f564d82750c5ab8156680854c2453cda6971
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064452"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="f740d-103">分析のために Microsoft にメッセージを手動で送信する</span><span class="sxs-lookup"><span data-stu-id="f740d-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f740d-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="f740d-104">**Applies to**</span></span>
- [<span data-ttu-id="f740d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f740d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f740d-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="f740d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f740d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f740d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="f740d-108">Exchange Online メールボックスを使用している組織の管理者の場合は、セキュリティ コンプライアンス センターの申請ポータルを使用&勧めします。</span><span class="sxs-lookup"><span data-stu-id="f740d-108">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f740d-109">詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f740d-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="f740d-110">組織内のユーザーが受信トレイで迷惑メール (スパム) またはフィッシング メッセージを受信した場合や、迷惑メールとしてマークされた正当な電子メール メッセージを受信しない場合は、イライラする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f740d-110">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="f740d-111">スパム フィルターの精度を高め、常に微調整を行っています。</span><span class="sxs-lookup"><span data-stu-id="f740d-111">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="f740d-112">ユーザーとユーザーは、誤検知 (悪いマークが付いた良いメール)、誤検知 (悪いメールが許可されている)、フィッシング メッセージを分析のために Microsoft に送信することで、このプロセスを支援できます。</span><span class="sxs-lookup"><span data-stu-id="f740d-112">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="f740d-113">送信が多いので、分析のすべての要求に回答できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f740d-113">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="f740d-114">False negatives を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="f740d-114">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="f740d-115">Outlook と Outlook on the web (以前は Outlook Web App と呼ばれる) のユーザーは、次の手順を使用して誤検知を報告する代わりに、レポート メッセージ アドインまたはレポート フィッシング アドインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f740d-115">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="f740d-116">これらのツールをインストールして使用する方法の詳細については、「[](enable-the-report-message-add-in.md)レポート メッセージ アドインを有効にする」および「レポート フィッシング アドインを有効にする」[を参照してください](enable-the-report-phish-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="f740d-116">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="f740d-117">スパムまたはフィッシングとして識別されている必要があるスパム フィルターを通過したメッセージを受信した場合は、必要に応じて Microsoft Spam Analysis チームと Microsoft フィッシング分析チームにメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="f740d-117">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="f740d-118">アナリストはメッセージを確認し、分類条件を満たす場合はサービス全体のフィルターに追加します。</span><span class="sxs-lookup"><span data-stu-id="f740d-118">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="f740d-119">次のいずれかの受信者を含む、新しい空白の電子メール メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="f740d-119">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="f740d-120">**迷惑** メール : `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="f740d-120">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="f740d-121">**フィッシング**: `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="f740d-121">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="f740d-122">迷惑メールまたはフィッシング メッセージを新しいメッセージにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="f740d-122">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="f740d-123">これにより、迷惑メールまたはフィッシング メッセージが新しいメッセージの添付ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="f740d-123">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="f740d-124">メッセージの内容をコピーして貼り付けるか、メッセージを転送したりしません (メッセージ ヘッダーを調べたい場合は、元のメッセージが必要です)。</span><span class="sxs-lookup"><span data-stu-id="f740d-124">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="f740d-125">新しいメッセージに複数のメッセージを添付できます。</span><span class="sxs-lookup"><span data-stu-id="f740d-125">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="f740d-126">すべてのメッセージがフィッシング メッセージまたは迷惑メール メッセージのいずれかと同じ種類に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f740d-126">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="f740d-127">新しいメッセージの本文は空のままにします。</span><span class="sxs-lookup"><span data-stu-id="f740d-127">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="f740d-128">添付メッセージには、.msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web 形式) 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="f740d-128">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="f740d-129">完了したら、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f740d-129">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="f740d-130">管理者は、スパムと誤認されている特定のメッセージをブロックするさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="f740d-130">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="f740d-131">詳細については [、「EOP で受信拒否リストを作成する」を参照してください](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="f740d-131">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="f740d-132">Microsoft に誤検知を送信する</span><span class="sxs-lookup"><span data-stu-id="f740d-132">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="f740d-133">次の手順を使用して誤検知を報告する代わりに、Outlook と Outlook on the web (以前は Outlook Web App と呼ばれる) のユーザーは、レポート メッセージ アドインまたはレポート フィッシング アドインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f740d-133">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="f740d-134">これらのツールをインストールして使用する方法の詳細については、「[](enable-the-report-message-add-in.md)レポート メッセージ アドインを有効にする」および「レポート フィッシング アドインを有効にする」[を参照してください](enable-the-report-phish-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="f740d-134">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>


<span data-ttu-id="f740d-135">メッセージがスパムとして誤って識別された場合は、Microsoft スパム分析チームにメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="f740d-135">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="f740d-136">アナリストはメッセージを評価し、(分析の結果に応じて) サービス全体のフィルターを調整してメッセージを通過できます。</span><span class="sxs-lookup"><span data-stu-id="f740d-136">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="f740d-137">受信者として新しい空白の電子メール `not_junk@office365.microsoft.com` メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="f740d-137">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="f740d-138">誤認されたメッセージを新しいメッセージにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="f740d-138">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="f740d-139">これにより、誤認されたメッセージが新しいメッセージの添付ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="f740d-139">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="f740d-140">メッセージの内容をコピーして貼り付けるか、メッセージを転送したりしません (メッセージ ヘッダーを調べたい場合は、元のメッセージが必要です)。</span><span class="sxs-lookup"><span data-stu-id="f740d-140">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="f740d-141">新しいメッセージに複数のメッセージを添付できます。</span><span class="sxs-lookup"><span data-stu-id="f740d-141">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="f740d-142">すべてのメッセージがフィッシング メッセージまたは迷惑メール メッセージのいずれかと同じ種類に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f740d-142">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="f740d-143">新しいメッセージの本文は空のままにします。</span><span class="sxs-lookup"><span data-stu-id="f740d-143">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="f740d-144">添付メッセージには、.msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web 形式) 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="f740d-144">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="f740d-145">完了したら、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f740d-145">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="f740d-146">管理者は、特定のメッセージがスパム フィルター処理をスキップできるさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="f740d-146">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="f740d-147">詳細については [、「EOP で差出人セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="f740d-147">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="f740d-148">申請から Microsoft へのデータはどこに保存されますか?</span><span class="sxs-lookup"><span data-stu-id="f740d-148">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="f740d-149">データは、北米のデータ センター Office 365 コンプライアンス境界に存在します。</span><span class="sxs-lookup"><span data-stu-id="f740d-149">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="f740d-150">データは、フィルターの有効性を向上させるために、エンジニアリング チームのアナリストによって確認されます。</span><span class="sxs-lookup"><span data-stu-id="f740d-150">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="f740d-151">Microsoft に報告されたメッセージのコピーを受信するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="f740d-151">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="f740d-152">手順については、「メール フロー ルールを使用して、ユーザーが Microsoft に報告している [情報を確認する」を参照してください](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="f740d-152">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
