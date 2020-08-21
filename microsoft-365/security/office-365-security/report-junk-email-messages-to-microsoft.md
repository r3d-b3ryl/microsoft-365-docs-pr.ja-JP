---
title: スパム、非スパム、フィッシングのメッセージを Microsoft に報告する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 管理者は、優れたメッセージと不良なメッセージとファイルを分析用として Microsoft に報告するさまざまな方法について学習できます。
ms.openlocfilehash: fabe28d084361041ae9e6a8d118dd8c43c2225f7
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827643"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="ea595-103">メッセージとファイルを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="ea595-103">Report messages and files to Microsoft</span></span>

<span data-ttu-id="ea595-104">Exchange Online にメールボックスがある Microsoft 365 組織、または Exchange Online メールボックスを使用しているスタンドアロン Exchange Online Protection (EOP) 組織では、ユーザーと管理者の両方が、電子メール メッセージとファイルを Microsoft に報告するさまざまな方法を使用しています。</span><span class="sxs-lookup"><span data-stu-id="ea595-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, both users and admins have several different methods for reporting email messages and files to Microsoft.</span></span>

****

|<span data-ttu-id="ea595-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ea595-105">Method</span></span>|<span data-ttu-id="ea595-106">説明</span><span class="sxs-lookup"><span data-stu-id="ea595-106">Description</span></span>|
|---|---|
|[<span data-ttu-id="ea595-107">管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="ea595-107">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="ea595-108">Exchange Online メールボックスを使用している組織の管理者向けの推奨レポート方式 (スタンドアロン EOP では使用不可)。</span><span class="sxs-lookup"><span data-stu-id="ea595-108">The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="ea595-109">レポート メッセージ アドインを有効にする</span><span class="sxs-lookup"><span data-stu-id="ea595-109">Enable the Report Message add-in</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="ea595-110">Outlook、Outlook for Mac、および Outlook on the web (Outlook Web App) を操作するもので、推奨されるアドインです。</span><span class="sxs-lookup"><span data-stu-id="ea595-110">Works with Outlook, Outlook for Mac, and Outlook on the web (formerly known as Outlook Web App), and is the recommended add-in.</span></span> <br/><br/> <span data-ttu-id="ea595-111">サブスクリプションによっては、アドインで報告されたユーザーのメッセージは[管理の送信ポータル](admin-submission.md)[、AIR (自動調査および応答 )、ユーザー](air-view-investigation-results.md)から報告されたメッセージ レポート、脅威[User-reported messages report](view-email-security-reports.md#user-reported-messages-report)[エクスプローラーで確認できます](threat-explorer-views.md#email--submissions)。</span><span class="sxs-lookup"><span data-stu-id="ea595-111">Depending on your subscription, messages that users reported with the add-in are available in [the Admin Submissions portal](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Threat Explorer](threat-explorer-views.md#email--submissions).</span></span> <br/><br/> <span data-ttu-id="ea595-112">報告されたメッセージを、指定したメールボックスにコピーまたはリダイレクトする構成ができます。</span><span class="sxs-lookup"><span data-stu-id="ea595-112">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="ea595-113">詳細については、「EOP でスパム [やフィッシング メッセージのユーザーを送信するためのメールボックスを指定する」を参照してください](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="ea595-113">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in EOP](user-submission.md).</span></span>|
|[<span data-ttu-id="ea595-114">Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する</span><span class="sxs-lookup"><span data-stu-id="ea595-114">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>](junk-email-reporting-add-in-for-microsoft-outlook.md)|<span data-ttu-id="ea595-115">Outlook でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="ea595-115">Only works in Outlook.</span></span>|
|[<span data-ttu-id="ea595-116">Outlook on the web で迷惑メールとフィッシング メールを報告する</span><span class="sxs-lookup"><span data-stu-id="ea595-116">Report junk and phishing email in Outlook on the web</span></span>](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|<span data-ttu-id="ea595-117">Exchange Online メールボックスを使用している組織には、Web 上の Outlook の組み込み機能を使用します (スタンドアロン EOP では使用できません)。</span><span class="sxs-lookup"><span data-stu-id="ea595-117">Use the built-in capabilities in Outlook on the web for organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span> <br/><br/> <span data-ttu-id="ea595-118">ユーザー レポートに表示されるメッセージは、 [管理の送信ポータルで確認できます](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="ea595-118">Messages that users report are available in [the Admin Submissions portal](admin-submission.md).</span></span> <br/><br/> <span data-ttu-id="ea595-119">報告されたメッセージを、指定したメールボックスにコピーまたはリダイレクトする構成ができます。</span><span class="sxs-lookup"><span data-stu-id="ea595-119">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="ea595-120">詳細については [、Exchange Online でスパムやフィッシングのメッセージを送信するためのメールボックスを指定する方法を参照してください](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="ea595-120">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange online](user-submission.md).</span></span>|
|[<span data-ttu-id="ea595-121">分析用に Microsoft に手動でメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="ea595-121">Manually submit messages to Microsoft for analysis</span></span>](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|<span data-ttu-id="ea595-122">スパムやフィッシング処理は、スパムおよびフィッシングでない特定の Microsoft 電子メール アドレスに手動で送信します。</span><span class="sxs-lookup"><span data-stu-id="ea595-122">Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing.</span></span>|
|[<span data-ttu-id="ea595-123">メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する</span><span class="sxs-lookup"><span data-stu-id="ea595-123">Use mail flow rules to see what your users are reporting to Microsoft</span></span>](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|<span data-ttu-id="ea595-124">ユーザーが分析を行うときに Microsoft にメッセージを報告するときにユーザーに知示すメール フロー ルール (トランスポート ルールとも呼ばれる) を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea595-124">Learn how to create a mail flow rule (also known as a transport rule) that notifies you when users report messages to Microsoft for analysis.</span></span>
|||
|[<span data-ttu-id="ea595-125">マルウェアおよびマルウェアでないファイルを分析のために Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="ea595-125">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="ea595-126">Microsoft セキュリティ インテリジェンス サイトを使用して添付ファイルおよびその他のファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="ea595-126">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="ea595-127">スパムまたはフィッシングのメッセージが配信ではなく検疫された場合、ユーザーはメッセージをセキュリティ & コンプライアンス センターの検疫ポータルから Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="ea595-127">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Security & Compliance Center.</span></span> <span data-ttu-id="ea595-128">詳細については [、「Microsoft 365 のユーザーとして検疫済みメッセージを検索して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="ea595-128">For details, see [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>
