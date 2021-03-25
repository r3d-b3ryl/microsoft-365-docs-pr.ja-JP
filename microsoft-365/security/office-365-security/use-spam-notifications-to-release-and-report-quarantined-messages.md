---
title: Microsoft 365 のエンド ユーザースパム通知
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
description: 管理者は、Exchange Online Protection (EOP) で検疫されたメッセージに対するエンド ユーザーのスパム通知について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9cff91be399bd98eb7e6e5a2a6d91a4a8bb602ec
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206082"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="ce881-103">ユーザーのスパム通知を使用して検疫済みメッセージを解放および報告する</span><span class="sxs-lookup"><span data-stu-id="ce881-103">Use user spam notifications to release and report quarantined messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ce881-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="ce881-104">**Applies to**</span></span>
- [<span data-ttu-id="ce881-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ce881-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ce881-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="ce881-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ce881-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ce881-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ce881-108">Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。</span><span class="sxs-lookup"><span data-stu-id="ce881-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="ce881-109">詳細については [、「EOP の検疫済みメッセージ」を参照してください](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="ce881-109">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="ce881-110">既定では、エンド ユーザーのスパム通知はスパム対策ポリシーで無効になっています。</span><span class="sxs-lookup"><span data-stu-id="ce881-110">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="ce881-111">管理者がエンド[](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)ユーザーのスパム通知を有効にすると、受信者 (自動マッピングが有効な共有メールボックスを含む) は、スパム、バルク メール、または (2020 年 4 月現在) フィッシングとして検疫されたメッセージに関する定期的な通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="ce881-111">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="ce881-112">共有メールボックスの場合、エンド ユーザーのスパム通知は、共有メールボックスに対する FullAccess アクセス許可が付与されたユーザーにのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ce881-112">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="ce881-113">詳細については [、「EAC を使用して共有メールボックスの委任を編集する」を参照してください](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)。</span><span class="sxs-lookup"><span data-stu-id="ce881-113">For more information, see [Use the EAC to edit shared mailbox delegation](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="ce881-114">エンド ユーザースパム通知は、グループではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ce881-114">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="ce881-115">信頼度の高いフィッシング、マルウェア、またはメール フロー ルール (トランスポート ルールとも呼ばれる) によって検疫されたメッセージは、管理者だけが使用できます。</span><span class="sxs-lookup"><span data-stu-id="ce881-115">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="ce881-116">詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce881-116">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="ce881-117">エンド ユーザーのスパム通知には、検疫されたメッセージごとに次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce881-117">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="ce881-118">**Sender**: 検疫済みメッセージの送信名と電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="ce881-118">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="ce881-119">**件名**: 検疫済みメッセージの件名テキスト。</span><span class="sxs-lookup"><span data-stu-id="ce881-119">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="ce881-120">**日付**: メッセージが検疫された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="ce881-120">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="ce881-121">**[送信者のブロック**] : このリンクをクリックして、送信者を [受信拒否] リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="ce881-121">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="ce881-122">詳細については、「メール送信者を [ブロックする」を参照してください](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。</span><span class="sxs-lookup"><span data-stu-id="ce881-122">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="ce881-123">**リリース**: スパム (フィッシングではない) メッセージの場合は、[セキュリティ とコンプライアンス センターの検疫] に移動せずに、ここで&できます。</span><span class="sxs-lookup"><span data-stu-id="ce881-123">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="ce881-124">**レビュー**: このリンクをクリックすると、セキュリティ & コンプライアンス センターの [検疫] に移動し、検疫済みメッセージの表示、リリース、削除、または報告が可能です (メッセージが検疫された理由に応じて)。</span><span class="sxs-lookup"><span data-stu-id="ce881-124">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="ce881-125">詳細については、「EOP で検疫済みメッセージをユーザーとして検索して解放する [」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="ce881-125">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![エンド ユーザーのスパム通知の例](../../media/end-user-spam-notification.png)

> [!NOTE]
> <span data-ttu-id="ce881-127">送信者がブロックされた場合でも、メールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="ce881-127">A blocked sender can still send you mail.</span></span> <span data-ttu-id="ce881-128">この送信者からメールボックスに送信されたメッセージは、直ちに迷惑メール フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="ce881-128">Any messages from this sender that make it to your mailbox will be immediately moved to the Junk Email folder.</span></span> <span data-ttu-id="ce881-129">この送信者からの今後のメッセージは、迷惑メール フォルダーまたはエンドユーザー検疫に移動します。</span><span class="sxs-lookup"><span data-stu-id="ce881-129">Future messages from this sender will go to your Junk Email folder or to the end-user quarantine.</span></span> <span data-ttu-id="ce881-130">これらのメッセージを quarantining ではなく、到着時に削除する場合は、メール フロー ルール [(トランスポート](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) ルールとも呼ばれる) を使用して、到着時にメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="ce881-130">If you would like to delete these messages on arrival instead of quarantining them, use [mail flow Rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to delete the messages on arrival.</span></span>