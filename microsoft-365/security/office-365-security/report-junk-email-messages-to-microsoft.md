---
title: スパム、非スパム、フィッシングメッセージを Microsoft に報告する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Microsoft Office Outlook 用迷惑メール報告アドインでは、次のような複数の方法で迷惑メール メッセージを報告できます。
ms.openlocfilehash: b7e7ed56f171ee3b74b36ed7c10c46286fb1e570
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033664"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="1935a-103">メッセージとファイルを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="1935a-103">Report messages and files to Microsoft</span></span>

<span data-ttu-id="1935a-104">Office 365 のユーザーおよび管理者 Exchange Online にメールボックスがある組織、または Exchange online のメールボックスを送信していないスタンドアロンの Exchange Online Protection (EOP) 組織では、メッセージを報告するためのいくつかの異なる方法があります。ファイルを Microsoft に。</span><span class="sxs-lookup"><span data-stu-id="1935a-104">Users and admins in Office 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes to submit email messages have several different methods for reporting messages and files to Microsoft.</span></span>

|||
|---|---|
|<span data-ttu-id="1935a-105">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="1935a-105">**Method**</span></span>|<span data-ttu-id="1935a-106">**説明**</span><span class="sxs-lookup"><span data-stu-id="1935a-106">**Description**</span></span>|
|[<span data-ttu-id="1935a-107">管理者提出を使用して、疑いのあるスパム、フィッシング、Url、およびファイルを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="1935a-107">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="1935a-108">これは、Exchange Online メールボックス (スタンドアロン EOP では使用できません) を持つ組織での管理者のための推奨レポート方法です。</span><span class="sxs-lookup"><span data-stu-id="1935a-108">This is the recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="1935a-109">Office 365 でレポートメッセージアドインを有効にする</span><span class="sxs-lookup"><span data-stu-id="1935a-109">Enable the Report Message add-in in Office 365</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="1935a-110">Outlook、outlook for Mac、および Outlook on the web で動作します。</span><span class="sxs-lookup"><span data-stu-id="1935a-110">Works with Outlook, Outlook for Mac, and Outlook on the web.</span></span> <span data-ttu-id="1935a-111">このアドインは推奨されています。</span><span class="sxs-lookup"><span data-stu-id="1935a-111">This is the recommended add-in.</span></span> <br/><br/> <span data-ttu-id="1935a-112">ライセンスに応じて、報告されたメッセージは[自動調査と応答 (AIR) の結果](air-view-investigation-results.md)、[ユーザーが報告したメッセージレポート](view-email-security-reports.md#user-reported-messages-report)および[脅威エクスプローラー](threat-explorer-views.md#email--submissions)で利用できます。</span><span class="sxs-lookup"><span data-stu-id="1935a-112">Depending on your license, the reported messages are available in [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report) and [Threat Explorer](threat-explorer-views.md#email--submissions).</span></span>|
|[<span data-ttu-id="1935a-113">Office 365 で Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する</span><span class="sxs-lookup"><span data-stu-id="1935a-113">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>](junk-email-reporting-add-in-for-microsoft-outlook.md)|<span data-ttu-id="1935a-114">Outlook でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="1935a-114">Only works in Outlook.</span></span>|
|[<span data-ttu-id="1935a-115">Office 365 の Outlook on the web で迷惑メールとフィッシング詐欺メールを報告する</span><span class="sxs-lookup"><span data-stu-id="1935a-115">Report junk and phishing email in Outlook on the web in Office 365</span></span>](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|<span data-ttu-id="1935a-116">Exchange Online のメールボックスを使用する組織では、web 上の Outlook の組み込み機能を使用します (スタンドアロン EOP では使用できません)。</span><span class="sxs-lookup"><span data-stu-id="1935a-116">Use the built-in capabilities in Outlook on the web for organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="1935a-117">マルウェアおよびマルウェアでないものを分析のために Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="1935a-117">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="1935a-118">Microsoft セキュリティインテリジェンスサイトを使用して、添付ファイルやその他のファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="1935a-118">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="1935a-119">スパムまたはフィッシングメッセージが配信されずに検疫された場合、ユーザーは Office 365 セキュリティ & コンプライアンスセンターの検疫ポータルから Microsoft にメッセージを報告できます。</span><span class="sxs-lookup"><span data-stu-id="1935a-119">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="1935a-120">詳細については、「 [Office 365 のユーザーとして、検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1935a-120">For details, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>