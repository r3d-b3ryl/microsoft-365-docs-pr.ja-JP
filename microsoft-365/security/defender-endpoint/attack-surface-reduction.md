---
title: 攻撃表面の縮小ルールを使用してマルウェアの感染を防止する
description: 攻撃表面の縮小ルールは、悪用がアプリやスクリプトを使用してデバイスにマルウェアに感染するのを防ぐのに役立ちます。
keywords: 攻撃表面の縮小ルール、asr、hips、ホスト侵入防止システム、保護ルール、悪用防止、脆弱性対策、悪用、感染防止、Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 58c2230d3a2e3323f7b9a315ca5d2a049f5f44fb
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903854"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a><span data-ttu-id="31faf-104">攻撃表面の縮小ルールを使用してマルウェアの感染を防止する</span><span class="sxs-lookup"><span data-stu-id="31faf-104">Use attack surface reduction rules to prevent malware infection</span></span>

<span data-ttu-id="31faf-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="31faf-105">**Applies to:**</span></span>

- [<span data-ttu-id="31faf-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="31faf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- [<span data-ttu-id="31faf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31faf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a><span data-ttu-id="31faf-108">攻撃表面の縮小ルールが重要な理由</span><span class="sxs-lookup"><span data-stu-id="31faf-108">Why attack surface reduction rules are important</span></span>

<span data-ttu-id="31faf-109">組織の攻撃表面には、攻撃者が組織のデバイスやネットワークを侵害する可能性があるすべての場所が含まれています。</span><span class="sxs-lookup"><span data-stu-id="31faf-109">Your organization's attack surface includes all the places where an attacker could compromise your organization's devices or networks.</span></span> <span data-ttu-id="31faf-110">攻撃の表面を減らすことは、組織のデバイスとネットワークを保護する手段であり、攻撃者は攻撃を実行する方法が少なくなっています。</span><span class="sxs-lookup"><span data-stu-id="31faf-110">Reducing your attack surface means protecting your organization's devices and network, which leaves attackers with fewer ways to perform attacks.</span></span> <span data-ttu-id="31faf-111">Microsoft Defender for Endpoint で攻撃表面の縮小ルールを構成すると役立ちます。</span><span class="sxs-lookup"><span data-stu-id="31faf-111">Configuring attack surface reduction rules in Microsoft Defender for Endpoint can help!</span></span>

<span data-ttu-id="31faf-112">攻撃表面の縮小ルールは、次のような特定のソフトウェア動作を対象とします。</span><span class="sxs-lookup"><span data-stu-id="31faf-112">Attack surface reduction rules target certain software behaviors, such as:</span></span>

- <span data-ttu-id="31faf-113">ファイルのダウンロードまたは実行を試みる実行可能ファイルとスクリプトを起動する。</span><span class="sxs-lookup"><span data-stu-id="31faf-113">Launching executable files and scripts that attempt to download or run files;</span></span>
- <span data-ttu-id="31faf-114">難読化されたスクリプトまたはその他の疑わしいスクリプトを実行する。そして</span><span class="sxs-lookup"><span data-stu-id="31faf-114">Running obfuscated or otherwise suspicious scripts; and</span></span>
- <span data-ttu-id="31faf-115">通常の毎日の作業中にアプリが開始しない動作を実行します。</span><span class="sxs-lookup"><span data-stu-id="31faf-115">Performing behaviors that apps don't usually initiate during normal day-to-day work.</span></span>

<span data-ttu-id="31faf-116">このようなソフトウェアの動作は、正当なアプリケーションで見られる場合があります。ただし、これらの動作は、マルウェアを介して攻撃者によって悪用されるのが一般的なので、リスクが高いと見なされる場合が多い。</span><span class="sxs-lookup"><span data-stu-id="31faf-116">Such software behaviors are sometimes seen in legitimate applications; however, these behaviors are often considered risky because they are commonly abused by attackers through malware.</span></span> <span data-ttu-id="31faf-117">攻撃表面の縮小ルールは、リスクの高い動作を制限し、組織を安全に保つのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="31faf-117">Attack surface reduction rules can constrain risky behaviors and help keep your organization safe.</span></span>

<span data-ttu-id="31faf-118">攻撃表面の縮小ルールの構成の詳細については、「攻撃表面の縮小ルールを有効 [にする」を参照してください](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="31faf-118">For more information about configuring attack surface reduction rules, see [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

## <a name="assess-rule-impact-before-deployment"></a><span data-ttu-id="31faf-119">展開前にルールへの影響を評価する</span><span class="sxs-lookup"><span data-stu-id="31faf-119">Assess rule impact before deployment</span></span>

<span data-ttu-id="31faf-120">攻撃表面の縮小ルールがネットワークに与える影響を評価するには、このルールのセキュリティに関する推奨事項を [脅威と脆弱性の管理][で開きます](/windows/security/threat-protection/#tvm)。</span><span class="sxs-lookup"><span data-stu-id="31faf-120">You can assess how an attack surface reduction rule might affect your network by opening the security recommendation for that rule in [threat and vulnerability management](/windows/security/threat-protection/#tvm).</span></span>

:::image type="content" source="images/asrrecommendation.png" alt-text="攻撃表面の縮小ルールのセキュリティ reco":::

<span data-ttu-id="31faf-122">[推奨事項の詳細] ウィンドウで、ユーザーの影響を確認して、生産性に悪影響を及ぼさずに、ブロック モードでルールを有効にする新しいポリシーを受け入れ可能なデバイスの割合を確認します。</span><span class="sxs-lookup"><span data-stu-id="31faf-122">In the recommendation details pane, check for user impact to determine what percentage of your devices can accept a new policy enabling the rule in blocking mode without adversely affecting productivity.</span></span>

## <a name="audit-mode-for-evaluation"></a><span data-ttu-id="31faf-123">評価の監査モード</span><span class="sxs-lookup"><span data-stu-id="31faf-123">Audit mode for evaluation</span></span>

<span data-ttu-id="31faf-124">監査 [モードを使用して](audit-windows-defender.md) 、攻撃表面の縮小ルールが有効になっている場合に組織に与える影響を評価します。</span><span class="sxs-lookup"><span data-stu-id="31faf-124">Use [audit mode](audit-windows-defender.md) to evaluate how attack surface reduction rules would affect your organization if they were enabled.</span></span> <span data-ttu-id="31faf-125">監査モードですべてのルールを最初に実行して、そのルールがビジネスライン アプリケーションに与える影響を理解できます。</span><span class="sxs-lookup"><span data-stu-id="31faf-125">Run all rules in audit mode first so you can understand how they affect your line-of-business applications.</span></span> <span data-ttu-id="31faf-126">多くの業務用アプリケーションは、限られたセキュリティ上の懸念を持って記述され、マルウェアに似た方法でタスクを実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-126">Many line-of-business applications are written with limited security concerns, and they might perform tasks in ways that seem similar to malware.</span></span> <span data-ttu-id="31faf-127">監査データを監視し、必要なアプリケーションの [除外](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) を追加することで、生産性を低下させずに攻撃表面の縮小ルールを展開できます。</span><span class="sxs-lookup"><span data-stu-id="31faf-127">By monitoring audit data and [adding exclusions](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) for necessary applications, you can deploy attack surface reduction rules without reducing productivity.</span></span>

## <a name="warn-mode-for-users"></a><span data-ttu-id="31faf-128">ユーザーの警告モード</span><span class="sxs-lookup"><span data-stu-id="31faf-128">Warn mode for users</span></span>

<span data-ttu-id="31faf-129">(**NEW**!)警告モード機能の前に、有効になっている攻撃表面の縮小ルールを監査モードまたはブロック モードに設定できます。</span><span class="sxs-lookup"><span data-stu-id="31faf-129">(**NEW**!) Prior to warn mode capabilities, attack surface reduction rules that are enabled could be set to either audit mode or block mode.</span></span> <span data-ttu-id="31faf-130">新しい警告モードでは、攻撃表面の縮小ルールによってコンテンツがブロックされるたびに、コンテンツがブロックされたかどうかを示すダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="31faf-130">With the new warn mode, whenever content is blocked by an attack surface reduction rule, users see a dialog box that indicates the content is blocked.</span></span> <span data-ttu-id="31faf-131">ダイアログ ボックスには、コンテンツのブロックを解除するオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="31faf-131">The dialog box also offers the user an option to unblock the content.</span></span> <span data-ttu-id="31faf-132">その後、ユーザーはアクションを再試行し、操作が完了します。</span><span class="sxs-lookup"><span data-stu-id="31faf-132">The user can then retry their action, and the operation completes.</span></span> <span data-ttu-id="31faf-133">ユーザーがコンテンツのブロックを解除すると、コンテンツは 24 時間ブロック解除されたままで、その後ブロックが再開されます。</span><span class="sxs-lookup"><span data-stu-id="31faf-133">When a user unblocks content, the content remains unblocked for 24 hours, and then blocking resumes.</span></span>

<span data-ttu-id="31faf-134">警告モードは、ユーザーが自分のタスクを実行するために必要なコンテンツにアクセスするのを防ぐことなく、組織が攻撃表面の縮小ルールを設定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="31faf-134">Warn mode helps your organization have attack surface reduction rules in place without preventing users from accessing the content they need to perform their tasks.</span></span>

### <a name="requirements-for-warn-mode-to-work"></a><span data-ttu-id="31faf-135">警告モードが機能する要件</span><span class="sxs-lookup"><span data-stu-id="31faf-135">Requirements for warn mode to work</span></span>

<span data-ttu-id="31faf-136">警告モードは、次のバージョンの警告を実行しているデバイスWindows。</span><span class="sxs-lookup"><span data-stu-id="31faf-136">Warn mode is supported on devices running the following versions of Windows:</span></span>

- <span data-ttu-id="31faf-137">[Windows 10バージョン 1809](/windows/whats-new/whats-new-windows-10-version-1809)以降</span><span class="sxs-lookup"><span data-stu-id="31faf-137">[Windows 10, version 1809](/windows/whats-new/whats-new-windows-10-version-1809) or later</span></span>
- <span data-ttu-id="31faf-138">[Windows Server バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)以降</span><span class="sxs-lookup"><span data-stu-id="31faf-138">[Windows Server, version 1809](/windows-server/get-started/whats-new-in-windows-server-1809) or later</span></span>

<span data-ttu-id="31faf-139">Microsoft Defender ウイルス対策モードでリアルタイム保護を実行している[必要があります](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)。</span><span class="sxs-lookup"><span data-stu-id="31faf-139">Microsoft Defender Antivirus must be running with real-time protection in [Active mode](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state).</span></span>

<span data-ttu-id="31faf-140">さらに、マルウェア対策[Microsoft Defender ウイルス対策更新プログラムがインストールされていることを](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)確認します。</span><span class="sxs-lookup"><span data-stu-id="31faf-140">In addition, make sure [Microsoft Defender Antivirus and antimalware updates](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) are installed.</span></span>

- <span data-ttu-id="31faf-141">プラットフォームリリースの最小要件: `4.18.2008.9`</span><span class="sxs-lookup"><span data-stu-id="31faf-141">Minimum platform release requirement: `4.18.2008.9`</span></span>
- <span data-ttu-id="31faf-142">エンジンリリースの最小要件: `1.1.17400.5`</span><span class="sxs-lookup"><span data-stu-id="31faf-142">Minimum engine release requirement: `1.1.17400.5`</span></span>

<span data-ttu-id="31faf-143">詳細と更新プログラムの取得については [、「Update for Microsoft Defender マルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="31faf-143">For more information and to get your updates, see [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).</span></span>

### <a name="cases-where-warn-mode-is-not-supported"></a><span data-ttu-id="31faf-144">警告モードがサポートされていない場合</span><span class="sxs-lookup"><span data-stu-id="31faf-144">Cases where warn mode is not supported</span></span>

<span data-ttu-id="31faf-145">警告モードは、3 つの攻撃表面の縮小ルールを構成するときにサポートMicrosoft エンドポイント マネージャー。</span><span class="sxs-lookup"><span data-stu-id="31faf-145">Warn mode is not supported for three attack surface reduction rules when you configure them in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="31faf-146">(グループ ポリシーを使用して攻撃表面の縮小ルールを構成する場合は、警告モードがサポートされます)。警告モードを構成するときに警告モードをサポートしない 3 つのMicrosoft エンドポイント マネージャーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="31faf-146">(If you use Group Policy to configure your attack surface reduction rules, warn mode is supported.) The three rules that do not support warn mode when you configure them in Microsoft Endpoint Manager are as follows:</span></span>

- <span data-ttu-id="31faf-147">[ダウンロードした実行可能コンテンツ (GUID)](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)の起動から JavaScript または VBScript をブロックする `d3e037e1-3eb8-44c8-a917-57927947596d`</span><span class="sxs-lookup"><span data-stu-id="31faf-147">[Block JavaScript or VBScript from launching downloaded executable content](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`)</span></span>
- <span data-ttu-id="31faf-148">[WMI イベント サブスクリプション (GUID) による永続](#block-persistence-through-wmi-event-subscription) 化をブロック `e6db77e5-3df2-4cf1-b95a-636979351e5b` する</span><span class="sxs-lookup"><span data-stu-id="31faf-148">[Block persistence through WMI event subscription](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`)</span></span>
- <span data-ttu-id="31faf-149">[ランサムウェアに対する高度な保護を使用](#use-advanced-protection-against-ransomware) する `c1db55ab-c21a-4637-bb3f-a12568109d35` (GUID)</span><span class="sxs-lookup"><span data-stu-id="31faf-149">[Use advanced protection against ransomware](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`)</span></span>

<span data-ttu-id="31faf-150">さらに、以前のバージョンのバージョンのデバイスで警告モードはサポートWindows。</span><span class="sxs-lookup"><span data-stu-id="31faf-150">In addition, warn mode is not supported on devices running older versions of Windows.</span></span> <span data-ttu-id="31faf-151">このような場合、警告モードで実行するように構成された攻撃表面の縮小ルールは、ブロック モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="31faf-151">In those cases, attack surface reduction rules that are configured to run in warn mode will run in block mode.</span></span>

## <a name="notifications-and-alerts"></a><span data-ttu-id="31faf-152">通知とアラート</span><span class="sxs-lookup"><span data-stu-id="31faf-152">Notifications and alerts</span></span>

<span data-ttu-id="31faf-153">攻撃表面の縮小ルールがトリガーされるたびに、デバイスに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="31faf-153">Whenever an attack surface reduction rule is triggered, a notification is displayed on the device.</span></span> <span data-ttu-id="31faf-154">会社の詳細や連絡先情報を使用して[通知をカスタマイズ](customize-attack-surface-reduction.md#customize-the-notification)することができます。</span><span class="sxs-lookup"><span data-stu-id="31faf-154">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span>

<span data-ttu-id="31faf-155">さらに、特定の攻撃表面の縮小ルールがトリガーされると、アラートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="31faf-155">In addition, when certain attack surface reduction rules are triggered, alerts are generated.</span></span>

<span data-ttu-id="31faf-156">通知と生成されたアラートは、Defender ポータル ( ) (以前は Microsoft 365 ) で表示 [https://security.microsoft.com](https://security.microsoft.com) [Microsoft Defender セキュリティ センター)。](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="31faf-156">Notifications and any alerts that are generated can be viewed in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) (formerly called the [Microsoft Defender Security Center](microsoft-defender-security-center.md)).</span></span>

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a><span data-ttu-id="31faf-157">高度な狩猟と攻撃表面の縮小イベント</span><span class="sxs-lookup"><span data-stu-id="31faf-157">Advanced hunting and attack surface reduction events</span></span>

<span data-ttu-id="31faf-158">高度な検索を使用して、攻撃表面の縮小イベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="31faf-158">You can use advanced hunting to view attack surface reduction events.</span></span> <span data-ttu-id="31faf-159">受信データの量を合理化するために、高度な検索では、1 時間ごとに一意のプロセスのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="31faf-159">To streamline the volume of incoming data, only unique processes for each hour are viewable with advanced hunting.</span></span> <span data-ttu-id="31faf-160">攻撃表面の縮小イベントの時間は、1 時間以内に初めてイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="31faf-160">The time of an attack surface reduction event is the first time that event is seen within the hour.</span></span>

<span data-ttu-id="31faf-161">たとえば、午後 2 時の間に 10 台のデバイスで攻撃表面の縮小イベントが発生するとします。</span><span class="sxs-lookup"><span data-stu-id="31faf-161">For example, suppose that an attack surface reduction event occurs on 10 devices during the 2:00 PM hour.</span></span> <span data-ttu-id="31faf-162">最初のイベントが 2:15、最後の 2:45 に発生したとします。</span><span class="sxs-lookup"><span data-stu-id="31faf-162">Suppose that the first event occurred at 2:15, and the last at 2:45.</span></span> <span data-ttu-id="31faf-163">高度な検索では、そのイベントのインスタンスが 1 つ表示されます (実際には 10 台のデバイスで発生した場合でも)、タイムスタンプは午後 2 時 15 分になります。</span><span class="sxs-lookup"><span data-stu-id="31faf-163">With advanced hunting, you'll see one instance of that event (even though it actually occurred on 10 devices), and its timestamp will be 2:15 PM.</span></span>

<span data-ttu-id="31faf-164">高度な狩猟の詳細については、「高度な狩猟 [を使用して脅威を事前に検出する」を参照してください](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="31faf-164">For more information about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="attack-surface-reduction-features-across-windows-versions"></a><span data-ttu-id="31faf-165">複数のバージョンの攻撃表面Windows機能</span><span class="sxs-lookup"><span data-stu-id="31faf-165">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="31faf-166">次のエディションとバージョンのデバイスを実行しているデバイスに対して攻撃表面の縮小ルールをWindows。</span><span class="sxs-lookup"><span data-stu-id="31faf-166">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="31faf-167">Windows 10 Proバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="31faf-167">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="31faf-168">Windows 10 Enterpriseバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="31faf-168">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="31faf-169">Windowsサーバー、[バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803)以降</span><span class="sxs-lookup"><span data-stu-id="31faf-169">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="31faf-170">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31faf-170">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="31faf-171">攻撃表面の縮小ルールでは[E5](/windows/deployment/deploy-enterprise-licenses)ライセンスをWindows必要とWindows、高度な管理機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="31faf-171">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="31faf-172">Windows E5 でのみ使用可能なこれらの機能には[、Defender for Endpoint](microsoft-defender-endpoint.md)で使用可能な監視、分析、およびワークフロー、および Microsoft 365 Defender のレポート[機能と構成機能が含まれます](/microsoft-365/security/defender/overview-security-center)。</span><span class="sxs-lookup"><span data-stu-id="31faf-172">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in [Defender for Endpoint](microsoft-defender-endpoint.md), as well as reporting and configuration capabilities in [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).</span></span> <span data-ttu-id="31faf-173">これらの高度な機能は、E3 ライセンスWindows ProfessionalまたはWindows使用できません。ただし、これらのライセンスを持っている場合は、イベント ビューアーとログMicrosoft Defender ウイルス対策を使用して、攻撃表面の縮小ルール イベントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="31faf-173">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="31faf-174">Defender ポータルで攻撃表面の縮小イベントMicrosoft 365確認する</span><span class="sxs-lookup"><span data-stu-id="31faf-174">Review attack surface reduction events in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="31faf-175">Defender for Endpoint は、アラート調査シナリオの一環として、イベントとブロックの詳細なレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="31faf-175">Defender for Endpoint provides detailed reporting for events and blocks as part of alert investigation scenarios.</span></span>

<span data-ttu-id="31faf-176">高度な検索を使用して、Defender for Endpoint[データMicrosoft 365 Defender](microsoft-defender-security-center.md)で[クエリを実行できます](advanced-hunting-query-language.md)。</span><span class="sxs-lookup"><span data-stu-id="31faf-176">You can query Defender for Endpoint data in [Microsoft 365 Defender](microsoft-defender-security-center.md) by using [advanced hunting](advanced-hunting-query-language.md).</span></span> <span data-ttu-id="31faf-177">監査モードを実行している [場合](audit-windows-defender.md)は、高度な検索を使用して、攻撃表面の縮小ルールが環境に与える影響を理解できます。</span><span class="sxs-lookup"><span data-stu-id="31faf-177">If you're running [audit mode](audit-windows-defender.md), you can use advanced hunting to understand how attack surface reduction rules could affect your environment.</span></span>

<span data-ttu-id="31faf-178">クエリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31faf-178">Here is an example query:</span></span>

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="31faf-179">イベント ビューアーで攻撃表面の縮小イベントWindows確認する</span><span class="sxs-lookup"><span data-stu-id="31faf-179">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="31faf-180">次のイベント ログをWindowsして、攻撃表面の縮小ルールによって生成されたイベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="31faf-180">You can review the Windows event log to view events generated by attack surface reduction rules:</span></span>

1. <span data-ttu-id="31faf-181">評価パッケージ [をダウンロードし](https://aka.ms/mp7z2w) 、デバイス上 *cfa-events.xmlアクセスしやすい* 場所にファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="31faf-181">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>

2. <span data-ttu-id="31faf-182">[スタート] メニューに「*イベント ビューアー*」という単語を入力し、イベント ビューアー Windows開きます。</span><span class="sxs-lookup"><span data-stu-id="31faf-182">Enter the words, *Event Viewer*, into the Start menu to open the Windows Event Viewer.</span></span>

3. <span data-ttu-id="31faf-183">[アクション **] で**、[カスタム **ビューのインポート.... を選択します**。</span><span class="sxs-lookup"><span data-stu-id="31faf-183">Under **Actions**, select **Import custom view...**.</span></span>

4. <span data-ttu-id="31faf-184">抽出された場所 *cfa-events.xml* ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="31faf-184">Select the file *cfa-events.xml* from where it was extracted.</span></span> <span data-ttu-id="31faf-185">または [、XML を直接コピーします](event-views.md)。</span><span class="sxs-lookup"><span data-stu-id="31faf-185">Alternatively, [copy the XML directly](event-views.md).</span></span>

5. <span data-ttu-id="31faf-186">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="31faf-186">Select **OK**.</span></span>

<span data-ttu-id="31faf-187">イベントをフィルター処理して、次のイベントのみを表示するカスタム ビューを作成できます。そのすべては、フォルダー アクセスの制御に関連しています。</span><span class="sxs-lookup"><span data-stu-id="31faf-187">You can create a custom view that filters events to only show the following events, all of which are related to controlled folder access:</span></span>

|<span data-ttu-id="31faf-188">イベント ID</span><span class="sxs-lookup"><span data-stu-id="31faf-188">Event ID</span></span>|<span data-ttu-id="31faf-189">説明</span><span class="sxs-lookup"><span data-stu-id="31faf-189">Description</span></span>|
|---|---|
|<span data-ttu-id="31faf-190">5007</span><span class="sxs-lookup"><span data-stu-id="31faf-190">5007</span></span>|<span data-ttu-id="31faf-191">設定が変更された場合のイベント</span><span class="sxs-lookup"><span data-stu-id="31faf-191">Event when settings are changed</span></span>|
|<span data-ttu-id="31faf-192">1121</span><span class="sxs-lookup"><span data-stu-id="31faf-192">1121</span></span>|<span data-ttu-id="31faf-193">ブロック モードでルールが発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="31faf-193">Event when rule fires in Block-mode</span></span>|
|<span data-ttu-id="31faf-194">1122</span><span class="sxs-lookup"><span data-stu-id="31faf-194">1122</span></span>|<span data-ttu-id="31faf-195">監査モードでルールが発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="31faf-195">Event when rule fires in Audit-mode</span></span>|

<span data-ttu-id="31faf-196">イベント ログの攻撃表面の縮小イベント用にリストされている "エンジンバージョン" は、オペレーティング システムではなく Defender for Endpoint によって生成されます。</span><span class="sxs-lookup"><span data-stu-id="31faf-196">The "engine version" listed for attack surface reduction events in the event log, is generated by Defender for Endpoint, not by the operating system.</span></span> <span data-ttu-id="31faf-197">Defender for Endpoint は、Windows 10と統合されています。そのため、この機能は、インストールされているすべてのデバイスWindows 10します。</span><span class="sxs-lookup"><span data-stu-id="31faf-197">Defender for Endpoint is integrated with Windows 10, so this feature works on all devices with Windows 10 installed.</span></span>

## <a name="attack-surface-reduction-rules"></a><span data-ttu-id="31faf-198">攻撃面の減少ルール</span><span class="sxs-lookup"><span data-stu-id="31faf-198">Attack surface reduction rules</span></span>

<span data-ttu-id="31faf-199">次の表とサブセクションでは、15 の攻撃表面の縮小ルールのそれぞれについて説明します。</span><span class="sxs-lookup"><span data-stu-id="31faf-199">The following table and subsections describe each of the 15 attack surface reduction rules.</span></span> <span data-ttu-id="31faf-200">攻撃表面の縮小ルールは、ルール名によってアルファベット順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="31faf-200">The attack surface reduction rules are listed in alphabetical order, by rule name.</span></span>

<span data-ttu-id="31faf-201">グループ ポリシーまたは PowerShell を使用して攻撃表面の縮小ルールを構成する場合は、GUID が必要です。</span><span class="sxs-lookup"><span data-stu-id="31faf-201">If you are configuring attack surface reduction rules by using Group Policy or PowerShell, you'll need the GUIDs.</span></span> <span data-ttu-id="31faf-202">一方、ユーザー設定またはMicrosoft エンドポイント マネージャーをMicrosoft Intune GUID は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="31faf-202">On the other hand, if you use Microsoft Endpoint Manager or Microsoft Intune, you do not need the GUIDs.</span></span>

|<span data-ttu-id="31faf-203">ルールの名前</span><span class="sxs-lookup"><span data-stu-id="31faf-203">Rule name</span></span>|<span data-ttu-id="31faf-204">GUID</span><span class="sxs-lookup"><span data-stu-id="31faf-204">GUID</span></span>|<span data-ttu-id="31faf-205">ファイル&フォルダーの除外</span><span class="sxs-lookup"><span data-stu-id="31faf-205">File & folder exclusions</span></span>|<span data-ttu-id="31faf-206">サポートされる最小 OS</span><span class="sxs-lookup"><span data-stu-id="31faf-206">Minimum OS supported</span></span>|
|---|:---:|---|---|
|[<span data-ttu-id="31faf-207">悪用された脆弱な署名済みドライバーの悪用をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-207">Block abuse of exploited vulnerable signed drivers</span></span>](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|<span data-ttu-id="31faf-208">サポート</span><span class="sxs-lookup"><span data-stu-id="31faf-208">Supported</span></span>|<span data-ttu-id="31faf-209">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上)</span><span class="sxs-lookup"><span data-stu-id="31faf-209">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater)</span></span> |
|[<span data-ttu-id="31faf-210">Adobe Reader の子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-210">Block Adobe Reader from creating child processes</span></span>](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|<span data-ttu-id="31faf-211">サポート</span><span class="sxs-lookup"><span data-stu-id="31faf-211">Supported</span></span>|<span data-ttu-id="31faf-212">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="31faf-212">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="31faf-213">すべてのアプリケーションOffice子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-213">Block all Office applications from creating child processes</span></span>](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|<span data-ttu-id="31faf-214">サポート</span><span class="sxs-lookup"><span data-stu-id="31faf-214">Supported</span></span>|<span data-ttu-id="31faf-215">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="31faf-215">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="31faf-216">ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="31faf-216">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|<span data-ttu-id="31faf-217">サポート</span><span class="sxs-lookup"><span data-stu-id="31faf-217">Supported</span></span>|<span data-ttu-id="31faf-218">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="31faf-218">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="31faf-219">メール クライアントと Web メールから実行可能なコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-219">Block executable content from email client and webmail</span></span>](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|<span data-ttu-id="31faf-220">サポート</span><span class="sxs-lookup"><span data-stu-id="31faf-220">Supported</span></span>|<span data-ttu-id="31faf-221">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="31faf-221">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="31faf-222">有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-222">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|<span data-ttu-id="31faf-223">サポート</span><span class="sxs-lookup"><span data-stu-id="31faf-223">Supported</span></span>|<span data-ttu-id="31faf-224">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="31faf-224">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="31faf-225">難読化される可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-225">Block execution of potentially obfuscated scripts</span></span>](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|<span data-ttu-id="31faf-226">サポート</span><span class="sxs-lookup"><span data-stu-id="31faf-226">Supported</span></span>|<span data-ttu-id="31faf-227">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="31faf-227">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="31faf-228">JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-228">Block JavaScript or VBScript from launching downloaded executable content</span></span>](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|<span data-ttu-id="31faf-229">サポート</span><span class="sxs-lookup"><span data-stu-id="31faf-229">Supported</span></span>|<span data-ttu-id="31faf-230">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="31faf-230">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="31faf-231">実行可能Office作成するアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="31faf-231">Block Office applications from creating executable content</span></span>](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|<span data-ttu-id="31faf-232">サポート</span><span class="sxs-lookup"><span data-stu-id="31faf-232">Supported</span></span>|<span data-ttu-id="31faf-233">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="31faf-233">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="31faf-234">アプリケーションOffice他のプロセスへのコードの挿入をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-234">Block Office applications from injecting code into other processes</span></span>](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|<span data-ttu-id="31faf-235">サポート</span><span class="sxs-lookup"><span data-stu-id="31faf-235">Supported</span></span>|<span data-ttu-id="31faf-236">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="31faf-236">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="31faf-237">通信Officeプロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-237">Block Office communication application from creating child processes</span></span>](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|<span data-ttu-id="31faf-238">サポート</span><span class="sxs-lookup"><span data-stu-id="31faf-238">Supported</span></span>|<span data-ttu-id="31faf-239">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="31faf-239">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="31faf-240">WMI イベント サブスクリプションによる永続化のブロック</span><span class="sxs-lookup"><span data-stu-id="31faf-240">Block persistence through WMI event subscription</span></span>](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|<span data-ttu-id="31faf-241">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="31faf-241">Not supported</span></span>|<span data-ttu-id="31faf-242">[Windows 10バージョン 1903](/windows/whats-new/whats-new-windows-10-version-1903) (ビルド 18362) 以上</span><span class="sxs-lookup"><span data-stu-id="31faf-242">[Windows 10, version 1903](/windows/whats-new/whats-new-windows-10-version-1903) (build 18362) or greater</span></span>|
|[<span data-ttu-id="31faf-243">PSExec および WMI コマンドから発生するプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-243">Block process creations originating from PSExec and WMI commands</span></span>](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|<span data-ttu-id="31faf-244">サポート</span><span class="sxs-lookup"><span data-stu-id="31faf-244">Supported</span></span>|<span data-ttu-id="31faf-245">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="31faf-245">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="31faf-246">USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-246">Block untrusted and unsigned processes that run from USB</span></span>](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|<span data-ttu-id="31faf-247">サポート</span><span class="sxs-lookup"><span data-stu-id="31faf-247">Supported</span></span>|<span data-ttu-id="31faf-248">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="31faf-248">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="31faf-249">Win32 API 呼び出しをブロックOfficeマクロ</span><span class="sxs-lookup"><span data-stu-id="31faf-249">Block Win32 API calls from Office macros</span></span>](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|<span data-ttu-id="31faf-250">サポート</span><span class="sxs-lookup"><span data-stu-id="31faf-250">Supported</span></span>|<span data-ttu-id="31faf-251">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="31faf-251">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="31faf-252">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="31faf-252">Use advanced protection against ransomware</span></span>](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|<span data-ttu-id="31faf-253">サポート</span><span class="sxs-lookup"><span data-stu-id="31faf-253">Supported</span></span>|<span data-ttu-id="31faf-254">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="31faf-254">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a><span data-ttu-id="31faf-255">悪用された脆弱な署名済みドライバーの悪用をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-255">Block abuse of exploited vulnerable signed drivers</span></span>

<span data-ttu-id="31faf-256">このルールは、アプリケーションが脆弱で署名されたドライバーをディスクに書き込むのを防ぐためです。</span><span class="sxs-lookup"><span data-stu-id="31faf-256">This rule prevents an application from writing a vulnerable, signed driver to disk.</span></span> <span data-ttu-id="31faf-257">インザワイルドで脆弱な署名済みドライバーは、カーネルにアクセスするのに十分な特権を持つローカル アプリケーション \-  \- によって悪用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-257">In-the-wild, vulnerable signed drivers can be exploited by local applications \- _that have sufficient privileges_ \- to gain access to the kernel.</span></span> <span data-ttu-id="31faf-258">脆弱な署名付きドライバーを使用すると、攻撃者はセキュリティ ソリューションを無効または回避し、最終的にはシステムの侵害につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-258">Vulnerable signed drivers enable attackers to disable or circumvent security solutions, eventually leading to system compromise.</span></span>

<span data-ttu-id="31faf-259">このルールは、システム上に既に存在するドライバーが読み込まれるのをブロックしない。</span><span class="sxs-lookup"><span data-stu-id="31faf-259">This rule does not block a driver already existing on the system from being loaded.</span></span>

>[!NOTE]
>
> <span data-ttu-id="31faf-260">このルールは [、MEM OMA-URI](enable-attack-surface-reduction.md#mem) カスタム ルールのプロシージャ情報に対して MEM OMA-URI を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="31faf-260">This rule can be configured using [MEM OMA-URI](enable-attack-surface-reduction.md#mem) for MEM OMA-URI custom rules procedural information.</span></span>
>
> <span data-ttu-id="31faf-261">このルールは [、PowerShell](enable-attack-surface-reduction.md#powershell)を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="31faf-261">This rule can also be configured using [PowerShell](enable-attack-surface-reduction.md#powershell).</span></span>
>
> <span data-ttu-id="31faf-262">この Web サイトを使用して、 [分析用にドライバーを送信できます](https://www.microsoft.com/en-us/wdsi/driversubmission)。</span><span class="sxs-lookup"><span data-stu-id="31faf-262">You can use this Web site to [Submit a driver for analysis](https://www.microsoft.com/en-us/wdsi/driversubmission).</span></span>

<span data-ttu-id="31faf-263">このルールは、ASR がサポートされているすべてのバージョンでサポートされます。これは次の場合です。</span><span class="sxs-lookup"><span data-stu-id="31faf-263">This rule is supported in all versions in which ASR is supported; which is:</span></span>

- <span data-ttu-id="31faf-264">[Windows 10 Proバージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="31faf-264">[Windows 10 Pro, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="31faf-265">[Windows 10 Enterpriseバージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="31faf-265">[Windows 10 Enterprise, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="31faf-266">[Windows Server バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803)以降</span><span class="sxs-lookup"><span data-stu-id="31faf-266">[Windows Server, version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="31faf-267">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31faf-267">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="31faf-268">Intune 名: `Block abuse of exploited vulnerable signed drivers`</span><span class="sxs-lookup"><span data-stu-id="31faf-268">Intune Name: `Block abuse of exploited vulnerable signed drivers`</span></span>

<span data-ttu-id="31faf-269">GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span><span class="sxs-lookup"><span data-stu-id="31faf-269">GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span></span>

### <a name="block-adobe-reader-from-creating-child-processes"></a><span data-ttu-id="31faf-270">Adobe Reader の子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-270">Block Adobe Reader from creating child processes</span></span>

<span data-ttu-id="31faf-271">このルールは、Adobe Reader によるプロセスの作成をブロックすることで攻撃を防止します。</span><span class="sxs-lookup"><span data-stu-id="31faf-271">This rule prevents attacks by blocking Adobe Reader from creating processes.</span></span>

<span data-ttu-id="31faf-272">ソーシャル エンジニアリングや悪用を通じて、マルウェアはペイロードをダウンロードして起動し、Adobe Reader から抜け出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-272">Through social engineering or exploits, malware can download and launch payloads, and break out of Adobe Reader.</span></span> <span data-ttu-id="31faf-273">Adobe Reader によって子プロセスが生成されるのをブロックすることで、子プロセスをベクターとして使用しようとするマルウェアが拡散を防止します。</span><span class="sxs-lookup"><span data-stu-id="31faf-273">By blocking child processes from being generated by Adobe Reader, malware attempting to use it as a vector are prevented from spreading.</span></span>

<span data-ttu-id="31faf-274">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31faf-274">This rule was introduced in:</span></span>

- [<span data-ttu-id="31faf-275">Windows 10バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="31faf-275">Windows 10, version 1809</span></span>](/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="31faf-276">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="31faf-276">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="31faf-277">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31faf-277">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="31faf-278">Intune 名: `Process creation from Adobe Reader (beta)`</span><span class="sxs-lookup"><span data-stu-id="31faf-278">Intune name: `Process creation from Adobe Reader (beta)`</span></span>

<span data-ttu-id="31faf-279">Configuration Manager 名: まだ使用できません</span><span class="sxs-lookup"><span data-stu-id="31faf-279">Configuration Manager name: Not yet available</span></span>

<span data-ttu-id="31faf-280">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span><span class="sxs-lookup"><span data-stu-id="31faf-280">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span></span>

### <a name="block-all-office-applications-from-creating-child-processes"></a><span data-ttu-id="31faf-281">すべてのアプリケーションOffice子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-281">Block all Office applications from creating child processes</span></span>

<span data-ttu-id="31faf-282">このルールは、Officeプロセスの作成をブロックします。</span><span class="sxs-lookup"><span data-stu-id="31faf-282">This rule blocks Office apps from creating child processes.</span></span> <span data-ttu-id="31faf-283">Officeには、Word、Excel、PowerPoint、OneNote、Access が含まれます。</span><span class="sxs-lookup"><span data-stu-id="31faf-283">Office apps include Word, Excel, PowerPoint, OneNote, and Access.</span></span>

<span data-ttu-id="31faf-284">悪意のある子プロセスを作成する方法は、一般的なマルウェア戦略です。</span><span class="sxs-lookup"><span data-stu-id="31faf-284">Creating malicious child processes is a common malware strategy.</span></span> <span data-ttu-id="31faf-285">マルウェアがベクターとしてOffice、VBA マクロを実行し、コードを悪用して、より多くのペイロードをダウンロードして実行しようとする場合があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-285">Malware that abuse Office as a vector often run VBA macros and exploit code to download and attempt to run more payloads.</span></span> <span data-ttu-id="31faf-286">ただし、一部の正当な業務行アプリケーションでは、コマンド プロンプトの生成や PowerShell を使用してレジストリ設定を構成するなどの、適切な目的で子プロセスを生成する場合があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-286">However, some legitimate line-of-business applications might also generate child processes for benign purposes, such as spawning a command prompt or using PowerShell to configure registry settings.</span></span>

<span data-ttu-id="31faf-287">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31faf-287">This rule was introduced in:</span></span>

- [<span data-ttu-id="31faf-288">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="31faf-288">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="31faf-289">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="31faf-289">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="31faf-290">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31faf-290">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="31faf-291">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="31faf-291">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="31faf-292">Intune 名: `Office apps launching child processes`</span><span class="sxs-lookup"><span data-stu-id="31faf-292">Intune name: `Office apps launching child processes`</span></span>

<span data-ttu-id="31faf-293">Configuration Manager 名: `Block Office application from creating child processes`</span><span class="sxs-lookup"><span data-stu-id="31faf-293">Configuration Manager name: `Block Office application from creating child processes`</span></span>

<span data-ttu-id="31faf-294">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span><span class="sxs-lookup"><span data-stu-id="31faf-294">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span></span>

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a><span data-ttu-id="31faf-295">ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-295">Block credential stealing from the Windows local security authority subsystem</span></span>

<span data-ttu-id="31faf-296">このルールは、ローカル セキュリティ機関サブシステム サービス (LSASS) をロックダウンすることで、資格情報の盗用を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="31faf-296">This rule helps prevent credential stealing, by locking down Local Security Authority Subsystem Service (LSASS).</span></span>

<span data-ttu-id="31faf-297">LSASS は、コンピューターにサインインするユーザーをWindowsします。</span><span class="sxs-lookup"><span data-stu-id="31faf-297">LSASS authenticates users who sign in on a Windows computer.</span></span> <span data-ttu-id="31faf-298">Microsoft Defender Credential Guard in Windows 10は、通常、LSASS から資格情報を抽出しようとして防止します。</span><span class="sxs-lookup"><span data-stu-id="31faf-298">Microsoft Defender Credential Guard in Windows 10 normally prevents attempts to extract credentials from LSASS.</span></span> <span data-ttu-id="31faf-299">ただし、一部の組織では、カスタム スマートカード ドライバーやローカル セキュリティ機関 (LSA) に読み込む他のプログラムとの互換性の問題により、すべてのコンピューターで Credential Guard を有効にできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-299">However, some organizations can't enable Credential Guard on all of their computers because of compatibility issues with custom smartcard drivers or other programs that load into the Local Security Authority (LSA).</span></span> <span data-ttu-id="31faf-300">このような場合、攻撃者は Mimikatz のようなハッキング ツールを使用して、LSASS からクリアテキスト パスワードと NTLM ハッシュをスクレイピングできます。</span><span class="sxs-lookup"><span data-stu-id="31faf-300">In these cases, attackers can use hack tools like Mimikatz to scrape cleartext passwords and NTLM hashes from LSASS.</span></span>

> [!NOTE]
> <span data-ttu-id="31faf-301">一部のアプリでは、実行中のすべてのプロセスを列挙し、網羅的なアクセス許可を使用して開きます。</span><span class="sxs-lookup"><span data-stu-id="31faf-301">In some apps, the code enumerates all running processes and attempts to open them with exhaustive permissions.</span></span> <span data-ttu-id="31faf-302">このルールは、アプリのプロセスのオープン アクションを拒否し、詳細をセキュリティ イベント ログに記録します。</span><span class="sxs-lookup"><span data-stu-id="31faf-302">This rule denies the app's process open action and logs the details to the security event log.</span></span> <span data-ttu-id="31faf-303">このルールでは、多くのノイズが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-303">This rule can generate a lot of noise.</span></span> <span data-ttu-id="31faf-304">LSASS を列挙するだけで、機能に実際の影響がないアプリがある場合は、除外リストに追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="31faf-304">If you have an app that simply enumerates LSASS, but has no real impact in functionality, there is NO need to add it to the exclusion list.</span></span> <span data-ttu-id="31faf-305">それ自体では、このイベント ログ エントリは必ずしも悪意のある脅威を示すとは限りません。</span><span class="sxs-lookup"><span data-stu-id="31faf-305">By itself, this event log entry doesn't necessarily indicate a malicious threat.</span></span>

<span data-ttu-id="31faf-306">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31faf-306">This rule was introduced in:</span></span>

- [<span data-ttu-id="31faf-307">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="31faf-307">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="31faf-308">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="31faf-308">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="31faf-309">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31faf-309">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="31faf-310">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="31faf-310">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="31faf-311">Intune 名: `Flag credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="31faf-311">Intune name: `Flag credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="31faf-312">Configuration Manager 名: `Block credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="31faf-312">Configuration Manager name: `Block credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="31faf-313">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span><span class="sxs-lookup"><span data-stu-id="31faf-313">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span></span>

### <a name="block-executable-content-from-email-client-and-webmail"></a><span data-ttu-id="31faf-314">メール クライアントと Web メールから実行可能なコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-314">Block executable content from email client and webmail</span></span>

<span data-ttu-id="31faf-315">このルールは、Microsoft Outlook アプリケーション、または Outlook.com や他の一般的な Web メール プロバイダー内で開いた電子メールから、次の種類のファイルの起動をブロックします。</span><span class="sxs-lookup"><span data-stu-id="31faf-315">This rule blocks the following file types from launching from email opened within the Microsoft Outlook application, or Outlook.com and other popular webmail providers:</span></span>

- <span data-ttu-id="31faf-316">実行可能ファイル (.exe、.dll.scr など)</span><span class="sxs-lookup"><span data-stu-id="31faf-316">Executable files (such as .exe, .dll, or .scr)</span></span>
- <span data-ttu-id="31faf-317">スクリプト ファイル (PowerShell .ps、Visual Basic .vbs、JavaScript .js ファイルなど)</span><span class="sxs-lookup"><span data-stu-id="31faf-317">Script files (such as a PowerShell .ps, Visual Basic .vbs, or JavaScript .js file)</span></span>

<span data-ttu-id="31faf-318">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31faf-318">This rule was introduced in:</span></span>

- [<span data-ttu-id="31faf-319">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="31faf-319">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="31faf-320">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="31faf-320">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="31faf-321">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31faf-321">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="31faf-322">Microsoft エンドポイント マネージャーCB 1710</span><span class="sxs-lookup"><span data-stu-id="31faf-322">Microsoft Endpoint Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="31faf-323">Intune 名: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="31faf-323">Intune name: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span></span>

<span data-ttu-id="31faf-324">Microsoft エンドポイント マネージャー名:`Block executable content from email client and webmail`</span><span class="sxs-lookup"><span data-stu-id="31faf-324">Microsoft Endpoint Manager name: `Block executable content from email client and webmail`</span></span>

<span data-ttu-id="31faf-325">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span><span class="sxs-lookup"><span data-stu-id="31faf-325">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span></span>

> [!NOTE]
> <span data-ttu-id="31faf-326">[メール **クライアントと Web メールからの** 実行可能なコンテンツをブロックする] というルールには、使用するアプリケーションに応じて、次の別の説明があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-326">The rule **Block executable content from email client and webmail** has the following alternative descriptions, depending on which application you use:</span></span>
>
> - <span data-ttu-id="31faf-327">Intune (構成プロファイル): 電子メール (Web メール/メール クライアント) から削除された実行可能コンテンツ (exe、dll、ps、js、vbs など) の実行 (例外なし)。</span><span class="sxs-lookup"><span data-stu-id="31faf-327">Intune (Configuration Profiles): Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions).</span></span>
> - <span data-ttu-id="31faf-328">エンドポイント マネージャー: メールおよび Web メール クライアントからの実行可能コンテンツのダウンロードをブロックします。</span><span class="sxs-lookup"><span data-stu-id="31faf-328">Endpoint Manager: Block executable content download from email and webmail clients.</span></span>
> - <span data-ttu-id="31faf-329">グループ ポリシー: 電子メール クライアントと Web メールから実行可能なコンテンツをブロックします。</span><span class="sxs-lookup"><span data-stu-id="31faf-329">Group Policy: Block executable content from email client and webmail.</span></span>

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a><span data-ttu-id="31faf-330">有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-330">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>

<span data-ttu-id="31faf-331">このルールは、有病率や年齢の条件を満たしたり、信頼できるリストまたは除外リストに含めない限り、次の種類のファイルの起動をブロックします。</span><span class="sxs-lookup"><span data-stu-id="31faf-331">This rule blocks the following file types from launching unless they meet prevalence or age criteria, or they're in a trusted list or an exclusion list:</span></span>

- <span data-ttu-id="31faf-332">実行可能ファイル (.exe、.dll.scr など)</span><span class="sxs-lookup"><span data-stu-id="31faf-332">Executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="31faf-333">信頼されていない実行可能ファイルまたは不明な実行可能ファイルを起動すると、ファイルが悪意のある場合、最初は明確にできない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-333">Launching untrusted or unknown executable files can be risky, as it may not be initially clear if the files are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31faf-334">このルールを [使用するには、クラウドによる保護](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-334">You must [enable cloud-delivered protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to use this rule.</span></span>
>
> <span data-ttu-id="31faf-335">GUID で **有病率** 、年齢、または信頼できるリスト条件を満たしていない場合、実行可能ファイルの実行をブロックするルールは、Microsoft が所有し、管理者によって `01443614-cd74-433a-b99e-2ecdc07bfc25` 指定されていません。</span><span class="sxs-lookup"><span data-stu-id="31faf-335">The rule **Block executable files from running unless they meet a prevalence, age, or trusted list criterion** with GUID `01443614-cd74-433a-b99e-2ecdc07bfc25` is owned by Microsoft and is not specified by admins.</span></span> <span data-ttu-id="31faf-336">このルールでは、クラウド配信の保護を使用して、信頼できるリストを定期的に更新します。</span><span class="sxs-lookup"><span data-stu-id="31faf-336">This rule uses cloud-delivered protection to update its trusted list regularly.</span></span>
>
> <span data-ttu-id="31faf-337">個々のファイルまたはフォルダー (フォルダー パスまたは完全修飾リソース名を使用) を指定できますが、適用するルールや除外を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="31faf-337">You can specify individual files or folders (using folder paths or fully qualified resource names) but you can't specify which rules or exclusions apply to.</span></span>

<span data-ttu-id="31faf-338">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31faf-338">This rule was introduced in:</span></span>

- [<span data-ttu-id="31faf-339">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="31faf-339">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="31faf-340">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="31faf-340">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="31faf-341">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31faf-341">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="31faf-342">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="31faf-342">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="31faf-343">Intune 名: `Executables that don't meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="31faf-343">Intune name: `Executables that don't meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="31faf-344">Configuration Manager 名: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="31faf-344">Configuration Manager name: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="31faf-345">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span><span class="sxs-lookup"><span data-stu-id="31faf-345">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span></span>

### <a name="block-execution-of-potentially-obfuscated-scripts"></a><span data-ttu-id="31faf-346">難読化される可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-346">Block execution of potentially obfuscated scripts</span></span>

<span data-ttu-id="31faf-347">このルールは、難読化されたスクリプト内の疑わしいプロパティを検出します。</span><span class="sxs-lookup"><span data-stu-id="31faf-347">This rule detects suspicious properties within an obfuscated script.</span></span>

<span data-ttu-id="31faf-348">スクリプト難読化は、マルウェア作成者と正当なアプリケーションの両方が、知的財産を隠したり、スクリプトの読み込み時間を短縮したりするために使用する一般的な手法です。</span><span class="sxs-lookup"><span data-stu-id="31faf-348">Script obfuscation is a common technique that both malware authors and legitimate applications use to hide intellectual property or decrease script loading times.</span></span> <span data-ttu-id="31faf-349">マルウェアの作成者は難読化を使用して悪意のあるコードを読みにくくし、人間やセキュリティ ソフトウェアによる詳細な調査を防止します。</span><span class="sxs-lookup"><span data-stu-id="31faf-349">Malware authors also use obfuscation to make malicious code harder to read, which prevents close scrutiny by humans and security software.</span></span>

<span data-ttu-id="31faf-350">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31faf-350">This rule was introduced in:</span></span>

- [<span data-ttu-id="31faf-351">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="31faf-351">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="31faf-352">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="31faf-352">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="31faf-353">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31faf-353">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="31faf-354">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="31faf-354">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="31faf-355">Intune 名: `Obfuscated js/vbs/ps/macro code`</span><span class="sxs-lookup"><span data-stu-id="31faf-355">Intune name: `Obfuscated js/vbs/ps/macro code`</span></span>

<span data-ttu-id="31faf-356">Configuration Manager 名: `Block execution of potentially obfuscated scripts`</span><span class="sxs-lookup"><span data-stu-id="31faf-356">Configuration Manager name: `Block execution of potentially obfuscated scripts`</span></span>

<span data-ttu-id="31faf-357">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span><span class="sxs-lookup"><span data-stu-id="31faf-357">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span></span>

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a><span data-ttu-id="31faf-358">JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-358">Block JavaScript or VBScript from launching downloaded executable content</span></span>

<span data-ttu-id="31faf-359">このルールにより、スクリプトは悪意のあるダウンロードコンテンツを起動できません。</span><span class="sxs-lookup"><span data-stu-id="31faf-359">This rule prevents scripts from launching potentially malicious downloaded content.</span></span> <span data-ttu-id="31faf-360">JavaScript または VBScript で記述されたマルウェアは、インターネットから他のマルウェアをフェッチして起動するダウンデータとして機能する場合が多い。</span><span class="sxs-lookup"><span data-stu-id="31faf-360">Malware written in JavaScript or VBScript often acts as a downloader to fetch and launch other malware from the Internet.</span></span>

<span data-ttu-id="31faf-361">一般的ではないが、一般企業向けアプリケーションでは、スクリプトを使用してインストーラーをダウンロードおよび起動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-361">Although not common, line-of-business applications sometimes use scripts to download and launch installers.</span></span>

<span data-ttu-id="31faf-362">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31faf-362">This rule was introduced in:</span></span>

- [<span data-ttu-id="31faf-363">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="31faf-363">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="31faf-364">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="31faf-364">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="31faf-365">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31faf-365">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="31faf-366">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="31faf-366">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="31faf-367">Intune 名: `js/vbs executing payload downloaded from Internet (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="31faf-367">Intune name: `js/vbs executing payload downloaded from Internet (no exceptions)`</span></span>

<span data-ttu-id="31faf-368">Configuration Manager 名: `Block JavaScript or VBScript from launching downloaded executable content`</span><span class="sxs-lookup"><span data-stu-id="31faf-368">Configuration Manager name: `Block JavaScript or VBScript from launching downloaded executable content`</span></span>

<span data-ttu-id="31faf-369">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span><span class="sxs-lookup"><span data-stu-id="31faf-369">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span></span>

### <a name="block-office-applications-from-creating-executable-content"></a><span data-ttu-id="31faf-370">実行可能Office作成するアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="31faf-370">Block Office applications from creating executable content</span></span>

<span data-ttu-id="31faf-371">このルール Officeは、悪意のあるコードがディスクに書き込まれるのをブロックすることで、Word、Excel、PowerPoint などのアプリが悪意のある実行可能コンテンツを作成するのを防ぐためです。</span><span class="sxs-lookup"><span data-stu-id="31faf-371">This rule prevents Office apps, including Word, Excel, and PowerPoint, from creating potentially malicious executable content, by blocking malicious code from being written to disk.</span></span>

<span data-ttu-id="31faf-372">マルウェアは、Officeとして悪用され、悪意のあるOfficeをディスクに保存しようとする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-372">Malware that abuses Office as a vector may attempt to break out of Office and save malicious components to disk.</span></span> <span data-ttu-id="31faf-373">これらの悪意のあるコンポーネントは、コンピューターの再起動後も存続し、システム上で保持されます。</span><span class="sxs-lookup"><span data-stu-id="31faf-373">These malicious components would survive a computer reboot and persist on the system.</span></span> <span data-ttu-id="31faf-374">したがって、このルールは一般的な永続化手法に対して防御します。</span><span class="sxs-lookup"><span data-stu-id="31faf-374">Therefore, this rule defends against a common persistence technique.</span></span>

<span data-ttu-id="31faf-375">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31faf-375">This rule was introduced in:</span></span>

- [<span data-ttu-id="31faf-376">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="31faf-376">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="31faf-377">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="31faf-377">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="31faf-378">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31faf-378">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- <span data-ttu-id="31faf-379">[System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM がMicrosoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="31faf-379">[System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM is now Microsoft Endpoint Configuration Manager)</span></span>

<span data-ttu-id="31faf-380">Intune 名: `Office apps/macros creating executable content`</span><span class="sxs-lookup"><span data-stu-id="31faf-380">Intune name: `Office apps/macros creating executable content`</span></span>

<span data-ttu-id="31faf-381">SCCM 名: `Block Office applications from creating executable content`</span><span class="sxs-lookup"><span data-stu-id="31faf-381">SCCM name: `Block Office applications from creating executable content`</span></span>

<span data-ttu-id="31faf-382">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span><span class="sxs-lookup"><span data-stu-id="31faf-382">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span></span>

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a><span data-ttu-id="31faf-383">アプリケーションOffice他のプロセスへのコードの挿入をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-383">Block Office applications from injecting code into other processes</span></span>

<span data-ttu-id="31faf-384">このルールは、アプリから他のプロセスへのコードOffice試行をブロックします。</span><span class="sxs-lookup"><span data-stu-id="31faf-384">This rule blocks code injection attempts from Office apps into other processes.</span></span>

<span data-ttu-id="31faf-385">攻撃者は、Officeを使用して、コード挿入を通じて悪意のあるコードを他のプロセスに移行しようとする可能性があります。そのため、コードはクリーン なプロセスとして悪用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-385">Attackers might attempt to use Office apps to migrate malicious code into other processes through code injection, so the code can masquerade as a clean process.</span></span>

<span data-ttu-id="31faf-386">コードインジェクションを使用する正当なビジネス上の目的はありません。</span><span class="sxs-lookup"><span data-stu-id="31faf-386">There are no known legitimate business purposes for using code injection.</span></span>

<span data-ttu-id="31faf-387">このルールは、Word、Excel、およびPowerPoint。</span><span class="sxs-lookup"><span data-stu-id="31faf-387">This rule applies to Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="31faf-388">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31faf-388">This rule was introduced in:</span></span>

- [<span data-ttu-id="31faf-389">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="31faf-389">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="31faf-390">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="31faf-390">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="31faf-391">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31faf-391">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="31faf-392">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="31faf-392">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="31faf-393">Intune 名: `Office apps injecting code into other processes (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="31faf-393">Intune name: `Office apps injecting code into other processes (no exceptions)`</span></span>

<span data-ttu-id="31faf-394">Configuration Manager 名: `Block Office applications from injecting code into other processes`</span><span class="sxs-lookup"><span data-stu-id="31faf-394">Configuration Manager name: `Block Office applications from injecting code into other processes`</span></span>

<span data-ttu-id="31faf-395">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span><span class="sxs-lookup"><span data-stu-id="31faf-395">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span></span>

### <a name="block-office-communication-application-from-creating-child-processes"></a><span data-ttu-id="31faf-396">通信Officeプロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-396">Block Office communication application from creating child processes</span></span>

<span data-ttu-id="31faf-397">このルールは、Outlookプロセスを作成する一方で、正当なプロセス機能Outlookします。</span><span class="sxs-lookup"><span data-stu-id="31faf-397">This rule prevents Outlook from creating child processes, while still allowing legitimate Outlook functions.</span></span>

<span data-ttu-id="31faf-398">このルールは、ソーシャル エンジニアリング攻撃から保護し、コードを悪用して、セキュリティ上の脆弱性を悪用Outlook。</span><span class="sxs-lookup"><span data-stu-id="31faf-398">This rule protects against social engineering attacks and prevents exploiting code from abusing vulnerabilities in Outlook.</span></span> <span data-ttu-id="31faf-399">また、ユーザーのOutlook[が](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/)侵害された場合に攻撃者が使用する可能性のある、特定のルールやフォームの悪用から保護します。</span><span class="sxs-lookup"><span data-stu-id="31faf-399">It also protects against [Outlook rules and forms exploits](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) that attackers can use when a user's credentials are compromised.</span></span>

> [!NOTE]
> <span data-ttu-id="31faf-400">このルールは、DLP ポリシー のヒントとツール ヒントをブロックOutlook。</span><span class="sxs-lookup"><span data-stu-id="31faf-400">This rule blocks DLP policy tips and ToolTips in Outlook.</span></span> <span data-ttu-id="31faf-401">このルールは、Outlookおよび Outlook.com にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="31faf-401">This rule applies to Outlook and Outlook.com only.</span></span> 

<span data-ttu-id="31faf-402">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31faf-402">This rule was introduced in:</span></span>

- [<span data-ttu-id="31faf-403">Windows 10バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="31faf-403">Windows 10, version 1809</span></span>](/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="31faf-404">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="31faf-404">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="31faf-405">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31faf-405">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="31faf-406">Intune 名: `Process creation from Office communication products (beta)`</span><span class="sxs-lookup"><span data-stu-id="31faf-406">Intune name: `Process creation from Office communication products (beta)`</span></span>

<span data-ttu-id="31faf-407">Configuration Manager 名: 使用できません</span><span class="sxs-lookup"><span data-stu-id="31faf-407">Configuration Manager name: Not available</span></span>

<span data-ttu-id="31faf-408">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span><span class="sxs-lookup"><span data-stu-id="31faf-408">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span></span>

### <a name="block-persistence-through-wmi-event-subscription"></a><span data-ttu-id="31faf-409">WMI イベント サブスクリプションによる永続化のブロック</span><span class="sxs-lookup"><span data-stu-id="31faf-409">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="31faf-410">このルールは、デバイス上で WMI を攻撃して永続化を達成するマルウェアを防止します。</span><span class="sxs-lookup"><span data-stu-id="31faf-410">This rule prevents malware from abusing WMI to attain persistence on a device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31faf-411">ファイルとフォルダーの除外は、この攻撃表面の縮小ルールには適用されません。</span><span class="sxs-lookup"><span data-stu-id="31faf-411">File and folder exclusions don't apply to this attack surface reduction rule.</span></span>

<span data-ttu-id="31faf-412">ファイルレスの脅威は、隠し、ファイル システムで見られない、定期的な実行制御を得るために、さまざまな戦術を採用しています。</span><span class="sxs-lookup"><span data-stu-id="31faf-412">Fileless threats employ various tactics to stay hidden, to avoid being seen in the file system, and to gain periodic execution control.</span></span> <span data-ttu-id="31faf-413">一部の脅威は、WMI リポジトリとイベント モデルを悪用して非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="31faf-413">Some threats can abuse the WMI repository and event model to stay hidden.</span></span>

<span data-ttu-id="31faf-414">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31faf-414">This rule was introduced in:</span></span>

- [<span data-ttu-id="31faf-415">Windows 10バージョン 1903</span><span class="sxs-lookup"><span data-stu-id="31faf-415">Windows 10, version 1903</span></span>](/windows/whats-new/whats-new-windows-10-version-1903)
- [<span data-ttu-id="31faf-416">Windowsサーバー 1903</span><span class="sxs-lookup"><span data-stu-id="31faf-416">Windows Server 1903</span></span>](/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

<span data-ttu-id="31faf-417">Intune 名: 使用できません</span><span class="sxs-lookup"><span data-stu-id="31faf-417">Intune name: Not available</span></span>

<span data-ttu-id="31faf-418">Configuration Manager 名: 使用できません</span><span class="sxs-lookup"><span data-stu-id="31faf-418">Configuration Manager name: Not available</span></span>

<span data-ttu-id="31faf-419">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span><span class="sxs-lookup"><span data-stu-id="31faf-419">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span></span>

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a><span data-ttu-id="31faf-420">PSExec および WMI コマンドから発生するプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-420">Block process creations originating from PSExec and WMI commands</span></span>

<span data-ttu-id="31faf-421">このルールは [、PsExec](/sysinternals/downloads/psexec) および WMI を介して作成 [されたプロセスの実行](/windows/win32/wmisdk/about-wmi) をブロックします。</span><span class="sxs-lookup"><span data-stu-id="31faf-421">This rule blocks processes created through [PsExec](/sysinternals/downloads/psexec) and [WMI](/windows/win32/wmisdk/about-wmi) from running.</span></span> <span data-ttu-id="31faf-422">PsExec と WMI の両方がコードをリモートで実行できるので、コマンドと制御の目的でこの機能を不正に使用したり、組織のネットワーク全体に感染を広げる危険性があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-422">Both PsExec and WMI can remotely execute code, so there is a risk of malware abusing this functionality for command and control purposes, or to spread an infection throughout an organization's network.</span></span>

> [!WARNING]
> <span data-ttu-id="31faf-423">Intune または別の MDM ソリューションを使用してデバイスを管理する場合にのみ、 [このルールを](/intune) 使用します。</span><span class="sxs-lookup"><span data-stu-id="31faf-423">Only use this rule if you're managing your devices with [Intune](/intune) or another MDM solution.</span></span> <span data-ttu-id="31faf-424">このルールは、Configuration Manager クライアント[が正しく機能するために使用Microsoft Endpoint Configuration Manager](/configmgr) WMI コマンドをブロックします。</span><span class="sxs-lookup"><span data-stu-id="31faf-424">This rule is incompatible with management through [Microsoft Endpoint Configuration Manager](/configmgr) because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span>

<span data-ttu-id="31faf-425">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31faf-425">This rule was introduced in:</span></span>

- [<span data-ttu-id="31faf-426">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="31faf-426">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="31faf-427">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="31faf-427">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="31faf-428">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31faf-428">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="31faf-429">Intune 名: `Process creation from PSExec and WMI commands`</span><span class="sxs-lookup"><span data-stu-id="31faf-429">Intune name: `Process creation from PSExec and WMI commands`</span></span>

<span data-ttu-id="31faf-430">Configuration Manager 名: 該当なし</span><span class="sxs-lookup"><span data-stu-id="31faf-430">Configuration Manager name: Not applicable</span></span>

<span data-ttu-id="31faf-431">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span><span class="sxs-lookup"><span data-stu-id="31faf-431">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span></span>

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a><span data-ttu-id="31faf-432">USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="31faf-432">Block untrusted and unsigned processes that run from USB</span></span>

<span data-ttu-id="31faf-433">このルールを使用すると、管理者は、SD カードを含む USB リムーバブル ドライブから署名されていない実行可能ファイルまたは信頼されていない実行可能ファイルを実行できません。</span><span class="sxs-lookup"><span data-stu-id="31faf-433">With this rule, admins can prevent unsigned or untrusted executable files from running from USB removable drives, including SD cards.</span></span> <span data-ttu-id="31faf-434">ブロックされたファイルの種類には、実行可能ファイル (.exe、.dll.scr など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="31faf-434">Blocked file types include executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="31faf-435">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31faf-435">This rule was introduced in:</span></span>

- [<span data-ttu-id="31faf-436">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="31faf-436">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="31faf-437">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="31faf-437">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="31faf-438">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31faf-438">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="31faf-439">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="31faf-439">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="31faf-440">Intune 名: `Untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="31faf-440">Intune name: `Untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="31faf-441">Configuration Manager 名: `Block untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="31faf-441">Configuration Manager name: `Block untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="31faf-442">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span><span class="sxs-lookup"><span data-stu-id="31faf-442">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span></span>

### <a name="block-win32-api-calls-from-office-macros"></a><span data-ttu-id="31faf-443">Win32 API 呼び出しをブロックOfficeマクロ</span><span class="sxs-lookup"><span data-stu-id="31faf-443">Block Win32 API calls from Office macros</span></span>

<span data-ttu-id="31faf-444">このルールは、VBA マクロが Win32 API を呼び出すのを防止します。</span><span class="sxs-lookup"><span data-stu-id="31faf-444">This rule prevents VBA macros from calling Win32 APIs.</span></span>

<span data-ttu-id="31faf-445">OfficeVBA では、Win32 API 呼び出しが有効です。</span><span class="sxs-lookup"><span data-stu-id="31faf-445">Office VBA enables Win32 API calls.</span></span> <span data-ttu-id="31faf-446">マルウェアは [、Win32 API](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) を呼び出してディスクに直接何も書き込みせずに悪意のあるシェルコードを起動するなど、この機能を悪用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-446">Malware can abuse this capability, such as [calling Win32 APIs to launch malicious shellcode](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) without writing anything directly to disk.</span></span> <span data-ttu-id="31faf-447">ほとんどの組織では、他の方法でマクロを使用している場合でも、Win32 API を毎日の機能で呼び出す機能に依存しません。</span><span class="sxs-lookup"><span data-stu-id="31faf-447">Most organizations don't rely on the ability to call Win32 APIs in their day-to-day functioning, even if they use macros in other ways.</span></span>

<span data-ttu-id="31faf-448">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31faf-448">This rule was introduced in:</span></span>

- [<span data-ttu-id="31faf-449">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="31faf-449">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="31faf-450">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="31faf-450">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="31faf-451">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31faf-451">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="31faf-452">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="31faf-452">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="31faf-453">Intune 名: `Win32 imports from Office macro code`</span><span class="sxs-lookup"><span data-stu-id="31faf-453">Intune name: `Win32 imports from Office macro code`</span></span>

<span data-ttu-id="31faf-454">Configuration Manager 名: `Block Win32 API calls from Office macros`</span><span class="sxs-lookup"><span data-stu-id="31faf-454">Configuration Manager name: `Block Win32 API calls from Office macros`</span></span>

<span data-ttu-id="31faf-455">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span><span class="sxs-lookup"><span data-stu-id="31faf-455">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span></span>

### <a name="use-advanced-protection-against-ransomware"></a><span data-ttu-id="31faf-456">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="31faf-456">Use advanced protection against ransomware</span></span>

<span data-ttu-id="31faf-457">このルールは、ランサムウェアに対する保護の追加層を提供します。</span><span class="sxs-lookup"><span data-stu-id="31faf-457">This rule provides an extra layer of protection against ransomware.</span></span> <span data-ttu-id="31faf-458">クライアントとクラウドの両方のヒューリスティックを使用して、ファイルがランサムウェアに似ているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="31faf-458">It uses both client and cloud heuristics to determine whether a file resembles ransomware.</span></span> <span data-ttu-id="31faf-459">このルールは、次の 1 つ以上の特性を持つファイルをブロックしない。</span><span class="sxs-lookup"><span data-stu-id="31faf-459">This rule does not block files that have one or more of the following characteristics:</span></span>

- <span data-ttu-id="31faf-460">このファイルは、Microsoft クラウドで既に無傷である必要があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-460">The file has already been found to be unharmful in the Microsoft cloud.</span></span>
- <span data-ttu-id="31faf-461">ファイルは有効な署名付きファイルです。</span><span class="sxs-lookup"><span data-stu-id="31faf-461">The file is a valid signed file.</span></span>
- <span data-ttu-id="31faf-462">ファイルはランサムウェアと見なされないほど普及しています。</span><span class="sxs-lookup"><span data-stu-id="31faf-462">The file is prevalent enough to not be considered as ransomware.</span></span>

<span data-ttu-id="31faf-463">このルールは、ランサムウェアを防止するために注意を払う傾向があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-463">The rule tends to err on the side of caution to prevent ransomware.</span></span>

> [!NOTE]
> <span data-ttu-id="31faf-464">このルールを [使用するには、クラウドによる保護](enable-cloud-protection-microsoft-defender-antivirus.md) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="31faf-464">You must [enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) to use this rule.</span></span>

<span data-ttu-id="31faf-465">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31faf-465">This rule was introduced in:</span></span>

- [<span data-ttu-id="31faf-466">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="31faf-466">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="31faf-467">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="31faf-467">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="31faf-468">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31faf-468">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="31faf-469">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="31faf-469">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="31faf-470">Intune 名: `Advanced ransomware protection`</span><span class="sxs-lookup"><span data-stu-id="31faf-470">Intune name: `Advanced ransomware protection`</span></span>

<span data-ttu-id="31faf-471">Configuration Manager 名: `Use advanced protection against ransomware`</span><span class="sxs-lookup"><span data-stu-id="31faf-471">Configuration Manager name: `Use advanced protection against ransomware`</span></span>

<span data-ttu-id="31faf-472">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span><span class="sxs-lookup"><span data-stu-id="31faf-472">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span></span>


