---
title: スパム、非スパム、フィッシングメッセージを Microsoft に報告する
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
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 管理者は、問題のあるメッセージを Microsoft に報告するさまざまな方法について説明します。
ms.openlocfilehash: 4578e3d29a89e94d23c04e4d80e45c79c18cfb85
ms.sourcegitcommit: 1d5db6e8411b45d0dd1c517339074c2840e33a63
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/10/2020
ms.locfileid: "43216877"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="ee5cf-103">メッセージとファイルを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="ee5cf-103">Report messages and files to Microsoft</span></span>

<span data-ttu-id="ee5cf-104">Office 365 のユーザーおよび管理者 Exchange Online にメールボックスがある組織、または Exchange Online メールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) 組織では、メッセージとファイルを Microsoft に報告する方法がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="ee5cf-104">Users and admins in Office 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes have several different methods for reporting messages and files to Microsoft.</span></span>

|||
|---|---|
|<span data-ttu-id="ee5cf-105">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="ee5cf-105">**Method**</span></span>|<span data-ttu-id="ee5cf-106">**説明**</span><span class="sxs-lookup"><span data-stu-id="ee5cf-106">**Description**</span></span>|
|[<span data-ttu-id="ee5cf-107">管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="ee5cf-107">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="ee5cf-108">Exchange Online メールボックスを使用する組織での管理者に推奨される報告方法 (スタンドアロン EOP では利用できません)。</span><span class="sxs-lookup"><span data-stu-id="ee5cf-108">The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="ee5cf-109">Office 365 でレポートメッセージアドインを有効にする</span><span class="sxs-lookup"><span data-stu-id="ee5cf-109">Enable the Report Message add-in in Office 365</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="ee5cf-110">Outlook、Outlook for Mac、および web 上の Outlook (旧称 Outlook Web App) と共に動作し、推奨されるアドインです。</span><span class="sxs-lookup"><span data-stu-id="ee5cf-110">Works with Outlook, Outlook for Mac, and Outlook on the web (formerly known as Outlook Web App), and is the recommended add-in.</span></span> <br/><br/> <span data-ttu-id="ee5cf-111">サブスクリプションによっては、ユーザーがアドインで報告したメッセージが、自動化された[調査と応答 (航空) 結果](air-view-investigation-results.md)、[ユーザーが報告したメッセージレポート](view-email-security-reports.md#user-reported-messages-report)、および[脅威エクスプローラー](threat-explorer-views.md#email--submissions)で利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ee5cf-111">Depending on your subscription, messages that users reported with the add-in are available in [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Threat Explorer](threat-explorer-views.md#email--submissions).</span></span>|
|[<span data-ttu-id="ee5cf-112">Office 365 で Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する</span><span class="sxs-lookup"><span data-stu-id="ee5cf-112">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>](junk-email-reporting-add-in-for-microsoft-outlook.md)|<span data-ttu-id="ee5cf-113">Outlook でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="ee5cf-113">Only works in Outlook.</span></span>|
|[<span data-ttu-id="ee5cf-114">Office 365 の Outlook on the web で迷惑メールとフィッシング詐欺メールを報告する</span><span class="sxs-lookup"><span data-stu-id="ee5cf-114">Report junk and phishing email in Outlook on the web in Office 365</span></span>](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|<span data-ttu-id="ee5cf-115">Exchange Online のメールボックスを使用する組織では、web 上の Outlook の組み込み機能を使用します (スタンドアロン EOP では使用できません)。</span><span class="sxs-lookup"><span data-stu-id="ee5cf-115">Use the built-in capabilities in Outlook on the web for organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="ee5cf-116">分析のためにメッセージを手動で Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="ee5cf-116">Manually submit messages to Microsoft for analysis</span></span>](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|<span data-ttu-id="ee5cf-117">スパムやフィッシングではなく、特定の Microsoft 電子メールアドレスに、添付されたメッセージを手動で送信します。</span><span class="sxs-lookup"><span data-stu-id="ee5cf-117">Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing.</span></span> <br/><br/> <span data-ttu-id="ee5cf-118">また、ユーザーがこれらのレポート電子メールアドレスにメッセージを送信するときに通知するメールフロールール (トランスポートルールとも呼ばれます) を作成する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="ee5cf-118">Also learn how to create a mail flow rule (also known as a transport rule) that notifies you when users send messages to these reporting email addresses.</span></span>|
|[<span data-ttu-id="ee5cf-119">マルウェアおよびマルウェアでないものを分析のために Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="ee5cf-119">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="ee5cf-120">Microsoft セキュリティインテリジェンスサイトを使用して、添付ファイルやその他のファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="ee5cf-120">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="ee5cf-121">スパムまたはフィッシングメッセージが配信されずに検疫された場合、ユーザーは Office 365 セキュリティ & コンプライアンスセンターの検疫ポータルから Microsoft にメッセージを報告できます。</span><span class="sxs-lookup"><span data-stu-id="ee5cf-121">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="ee5cf-122">詳細については、「 [Office 365 のユーザーとして、検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee5cf-122">For details, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>