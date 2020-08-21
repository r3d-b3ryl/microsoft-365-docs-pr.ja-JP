---
title: ゼロアハンド消去 (ZAP)
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
description: 管理者は、ゼロア自動消去 (ZAP) が、Exchange Online メールボックス内の配信メッセージを、スパムやフィッシングとして再アクティブに見つかった [迷惑メール] フォルダーまたは検疫に、どのように再トロビードで移動できるかを学習できます。
ms.openlocfilehash: 9096486ed98657fede7927089592c92fffdad70e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826699"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a><span data-ttu-id="bd77a-103">Exchange Online のゼロアハル自動消去 (ZAP)</span><span class="sxs-lookup"><span data-stu-id="bd77a-103">Zero-hour auto purge (ZAP) in Exchange Online</span></span>

## <a name="basic-features-of-zap"></a><span data-ttu-id="bd77a-104">ZAP の基本機能</span><span class="sxs-lookup"><span data-stu-id="bd77a-104">Basic features of ZAP</span></span>

<span data-ttu-id="bd77a-105">Exchange Online にメールボックスがある Microsoft 365 組織では、ゼロアフォージョン自動消去 (ZAP) は、Exchange Online のメールボックスに配信済みの悪意のあるフィッシング、スパム、またはマルウェアのメッセージを再期的に検出して neutralizeするメール保護機能です。</span><span class="sxs-lookup"><span data-stu-id="bd77a-105">In Microsoft 365 organizations with mailboxes in Exchange Online, zero-hour auto purge (ZAP) is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="bd77a-106">ZAP は、オンプレミスの Exchange メールボックスを保護するスタンドアロン Exchange Online Protection (EOP) 環境では機能しません。</span><span class="sxs-lookup"><span data-stu-id="bd77a-106">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="bd77a-107">ZAP のしくみ</span><span class="sxs-lookup"><span data-stu-id="bd77a-107">How ZAP works</span></span>

<span data-ttu-id="bd77a-108">スパムとマルウェアのシグネチャは、サービスのリアルタイムで日単位で更新されます。</span><span class="sxs-lookup"><span data-stu-id="bd77a-108">Spam and malware signatures are updated in the service real-time on a daily basis.</span></span> <span data-ttu-id="bd77a-109">ただし、ユーザーに配信された後にコンテンツが統合されている場合など、さまざまな理由で悪意のあるメッセージをユーザーが受信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd77a-109">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="bd77a-110">ZAP は、サービスのスパムシグネチャとマルウェア シグネチャの更新をさらに監視して、この問題に対し対応します。</span><span class="sxs-lookup"><span data-stu-id="bd77a-110">ZAP addresses this issue by continually monitoring updates to the spam and malware signatures in the service.</span></span> <span data-ttu-id="bd77a-111">ZAP は、ユーザーのメールボックスに既に存在するメッセージを検索して削除できます。</span><span class="sxs-lookup"><span data-stu-id="bd77a-111">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="bd77a-112">ZAP アクションは、ユーザーに対してシームレスです。メッセージが検出され、移動された場合は通知されません。</span><span class="sxs-lookup"><span data-stu-id="bd77a-112">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="bd77a-113">[差出人セ](create-safe-sender-lists-in-office-365.md)ーフ リスト、メール フロー ルール (トランスポート ルールとも呼ばれる)、受信トレイ ルール、または他のフィルターは ZAP より優先されます。</span><span class="sxs-lookup"><span data-stu-id="bd77a-113">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="bd77a-114">これはメール フローで起きうのと同様に、サービスで配信されたメッセージが ZAP を必要であると判断しても、信頼できる差出人の構成が原因でメッセージが処理されなけれないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="bd77a-114">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="bd77a-115">フィルター処理をバイパスするメッセージの構成に関しては、このエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd77a-115">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="bd77a-116">マルウェア ZAP</span><span class="sxs-lookup"><span data-stu-id="bd77a-116">Malware ZAP</span></span>

<span data-ttu-id="bd77a-117">配信 **後にマルウェアを含むことが** 検出される読み取りまたは未読メッセージについては、ZAP がマルウェア添付ファイルを含むメッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="bd77a-117">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="bd77a-118">検疫からマルウェア メッセージを表示および管理できるのは管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="bd77a-118">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="bd77a-119">マルウェア対策ポリシーでは、マルウェア ZAP が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="bd77a-119">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="bd77a-120">詳細については [、EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bd77a-120">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="bd77a-121">フィッシング ZAP</span><span class="sxs-lookup"><span data-stu-id="bd77a-121">Phish ZAP</span></span>

<span data-ttu-id="bd77a-122">配信 **後フィッシング** として識別される開かれていたメッセージまたは未読メッセージの ZAP の結果は、適用可能なスパム対策ポリシーで **フィ** ッシングメール フィルターしか diinct に構成されるアクションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="bd77a-122">For **read or unread messages** that are identified as phish after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="bd77a-123">フィッシングに使用できるフィルターしきい値と ZAP 結果に対して使用可能なフィルター操作を次の一覧に示します。</span><span class="sxs-lookup"><span data-stu-id="bd77a-123">The available filtering verdict actions for phish and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="bd77a-124">**X-Header、件\*\*\*\*名行の前にテキストを追加**します。ZAP がメッセージに対して何もアクションを実行しなけれない。</span><span class="sxs-lookup"><span data-stu-id="bd77a-124">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="bd77a-125">**迷惑メールにメッセージを移動**: ZAP は、メールボックスで迷惑メール ルールが有効になっている (既定では有効になっている) ので、メッセージを [迷惑メール] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="bd77a-125">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="bd77a-126">詳細については [、「Microsoft 365 の Exchange Online メールボックスで迷惑メール設定を構成する」を参照してください](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="bd77a-126">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="bd77a-127">**メール アドレス、メッセージの削除**、**検疫メッセージ\*\*\*\*:** ZAP でメッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="bd77a-127">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span>

<span data-ttu-id="bd77a-128">既定では、フィッシング対策ポリシーではフィッシング ZAP が有効になっており、 **フ** ィッシング メール フィルタリングの詳細に対する既定のアクションは **Quarantine メッセージです**。これは、フィッシング ZAP が既定でメッセージを検疫するという意味です。</span><span class="sxs-lookup"><span data-stu-id="bd77a-128">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="bd77a-129">スパム フィルターの詳細の構成の詳細については [、「Microsoft 365 でスパム対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bd77a-129">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="bd77a-130">スパム ZAP</span><span class="sxs-lookup"><span data-stu-id="bd77a-130">Spam ZAP</span></span>

<span data-ttu-id="bd77a-131">配信 **後にスパム** として識別される未読メッセージについては、適用されるスパム対策ポリシーで **スパム** フィルター常ーディシングに構成されているアクションによって ZAP 結果が異なります。</span><span class="sxs-lookup"><span data-stu-id="bd77a-131">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="bd77a-132">次の一覧に、使用可能なスパムに対するフィルター指定アクションと ZAP 結果の例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd77a-132">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="bd77a-133">**X-Header、件\*\*\*\*名行の前にテキストを追加**します。ZAP がメッセージに対して何もアクションを実行しなけれない。</span><span class="sxs-lookup"><span data-stu-id="bd77a-133">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="bd77a-134">**迷惑メールにメッセージを移動**: ZAP は、メールボックスで迷惑メール ルールが有効になっている (既定では有効になっている) ので、メッセージを [迷惑メール] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="bd77a-134">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="bd77a-135">詳細については [、「Microsoft 365 の Exchange Online メールボックスで迷惑メール設定を構成する」を参照してください](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="bd77a-135">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="bd77a-136">**メール アドレス、メッセージの削除**、**検疫メッセージ\*\*\*\*:** ZAP でメッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="bd77a-136">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="bd77a-137">エンドユーザーは、自分のスパム検疫済みメッセージを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="bd77a-137">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="bd77a-138">既定では、スパム対策ポリシーではスパム ZAP が有効になっています。スパム 対策フィルター**Spam**解読の既定のアクションは **[迷惑メール] フォルダーに移動**されます。これは、スパム ZAP が既定で未**読**メッセージを [迷惑メール] フォルダーに移動することを意味します。</span><span class="sxs-lookup"><span data-stu-id="bd77a-138">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="bd77a-139">スパム フィルターの詳細の構成の詳細については [、「Microsoft 365 でスパム対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bd77a-139">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a><span data-ttu-id="bd77a-140">Office 365 Advanced Threat Protection (Office 365 ATP) の ZAP に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="bd77a-140">ZAP considerations for Office 365 Advanced Threat Protection (Office 365 ATP)</span></span>

<span data-ttu-id="bd77a-141">ZAP は動的配信スキャンの過中であるメッセージ [を検](dynamic-delivery-and-previewing.md) 疫しないか、マルウェア フィルター処理によって添付ファイルが既にマルウェア警告およびファイル ファイル **で置きText.txt** されません。</span><span class="sxs-lookup"><span data-stu-id="bd77a-141">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](dynamic-delivery-and-previewing.md) scanning, or where malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="bd77a-142">これらの種類のメッセージに対してフィッシングまたはスパム信号が受信され、スパム対策ポリシーのフィルター確認方法がメッセージに対して処理 ([迷惑メール、リダイレクト、削除、検疫に移動] に移動) を行うように設定されている場合、ZAP は既定で「迷惑メールに移動する」アクションに設定されます。</span><span class="sxs-lookup"><span data-stu-id="bd77a-142">If a phish or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="bd77a-143">ZAP がメッセージを移動したかを確認する方法</span><span class="sxs-lookup"><span data-stu-id="bd77a-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="bd77a-144">ZAP がメッセージを移動したかどうかを確認するには、脅威保護の [状態](view-email-security-reports.md#threat-protection-status-report) レポートまたは [脅威エクスプローラー (およびリアルタイムの検出) のどちらかを使用します](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="bd77a-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="bd77a-145">システム動作として、ZAP は Exchange メールボックス監査ログに記録されない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="bd77a-145">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="bd77a-146">ZAP FAQ</span><span class="sxs-lookup"><span data-stu-id="bd77a-146">ZAP FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="bd77a-147">[迷惑メール] フォルダーに移動するとどうなりうりますか?</span><span class="sxs-lookup"><span data-stu-id="bd77a-147">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="bd77a-148">誤検知の通常の報告 [プロセスに従う必要があります](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="bd77a-148">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="bd77a-149">メッセージが、メッセージがスパムか悪意のあるものであるとサービスによって判別されたため、メッセージが受信トレイから迷惑メール フォルダーに移動される理由は、そののみです。</span><span class="sxs-lookup"><span data-stu-id="bd77a-149">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="bd77a-150">迷惑メール フォルダーの代わりに [検疫] フォルダーを使用した場合の処理</span><span class="sxs-lookup"><span data-stu-id="bd77a-150">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="bd77a-151">前述のとおり、ZAP はスパム対策ポリシーに基づいてメッセージに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="bd77a-151">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this topic.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="bd77a-152">信頼できる送信者、メール フロー ルール、許可/受信拒否リストを使用している場合はどうですか。</span><span class="sxs-lookup"><span data-stu-id="bd77a-152">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="bd77a-153">差出人セーフ リスト、メール フロー ルール、組織の設定のブロック、および組織の設定の許可優先順位。</span><span class="sxs-lookup"><span data-stu-id="bd77a-153">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="bd77a-154">これらのメッセージは、サービスが構成内容を実行しているため、ZAP から除外されます。</span><span class="sxs-lookup"><span data-stu-id="bd77a-154">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="bd77a-155">フィルター処理をバイパスするメッセージの構成に関しては、このエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd77a-155">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="bd77a-156">メッセージが別のフォルダー (受信トレイのルールなど) に移動した場合、どうなりますか?</span><span class="sxs-lookup"><span data-stu-id="bd77a-156">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="bd77a-157">ZAP は、メッセージが削除されていない場合、または同じ操作または強力なアクションが適用されていない場合に機能します。</span><span class="sxs-lookup"><span data-stu-id="bd77a-157">ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="bd77a-158">たとえば、フィッシング ポリシーが検疫に設定されている場合、ユーザーまたは管理者が既にメールを迷惑メールにしている場合は、検疫を行ってファイルを検疫します。</span><span class="sxs-lookup"><span data-stu-id="bd77a-158">For example, if the phish policy is set to quarantine and the user or administrator has already junked the email, then quarantine will take action to quarantine the file.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="bd77a-159">ZAP はメールボックスの保持にどのような影響を与えるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="bd77a-159">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="bd77a-160">ZAP は、保留中のメールボックスからのメッセージを検疫しません。</span><span class="sxs-lookup"><span data-stu-id="bd77a-160">ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="bd77a-161">ZAP は、スパム対策ポリシーのスパムまたはフィッシングの頂点として構成されているアクションに基づいて、メッセージを [迷惑メール] フォルダーに移動できます。</span><span class="sxs-lookup"><span data-stu-id="bd77a-161">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="bd77a-162">Exchange Online でのホールドの詳細については、Exchange Online [のインプレース保持と訴訟ホールドを参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)。</span><span class="sxs-lookup"><span data-stu-id="bd77a-162">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
