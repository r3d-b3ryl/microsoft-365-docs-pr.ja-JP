---
title: ゼロ時間自動削除 (ZAP)-スパム、マルウェア、フィッシングからの retroactive 保護。
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
description: ゼロ時間自動削除 (ZAP) は、Microsoft 365 の電子メール保護機能であり、Exchange Online に既に配信されているスパム、マルウェア、またはフィッシングメッセージを検出します。 これは、検出された悪意のあるコンテンツの種類によってどのような違いがありますか。
ms.openlocfilehash: f1b36f1152882f446c8f611ceafb44a085cc0a5d
ms.sourcegitcommit: d4d082292dc711a579fe925ad989ea54ec2e27f4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43708453"
---
# <a name="zero-hour-auto-purge-zap---protection-against-spam-and-malware-in-microsoft-365"></a><span data-ttu-id="f3abc-104">ゼロ時間自動削除 (ZAP)-Microsoft 365 でのスパムおよびマルウェアからの保護</span><span class="sxs-lookup"><span data-stu-id="f3abc-104">Zero-hour auto purge (ZAP) - protection against spam and malware in Microsoft 365</span></span>

## <a name="overview"></a><span data-ttu-id="f3abc-105">概要</span><span class="sxs-lookup"><span data-stu-id="f3abc-105">Overview</span></span>

<span data-ttu-id="f3abc-106">ゼロ時間自動削除 (ZAP) は、Microsoft 365 の電子メール保護機能で、Exchange Online メールボックスに既に配信されている悪意のあるフィッシング、スパム、またはマルウェアメッセージをさかのぼって検出し、neutralizes します。</span><span class="sxs-lookup"><span data-stu-id="f3abc-106">Zero-hour auto purge (ZAP) is an email protection feature in Microsoft 365 that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="f3abc-107">ZAP は、Exchange Online メールボックスを含む Microsoft 365 サブスクリプションに含まれている既定の Exchange Online Protection (EOP) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3abc-107">ZAP is available with the default Exchange Online Protection (EOP) that's included with any Microsoft 365 subscription that contains Exchange Online mailboxes.</span></span> <span data-ttu-id="f3abc-108">ZAP は、オンプレミスの Exchange メールボックスを保護するスタンドアロンの EOP 環境では機能しません。</span><span class="sxs-lookup"><span data-stu-id="f3abc-108">ZAP doesn't work in standalone EOP environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="f3abc-109">ZAP のしくみ</span><span class="sxs-lookup"><span data-stu-id="f3abc-109">How ZAP works</span></span>

<span data-ttu-id="f3abc-110">Microsoft 365 は、毎日リアルタイムでスパムおよびマルウェアの署名を更新します。</span><span class="sxs-lookup"><span data-stu-id="f3abc-110">Microsoft 365 updates spam and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="f3abc-111">ただし、ユーザーが配信された後にコンテンツが weaponized されているかどうかなど、さまざまな理由で、ユーザーが悪意のあるメッセージを引き続き受信できます。</span><span class="sxs-lookup"><span data-stu-id="f3abc-111">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="f3abc-112">ZAP は、Microsoft 365 スパムおよびマルウェア署名の更新を継続的に監視することによって、この問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="f3abc-112">ZAP addresses this issue by continually monitoring updates to the Microsoft 365 spam and malware signatures.</span></span> <span data-ttu-id="f3abc-113">ZAP は、ユーザーのメールボックスに既に存在するメッセージを見つけて削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f3abc-113">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="f3abc-114">ZAP アクションはユーザーにとってシームレスです。メッセージが検出され、移動された場合は通知されません。</span><span class="sxs-lookup"><span data-stu-id="f3abc-114">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="f3abc-115">[信頼できる差出人のリスト](create-safe-sender-lists-in-office-365.md)、メールフロールール (トランスポートルールとも呼ばれる)、受信トレイルール、または追加フィルターは、ZAP より優先されます。</span><span class="sxs-lookup"><span data-stu-id="f3abc-115">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="f3abc-116">マルウェアの ZAP</span><span class="sxs-lookup"><span data-stu-id="f3abc-116">Malware ZAP</span></span>

<span data-ttu-id="f3abc-117">配信後にマルウェアが含まれていることが検出された**開封済みメッセージまたは未読メッセージ**の場合、ZAP 検疫は、マルウェアの添付ファイルを含むメッセージを検出します。</span><span class="sxs-lookup"><span data-stu-id="f3abc-117">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="f3abc-118">管理者のみが、検疫からマルウェアメッセージを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="f3abc-118">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="f3abc-119">マルウェア対策ポリシーでは、既定でマルウェアの ZAP が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="f3abc-119">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="f3abc-120">詳細については、「 [Microsoft 365 でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3abc-120">For more information, see [Configure anti-malware policies in Microsoft 365](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="f3abc-121">フィッシング ZAP</span><span class="sxs-lookup"><span data-stu-id="f3abc-121">Phish ZAP</span></span>

<span data-ttu-id="f3abc-122">配信後にフィッシングとして識別される**開封済みメッセージまたは未読メッセージ**の場合、ZAP の結果は、該当するスパム対策ポリシーで**フィッシング電子メール**フィルター verdict に対して構成されているアクションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="f3abc-122">For **read or unread messages** that are identified as phish after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="f3abc-123">フィッシングの使用可能なフィルター処理の verdict アクションと、その可能性のある ZAP の結果については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="f3abc-123">The available filtering verdict actions for phish and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="f3abc-124">**X-ヘッダー**、**先頭に件名行**を追加する: ZAP はメッセージに対してアクションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="f3abc-124">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="f3abc-125">**迷惑メールにメッセージを移動する**: 迷惑メールルールがメールボックスで有効になっていれば (既定で有効になっている場合)、メッセージは迷惑メールフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="f3abc-125">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="f3abc-126">詳細については、「 [Microsoft 365 の「Exchange Online メールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3abc-126">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="f3abc-127">メッセージ**を電子メールアドレス**、**削除メッセージ**、**検疫メッセージ**: ZAP 検疫メッセージにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="f3abc-127">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="f3abc-128">管理者のみが、フィッシング検疫済みメッセージを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="f3abc-128">Only admins can view and manage phish quarantined messages.</span></span>

<span data-ttu-id="f3abc-129">既定では、スパム対策ポリシーではフィッシング ZAP が有効になっており、**フィッシング電子メール**フィルター verdict の既定のアクションは**検疫メッセージ**で、既定ではフィッシング ZAP 検疫メッセージを示します。</span><span class="sxs-lookup"><span data-stu-id="f3abc-129">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="f3abc-130">スパムフィルター verdicts の構成の詳細については、「 [Microsoft 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3abc-130">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="f3abc-131">スパム ZAP</span><span class="sxs-lookup"><span data-stu-id="f3abc-131">Spam ZAP</span></span>

<span data-ttu-id="f3abc-132">配信後にスパムとして識別される**未開封のメッセージ**の場合、ZAP の結果**は、該当**するスパム対策ポリシーの verdict に対して構成されているアクションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="f3abc-132">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="f3abc-133">スパムに対して使用可能なフィルター処理の verdict アクションと、ZAP の結果については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="f3abc-133">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="f3abc-134">**X-ヘッダー**、**先頭に件名行**を追加する: ZAP はメッセージに対してアクションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="f3abc-134">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="f3abc-135">**迷惑メールにメッセージを移動する**: 迷惑メールルールがメールボックスで有効になっていれば (既定で有効になっている場合)、メッセージは迷惑メールフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="f3abc-135">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="f3abc-136">詳細については、「 [Microsoft 365 の「Exchange Online メールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3abc-136">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="f3abc-137">メッセージ**を電子メールアドレス**、**削除メッセージ**、**検疫メッセージ**: ZAP 検疫メッセージにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="f3abc-137">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="f3abc-138">エンドユーザーは、自分のスパム検疫済みメッセージを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="f3abc-138">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="f3abc-139">既定では、スパム対策ポリシーでスパム ZAP が有効になっており、**スパム**フィルター verdict の既定のアクションが **[迷惑メール] フォルダーに移動**します。この場合、スパム ZAP は**未読**メッセージを迷惑メールフォルダーに既定で移動します。</span><span class="sxs-lookup"><span data-stu-id="f3abc-139">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="f3abc-140">スパムフィルター verdicts の構成の詳細については、「 [Microsoft 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3abc-140">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-office-365-advanced-threat-protection-atp"></a><span data-ttu-id="f3abc-141">Office 365 Advanced Threat Protection (ATP) に関する ZAP に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="f3abc-141">ZAP considerations for Office 365 Advanced Threat Protection (ATP)</span></span>

<span data-ttu-id="f3abc-142">ZAP は、[動的配信](dynamic-delivery-and-previewing.md)スキャンのプロセス内のメッセージを検疫しません。または、マルウェアフィルターによって添付ファイルが既に**マルウェアアラートテキスト .txt**ファイルに置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="f3abc-142">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](dynamic-delivery-and-previewing.md) scanning, or where malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="f3abc-143">これらの種類のメッセージに対してフィッシングまたはスパムのシグナルを受信し、スパム対策ポリシーのフィルター verdict がメッセージに対して何らかのアクションを実行するように設定されている場合 ([迷惑メールに移動] に移動します)、ZAP は既定で [迷惑メールに移行] アクションになります。</span><span class="sxs-lookup"><span data-stu-id="f3abc-143">If a phish or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="f3abc-144">ZAP がメッセージを移動したかどうかを確認する方法</span><span class="sxs-lookup"><span data-stu-id="f3abc-144">How to see if ZAP moved your message</span></span>

<span data-ttu-id="f3abc-145">ZAP がメッセージを移動したかどうかを確認するには、[脅威保護状態レポート](view-email-security-reports.md#threat-protection-status-report)または[脅威エクスプローラー (およびリアルタイム検出)](threat-explorer.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3abc-145">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="f3abc-146">システムアクションとして、ZAP が Exchange メールボックス監査ログに記録されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f3abc-146">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="f3abc-147">ZAP FAQ</span><span class="sxs-lookup"><span data-stu-id="f3abc-147">ZAP FAQ</span></span>

### <a name="q-what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="f3abc-148">Q: 正当なメッセージが迷惑メールフォルダーに移動された場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="f3abc-148">Q: What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="f3abc-149">A: 誤[検知](report-junk-email-messages-to-microsoft.md)に対して通常のレポートプロセスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3abc-149">A: You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="f3abc-150">メッセージが [受信トレイ] から [迷惑メール] フォルダーに移動されるのは、サービスがスパムまたは悪意のあるメッセージであると判断した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="f3abc-150">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="q-what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="f3abc-151">Q: 迷惑メールフォルダーではなく、検疫フォルダーを使用している場合はどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="f3abc-151">Q: What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="f3abc-152">A: ZAP は、このトピックで前述したように、スパム対策ポリシーの構成に基づいてメッセージに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="f3abc-152">A: ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this topic.</span></span>

### <a name="q-what-if-im-using-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="f3abc-153">Q: メールフロールールまたは許可/ブロックされた送信者の一覧を使用している場合はどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="f3abc-153">Q: What if I'm using mail flow rules or allowed/blocked sender lists?</span></span>

<span data-ttu-id="f3abc-154">A: メールフロールールまたは [組織設定の禁止] と [許可] が優先されます。</span><span class="sxs-lookup"><span data-stu-id="f3abc-154">A: Mail flow rules or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="f3abc-155">これらのメッセージは ZAP から除外されます。</span><span class="sxs-lookup"><span data-stu-id="f3abc-155">These messages are excluded from ZAP.</span></span>

### <a name="q-what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="f3abc-156">Q: メッセージが別のフォルダー (たとえば、受信トレイルールなど) に移動した場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="f3abc-156">Q: What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="f3abc-157">A: 問題なく、メッセージが削除されていない場合、または同じまたはより強力なアクションがまだ適用されていない場合に限り、このまま動作します。</span><span class="sxs-lookup"><span data-stu-id="f3abc-157">A:  ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="f3abc-158">たとえば、フィッシングポリシーが [検疫] に設定されており、ユーザーまたは管理者が既に電子メールを junked している場合、検疫はファイルを検疫する処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="f3abc-158">For example, if the phish policy is set to quarantine and the user or administrator has already junked the email, then quarantine will take action to quarantine the file.</span></span>

### <a name="q-does-zap-change-the-message-header"></a><span data-ttu-id="f3abc-159">Q: メッセージヘッダーは ZAP によって変更されますか?</span><span class="sxs-lookup"><span data-stu-id="f3abc-159">Q: Does ZAP change the message header?</span></span>

<span data-ttu-id="f3abc-160">A: ZAP アクションは、メッセージヘッダーに変更を加えません。</span><span class="sxs-lookup"><span data-stu-id="f3abc-160">A: A ZAP action does not make any changes to the message header.</span></span>

### <a name="q-how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="f3abc-161">Q: どのようにして、ZAP がメールボックスを保留にするのですか?</span><span class="sxs-lookup"><span data-stu-id="f3abc-161">Q: How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="f3abc-162">A: ZAP は、保留中のメールボックスからメッセージを検疫しません。</span><span class="sxs-lookup"><span data-stu-id="f3abc-162">A: ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="f3abc-163">ZAP は、スパム対策ポリシーでスパムまたはフィッシング verdict に対して構成されたアクションに基づいて、メッセージを [迷惑メール] フォルダーに移動できます。</span><span class="sxs-lookup"><span data-stu-id="f3abc-163">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="f3abc-164">Exchange Online のホールドの詳細については、「[インプレース保持と訴訟ホールド (Exchange online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3abc-164">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
