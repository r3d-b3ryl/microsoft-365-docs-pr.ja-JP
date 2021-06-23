---
title: Microsoft Defender で 0 時間の自動削除を実行Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 06/22/2021
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
description: ゼロ時間自動削除 (ZAP) は、Exchange Online メールボックス内の配信されたメッセージを迷惑メール フォルダーまたは検疫にさかのぼって移動し、配信後にスパムやフィッシングと見なされます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fdfc39b8bd18d33f95b85028e3661008a17a1209
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083502"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a><span data-ttu-id="beaf2-103">ゼロ時間自動削除 (ZAP) (Exchange Online</span><span class="sxs-lookup"><span data-stu-id="beaf2-103">Zero-hour auto purge (ZAP) in Exchange Online</span></span>

<span data-ttu-id="beaf2-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="beaf2-104">**Applies to**</span></span>
- [<span data-ttu-id="beaf2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="beaf2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="beaf2-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="beaf2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="beaf2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="beaf2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="zero-hour-auto-purge-zap-basics"></a><span data-ttu-id="beaf2-108">ゼロ時間自動削除 (ZAP) の基本</span><span class="sxs-lookup"><span data-stu-id="beaf2-108">Zero-hour auto purge (ZAP) basics</span></span>

<span data-ttu-id="beaf2-109">Exchange Online のメールボックスを持つ Microsoft 365 組織では、ゼロ時間自動削除 (ZAP) は、Exchange Online メールボックスに既に配信されている悪意のあるフィッシング、スパム、マルウェア メッセージをさかのぼって検出し、中和する電子メール保護機能です。</span><span class="sxs-lookup"><span data-stu-id="beaf2-109">In Microsoft 365 organizations with mailboxes in Exchange Online, zero-hour auto purge (ZAP) is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="beaf2-110">ZAP は、オンプレミスのメールボックスを保護するスタンドアロン Exchange Online Protection (EOP) 環境Exchangeしません。</span><span class="sxs-lookup"><span data-stu-id="beaf2-110">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="beaf2-111">ZAP のしくみ</span><span class="sxs-lookup"><span data-stu-id="beaf2-111">How ZAP works</span></span>

<span data-ttu-id="beaf2-112">スパムやマルウェアの署名は、サービス内で毎日リアルタイムで更新されます。</span><span class="sxs-lookup"><span data-stu-id="beaf2-112">Spam and malware signatures are updated in the service real-time on a daily basis.</span></span> <span data-ttu-id="beaf2-113">ただし、ユーザーに配信された後にコンテンツが武器化される場合など、さまざまな理由で悪意のあるメッセージを受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="beaf2-113">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="beaf2-114">ZAP は、サービス内のスパムとマルウェアの署名に対する更新プログラムを継続的に監視することで、この問題に取り組む。</span><span class="sxs-lookup"><span data-stu-id="beaf2-114">ZAP addresses this issue by continually monitoring updates to the spam and malware signatures in the service.</span></span> <span data-ttu-id="beaf2-115">ZAP は、ユーザーのメールボックスに既に存在するメッセージを見つけて削除できます。</span><span class="sxs-lookup"><span data-stu-id="beaf2-115">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="beaf2-116">ZAP アクションはユーザーにシームレスです。メッセージが検出および移動された場合は、通知されません。</span><span class="sxs-lookup"><span data-stu-id="beaf2-116">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="beaf2-117">[セーフリスト、](create-safe-sender-lists-in-office-365.md)メール フロー ルール (トランスポート ルールとも呼ばれる)、受信トレイ ルール、または追加のフィルターが ZAP よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="beaf2-117">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="beaf2-118">メール フローで発生する処理と同様に、これは、サービスが配信されたメッセージに ZAP が必要と判断した場合でも、差出人セーフ リストの構成のためにメッセージが処理されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="beaf2-118">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="beaf2-119">これは、フィルター処理をバイパスするメッセージの構成に注意するもう 1 つの理由です。</span><span class="sxs-lookup"><span data-stu-id="beaf2-119">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="zero-hour-auto-purge-zap-for-malware"></a><span data-ttu-id="beaf2-120">マルウェアのゼロ時間自動削除 (ZAP)</span><span class="sxs-lookup"><span data-stu-id="beaf2-120">Zero-hour auto purge (ZAP) for malware</span></span>

<span data-ttu-id="beaf2-121">配信 **後にマルウェアが含まれている** と判明した読み取りメッセージまたは未読メッセージの場合、ZAP はマルウェア添付ファイルを含むメッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="beaf2-121">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="beaf2-122">検疫からマルウェア メッセージを表示および管理できるのは管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="beaf2-122">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="beaf2-123">マルウェアに対する ZAP は、マルウェア対策ポリシーで既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="beaf2-123">ZAP for malware is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="beaf2-124">詳細については [、「EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="beaf2-124">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

### <a name="zero-hour-auto-purge-zap-for-phishing"></a><span data-ttu-id="beaf2-125">フィッシングのゼロ時間自動削除 (ZAP)</span><span class="sxs-lookup"><span data-stu-id="beaf2-125">Zero-hour auto purge (ZAP) for phishing</span></span>

<span data-ttu-id="beaf2-126">配信後 **に** フィッシングとして識別される読み取りメッセージまたは未読メッセージの場合、ZAP の結果は、該当するスパム対策ポリシーのフィッシングメール フィルターの評決に対して構成されたアクションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="beaf2-126">For **read or unread messages** that are identified as phishing after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="beaf2-127">フィッシングに対して使用可能なフィルター処理の評決アクションと、可能な ZAP 結果については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="beaf2-127">The available filtering verdict actions for phishing and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="beaf2-128">**X-Header**、テキスト付 **き** 件名行の先頭に追加 **する、メッセージ** を電子メール アドレスにリダイレクト **する、メッセージ** を削除する: ZAP はメッセージに対してアクションを実行しない。</span><span class="sxs-lookup"><span data-stu-id="beaf2-128">**Add X-Header**, **Prepend subject line with text**, **Redirect message to email address**, **Delete message**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="beaf2-129">**メッセージを迷惑メールに** 移動する: ZAP は、メールボックスで迷惑メール ルールが有効になっている限り、メッセージを迷惑メール フォルダーに移動します (既定で有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="beaf2-129">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="beaf2-130">詳細については、「迷惑メールの[設定を構成する」を参照Exchange OnlineのメールボックスMicrosoft 365。](configure-junk-email-settings-on-exo-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="beaf2-130">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="beaf2-131">**検疫メッセージ**: ZAP はメッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="beaf2-131">**Quarantine message**: ZAP quarantines the message.</span></span>

<span data-ttu-id="beaf2-132">既定では、スパム対策ポリシーでフィッシングの ZAP が有効にされ、フィッシングメール フィルターの既定のアクションは検疫メッセージです。つまり、フィッシング検疫の ZAP は既定でメッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="beaf2-132">By default, ZAP for phishing is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means ZAP for phishing quarantines the message by default.</span></span>

<span data-ttu-id="beaf2-133">スパム フィルターの評決を構成する方法の詳細については、「[スパム](configure-your-spam-filter-policies.md)対策ポリシーを構成する」を参照Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="beaf2-133">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zero-hour-auto-purge-zap-for-high-confidence-phishing"></a><span data-ttu-id="beaf2-134">信頼性の高いフィッシングのためのゼロ時間自動削除 (ZAP)</span><span class="sxs-lookup"><span data-stu-id="beaf2-134">Zero-hour auto purge (ZAP) for high confidence phishing</span></span>

<span data-ttu-id="beaf2-135">配信 **後に高信頼** フィッシングとして識別される読み取りメッセージまたは未読メッセージの場合、ZAP はメッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="beaf2-135">For **read or unread messages** that are identified as high confidence phishing after delivery, ZAP quarantines the message.</span></span> <span data-ttu-id="beaf2-136">検疫からの信頼度の高いフィッシング メッセージを表示および管理できるのは管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="beaf2-136">Only admins can view and manage high confidence phish messages from quarantine.</span></span>

<span data-ttu-id="beaf2-137">信頼度の高いフィッシングの ZAP は既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="beaf2-137">ZAP for high confidence phish is enabled by default.</span></span> <span data-ttu-id="beaf2-138">詳細については、「Secure [by Default in Office 365」を参照してください](secure-by-default.md)。</span><span class="sxs-lookup"><span data-stu-id="beaf2-138">For more information, see [Secure by Default in Office 365](secure-by-default.md).</span></span>

### <a name="zero-hour-auto-purge-zap-for-spam"></a><span data-ttu-id="beaf2-139">スパムのゼロ時間自動削除 (ZAP)</span><span class="sxs-lookup"><span data-stu-id="beaf2-139">Zero-hour auto purge (ZAP) for spam</span></span>

<span data-ttu-id="beaf2-140">配信 **後に** スパムとして識別される未読メッセージの場合、ZAP の結果は、該当するスパム対策ポリシーのスパムフィルターの評決に対して構成されているアクションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="beaf2-140">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="beaf2-141">スパムに対して使用可能なフィルター処理の評決アクションと、その可能な ZAP 結果については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="beaf2-141">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="beaf2-142">**X-Header**、テキスト付 **き** 件名行の先頭に追加 **する、メッセージ** を電子メール アドレスにリダイレクト **する、メッセージ** を削除する: ZAP はメッセージに対してアクションを実行しない。</span><span class="sxs-lookup"><span data-stu-id="beaf2-142">**Add X-Header**, **Prepend subject line with text**, **Redirect message to email address**, **Delete message**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="beaf2-143">**メッセージを迷惑メールに** 移動する: ZAP は、メールボックスで迷惑メール ルールが有効になっている限り、メッセージを迷惑メール フォルダーに移動します (既定で有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="beaf2-143">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="beaf2-144">詳細については、「迷惑メールの[設定を構成する」を参照Exchange OnlineのメールボックスMicrosoft 365。](configure-junk-email-settings-on-exo-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="beaf2-144">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="beaf2-145">**検疫メッセージ**: ZAP はメッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="beaf2-145">**Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="beaf2-146">エンド ユーザーは、独自のスパム検疫済みメッセージを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="beaf2-146">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="beaf2-147">既定では、スパム ZAP はスパム対策ポリシーで有効にされ、スパム フィルターの評決の既定のアクションは[メッセージを迷惑メール フォルダーに移動する]です。つまり、スパム ZAP は既定で未読メッセージを迷惑メール フォルダーに移動します。 </span><span class="sxs-lookup"><span data-stu-id="beaf2-147">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="beaf2-148">スパム フィルターの評決を構成する方法の詳細については、「[スパム](configure-your-spam-filter-policies.md)対策ポリシーを構成する」を参照Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="beaf2-148">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zero-hour-auto-purge-zap-considerations-for-microsoft-defender-for-office-365"></a><span data-ttu-id="beaf2-149">Microsoft Defender のゼロ時間自動削除 (ZAP) に関する考慮事項 (Office 365</span><span class="sxs-lookup"><span data-stu-id="beaf2-149">Zero-hour auto purge (ZAP) considerations for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="beaf2-150">ZAP は、セーフ 添付ファイルのスキャンで動的配信 [](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)の過程にあるメッセージや、EOP マルウェア フィルターによって既に添付ファイルをマルウェア アラート Text.txtファイル **に置き** 換えたメッセージは検疫されません。</span><span class="sxs-lookup"><span data-stu-id="beaf2-150">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) in Safe Attachments scanning, or where EOP malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="beaf2-151">このような種類のメッセージに対してフィッシングまたはスパム信号が受信され、スパム対策ポリシーのフィルター処理の評決がメッセージに対して何らかのアクション (迷惑メールへの移動、リダイレクト、削除、または検疫) に設定されている場合、ZAP は既定で [迷惑メールに移動] アクションに設定されます。</span><span class="sxs-lookup"><span data-stu-id="beaf2-151">If a phishing or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, or Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="beaf2-152">ZAP がメッセージを移動した場合の確認方法</span><span class="sxs-lookup"><span data-stu-id="beaf2-152">How to see if ZAP moved your message</span></span>

<span data-ttu-id="beaf2-153">ZAP がメッセージを移動したかどうかを確認するには、脅威保護[](view-email-security-reports.md#threat-protection-status-report)状態レポートまたは脅威エクスプローラー (およびリアルタイムの検出) を[使用します](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="beaf2-153">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="beaf2-154">システム アクションとして、ZAP はメールボックス監査ログのExchangeされません。</span><span class="sxs-lookup"><span data-stu-id="beaf2-154">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zero-hour-auto-purge-zap-faq"></a><span data-ttu-id="beaf2-155">ゼロ時間自動削除 (ZAP) FAQ</span><span class="sxs-lookup"><span data-stu-id="beaf2-155">Zero-hour auto purge (ZAP) FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="beaf2-156">正当なメッセージが迷惑メール フォルダーに移動された場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="beaf2-156">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="beaf2-157">誤検知については、通常の報告プロセス [に従う必要があります](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="beaf2-157">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="beaf2-158">メッセージが受信トレイから迷惑メール フォルダーに移動される唯一の理由は、サービスがメッセージがスパムまたは悪意のあると判断したためです。</span><span class="sxs-lookup"><span data-stu-id="beaf2-158">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="beaf2-159">迷惑メール フォルダーの代わりに検疫フォルダーを使用する場合は、</span><span class="sxs-lookup"><span data-stu-id="beaf2-159">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="beaf2-160">ZAP は、この記事で前述したように、スパム対策ポリシーの構成に基づいてメッセージに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="beaf2-160">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this article.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="beaf2-161">差出人セーフ リスト、メール フロー ルール、許可またはブロックされた送信者リストを使用している場合は、</span><span class="sxs-lookup"><span data-stu-id="beaf2-161">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="beaf2-162">セーフ、メール フロー ルール、またはブロックし、組織の設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="beaf2-162">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="beaf2-163">これらのメッセージは、サービスが構成した処理を実行しているから ZAP から除外されます。</span><span class="sxs-lookup"><span data-stu-id="beaf2-163">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="beaf2-164">これは、フィルター処理をバイパスするメッセージの構成に注意するもう 1 つの理由です。</span><span class="sxs-lookup"><span data-stu-id="beaf2-164">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-are-the-licensing-requirements-for-zero-hour-auto-purge-zap-to-work"></a><span data-ttu-id="beaf2-165">ゼロ時間自動削除 (ZAP) のライセンス要件は何ですか?</span><span class="sxs-lookup"><span data-stu-id="beaf2-165">What are the licensing Requirements for Zero-hour auto purge (ZAP) to work?</span></span>

<span data-ttu-id="beaf2-166">ライセンスに制限はありません。</span><span class="sxs-lookup"><span data-stu-id="beaf2-166">There are no limitations on licenses.</span></span> <span data-ttu-id="beaf2-167">ZAP は、オンライン上でホストされているExchange動作します。</span><span class="sxs-lookup"><span data-stu-id="beaf2-167">ZAP works on all mailboxes hosted on Exchange online.</span></span> <span data-ttu-id="beaf2-168">ZAP は、オンプレミスのメールボックスを保護するスタンドアロン Exchange Online Protection (EOP) 環境Exchangeしません。</span><span class="sxs-lookup"><span data-stu-id="beaf2-168">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="beaf2-169">メッセージが別のフォルダー (受信トレイ ルールなど) に移動された場合は、どうしますか。</span><span class="sxs-lookup"><span data-stu-id="beaf2-169">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="beaf2-170">ゼロ時間自動削除は、メッセージが削除されていない限り、または同じ、またはより強力なアクションがまだ適用されていない限り、引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="beaf2-170">Zero-hour auto purge still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="beaf2-171">たとえば、フィッシング対策ポリシーが検疫に設定され、メッセージが既に迷惑メール内にある場合、ZAP はメッセージを検疫するアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="beaf2-171">For example, if the anti-phishing policy is set to quarantine and message is already in the Junk Email, then ZAP will take action to quarantine the message.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="beaf2-172">ZAP は、保留メールボックスにどのような影響を与えるのですか?</span><span class="sxs-lookup"><span data-stu-id="beaf2-172">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="beaf2-173">0 時間の自動削除では、保留のメールボックスからメッセージが検疫されます。</span><span class="sxs-lookup"><span data-stu-id="beaf2-173">Zero-hour auto purge will quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="beaf2-174">ZAP は、スパム対策ポリシーでスパムまたはフィッシングの評決用に構成されたアクションに基づいて、メッセージを迷惑メール フォルダーに移動できます。</span><span class="sxs-lookup"><span data-stu-id="beaf2-174">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="beaf2-175">インプレイス 保持と訴訟ホールドの詳細Exchange Online、インプレイス保持と訴訟ホールドを参照[Exchange Online。](/Exchange/security-and-compliance/in-place-and-litigation-holds)</span><span class="sxs-lookup"><span data-stu-id="beaf2-175">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
