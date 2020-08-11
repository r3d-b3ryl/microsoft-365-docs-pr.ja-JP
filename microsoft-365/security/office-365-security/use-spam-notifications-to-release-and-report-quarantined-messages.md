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
ms.openlocfilehash: b196a9e11d54d9d86acc991ba877279f1fa3d115
ms.sourcegitcommit: 51f040a4edb8dd52521a5d7b0f7a975986a1af10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "46608301"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="410a9-103">ユーザースパム通知を使用して、検疫済みメッセージを解放して報告する</span><span class="sxs-lookup"><span data-stu-id="410a9-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="410a9-104">Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。</span><span class="sxs-lookup"><span data-stu-id="410a9-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="410a9-105">詳細については、「 [EOP での検疫済みメッセージ](quarantine-email-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="410a9-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="410a9-106">既定では、エンドユーザーのスパム通知はスパム対策ポリシーで無効になっています。</span><span class="sxs-lookup"><span data-stu-id="410a9-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="410a9-107">管理者が[エンドユーザーのスパム通知を有効](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)にすると、受信者 (自動マッピングが有効になっている共有メールボックスを含む) は、スパム、バルクメール、または (2020 年4月の) フィッシングとして検疫されたメッセージに関する定期的な通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="410a9-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="410a9-108">高信頼フィッシング、マルウェア、またはメールフロールール (トランスポートルールとも呼ばれます) として検疫されたメッセージは、管理者のみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="410a9-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="410a9-109">詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="410a9-109">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="410a9-110">エンドユーザーのスパム通知には、検疫済みメッセージごとに次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="410a9-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="410a9-111">**Sender**: 検疫されたメッセージの送信者名と電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="410a9-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="410a9-112">**Subject**: 検疫されたメッセージの件名のテキスト。</span><span class="sxs-lookup"><span data-stu-id="410a9-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="410a9-113">**日付**: メッセージが検疫された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="410a9-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="410a9-114">[**送信者のブロック**]: このリンクをクリックして、受信拒否リストに送信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="410a9-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="410a9-115">詳細については、「[メールの送信者をブロックする](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="410a9-115">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="410a9-116">**Release**: スパム (フィッシング詐欺ではない) メッセージに対して、セキュリティ & コンプライアンスセンターの検疫を行わずに、ここでメッセージを解放することができます。</span><span class="sxs-lookup"><span data-stu-id="410a9-116">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="410a9-117">**レビュー**: このリンクをクリックすると、セキュリティ & コンプライアンスセンターの [検疫] に移動します (メッセージが検疫された理由によっては、検疫済みメッセージの表示、リリース、削除、または報告を行うことができます)。</span><span class="sxs-lookup"><span data-stu-id="410a9-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="410a9-118">詳細については、「 [EOP でユーザーとして検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="410a9-118">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![エンドユーザーのスパム通知の例](../../media/end-user-spam-notification.png)
