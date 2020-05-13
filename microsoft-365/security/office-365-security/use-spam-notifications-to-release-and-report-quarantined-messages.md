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
description: 管理者は、Exchange Online Protection (EOP) で検疫されたメッセージのエンドユーザースパム通知について知ることができます。
ms.openlocfilehash: 7dd6b2d14bbb4a1771c59c8a1e654e36f0f83d3e
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208551"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="e86f6-103">ユーザースパム通知を使用して、検疫済みメッセージを解放して報告する</span><span class="sxs-lookup"><span data-stu-id="e86f6-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="e86f6-104">Exchange online またはスタンドアロンの exchange Online Protection (EOP) 組織にメールボックスがあり、Exchange online メールボックスがない場合、検疫は潜在的に危険または不要なメッセージを保持します。365</span><span class="sxs-lookup"><span data-stu-id="e86f6-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="e86f6-105">詳細については、「 [EOP での検疫済みメッセージ](quarantine-email-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e86f6-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="e86f6-106">既定では、エンドユーザーのスパム通知はスパム対策ポリシーで無効になっています。</span><span class="sxs-lookup"><span data-stu-id="e86f6-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="e86f6-107">管理者が[エンドユーザーのスパム通知を有効](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)にすると、受信者はスパム、バルクメール、または (2020 年4月の) フィッシングとして検疫されたメッセージに関する定期的な通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="e86f6-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="e86f6-108">高信頼フィッシング、マルウェア、またはメールフロールール (トランスポートルールとも呼ばれます) として検疫されたメッセージは、管理者のみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="e86f6-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="e86f6-109">詳細については、「 [EOP で管理者として検疫済みメッセージおよびファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e86f6-109">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="e86f6-110">エンドユーザーのスパム通知には、検疫済みメッセージごとに次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e86f6-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="e86f6-111">**Sender**: 検疫されたメッセージの送信者名と電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="e86f6-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="e86f6-112">**Subject**: 検疫されたメッセージの件名のテキスト。</span><span class="sxs-lookup"><span data-stu-id="e86f6-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="e86f6-113">**日付**: メッセージが検疫された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="e86f6-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="e86f6-114">[**送信者のブロック**]: このリンクをクリックして、受信拒否リストに送信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="e86f6-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="e86f6-115">詳細については、「 [Outlook でメール送信者をブロックする](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e86f6-115">For more information, see [Block a mail sender in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="e86f6-116">**Release**: スパム (フィッシングではない) メッセージに対して、セキュリティ & コンプライアンスセンターの検疫を行わずに、ここでメッセージを解放することができます。</span><span class="sxs-lookup"><span data-stu-id="e86f6-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="e86f6-117">**レビュー**: このリンクをクリックすると、セキュリティ & コンプライアンスセンターで、検疫済みメッセージのリリース、削除、またはレポート作成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e86f6-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="e86f6-118">詳細については、「 [EOP でユーザーとして検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e86f6-118">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![エンドユーザーのスパム通知の例](../../media/end-user-spam-notification.png)
