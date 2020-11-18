---
title: ゼロ時間自動削除 (ZAP)
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
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、ゼロ時間自動削除 (ZAP) を使用して、Exchange Online メールボックス内の配信されたメッセージを迷惑メールフォルダーに移動する方法、またはスパムまたはフィッシングとして検出された検疫について調べることができます。
ms.openlocfilehash: fd5186bc40d2d80097e6292d86ea113a41e0dd52
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131149"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a><span data-ttu-id="2b120-103">Exchange Online でのゼロ時間自動削除 (ZAP)</span><span class="sxs-lookup"><span data-stu-id="2b120-103">Zero-hour auto purge (ZAP) in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a><span data-ttu-id="2b120-104">ZAP の基本的な機能</span><span class="sxs-lookup"><span data-stu-id="2b120-104">Basic features of ZAP</span></span>

<span data-ttu-id="2b120-105">Exchange Online のメールボックスを使用する Microsoft 365 組織では、ゼロ時間自動削除 (ZAP) は電子メール保護機能の1つであり、Exchange Online メールボックスに既に配信されている悪意のあるフィッシング、スパム、またはマルウェアメッセージを neutralizes が検出し、それを検出します。</span><span class="sxs-lookup"><span data-stu-id="2b120-105">In Microsoft 365 organizations with mailboxes in Exchange Online, zero-hour auto purge (ZAP) is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="2b120-106">オンプレミスの Exchange メールボックスを保護するスタンドアロンの Exchange Online Protection (EOP) 環境では、ZAP は機能しません。</span><span class="sxs-lookup"><span data-stu-id="2b120-106">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="2b120-107">ZAP のしくみ</span><span class="sxs-lookup"><span data-stu-id="2b120-107">How ZAP works</span></span>

<span data-ttu-id="2b120-108">スパムとマルウェアの署名は、日単位でサービスのリアルタイムで更新されます。</span><span class="sxs-lookup"><span data-stu-id="2b120-108">Spam and malware signatures are updated in the service real-time on a daily basis.</span></span> <span data-ttu-id="2b120-109">ただし、ユーザーが配信された後にコンテンツが weaponized されているかどうかなど、さまざまな理由で、ユーザーが悪意のあるメッセージを引き続き受信できます。</span><span class="sxs-lookup"><span data-stu-id="2b120-109">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="2b120-110">ZAP は、スパムおよびマルウェア署名の更新を継続的に監視することによって、この問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="2b120-110">ZAP addresses this issue by continually monitoring updates to the spam and malware signatures in the service.</span></span> <span data-ttu-id="2b120-111">ZAP は、ユーザーのメールボックスに既に存在するメッセージを見つけて削除することができます。</span><span class="sxs-lookup"><span data-stu-id="2b120-111">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="2b120-112">ZAP アクションはユーザーにとってシームレスです。メッセージが検出され、移動された場合は通知されません。</span><span class="sxs-lookup"><span data-stu-id="2b120-112">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="2b120-113">[信頼できる差出人のリスト](create-safe-sender-lists-in-office-365.md)、メールフロールール (トランスポートルールとも呼ばれる)、受信トレイルール、または追加フィルターは、ZAP より優先されます。</span><span class="sxs-lookup"><span data-stu-id="2b120-113">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="2b120-114">メールフローの場合と同様に、配信されたメッセージが ZAP する必要があると判断された場合でも、安全な送信者の構成が原因でメッセージが処理されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="2b120-114">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="2b120-115">これは、フィルター処理をバイパスするようにメッセージを構成するためのもう1つの理由です。</span><span class="sxs-lookup"><span data-stu-id="2b120-115">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="2b120-116">マルウェアの ZAP</span><span class="sxs-lookup"><span data-stu-id="2b120-116">Malware ZAP</span></span>

<span data-ttu-id="2b120-117">配信後にマルウェアが含まれていることが検出された **開封済みメッセージまたは未読メッセージ** の場合、ZAP 検疫は、マルウェアの添付ファイルを含むメッセージを検出します。</span><span class="sxs-lookup"><span data-stu-id="2b120-117">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="2b120-118">管理者のみが、検疫からマルウェアメッセージを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="2b120-118">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="2b120-119">マルウェア対策ポリシーでは、既定でマルウェアの ZAP が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="2b120-119">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="2b120-120">詳細については、「 [EOP でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b120-120">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="2b120-121">フィッシング ZAP</span><span class="sxs-lookup"><span data-stu-id="2b120-121">Phish ZAP</span></span>

<span data-ttu-id="2b120-122">配信後にフィッシングとして識別される **開封済みメッセージまたは未読メッセージ** の場合、ZAP の結果は、該当するスパム対策ポリシーで **フィッシング電子メール** フィルター verdict に対して構成されているアクションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="2b120-122">For **read or unread messages** that are identified as phishing after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="2b120-123">フィッシングに対して使用可能なフィルター処理の verdict アクションと、ZAP の結果については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="2b120-123">The available filtering verdict actions for phishing and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="2b120-124">**X-ヘッダー**、 **先頭に件名行** を追加する: ZAP はメッセージに対してアクションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="2b120-124">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="2b120-125">**迷惑メールにメッセージを移動する**: 迷惑メールルールがメールボックスで有効になっていれば (既定で有効になっている場合)、メッセージは迷惑メールフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="2b120-125">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="2b120-126">詳細については、「 [Microsoft 365 の「Exchange Online メールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b120-126">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="2b120-127">メッセージ **を電子メールアドレス**、**削除メッセージ**、**検疫メッセージ**: ZAP 検疫メッセージにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="2b120-127">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span>

<span data-ttu-id="2b120-128">既定では、スパム対策ポリシーではフィッシング ZAP が有効になっており、 **フィッシング電子メール** フィルター verdict の既定のアクションは **検疫メッセージ** で、既定ではフィッシング ZAP 検疫メッセージを示します。</span><span class="sxs-lookup"><span data-stu-id="2b120-128">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="2b120-129">スパムフィルター verdicts の構成の詳細については、「 [Microsoft 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b120-129">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="2b120-130">スパム ZAP</span><span class="sxs-lookup"><span data-stu-id="2b120-130">Spam ZAP</span></span>

<span data-ttu-id="2b120-131">配信後にスパムとして識別される **未開封のメッセージ** の場合、ZAP の結果 **は、該当** するスパム対策ポリシーの verdict に対して構成されているアクションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="2b120-131">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="2b120-132">スパムに対して使用可能なフィルター処理の verdict アクションと、ZAP の結果については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="2b120-132">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="2b120-133">**X-ヘッダー**、 **先頭に件名行** を追加する: ZAP はメッセージに対してアクションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="2b120-133">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="2b120-134">**迷惑メールにメッセージを移動する**: 迷惑メールルールがメールボックスで有効になっていれば (既定で有効になっている場合)、メッセージは迷惑メールフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="2b120-134">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="2b120-135">詳細については、「 [Microsoft 365 の「Exchange Online メールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b120-135">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="2b120-136">メッセージ **を電子メールアドレス**、**削除メッセージ**、**検疫メッセージ**: ZAP 検疫メッセージにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="2b120-136">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="2b120-137">エンドユーザーは、自分のスパム検疫済みメッセージを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="2b120-137">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="2b120-138">既定では、スパム対策ポリシーでスパム ZAP が有効になっており、 **スパム** フィルター verdict の既定のアクションが **[迷惑メール] フォルダーに移動** します。この場合、スパム ZAP は **未読** メッセージを迷惑メールフォルダーに既定で移動します。</span><span class="sxs-lookup"><span data-stu-id="2b120-138">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="2b120-139">スパムフィルター verdicts の構成の詳細については、「 [Microsoft 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b120-139">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a><span data-ttu-id="2b120-140">Microsoft Defender for Office 365 に関する ZAP に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="2b120-140">ZAP considerations for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="2b120-141">ZAP は、安全な添付ファイルのスキャンで [動的配信](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) のプロセスに含まれるメッセージを検疫しません。または、EOP マルウェアフィルターによって添付ファイルが **マルウェアアラート Text.txt** ファイルに置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="2b120-141">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) in Safe Attachments scanning, or where EOP malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="2b120-142">このような種類のメッセージに対してフィッシングまたはスパムの信号を受信し、スパム対策ポリシーのフィルター verdict がメッセージに対して何らかのアクションを実行するように設定されている場合 ([迷惑メールに移動] に移動)、ZAP は既定で [迷惑メールに移行] アクションになります。</span><span class="sxs-lookup"><span data-stu-id="2b120-142">If a phishing or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, or Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="2b120-143">ZAP がメッセージを移動したかどうかを確認する方法</span><span class="sxs-lookup"><span data-stu-id="2b120-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="2b120-144">ZAP がメッセージを移動したかどうかを確認するには、 [脅威保護状態レポート](view-email-security-reports.md#threat-protection-status-report) または [脅威エクスプローラー (およびリアルタイム検出)](threat-explorer.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b120-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="2b120-145">システムアクションとして、ZAP が Exchange メールボックス監査ログに記録されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2b120-145">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="2b120-146">ZAP FAQ</span><span class="sxs-lookup"><span data-stu-id="2b120-146">ZAP FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="2b120-147">正当なメッセージが迷惑メールフォルダーに移動された場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="2b120-147">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="2b120-148">誤 [検知](report-junk-email-messages-to-microsoft.md)には通常のレポートプロセスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b120-148">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="2b120-149">メッセージが [受信トレイ] から [迷惑メール] フォルダーに移動されるのは、サービスがスパムまたは悪意のあるメッセージであると判断した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="2b120-149">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="2b120-150">迷惑メールフォルダーではなく、検疫フォルダーを使用している場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="2b120-150">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="2b120-151">ZAP は、このトピックの前半で説明したように、スパム対策ポリシーの構成に基づいてメッセージに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b120-151">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this topic.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="2b120-152">差出人セーフリスト、メールフロールール、許可/ブロックされる送信者リストを使用している場合は、どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="2b120-152">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="2b120-153">信頼できる差出人、メールフロールール、またはブロックと許可の組織設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="2b120-153">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="2b120-154">これらのメッセージは、サービスが設定した内容を実行しているため、ZAP から除外されます。</span><span class="sxs-lookup"><span data-stu-id="2b120-154">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="2b120-155">これは、フィルター処理をバイパスするようにメッセージを構成するためのもう1つの理由です。</span><span class="sxs-lookup"><span data-stu-id="2b120-155">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="2b120-156">メッセージが別のフォルダー (たとえば、受信トレイルールなど) に移動した場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="2b120-156">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="2b120-157">ZAP は、メッセージが削除されていない場合、または同じまたはより強力なアクションがまだ適用されていない限り、引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="2b120-157">ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="2b120-158">たとえば、[フィッシング対策] ポリシーが [検疫] に設定され、メッセージが既に迷惑メールに含まれている場合、ZAP はメッセージを検疫するアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b120-158">For example, if the anti-phishing policy is set to quarantine and message is already in the Junk Email, then ZAP will take action to quarantine the message.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="2b120-159">ZAP がメールボックスを保留にする方法</span><span class="sxs-lookup"><span data-stu-id="2b120-159">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="2b120-160">ZAP は、保留中のメールボックスからのメッセージを検疫しません。</span><span class="sxs-lookup"><span data-stu-id="2b120-160">ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="2b120-161">ZAP は、スパム対策ポリシーでスパムまたはフィッシング verdict に対して構成されたアクションに基づいて、メッセージを [迷惑メール] フォルダーに移動できます。</span><span class="sxs-lookup"><span data-stu-id="2b120-161">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="2b120-162">Exchange Online のホールドの詳細については、「 [インプレース保持と訴訟ホールド (Exchange online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b120-162">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
