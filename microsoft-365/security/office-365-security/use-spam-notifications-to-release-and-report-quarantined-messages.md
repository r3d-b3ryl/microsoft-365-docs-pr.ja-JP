---
title: Microsoft 365 でのエンドユーザースパム通知
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: この記事では、検疫済みメッセージのエンドユーザースパム通知について説明します。
ms.openlocfilehash: 2a865130bf1fa0c09b5b68254fb604795b204c22
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035000"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="032b3-103">ユーザースパム通知を使用して、検疫済みメッセージを解放して報告する</span><span class="sxs-lookup"><span data-stu-id="032b3-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="032b3-104">検疫を実行すると、Exchange Online メールボックスを使用している Microsoft 365 組織や、Exchange Online メールボックスを使用していないスタンドアロン Exchange Online Protection (EOP) 組織の危険性の高いメッセージや不要なメッセージが保留にされます。</span><span class="sxs-lookup"><span data-stu-id="032b3-104">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="032b3-105">詳細については、「[Office 365 での検疫](quarantine-email-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="032b3-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="032b3-106">既定では、エンドユーザーのスパム通知はスパム対策ポリシーで無効になっています。</span><span class="sxs-lookup"><span data-stu-id="032b3-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="032b3-107">管理者が[エンドユーザーのスパム通知を有効](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)にすると、受信者はスパム、バルクメール、または (4 月 2020) フィッシングとして検疫されたメッセージに関する定期的な通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="032b3-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="032b3-108">高信頼フィッシング、マルウェア、またはメールフロールール (トランスポートルールとも呼ばれます) として検疫されたメッセージは、管理者のみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="032b3-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="032b3-109">詳細については、「[Office 365 の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="032b3-109">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="032b3-110">エンドユーザーのスパム通知には、検疫済みメッセージごとに次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="032b3-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="032b3-111">**Sender**: 検疫されたメッセージの送信者名と電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="032b3-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="032b3-112">**Subject**: 検疫されたメッセージの件名のテキスト。</span><span class="sxs-lookup"><span data-stu-id="032b3-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="032b3-113">**日付**: メッセージが検疫された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="032b3-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="032b3-114">[**送信者のブロック**]: このリンクをクリックして、受信拒否リストに送信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="032b3-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="032b3-115">詳細については、「 [Outlook でメール送信者をブロックする](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="032b3-115">For more information, see [Block a mail sender in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="032b3-116">**Release**: スパム (フィッシングではない) メッセージに対して、セキュリティ & コンプライアンスセンターの検疫を行わずに、ここでメッセージを解放することができます。</span><span class="sxs-lookup"><span data-stu-id="032b3-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="032b3-117">**レビュー**: このリンクをクリックすると、セキュリティ & コンプライアンスセンターで、検疫済みメッセージのリリース、削除、またはレポート作成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="032b3-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="032b3-118">詳細については、「 [Office 365 のユーザーとして、検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="032b3-118">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![エンドユーザーのスパム通知の例](../../media/end-user-spam-notification.png)
