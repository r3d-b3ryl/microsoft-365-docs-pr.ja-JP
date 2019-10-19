---
title: ゼロアワー自動消去 - スパムまたはマルウェアからの保護
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/11/2019
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
ms.openlocfilehash: 725dc9da9119169937231372585489bdf192b11e
ms.sourcegitcommit: 0d423b50d2f1f4eccd64e35e00f67313244efba9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "37319270"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="646c6-104">ゼロアワー自動消去 - スパムまたはマルウェアからの保護</span><span class="sxs-lookup"><span data-stu-id="646c6-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="646c6-105">概要</span><span class="sxs-lookup"><span data-stu-id="646c6-105">Overview</span></span>

<span data-ttu-id="646c6-106">ゼロ時間自動削除 (ZAP) は、ユーザーの受信トレイに既に配信されているフィッシング、スパム、またはマルウェアを含むメッセージを検出し、悪意のあるコンテンツを表示する電子メール保護機能です。</span><span class="sxs-lookup"><span data-stu-id="646c6-106">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless.</span></span> <span data-ttu-id="646c6-107">これは、検出された悪意のあるコンテンツの種類によってどのような違いがありますか。メールの内容、Url、または添付ファイルのため、メールを zapped することができます。</span><span class="sxs-lookup"><span data-stu-id="646c6-107">How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="646c6-108">ZAP は、Exchange Online メールボックスを含む Office 365 サブスクリプションに含まれている既定の Exchange Online Protection で利用できます。</span><span class="sxs-lookup"><span data-stu-id="646c6-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="646c6-109">ZAP は既定で有効になっていますが、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="646c6-109">ZAP is turned on by default, but the following conditions must be met:</span></span>
  
- <span data-ttu-id="646c6-110">**迷惑メールフォルダーにメッセージを移動**するように**スパムアクション**が設定されています。</span><span class="sxs-lookup"><span data-stu-id="646c6-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <span data-ttu-id="646c6-111">すべてのメールボックスを ZAP でスクリーニングしないようにする場合は、ユーザーのセットにのみ適用される新しいスパムフィルターポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="646c6-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="646c6-112">ユーザーが既定の迷惑メール設定を保持しており、迷惑メールの保護がオフになっていない。</span><span class="sxs-lookup"><span data-stu-id="646c6-112">Users have kept their default junk mail settings, and have not turned off junk email protection.</span></span> <span data-ttu-id="646c6-113">(Outlook のユーザーオプションの詳細については[、「迷惑メールフィルターの保護レベルを変更](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="646c6-113">(See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span>
  
## <a name="how-zap-works"></a><span data-ttu-id="646c6-114">ZAP のしくみ</span><span class="sxs-lookup"><span data-stu-id="646c6-114">How ZAP works</span></span>

<span data-ttu-id="646c6-115">Office 365 は、毎日スパム対策エンジンとマルウェア署名をリアルタイムで更新します。</span><span class="sxs-lookup"><span data-stu-id="646c6-115">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="646c6-116">ただし、ユーザーが配信された後にコンテンツが weaponized されている場合を含め、さまざまな理由で、ユーザーは引き続き悪意のあるメッセージを受信トレイに配信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="646c6-116">However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="646c6-117">ZAP は、継続的に Office 365 スパムおよびマルウェア署名の更新を監視することによって解決します。</span><span class="sxs-lookup"><span data-stu-id="646c6-117">ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="646c6-118">ZAP は、既にユーザーの受信トレイにある配信済みメッセージを見つけて削除することができます。</span><span class="sxs-lookup"><span data-stu-id="646c6-118">ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span>

<span data-ttu-id="646c6-119">ZAP アクションは、メールボックスユーザーにとってシームレスです。電子メールメッセージが移動された場合は通知されません。</span><span class="sxs-lookup"><span data-stu-id="646c6-119">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span> <span data-ttu-id="646c6-120">メッセージを2日より前にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="646c6-120">Message must not be older than 2 days.</span></span>
  
<span data-ttu-id="646c6-121">許可リスト、[メールフロールール](https://go.microsoft.com/fwlink/p/?LinkId=722755)(トランスポートルールとも呼ばれます)、およびエンドユーザールールまたは追加フィルターは、ZAP より優先されます。</span><span class="sxs-lookup"><span data-stu-id="646c6-121">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755) (also known as transport rules), and end user rules or additional filters take precedence over ZAP.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="646c6-122">マルウェアの ZAP</span><span class="sxs-lookup"><span data-stu-id="646c6-122">Malware ZAP</span></span>

<span data-ttu-id="646c6-123">新たに検出されたマルウェアの場合、ZAP は電子メールメッセージから添付ファイルを削除し、ユーザーのメールボックスにメッセージの本文を残します。</span><span class="sxs-lookup"><span data-stu-id="646c6-123">For newly detected malware, ZAP removes attachments from email messages, leaving the body of the message in the user's mailbox.</span></span> <span data-ttu-id="646c6-124">添付ファイルは、メールの開封状況に関係なく削除されます。</span><span class="sxs-lookup"><span data-stu-id="646c6-124">Attachments are removed regardless of the read status of the mail.</span></span>

<span data-ttu-id="646c6-125">マルウェアの ZAP は、マルウェアポリシーで既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="646c6-125">Malware ZAP is enabled by default in the Malware Policy.</span></span> <span data-ttu-id="646c6-126">Exchange Online PowerShell または Exchange Online Protection PowerShell で[new-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)コマンドレットの*zapenabled*パラメーターを使用して、マルウェアの ZAP を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="646c6-126">You can disable Malware ZAP by using the *ZapEnabled* parameter on the [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="phish-zap"></a><span data-ttu-id="646c6-127">フィッシング ZAP</span><span class="sxs-lookup"><span data-stu-id="646c6-127">Phish ZAP</span></span>

<span data-ttu-id="646c6-128">配信後にフィッシングとして識別されるメールの場合、ZAP はユーザーが対象とするスパムポリシーに従って処理を行います。</span><span class="sxs-lookup"><span data-stu-id="646c6-128">For mail that is identified as phish after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="646c6-129">[Policy フィッシング] アクションがメールに対してアクションを実行するように設定されている場合 (リダイレクト、削除、検疫、迷惑メールへの移動)、ZAP により、メールの開封状況に関係なく、ユーザーの受信トレイの迷惑メールフォルダーにメッセージが移動されます。</span><span class="sxs-lookup"><span data-stu-id="646c6-129">If the policy Phish action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, regardless of the read status of the mail.</span></span> <span data-ttu-id="646c6-130">[ポリシーのフィッシング] アクションが [アクションを実行する] に設定されていない ([X-ヘッダーの追加]、[件名の変更]、[アクションなし]) 場合、ZAP はメールに対してアクションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="646c6-130">If the policy Phish action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="646c6-131">ここでは[、スパムフィルターポリシーを構成](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="646c6-131">Learn more about how to [configure your spam filter policies](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) here.</span></span>

<span data-ttu-id="646c6-132">スパムポリシーでは、フィッシング ZAP が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="646c6-132">Phish ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="646c6-133">フィッシング ZAP[は、EOP コマンドレットの](https://go.microsoft.com/fwlink/p/?LinkId=722758) *PhishZapEnabled*パラメーターを使用して無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="646c6-133">Phish ZAP can be disabled using the *PhishZapEnabled* parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>

> <span data-ttu-id="646c6-134">**[メモ]** フィッシングとスパム ZAP の両方を制御する Previous *zapenabled*コマンドレットパラメーターは、 **2020 年2月1日**に使用されなくなります。</span><span class="sxs-lookup"><span data-stu-id="646c6-134">**[NOTE]** the previous *ZapEnabled* cmdlet parameter which controlled both Phish and Spam ZAP will be **deprecated February 1, 2020**.</span></span> <span data-ttu-id="646c6-135">ZapEnabled パラメーターを使用するスクリプトを記述した場合は、SpamZapEnabled と PhishZapEnabled を使用するように更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="646c6-135">If you have written any scripts which use the ZapEnabled parameter, we recommend updating them to use SpamZapEnabled and PhishZapEnabled.</span></span> <span data-ttu-id="646c6-136">移行期間では、3つすべてのパラメーター (ZapEnabled、PhishZapEnabled、および SpamZapEnabled) がコマンドレットで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="646c6-136">In the transitional period all 3 parameters (ZapEnabled, PhishZapEnabled, and SpamZapEnabled) will be available through the cmdlet.</span></span> <span data-ttu-id="646c6-137">UI または PowerShell を使用して明示的に設定されるまで、PhishZapEnabled と SpamZapEnabled は ZapEnabled パラメーターから継承した値を表示します。</span><span class="sxs-lookup"><span data-stu-id="646c6-137">Until explicitly set via UI or PowerShell, PhishZapEnabled and SpamZapEnabled will show an inherited value from the ZapEnabled parameter.</span></span> <span data-ttu-id="646c6-138">新しいパラメーターが設定されると、ZapEnabled パラメーターから継承されなくなります。</span><span class="sxs-lookup"><span data-stu-id="646c6-138">Once the new parameters are set, they will no longer inherit from the ZapEnabled parameter.</span></span> <span data-ttu-id="646c6-139">使用されなくなった場合、ZapEnabled を設定しても、PhishZapEnabled または SpamZapEnabled のプロパティには影響しません。 ZapEnabled は、コマンドレットのパラメーターのリストから削除されます。</span><span class="sxs-lookup"><span data-stu-id="646c6-139">After it is deprecated, setting ZapEnabled will have no affect on the PhishZapEnabled or SpamZapEnabled properties and ZapEnabled will be removed from the list of parameters in cmdlets.</span></span>

### <a name="spam-zap"></a><span data-ttu-id="646c6-140">スパム ZAP</span><span class="sxs-lookup"><span data-stu-id="646c6-140">Spam ZAP</span></span>

<span data-ttu-id="646c6-141">配信後にスパムとして識別されるメールの場合、ZAP はユーザーが対象とするスパムポリシーに従って処理を行います。</span><span class="sxs-lookup"><span data-stu-id="646c6-141">For mail that is identified as spam after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="646c6-142">メールに対してアクションを実行するようにポリシーのスパムアクションが設定されている場合 (リダイレクト、削除、検疫、迷惑メールへの移動)、ZAP により、メッセージが未読の場合は、ユーザーの受信トレイの迷惑メールフォルダーにメッセージが移動されます。</span><span class="sxs-lookup"><span data-stu-id="646c6-142">If the policy Spam action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, if the message is unread.</span></span> <span data-ttu-id="646c6-143">[Policy Spam] アクションがアクションを実行するように設定されていない ([X-ヘッダーの追加]、[件名の変更]、[アクションなし]) 場合、ZAP はメールに対してアクションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="646c6-143">If the policy Spam action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="646c6-144">ここでは[、スパムフィルターポリシーを構成](configure-your-spam-filter-policies.md)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="646c6-144">Learn more about how to [Configure your spam filter policies](configure-your-spam-filter-policies.md) here.</span></span>

<span data-ttu-id="646c6-145">スパム ZAP は、スパムポリシーでは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="646c6-145">Spam ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="646c6-146">Exchange Online PowerShell または Exchange Online Protection PowerShell で[set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)コマンドレットの*SpamZapEnabled*パラメーターを使用して、スパム ZAP を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="646c6-146">You can disable Spam ZAP by using the *SpamZapEnabled* parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

> <span data-ttu-id="646c6-147">**[メモ]** フィッシングとスパム ZAP の両方を制御する Previous *zapenabled*コマンドレットパラメーターは、 **2020 年2月1日**に使用されなくなります。</span><span class="sxs-lookup"><span data-stu-id="646c6-147">**[NOTE]** the previous *ZapEnabled* cmdlet parameter which controlled both Phish and Spam ZAP will be **deprecated February 1, 2020**.</span></span> <span data-ttu-id="646c6-148">ZapEnabled パラメーターを使用するスクリプトを記述した場合は、SpamZapEnabled と PhishZapEnabled を使用するように更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="646c6-148">If you have written any scripts which use the ZapEnabled parameter, we recommend updating them to use SpamZapEnabled and PhishZapEnabled.</span></span> <span data-ttu-id="646c6-149">移行期間では、3つすべてのパラメーター (ZapEnabled、PhishZapEnabled、および SpamZapEnabled) がコマンドレットで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="646c6-149">In the transitional period all 3 parameters (ZapEnabled, PhishZapEnabled, and SpamZapEnabled) will be available through the cmdlet.</span></span> <span data-ttu-id="646c6-150">UI または PowerShell を使用して明示的に設定されるまで、PhishZapEnabled と SpamZapEnabled は ZapEnabled パラメーターから継承した値を表示します。</span><span class="sxs-lookup"><span data-stu-id="646c6-150">Until explicitly set via UI or PowerShell, PhishZapEnabled and SpamZapEnabled will show an inherited value from the ZapEnabled parameter.</span></span> <span data-ttu-id="646c6-151">新しいパラメーターが設定されると、ZapEnabled パラメーターから継承されなくなります。</span><span class="sxs-lookup"><span data-stu-id="646c6-151">Once the new parameters are set, they will no longer inherit from the ZapEnabled parameter.</span></span> <span data-ttu-id="646c6-152">使用されなくなった場合、ZapEnabled を設定しても、PhishZapEnabled または SpamZapEnabled のプロパティには影響しません。 ZapEnabled は、コマンドレットのパラメーターのリストから削除されます。</span><span class="sxs-lookup"><span data-stu-id="646c6-152">After it is deprecated, setting ZapEnabled will have no affect on the PhishZapEnabled or SpamZapEnabled properties and ZapEnabled will be removed from the list of parameters in cmdlets.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="646c6-153">ZAP がメッセージを移動したかどうかを確認する方法</span><span class="sxs-lookup"><span data-stu-id="646c6-153">How to see if ZAP moved your message</span></span>

<span data-ttu-id="646c6-154">ZAP がメッセージを移動したかどうかを確認するには、[脅威保護状態レポート](../../compliance/view-email-security-reports.md#threat-protection-status-report)または[脅威エクスプローラー (およびリアルタイム検出)](threat-explorer.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="646c6-154">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](../../compliance/view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span>

## <a name="disable-zap"></a><span data-ttu-id="646c6-155">ZAP を無効にする</span><span class="sxs-lookup"><span data-stu-id="646c6-155">Disable ZAP</span></span>

<span data-ttu-id="646c6-156">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="646c6-156">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span> <span data-ttu-id="646c6-157">Exchange Online Protection PowerShell に接続するには、「 [Exchange Online protection の powershell への接続](https://go.microsoft.com/fwlink/p/?linkid=627290)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="646c6-157">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span>

### <a name="disable-malware-zap"></a><span data-ttu-id="646c6-158">マルウェアの無効化 \* \*</span><span class="sxs-lookup"><span data-stu-id="646c6-158">Disable Malware ZAP\*\*</span></span>

<span data-ttu-id="646c6-159">この例では、"Test" という名前のマルウェアフィルターポリシーの ZAP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="646c6-159">This example disables ZAP in the malware filter policy named "Test".</span></span>

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="646c6-160">構文とパラメーターの詳細については、「[Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="646c6-160">For detailed syntax and parameter information, see [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).</span></span>

### <a name="disable-phish-zap-and-spam-zap"></a><span data-ttu-id="646c6-161">フィッシング ZAP とスパム ZAP を無効にする</span><span class="sxs-lookup"><span data-stu-id="646c6-161">Disable Phish ZAP and Spam ZAP</span></span>

<span data-ttu-id="646c6-162">O365 テナントまたはユーザーのセットに対してフィッシングおよびスパム ZAP を無効にするに[は、EOP コマンドレットの](https://go.microsoft.com/fwlink/p/?LinkId=722758) *PhishZapEnabled*パラメーターと*SpamZapEnabled*パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="646c6-162">To disable Phish and Spam ZAP for your O365 tenant, or a set of users, use the *PhishZapEnabled* and *SpamZapEnabled* parameters of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>

<span data-ttu-id="646c6-163">次の例では、"Test" という名前のコンテンツフィルターポリシーに対してフィッシングおよびスパム ZAP が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="646c6-163">In the following example, phish and spam ZAP are disabled for a content filter policy named "Test".</span></span>

```Powershell
Set-HostedContentFilterPolicy -Identity Test -PhishZapEnabled $false -SpamZapEnabled $false
```

<span data-ttu-id="646c6-164">構文およびパラメーターの詳細については、「 [set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="646c6-164">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758).</span></span>

## <a name="faq"></a><span data-ttu-id="646c6-165">FAQ</span><span class="sxs-lookup"><span data-stu-id="646c6-165">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="646c6-166">正当なメッセージが迷惑メールフォルダーに移動された場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="646c6-166">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="646c6-167">誤[検知](../../compliance/prevent-email-from-being-marked-as-spam.md)の通常のレポートプロセスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="646c6-167">You should follow the normal reporting process for [false-positives](../../compliance/prevent-email-from-being-marked-as-spam.md).</span></span> <span data-ttu-id="646c6-168">メッセージが [受信トレイ] から [迷惑メール] フォルダーに移動されるのは、サービスがスパムまたは悪意のあるメッセージであると判断した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="646c6-168">The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="646c6-169">迷惑メールフォルダーではなく、Office 365 検疫を使用している場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="646c6-169">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="646c6-170">この時点で、ZAP は受信トレイからメッセージを検疫に移動しません。</span><span class="sxs-lookup"><span data-stu-id="646c6-170">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="646c6-171">カスタムメールフロールール (ブロック/許可ルール) を持っている場合</span><span class="sxs-lookup"><span data-stu-id="646c6-171">What if I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="646c6-172">管理者によって作成されたルール (メールフロールール) またはブロックと許可ルールが優先されます。</span><span class="sxs-lookup"><span data-stu-id="646c6-172">Rules created by admins (mail flow rules) or Block and Allow rules take precedence.</span></span> <span data-ttu-id="646c6-173">このようなメッセージは、機能の条件から除外されるので、メールフローはルールの処理 (ブロック/許可ルール) に従います。</span><span class="sxs-lookup"><span data-stu-id="646c6-173">Such messages are excluded from the feature criteria so the mail flow will follow the rule action (Block/Allow Rule).</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a><span data-ttu-id="646c6-174">メッセージが別のフォルダー (たとえば、受信トレイルールなど) に移動した場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="646c6-174">What if a message is moved to another folder (e.g. Inbox rule)?</span></span>

<span data-ttu-id="646c6-175">この場合、ZAP は、メッセージが削除されているか、迷惑メールにある場合を除き、この場合でも動作します。</span><span class="sxs-lookup"><span data-stu-id="646c6-175">ZAP still works in this case, unless the message has been deleted or is in Junk.</span></span>

## <a name="related-topics"></a><span data-ttu-id="646c6-176">関連トピック</span><span class="sxs-lookup"><span data-stu-id="646c6-176">Related Topics</span></span>

[<span data-ttu-id="646c6-177">Office 365 の電子メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="646c6-177">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="646c6-178">検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする</span><span class="sxs-lookup"><span data-stu-id="646c6-178">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
