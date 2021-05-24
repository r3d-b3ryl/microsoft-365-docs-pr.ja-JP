---
title: Outlook の誤検出と検出漏れを報告する
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: レポート メッセージ機能を使用して、誤検知と誤Outlookを報告する方法について学習します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6f8c4fc327bfd467cdd1d0043c454e222e84125c
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625115"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="62fa6-103">Outlook の誤検出と検出漏れを報告する</span><span class="sxs-lookup"><span data-stu-id="62fa6-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="62fa6-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="62fa6-104">**Applies to**</span></span>
- [<span data-ttu-id="62fa6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="62fa6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="62fa6-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="62fa6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="62fa6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62fa6-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="62fa6-108">Exchange Online メールボックスを持つ Microsoft 365 組織の管理者である場合は、セキュリティ & コンプライアンス センターで申請ポータルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="62fa6-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="62fa6-109">詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62fa6-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="62fa6-110">ハイブリッドモダン認証を使用して Exchange Online Microsoft 365 またはオンプレミスのメールボックスにメールボックスを持つ Microsoft 365 組織では、誤検知 (ブロックまたは迷惑メール フォルダーに送信された良いメール) と誤検知 (受信トレイに配信された不要な電子メールまたはフィッシング) を Exchange Online Protection (EOP) に送信できます。</span><span class="sxs-lookup"><span data-stu-id="62fa6-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="62fa6-111">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="62fa6-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="62fa6-112">最適なユーザー申請エクスペリエンスを得る場合は、レポート メッセージ アドインまたはレポート フィッシング アドインを使用します。</span><span class="sxs-lookup"><span data-stu-id="62fa6-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="62fa6-113">このアドインは、web、iOS、Android、デスクトップOutlookのすべてのプラットフォームで機能します。</span><span class="sxs-lookup"><span data-stu-id="62fa6-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="62fa6-114">ユーザーがメールボックスを使用している組織の管理者Exchange Online、セキュリティ コンプライアンス センターの Submissions ポータル&使用します。</span><span class="sxs-lookup"><span data-stu-id="62fa6-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="62fa6-115">詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62fa6-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="62fa6-116">Microsoft、指定したメールボックス、または両方にメッセージを直接送信する構成が可能です。</span><span class="sxs-lookup"><span data-stu-id="62fa6-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="62fa6-117">詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="62fa6-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="62fa6-118">レポート メッセージまたはレポート フィッシング アドインを取得して有効にする方法の詳細については、「レポート メッセージを有効にする」または「レポート フィッシング アドイン」を [参照してください](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="62fa6-118">For more information on how to get and enable the Report Message or the Report Phishing add-ins, see [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="62fa6-119">Microsoft へのメッセージの報告の詳細については、「メッセージとファイルを Microsoft に報告 [する」を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="62fa6-119">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="62fa6-120">レポート メッセージ機能を使用する</span><span class="sxs-lookup"><span data-stu-id="62fa6-120">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="62fa6-121">迷惑メールとフィッシング メッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="62fa6-121">Report junk and phishing messages</span></span>

<span data-ttu-id="62fa6-122">迷惑メール以外の受信トレイまたは他のメール フォルダー内のメッセージの場合は、次の方法を使用してスパムメッセージとフィッシング メッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="62fa6-122">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="62fa6-123">選択した **メッセージの右上隅** にある [その他の操作] 楕円をクリックし、ドロップダウン メニューから [メッセージの報告] をクリックし、[迷惑メール] または [フィッシング]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62fa6-123">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="62fa6-124">![レポート メッセージ - その他のアクション](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="62fa6-124">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="62fa6-125">![レポート メッセージ - 迷惑メールとフィッシング](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="62fa6-125">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="62fa6-126">選択したメッセージは、分析のために Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="62fa6-126">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="62fa6-127">迷惑メールとして報告された場合は、迷惑メール フォルダーに移動しました。</span><span class="sxs-lookup"><span data-stu-id="62fa6-127">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="62fa6-128">フィッシングとして報告された場合に削除されます。</span><span class="sxs-lookup"><span data-stu-id="62fa6-128">Deleted if it was reported as phishing.</span></span>

### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="62fa6-129">迷惑メールではないメッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="62fa6-129">Report messages that are not junk</span></span>

1. <span data-ttu-id="62fa6-130">選択した **メッセージの右上隅** にある [その他のアクションの省略記号] をクリックし、ドロップダウン メニューから [メッセージの報告] をクリックし、[迷惑メールではない] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="62fa6-130">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="62fa6-131">![レポート メッセージ - その他のアクション](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="62fa6-131">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="62fa6-132">![レポート メッセージ - 迷惑メールではない](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="62fa6-132">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="62fa6-133">選択したメッセージは分析のために Microsoft に送信され、受信トレイまたは指定したその他のフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="62fa6-133">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="62fa6-134">報告されたメッセージの表示と確認</span><span class="sxs-lookup"><span data-stu-id="62fa6-134">View and review reported messages</span></span>

<span data-ttu-id="62fa6-135">ユーザーが Microsoft に報告するメッセージを確認するには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="62fa6-135">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="62fa6-136">管理者申請ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="62fa6-136">Use the Admin Submissions portal.</span></span> <span data-ttu-id="62fa6-137">詳細については [、「Microsoft へのユーザー申請の表示」を参照してください](admin-submission.md#view-user-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="62fa6-137">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="62fa6-138">報告されたメッセージのコピーを送信するメール フロー ルール (トランスポート ルールとも呼ばれる) を作成します。</span><span class="sxs-lookup"><span data-stu-id="62fa6-138">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="62fa6-139">手順については、「メール フロー ルールを使用して、ユーザーが Microsoft に報告している [情報を確認する」を参照してください](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="62fa6-139">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
