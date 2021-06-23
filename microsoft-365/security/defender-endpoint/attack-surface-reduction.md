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
ms.openlocfilehash: 461911a1e14241112f4ff0e8efb0135b4e1a5a25
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096734"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a><span data-ttu-id="2d810-104">攻撃表面の縮小ルールを使用してマルウェアの感染を防止する</span><span class="sxs-lookup"><span data-stu-id="2d810-104">Use attack surface reduction rules to prevent malware infection</span></span>

<span data-ttu-id="2d810-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2d810-105">**Applies to:**</span></span>

- [<span data-ttu-id="2d810-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2d810-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="2d810-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d810-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a><span data-ttu-id="2d810-108">攻撃表面の縮小ルールが重要な理由</span><span class="sxs-lookup"><span data-stu-id="2d810-108">Why attack surface reduction rules are important</span></span>

<span data-ttu-id="2d810-109">組織の攻撃表面には、攻撃者が組織のデバイスやネットワークを侵害する可能性があるすべての場所が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d810-109">Your organization's attack surface includes all the places where an attacker could compromise your organization's devices or networks.</span></span> <span data-ttu-id="2d810-110">攻撃の表面を減らすことは、組織のデバイスとネットワークを保護する手段であり、攻撃者は攻撃を実行する方法が少なくなっています。</span><span class="sxs-lookup"><span data-stu-id="2d810-110">Reducing your attack surface means protecting your organization's devices and network, which leaves attackers with fewer ways to perform attacks.</span></span> <span data-ttu-id="2d810-111">Microsoft Defender for Endpoint で攻撃表面の縮小ルールを構成すると役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2d810-111">Configuring attack surface reduction rules in Microsoft Defender for Endpoint can help!</span></span>

<span data-ttu-id="2d810-112">攻撃表面の縮小ルールは、次のような特定のソフトウェア動作を対象とします。</span><span class="sxs-lookup"><span data-stu-id="2d810-112">Attack surface reduction rules target certain software behaviors, such as:</span></span>

- <span data-ttu-id="2d810-113">ファイルのダウンロードまたは実行を試みる実行可能ファイルとスクリプトの起動</span><span class="sxs-lookup"><span data-stu-id="2d810-113">Launching executable files and scripts that attempt to download or run files</span></span>
- <span data-ttu-id="2d810-114">難読化されたスクリプトまたはその他の疑わしいスクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="2d810-114">Running obfuscated or otherwise suspicious scripts</span></span>
- <span data-ttu-id="2d810-115">通常の毎日の作業中にアプリが通常開始しない動作を実行する</span><span class="sxs-lookup"><span data-stu-id="2d810-115">Performing behaviors that apps don't usually initiate during normal day-to-day work</span></span>

<span data-ttu-id="2d810-116">このようなソフトウェアの動作は、正当なアプリケーションで見られる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-116">Such software behaviors are sometimes seen in legitimate applications.</span></span> <span data-ttu-id="2d810-117">ただし、これらの動作は、マルウェアを介して攻撃者によって悪用されるのが一般的なので、リスクが高いと見なされる場合が多い。</span><span class="sxs-lookup"><span data-stu-id="2d810-117">However, these behaviors are often considered risky because they are commonly abused by attackers through malware.</span></span> <span data-ttu-id="2d810-118">攻撃表面の縮小ルールは、ソフトウェア ベースのリスクの高い動作を制限し、組織の安全を維持するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2d810-118">Attack surface reduction rules can constrain software-based risky behaviors and help keep your organization safe.</span></span>

<span data-ttu-id="2d810-119">攻撃表面の縮小ルールの構成の詳細については、「攻撃表面の縮小ルールを有効 [にする」を参照してください](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="2d810-119">For more information about configuring attack surface reduction rules, see [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

## <a name="assess-rule-impact-before-deployment"></a><span data-ttu-id="2d810-120">展開前にルールへの影響を評価する</span><span class="sxs-lookup"><span data-stu-id="2d810-120">Assess rule impact before deployment</span></span>

<span data-ttu-id="2d810-121">攻撃表面の縮小ルールがネットワークに与える影響を評価するには、このルールのセキュリティに関する推奨事項を [脅威と脆弱性の管理][で開きます](/windows/security/threat-protection/#tvm)。</span><span class="sxs-lookup"><span data-stu-id="2d810-121">You can assess how an attack surface reduction rule might affect your network by opening the security recommendation for that rule in [threat and vulnerability management](/windows/security/threat-protection/#tvm).</span></span>

:::image type="content" source="images/asrrecommendation.png" alt-text="攻撃表面の縮小ルールのセキュリティ reco":::

<span data-ttu-id="2d810-123">[推奨事項の詳細] ウィンドウで、ユーザーの影響を確認して、生産性に悪影響を及ぼさずに、ブロック モードでルールを有効にする新しいポリシーを受け入れ可能なデバイスの割合を確認します。</span><span class="sxs-lookup"><span data-stu-id="2d810-123">In the recommendation details pane, check for user impact to determine what percentage of your devices can accept a new policy enabling the rule in blocking mode without adversely affecting productivity.</span></span>

## <a name="audit-mode-for-evaluation"></a><span data-ttu-id="2d810-124">評価の監査モード</span><span class="sxs-lookup"><span data-stu-id="2d810-124">Audit mode for evaluation</span></span>

<span data-ttu-id="2d810-125">監査 [モードを使用して](audit-windows-defender.md) 、攻撃表面の縮小ルールが有効な場合に組織に与える影響を評価します。</span><span class="sxs-lookup"><span data-stu-id="2d810-125">Use [audit mode](audit-windows-defender.md) to evaluate how attack surface reduction rules would affect your organization if enabled.</span></span> <span data-ttu-id="2d810-126">監査モードですべてのルールを最初に実行して、そのルールがビジネスライン アプリケーションに与える影響を理解できます。</span><span class="sxs-lookup"><span data-stu-id="2d810-126">Run all rules in audit mode first so you can understand how they affect your line-of-business applications.</span></span> <span data-ttu-id="2d810-127">多くの業務用アプリケーションは、限られたセキュリティ上の懸念を持って記述され、マルウェアに似た方法でタスクを実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-127">Many line-of-business applications are written with limited security concerns, and they might perform tasks in ways that seem similar to malware.</span></span> <span data-ttu-id="2d810-128">監査データを監視し、必要なアプリケーションの [除外](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) を追加することで、生産性を低下させずに攻撃表面の縮小ルールを展開できます。</span><span class="sxs-lookup"><span data-stu-id="2d810-128">By monitoring audit data and [adding exclusions](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) for necessary applications, you can deploy attack surface reduction rules without reducing productivity.</span></span>

## <a name="warn-mode-for-users"></a><span data-ttu-id="2d810-129">ユーザーの警告モード</span><span class="sxs-lookup"><span data-stu-id="2d810-129">Warn mode for users</span></span>

<span data-ttu-id="2d810-130">(**NEW**!)警告モード機能の前に、有効になっている攻撃表面の縮小ルールを監査モードまたはブロック モードに設定できます。</span><span class="sxs-lookup"><span data-stu-id="2d810-130">(**NEW**!) Prior to warn mode capabilities, attack surface reduction rules that are enabled could be set to either audit mode or block mode.</span></span> <span data-ttu-id="2d810-131">新しい警告モードでは、攻撃表面の縮小ルールによってコンテンツがブロックされるたびに、コンテンツがブロックされたかどうかを示すダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d810-131">With the new warn mode, whenever content is blocked by an attack surface reduction rule, users see a dialog box that indicates the content is blocked.</span></span> <span data-ttu-id="2d810-132">ダイアログ ボックスには、コンテンツのブロックを解除するオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d810-132">The dialog box also offers the user an option to unblock the content.</span></span> <span data-ttu-id="2d810-133">その後、ユーザーはアクションを再試行し、操作が完了します。</span><span class="sxs-lookup"><span data-stu-id="2d810-133">The user can then retry their action, and the operation completes.</span></span> <span data-ttu-id="2d810-134">ユーザーがコンテンツのブロックを解除すると、コンテンツは 24 時間ブロック解除されたままで、その後ブロックが再開されます。</span><span class="sxs-lookup"><span data-stu-id="2d810-134">When a user unblocks content, the content remains unblocked for 24 hours, and then blocking resumes.</span></span>

<span data-ttu-id="2d810-135">警告モードは、ユーザーが自分のタスクを実行するために必要なコンテンツにアクセスするのを防ぐことなく、組織が攻撃表面の縮小ルールを設定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2d810-135">Warn mode helps your organization have attack surface reduction rules in place without preventing users from accessing the content they need to perform their tasks.</span></span>

### <a name="requirements-for-warn-mode-to-work"></a><span data-ttu-id="2d810-136">警告モードが機能する要件</span><span class="sxs-lookup"><span data-stu-id="2d810-136">Requirements for warn mode to work</span></span>

<span data-ttu-id="2d810-137">警告モードは、次のバージョンの警告を実行しているデバイスWindows。</span><span class="sxs-lookup"><span data-stu-id="2d810-137">Warn mode is supported on devices running the following versions of Windows:</span></span>

- <span data-ttu-id="2d810-138">[Windows 10 Version 1809](/windows/whats-new/whats-new-windows-10-version-1809)以降</span><span class="sxs-lookup"><span data-stu-id="2d810-138">[Windows 10, version 1809](/windows/whats-new/whats-new-windows-10-version-1809) or later</span></span>
- <span data-ttu-id="2d810-139">[Windows Server バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)以降</span><span class="sxs-lookup"><span data-stu-id="2d810-139">[Windows Server, version 1809](/windows-server/get-started/whats-new-in-windows-server-1809) or later</span></span>

<span data-ttu-id="2d810-140">Microsoft Defender ウイルス対策モードでリアルタイム保護を実行している[必要があります](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)。</span><span class="sxs-lookup"><span data-stu-id="2d810-140">Microsoft Defender Antivirus must be running with real-time protection in [Active mode](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state).</span></span>

<span data-ttu-id="2d810-141">さらに、マルウェア対策[Microsoft Defender ウイルス対策更新プログラムがインストールされていることを](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)確認します。</span><span class="sxs-lookup"><span data-stu-id="2d810-141">In addition, make sure [Microsoft Defender Antivirus and antimalware updates](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) are installed.</span></span>

- <span data-ttu-id="2d810-142">プラットフォームリリースの最小要件: `4.18.2008.9`</span><span class="sxs-lookup"><span data-stu-id="2d810-142">Minimum platform release requirement: `4.18.2008.9`</span></span>
- <span data-ttu-id="2d810-143">エンジンリリースの最小要件: `1.1.17400.5`</span><span class="sxs-lookup"><span data-stu-id="2d810-143">Minimum engine release requirement: `1.1.17400.5`</span></span>

<span data-ttu-id="2d810-144">詳細と更新プログラムの取得については [、「Update for Microsoft Defender マルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="2d810-144">For more information and to get your updates, see [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).</span></span>

### <a name="cases-where-warn-mode-is-not-supported"></a><span data-ttu-id="2d810-145">警告モードがサポートされていない場合</span><span class="sxs-lookup"><span data-stu-id="2d810-145">Cases where warn mode is not supported</span></span>

<span data-ttu-id="2d810-146">警告モードは、3 つの攻撃表面の縮小ルールを構成するときにサポートMicrosoft エンドポイント マネージャー。</span><span class="sxs-lookup"><span data-stu-id="2d810-146">Warn mode is not supported for three attack surface reduction rules when you configure them in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="2d810-147">(グループ ポリシーを使用して攻撃表面の縮小ルールを構成する場合は、警告モードがサポートされます)。警告モードを構成するときに警告モードをサポートしない 3 つのMicrosoft エンドポイント マネージャーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d810-147">(If you use Group Policy to configure your attack surface reduction rules, warn mode is supported.) The three rules that do not support warn mode when you configure them in Microsoft Endpoint Manager are as follows:</span></span>

- <span data-ttu-id="2d810-148">[ダウンロードした実行可能コンテンツ (GUID)](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)の起動から JavaScript または VBScript をブロックする `d3e037e1-3eb8-44c8-a917-57927947596d`</span><span class="sxs-lookup"><span data-stu-id="2d810-148">[Block JavaScript or VBScript from launching downloaded executable content](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`)</span></span>
- <span data-ttu-id="2d810-149">[WMI イベント サブスクリプション (GUID) による永続](#block-persistence-through-wmi-event-subscription) 化をブロック `e6db77e5-3df2-4cf1-b95a-636979351e5b` する</span><span class="sxs-lookup"><span data-stu-id="2d810-149">[Block persistence through WMI event subscription](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`)</span></span>
- <span data-ttu-id="2d810-150">[ランサムウェアに対する高度な保護を使用](#use-advanced-protection-against-ransomware) する `c1db55ab-c21a-4637-bb3f-a12568109d35` (GUID)</span><span class="sxs-lookup"><span data-stu-id="2d810-150">[Use advanced protection against ransomware](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`)</span></span>

<span data-ttu-id="2d810-151">さらに、以前のバージョンのバージョンのデバイスで警告モードはサポートWindows。</span><span class="sxs-lookup"><span data-stu-id="2d810-151">In addition, warn mode is not supported on devices running older versions of Windows.</span></span> <span data-ttu-id="2d810-152">このような場合、警告モードで実行するように構成された攻撃表面の縮小ルールは、ブロック モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="2d810-152">In those cases, attack surface reduction rules that are configured to run in warn mode will run in block mode.</span></span>

## <a name="notifications-and-alerts"></a><span data-ttu-id="2d810-153">通知とアラート</span><span class="sxs-lookup"><span data-stu-id="2d810-153">Notifications and alerts</span></span>

<span data-ttu-id="2d810-154">攻撃表面の縮小ルールがトリガーされるたびに、デバイスに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d810-154">Whenever an attack surface reduction rule is triggered, a notification is displayed on the device.</span></span> <span data-ttu-id="2d810-155">会社の詳細や連絡先情報を使用して[通知をカスタマイズ](customize-attack-surface-reduction.md#customize-the-notification)することができます。</span><span class="sxs-lookup"><span data-stu-id="2d810-155">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span>

<span data-ttu-id="2d810-156">さらに、特定の攻撃表面の縮小ルールがトリガーされると、アラートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2d810-156">In addition, when certain attack surface reduction rules are triggered, alerts are generated.</span></span>

<span data-ttu-id="2d810-157">通知と生成されたアラートは、Microsoft 365 Defender ポータル ( ) (以前は [https://security.microsoft.com](https://security.microsoft.com) Microsoft Defender セキュリティ センター)[で表示できます](microsoft-defender-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2d810-157">Notifications and any alerts that are generated can be viewed in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) (formerly called the [Microsoft Defender Security Center](microsoft-defender-security-center.md)).</span></span>

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a><span data-ttu-id="2d810-158">高度な狩猟と攻撃表面の縮小イベント</span><span class="sxs-lookup"><span data-stu-id="2d810-158">Advanced hunting and attack surface reduction events</span></span>

<span data-ttu-id="2d810-159">高度な検索を使用して、攻撃表面の縮小イベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2d810-159">You can use advanced hunting to view attack surface reduction events.</span></span> <span data-ttu-id="2d810-160">受信データの量を合理化するために、高度な検索では、1 時間ごとに一意のプロセスのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2d810-160">To streamline the volume of incoming data, only unique processes for each hour are viewable with advanced hunting.</span></span> <span data-ttu-id="2d810-161">攻撃表面の縮小イベントの時間は、1 時間以内に初めてイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d810-161">The time of an attack surface reduction event is the first time that event is seen within the hour.</span></span>

<span data-ttu-id="2d810-162">たとえば、午後 2 時の間に 10 台のデバイスで攻撃表面の縮小イベントが発生するとします。</span><span class="sxs-lookup"><span data-stu-id="2d810-162">For example, suppose that an attack surface reduction event occurs on 10 devices during the 2:00 PM hour.</span></span> <span data-ttu-id="2d810-163">最初のイベントが 2:15、最後の 2:45 に発生したとします。</span><span class="sxs-lookup"><span data-stu-id="2d810-163">Suppose that the first event occurred at 2:15, and the last at 2:45.</span></span> <span data-ttu-id="2d810-164">高度な検索では、そのイベントのインスタンスが 1 つ表示されます (実際には 10 台のデバイスで発生した場合でも)、タイムスタンプは午後 2 時 15 分になります。</span><span class="sxs-lookup"><span data-stu-id="2d810-164">With advanced hunting, you'll see one instance of that event (even though it actually occurred on 10 devices), and its timestamp will be 2:15 PM.</span></span>

<span data-ttu-id="2d810-165">高度な狩猟の詳細については、「高度な狩猟 [を使用して脅威を事前に検出する」を参照してください](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2d810-165">For more information about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="attack-surface-reduction-features-across-windows-versions"></a><span data-ttu-id="2d810-166">複数のバージョンの攻撃表面Windows機能</span><span class="sxs-lookup"><span data-stu-id="2d810-166">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="2d810-167">次のエディションとバージョンのデバイスを実行しているデバイスに対して攻撃表面の縮小ルールをWindows。</span><span class="sxs-lookup"><span data-stu-id="2d810-167">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="2d810-168">Windows 10 Proバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="2d810-168">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="2d810-169">Windows 10 Enterpriseバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="2d810-169">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="2d810-170">Windowsサーバー、[バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803)以降</span><span class="sxs-lookup"><span data-stu-id="2d810-170">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="2d810-171">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d810-171">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="2d810-172">攻撃表面の縮小ルールでは[E5](/windows/deployment/deploy-enterprise-licenses)ライセンスをWindows必要とWindows、高度な管理機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="2d810-172">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="2d810-173">E5 でのみ使用できる高度な機能はWindows含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d810-173">The advanced capabilities - available only in Windows E5 - include:</span></span>

- <span data-ttu-id="2d810-174">Defender for Endpoint で利用できる監視、分析、 [およびワークフロー](microsoft-defender-endpoint.md)</span><span class="sxs-lookup"><span data-stu-id="2d810-174">The monitoring, analytics, and workflows available in [Defender for Endpoint](microsoft-defender-endpoint.md)</span></span>
- <span data-ttu-id="2d810-175">レポート機能と構成機能は[、Microsoft 365 Defender。](/microsoft-365/security/defender/overview-security-center)</span><span class="sxs-lookup"><span data-stu-id="2d810-175">The reporting and configuration capabilities in [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="2d810-176">これらの高度な機能は、E3 ライセンスWindows ProfessionalまたはWindows使用できません。</span><span class="sxs-lookup"><span data-stu-id="2d810-176">These advanced capabilities aren't available with a Windows Professional or Windows E3 license.</span></span> <span data-ttu-id="2d810-177">ただし、これらのライセンスがある場合は、イベント ビューアーとログMicrosoft Defender ウイルス対策を使用して、攻撃表面の縮小ルール イベントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2d810-177">However, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="2d810-178">ポータルで攻撃表面の縮小イベントをMicrosoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="2d810-178">Review attack surface reduction events in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="2d810-179">Defender for Endpoint は、アラート調査シナリオの一環として、イベントとブロックの詳細なレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="2d810-179">Defender for Endpoint provides detailed reporting for events and blocks as part of alert investigation scenarios.</span></span>

<span data-ttu-id="2d810-180">高度な検索を使用して、Microsoft 365 Defender Defender [for](microsoft-defender-security-center.md) Endpoint データ[をクエリできます](advanced-hunting-query-language.md)。</span><span class="sxs-lookup"><span data-stu-id="2d810-180">You can query Defender for Endpoint data in [Microsoft 365 Defender](microsoft-defender-security-center.md) by using [advanced hunting](advanced-hunting-query-language.md).</span></span> <span data-ttu-id="2d810-181">監査モードを実行している [場合](audit-windows-defender.md)は、高度な検索を使用して、攻撃表面の縮小ルールが環境に与える影響を理解できます。</span><span class="sxs-lookup"><span data-stu-id="2d810-181">If you're running [audit mode](audit-windows-defender.md), you can use advanced hunting to understand how attack surface reduction rules might affect your environment.</span></span>

<span data-ttu-id="2d810-182">クエリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2d810-182">Here is an example query:</span></span>

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="2d810-183">イベント ビューアーで攻撃表面の縮小イベントWindows確認する</span><span class="sxs-lookup"><span data-stu-id="2d810-183">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="2d810-184">次のイベント ログをWindowsして、攻撃表面の縮小ルールによって生成されたイベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2d810-184">You can review the Windows event log to view events generated by attack surface reduction rules:</span></span>

1. <span data-ttu-id="2d810-185">評価パッケージ [をダウンロードし](https://aka.ms/mp7z2w) 、デバイス上 *cfa-events.xmlアクセスしやすい* 場所にファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="2d810-185">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>

2. <span data-ttu-id="2d810-186">[イベント ビューアー] という *単語* を入力して、スタート メニューを開Windowsします。</span><span class="sxs-lookup"><span data-stu-id="2d810-186">Enter the words, *Event Viewer*, into the Start menu to open the Windows Event Viewer.</span></span>

3. <span data-ttu-id="2d810-187">[アクション **] で**、[カスタム **ビューのインポート.... を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2d810-187">Under **Actions**, select **Import custom view...**.</span></span>

4. <span data-ttu-id="2d810-188">抽出された場所 *cfa-events.xml* ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="2d810-188">Select the file *cfa-events.xml* from where it was extracted.</span></span> <span data-ttu-id="2d810-189">または [、XML を直接コピーします](event-views.md)。</span><span class="sxs-lookup"><span data-stu-id="2d810-189">Alternatively, [copy the XML directly](event-views.md).</span></span>

5. <span data-ttu-id="2d810-190">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d810-190">Select **OK**.</span></span>

<span data-ttu-id="2d810-191">イベントをフィルター処理して、次のイベントのみを表示するカスタム ビューを作成できます。そのすべては、フォルダー アクセスの制御に関連しています。</span><span class="sxs-lookup"><span data-stu-id="2d810-191">You can create a custom view that filters events to only show the following events, all of which are related to controlled folder access:</span></span>

|<span data-ttu-id="2d810-192">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2d810-192">Event ID</span></span>|<span data-ttu-id="2d810-193">説明</span><span class="sxs-lookup"><span data-stu-id="2d810-193">Description</span></span>|
|---|---|
|<span data-ttu-id="2d810-194">5007</span><span class="sxs-lookup"><span data-stu-id="2d810-194">5007</span></span>|<span data-ttu-id="2d810-195">設定が変更された場合のイベント</span><span class="sxs-lookup"><span data-stu-id="2d810-195">Event when settings are changed</span></span>|
|<span data-ttu-id="2d810-196">1121</span><span class="sxs-lookup"><span data-stu-id="2d810-196">1121</span></span>|<span data-ttu-id="2d810-197">ブロック モードでルールが発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="2d810-197">Event when rule fires in Block-mode</span></span>|
|<span data-ttu-id="2d810-198">1122</span><span class="sxs-lookup"><span data-stu-id="2d810-198">1122</span></span>|<span data-ttu-id="2d810-199">監査モードでルールが発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="2d810-199">Event when rule fires in Audit-mode</span></span>|

<span data-ttu-id="2d810-200">イベント ログの攻撃表面の縮小イベント用にリストされている "エンジンバージョン" は、オペレーティング システムではなく Defender for Endpoint によって生成されます。</span><span class="sxs-lookup"><span data-stu-id="2d810-200">The "engine version" listed for attack surface reduction events in the event log, is generated by Defender for Endpoint, not by the operating system.</span></span> <span data-ttu-id="2d810-201">Defender for Endpoint は、Windows 10と統合されています。そのため、この機能は、インストールされているすべてのデバイスWindows 10します。</span><span class="sxs-lookup"><span data-stu-id="2d810-201">Defender for Endpoint is integrated with Windows 10, so this feature works on all devices with Windows 10 installed.</span></span>

## <a name="attack-surface-reduction-rules"></a><span data-ttu-id="2d810-202">攻撃面の減少ルール</span><span class="sxs-lookup"><span data-stu-id="2d810-202">Attack surface reduction rules</span></span>

<span data-ttu-id="2d810-203">次の表とサブセクションでは、16 の攻撃表面の縮小ルールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2d810-203">The following table and subsections describe each of the 16 attack surface reduction rules.</span></span> <span data-ttu-id="2d810-204">攻撃表面の縮小ルールは、ルール名によってアルファベット順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d810-204">The attack surface reduction rules are listed in alphabetical order, by rule name.</span></span>

<span data-ttu-id="2d810-205">グループ ポリシーまたは PowerShell を使用して攻撃表面の縮小ルールを構成する場合は、GUID が必要です。</span><span class="sxs-lookup"><span data-stu-id="2d810-205">If you are configuring attack surface reduction rules by using Group Policy or PowerShell, you'll need the GUIDs.</span></span> <span data-ttu-id="2d810-206">一方、ユーザー設定またはMicrosoft エンドポイント マネージャーをMicrosoft Intune GUID は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="2d810-206">On the other hand, if you use Microsoft Endpoint Manager or Microsoft Intune, you do not need the GUIDs.</span></span>

|<span data-ttu-id="2d810-207">ルールの名前</span><span class="sxs-lookup"><span data-stu-id="2d810-207">Rule name</span></span>|<span data-ttu-id="2d810-208">GUID</span><span class="sxs-lookup"><span data-stu-id="2d810-208">GUID</span></span>|<span data-ttu-id="2d810-209">ファイル&フォルダーの除外</span><span class="sxs-lookup"><span data-stu-id="2d810-209">File & folder exclusions</span></span>|<span data-ttu-id="2d810-210">サポートされる最小 OS</span><span class="sxs-lookup"><span data-stu-id="2d810-210">Minimum OS supported</span></span>|
|---|:---:|---|---|
|[<span data-ttu-id="2d810-211">悪用された脆弱な署名済みドライバーの悪用をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-211">Block abuse of exploited vulnerable signed drivers</span></span>](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|<span data-ttu-id="2d810-212">サポート</span><span class="sxs-lookup"><span data-stu-id="2d810-212">Supported</span></span>|<span data-ttu-id="2d810-213">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上)</span><span class="sxs-lookup"><span data-stu-id="2d810-213">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater)</span></span> |
|[<span data-ttu-id="2d810-214">Adobe Reader の子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-214">Block Adobe Reader from creating child processes</span></span>](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|<span data-ttu-id="2d810-215">サポート</span><span class="sxs-lookup"><span data-stu-id="2d810-215">Supported</span></span>|<span data-ttu-id="2d810-216">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="2d810-216">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="2d810-217">すべてのアプリケーションOffice子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-217">Block all Office applications from creating child processes</span></span>](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|<span data-ttu-id="2d810-218">サポート</span><span class="sxs-lookup"><span data-stu-id="2d810-218">Supported</span></span>|<span data-ttu-id="2d810-219">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="2d810-219">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="2d810-220">ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="2d810-220">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|<span data-ttu-id="2d810-221">サポート</span><span class="sxs-lookup"><span data-stu-id="2d810-221">Supported</span></span>|<span data-ttu-id="2d810-222">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="2d810-222">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="2d810-223">メール クライアントと Web メールから実行可能なコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-223">Block executable content from email client and webmail</span></span>](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|<span data-ttu-id="2d810-224">サポート</span><span class="sxs-lookup"><span data-stu-id="2d810-224">Supported</span></span>|<span data-ttu-id="2d810-225">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="2d810-225">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="2d810-226">有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-226">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|<span data-ttu-id="2d810-227">サポート</span><span class="sxs-lookup"><span data-stu-id="2d810-227">Supported</span></span>|<span data-ttu-id="2d810-228">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="2d810-228">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="2d810-229">難読化される可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-229">Block execution of potentially obfuscated scripts</span></span>](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|<span data-ttu-id="2d810-230">サポート</span><span class="sxs-lookup"><span data-stu-id="2d810-230">Supported</span></span>|<span data-ttu-id="2d810-231">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="2d810-231">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="2d810-232">JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-232">Block JavaScript or VBScript from launching downloaded executable content</span></span>](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|<span data-ttu-id="2d810-233">サポート</span><span class="sxs-lookup"><span data-stu-id="2d810-233">Supported</span></span>|<span data-ttu-id="2d810-234">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="2d810-234">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="2d810-235">実行可能Office作成するアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="2d810-235">Block Office applications from creating executable content</span></span>](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|<span data-ttu-id="2d810-236">サポート</span><span class="sxs-lookup"><span data-stu-id="2d810-236">Supported</span></span>|<span data-ttu-id="2d810-237">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="2d810-237">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="2d810-238">アプリケーションOffice他のプロセスへのコードの挿入をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-238">Block Office applications from injecting code into other processes</span></span>](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|<span data-ttu-id="2d810-239">サポート</span><span class="sxs-lookup"><span data-stu-id="2d810-239">Supported</span></span>|<span data-ttu-id="2d810-240">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="2d810-240">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="2d810-241">通信Officeプロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-241">Block Office communication application from creating child processes</span></span>](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|<span data-ttu-id="2d810-242">サポート</span><span class="sxs-lookup"><span data-stu-id="2d810-242">Supported</span></span>|<span data-ttu-id="2d810-243">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="2d810-243">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="2d810-244">WMI イベント サブスクリプションによる永続化のブロック</span><span class="sxs-lookup"><span data-stu-id="2d810-244">Block persistence through WMI event subscription</span></span>](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|<span data-ttu-id="2d810-245">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="2d810-245">Not supported</span></span>|<span data-ttu-id="2d810-246">[Windows 10バージョン 1903](/windows/whats-new/whats-new-windows-10-version-1903) (ビルド 18362) 以上</span><span class="sxs-lookup"><span data-stu-id="2d810-246">[Windows 10, version 1903](/windows/whats-new/whats-new-windows-10-version-1903) (build 18362) or greater</span></span>|
|[<span data-ttu-id="2d810-247">PSExec および WMI コマンドから発生するプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-247">Block process creations originating from PSExec and WMI commands</span></span>](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|<span data-ttu-id="2d810-248">サポート</span><span class="sxs-lookup"><span data-stu-id="2d810-248">Supported</span></span>|<span data-ttu-id="2d810-249">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="2d810-249">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="2d810-250">USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-250">Block untrusted and unsigned processes that run from USB</span></span>](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|<span data-ttu-id="2d810-251">サポート</span><span class="sxs-lookup"><span data-stu-id="2d810-251">Supported</span></span>|<span data-ttu-id="2d810-252">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="2d810-252">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="2d810-253">Win32 API 呼び出しをブロックOfficeマクロ</span><span class="sxs-lookup"><span data-stu-id="2d810-253">Block Win32 API calls from Office macros</span></span>](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|<span data-ttu-id="2d810-254">サポート</span><span class="sxs-lookup"><span data-stu-id="2d810-254">Supported</span></span>|<span data-ttu-id="2d810-255">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="2d810-255">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="2d810-256">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="2d810-256">Use advanced protection against ransomware</span></span>](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|<span data-ttu-id="2d810-257">サポート</span><span class="sxs-lookup"><span data-stu-id="2d810-257">Supported</span></span>|<span data-ttu-id="2d810-258">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="2d810-258">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a><span data-ttu-id="2d810-259">悪用された脆弱な署名済みドライバーの悪用をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-259">Block abuse of exploited vulnerable signed drivers</span></span>

<span data-ttu-id="2d810-260">このルールは、アプリケーションが脆弱な署名済みドライバーをディスクに書き込むのを防ぐためです。</span><span class="sxs-lookup"><span data-stu-id="2d810-260">This rule prevents an application from writing a vulnerable signed driver to disk.</span></span> <span data-ttu-id="2d810-261">インザワイルドで脆弱な署名済みドライバーは、カーネルにアクセスするのに十分な特権を持つローカル アプリケーション \-  \- によって悪用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-261">In-the-wild, vulnerable signed drivers can be exploited by local applications \- _that have sufficient privileges_ \- to gain access to the kernel.</span></span> <span data-ttu-id="2d810-262">脆弱な署名付きドライバーを使用すると、攻撃者はセキュリティ ソリューションを無効または回避し、最終的にはシステムの侵害につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-262">Vulnerable signed drivers enable attackers to disable or circumvent security solutions, eventually leading to system compromise.</span></span>

<span data-ttu-id="2d810-263">[ **悪用された脆弱な** 署名済みドライバーの悪用をブロックする] ルールは、システム上に既に存在するドライバーの読み込みをブロックしない。</span><span class="sxs-lookup"><span data-stu-id="2d810-263">The **Block abuse of exploited vulnerable signed drivers** rule does not block a driver already existing on the system from being loaded.</span></span>

>[!NOTE]
>
> <span data-ttu-id="2d810-264">このルールは [、MEM OMA-URI](enable-attack-surface-reduction.md#mem) カスタム ルールのプロシージャ情報に対して MEM OMA-URI を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="2d810-264">You can configure this rule using [MEM OMA-URI](enable-attack-surface-reduction.md#mem) for MEM OMA-URI custom rules procedural information.</span></span>
>
> <span data-ttu-id="2d810-265">PowerShell を使用してこのルールを [構成できます](enable-attack-surface-reduction.md#powershell)。</span><span class="sxs-lookup"><span data-stu-id="2d810-265">You can also configure this rule using [PowerShell](enable-attack-surface-reduction.md#powershell).</span></span>
>
> <span data-ttu-id="2d810-266">ドライバーを調べるには、この Web サイトを使用して分析 [用のドライバーを送信します](https://www.microsoft.com/en-us/wdsi/driversubmission)。</span><span class="sxs-lookup"><span data-stu-id="2d810-266">To have a driver examined, use this Web site to [Submit a driver for analysis](https://www.microsoft.com/en-us/wdsi/driversubmission).</span></span>

<span data-ttu-id="2d810-267">このルールは、ASR がサポートされているすべてのバージョンでサポートされます。これは次の場合です。</span><span class="sxs-lookup"><span data-stu-id="2d810-267">This rule is supported in all versions in which ASR is supported; which is:</span></span>

- <span data-ttu-id="2d810-268">[Windows 10 Proバージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="2d810-268">[Windows 10 Pro, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="2d810-269">[Windows 10 Enterpriseバージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="2d810-269">[Windows 10 Enterprise, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="2d810-270">[Windows Server バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803)以降</span><span class="sxs-lookup"><span data-stu-id="2d810-270">[Windows Server, version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="2d810-271">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d810-271">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="2d810-272">Intune 名: `Block abuse of exploited vulnerable signed drivers`</span><span class="sxs-lookup"><span data-stu-id="2d810-272">Intune Name: `Block abuse of exploited vulnerable signed drivers`</span></span>

<span data-ttu-id="2d810-273">GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span><span class="sxs-lookup"><span data-stu-id="2d810-273">GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span></span>

### <a name="block-adobe-reader-from-creating-child-processes"></a><span data-ttu-id="2d810-274">Adobe Reader の子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-274">Block Adobe Reader from creating child processes</span></span>

<span data-ttu-id="2d810-275">このルールは、Adobe Reader によるプロセスの作成をブロックすることで攻撃を防止します。</span><span class="sxs-lookup"><span data-stu-id="2d810-275">This rule prevents attacks by blocking Adobe Reader from creating processes.</span></span>

<span data-ttu-id="2d810-276">ソーシャル エンジニアリングや悪用を通じて、マルウェアはペイロードをダウンロードして起動し、Adobe Reader から抜け出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-276">Through social engineering or exploits, malware can download and launch payloads, and break out of Adobe Reader.</span></span> <span data-ttu-id="2d810-277">Adobe Reader によって子プロセスが生成されるのをブロックすることで、子プロセスをベクターとして使用しようとするマルウェアが拡散を防止します。</span><span class="sxs-lookup"><span data-stu-id="2d810-277">By blocking child processes from being generated by Adobe Reader, malware attempting to use it as a vector are prevented from spreading.</span></span>

<span data-ttu-id="2d810-278">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2d810-278">This rule was introduced in:</span></span>

- [<span data-ttu-id="2d810-279">Windows 10 Version 1809</span><span class="sxs-lookup"><span data-stu-id="2d810-279">Windows 10, version 1809</span></span>](/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="2d810-280">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="2d810-280">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="2d810-281">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d810-281">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="2d810-282">Intune 名: `Process creation from Adobe Reader (beta)`</span><span class="sxs-lookup"><span data-stu-id="2d810-282">Intune name: `Process creation from Adobe Reader (beta)`</span></span>

<span data-ttu-id="2d810-283">Configuration Manager 名: まだ使用できません</span><span class="sxs-lookup"><span data-stu-id="2d810-283">Configuration Manager name: Not yet available</span></span>

<span data-ttu-id="2d810-284">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span><span class="sxs-lookup"><span data-stu-id="2d810-284">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span></span>

### <a name="block-all-office-applications-from-creating-child-processes"></a><span data-ttu-id="2d810-285">すべてのアプリケーションOffice子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-285">Block all Office applications from creating child processes</span></span>

<span data-ttu-id="2d810-286">このルールは、Officeプロセスの作成をブロックします。</span><span class="sxs-lookup"><span data-stu-id="2d810-286">This rule blocks Office apps from creating child processes.</span></span> <span data-ttu-id="2d810-287">Officeには、Word、Excel、PowerPoint、OneNote、Access が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d810-287">Office apps include Word, Excel, PowerPoint, OneNote, and Access.</span></span>

<span data-ttu-id="2d810-288">悪意のある子プロセスを作成する方法は、一般的なマルウェア戦略です。</span><span class="sxs-lookup"><span data-stu-id="2d810-288">Creating malicious child processes is a common malware strategy.</span></span> <span data-ttu-id="2d810-289">マルウェアがベクターとしてOffice、VBA マクロを実行し、コードを悪用して、より多くのペイロードをダウンロードして実行しようとする場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-289">Malware that abuse Office as a vector often run VBA macros and exploit code to download and attempt to run more payloads.</span></span> <span data-ttu-id="2d810-290">ただし、一部の正当な業務行アプリケーションでは、良性の目的で子プロセスを生成する場合があります。コマンド プロンプトを生成したり、PowerShell を使用してレジストリ設定を構成したりします。</span><span class="sxs-lookup"><span data-stu-id="2d810-290">However, some legitimate line-of-business applications might also generate child processes for benign purposes; such as spawning a command prompt or using PowerShell to configure registry settings.</span></span>

<span data-ttu-id="2d810-291">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2d810-291">This rule was introduced in:</span></span>

- [<span data-ttu-id="2d810-292">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="2d810-292">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="2d810-293">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="2d810-293">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="2d810-294">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d810-294">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="2d810-295">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="2d810-295">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="2d810-296">Intune 名: `Office apps launching child processes`</span><span class="sxs-lookup"><span data-stu-id="2d810-296">Intune name: `Office apps launching child processes`</span></span>

<span data-ttu-id="2d810-297">Configuration Manager 名: `Block Office application from creating child processes`</span><span class="sxs-lookup"><span data-stu-id="2d810-297">Configuration Manager name: `Block Office application from creating child processes`</span></span>

<span data-ttu-id="2d810-298">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span><span class="sxs-lookup"><span data-stu-id="2d810-298">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span></span>

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a><span data-ttu-id="2d810-299">ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-299">Block credential stealing from the Windows local security authority subsystem</span></span>

<span data-ttu-id="2d810-300">このルールは、ローカル セキュリティ機関サブシステム サービス (LSASS) をロックダウンして資格情報の盗用を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2d810-300">This rule helps prevent credential stealing by locking down Local Security Authority Subsystem Service (LSASS).</span></span>

<span data-ttu-id="2d810-301">LSASS は、コンピューターにサインインするユーザーをWindowsします。</span><span class="sxs-lookup"><span data-stu-id="2d810-301">LSASS authenticates users who sign in on a Windows computer.</span></span> <span data-ttu-id="2d810-302">Microsoft Defender Credential Guard in Windows 10は、通常、LSASS から資格情報を抽出しようとして防止します。</span><span class="sxs-lookup"><span data-stu-id="2d810-302">Microsoft Defender Credential Guard in Windows 10 normally prevents attempts to extract credentials from LSASS.</span></span> <span data-ttu-id="2d810-303">ただし、一部の組織では、カスタム スマートカード ドライバーやローカル セキュリティ機関 (LSA) に読み込む他のプログラムとの互換性の問題により、すべてのコンピューターで Credential Guard を有効にできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-303">However, some organizations can't enable Credential Guard on all of their computers because of compatibility issues with custom smartcard drivers or other programs that load into the Local Security Authority (LSA).</span></span> <span data-ttu-id="2d810-304">このような場合、攻撃者は Mimikatz のようなハッキング ツールを使用して、LSASS からクリアテキスト パスワードと NTLM ハッシュをスクレイピングできます。</span><span class="sxs-lookup"><span data-stu-id="2d810-304">In these cases, attackers can use hack tools like Mimikatz to scrape cleartext passwords and NTLM hashes from LSASS.</span></span>

> [!NOTE]
> <span data-ttu-id="2d810-305">一部のアプリでは、実行中のすべてのプロセスを列挙し、網羅的なアクセス許可を使用して開きます。</span><span class="sxs-lookup"><span data-stu-id="2d810-305">In some apps, the code enumerates all running processes and attempts to open them with exhaustive permissions.</span></span> <span data-ttu-id="2d810-306">このルールは、アプリのプロセスのオープン アクションを拒否し、詳細をセキュリティ イベント ログに記録します。</span><span class="sxs-lookup"><span data-stu-id="2d810-306">This rule denies the app's process open action and logs the details to the security event log.</span></span> <span data-ttu-id="2d810-307">このルールでは、多くのノイズが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-307">This rule can generate a lot of noise.</span></span> <span data-ttu-id="2d810-308">LSASS を列挙するだけで、機能に実際の影響がないアプリがある場合は、除外リストに追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2d810-308">If you have an app that simply enumerates LSASS, but has no real impact in functionality, there is NO need to add it to the exclusion list.</span></span> <span data-ttu-id="2d810-309">それ自体では、このイベント ログ エントリは必ずしも悪意のある脅威を示すとは限りません。</span><span class="sxs-lookup"><span data-stu-id="2d810-309">By itself, this event log entry doesn't necessarily indicate a malicious threat.</span></span>

<span data-ttu-id="2d810-310">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2d810-310">This rule was introduced in:</span></span>

- [<span data-ttu-id="2d810-311">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="2d810-311">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="2d810-312">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="2d810-312">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="2d810-313">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d810-313">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="2d810-314">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="2d810-314">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="2d810-315">Intune 名: `Flag credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="2d810-315">Intune name: `Flag credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="2d810-316">Configuration Manager 名: `Block credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="2d810-316">Configuration Manager name: `Block credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="2d810-317">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span><span class="sxs-lookup"><span data-stu-id="2d810-317">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span></span>

### <a name="block-executable-content-from-email-client-and-webmail"></a><span data-ttu-id="2d810-318">メール クライアントと Web メールから実行可能なコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-318">Block executable content from email client and webmail</span></span>

<span data-ttu-id="2d810-319">このルールは、Microsoft Outlook アプリケーション、または Outlook.com や他の一般的な Web メール プロバイダー内で開いた電子メールから、次の種類のファイルの起動をブロックします。</span><span class="sxs-lookup"><span data-stu-id="2d810-319">This rule blocks the following file types from launching from email opened within the Microsoft Outlook application, or Outlook.com and other popular webmail providers:</span></span>

- <span data-ttu-id="2d810-320">実行可能ファイル (.exe、.dll.scr など)</span><span class="sxs-lookup"><span data-stu-id="2d810-320">Executable files (such as .exe, .dll, or .scr)</span></span>
- <span data-ttu-id="2d810-321">スクリプト ファイル (PowerShell .ps、Visual Basic .vbs、JavaScript .js ファイルなど)</span><span class="sxs-lookup"><span data-stu-id="2d810-321">Script files (such as a PowerShell .ps, Visual Basic .vbs, or JavaScript .js file)</span></span>

<span data-ttu-id="2d810-322">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2d810-322">This rule was introduced in:</span></span>

- [<span data-ttu-id="2d810-323">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="2d810-323">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="2d810-324">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="2d810-324">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="2d810-325">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d810-325">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="2d810-326">Microsoft エンドポイント マネージャーCB 1710</span><span class="sxs-lookup"><span data-stu-id="2d810-326">Microsoft Endpoint Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="2d810-327">Intune 名: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="2d810-327">Intune name: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span></span>

<span data-ttu-id="2d810-328">Microsoft エンドポイント マネージャー名:`Block executable content from email client and webmail`</span><span class="sxs-lookup"><span data-stu-id="2d810-328">Microsoft Endpoint Manager name: `Block executable content from email client and webmail`</span></span>

<span data-ttu-id="2d810-329">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span><span class="sxs-lookup"><span data-stu-id="2d810-329">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span></span>

> [!NOTE]
> <span data-ttu-id="2d810-330">[メール **クライアントと Web メールからの** 実行可能なコンテンツをブロックする] というルールには、使用するアプリケーションに応じて、次の別の説明があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-330">The rule **Block executable content from email client and webmail** has the following alternative descriptions, depending on which application you use:</span></span>
>
> - <span data-ttu-id="2d810-331">Intune (構成プロファイル): 電子メール (Web メール/メール クライアント) から削除された実行可能コンテンツ (exe、dll、ps、js、vbs など) の実行 (例外なし)。</span><span class="sxs-lookup"><span data-stu-id="2d810-331">Intune (Configuration Profiles): Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions).</span></span>
> - <span data-ttu-id="2d810-332">エンドポイント マネージャー: メールおよび Web メール クライアントからの実行可能コンテンツのダウンロードをブロックします。</span><span class="sxs-lookup"><span data-stu-id="2d810-332">Endpoint Manager: Block executable content download from email and webmail clients.</span></span>
> - <span data-ttu-id="2d810-333">グループ ポリシー: 電子メール クライアントと Web メールから実行可能なコンテンツをブロックします。</span><span class="sxs-lookup"><span data-stu-id="2d810-333">Group Policy: Block executable content from email client and webmail.</span></span>

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a><span data-ttu-id="2d810-334">有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-334">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>

<span data-ttu-id="2d810-335">次の条件が満たされていない限り、.exe、.dll、.scr などの実行可能ファイルが起動をブロックします。</span><span class="sxs-lookup"><span data-stu-id="2d810-335">This rule blocks executable files, such as .exe, .dll, or .scr, from launching unless any of the following conditions are met:</span></span>

- <span data-ttu-id="2d810-336">有病率: 実行可能ファイルは 1,000 を超えるエンドポイントで検出されます</span><span class="sxs-lookup"><span data-stu-id="2d810-336">Prevalence: The executable files are found on more than 1,000 endpoints</span></span>
- <span data-ttu-id="2d810-337">Age: 実行可能ファイルは 24 時間以上前にリリースされました</span><span class="sxs-lookup"><span data-stu-id="2d810-337">Age: The executable files were released more than 24 hours ago</span></span>
- <span data-ttu-id="2d810-338">場所: 実行可能ファイルが信頼できるリストまたは除外リストに含まれている</span><span class="sxs-lookup"><span data-stu-id="2d810-338">Location: The executable files are included in a trusted list or an exclusion list</span></span>

<span data-ttu-id="2d810-339">信頼されていない実行可能ファイルまたは不明な実行可能ファイルを起動すると、ファイルが悪意のあるものか最初ははっきりしない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-339">Launching untrusted or unknown executable files can be risky, as it might not be initially clear if the files are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d810-340">このルールを [使用するには、クラウドによる保護](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-340">You must [enable cloud-delivered protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to use this rule.</span></span>
>
> <span data-ttu-id="2d810-341">GUID で **有病率** 、年齢、または信頼できるリスト条件を満たしていない場合、実行可能ファイルの実行をブロックするルールは、Microsoft が所有し、管理者によって `01443614-cd74-433a-b99e-2ecdc07bfc25` 指定されていません。</span><span class="sxs-lookup"><span data-stu-id="2d810-341">The rule **Block executable files from running unless they meet a prevalence, age, or trusted list criterion** with GUID `01443614-cd74-433a-b99e-2ecdc07bfc25` is owned by Microsoft and is not specified by admins.</span></span> <span data-ttu-id="2d810-342">このルールでは、クラウド配信の保護を使用して、信頼できるリストを定期的に更新します。</span><span class="sxs-lookup"><span data-stu-id="2d810-342">This rule uses cloud-delivered protection to update its trusted list regularly.</span></span>
>
> <span data-ttu-id="2d810-343">個々のファイルまたはフォルダー (フォルダー パスまたは完全修飾リソース名を使用) を指定できますが、適用するルールや除外を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2d810-343">You can specify individual files or folders (using folder paths or fully qualified resource names) but you can't specify which rules or exclusions apply to.</span></span>

<span data-ttu-id="2d810-344">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2d810-344">This rule was introduced in:</span></span>

- [<span data-ttu-id="2d810-345">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="2d810-345">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="2d810-346">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="2d810-346">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="2d810-347">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d810-347">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="2d810-348">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="2d810-348">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="2d810-349">Intune 名: `Executables that don't meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="2d810-349">Intune name: `Executables that don't meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="2d810-350">Configuration Manager 名: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="2d810-350">Configuration Manager name: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="2d810-351">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span><span class="sxs-lookup"><span data-stu-id="2d810-351">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span></span>

### <a name="block-execution-of-potentially-obfuscated-scripts"></a><span data-ttu-id="2d810-352">難読化される可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-352">Block execution of potentially obfuscated scripts</span></span>

<span data-ttu-id="2d810-353">このルールは、難読化されたスクリプト内の疑わしいプロパティを検出します。</span><span class="sxs-lookup"><span data-stu-id="2d810-353">This rule detects suspicious properties within an obfuscated script.</span></span>

<span data-ttu-id="2d810-354">スクリプト難読化は、マルウェア作成者と正当なアプリケーションの両方が、知的財産を隠したり、スクリプトの読み込み時間を短縮したりするために使用する一般的な手法です。</span><span class="sxs-lookup"><span data-stu-id="2d810-354">Script obfuscation is a common technique that both malware authors and legitimate applications use to hide intellectual property or decrease script loading times.</span></span> <span data-ttu-id="2d810-355">マルウェアの作成者は難読化を使用して悪意のあるコードを読みにくくし、人間やセキュリティ ソフトウェアによる詳細な調査を防止します。</span><span class="sxs-lookup"><span data-stu-id="2d810-355">Malware authors also use obfuscation to make malicious code harder to read, which prevents close scrutiny by humans and security software.</span></span>

<span data-ttu-id="2d810-356">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2d810-356">This rule was introduced in:</span></span>

- [<span data-ttu-id="2d810-357">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="2d810-357">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="2d810-358">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="2d810-358">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="2d810-359">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d810-359">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="2d810-360">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="2d810-360">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="2d810-361">Intune 名: `Obfuscated js/vbs/ps/macro code`</span><span class="sxs-lookup"><span data-stu-id="2d810-361">Intune name: `Obfuscated js/vbs/ps/macro code`</span></span>

<span data-ttu-id="2d810-362">Configuration Manager 名: `Block execution of potentially obfuscated scripts`</span><span class="sxs-lookup"><span data-stu-id="2d810-362">Configuration Manager name: `Block execution of potentially obfuscated scripts`</span></span>

<span data-ttu-id="2d810-363">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span><span class="sxs-lookup"><span data-stu-id="2d810-363">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span></span>

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a><span data-ttu-id="2d810-364">JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-364">Block JavaScript or VBScript from launching downloaded executable content</span></span>

<span data-ttu-id="2d810-365">このルールにより、スクリプトは悪意のあるダウンロードコンテンツを起動できません。</span><span class="sxs-lookup"><span data-stu-id="2d810-365">This rule prevents scripts from launching potentially malicious downloaded content.</span></span> <span data-ttu-id="2d810-366">JavaScript または VBScript で記述されたマルウェアは、インターネットから他のマルウェアをフェッチして起動するダウンデータとして機能する場合が多い。</span><span class="sxs-lookup"><span data-stu-id="2d810-366">Malware written in JavaScript or VBScript often acts as a downloader to fetch and launch other malware from the Internet.</span></span>

<span data-ttu-id="2d810-367">一般的ではないが、一般企業向けアプリケーションでは、スクリプトを使用してインストーラーをダウンロードおよび起動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-367">Although not common, line-of-business applications sometimes use scripts to download and launch installers.</span></span>

<span data-ttu-id="2d810-368">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2d810-368">This rule was introduced in:</span></span>

- [<span data-ttu-id="2d810-369">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="2d810-369">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="2d810-370">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="2d810-370">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="2d810-371">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d810-371">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="2d810-372">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="2d810-372">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="2d810-373">Intune 名: `js/vbs executing payload downloaded from Internet (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="2d810-373">Intune name: `js/vbs executing payload downloaded from Internet (no exceptions)`</span></span>

<span data-ttu-id="2d810-374">Configuration Manager 名: `Block JavaScript or VBScript from launching downloaded executable content`</span><span class="sxs-lookup"><span data-stu-id="2d810-374">Configuration Manager name: `Block JavaScript or VBScript from launching downloaded executable content`</span></span>

<span data-ttu-id="2d810-375">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span><span class="sxs-lookup"><span data-stu-id="2d810-375">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span></span>

### <a name="block-office-applications-from-creating-executable-content"></a><span data-ttu-id="2d810-376">実行可能Office作成するアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="2d810-376">Block Office applications from creating executable content</span></span>

<span data-ttu-id="2d810-377">このルール Officeは、悪意のあるコードがディスクに書き込まれるのをブロックすることで、Word、Excel、PowerPoint などのアプリが悪意のある実行可能コンテンツを作成するのを防ぐためです。</span><span class="sxs-lookup"><span data-stu-id="2d810-377">This rule prevents Office apps, including Word, Excel, and PowerPoint, from creating potentially malicious executable content, by blocking malicious code from being written to disk.</span></span>

<span data-ttu-id="2d810-378">マルウェアは、Officeとして悪用され、悪意のあるOfficeをディスクに保存しようとする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-378">Malware that abuses Office as a vector might attempt to break out of Office and save malicious components to disk.</span></span> <span data-ttu-id="2d810-379">これらの悪意のあるコンポーネントは、コンピューターの再起動後も存続し、システム上で保持されます。</span><span class="sxs-lookup"><span data-stu-id="2d810-379">These malicious components would survive a computer reboot and persist on the system.</span></span> <span data-ttu-id="2d810-380">したがって、このルールは一般的な永続化手法に対して防御します。</span><span class="sxs-lookup"><span data-stu-id="2d810-380">Therefore, this rule defends against a common persistence technique.</span></span>

<span data-ttu-id="2d810-381">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2d810-381">This rule was introduced in:</span></span>

- [<span data-ttu-id="2d810-382">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="2d810-382">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="2d810-383">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="2d810-383">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="2d810-384">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d810-384">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- <span data-ttu-id="2d810-385">[System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM がMicrosoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="2d810-385">[System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM is now Microsoft Endpoint Configuration Manager)</span></span>

<span data-ttu-id="2d810-386">Intune 名: `Office apps/macros creating executable content`</span><span class="sxs-lookup"><span data-stu-id="2d810-386">Intune name: `Office apps/macros creating executable content`</span></span>

<span data-ttu-id="2d810-387">SCCM 名: `Block Office applications from creating executable content`</span><span class="sxs-lookup"><span data-stu-id="2d810-387">SCCM name: `Block Office applications from creating executable content`</span></span>

<span data-ttu-id="2d810-388">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span><span class="sxs-lookup"><span data-stu-id="2d810-388">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span></span>

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a><span data-ttu-id="2d810-389">アプリケーションOffice他のプロセスへのコードの挿入をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-389">Block Office applications from injecting code into other processes</span></span>

<span data-ttu-id="2d810-390">このルールは、アプリから他のプロセスへのコードOffice試行をブロックします。</span><span class="sxs-lookup"><span data-stu-id="2d810-390">This rule blocks code injection attempts from Office apps into other processes.</span></span>

<span data-ttu-id="2d810-391">攻撃者は、Officeを使用して、コード挿入を通じて悪意のあるコードを他のプロセスに移行しようとする可能性があります。そのため、コードはクリーン なプロセスとして悪用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-391">Attackers might attempt to use Office apps to migrate malicious code into other processes through code injection, so the code can masquerade as a clean process.</span></span>

<span data-ttu-id="2d810-392">コードインジェクションを使用する正当なビジネス上の目的はありません。</span><span class="sxs-lookup"><span data-stu-id="2d810-392">There are no known legitimate business purposes for using code injection.</span></span>

<span data-ttu-id="2d810-393">このルールは、Word、Excel、およびPowerPoint。</span><span class="sxs-lookup"><span data-stu-id="2d810-393">This rule applies to Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="2d810-394">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2d810-394">This rule was introduced in:</span></span>

- [<span data-ttu-id="2d810-395">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="2d810-395">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="2d810-396">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="2d810-396">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="2d810-397">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d810-397">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="2d810-398">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="2d810-398">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="2d810-399">Intune 名: `Office apps injecting code into other processes (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="2d810-399">Intune name: `Office apps injecting code into other processes (no exceptions)`</span></span>

<span data-ttu-id="2d810-400">Configuration Manager 名: `Block Office applications from injecting code into other processes`</span><span class="sxs-lookup"><span data-stu-id="2d810-400">Configuration Manager name: `Block Office applications from injecting code into other processes`</span></span>

<span data-ttu-id="2d810-401">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span><span class="sxs-lookup"><span data-stu-id="2d810-401">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span></span>

### <a name="block-office-communication-application-from-creating-child-processes"></a><span data-ttu-id="2d810-402">通信Officeプロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-402">Block Office communication application from creating child processes</span></span>

<span data-ttu-id="2d810-403">このルールは、Outlookプロセスを作成する一方で、正当なプロセス機能Outlookします。</span><span class="sxs-lookup"><span data-stu-id="2d810-403">This rule prevents Outlook from creating child processes, while still allowing legitimate Outlook functions.</span></span>

<span data-ttu-id="2d810-404">このルールは、ソーシャル エンジニアリング攻撃から保護し、コードを悪用して、セキュリティ上の脆弱性を悪用Outlook。</span><span class="sxs-lookup"><span data-stu-id="2d810-404">This rule protects against social engineering attacks and prevents exploiting code from abusing vulnerabilities in Outlook.</span></span> <span data-ttu-id="2d810-405">また、ユーザーのOutlook[が](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/)侵害された場合に攻撃者が使用する可能性のある、特定のルールやフォームの悪用から保護します。</span><span class="sxs-lookup"><span data-stu-id="2d810-405">It also protects against [Outlook rules and forms exploits](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) that attackers can use when a user's credentials are compromised.</span></span>

> [!NOTE]
> <span data-ttu-id="2d810-406">このルールは、DLP ポリシー のヒントとツール ヒントをブロックOutlook。</span><span class="sxs-lookup"><span data-stu-id="2d810-406">This rule blocks DLP policy tips and ToolTips in Outlook.</span></span> <span data-ttu-id="2d810-407">このルールは、Outlookおよび Outlook.com にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2d810-407">This rule applies to Outlook and Outlook.com only.</span></span>

<span data-ttu-id="2d810-408">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2d810-408">This rule was introduced in:</span></span>

- [<span data-ttu-id="2d810-409">Windows 10 Version 1809</span><span class="sxs-lookup"><span data-stu-id="2d810-409">Windows 10, version 1809</span></span>](/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="2d810-410">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="2d810-410">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="2d810-411">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d810-411">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="2d810-412">Intune 名: `Process creation from Office communication products (beta)`</span><span class="sxs-lookup"><span data-stu-id="2d810-412">Intune name: `Process creation from Office communication products (beta)`</span></span>

<span data-ttu-id="2d810-413">Configuration Manager 名: 使用できません</span><span class="sxs-lookup"><span data-stu-id="2d810-413">Configuration Manager name: Not available</span></span>

<span data-ttu-id="2d810-414">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span><span class="sxs-lookup"><span data-stu-id="2d810-414">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span></span>

### <a name="block-persistence-through-wmi-event-subscription"></a><span data-ttu-id="2d810-415">WMI イベント サブスクリプションによる永続化のブロック</span><span class="sxs-lookup"><span data-stu-id="2d810-415">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="2d810-416">このルールは、デバイス上で WMI を攻撃して永続化を達成するマルウェアを防止します。</span><span class="sxs-lookup"><span data-stu-id="2d810-416">This rule prevents malware from abusing WMI to attain persistence on a device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d810-417">ファイルとフォルダーの除外は、この攻撃表面の縮小ルールには適用されません。</span><span class="sxs-lookup"><span data-stu-id="2d810-417">File and folder exclusions don't apply to this attack surface reduction rule.</span></span>

<span data-ttu-id="2d810-418">ファイルレスの脅威は、隠し、ファイル システムで見られない、定期的な実行制御を得るために、さまざまな戦術を採用しています。</span><span class="sxs-lookup"><span data-stu-id="2d810-418">Fileless threats employ various tactics to stay hidden, to avoid being seen in the file system, and to gain periodic execution control.</span></span> <span data-ttu-id="2d810-419">一部の脅威は、WMI リポジトリとイベント モデルを悪用して非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="2d810-419">Some threats can abuse the WMI repository and event model to stay hidden.</span></span>

<span data-ttu-id="2d810-420">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2d810-420">This rule was introduced in:</span></span>

- [<span data-ttu-id="2d810-421">Windows 10バージョン 1903</span><span class="sxs-lookup"><span data-stu-id="2d810-421">Windows 10, version 1903</span></span>](/windows/whats-new/whats-new-windows-10-version-1903)
- [<span data-ttu-id="2d810-422">Windowsサーバー 1903</span><span class="sxs-lookup"><span data-stu-id="2d810-422">Windows Server 1903</span></span>](/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

<span data-ttu-id="2d810-423">Intune 名: 使用できません</span><span class="sxs-lookup"><span data-stu-id="2d810-423">Intune name: Not available</span></span>

<span data-ttu-id="2d810-424">Configuration Manager 名: 使用できません</span><span class="sxs-lookup"><span data-stu-id="2d810-424">Configuration Manager name: Not available</span></span>

<span data-ttu-id="2d810-425">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span><span class="sxs-lookup"><span data-stu-id="2d810-425">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span></span>

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a><span data-ttu-id="2d810-426">PSExec および WMI コマンドから発生するプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-426">Block process creations originating from PSExec and WMI commands</span></span>

<span data-ttu-id="2d810-427">このルールは [、PsExec](/sysinternals/downloads/psexec) および WMI を介して作成 [されたプロセスの実行](/windows/win32/wmisdk/about-wmi) をブロックします。</span><span class="sxs-lookup"><span data-stu-id="2d810-427">This rule blocks processes created through [PsExec](/sysinternals/downloads/psexec) and [WMI](/windows/win32/wmisdk/about-wmi) from running.</span></span> <span data-ttu-id="2d810-428">PsExec と WMI の両方がコードをリモートで実行できるので、コマンドと制御の目的でこの機能を不正に使用したり、組織のネットワーク全体に感染を広げる危険性があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-428">Both PsExec and WMI can remotely execute code, so there is a risk of malware abusing this functionality for command and control purposes, or to spread an infection throughout an organization's network.</span></span>

> [!WARNING]
> <span data-ttu-id="2d810-429">Intune または別の MDM ソリューションを使用してデバイスを管理する場合にのみ、 [このルールを](/intune) 使用します。</span><span class="sxs-lookup"><span data-stu-id="2d810-429">Only use this rule if you're managing your devices with [Intune](/intune) or another MDM solution.</span></span> <span data-ttu-id="2d810-430">このルールは、Configuration Manager クライアント[が正しく機能するために使用Microsoft Endpoint Configuration Manager](/configmgr) WMI コマンドをブロックします。</span><span class="sxs-lookup"><span data-stu-id="2d810-430">This rule is incompatible with management through [Microsoft Endpoint Configuration Manager](/configmgr) because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span>

<span data-ttu-id="2d810-431">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2d810-431">This rule was introduced in:</span></span>

- [<span data-ttu-id="2d810-432">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="2d810-432">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="2d810-433">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="2d810-433">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="2d810-434">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d810-434">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="2d810-435">Intune 名: `Process creation from PSExec and WMI commands`</span><span class="sxs-lookup"><span data-stu-id="2d810-435">Intune name: `Process creation from PSExec and WMI commands`</span></span>

<span data-ttu-id="2d810-436">Configuration Manager 名: 該当なし</span><span class="sxs-lookup"><span data-stu-id="2d810-436">Configuration Manager name: Not applicable</span></span>

<span data-ttu-id="2d810-437">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span><span class="sxs-lookup"><span data-stu-id="2d810-437">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span></span>

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a><span data-ttu-id="2d810-438">USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="2d810-438">Block untrusted and unsigned processes that run from USB</span></span>

<span data-ttu-id="2d810-439">このルールを使用すると、管理者は、SD カードを含む USB リムーバブル ドライブから署名されていない実行可能ファイルまたは信頼されていない実行可能ファイルを実行できません。</span><span class="sxs-lookup"><span data-stu-id="2d810-439">With this rule, admins can prevent unsigned or untrusted executable files from running from USB removable drives, including SD cards.</span></span> <span data-ttu-id="2d810-440">ブロックされたファイルの種類には、実行可能ファイル (.exe、.dll.scr など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d810-440">Blocked file types include executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="2d810-441">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2d810-441">This rule was introduced in:</span></span>

- [<span data-ttu-id="2d810-442">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="2d810-442">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="2d810-443">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="2d810-443">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="2d810-444">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d810-444">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="2d810-445">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="2d810-445">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="2d810-446">Intune 名: `Untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="2d810-446">Intune name: `Untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="2d810-447">Configuration Manager 名: `Block untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="2d810-447">Configuration Manager name: `Block untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="2d810-448">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span><span class="sxs-lookup"><span data-stu-id="2d810-448">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span></span>

### <a name="block-win32-api-calls-from-office-macros"></a><span data-ttu-id="2d810-449">Win32 API 呼び出しをブロックOfficeマクロ</span><span class="sxs-lookup"><span data-stu-id="2d810-449">Block Win32 API calls from Office macros</span></span>

<span data-ttu-id="2d810-450">このルールは、VBA マクロが Win32 API を呼び出すのを防止します。</span><span class="sxs-lookup"><span data-stu-id="2d810-450">This rule prevents VBA macros from calling Win32 APIs.</span></span>

<span data-ttu-id="2d810-451">OfficeVBA では、Win32 API 呼び出しが有効です。</span><span class="sxs-lookup"><span data-stu-id="2d810-451">Office VBA enables Win32 API calls.</span></span> <span data-ttu-id="2d810-452">マルウェアは [、Win32 API](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) を呼び出してディスクに直接何も書き込みせずに悪意のあるシェルコードを起動するなど、この機能を悪用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-452">Malware can abuse this capability, such as [calling Win32 APIs to launch malicious shellcode](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) without writing anything directly to disk.</span></span> <span data-ttu-id="2d810-453">ほとんどの組織では、他の方法でマクロを使用している場合でも、Win32 API を毎日の機能で呼び出す機能に依存しません。</span><span class="sxs-lookup"><span data-stu-id="2d810-453">Most organizations don't rely on the ability to call Win32 APIs in their day-to-day functioning, even if they use macros in other ways.</span></span>

<span data-ttu-id="2d810-454">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2d810-454">This rule was introduced in:</span></span>

- [<span data-ttu-id="2d810-455">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="2d810-455">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="2d810-456">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="2d810-456">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="2d810-457">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d810-457">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="2d810-458">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="2d810-458">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="2d810-459">Intune 名: `Win32 imports from Office macro code`</span><span class="sxs-lookup"><span data-stu-id="2d810-459">Intune name: `Win32 imports from Office macro code`</span></span>

<span data-ttu-id="2d810-460">Configuration Manager 名: `Block Win32 API calls from Office macros`</span><span class="sxs-lookup"><span data-stu-id="2d810-460">Configuration Manager name: `Block Win32 API calls from Office macros`</span></span>

<span data-ttu-id="2d810-461">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span><span class="sxs-lookup"><span data-stu-id="2d810-461">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span></span>

### <a name="use-advanced-protection-against-ransomware"></a><span data-ttu-id="2d810-462">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="2d810-462">Use advanced protection against ransomware</span></span>

<span data-ttu-id="2d810-463">このルールは、ランサムウェアに対する保護の追加層を提供します。</span><span class="sxs-lookup"><span data-stu-id="2d810-463">This rule provides an extra layer of protection against ransomware.</span></span> <span data-ttu-id="2d810-464">クライアントとクラウドの両方のヒューリスティックを使用して、ファイルがランサムウェアに似ているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="2d810-464">It uses both client and cloud heuristics to determine whether a file resembles ransomware.</span></span> <span data-ttu-id="2d810-465">このルールは、次の 1 つ以上の特性を持つファイルをブロックしない。</span><span class="sxs-lookup"><span data-stu-id="2d810-465">This rule does not block files that have one or more of the following characteristics:</span></span>

- <span data-ttu-id="2d810-466">このファイルは、Microsoft クラウドで既に無傷である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-466">The file has already been found to be unharmful in the Microsoft cloud.</span></span>
- <span data-ttu-id="2d810-467">ファイルは有効な署名付きファイルです。</span><span class="sxs-lookup"><span data-stu-id="2d810-467">The file is a valid signed file.</span></span>
- <span data-ttu-id="2d810-468">ファイルはランサムウェアと見なされないほど普及しています。</span><span class="sxs-lookup"><span data-stu-id="2d810-468">The file is prevalent enough to not be considered as ransomware.</span></span>

<span data-ttu-id="2d810-469">このルールは、ランサムウェアを防止するために注意を払う傾向があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-469">The rule tends to err on the side of caution to prevent ransomware.</span></span>

> [!NOTE]
> <span data-ttu-id="2d810-470">このルールを [使用するには、クラウドによる保護](enable-cloud-protection-microsoft-defender-antivirus.md) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d810-470">You must [enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) to use this rule.</span></span>

<span data-ttu-id="2d810-471">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2d810-471">This rule was introduced in:</span></span>

- [<span data-ttu-id="2d810-472">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="2d810-472">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="2d810-473">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="2d810-473">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="2d810-474">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d810-474">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="2d810-475">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="2d810-475">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="2d810-476">Intune 名: `Advanced ransomware protection`</span><span class="sxs-lookup"><span data-stu-id="2d810-476">Intune name: `Advanced ransomware protection`</span></span>

<span data-ttu-id="2d810-477">Configuration Manager 名: `Use advanced protection against ransomware`</span><span class="sxs-lookup"><span data-stu-id="2d810-477">Configuration Manager name: `Use advanced protection against ransomware`</span></span>

<span data-ttu-id="2d810-478">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span><span class="sxs-lookup"><span data-stu-id="2d810-478">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span></span>
