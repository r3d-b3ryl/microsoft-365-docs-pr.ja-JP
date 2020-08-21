---
title: Microsoft 365 でのエンドユーザー スパム通知
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
description: 管理者は、Exchange Online Protection (EOP) の検疫済みメッセージに対するエンドユーザー スパム通知について学習できます。
ms.openlocfilehash: 9e9c95fafe3610e0ad945f18aa85ff13342d8d65
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827363"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="facba-103">ユーザーのスパム通知を使って検疫済みメッセージを解放して報告する</span><span class="sxs-lookup"><span data-stu-id="facba-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="facba-104">Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。</span><span class="sxs-lookup"><span data-stu-id="facba-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="facba-105">詳細については [、EOP の検疫済みメッセージを参照してください](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="facba-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="facba-106">既定では、エンドユーザーのスパム通知はスパム対策ポリシーで無効になっています。</span><span class="sxs-lookup"><span data-stu-id="facba-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="facba-107">管理者がエンド [ユーザー向けスパム通知を有効にすると、](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)受信者 (自動マッピングが有効になっている共有メールボックスを含む) は、スパム、バルク メール、(2020 年 4 月に) フィッシングとして検疫されたメッセージに関する定期的な通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="facba-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="facba-108">共有メールボックスでは、エンド ユーザーのスパム通知は、共有メールボックスへの FullAccess アクセス許可が付与されたユーザーに対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="facba-108">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="facba-109">詳細については [、「EAC を使用して共有メールボックスの委任を編集する」を参照してください](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)。</span><span class="sxs-lookup"><span data-stu-id="facba-109">For more information, see [Use the EAC to edit shared mailbox delegation](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="facba-110">エンド ユーザー スパム通知は、グループではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="facba-110">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="facba-111">高信頼フィッシング、マルウェア、またはメール フロー ルール (別名: トランスポート ルール) によって検疫されたメッセージは、管理者のみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="facba-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="facba-112">詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="facba-112">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="facba-113">エンド ユーザー向けスパム通知には、検疫された各メッセージについて次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="facba-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="facba-114">**送信者**: 検疫されたメッセージの送信名と電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="facba-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="facba-115">**件**名: 検疫済みメッセージの件名行テキスト。</span><span class="sxs-lookup"><span data-stu-id="facba-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="facba-116">**日付**: メッセージが検疫された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="facba-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="facba-117">**[受信拒否**] : このリンクをクリックして、その送信者を受信拒否リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="facba-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="facba-118">詳細については、「メールの送信者 [をブロックする」を参照してください](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。</span><span class="sxs-lookup"><span data-stu-id="facba-118">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="facba-119">**リリース**: スパム (フィッシングでない) メッセージに関しては、セキュリティ センターのセキュリティ センターを検疫しなくても、メッセージ&解放できます。</span><span class="sxs-lookup"><span data-stu-id="facba-119">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="facba-120">\*\*[Review](** 確認): このリンクをクリックしてセキュリティ & コンプライアンス センターの [検疫] に移動します。このセンターは、(メッセージが検疫された理由によって異なる) ビュー、解放、または報告できます。</span><span class="sxs-lookup"><span data-stu-id="facba-120">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="facba-121">詳細については、「EOP でユーザーとして [検疫済みメッセージを検索して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="facba-121">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![エンド ユーザー向けスパム通知の例](../../media/end-user-spam-notification.png)
