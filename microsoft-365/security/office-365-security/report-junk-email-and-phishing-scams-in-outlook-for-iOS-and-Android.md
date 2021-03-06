---
title: Outlook for iOS および Android で迷惑メールとフィッシングメールを報告する
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理者は、Outlook for iOS と Android の組み込みの迷惑メール、迷惑メール、フィッシングメールレポートのオプションについて学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e6e63f534a9f9516c6e1a87ff82d5b0916d25778
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509328"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="a506c-103">Exchange Online で Outlook for iOS と Android で迷惑メールとフィッシングメールを報告する</span><span class="sxs-lookup"><span data-stu-id="a506c-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a506c-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="a506c-104">**Applies to**</span></span>
- [<span data-ttu-id="a506c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a506c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a506c-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="a506c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a506c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a506c-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="a506c-108">ハイブリッドモダン認証を使用して Exchange Online またはオンプレミスメールボックスにメールボックスを持つ[](../../enterprise/hybrid-modern-auth-overview.md)Microsoft 365 組織では、誤検知 (スパムとしてマークされた良いメール)、偽陰性 (悪い電子メールが許可されている)、フィッシング メッセージを Exchange Online Protection (EOP) に送信できます。</span><span class="sxs-lookup"><span data-stu-id="a506c-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a506c-109">開始する前に知る必要があるもの</span><span class="sxs-lookup"><span data-stu-id="a506c-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="a506c-110">最適なユーザー申請エクスペリエンスを得る場合は、レポート メッセージとレポート フィッシング アドインを使用することをお勧めします。詳細 [については、「レポート メッセージ アドインを有効](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) にする」および「レポート フィッシング アドインを [有効にする」](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a506c-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) and [Enable the Report Phishing add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) for more information.</span></span>

- <span data-ttu-id="a506c-111">Exchange Online メールボックスを使用している組織の管理者の場合は、セキュリティ コンプライアンス センターの申請ポータルを使用&勧めします。</span><span class="sxs-lookup"><span data-stu-id="a506c-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="a506c-112">詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a506c-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="a506c-113">指定したメールボックスにコピーまたはリダイレクトするレポート メッセージを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a506c-113">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="a506c-114">詳細については [、「User Submissions ポリシー」を参照してください](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="a506c-114">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="a506c-115">Microsoft へのメッセージの報告の詳細については、「メッセージとファイルを Microsoft に報告 [する」を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="a506c-115">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a506c-116">ユーザー申請ポリシーで Outlook の迷惑メールレポートが無効になっている場合、迷惑メールまたはフィッシング メッセージは迷惑メール フォルダーに移動され、管理者または Microsoft には報告されません。</span><span class="sxs-lookup"><span data-stu-id="a506c-116">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>
