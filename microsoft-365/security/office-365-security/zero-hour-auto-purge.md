---
title: ゼロアワー自動消去 (ZAP)
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
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、ゼロアワー自動消去 (ZAP) を使用して、Exchange Online メールボックス内の配信済みメッセージを迷惑メール フォルダーまたは検疫 (スパムまたはフィッシングと見なされた検疫) にさかのぼって移動する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5fd41cf45ad2a49d74684ae3e20dded5c1b8f034
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287307"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a><span data-ttu-id="1b27c-103">Exchange Online でのゼロアワー自動消去 (ZAP)</span><span class="sxs-lookup"><span data-stu-id="1b27c-103">Zero-hour auto purge (ZAP) in Exchange Online</span></span>

<span data-ttu-id="1b27c-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="1b27c-104">**Applies to**</span></span>
- [<span data-ttu-id="1b27c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1b27c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1b27c-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="1b27c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="1b27c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b27c-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a><span data-ttu-id="1b27c-108">ZAP の基本的な機能</span><span class="sxs-lookup"><span data-stu-id="1b27c-108">Basic features of ZAP</span></span>

<span data-ttu-id="1b27c-109">Exchange Online にメールボックスを持つ Microsoft 365 組織では、ゼロアワー自動消去 (ZAP) は、Exchange Online メールボックスに既に配信されている悪意のあるフィッシング、スパム、またはマルウェア メッセージを検出し、それを防除する電子メール保護機能です。</span><span class="sxs-lookup"><span data-stu-id="1b27c-109">In Microsoft 365 organizations with mailboxes in Exchange Online, zero-hour auto purge (ZAP) is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="1b27c-110">ZAP は、オンプレミスの Exchange メールボックスを保護するスタンドアロンの Exchange Online Protection (EOP) 環境では動作しません。</span><span class="sxs-lookup"><span data-stu-id="1b27c-110">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="1b27c-111">ZAP のしくみ</span><span class="sxs-lookup"><span data-stu-id="1b27c-111">How ZAP works</span></span>

<span data-ttu-id="1b27c-112">スパムとマルウェアの署名は、サービスで毎日リアルタイムで更新されます。</span><span class="sxs-lookup"><span data-stu-id="1b27c-112">Spam and malware signatures are updated in the service real-time on a daily basis.</span></span> <span data-ttu-id="1b27c-113">ただし、ユーザーに配信された後にコンテンツが武器化された場合など、さまざまな理由で悪意のあるメッセージを受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b27c-113">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="1b27c-114">ZAP では、サービス内のスパムおよびマルウェアの署名に対する更新を継続的に監視することで、この問題に取り組まれています。</span><span class="sxs-lookup"><span data-stu-id="1b27c-114">ZAP addresses this issue by continually monitoring updates to the spam and malware signatures in the service.</span></span> <span data-ttu-id="1b27c-115">ZAP は、ユーザーのメールボックスに既に存在するメッセージを検索および削除できます。</span><span class="sxs-lookup"><span data-stu-id="1b27c-115">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="1b27c-116">ZAP アクションはユーザーにシームレスです。メッセージが検出され、移動された場合は通知されません。</span><span class="sxs-lookup"><span data-stu-id="1b27c-116">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="1b27c-117">[差出人セーフ](create-safe-sender-lists-in-office-365.md)リスト、メール フロー ルール (トランスポート ルールとも呼ばれる)、受信トレイ ルール、または追加フィルターが ZAP よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="1b27c-117">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="1b27c-118">メール フローでの処理と同様に、これは、サービスが配信されたメッセージに ZAP が必要と判断した場合でも、差出人セーフ リストの構成のためにメッセージが処理されないという意味です。</span><span class="sxs-lookup"><span data-stu-id="1b27c-118">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="1b27c-119">これは、フィルター処理をバイパスするメッセージの構成に注意するもう 1 つの理由です。</span><span class="sxs-lookup"><span data-stu-id="1b27c-119">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="1b27c-120">マルウェア ZAP</span><span class="sxs-lookup"><span data-stu-id="1b27c-120">Malware ZAP</span></span>

<span data-ttu-id="1b27c-121">配信 **後にマルウェア** が含まれていると見つかった読み取りメッセージまたは未読メッセージの場合、ZAP はマルウェアの添付ファイルを含むメッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="1b27c-121">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="1b27c-122">管理者だけが検疫からのマルウェア メッセージを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="1b27c-122">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="1b27c-123">マルウェア ZAP は、マルウェア対策ポリシーで既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="1b27c-123">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="1b27c-124">詳細については [、「EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1b27c-124">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="1b27c-125">フィッシング ZAP</span><span class="sxs-lookup"><span data-stu-id="1b27c-125">Phish ZAP</span></span>

<span data-ttu-id="1b27c-126">配信 **後** にフィッシングとして識別される読み取りメッセージまたは未読メッセージの場合、ZAP の結果は、該当するスパム対策ポリシーのフィッシング メール フィルターの決定に対して構成されているアクションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1b27c-126">For **read or unread messages** that are identified as phishing after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="1b27c-127">フィッシングに対して使用可能なフィルター処理の決定アクションと、それらの ZAP の結果について、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="1b27c-127">The available filtering verdict actions for phishing and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="1b27c-128">**X-Header を追加** し **、件名行の先頭にテキストを** 追加します。ZAP はメッセージに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="1b27c-128">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="1b27c-129">**[迷惑メールに** メッセージを移動する]: ZAP は、メールボックスで迷惑メール ルールが有効になっている限り (既定で有効になっている) 限り、メッセージを [迷惑メール] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="1b27c-129">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="1b27c-130">詳細については [、「Microsoft 365 の Exchange Online メールボックスで迷惑メール](configure-junk-email-settings-on-exo-mailboxes.md)設定を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b27c-130">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="1b27c-131">**電子メール アドレスへのメッセージのリダイレクト**、 **メッセージの削除**、 **メッセージの検疫**: ZAP はメッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="1b27c-131">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span>

<span data-ttu-id="1b27c-132">既定では、フィッシング ZAP はスパム対策ポリシーで有効にされ、フィッシング メールフィルターの条件に対する既定のアクションは検疫メッセージです。これは、フィッシング ZAP が既定でメッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="1b27c-132">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="1b27c-133">スパム フィルターの条件の構成の詳細については [、「Microsoft 365](configure-your-spam-filter-policies.md)でスパム対策ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b27c-133">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="1b27c-134">スパム ZAP</span><span class="sxs-lookup"><span data-stu-id="1b27c-134">Spam ZAP</span></span>

<span data-ttu-id="1b27c-135">配信 **後** にスパムとして識別される未読メッセージの場合、ZAP の結果は、該当するスパム対策ポリシーのスパムフィルターの決定に対して構成されているアクションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1b27c-135">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="1b27c-136">スパムに対して使用可能なフィルター処理の決定アクションと、その ZAP の結果について、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="1b27c-136">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="1b27c-137">**X-Header を追加** し **、件名行の先頭にテキストを** 追加します。ZAP はメッセージに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="1b27c-137">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="1b27c-138">**[迷惑メールに** メッセージを移動する]: ZAP は、メールボックスで迷惑メール ルールが有効になっている限り (既定で有効になっている) 限り、メッセージを [迷惑メール] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="1b27c-138">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="1b27c-139">詳細については [、「Microsoft 365 の Exchange Online メールボックスで迷惑メール](configure-junk-email-settings-on-exo-mailboxes.md)設定を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b27c-139">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="1b27c-140">**電子メール アドレスへのメッセージのリダイレクト**、 **メッセージの削除**、 **メッセージの検疫**: ZAP はメッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="1b27c-140">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="1b27c-141">エンドユーザーは、独自のスパム検疫済みメッセージを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="1b27c-141">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="1b27c-142">既定では、スパム ZAP はスパム対策ポリシーで有効にされ、スパム フィルターの条件の既定のアクションは[迷惑メール] フォルダーにメッセージを移動します。つまり、スパム ZAP は既定で未読のメッセージを [迷惑メール] フォルダーに移動します。 </span><span class="sxs-lookup"><span data-stu-id="1b27c-142">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="1b27c-143">スパム フィルターの条件の構成の詳細については [、「Microsoft 365](configure-your-spam-filter-policies.md)でスパム対策ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b27c-143">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a><span data-ttu-id="1b27c-144">Microsoft Defender for Office 365 の ZAP に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="1b27c-144">ZAP considerations for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="1b27c-145">ZAP は、安全な添付ファイルのスキャンで動的配信 [](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)の過程にあるメッセージや、EOP マルウェア フィルター処理によって添付ファイルが既に **Malware Alert Text.txt** ファイルに置き換えられたメッセージは検疫されません。</span><span class="sxs-lookup"><span data-stu-id="1b27c-145">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) in Safe Attachments scanning, or where EOP malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="1b27c-146">これらの種類のメッセージに対してフィッシングまたはスパムシグナルが受信され、スパム対策ポリシーのフィルター処理の条件がメッセージに対して何らかのアクション ([迷惑メールへの移動]、[リダイレクト]、[削除]、または [検疫]) に設定されている場合、ZAP は既定で [迷惑メールに移動] アクションに設定されます。</span><span class="sxs-lookup"><span data-stu-id="1b27c-146">If a phishing or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, or Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="1b27c-147">ZAP がメッセージを移動したどうか確認する方法</span><span class="sxs-lookup"><span data-stu-id="1b27c-147">How to see if ZAP moved your message</span></span>

<span data-ttu-id="1b27c-148">ZAP がメッセージを移動したかどうかを確認するには [、Threat Protection の](view-email-security-reports.md#threat-protection-status-report) 状態レポートまたは脅威エクスプローラー (およびリアルタイムの検出) [を使用します](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="1b27c-148">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="1b27c-149">システム操作として、ZAP は Exchange メールボックス監査ログに記録されません。</span><span class="sxs-lookup"><span data-stu-id="1b27c-149">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="1b27c-150">ZAP FAQ</span><span class="sxs-lookup"><span data-stu-id="1b27c-150">ZAP FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="1b27c-151">正当なメッセージが迷惑メール フォルダーに移動された場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="1b27c-151">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="1b27c-152">誤検知については、通常の報告 [プロセスに従う必要があります](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="1b27c-152">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="1b27c-153">メッセージが受信トレイから迷惑メール フォルダーに移動される唯一の理由は、サービスがメッセージがスパムまたは悪意のあるメッセージと判断したためです。</span><span class="sxs-lookup"><span data-stu-id="1b27c-153">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="1b27c-154">迷惑メール フォルダーの代わりに検疫フォルダーを使用した場合</span><span class="sxs-lookup"><span data-stu-id="1b27c-154">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="1b27c-155">ZAP は、この記事で前述したスパム対策ポリシーの構成に基づいて、メッセージに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="1b27c-155">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this article.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="1b27c-156">差出人セーフ リスト、メール フロー ルール、許可/受信拒否リストを使用している場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="1b27c-156">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="1b27c-157">差出人セーフ リスト、メール フロー ルール、または組織の設定のブロックと許可が優先されます。</span><span class="sxs-lookup"><span data-stu-id="1b27c-157">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="1b27c-158">これらのメッセージは、サービスが構成した処理を行うので、ZAP から除外されます。</span><span class="sxs-lookup"><span data-stu-id="1b27c-158">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="1b27c-159">これは、フィルター処理をバイパスするメッセージの構成に注意するもう 1 つの理由です。</span><span class="sxs-lookup"><span data-stu-id="1b27c-159">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="1b27c-160">メッセージが別のフォルダー (受信トレイ ルールなど) に移動された場合は、どうでしょうか。</span><span class="sxs-lookup"><span data-stu-id="1b27c-160">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="1b27c-161">ZAP は、メッセージが削除されていない限り、または同じ、またはより強力なアクションがまだ適用されていない限り、引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="1b27c-161">ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="1b27c-162">たとえば、フィッシング対策ポリシーが検疫に設定され、メッセージが既に迷惑メール内にある場合、ZAP はメッセージを検疫するアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="1b27c-162">For example, if the anti-phishing policy is set to quarantine and message is already in the Junk Email, then ZAP will take action to quarantine the message.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="1b27c-163">ZAP は保持中のメールボックスにどのような影響を与えるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="1b27c-163">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="1b27c-164">ZAP は、保持中のメールボックスからメッセージを検疫しません。</span><span class="sxs-lookup"><span data-stu-id="1b27c-164">ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="1b27c-165">ZAP は、スパム対策ポリシーでスパムまたはフィッシングの確認に対して構成されたアクションに基づいて、メッセージを [迷惑メール] フォルダーに移動できます。</span><span class="sxs-lookup"><span data-stu-id="1b27c-165">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="1b27c-166">Exchange Online の保留の詳細については、「Exchange Online のインホールドと訴訟ホールド」を [参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)。</span><span class="sxs-lookup"><span data-stu-id="1b27c-166">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
