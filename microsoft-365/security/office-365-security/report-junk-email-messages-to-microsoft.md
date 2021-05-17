---
title: スパム、非スパム、フィッシング メッセージを Microsoft に報告する
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 管理者は、良いメッセージと悪いメッセージやファイルを分析のために Microsoft に報告するさまざまな方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8c87938a8716da36f027300d685f0caedcf69660
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291129"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="c12ee-103">メッセージとファイルを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="c12ee-103">Report messages and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c12ee-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c12ee-104">**Applies to**</span></span>
- [<span data-ttu-id="c12ee-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c12ee-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c12ee-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="c12ee-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c12ee-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c12ee-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c12ee-108">Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、ユーザーと管理者の両方が、電子メール メッセージとファイルを Microsoft に報告するさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="c12ee-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, both users and admins have several different methods for reporting email messages and files to Microsoft.</span></span>

****

|<span data-ttu-id="c12ee-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="c12ee-109">Method</span></span>|<span data-ttu-id="c12ee-110">説明</span><span class="sxs-lookup"><span data-stu-id="c12ee-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="c12ee-111">管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="c12ee-111">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="c12ee-112">管理者がメールボックスを使用している組織の管理者Exchange Online推奨されるレポート方法 (スタンドアロン EOP では使用できません)。</span><span class="sxs-lookup"><span data-stu-id="c12ee-112">The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="c12ee-113">レポート メッセージまたはレポートフィッシング アドインを有効にする</span><span class="sxs-lookup"><span data-stu-id="c12ee-113">Enable the Report Message or the Report Phishing add-ins</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="c12ee-114">Web 上OutlookおよびOutlookを使用します (以前は[Outlook Web App] と呼Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="c12ee-114">Works with Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <p> <span data-ttu-id="c12ee-115">サブスクリプションに応じて、ユーザーがアドインで報告したメッセージは[、Admin Submissions ポータル](admin-submission.md)、自動調査と応答[(AIR)](air-view-investigation-results.md)の結果、ユーザーが報告[](view-email-security-reports.md#user-reported-messages-report)したメッセージ レポート、および脅威エクスプローラーで[利用できます](threat-explorer-views.md#email--submissions)。</span><span class="sxs-lookup"><span data-stu-id="c12ee-115">Depending on your subscription, messages that users reported with the add-ins are available in [the Admin Submissions portal](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Threat Explorer](threat-explorer-views.md#email--submissions).</span></span> <p> <span data-ttu-id="c12ee-116">指定したメールボックスにコピーまたはリダイレクトするレポート メッセージを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c12ee-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="c12ee-117">詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="c12ee-117">For more information, see [User submissions policies](user-submission.md).</span></span>
|[<span data-ttu-id="c12ee-118">誤検知と誤検知を報告して、Outlook</span><span class="sxs-lookup"><span data-stu-id="c12ee-118">Report false positives and false negatives to Outlook</span></span>](report-false-positives-and-false-negatives.md)|<span data-ttu-id="c12ee-119">レポート メッセージ機能を使用して、誤検知 (迷惑メール フォルダーにブロックまたは送信された良い電子メール) と誤検知 (受信トレイに配信された不要な電子メールまたはフィッシング) を Exchange Online Protection (EOP) に送信します。</span><span class="sxs-lookup"><span data-stu-id="c12ee-119">Submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP) using the Report Message feature.</span></span>|
|[<span data-ttu-id="c12ee-120">分析のために Microsoft にメッセージを手動で送信する</span><span class="sxs-lookup"><span data-stu-id="c12ee-120">Manually submit messages to Microsoft for analysis</span></span>](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|<span data-ttu-id="c12ee-121">スパムやフィッシングではなく、スパムのために、添付されたメッセージを特定の Microsoft の電子メール アドレスに手動で送信します。</span><span class="sxs-lookup"><span data-stu-id="c12ee-121">Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing.</span></span>|
|[<span data-ttu-id="c12ee-122">メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する</span><span class="sxs-lookup"><span data-stu-id="c12ee-122">Use mail flow rules to see what your users are reporting to Microsoft</span></span>](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|<span data-ttu-id="c12ee-123">ユーザーが分析のために Microsoft にメッセージを報告したときに通知するメール フロー ルール (トランスポート ルールとも呼ばれる) を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c12ee-123">Learn how to create a mail flow rule (also known as a transport rule) that notifies you when users report messages to Microsoft for analysis.</span></span>|
|[<span data-ttu-id="c12ee-124">分析のためにマルウェアとマルウェア以外のファイルを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="c12ee-124">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="c12ee-125">添付ファイルや他Microsoft セキュリティ インテリジェンス送信するには、このサイトを使用します。</span><span class="sxs-lookup"><span data-stu-id="c12ee-125">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|

<span data-ttu-id="c12ee-126">スパムメッセージまたはフィッシング メッセージが配信される代わりに検疫された場合、ユーザーはセキュリティ コンプライアンス センターの検疫ポータルから Microsoft にメッセージ&できます。</span><span class="sxs-lookup"><span data-stu-id="c12ee-126">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Security & Compliance Center.</span></span> <span data-ttu-id="c12ee-127">詳細については、「検疫済み[メッセージをユーザーとして](find-and-release-quarantined-messages-as-a-user.md)検索して解放する」を参照Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c12ee-127">For details, see [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c12ee-128">Microsoft への提出からのデータは、北米のOffice 365コンプライアンス境界に存在します。</span><span class="sxs-lookup"><span data-stu-id="c12ee-128">Data from submissions to Microsoft resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="c12ee-129">データは、フィルターの有効性を向上させるために、エンジニアリング チームのアナリストによって確認されます。</span><span class="sxs-lookup"><span data-stu-id="c12ee-129">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>
