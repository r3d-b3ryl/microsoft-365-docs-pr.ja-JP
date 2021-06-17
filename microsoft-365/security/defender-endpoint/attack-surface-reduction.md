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
ms.openlocfilehash: 409f6d0bbbcf9f8b50119e35bdb7852c4323bbf9
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984990"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a><span data-ttu-id="5e8e0-104">攻撃表面の縮小ルールを使用してマルウェアの感染を防止する</span><span class="sxs-lookup"><span data-stu-id="5e8e0-104">Use attack surface reduction rules to prevent malware infection</span></span>

<span data-ttu-id="5e8e0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5e8e0-105">**Applies to:**</span></span>

- [<span data-ttu-id="5e8e0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5e8e0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- [<span data-ttu-id="5e8e0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e8e0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a><span data-ttu-id="5e8e0-108">攻撃表面の縮小ルールが重要な理由</span><span class="sxs-lookup"><span data-stu-id="5e8e0-108">Why attack surface reduction rules are important</span></span>

<span data-ttu-id="5e8e0-109">組織の攻撃表面には、攻撃者が組織のデバイスやネットワークを侵害する可能性があるすべての場所が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-109">Your organization's attack surface includes all the places where an attacker could compromise your organization's devices or networks.</span></span> <span data-ttu-id="5e8e0-110">攻撃の表面を減らすことは、組織のデバイスとネットワークを保護する手段であり、攻撃者は攻撃を実行する方法が少なくなっています。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-110">Reducing your attack surface means protecting your organization's devices and network, which leaves attackers with fewer ways to perform attacks.</span></span> <span data-ttu-id="5e8e0-111">Microsoft Defender for Endpoint で攻撃表面の縮小ルールを構成すると役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-111">Configuring attack surface reduction rules in Microsoft Defender for Endpoint can help!</span></span>

<span data-ttu-id="5e8e0-112">攻撃表面の縮小ルールは、次のような特定のソフトウェア動作を対象とします。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-112">Attack surface reduction rules target certain software behaviors, such as:</span></span>

- <span data-ttu-id="5e8e0-113">ファイルのダウンロードまたは実行を試みる実行可能ファイルとスクリプトの起動</span><span class="sxs-lookup"><span data-stu-id="5e8e0-113">Launching executable files and scripts that attempt to download or run files</span></span>
- <span data-ttu-id="5e8e0-114">難読化されたスクリプトまたはその他の疑わしいスクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="5e8e0-114">Running obfuscated or otherwise suspicious scripts</span></span>
- <span data-ttu-id="5e8e0-115">通常の毎日の作業中にアプリが通常開始しない動作を実行する</span><span class="sxs-lookup"><span data-stu-id="5e8e0-115">Performing behaviors that apps don't usually initiate during normal day-to-day work</span></span>

<span data-ttu-id="5e8e0-116">このようなソフトウェアの動作は、正当なアプリケーションで見られる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-116">Such software behaviors are sometimes seen in legitimate applications.</span></span> <span data-ttu-id="5e8e0-117">ただし、これらの動作は、マルウェアを介して攻撃者によって悪用されるのが一般的なので、リスクが高いと見なされる場合が多い。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-117">However, these behaviors are often considered risky because they are commonly abused by attackers through malware.</span></span> <span data-ttu-id="5e8e0-118">攻撃表面の縮小ルールは、ソフトウェア ベースのリスクの高い動作を制限し、組織の安全を維持するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-118">Attack surface reduction rules can constrain software-based risky behaviors and help keep your organization safe.</span></span>

<span data-ttu-id="5e8e0-119">攻撃表面の縮小ルールの構成の詳細については、「攻撃表面の縮小ルールを有効 [にする」を参照してください](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-119">For more information about configuring attack surface reduction rules, see [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

## <a name="assess-rule-impact-before-deployment"></a><span data-ttu-id="5e8e0-120">展開前にルールへの影響を評価する</span><span class="sxs-lookup"><span data-stu-id="5e8e0-120">Assess rule impact before deployment</span></span>

<span data-ttu-id="5e8e0-121">攻撃表面の縮小ルールがネットワークに与える影響を評価するには、このルールのセキュリティに関する推奨事項を [脅威と脆弱性の管理][で開きます](/windows/security/threat-protection/#tvm)。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-121">You can assess how an attack surface reduction rule might affect your network by opening the security recommendation for that rule in [threat and vulnerability management](/windows/security/threat-protection/#tvm).</span></span>

:::image type="content" source="images/asrrecommendation.png" alt-text="攻撃表面の縮小ルールのセキュリティ reco":::

<span data-ttu-id="5e8e0-123">[推奨事項の詳細] ウィンドウで、ユーザーの影響を確認して、生産性に悪影響を及ぼさずに、ブロック モードでルールを有効にする新しいポリシーを受け入れ可能なデバイスの割合を確認します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-123">In the recommendation details pane, check for user impact to determine what percentage of your devices can accept a new policy enabling the rule in blocking mode without adversely affecting productivity.</span></span>

## <a name="audit-mode-for-evaluation"></a><span data-ttu-id="5e8e0-124">評価の監査モード</span><span class="sxs-lookup"><span data-stu-id="5e8e0-124">Audit mode for evaluation</span></span>

<span data-ttu-id="5e8e0-125">監査 [モードを使用して](audit-windows-defender.md) 、攻撃表面の縮小ルールが有効な場合に組織に与える影響を評価します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-125">Use [audit mode](audit-windows-defender.md) to evaluate how attack surface reduction rules would affect your organization if enabled.</span></span> <span data-ttu-id="5e8e0-126">監査モードですべてのルールを最初に実行して、そのルールがビジネスライン アプリケーションに与える影響を理解できます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-126">Run all rules in audit mode first so you can understand how they affect your line-of-business applications.</span></span> <span data-ttu-id="5e8e0-127">多くの業務用アプリケーションは、限られたセキュリティ上の懸念を持って記述され、マルウェアに似た方法でタスクを実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-127">Many line-of-business applications are written with limited security concerns, and they might perform tasks in ways that seem similar to malware.</span></span> <span data-ttu-id="5e8e0-128">監査データを監視し、必要なアプリケーションの [除外](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) を追加することで、生産性を低下させずに攻撃表面の縮小ルールを展開できます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-128">By monitoring audit data and [adding exclusions](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) for necessary applications, you can deploy attack surface reduction rules without reducing productivity.</span></span>

## <a name="warn-mode-for-users"></a><span data-ttu-id="5e8e0-129">ユーザーの警告モード</span><span class="sxs-lookup"><span data-stu-id="5e8e0-129">Warn mode for users</span></span>

<span data-ttu-id="5e8e0-130">(**NEW**!)警告モード機能の前に、有効になっている攻撃表面の縮小ルールを監査モードまたはブロック モードに設定できます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-130">(**NEW**!) Prior to warn mode capabilities, attack surface reduction rules that are enabled could be set to either audit mode or block mode.</span></span> <span data-ttu-id="5e8e0-131">新しい警告モードでは、攻撃表面の縮小ルールによってコンテンツがブロックされるたびに、コンテンツがブロックされたかどうかを示すダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-131">With the new warn mode, whenever content is blocked by an attack surface reduction rule, users see a dialog box that indicates the content is blocked.</span></span> <span data-ttu-id="5e8e0-132">ダイアログ ボックスには、コンテンツのブロックを解除するオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-132">The dialog box also offers the user an option to unblock the content.</span></span> <span data-ttu-id="5e8e0-133">その後、ユーザーはアクションを再試行し、操作が完了します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-133">The user can then retry their action, and the operation completes.</span></span> <span data-ttu-id="5e8e0-134">ユーザーがコンテンツのブロックを解除すると、コンテンツは 24 時間ブロック解除されたままで、その後ブロックが再開されます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-134">When a user unblocks content, the content remains unblocked for 24 hours, and then blocking resumes.</span></span>

<span data-ttu-id="5e8e0-135">警告モードは、ユーザーが自分のタスクを実行するために必要なコンテンツにアクセスするのを防ぐことなく、組織が攻撃表面の縮小ルールを設定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-135">Warn mode helps your organization have attack surface reduction rules in place without preventing users from accessing the content they need to perform their tasks.</span></span>

### <a name="requirements-for-warn-mode-to-work"></a><span data-ttu-id="5e8e0-136">警告モードが機能する要件</span><span class="sxs-lookup"><span data-stu-id="5e8e0-136">Requirements for warn mode to work</span></span>

<span data-ttu-id="5e8e0-137">警告モードは、次のバージョンの警告を実行しているデバイスWindows。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-137">Warn mode is supported on devices running the following versions of Windows:</span></span>

- <span data-ttu-id="5e8e0-138">[Windows 10 Version 1809](/windows/whats-new/whats-new-windows-10-version-1809)以降</span><span class="sxs-lookup"><span data-stu-id="5e8e0-138">[Windows 10, version 1809](/windows/whats-new/whats-new-windows-10-version-1809) or later</span></span>
- <span data-ttu-id="5e8e0-139">[Windows Server バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)以降</span><span class="sxs-lookup"><span data-stu-id="5e8e0-139">[Windows Server, version 1809](/windows-server/get-started/whats-new-in-windows-server-1809) or later</span></span>

<span data-ttu-id="5e8e0-140">Microsoft Defender ウイルス対策モードでリアルタイム保護を実行している[必要があります](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-140">Microsoft Defender Antivirus must be running with real-time protection in [Active mode](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state).</span></span>

<span data-ttu-id="5e8e0-141">さらに、マルウェア対策[Microsoft Defender ウイルス対策更新プログラムがインストールされていることを](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)確認します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-141">In addition, make sure [Microsoft Defender Antivirus and antimalware updates](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) are installed.</span></span>

- <span data-ttu-id="5e8e0-142">プラットフォームリリースの最小要件: `4.18.2008.9`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-142">Minimum platform release requirement: `4.18.2008.9`</span></span>
- <span data-ttu-id="5e8e0-143">エンジンリリースの最小要件: `1.1.17400.5`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-143">Minimum engine release requirement: `1.1.17400.5`</span></span>

<span data-ttu-id="5e8e0-144">詳細と更新プログラムの取得については [、「Update for Microsoft Defender マルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-144">For more information and to get your updates, see [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).</span></span>

### <a name="cases-where-warn-mode-is-not-supported"></a><span data-ttu-id="5e8e0-145">警告モードがサポートされていない場合</span><span class="sxs-lookup"><span data-stu-id="5e8e0-145">Cases where warn mode is not supported</span></span>

<span data-ttu-id="5e8e0-146">警告モードは、3 つの攻撃表面の縮小ルールを構成するときにサポートMicrosoft エンドポイント マネージャー。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-146">Warn mode is not supported for three attack surface reduction rules when you configure them in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="5e8e0-147">(グループ ポリシーを使用して攻撃表面の縮小ルールを構成する場合は、警告モードがサポートされます)。警告モードを構成するときに警告モードをサポートしない 3 つのMicrosoft エンドポイント マネージャーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-147">(If you use Group Policy to configure your attack surface reduction rules, warn mode is supported.) The three rules that do not support warn mode when you configure them in Microsoft Endpoint Manager are as follows:</span></span>

- <span data-ttu-id="5e8e0-148">[ダウンロードした実行可能コンテンツ (GUID)](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)の起動から JavaScript または VBScript をブロックする `d3e037e1-3eb8-44c8-a917-57927947596d`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-148">[Block JavaScript or VBScript from launching downloaded executable content](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`)</span></span>
- <span data-ttu-id="5e8e0-149">[WMI イベント サブスクリプション (GUID) による永続](#block-persistence-through-wmi-event-subscription) 化をブロック `e6db77e5-3df2-4cf1-b95a-636979351e5b` する</span><span class="sxs-lookup"><span data-stu-id="5e8e0-149">[Block persistence through WMI event subscription](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`)</span></span>
- <span data-ttu-id="5e8e0-150">[ランサムウェアに対する高度な保護を使用](#use-advanced-protection-against-ransomware) する `c1db55ab-c21a-4637-bb3f-a12568109d35` (GUID)</span><span class="sxs-lookup"><span data-stu-id="5e8e0-150">[Use advanced protection against ransomware](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`)</span></span>

<span data-ttu-id="5e8e0-151">さらに、以前のバージョンのバージョンのデバイスで警告モードはサポートWindows。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-151">In addition, warn mode is not supported on devices running older versions of Windows.</span></span> <span data-ttu-id="5e8e0-152">このような場合、警告モードで実行するように構成された攻撃表面の縮小ルールは、ブロック モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-152">In those cases, attack surface reduction rules that are configured to run in warn mode will run in block mode.</span></span>

## <a name="notifications-and-alerts"></a><span data-ttu-id="5e8e0-153">通知とアラート</span><span class="sxs-lookup"><span data-stu-id="5e8e0-153">Notifications and alerts</span></span>

<span data-ttu-id="5e8e0-154">攻撃表面の縮小ルールがトリガーされるたびに、デバイスに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-154">Whenever an attack surface reduction rule is triggered, a notification is displayed on the device.</span></span> <span data-ttu-id="5e8e0-155">会社の詳細や連絡先情報を使用して[通知をカスタマイズ](customize-attack-surface-reduction.md#customize-the-notification)することができます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-155">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span>

<span data-ttu-id="5e8e0-156">さらに、特定の攻撃表面の縮小ルールがトリガーされると、アラートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-156">In addition, when certain attack surface reduction rules are triggered, alerts are generated.</span></span>

<span data-ttu-id="5e8e0-157">通知と生成されたアラートは、Microsoft 365 Defender ポータル ( ) (以前は [https://security.microsoft.com](https://security.microsoft.com) Microsoft Defender セキュリティ センター)[で表示できます](microsoft-defender-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-157">Notifications and any alerts that are generated can be viewed in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) (formerly called the [Microsoft Defender Security Center](microsoft-defender-security-center.md)).</span></span>

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a><span data-ttu-id="5e8e0-158">高度な狩猟と攻撃表面の縮小イベント</span><span class="sxs-lookup"><span data-stu-id="5e8e0-158">Advanced hunting and attack surface reduction events</span></span>

<span data-ttu-id="5e8e0-159">高度な検索を使用して、攻撃表面の縮小イベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-159">You can use advanced hunting to view attack surface reduction events.</span></span> <span data-ttu-id="5e8e0-160">受信データの量を合理化するために、高度な検索では、1 時間ごとに一意のプロセスのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-160">To streamline the volume of incoming data, only unique processes for each hour are viewable with advanced hunting.</span></span> <span data-ttu-id="5e8e0-161">攻撃表面の縮小イベントの時間は、1 時間以内に初めてイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-161">The time of an attack surface reduction event is the first time that event is seen within the hour.</span></span>

<span data-ttu-id="5e8e0-162">たとえば、午後 2 時の間に 10 台のデバイスで攻撃表面の縮小イベントが発生するとします。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-162">For example, suppose that an attack surface reduction event occurs on 10 devices during the 2:00 PM hour.</span></span> <span data-ttu-id="5e8e0-163">最初のイベントが 2:15、最後の 2:45 に発生したとします。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-163">Suppose that the first event occurred at 2:15, and the last at 2:45.</span></span> <span data-ttu-id="5e8e0-164">高度な検索では、そのイベントのインスタンスが 1 つ表示されます (実際には 10 台のデバイスで発生した場合でも)、タイムスタンプは午後 2 時 15 分になります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-164">With advanced hunting, you'll see one instance of that event (even though it actually occurred on 10 devices), and its timestamp will be 2:15 PM.</span></span>

<span data-ttu-id="5e8e0-165">高度な狩猟の詳細については、「高度な狩猟 [を使用して脅威を事前に検出する」を参照してください](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-165">For more information about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="attack-surface-reduction-features-across-windows-versions"></a><span data-ttu-id="5e8e0-166">複数のバージョンの攻撃表面Windows機能</span><span class="sxs-lookup"><span data-stu-id="5e8e0-166">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="5e8e0-167">次のエディションとバージョンのデバイスを実行しているデバイスに対して攻撃表面の縮小ルールをWindows。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-167">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="5e8e0-168">Windows 10 Proバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="5e8e0-168">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="5e8e0-169">Windows 10 Enterpriseバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="5e8e0-169">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="5e8e0-170">Windowsサーバー、[バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803)以降</span><span class="sxs-lookup"><span data-stu-id="5e8e0-170">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="5e8e0-171">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e8e0-171">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="5e8e0-172">攻撃表面の縮小ルールでは[E5](/windows/deployment/deploy-enterprise-licenses)ライセンスをWindows必要とWindows、高度な管理機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-172">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="5e8e0-173">E5 でのみ使用できる高度な機能はWindows含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-173">The advanced capabilities - available only in Windows E5 - include:</span></span>

- <span data-ttu-id="5e8e0-174">Defender for Endpoint で利用できる監視、分析、 [およびワークフロー](microsoft-defender-endpoint.md)</span><span class="sxs-lookup"><span data-stu-id="5e8e0-174">The monitoring, analytics, and workflows available in [Defender for Endpoint](microsoft-defender-endpoint.md)</span></span>
- <span data-ttu-id="5e8e0-175">レポート機能と構成機能は[、Microsoft 365 Defender。](/microsoft-365/security/defender/overview-security-center)</span><span class="sxs-lookup"><span data-stu-id="5e8e0-175">The reporting and configuration capabilities in [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="5e8e0-176">これらの高度な機能は、E3 ライセンスWindows ProfessionalまたはWindows使用できません。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-176">These advanced capabilities aren't available with a Windows Professional or Windows E3 license.</span></span> <span data-ttu-id="5e8e0-177">ただし、これらのライセンスがある場合は、イベント ビューアーとログMicrosoft Defender ウイルス対策を使用して、攻撃表面の縮小ルール イベントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-177">However, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="5e8e0-178">ポータルで攻撃表面の縮小イベントをMicrosoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-178">Review attack surface reduction events in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="5e8e0-179">Defender for Endpoint は、アラート調査シナリオの一環として、イベントとブロックの詳細なレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-179">Defender for Endpoint provides detailed reporting for events and blocks as part of alert investigation scenarios.</span></span>

<span data-ttu-id="5e8e0-180">高度な検索を使用して、Microsoft 365 Defender Defender [for](microsoft-defender-security-center.md) Endpoint データ[をクエリできます](advanced-hunting-query-language.md)。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-180">You can query Defender for Endpoint data in [Microsoft 365 Defender](microsoft-defender-security-center.md) by using [advanced hunting](advanced-hunting-query-language.md).</span></span> <span data-ttu-id="5e8e0-181">監査モードを実行している [場合](audit-windows-defender.md)は、高度な検索を使用して、攻撃表面の縮小ルールが環境に与える影響を理解できます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-181">If you're running [audit mode](audit-windows-defender.md), you can use advanced hunting to understand how attack surface reduction rules might affect your environment.</span></span>

<span data-ttu-id="5e8e0-182">クエリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-182">Here is an example query:</span></span>

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="5e8e0-183">イベント ビューアーで攻撃表面の縮小イベントWindows確認する</span><span class="sxs-lookup"><span data-stu-id="5e8e0-183">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="5e8e0-184">次のイベント ログをWindowsして、攻撃表面の縮小ルールによって生成されたイベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-184">You can review the Windows event log to view events generated by attack surface reduction rules:</span></span>

1. <span data-ttu-id="5e8e0-185">評価パッケージ [をダウンロードし](https://aka.ms/mp7z2w) 、デバイス上 *cfa-events.xmlアクセスしやすい* 場所にファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-185">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>

2. <span data-ttu-id="5e8e0-186">[イベント ビューアー] という *単語* を入力して、スタート メニューを開Windowsします。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-186">Enter the words, *Event Viewer*, into the Start menu to open the Windows Event Viewer.</span></span>

3. <span data-ttu-id="5e8e0-187">[アクション **] で**、[カスタム **ビューのインポート.... を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-187">Under **Actions**, select **Import custom view...**.</span></span>

4. <span data-ttu-id="5e8e0-188">抽出された場所 *cfa-events.xml* ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-188">Select the file *cfa-events.xml* from where it was extracted.</span></span> <span data-ttu-id="5e8e0-189">または [、XML を直接コピーします](event-views.md)。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-189">Alternatively, [copy the XML directly](event-views.md).</span></span>

5. <span data-ttu-id="5e8e0-190">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-190">Select **OK**.</span></span>

<span data-ttu-id="5e8e0-191">イベントをフィルター処理して、次のイベントのみを表示するカスタム ビューを作成できます。そのすべては、フォルダー アクセスの制御に関連しています。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-191">You can create a custom view that filters events to only show the following events, all of which are related to controlled folder access:</span></span>

|<span data-ttu-id="5e8e0-192">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5e8e0-192">Event ID</span></span>|<span data-ttu-id="5e8e0-193">説明</span><span class="sxs-lookup"><span data-stu-id="5e8e0-193">Description</span></span>|
|---|---|
|<span data-ttu-id="5e8e0-194">5007</span><span class="sxs-lookup"><span data-stu-id="5e8e0-194">5007</span></span>|<span data-ttu-id="5e8e0-195">設定が変更された場合のイベント</span><span class="sxs-lookup"><span data-stu-id="5e8e0-195">Event when settings are changed</span></span>|
|<span data-ttu-id="5e8e0-196">1121</span><span class="sxs-lookup"><span data-stu-id="5e8e0-196">1121</span></span>|<span data-ttu-id="5e8e0-197">ブロック モードでルールが発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="5e8e0-197">Event when rule fires in Block-mode</span></span>|
|<span data-ttu-id="5e8e0-198">1122</span><span class="sxs-lookup"><span data-stu-id="5e8e0-198">1122</span></span>|<span data-ttu-id="5e8e0-199">監査モードでルールが発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="5e8e0-199">Event when rule fires in Audit-mode</span></span>|

<span data-ttu-id="5e8e0-200">イベント ログの攻撃表面の縮小イベント用にリストされている "エンジンバージョン" は、オペレーティング システムではなく Defender for Endpoint によって生成されます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-200">The "engine version" listed for attack surface reduction events in the event log, is generated by Defender for Endpoint, not by the operating system.</span></span> <span data-ttu-id="5e8e0-201">Defender for Endpoint は、Windows 10と統合されています。そのため、この機能は、インストールされているすべてのデバイスWindows 10します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-201">Defender for Endpoint is integrated with Windows 10, so this feature works on all devices with Windows 10 installed.</span></span>

## <a name="attack-surface-reduction-rules"></a><span data-ttu-id="5e8e0-202">攻撃面の減少ルール</span><span class="sxs-lookup"><span data-stu-id="5e8e0-202">Attack surface reduction rules</span></span>

<span data-ttu-id="5e8e0-203">次の表とサブセクションでは、15 の攻撃表面の縮小ルールのそれぞれについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-203">The following table and subsections describe each of the 15 attack surface reduction rules.</span></span> <span data-ttu-id="5e8e0-204">攻撃表面の縮小ルールは、ルール名によってアルファベット順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-204">The attack surface reduction rules are listed in alphabetical order, by rule name.</span></span>

<span data-ttu-id="5e8e0-205">グループ ポリシーまたは PowerShell を使用して攻撃表面の縮小ルールを構成する場合は、GUID が必要です。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-205">If you are configuring attack surface reduction rules by using Group Policy or PowerShell, you'll need the GUIDs.</span></span> <span data-ttu-id="5e8e0-206">一方、ユーザー設定またはMicrosoft エンドポイント マネージャーをMicrosoft Intune GUID は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-206">On the other hand, if you use Microsoft Endpoint Manager or Microsoft Intune, you do not need the GUIDs.</span></span>

|<span data-ttu-id="5e8e0-207">ルールの名前</span><span class="sxs-lookup"><span data-stu-id="5e8e0-207">Rule name</span></span>|<span data-ttu-id="5e8e0-208">GUID</span><span class="sxs-lookup"><span data-stu-id="5e8e0-208">GUID</span></span>|<span data-ttu-id="5e8e0-209">ファイル&フォルダーの除外</span><span class="sxs-lookup"><span data-stu-id="5e8e0-209">File & folder exclusions</span></span>|<span data-ttu-id="5e8e0-210">サポートされる最小 OS</span><span class="sxs-lookup"><span data-stu-id="5e8e0-210">Minimum OS supported</span></span>|
|---|:---:|---|---|
|[<span data-ttu-id="5e8e0-211">悪用された脆弱な署名済みドライバーの悪用をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-211">Block abuse of exploited vulnerable signed drivers</span></span>](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|<span data-ttu-id="5e8e0-212">サポート済み</span><span class="sxs-lookup"><span data-stu-id="5e8e0-212">Supported</span></span>|<span data-ttu-id="5e8e0-213">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上)</span><span class="sxs-lookup"><span data-stu-id="5e8e0-213">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater)</span></span> |
|[<span data-ttu-id="5e8e0-214">Adobe Reader の子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-214">Block Adobe Reader from creating child processes</span></span>](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|<span data-ttu-id="5e8e0-215">サポート済み</span><span class="sxs-lookup"><span data-stu-id="5e8e0-215">Supported</span></span>|<span data-ttu-id="5e8e0-216">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="5e8e0-216">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="5e8e0-217">すべてのアプリケーションOffice子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-217">Block all Office applications from creating child processes</span></span>](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|<span data-ttu-id="5e8e0-218">サポート済み</span><span class="sxs-lookup"><span data-stu-id="5e8e0-218">Supported</span></span>|<span data-ttu-id="5e8e0-219">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="5e8e0-219">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="5e8e0-220">ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="5e8e0-220">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|<span data-ttu-id="5e8e0-221">サポート済み</span><span class="sxs-lookup"><span data-stu-id="5e8e0-221">Supported</span></span>|<span data-ttu-id="5e8e0-222">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="5e8e0-222">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="5e8e0-223">メール クライアントと Web メールから実行可能なコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-223">Block executable content from email client and webmail</span></span>](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|<span data-ttu-id="5e8e0-224">サポート済み</span><span class="sxs-lookup"><span data-stu-id="5e8e0-224">Supported</span></span>|<span data-ttu-id="5e8e0-225">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="5e8e0-225">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="5e8e0-226">有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-226">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|<span data-ttu-id="5e8e0-227">サポート済み</span><span class="sxs-lookup"><span data-stu-id="5e8e0-227">Supported</span></span>|<span data-ttu-id="5e8e0-228">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="5e8e0-228">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="5e8e0-229">難読化される可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-229">Block execution of potentially obfuscated scripts</span></span>](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|<span data-ttu-id="5e8e0-230">サポート済み</span><span class="sxs-lookup"><span data-stu-id="5e8e0-230">Supported</span></span>|<span data-ttu-id="5e8e0-231">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="5e8e0-231">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="5e8e0-232">JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-232">Block JavaScript or VBScript from launching downloaded executable content</span></span>](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|<span data-ttu-id="5e8e0-233">サポート済み</span><span class="sxs-lookup"><span data-stu-id="5e8e0-233">Supported</span></span>|<span data-ttu-id="5e8e0-234">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="5e8e0-234">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="5e8e0-235">実行可能Office作成するアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="5e8e0-235">Block Office applications from creating executable content</span></span>](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|<span data-ttu-id="5e8e0-236">サポート済み</span><span class="sxs-lookup"><span data-stu-id="5e8e0-236">Supported</span></span>|<span data-ttu-id="5e8e0-237">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="5e8e0-237">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="5e8e0-238">アプリケーションOffice他のプロセスへのコードの挿入をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-238">Block Office applications from injecting code into other processes</span></span>](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|<span data-ttu-id="5e8e0-239">サポート済み</span><span class="sxs-lookup"><span data-stu-id="5e8e0-239">Supported</span></span>|<span data-ttu-id="5e8e0-240">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="5e8e0-240">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="5e8e0-241">通信Officeプロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-241">Block Office communication application from creating child processes</span></span>](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|<span data-ttu-id="5e8e0-242">サポート済み</span><span class="sxs-lookup"><span data-stu-id="5e8e0-242">Supported</span></span>|<span data-ttu-id="5e8e0-243">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="5e8e0-243">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="5e8e0-244">WMI イベント サブスクリプションによる永続化のブロック</span><span class="sxs-lookup"><span data-stu-id="5e8e0-244">Block persistence through WMI event subscription</span></span>](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|<span data-ttu-id="5e8e0-245">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="5e8e0-245">Not supported</span></span>|<span data-ttu-id="5e8e0-246">[Windows 10バージョン 1903](/windows/whats-new/whats-new-windows-10-version-1903) (ビルド 18362) 以上</span><span class="sxs-lookup"><span data-stu-id="5e8e0-246">[Windows 10, version 1903](/windows/whats-new/whats-new-windows-10-version-1903) (build 18362) or greater</span></span>|
|[<span data-ttu-id="5e8e0-247">PSExec および WMI コマンドから発生するプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-247">Block process creations originating from PSExec and WMI commands</span></span>](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|<span data-ttu-id="5e8e0-248">サポート済み</span><span class="sxs-lookup"><span data-stu-id="5e8e0-248">Supported</span></span>|<span data-ttu-id="5e8e0-249">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="5e8e0-249">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="5e8e0-250">USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-250">Block untrusted and unsigned processes that run from USB</span></span>](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|<span data-ttu-id="5e8e0-251">サポート済み</span><span class="sxs-lookup"><span data-stu-id="5e8e0-251">Supported</span></span>|<span data-ttu-id="5e8e0-252">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="5e8e0-252">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="5e8e0-253">Win32 API 呼び出しをブロックOfficeマクロ</span><span class="sxs-lookup"><span data-stu-id="5e8e0-253">Block Win32 API calls from Office macros</span></span>](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|<span data-ttu-id="5e8e0-254">サポート済み</span><span class="sxs-lookup"><span data-stu-id="5e8e0-254">Supported</span></span>|<span data-ttu-id="5e8e0-255">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="5e8e0-255">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="5e8e0-256">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="5e8e0-256">Use advanced protection against ransomware</span></span>](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|<span data-ttu-id="5e8e0-257">サポート済み</span><span class="sxs-lookup"><span data-stu-id="5e8e0-257">Supported</span></span>|<span data-ttu-id="5e8e0-258">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="5e8e0-258">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a><span data-ttu-id="5e8e0-259">悪用された脆弱な署名済みドライバーの悪用をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-259">Block abuse of exploited vulnerable signed drivers</span></span>

<span data-ttu-id="5e8e0-260">このルールは、アプリケーションが脆弱な署名済みドライバーをディスクに書き込むのを防ぐためです。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-260">This rule prevents an application from writing a vulnerable signed driver to disk.</span></span> <span data-ttu-id="5e8e0-261">インザワイルドで脆弱な署名済みドライバーは、カーネルにアクセスするのに十分な特権を持つローカル アプリケーション \-  \- によって悪用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-261">In-the-wild, vulnerable signed drivers can be exploited by local applications \- _that have sufficient privileges_ \- to gain access to the kernel.</span></span> <span data-ttu-id="5e8e0-262">脆弱な署名付きドライバーを使用すると、攻撃者はセキュリティ ソリューションを無効または回避し、最終的にはシステムの侵害につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-262">Vulnerable signed drivers enable attackers to disable or circumvent security solutions, eventually leading to system compromise.</span></span>

<span data-ttu-id="5e8e0-263">[ **悪用された脆弱な** 署名済みドライバーの悪用をブロックする] ルールは、システム上に既に存在するドライバーの読み込みをブロックしない。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-263">The **Block abuse of exploited vulnerable signed drivers** rule does not block a driver already existing on the system from being loaded.</span></span>

>[!NOTE]
>
> <span data-ttu-id="5e8e0-264">このルールは [、MEM OMA-URI](enable-attack-surface-reduction.md#mem) カスタム ルールのプロシージャ情報に対して MEM OMA-URI を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-264">You can configure this rule using [MEM OMA-URI](enable-attack-surface-reduction.md#mem) for MEM OMA-URI custom rules procedural information.</span></span>
>
> <span data-ttu-id="5e8e0-265">PowerShell を使用してこのルールを [構成できます](enable-attack-surface-reduction.md#powershell)。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-265">You can also configure this rule using [PowerShell](enable-attack-surface-reduction.md#powershell).</span></span>
>
> <span data-ttu-id="5e8e0-266">ドライバーを調べるには、この Web サイトを使用して分析 [用のドライバーを送信します](https://www.microsoft.com/en-us/wdsi/driversubmission)。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-266">To have a driver examined, use this Web site to [Submit a driver for analysis](https://www.microsoft.com/en-us/wdsi/driversubmission).</span></span>

<span data-ttu-id="5e8e0-267">このルールは、ASR がサポートされているすべてのバージョンでサポートされます。これは次の場合です。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-267">This rule is supported in all versions in which ASR is supported; which is:</span></span>

- <span data-ttu-id="5e8e0-268">[Windows 10 Proバージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="5e8e0-268">[Windows 10 Pro, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="5e8e0-269">[Windows 10 Enterpriseバージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="5e8e0-269">[Windows 10 Enterprise, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="5e8e0-270">[Windows Server バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803)以降</span><span class="sxs-lookup"><span data-stu-id="5e8e0-270">[Windows Server, version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="5e8e0-271">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e8e0-271">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="5e8e0-272">Intune 名: `Block abuse of exploited vulnerable signed drivers`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-272">Intune Name: `Block abuse of exploited vulnerable signed drivers`</span></span>

<span data-ttu-id="5e8e0-273">GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-273">GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span></span>

### <a name="block-adobe-reader-from-creating-child-processes"></a><span data-ttu-id="5e8e0-274">Adobe Reader の子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-274">Block Adobe Reader from creating child processes</span></span>

<span data-ttu-id="5e8e0-275">このルールは、Adobe Reader によるプロセスの作成をブロックすることで攻撃を防止します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-275">This rule prevents attacks by blocking Adobe Reader from creating processes.</span></span>

<span data-ttu-id="5e8e0-276">ソーシャル エンジニアリングや悪用を通じて、マルウェアはペイロードをダウンロードして起動し、Adobe Reader から抜け出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-276">Through social engineering or exploits, malware can download and launch payloads, and break out of Adobe Reader.</span></span> <span data-ttu-id="5e8e0-277">Adobe Reader によって子プロセスが生成されるのをブロックすることで、子プロセスをベクターとして使用しようとするマルウェアが拡散を防止します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-277">By blocking child processes from being generated by Adobe Reader, malware attempting to use it as a vector are prevented from spreading.</span></span>

<span data-ttu-id="5e8e0-278">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-278">This rule was introduced in:</span></span>

- [<span data-ttu-id="5e8e0-279">Windows 10 Version 1809</span><span class="sxs-lookup"><span data-stu-id="5e8e0-279">Windows 10, version 1809</span></span>](/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="5e8e0-280">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="5e8e0-280">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="5e8e0-281">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e8e0-281">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="5e8e0-282">Intune 名: `Process creation from Adobe Reader (beta)`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-282">Intune name: `Process creation from Adobe Reader (beta)`</span></span>

<span data-ttu-id="5e8e0-283">Configuration Manager 名: まだ使用できません</span><span class="sxs-lookup"><span data-stu-id="5e8e0-283">Configuration Manager name: Not yet available</span></span>

<span data-ttu-id="5e8e0-284">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-284">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span></span>

### <a name="block-all-office-applications-from-creating-child-processes"></a><span data-ttu-id="5e8e0-285">すべてのアプリケーションOffice子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-285">Block all Office applications from creating child processes</span></span>

<span data-ttu-id="5e8e0-286">このルールは、Officeプロセスの作成をブロックします。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-286">This rule blocks Office apps from creating child processes.</span></span> <span data-ttu-id="5e8e0-287">Officeには、Word、Excel、PowerPoint、OneNote、Access が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-287">Office apps include Word, Excel, PowerPoint, OneNote, and Access.</span></span>

<span data-ttu-id="5e8e0-288">悪意のある子プロセスを作成する方法は、一般的なマルウェア戦略です。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-288">Creating malicious child processes is a common malware strategy.</span></span> <span data-ttu-id="5e8e0-289">マルウェアがベクターとしてOffice、VBA マクロを実行し、コードを悪用して、より多くのペイロードをダウンロードして実行しようとする場合があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-289">Malware that abuse Office as a vector often run VBA macros and exploit code to download and attempt to run more payloads.</span></span> <span data-ttu-id="5e8e0-290">ただし、一部の正当な業務行アプリケーションでは、良性の目的で子プロセスを生成する場合があります。コマンド プロンプトを生成したり、PowerShell を使用してレジストリ設定を構成したりします。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-290">However, some legitimate line-of-business applications might also generate child processes for benign purposes; such as spawning a command prompt or using PowerShell to configure registry settings.</span></span>

<span data-ttu-id="5e8e0-291">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-291">This rule was introduced in:</span></span>

- [<span data-ttu-id="5e8e0-292">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="5e8e0-292">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="5e8e0-293">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="5e8e0-293">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="5e8e0-294">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e8e0-294">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="5e8e0-295">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="5e8e0-295">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="5e8e0-296">Intune 名: `Office apps launching child processes`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-296">Intune name: `Office apps launching child processes`</span></span>

<span data-ttu-id="5e8e0-297">Configuration Manager 名: `Block Office application from creating child processes`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-297">Configuration Manager name: `Block Office application from creating child processes`</span></span>

<span data-ttu-id="5e8e0-298">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-298">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span></span>

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a><span data-ttu-id="5e8e0-299">ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-299">Block credential stealing from the Windows local security authority subsystem</span></span>

<span data-ttu-id="5e8e0-300">このルールは、ローカル セキュリティ機関サブシステム サービス (LSASS) をロックダウンして資格情報の盗用を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-300">This rule helps prevent credential stealing by locking down Local Security Authority Subsystem Service (LSASS).</span></span>

<span data-ttu-id="5e8e0-301">LSASS は、コンピューターにサインインするユーザーをWindowsします。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-301">LSASS authenticates users who sign in on a Windows computer.</span></span> <span data-ttu-id="5e8e0-302">Microsoft Defender Credential Guard in Windows 10は、通常、LSASS から資格情報を抽出しようとして防止します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-302">Microsoft Defender Credential Guard in Windows 10 normally prevents attempts to extract credentials from LSASS.</span></span> <span data-ttu-id="5e8e0-303">ただし、一部の組織では、カスタム スマートカード ドライバーやローカル セキュリティ機関 (LSA) に読み込む他のプログラムとの互換性の問題により、すべてのコンピューターで Credential Guard を有効にできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-303">However, some organizations can't enable Credential Guard on all of their computers because of compatibility issues with custom smartcard drivers or other programs that load into the Local Security Authority (LSA).</span></span> <span data-ttu-id="5e8e0-304">このような場合、攻撃者は Mimikatz のようなハッキング ツールを使用して、LSASS からクリアテキスト パスワードと NTLM ハッシュをスクレイピングできます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-304">In these cases, attackers can use hack tools like Mimikatz to scrape cleartext passwords and NTLM hashes from LSASS.</span></span>

> [!NOTE]
> <span data-ttu-id="5e8e0-305">一部のアプリでは、実行中のすべてのプロセスを列挙し、網羅的なアクセス許可を使用して開きます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-305">In some apps, the code enumerates all running processes and attempts to open them with exhaustive permissions.</span></span> <span data-ttu-id="5e8e0-306">このルールは、アプリのプロセスのオープン アクションを拒否し、詳細をセキュリティ イベント ログに記録します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-306">This rule denies the app's process open action and logs the details to the security event log.</span></span> <span data-ttu-id="5e8e0-307">このルールでは、多くのノイズが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-307">This rule can generate a lot of noise.</span></span> <span data-ttu-id="5e8e0-308">LSASS を列挙するだけで、機能に実際の影響がないアプリがある場合は、除外リストに追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-308">If you have an app that simply enumerates LSASS, but has no real impact in functionality, there is NO need to add it to the exclusion list.</span></span> <span data-ttu-id="5e8e0-309">それ自体では、このイベント ログ エントリは必ずしも悪意のある脅威を示すとは限りません。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-309">By itself, this event log entry doesn't necessarily indicate a malicious threat.</span></span>

<span data-ttu-id="5e8e0-310">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-310">This rule was introduced in:</span></span>

- [<span data-ttu-id="5e8e0-311">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="5e8e0-311">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="5e8e0-312">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="5e8e0-312">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="5e8e0-313">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e8e0-313">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="5e8e0-314">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="5e8e0-314">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="5e8e0-315">Intune 名: `Flag credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-315">Intune name: `Flag credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="5e8e0-316">Configuration Manager 名: `Block credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-316">Configuration Manager name: `Block credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="5e8e0-317">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-317">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span></span>

### <a name="block-executable-content-from-email-client-and-webmail"></a><span data-ttu-id="5e8e0-318">メール クライアントと Web メールから実行可能なコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-318">Block executable content from email client and webmail</span></span>

<span data-ttu-id="5e8e0-319">このルールは、Microsoft Outlook アプリケーション、または Outlook.com や他の一般的な Web メール プロバイダー内で開いた電子メールから、次の種類のファイルの起動をブロックします。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-319">This rule blocks the following file types from launching from email opened within the Microsoft Outlook application, or Outlook.com and other popular webmail providers:</span></span>

- <span data-ttu-id="5e8e0-320">実行可能ファイル (.exe、.dll.scr など)</span><span class="sxs-lookup"><span data-stu-id="5e8e0-320">Executable files (such as .exe, .dll, or .scr)</span></span>
- <span data-ttu-id="5e8e0-321">スクリプト ファイル (PowerShell .ps、Visual Basic .vbs、JavaScript .js ファイルなど)</span><span class="sxs-lookup"><span data-stu-id="5e8e0-321">Script files (such as a PowerShell .ps, Visual Basic .vbs, or JavaScript .js file)</span></span>

<span data-ttu-id="5e8e0-322">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-322">This rule was introduced in:</span></span>

- [<span data-ttu-id="5e8e0-323">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="5e8e0-323">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="5e8e0-324">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="5e8e0-324">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="5e8e0-325">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e8e0-325">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="5e8e0-326">Microsoft エンドポイント マネージャーCB 1710</span><span class="sxs-lookup"><span data-stu-id="5e8e0-326">Microsoft Endpoint Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="5e8e0-327">Intune 名: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-327">Intune name: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span></span>

<span data-ttu-id="5e8e0-328">Microsoft エンドポイント マネージャー名:`Block executable content from email client and webmail`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-328">Microsoft Endpoint Manager name: `Block executable content from email client and webmail`</span></span>

<span data-ttu-id="5e8e0-329">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-329">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span></span>

> [!NOTE]
> <span data-ttu-id="5e8e0-330">[メール **クライアントと Web メールからの** 実行可能なコンテンツをブロックする] というルールには、使用するアプリケーションに応じて、次の別の説明があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-330">The rule **Block executable content from email client and webmail** has the following alternative descriptions, depending on which application you use:</span></span>
>
> - <span data-ttu-id="5e8e0-331">Intune (構成プロファイル): 電子メール (Web メール/メール クライアント) から削除された実行可能コンテンツ (exe、dll、ps、js、vbs など) の実行 (例外なし)。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-331">Intune (Configuration Profiles): Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions).</span></span>
> - <span data-ttu-id="5e8e0-332">エンドポイント マネージャー: メールおよび Web メール クライアントからの実行可能コンテンツのダウンロードをブロックします。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-332">Endpoint Manager: Block executable content download from email and webmail clients.</span></span>
> - <span data-ttu-id="5e8e0-333">グループ ポリシー: 電子メール クライアントと Web メールから実行可能なコンテンツをブロックします。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-333">Group Policy: Block executable content from email client and webmail.</span></span>

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a><span data-ttu-id="5e8e0-334">有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-334">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>

<span data-ttu-id="5e8e0-335">このルールは、有病率や年齢の条件を満たしたり、信頼できるリストまたは除外リストに含めない限り、次の種類のファイルの起動をブロックします。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-335">This rule blocks the following file types from launching unless they meet prevalence or age criteria, or they're in a trusted list or an exclusion list:</span></span>

- <span data-ttu-id="5e8e0-336">実行可能ファイル (.exe、.dll.scr など)</span><span class="sxs-lookup"><span data-stu-id="5e8e0-336">Executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="5e8e0-337">信頼されていない実行可能ファイルまたは不明な実行可能ファイルを起動すると、ファイルが悪意のあるものか最初ははっきりしない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-337">Launching untrusted or unknown executable files can be risky, as it might not be initially clear if the files are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e8e0-338">このルールを [使用するには、クラウドによる保護](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-338">You must [enable cloud-delivered protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to use this rule.</span></span>
>
> <span data-ttu-id="5e8e0-339">GUID で **有病率** 、年齢、または信頼できるリスト条件を満たしていない場合、実行可能ファイルの実行をブロックするルールは、Microsoft が所有し、管理者によって `01443614-cd74-433a-b99e-2ecdc07bfc25` 指定されていません。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-339">The rule **Block executable files from running unless they meet a prevalence, age, or trusted list criterion** with GUID `01443614-cd74-433a-b99e-2ecdc07bfc25` is owned by Microsoft and is not specified by admins.</span></span> <span data-ttu-id="5e8e0-340">このルールでは、クラウド配信の保護を使用して、信頼できるリストを定期的に更新します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-340">This rule uses cloud-delivered protection to update its trusted list regularly.</span></span>
>
> <span data-ttu-id="5e8e0-341">個々のファイルまたはフォルダー (フォルダー パスまたは完全修飾リソース名を使用) を指定できますが、適用するルールや除外を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-341">You can specify individual files or folders (using folder paths or fully qualified resource names) but you can't specify which rules or exclusions apply to.</span></span>

<span data-ttu-id="5e8e0-342">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-342">This rule was introduced in:</span></span>

- [<span data-ttu-id="5e8e0-343">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="5e8e0-343">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="5e8e0-344">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="5e8e0-344">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="5e8e0-345">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e8e0-345">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="5e8e0-346">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="5e8e0-346">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="5e8e0-347">Intune 名: `Executables that don't meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-347">Intune name: `Executables that don't meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="5e8e0-348">Configuration Manager 名: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-348">Configuration Manager name: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="5e8e0-349">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-349">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span></span>

### <a name="block-execution-of-potentially-obfuscated-scripts"></a><span data-ttu-id="5e8e0-350">難読化される可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-350">Block execution of potentially obfuscated scripts</span></span>

<span data-ttu-id="5e8e0-351">このルールは、難読化されたスクリプト内の疑わしいプロパティを検出します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-351">This rule detects suspicious properties within an obfuscated script.</span></span>

<span data-ttu-id="5e8e0-352">スクリプト難読化は、マルウェア作成者と正当なアプリケーションの両方が、知的財産を隠したり、スクリプトの読み込み時間を短縮したりするために使用する一般的な手法です。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-352">Script obfuscation is a common technique that both malware authors and legitimate applications use to hide intellectual property or decrease script loading times.</span></span> <span data-ttu-id="5e8e0-353">マルウェアの作成者は難読化を使用して悪意のあるコードを読みにくくし、人間やセキュリティ ソフトウェアによる詳細な調査を防止します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-353">Malware authors also use obfuscation to make malicious code harder to read, which prevents close scrutiny by humans and security software.</span></span>

<span data-ttu-id="5e8e0-354">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-354">This rule was introduced in:</span></span>

- [<span data-ttu-id="5e8e0-355">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="5e8e0-355">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="5e8e0-356">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="5e8e0-356">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="5e8e0-357">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e8e0-357">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="5e8e0-358">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="5e8e0-358">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="5e8e0-359">Intune 名: `Obfuscated js/vbs/ps/macro code`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-359">Intune name: `Obfuscated js/vbs/ps/macro code`</span></span>

<span data-ttu-id="5e8e0-360">Configuration Manager 名: `Block execution of potentially obfuscated scripts`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-360">Configuration Manager name: `Block execution of potentially obfuscated scripts`</span></span>

<span data-ttu-id="5e8e0-361">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-361">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span></span>

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a><span data-ttu-id="5e8e0-362">JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-362">Block JavaScript or VBScript from launching downloaded executable content</span></span>

<span data-ttu-id="5e8e0-363">このルールにより、スクリプトは悪意のあるダウンロードコンテンツを起動できません。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-363">This rule prevents scripts from launching potentially malicious downloaded content.</span></span> <span data-ttu-id="5e8e0-364">JavaScript または VBScript で記述されたマルウェアは、インターネットから他のマルウェアをフェッチして起動するダウンデータとして機能する場合が多い。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-364">Malware written in JavaScript or VBScript often acts as a downloader to fetch and launch other malware from the Internet.</span></span>

<span data-ttu-id="5e8e0-365">一般的ではないが、一般企業向けアプリケーションでは、スクリプトを使用してインストーラーをダウンロードおよび起動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-365">Although not common, line-of-business applications sometimes use scripts to download and launch installers.</span></span>

<span data-ttu-id="5e8e0-366">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-366">This rule was introduced in:</span></span>

- [<span data-ttu-id="5e8e0-367">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="5e8e0-367">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="5e8e0-368">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="5e8e0-368">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="5e8e0-369">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e8e0-369">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="5e8e0-370">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="5e8e0-370">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="5e8e0-371">Intune 名: `js/vbs executing payload downloaded from Internet (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-371">Intune name: `js/vbs executing payload downloaded from Internet (no exceptions)`</span></span>

<span data-ttu-id="5e8e0-372">Configuration Manager 名: `Block JavaScript or VBScript from launching downloaded executable content`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-372">Configuration Manager name: `Block JavaScript or VBScript from launching downloaded executable content`</span></span>

<span data-ttu-id="5e8e0-373">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-373">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span></span>

### <a name="block-office-applications-from-creating-executable-content"></a><span data-ttu-id="5e8e0-374">実行可能Office作成するアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="5e8e0-374">Block Office applications from creating executable content</span></span>

<span data-ttu-id="5e8e0-375">このルール Officeは、悪意のあるコードがディスクに書き込まれるのをブロックすることで、Word、Excel、PowerPoint などのアプリが悪意のある実行可能コンテンツを作成するのを防ぐためです。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-375">This rule prevents Office apps, including Word, Excel, and PowerPoint, from creating potentially malicious executable content, by blocking malicious code from being written to disk.</span></span>

<span data-ttu-id="5e8e0-376">マルウェアは、Officeとして悪用され、悪意のあるOfficeをディスクに保存しようとする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-376">Malware that abuses Office as a vector might attempt to break out of Office and save malicious components to disk.</span></span> <span data-ttu-id="5e8e0-377">これらの悪意のあるコンポーネントは、コンピューターの再起動後も存続し、システム上で保持されます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-377">These malicious components would survive a computer reboot and persist on the system.</span></span> <span data-ttu-id="5e8e0-378">したがって、このルールは一般的な永続化手法に対して防御します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-378">Therefore, this rule defends against a common persistence technique.</span></span>

<span data-ttu-id="5e8e0-379">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-379">This rule was introduced in:</span></span>

- [<span data-ttu-id="5e8e0-380">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="5e8e0-380">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="5e8e0-381">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="5e8e0-381">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="5e8e0-382">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e8e0-382">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- <span data-ttu-id="5e8e0-383">[System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM がMicrosoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="5e8e0-383">[System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM is now Microsoft Endpoint Configuration Manager)</span></span>

<span data-ttu-id="5e8e0-384">Intune 名: `Office apps/macros creating executable content`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-384">Intune name: `Office apps/macros creating executable content`</span></span>

<span data-ttu-id="5e8e0-385">SCCM 名: `Block Office applications from creating executable content`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-385">SCCM name: `Block Office applications from creating executable content`</span></span>

<span data-ttu-id="5e8e0-386">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-386">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span></span>

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a><span data-ttu-id="5e8e0-387">アプリケーションOffice他のプロセスへのコードの挿入をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-387">Block Office applications from injecting code into other processes</span></span>

<span data-ttu-id="5e8e0-388">このルールは、アプリから他のプロセスへのコードOffice試行をブロックします。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-388">This rule blocks code injection attempts from Office apps into other processes.</span></span>

<span data-ttu-id="5e8e0-389">攻撃者は、Officeを使用して、コード挿入を通じて悪意のあるコードを他のプロセスに移行しようとする可能性があります。そのため、コードはクリーン なプロセスとして悪用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-389">Attackers might attempt to use Office apps to migrate malicious code into other processes through code injection, so the code can masquerade as a clean process.</span></span>

<span data-ttu-id="5e8e0-390">コードインジェクションを使用する正当なビジネス上の目的はありません。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-390">There are no known legitimate business purposes for using code injection.</span></span>

<span data-ttu-id="5e8e0-391">このルールは、Word、Excel、およびPowerPoint。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-391">This rule applies to Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="5e8e0-392">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-392">This rule was introduced in:</span></span>

- [<span data-ttu-id="5e8e0-393">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="5e8e0-393">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="5e8e0-394">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="5e8e0-394">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="5e8e0-395">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e8e0-395">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="5e8e0-396">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="5e8e0-396">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="5e8e0-397">Intune 名: `Office apps injecting code into other processes (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-397">Intune name: `Office apps injecting code into other processes (no exceptions)`</span></span>

<span data-ttu-id="5e8e0-398">Configuration Manager 名: `Block Office applications from injecting code into other processes`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-398">Configuration Manager name: `Block Office applications from injecting code into other processes`</span></span>

<span data-ttu-id="5e8e0-399">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-399">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span></span>

### <a name="block-office-communication-application-from-creating-child-processes"></a><span data-ttu-id="5e8e0-400">通信Officeプロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-400">Block Office communication application from creating child processes</span></span>

<span data-ttu-id="5e8e0-401">このルールは、Outlook が子プロセスを作成することを妨げる一方で、正当な Outlook 関数を許可します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-401">This rule prevents Outlook from creating child processes, while still allowing legitimate Outlook functions.</span></span>

<span data-ttu-id="5e8e0-402">このルールは、ソーシャル エンジニアリング攻撃から保護し、Outlook の脆弱性を悪用するコードの悪用を防止します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-402">This rule protects against social engineering attacks and prevents exploiting code from abusing vulnerabilities in Outlook.</span></span> <span data-ttu-id="5e8e0-403">また、ユーザーの [資格情報が侵害された](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) 場合に攻撃者が使用できる Outlook ルールやフォームの悪用から保護します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-403">It also protects against [Outlook rules and forms exploits](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) that attackers can use when a user's credentials are compromised.</span></span>

> [!NOTE]
> <span data-ttu-id="5e8e0-404">このルールは、Outlook の DLP ポリシー ヒントとツール ヒントをブロックします。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-404">This rule blocks DLP policy tips and ToolTips in Outlook.</span></span> <span data-ttu-id="5e8e0-405">このルールは、Outlook および Outlook Outlook.com 適用されます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-405">This rule applies to Outlook and Outlook.com only.</span></span>

<span data-ttu-id="5e8e0-406">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-406">This rule was introduced in:</span></span>

- [<span data-ttu-id="5e8e0-407">Windows 10 バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="5e8e0-407">Windows 10, version 1809</span></span>](/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="5e8e0-408">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="5e8e0-408">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="5e8e0-409">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e8e0-409">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="5e8e0-410">Intune 名: `Process creation from Office communication products (beta)`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-410">Intune name: `Process creation from Office communication products (beta)`</span></span>

<span data-ttu-id="5e8e0-411">Configuration Manager 名: 使用できません</span><span class="sxs-lookup"><span data-stu-id="5e8e0-411">Configuration Manager name: Not available</span></span>

<span data-ttu-id="5e8e0-412">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-412">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span></span>

### <a name="block-persistence-through-wmi-event-subscription"></a><span data-ttu-id="5e8e0-413">WMI イベント サブスクリプションによる永続化のブロック</span><span class="sxs-lookup"><span data-stu-id="5e8e0-413">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="5e8e0-414">このルールは、デバイス上で WMI を攻撃して永続化を達成するマルウェアを防止します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-414">This rule prevents malware from abusing WMI to attain persistence on a device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e8e0-415">ファイルとフォルダーの除外は、この攻撃表面の縮小ルールには適用されません。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-415">File and folder exclusions don't apply to this attack surface reduction rule.</span></span>

<span data-ttu-id="5e8e0-416">ファイルレスの脅威は、隠し、ファイル システムで見られない、定期的な実行制御を得るために、さまざまな戦術を採用しています。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-416">Fileless threats employ various tactics to stay hidden, to avoid being seen in the file system, and to gain periodic execution control.</span></span> <span data-ttu-id="5e8e0-417">一部の脅威は、WMI リポジトリとイベント モデルを悪用して非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-417">Some threats can abuse the WMI repository and event model to stay hidden.</span></span>

<span data-ttu-id="5e8e0-418">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-418">This rule was introduced in:</span></span>

- [<span data-ttu-id="5e8e0-419">Windows 10 バージョン 1903</span><span class="sxs-lookup"><span data-stu-id="5e8e0-419">Windows 10, version 1903</span></span>](/windows/whats-new/whats-new-windows-10-version-1903)
- [<span data-ttu-id="5e8e0-420">Windows Server 1903</span><span class="sxs-lookup"><span data-stu-id="5e8e0-420">Windows Server 1903</span></span>](/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

<span data-ttu-id="5e8e0-421">Intune 名: 使用できません</span><span class="sxs-lookup"><span data-stu-id="5e8e0-421">Intune name: Not available</span></span>

<span data-ttu-id="5e8e0-422">Configuration Manager 名: 使用できません</span><span class="sxs-lookup"><span data-stu-id="5e8e0-422">Configuration Manager name: Not available</span></span>

<span data-ttu-id="5e8e0-423">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-423">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span></span>

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a><span data-ttu-id="5e8e0-424">PSExec および WMI コマンドから発生するプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-424">Block process creations originating from PSExec and WMI commands</span></span>

<span data-ttu-id="5e8e0-425">このルールは [、PsExec](/sysinternals/downloads/psexec) および WMI を介して作成 [されたプロセスの実行](/windows/win32/wmisdk/about-wmi) をブロックします。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-425">This rule blocks processes created through [PsExec](/sysinternals/downloads/psexec) and [WMI](/windows/win32/wmisdk/about-wmi) from running.</span></span> <span data-ttu-id="5e8e0-426">PsExec と WMI の両方がコードをリモートで実行できるので、コマンドと制御の目的でこの機能を不正に使用したり、組織のネットワーク全体に感染を広げる危険性があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-426">Both PsExec and WMI can remotely execute code, so there is a risk of malware abusing this functionality for command and control purposes, or to spread an infection throughout an organization's network.</span></span>

> [!WARNING]
> <span data-ttu-id="5e8e0-427">Intune または別の MDM ソリューションを使用してデバイスを管理する場合にのみ、 [このルールを](/intune) 使用します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-427">Only use this rule if you're managing your devices with [Intune](/intune) or another MDM solution.</span></span> <span data-ttu-id="5e8e0-428">このルールは [、Configuration Manager](/configmgr) クライアントが正しく機能するために使用する WMI コマンドをブロックする Microsoft Endpoint Configuration Manager による管理と互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-428">This rule is incompatible with management through [Microsoft Endpoint Configuration Manager](/configmgr) because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span>

<span data-ttu-id="5e8e0-429">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-429">This rule was introduced in:</span></span>

- [<span data-ttu-id="5e8e0-430">Windows 10 バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="5e8e0-430">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="5e8e0-431">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="5e8e0-431">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="5e8e0-432">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e8e0-432">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="5e8e0-433">Intune 名: `Process creation from PSExec and WMI commands`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-433">Intune name: `Process creation from PSExec and WMI commands`</span></span>

<span data-ttu-id="5e8e0-434">Configuration Manager 名: 該当なし</span><span class="sxs-lookup"><span data-stu-id="5e8e0-434">Configuration Manager name: Not applicable</span></span>

<span data-ttu-id="5e8e0-435">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-435">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span></span>

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a><span data-ttu-id="5e8e0-436">USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="5e8e0-436">Block untrusted and unsigned processes that run from USB</span></span>

<span data-ttu-id="5e8e0-437">このルールを使用すると、管理者は、SD カードを含む USB リムーバブル ドライブから署名されていない実行可能ファイルまたは信頼されていない実行可能ファイルを実行できません。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-437">With this rule, admins can prevent unsigned or untrusted executable files from running from USB removable drives, including SD cards.</span></span> <span data-ttu-id="5e8e0-438">ブロックされたファイルの種類には、実行可能ファイル (.exe、.dll.scr など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-438">Blocked file types include executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="5e8e0-439">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-439">This rule was introduced in:</span></span>

- [<span data-ttu-id="5e8e0-440">Windows 10 バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="5e8e0-440">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="5e8e0-441">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="5e8e0-441">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="5e8e0-442">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e8e0-442">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="5e8e0-443">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="5e8e0-443">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="5e8e0-444">Intune 名: `Untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-444">Intune name: `Untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="5e8e0-445">Configuration Manager 名: `Block untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-445">Configuration Manager name: `Block untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="5e8e0-446">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-446">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span></span>

### <a name="block-win32-api-calls-from-office-macros"></a><span data-ttu-id="5e8e0-447">Win32 API 呼び出しをブロックOfficeマクロ</span><span class="sxs-lookup"><span data-stu-id="5e8e0-447">Block Win32 API calls from Office macros</span></span>

<span data-ttu-id="5e8e0-448">このルールは、VBA マクロが Win32 API を呼び出すのを防止します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-448">This rule prevents VBA macros from calling Win32 APIs.</span></span>

<span data-ttu-id="5e8e0-449">Office VBA では、Win32 API 呼び出しが有効です。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-449">Office VBA enables Win32 API calls.</span></span> <span data-ttu-id="5e8e0-450">マルウェアは [、Win32 API](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) を呼び出してディスクに直接何も書き込みせずに悪意のあるシェルコードを起動するなど、この機能を悪用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-450">Malware can abuse this capability, such as [calling Win32 APIs to launch malicious shellcode](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) without writing anything directly to disk.</span></span> <span data-ttu-id="5e8e0-451">ほとんどの組織では、他の方法でマクロを使用している場合でも、Win32 API を毎日の機能で呼び出す機能に依存しません。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-451">Most organizations don't rely on the ability to call Win32 APIs in their day-to-day functioning, even if they use macros in other ways.</span></span>

<span data-ttu-id="5e8e0-452">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-452">This rule was introduced in:</span></span>

- [<span data-ttu-id="5e8e0-453">Windows 10 バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="5e8e0-453">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="5e8e0-454">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="5e8e0-454">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="5e8e0-455">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e8e0-455">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="5e8e0-456">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="5e8e0-456">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="5e8e0-457">Intune 名: `Win32 imports from Office macro code`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-457">Intune name: `Win32 imports from Office macro code`</span></span>

<span data-ttu-id="5e8e0-458">Configuration Manager 名: `Block Win32 API calls from Office macros`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-458">Configuration Manager name: `Block Win32 API calls from Office macros`</span></span>

<span data-ttu-id="5e8e0-459">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-459">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span></span>

### <a name="use-advanced-protection-against-ransomware"></a><span data-ttu-id="5e8e0-460">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="5e8e0-460">Use advanced protection against ransomware</span></span>

<span data-ttu-id="5e8e0-461">このルールは、ランサムウェアに対する保護の追加層を提供します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-461">This rule provides an extra layer of protection against ransomware.</span></span> <span data-ttu-id="5e8e0-462">クライアントとクラウドの両方のヒューリスティックを使用して、ファイルがランサムウェアに似ているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-462">It uses both client and cloud heuristics to determine whether a file resembles ransomware.</span></span> <span data-ttu-id="5e8e0-463">このルールは、次の 1 つ以上の特性を持つファイルをブロックしない。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-463">This rule does not block files that have one or more of the following characteristics:</span></span>

- <span data-ttu-id="5e8e0-464">このファイルは、Microsoft クラウドで既に無傷である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-464">The file has already been found to be unharmful in the Microsoft cloud.</span></span>
- <span data-ttu-id="5e8e0-465">ファイルは有効な署名付きファイルです。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-465">The file is a valid signed file.</span></span>
- <span data-ttu-id="5e8e0-466">ファイルはランサムウェアと見なされないほど普及しています。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-466">The file is prevalent enough to not be considered as ransomware.</span></span>

<span data-ttu-id="5e8e0-467">このルールは、ランサムウェアを防止するために注意を払う傾向があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-467">The rule tends to err on the side of caution to prevent ransomware.</span></span>

> [!NOTE]
> <span data-ttu-id="5e8e0-468">このルールを [使用するには、クラウドによる保護](enable-cloud-protection-microsoft-defender-antivirus.md) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-468">You must [enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) to use this rule.</span></span>

<span data-ttu-id="5e8e0-469">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-469">This rule was introduced in:</span></span>

- [<span data-ttu-id="5e8e0-470">Windows 10 バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="5e8e0-470">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="5e8e0-471">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="5e8e0-471">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="5e8e0-472">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e8e0-472">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="5e8e0-473">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="5e8e0-473">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="5e8e0-474">Intune 名: `Advanced ransomware protection`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-474">Intune name: `Advanced ransomware protection`</span></span>

<span data-ttu-id="5e8e0-475">Configuration Manager 名: `Use advanced protection against ransomware`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-475">Configuration Manager name: `Use advanced protection against ransomware`</span></span>

<span data-ttu-id="5e8e0-476">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span><span class="sxs-lookup"><span data-stu-id="5e8e0-476">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span></span>
