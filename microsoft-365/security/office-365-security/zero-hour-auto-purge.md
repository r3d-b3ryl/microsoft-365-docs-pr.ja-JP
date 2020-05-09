---
title: ゼロ時間自動削除 (ZAP)-電子メール保護機能
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
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Exchange Online に既に配信されているスパム、マルウェア、またはフィッシングメッセージを検出する、Microsoft 365 の電子メール保護機能であるゼロ時間の自動削除 (ZAP) について説明します。
ms.openlocfilehash: ba7aa74dd9152990ce327d1b1564c3246d15cbb8
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173300"
---
# <a name="zero-hour-auto-purge-zap---protection-against-spam-and-malware-in-microsoft-365"></a><span data-ttu-id="be5be-103">ゼロ時間自動削除 (ZAP)-Microsoft 365 でのスパムおよびマルウェアからの保護</span><span class="sxs-lookup"><span data-stu-id="be5be-103">Zero-hour auto purge (ZAP) - protection against spam and malware in Microsoft 365</span></span>

## <a name="overview"></a><span data-ttu-id="be5be-104">概要</span><span class="sxs-lookup"><span data-stu-id="be5be-104">Overview</span></span>

<span data-ttu-id="be5be-105">ゼロ時間自動削除 (ZAP) は、Microsoft 365 の電子メール保護機能で、Exchange Online メールボックスに既に配信されている悪意のあるフィッシング、スパム、またはマルウェアメッセージをさかのぼって検出し、neutralizes します。</span><span class="sxs-lookup"><span data-stu-id="be5be-105">Zero-hour auto purge (ZAP) is an email protection feature in Microsoft 365 that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="be5be-106">ZAP は、Exchange Online メールボックスを含む Microsoft 365 サブスクリプションに含まれている既定の Exchange Online Protection (EOP) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="be5be-106">ZAP is available with the default Exchange Online Protection (EOP) that's included with any Microsoft 365 subscription that contains Exchange Online mailboxes.</span></span> <span data-ttu-id="be5be-107">ZAP は、オンプレミスの Exchange メールボックスを保護するスタンドアロンの EOP 環境では機能しません。</span><span class="sxs-lookup"><span data-stu-id="be5be-107">ZAP doesn't work in standalone EOP environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="be5be-108">ZAP のしくみ</span><span class="sxs-lookup"><span data-stu-id="be5be-108">How ZAP works</span></span>

<span data-ttu-id="be5be-109">Microsoft 365 は、毎日リアルタイムでスパムおよびマルウェアの署名を更新します。</span><span class="sxs-lookup"><span data-stu-id="be5be-109">Microsoft 365 updates spam and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="be5be-110">ただし、ユーザーが配信された後にコンテンツが weaponized されているかどうかなど、さまざまな理由で、ユーザーが悪意のあるメッセージを引き続き受信できます。</span><span class="sxs-lookup"><span data-stu-id="be5be-110">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="be5be-111">ZAP は、Microsoft 365 スパムおよびマルウェア署名の更新を継続的に監視することによって、この問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="be5be-111">ZAP addresses this issue by continually monitoring updates to the Microsoft 365 spam and malware signatures.</span></span> <span data-ttu-id="be5be-112">ZAP は、ユーザーのメールボックスに既に存在するメッセージを見つけて削除することができます。</span><span class="sxs-lookup"><span data-stu-id="be5be-112">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="be5be-113">ZAP アクションはユーザーにとってシームレスです。メッセージが検出され、移動された場合は通知されません。</span><span class="sxs-lookup"><span data-stu-id="be5be-113">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="be5be-114">[信頼できる差出人のリスト](create-safe-sender-lists-in-office-365.md)、メールフロールール (トランスポートルールとも呼ばれる)、受信トレイルール、または追加フィルターは、ZAP より優先されます。</span><span class="sxs-lookup"><span data-stu-id="be5be-114">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="be5be-115">メールフローの場合と同様に、配信されたメッセージが ZAP する必要があると判断された場合でも、安全な送信者の構成が原因でメッセージが処理されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="be5be-115">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="be5be-116">これは、フィルター処理をバイパスするようにメッセージを構成するためのもう1つの理由です。</span><span class="sxs-lookup"><span data-stu-id="be5be-116">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="be5be-117">マルウェアの ZAP</span><span class="sxs-lookup"><span data-stu-id="be5be-117">Malware ZAP</span></span>

<span data-ttu-id="be5be-118">配信後にマルウェアが含まれていることが検出された**開封済みメッセージまたは未読メッセージ**の場合、ZAP 検疫は、マルウェアの添付ファイルを含むメッセージを検出します。</span><span class="sxs-lookup"><span data-stu-id="be5be-118">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="be5be-119">管理者のみが、検疫からマルウェアメッセージを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="be5be-119">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="be5be-120">マルウェア対策ポリシーでは、既定でマルウェアの ZAP が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="be5be-120">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="be5be-121">詳細については、「 [Microsoft 365 でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be5be-121">For more information, see [Configure anti-malware policies in Microsoft 365](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="be5be-122">フィッシング ZAP</span><span class="sxs-lookup"><span data-stu-id="be5be-122">Phish ZAP</span></span>

<span data-ttu-id="be5be-123">配信後にフィッシングとして識別される**開封済みメッセージまたは未読メッセージ**の場合、ZAP の結果は、該当するスパム対策ポリシーで**フィッシング電子メール**フィルター verdict に対して構成されているアクションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="be5be-123">For **read or unread messages** that are identified as phish after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="be5be-124">フィッシングの使用可能なフィルター処理の verdict アクションと、その可能性のある ZAP の結果については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="be5be-124">The available filtering verdict actions for phish and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="be5be-125">**X-ヘッダー**、**先頭に件名行**を追加する: ZAP はメッセージに対してアクションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="be5be-125">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="be5be-126">**迷惑メールにメッセージを移動する**: 迷惑メールルールがメールボックスで有効になっていれば (既定で有効になっている場合)、メッセージは迷惑メールフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="be5be-126">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="be5be-127">詳細については、「 [Microsoft 365 の「Exchange Online メールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be5be-127">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="be5be-128">メッセージ**を電子メールアドレス**、**削除メッセージ**、**検疫メッセージ**: ZAP 検疫メッセージにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="be5be-128">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="be5be-129">管理者のみが、フィッシング検疫済みメッセージを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="be5be-129">Only admins can view and manage phish quarantined messages.</span></span>

<span data-ttu-id="be5be-130">既定では、スパム対策ポリシーではフィッシング ZAP が有効になっており、**フィッシング電子メール**フィルター verdict の既定のアクションは**検疫メッセージ**で、既定ではフィッシング ZAP 検疫メッセージを示します。</span><span class="sxs-lookup"><span data-stu-id="be5be-130">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="be5be-131">スパムフィルター verdicts の構成の詳細については、「 [Microsoft 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be5be-131">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="be5be-132">スパム ZAP</span><span class="sxs-lookup"><span data-stu-id="be5be-132">Spam ZAP</span></span>

<span data-ttu-id="be5be-133">配信後にスパムとして識別される**未開封のメッセージ**の場合、ZAP の結果**は、該当**するスパム対策ポリシーの verdict に対して構成されているアクションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="be5be-133">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="be5be-134">スパムに対して使用可能なフィルター処理の verdict アクションと、ZAP の結果については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="be5be-134">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="be5be-135">**X-ヘッダー**、**先頭に件名行**を追加する: ZAP はメッセージに対してアクションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="be5be-135">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="be5be-136">**迷惑メールにメッセージを移動する**: 迷惑メールルールがメールボックスで有効になっていれば (既定で有効になっている場合)、メッセージは迷惑メールフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="be5be-136">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="be5be-137">詳細については、「 [Microsoft 365 の「Exchange Online メールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be5be-137">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="be5be-138">メッセージ**を電子メールアドレス**、**削除メッセージ**、**検疫メッセージ**: ZAP 検疫メッセージにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="be5be-138">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="be5be-139">エンドユーザーは、自分のスパム検疫済みメッセージを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="be5be-139">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="be5be-140">既定では、スパム対策ポリシーでスパム ZAP が有効になっており、**スパム**フィルター verdict の既定のアクションが **[迷惑メール] フォルダーに移動**します。この場合、スパム ZAP は**未読**メッセージを迷惑メールフォルダーに既定で移動します。</span><span class="sxs-lookup"><span data-stu-id="be5be-140">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="be5be-141">スパムフィルター verdicts の構成の詳細については、「 [Microsoft 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be5be-141">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-office-365-advanced-threat-protection-atp"></a><span data-ttu-id="be5be-142">Office 365 Advanced Threat Protection (ATP) に関する ZAP に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="be5be-142">ZAP considerations for Office 365 Advanced Threat Protection (ATP)</span></span>

<span data-ttu-id="be5be-143">ZAP は、[動的配信](dynamic-delivery-and-previewing.md)スキャンのプロセス内のメッセージを検疫しません。または、マルウェアフィルターによって添付ファイルが既に**マルウェアアラートテキスト .txt**ファイルに置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="be5be-143">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](dynamic-delivery-and-previewing.md) scanning, or where malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="be5be-144">これらの種類のメッセージに対してフィッシングまたはスパムのシグナルを受信し、スパム対策ポリシーのフィルター verdict がメッセージに対して何らかのアクションを実行するように設定されている場合 ([迷惑メールに移動] に移動します)、ZAP は既定で [迷惑メールに移行] アクションになります。</span><span class="sxs-lookup"><span data-stu-id="be5be-144">If a phish or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="be5be-145">ZAP がメッセージを移動したかどうかを確認する方法</span><span class="sxs-lookup"><span data-stu-id="be5be-145">How to see if ZAP moved your message</span></span>

<span data-ttu-id="be5be-146">ZAP がメッセージを移動したかどうかを確認するには、[脅威保護状態レポート](view-email-security-reports.md#threat-protection-status-report)または[脅威エクスプローラー (およびリアルタイム検出)](threat-explorer.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="be5be-146">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="be5be-147">システムアクションとして、ZAP が Exchange メールボックス監査ログに記録されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="be5be-147">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="be5be-148">ZAP FAQ</span><span class="sxs-lookup"><span data-stu-id="be5be-148">ZAP FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="be5be-149">正当なメッセージが迷惑メールフォルダーに移動された場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="be5be-149">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="be5be-150">誤[検知](report-junk-email-messages-to-microsoft.md)には通常のレポートプロセスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="be5be-150">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="be5be-151">メッセージが [受信トレイ] から [迷惑メール] フォルダーに移動されるのは、サービスがスパムまたは悪意のあるメッセージであると判断した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="be5be-151">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="be5be-152">迷惑メールフォルダーではなく、検疫フォルダーを使用している場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="be5be-152">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="be5be-153">ZAP は、このトピックの前半で説明したように、スパム対策ポリシーの構成に基づいてメッセージに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="be5be-153">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this topic.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="be5be-154">差出人セーフリスト、メールフロールール、許可/ブロックされる送信者リストを使用している場合は、どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="be5be-154">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="be5be-155">信頼できる差出人、メールフロールール、またはブロックと許可の組織設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="be5be-155">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="be5be-156">これらのメッセージは、サービスが設定した内容を実行しているため、ZAP から除外されます。</span><span class="sxs-lookup"><span data-stu-id="be5be-156">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="be5be-157">これは、フィルター処理をバイパスするようにメッセージを構成するためのもう1つの理由です。</span><span class="sxs-lookup"><span data-stu-id="be5be-157">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="be5be-158">メッセージが別のフォルダー (たとえば、受信トレイルールなど) に移動した場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="be5be-158">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="be5be-159">ZAP は、メッセージが削除されていない場合、または同じまたはより強力なアクションがまだ適用されていない限り、引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="be5be-159">ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="be5be-160">たとえば、フィッシングポリシーが [検疫] に設定されており、ユーザーまたは管理者が既に電子メールを junked している場合、検疫はファイルを検疫する処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="be5be-160">For example, if the phish policy is set to quarantine and the user or administrator has already junked the email, then quarantine will take action to quarantine the file.</span></span>

### <a name="does-zap-change-the-message-header"></a><span data-ttu-id="be5be-161">メッセージヘッダーを ZAP に変更しますか?</span><span class="sxs-lookup"><span data-stu-id="be5be-161">Does ZAP change the message header?</span></span>

<span data-ttu-id="be5be-162">ZAP アクションでは、メッセージヘッダーに対して変更は行われません。</span><span class="sxs-lookup"><span data-stu-id="be5be-162">A ZAP action does not make any changes to the message header.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="be5be-163">ZAP がメールボックスを保留にする方法</span><span class="sxs-lookup"><span data-stu-id="be5be-163">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="be5be-164">ZAP は、保留中のメールボックスからのメッセージを検疫しません。</span><span class="sxs-lookup"><span data-stu-id="be5be-164">ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="be5be-165">ZAP は、スパム対策ポリシーでスパムまたはフィッシング verdict に対して構成されたアクションに基づいて、メッセージを [迷惑メール] フォルダーに移動できます。</span><span class="sxs-lookup"><span data-stu-id="be5be-165">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="be5be-166">Exchange Online のホールドの詳細については、「[インプレース保持と訴訟ホールド (Exchange online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be5be-166">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
