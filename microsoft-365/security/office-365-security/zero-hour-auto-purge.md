---
title: ゼロアワー自動消去 - スパムまたはマルウェアからの保護
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
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
description: ゼロ時間自動削除 (ZAP) は、ユーザーの受信トレイに既に配信されているスパムまたはマルウェアを含むメッセージを検出し、その悪意のあるコンテンツを無害にする電子メール保護機能です。 これは、検出された悪意のあるコンテンツの種類によってどのような違いがありますか。
ms.openlocfilehash: dd702e88dc2400367330d9cb1b54b5b0017334e4
ms.sourcegitcommit: caa3f681a68daf5e463093a922c3d6f378143d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "39191232"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="37b7a-104">ゼロアワー自動消去 - スパムまたはマルウェアからの保護</span><span class="sxs-lookup"><span data-stu-id="37b7a-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="37b7a-105">概要</span><span class="sxs-lookup"><span data-stu-id="37b7a-105">Overview</span></span>

<span data-ttu-id="37b7a-106">ゼロ時間自動削除 (ZAP) は、ユーザーの受信トレイに既に配信されているフィッシング、スパム、またはマルウェアを含むメッセージを検出し、悪意のあるコンテンツを表示する電子メール保護機能です。</span><span class="sxs-lookup"><span data-stu-id="37b7a-106">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless.</span></span> <span data-ttu-id="37b7a-107">これは、検出された悪意のあるコンテンツの種類によってどのような違いがありますか。</span><span class="sxs-lookup"><span data-stu-id="37b7a-107">How ZAP does this depends on the type of malicious content detected.</span></span> <span data-ttu-id="37b7a-108">メールの内容、Url、または添付ファイルのため、メールを zapped することができます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-108">Mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="37b7a-109">ZAP は、Exchange Online メールボックスを含む Office 365 サブスクリプションに含まれている既定の Exchange Online Protection で利用できます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-109">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="37b7a-110">ZAP のしくみ</span><span class="sxs-lookup"><span data-stu-id="37b7a-110">How ZAP works</span></span>

<span data-ttu-id="37b7a-111">Office 365 は、毎日スパム対策エンジンとマルウェア署名をリアルタイムで更新します。</span><span class="sxs-lookup"><span data-stu-id="37b7a-111">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="37b7a-112">ただし、ユーザーが配信された後にコンテンツが weaponized されている場合を含め、さまざまな理由で、ユーザーは引き続き悪意のあるメッセージを受信トレイに配信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="37b7a-112">However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="37b7a-113">ZAP は、継続的に Office 365 スパムおよびマルウェア署名の更新を監視することによって解決します。</span><span class="sxs-lookup"><span data-stu-id="37b7a-113">ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="37b7a-114">ZAP は、既にユーザーの受信トレイにある配信済みメッセージを見つけて削除することができます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-114">ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span>

<span data-ttu-id="37b7a-115">ZAP アクションは、メールボックスユーザーにとってシームレスです。電子メールメッセージが移動された場合は通知されません。</span><span class="sxs-lookup"><span data-stu-id="37b7a-115">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span> <span data-ttu-id="37b7a-116">メッセージを2日より前にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="37b7a-116">Message must not be older than 2 days.</span></span>
  
<span data-ttu-id="37b7a-117">許可リスト、[メールフロールール](https://go.microsoft.com/fwlink/p/?LinkId=722755)(トランスポートルールとも呼ばれます)、およびエンドユーザールールまたは追加フィルターは、ZAP より優先されます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-117">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755) (also known as transport rules), and end user rules or additional filters take precedence over ZAP.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="37b7a-118">マルウェアの ZAP</span><span class="sxs-lookup"><span data-stu-id="37b7a-118">Malware ZAP</span></span>

<span data-ttu-id="37b7a-119">新たに検出されたマルウェアの場合、ZAP は電子メールメッセージから添付ファイルを削除し、ユーザーのメールボックスにメッセージの本文を残します。</span><span class="sxs-lookup"><span data-stu-id="37b7a-119">For newly detected malware, ZAP removes attachments from email messages, leaving the body of the message in the user's mailbox.</span></span> <span data-ttu-id="37b7a-120">添付ファイルは、メールの開封状況に関係なく削除されます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-120">Attachments are removed regardless of the read status of the mail.</span></span>

<span data-ttu-id="37b7a-121">マルウェアの ZAP は、マルウェアポリシーで既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="37b7a-121">Malware ZAP is enabled by default in the Malware Policy.</span></span> <span data-ttu-id="37b7a-122">Exchange Online PowerShell または Exchange Online Protection PowerShell で[new-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)コマンドレットの*zapenabled*パラメーターを使用して、マルウェアの ZAP を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-122">You can disable Malware ZAP by using the *ZapEnabled* parameter on the [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="37b7a-123">セキュリティ/コンプライアンスセンターでマルウェアポリシーを編集することによって、マルウェアの ZAP を有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-123">Malware ZAP can also be enabled or disabled by editing the Malware Policy in the Security and Compliance Center.</span></span>

### <a name="phish-zap"></a><span data-ttu-id="37b7a-124">フィッシング ZAP</span><span class="sxs-lookup"><span data-stu-id="37b7a-124">Phish ZAP</span></span>

<span data-ttu-id="37b7a-125">配信後にフィッシングとして識別されるメールの場合、ZAP は、メールの読み取り状態に関係なく、特定のユーザーを対象とするスパムポリシーに従って処理を行います。</span><span class="sxs-lookup"><span data-stu-id="37b7a-125">For mail that is identified as phish after delivery, ZAP takes action according to the Spam policy that covers a specific user, regardless of the read status of the mail.</span></span> <span data-ttu-id="37b7a-126">[Policy フィッシング] アクションが [操作を行わ*ない*(追加する X-ヘッダー、件名の変更、アクションなし)] に設定されている場合、ZAP はメールに対して何のアクションも実行しません。</span><span class="sxs-lookup"><span data-stu-id="37b7a-126">If the policy Phish action is set to *not* take action (Add X-header, Modify subject, No action) then ZAP will not take any action on the mail.</span></span> <span data-ttu-id="37b7a-127">フィッシングアクションが迷惑メールに移行するように設定されている場合、ZAP はメッセージをユーザーの受信トレイの迷惑メールフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="37b7a-127">If the Phish action is set to Move to Junk then ZAP will move the message to the Junk mail folder of the user's inbox.</span></span> <span data-ttu-id="37b7a-128">**その他のフィッシングアクション (リダイレクト、削除、検疫) ZAP では、メッセージはフィッシング検疫に移動され**ます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-128">**For any other Phish action (Redirect, Delete, Quarantine) ZAP will move the message to phish Quarantine**.</span></span> <span data-ttu-id="37b7a-129">構成の要件と除外については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37b7a-129">Read below for configuration requirements and exclusions.</span></span> <span data-ttu-id="37b7a-130">ここでは[、スパムフィルターポリシーを構成](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="37b7a-130">Learn more about how to [configure your spam filter policies](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) here.</span></span>  

<span data-ttu-id="37b7a-131">スパムポリシーでは、フィッシング ZAP が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="37b7a-131">Phish ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="37b7a-132">フィッシング ZAP[は、EOP コマンドレットの](https://go.microsoft.com/fwlink/p/?LinkId=722758) *PhishZapEnabled*パラメーターを使用して無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-132">Phish ZAP can be disabled using the *PhishZapEnabled* parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>

### <a name="spam-zap"></a><span data-ttu-id="37b7a-133">スパム ZAP</span><span class="sxs-lookup"><span data-stu-id="37b7a-133">Spam ZAP</span></span>

<span data-ttu-id="37b7a-134">配信後にスパムとして識別されるメールの場合、ZAP は、メッセージが未読の場合にのみ、特定のユーザーを対象としたスパムポリシーに従って処理を行います。</span><span class="sxs-lookup"><span data-stu-id="37b7a-134">For mail that is identified as spam after delivery, ZAP takes action according to the Spam policy that covers the specific user, only if the message is unread.</span></span>  <span data-ttu-id="37b7a-135">[迷惑メールの処理] アクションが行われない ([X-ヘッダーの追加]、[件名の変更]、[アクションなし)] の順に設定した場合、ZAP はメールに対して何のアクションも実行しません。</span><span class="sxs-lookup"><span data-stu-id="37b7a-135">If the policy Spam action is set to not take action (Add X-header, Modify subject, No action) then ZAP won't take any action on the mail.</span></span> <span data-ttu-id="37b7a-136">スパムアクションが迷惑メールに移行するように設定されている場合、ZAP はメッセージをユーザーの受信トレイの迷惑メールフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="37b7a-136">If the Spam action is set to Move to Junk then ZAP will move the message to the Junk mail folder of the user's inbox.</span></span> <span data-ttu-id="37b7a-137">**その他のスパム操作 (リダイレクト、削除、検疫) ZAP では、メッセージはスパム検疫に移動され**ます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-137">**For any other Spam action (Redirect, Delete, Quarantine) ZAP will move the message to spam Quarantine**.</span></span> <span data-ttu-id="37b7a-138">構成の要件と除外については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37b7a-138">Read below for configuration requirements and exclusions.</span></span> <span data-ttu-id="37b7a-139">ここでは[、スパムフィルターポリシーを構成](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="37b7a-139">Learn more about how to [configure your spam filter policies](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) here.</span></span>

<span data-ttu-id="37b7a-140">スパム ZAP は、スパムポリシーでは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="37b7a-140">Spam ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="37b7a-141">Exchange Online PowerShell または Exchange Online Protection PowerShell で[set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)コマンドレットの*SpamZapEnabled*パラメーターを使用して、スパム ZAP を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-141">You can disable Spam ZAP by using the *SpamZapEnabled* parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

###<a name="phish-and-spam-zap-requirements-exclusions-and-notices"></a><span data-ttu-id="37b7a-142">フィッシングおよびスパム ZAP の要件、除外、および通知</span><span class="sxs-lookup"><span data-stu-id="37b7a-142">Phish and Spam ZAP requirements, exclusions, and notices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37b7a-143">フィッシングとスパム ZAP の両方を制御する前の*Zapenabled*コマンドレットパラメーターは、 **2020 年2月1日に廃止**されます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-143">the previous *ZapEnabled* cmdlet parameter which controlled both Phish and Spam ZAP will be **deprecated February 1, 2020**.</span></span> <span data-ttu-id="37b7a-144">ZapEnabled パラメーターを使用するスクリプトを記述した場合は、SpamZapEnabled と PhishZapEnabled を使用するように更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="37b7a-144">If you have written any scripts which use the ZapEnabled parameter, we recommend updating them to use SpamZapEnabled and PhishZapEnabled.</span></span> <span data-ttu-id="37b7a-145">移行期間では、3つすべてのパラメーター (ZapEnabled、PhishZapEnabled、および SpamZapEnabled) がコマンドレットで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="37b7a-145">In the transitional period all 3 parameters (ZapEnabled, PhishZapEnabled, and SpamZapEnabled) will be available through the cmdlet.</span></span> <span data-ttu-id="37b7a-146">UI または PowerShell を使用して明示的に設定されるまで、PhishZapEnabled と SpamZapEnabled は ZapEnabled パラメーターから継承した値を表示します。</span><span class="sxs-lookup"><span data-stu-id="37b7a-146">Until explicitly set via UI or PowerShell, PhishZapEnabled and SpamZapEnabled will show an inherited value from the ZapEnabled parameter.</span></span> <span data-ttu-id="37b7a-147">新しいパラメーターが設定されると、ZapEnabled パラメーターから継承されなくなります。</span><span class="sxs-lookup"><span data-stu-id="37b7a-147">Once the new parameters are set, they will no longer inherit from the ZapEnabled parameter.</span></span> <span data-ttu-id="37b7a-148">使用されなくなった場合、ZapEnabled が PhishZapEnabled または SpamZapEnabled プロパティに影響を与えることはありません。また、ZapEnabled はコマンドレットのパラメータリストから削除されます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-148">After it is deprecated setting ZapEnabled will have no affect on the PhishZapEnabled or SpamZapEnabled properties and ZapEnabled will be removed from the list of parameters in cmdlets.</span></span>

<span data-ttu-id="37b7a-149">ZAP は、動的配信スキャンのプロセスに含まれるすべてのメッセージ、または既にマルウェアが verdict に置き換えられた添付ファイルを持つ検疫に移動しません。</span><span class="sxs-lookup"><span data-stu-id="37b7a-149">ZAP will not move any message to Quarantine which is in the process of Dynamic Delivery scanning, or which already has a Malware verdict with a replaced attachment.</span></span> <span data-ttu-id="37b7a-150">これらの種類のメッセージに対してフィッシングまたはスパムのシグナルを受信し、Spam policy/フィッシングアクションを実行するように設定されている場合 ([迷惑メールに移動] に移動)、ZAP は既定で [迷惑メールに移動] アクションになります。</span><span class="sxs-lookup"><span data-stu-id="37b7a-150">If a phish or spam signal is received for these types of messages and the Spam policy / Phish action is set to take some action (Move to Junk, Redirect, Delete, Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span> <span data-ttu-id="37b7a-151">メッセージに対して [迷惑メールに移動] アクションを使用するには、ユーザーは既定の迷惑メール設定を使用して、迷惑メール保護を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="37b7a-151">For ZAP to take a 'Move to Junk' action on a message, the user must have their junk email protection enabled, with the default junk mail settings.</span></span> <span data-ttu-id="37b7a-152">(Outlook のユーザーオプションの詳細については[、「迷惑メールフィルターの保護レベルを変更](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="37b7a-152">(See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="37b7a-153">ZAP がメッセージを移動したかどうかを確認する方法</span><span class="sxs-lookup"><span data-stu-id="37b7a-153">How to see if ZAP moved your message</span></span>

<span data-ttu-id="37b7a-154">ZAP がメッセージを移動したかどうかを確認するには、[脅威保護状態レポート](../../compliance/view-email-security-reports.md#threat-protection-status-report)または[脅威エクスプローラー (およびリアルタイム検出)](threat-explorer.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-154">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](../../compliance/view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span>

## <a name="disable-zap"></a><span data-ttu-id="37b7a-155">ZAP を無効にする</span><span class="sxs-lookup"><span data-stu-id="37b7a-155">Disable ZAP</span></span>

<span data-ttu-id="37b7a-156">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37b7a-156">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span> <span data-ttu-id="37b7a-157">Exchange Online Protection PowerShell に接続するには、「 [Exchange Online protection の powershell への接続](https://go.microsoft.com/fwlink/p/?linkid=627290)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37b7a-157">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span>

### <a name="disable-malware-zap"></a><span data-ttu-id="37b7a-158">マルウェアの無効化 \* \*</span><span class="sxs-lookup"><span data-stu-id="37b7a-158">Disable Malware ZAP\*\*</span></span>

<span data-ttu-id="37b7a-159">[New-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)コマンドレットでは、Exchange online powershell または Exchange Online Protection Powershell で*zapenabled*パラメーターを使用して、マルウェアの ZAP を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-159">Malware ZAP can be disabled through the *ZapEnabled* parameter on the [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="37b7a-160">セキュリティ/コンプライアンスセンターでマルウェアポリシーを編集することによって、マルウェアの ZAP を有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-160">Malware ZAP can also be enabled or disabled by editing the Malware Policy in the Security and Compliance Center.</span></span>
 
<span data-ttu-id="37b7a-161">この例では、"Test" という名前のマルウェアフィルターポリシーの ZAP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="37b7a-161">This example disables ZAP in the malware filter policy named "Test".</span></span>
 
```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```
 
<span data-ttu-id="37b7a-162">構文とパラメーターの詳細については、「[Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37b7a-162">For detailed syntax and parameter information, see [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).</span></span>

### <a name="disable-phish-zap-and-spam-zap"></a><span data-ttu-id="37b7a-163">フィッシング ZAP とスパム ZAP を無効にする</span><span class="sxs-lookup"><span data-stu-id="37b7a-163">Disable Phish ZAP and Spam ZAP</span></span>

<span data-ttu-id="37b7a-164">O365 テナントまたはユーザーのセットに対してフィッシングおよびスパム ZAP を無効にするに[は、EOP コマンドレットの](https://go.microsoft.com/fwlink/p/?LinkId=722758) *PhishZapEnabled*パラメーターと*SpamZapEnabled*パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="37b7a-164">To disable Phish and Spam ZAP for your O365 tenant, or a set of users, use the *PhishZapEnabled* and *SpamZapEnabled* parameters of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>

<span data-ttu-id="37b7a-165">次の例では、"Test" という名前のコンテンツフィルターポリシーに対してフィッシングおよびスパム ZAP が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="37b7a-165">In the following example, phish and spam ZAP are disabled for a content filter policy named "Test".</span></span>

```Powershell
Set-HostedContentFilterPolicy -Identity Test -PhishZapEnabled $false -SpamZapEnabled $false
```

<span data-ttu-id="37b7a-166">構文およびパラメーターの詳細については、「 [set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37b7a-166">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758).</span></span>

## <a name="faq"></a><span data-ttu-id="37b7a-167">FAQ</span><span class="sxs-lookup"><span data-stu-id="37b7a-167">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="37b7a-168">正当なメッセージが迷惑メールフォルダーに移動された場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="37b7a-168">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="37b7a-169">誤[検知](../../compliance/prevent-email-from-being-marked-as-spam.md)の通常のレポートプロセスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="37b7a-169">You should follow the normal reporting process for [false-positives](../../compliance/prevent-email-from-being-marked-as-spam.md).</span></span> <span data-ttu-id="37b7a-170">メッセージが [受信トレイ] から [迷惑メール] フォルダーに移動されるのは、サービスがスパムまたは悪意のあるメッセージであると判断した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="37b7a-170">The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="37b7a-171">迷惑メールフォルダーではなく、Office 365 検疫を使用している場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="37b7a-171">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="37b7a-172">ZAP は、スパム対策ポリシーのフィッシングおよびスパムの処理設定の構成に従って処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="37b7a-172">ZAP will take action according to the configuration of the Phish and Spam action settings in your Anti-spam policy.</span></span> <span data-ttu-id="37b7a-173">マルウェア、フィッシング、スパム ZAP の詳細については、上記を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37b7a-173">See above for more details on Malware, Phish, and Spam ZAP.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="37b7a-174">カスタムメールフロールール (ブロック/許可ルール) を持っている場合</span><span class="sxs-lookup"><span data-stu-id="37b7a-174">What if I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="37b7a-175">管理者によって作成されたルール (メールフロールール) またはブロックと許可ルールが優先されます。</span><span class="sxs-lookup"><span data-stu-id="37b7a-175">Rules created by admins (mail flow rules) or Block and Allow rules take precedence.</span></span> <span data-ttu-id="37b7a-176">このようなメッセージは、機能の条件から除外されるので、メールフローはルールの処理 (ブロック/許可ルール) に従います。</span><span class="sxs-lookup"><span data-stu-id="37b7a-176">Such messages are excluded from the feature criteria so the mail flow will follow the rule action (Block/Allow Rule).</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a><span data-ttu-id="37b7a-177">メッセージが別のフォルダー (たとえば、受信トレイルールなど) に移動した場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="37b7a-177">What if a message is moved to another folder (e.g. Inbox rule)?</span></span>

<span data-ttu-id="37b7a-178">この場合、ZAP は、メッセージが削除されているか、迷惑メールにある場合を除き、この場合でも動作します。</span><span class="sxs-lookup"><span data-stu-id="37b7a-178">ZAP still works in this case, unless the message has been deleted or is in Junk.</span></span>

## <a name="related-topics"></a><span data-ttu-id="37b7a-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="37b7a-179">Related Topics</span></span>

[<span data-ttu-id="37b7a-180">Office 365 の電子メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="37b7a-180">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="37b7a-181">検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする</span><span class="sxs-lookup"><span data-stu-id="37b7a-181">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
