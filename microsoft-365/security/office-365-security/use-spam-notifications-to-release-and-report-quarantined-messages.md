---
title: Office 36 でのエンドユーザースパム通知
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
description: 管理者がスパム対策ポリシーでエンドユーザーのスパム通知を有効にすると、メッセージの受信者は検疫済みメッセージに関する定期的な通知を受信します。
ms.openlocfilehash: 67dbf311c37ae61c007b78110522033d79c0b161
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857147"
---
# <a name="end-user-spam-notifications-in-office-365"></a><span data-ttu-id="8201b-103">Office 365 でのエンドユーザースパム通知</span><span class="sxs-lookup"><span data-stu-id="8201b-103">End-user spam notifications in Office 365</span></span>

<span data-ttu-id="8201b-104">検疫は、exchange online またはスタンドアロンの exchange online Protection (EOP) 組織内のメールボックスを使用する Office 365 組織で潜在的に危険または不要なメッセージを保持します。 exchange online メールボックスはありません。</span><span class="sxs-lookup"><span data-stu-id="8201b-104">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="8201b-105">詳細については、「 [Quarantine In Office 365](quarantine-email-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8201b-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="8201b-106">既定では、エンドユーザーのスパム通知はスパム対策ポリシーで無効になっています。</span><span class="sxs-lookup"><span data-stu-id="8201b-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="8201b-107">管理者が[エンドユーザーのスパム通知を有効](configure-your-spam-filter-policies.md)にした場合、メッセージの受信者は、スパム、バルクメール、または (4 月 2020) フィッシングとして検疫されたメッセージに関する定期的な通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="8201b-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md), message recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="8201b-108">2019年10月に、検疫済みメッセージをエンドユーザーのスパム通知から直接解放する機能が削除されました。</span><span class="sxs-lookup"><span data-stu-id="8201b-108">In October 2019, we removed the ability to release quarantined messages directly from end-user spam notifications.</span></span> <span data-ttu-id="8201b-109">その代わりに、ユーザーは Office 365 セキュリティ & コンプライアンスセンターに移動して、検疫済みメッセージを (直接、または通知で [**レビュー** ] をクリックすることで) 解放できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8201b-109">Instead, users can now go to the Office 365 Security & Compliance Center to release their quarantined messages (either directly, or by clicking **Review** in the notification).</span></span> <span data-ttu-id="8201b-110">詳細については、「 [Office 365 のユーザーとして、検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8201b-110">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span> <br/><br/> <span data-ttu-id="8201b-111">高信頼フィッシング、マルウェア、またはメールフロールール (トランスポートルールとも呼ばれます) として検疫されたメッセージは、管理者のみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="8201b-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="8201b-112">詳細については、「 [Office 365 の管理者として検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-an-administrator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8201b-112">For more information, see [Find and release quarantined messages as an admin in Office 365](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>

<span data-ttu-id="8201b-113">エンドユーザーのスパム通知には、検疫済みメッセージごとに次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8201b-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="8201b-114">**Sender**: 検疫されたメッセージの送信者名と電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="8201b-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="8201b-115">**Subject**: 検疫されたメッセージの件名のテキスト。</span><span class="sxs-lookup"><span data-stu-id="8201b-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="8201b-116">**日付**: メッセージが検疫された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="8201b-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="8201b-117">[**送信者のブロック**]: このリンクをクリックして、受信拒否リストに送信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="8201b-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span>

- <span data-ttu-id="8201b-118">**レビュー**: このリンクをクリックすると、セキュリティ & コンプライアンスセンターの検疫に移動し、検疫済みメッセージをリリース、削除、または報告することができます。</span><span class="sxs-lookup"><span data-stu-id="8201b-118">**Review**: Click this link to go the the Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span>

![エンドユーザーのスパム通知の例](../../media/end-user-spam-notification.png)
