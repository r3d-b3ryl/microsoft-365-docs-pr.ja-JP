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
ms.openlocfilehash: 59f116e3fe2b617803efd9625f399235b79a1142
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177635"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a><span data-ttu-id="cd4d8-104">攻撃表面の縮小ルールを使用してマルウェアの感染を防止する</span><span class="sxs-lookup"><span data-stu-id="cd4d8-104">Use attack surface reduction rules to prevent malware infection</span></span>

<span data-ttu-id="cd4d8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cd4d8-105">**Applies to:**</span></span>

- [<span data-ttu-id="cd4d8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cd4d8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="cd4d8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd4d8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a><span data-ttu-id="cd4d8-108">攻撃表面の縮小ルールが重要な理由</span><span class="sxs-lookup"><span data-stu-id="cd4d8-108">Why attack surface reduction rules are important</span></span>

<span data-ttu-id="cd4d8-109">組織の攻撃表面には、攻撃者が組織のデバイスやネットワークを侵害する可能性があるすべての場所が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-109">Your organization's attack surface includes all the places where an attacker could compromise your organization's devices or networks.</span></span> <span data-ttu-id="cd4d8-110">攻撃の表面を減らすことは、組織のデバイスとネットワークを保護する手段であり、攻撃者は攻撃を実行する方法が少なくなっています。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-110">Reducing your attack surface means protecting your organization's devices and network, which leaves attackers with fewer ways to perform attacks.</span></span> <span data-ttu-id="cd4d8-111">Microsoft Defender for Endpoint で攻撃表面の縮小ルールを構成すると役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-111">Configuring attack surface reduction rules in Microsoft Defender for Endpoint can help!</span></span>

<span data-ttu-id="cd4d8-112">攻撃表面の縮小ルールは、次のような特定のソフトウェア動作を対象とします。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-112">Attack surface reduction rules target certain software behaviors, such as:</span></span>

- <span data-ttu-id="cd4d8-113">ファイルのダウンロードまたは実行を試みる実行可能ファイルとスクリプトの起動</span><span class="sxs-lookup"><span data-stu-id="cd4d8-113">Launching executable files and scripts that attempt to download or run files</span></span>
- <span data-ttu-id="cd4d8-114">難読化されたスクリプトまたはその他の疑わしいスクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="cd4d8-114">Running obfuscated or otherwise suspicious scripts</span></span>
- <span data-ttu-id="cd4d8-115">通常の毎日の作業中にアプリが通常開始しない動作を実行する</span><span class="sxs-lookup"><span data-stu-id="cd4d8-115">Performing behaviors that apps don't usually initiate during normal day-to-day work</span></span>

<span data-ttu-id="cd4d8-116">このようなソフトウェアの動作は、正当なアプリケーションで見られる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-116">Such software behaviors are sometimes seen in legitimate applications.</span></span> <span data-ttu-id="cd4d8-117">ただし、これらの動作は、マルウェアを介して攻撃者によって悪用されるのが一般的なので、リスクが高いと見なされる場合が多い。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-117">However, these behaviors are often considered risky because they are commonly abused by attackers through malware.</span></span> <span data-ttu-id="cd4d8-118">攻撃表面の縮小ルールは、ソフトウェア ベースのリスクの高い動作を制限し、組織の安全を維持するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-118">Attack surface reduction rules can constrain software-based risky behaviors and help keep your organization safe.</span></span>

<span data-ttu-id="cd4d8-119">攻撃表面の縮小ルールの構成の詳細については、「攻撃表面の縮小ルールを有効 [にする」を参照してください](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-119">For more information about configuring attack surface reduction rules, see [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

## <a name="assess-rule-impact-before-deployment"></a><span data-ttu-id="cd4d8-120">展開前にルールへの影響を評価する</span><span class="sxs-lookup"><span data-stu-id="cd4d8-120">Assess rule impact before deployment</span></span>

<span data-ttu-id="cd4d8-121">攻撃表面の縮小ルールがネットワークに与える影響を評価するには、このルールのセキュリティに関する推奨事項を [脅威と脆弱性の管理][で開きます](/windows/security/threat-protection/#tvm)。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-121">You can assess how an attack surface reduction rule might affect your network by opening the security recommendation for that rule in [threat and vulnerability management](/windows/security/threat-protection/#tvm).</span></span>

:::image type="content" source="images/asrrecommendation.png" alt-text="攻撃表面の縮小ルールのセキュリティ reco":::

<span data-ttu-id="cd4d8-123">[推奨事項の詳細] ウィンドウで、ユーザーの影響を確認して、生産性に悪影響を及ぼさずに、ブロック モードでルールを有効にする新しいポリシーを受け入れ可能なデバイスの割合を確認します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-123">In the recommendation details pane, check for user impact to determine what percentage of your devices can accept a new policy enabling the rule in blocking mode without adversely affecting productivity.</span></span>

<span data-ttu-id="cd4d8-124">サポート [されるオペレーティング システムと](enable-attack-surface-reduction.md#requirements) 追加の要件情報については、「攻撃表面縮小ルールを有効にする」の記事の「要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-124">See [Requirements](enable-attack-surface-reduction.md#requirements) in the "Enable attack surface reduction rules" article for information about supported operating systems and additional requirement information.</span></span>

## <a name="audit-mode-for-evaluation"></a><span data-ttu-id="cd4d8-125">評価の監査モード</span><span class="sxs-lookup"><span data-stu-id="cd4d8-125">Audit mode for evaluation</span></span>

<span data-ttu-id="cd4d8-126">監査 [モードを使用して](audit-windows-defender.md) 、攻撃表面の縮小ルールが有効な場合に組織に与える影響を評価します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-126">Use [audit mode](audit-windows-defender.md) to evaluate how attack surface reduction rules would affect your organization if enabled.</span></span> <span data-ttu-id="cd4d8-127">監査モードですべてのルールを最初に実行して、そのルールがビジネスライン アプリケーションに与える影響を理解できます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-127">Run all rules in audit mode first so you can understand how they affect your line-of-business applications.</span></span> <span data-ttu-id="cd4d8-128">多くの業務用アプリケーションは、限られたセキュリティ上の懸念を持って記述され、マルウェアに似た方法でタスクを実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-128">Many line-of-business applications are written with limited security concerns, and they might perform tasks in ways that seem similar to malware.</span></span> <span data-ttu-id="cd4d8-129">監査データを監視し、必要なアプリケーションの [除外](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) を追加することで、生産性を低下させずに攻撃表面の縮小ルールを展開できます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-129">By monitoring audit data and [adding exclusions](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) for necessary applications, you can deploy attack surface reduction rules without reducing productivity.</span></span>

## <a name="warn-mode-for-users"></a><span data-ttu-id="cd4d8-130">ユーザーの警告モード</span><span class="sxs-lookup"><span data-stu-id="cd4d8-130">Warn mode for users</span></span>

<span data-ttu-id="cd4d8-131">(**NEW**!)警告モード機能の前に、有効になっている攻撃表面の縮小ルールを監査モードまたはブロック モードに設定できます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-131">(**NEW**!) Prior to warn mode capabilities, attack surface reduction rules that are enabled could be set to either audit mode or block mode.</span></span> <span data-ttu-id="cd4d8-132">新しい警告モードでは、攻撃表面の縮小ルールによってコンテンツがブロックされるたびに、コンテンツがブロックされたかどうかを示すダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-132">With the new warn mode, whenever content is blocked by an attack surface reduction rule, users see a dialog box that indicates the content is blocked.</span></span> <span data-ttu-id="cd4d8-133">ダイアログ ボックスには、コンテンツのブロックを解除するオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-133">The dialog box also offers the user an option to unblock the content.</span></span> <span data-ttu-id="cd4d8-134">その後、ユーザーはアクションを再試行し、操作が完了します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-134">The user can then retry their action, and the operation completes.</span></span> <span data-ttu-id="cd4d8-135">ユーザーがコンテンツのブロックを解除すると、コンテンツは 24 時間ブロック解除されたままで、その後ブロックが再開されます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-135">When a user unblocks content, the content remains unblocked for 24 hours, and then blocking resumes.</span></span>

<span data-ttu-id="cd4d8-136">警告モードは、ユーザーが自分のタスクを実行するために必要なコンテンツにアクセスするのを防ぐことなく、組織が攻撃表面の縮小ルールを設定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-136">Warn mode helps your organization have attack surface reduction rules in place without preventing users from accessing the content they need to perform their tasks.</span></span>

### <a name="requirements-for-warn-mode-to-work"></a><span data-ttu-id="cd4d8-137">警告モードが機能する要件</span><span class="sxs-lookup"><span data-stu-id="cd4d8-137">Requirements for warn mode to work</span></span>

<span data-ttu-id="cd4d8-138">警告モードは、次のバージョンの警告を実行しているデバイスWindows。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-138">Warn mode is supported on devices running the following versions of Windows:</span></span>

- <span data-ttu-id="cd4d8-139">[Windows 10 Version 1809](/windows/whats-new/whats-new-windows-10-version-1809)以降</span><span class="sxs-lookup"><span data-stu-id="cd4d8-139">[Windows 10, version 1809](/windows/whats-new/whats-new-windows-10-version-1809) or later</span></span>
- <span data-ttu-id="cd4d8-140">[Windows Server バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)以降</span><span class="sxs-lookup"><span data-stu-id="cd4d8-140">[Windows Server, version 1809](/windows-server/get-started/whats-new-in-windows-server-1809) or later</span></span>

<span data-ttu-id="cd4d8-141">Microsoft Defender ウイルス対策モードでリアルタイム保護を実行している[必要があります](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-141">Microsoft Defender Antivirus must be running with real-time protection in [Active mode](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state).</span></span>

<span data-ttu-id="cd4d8-142">さらに、マルウェア対策[Microsoft Defender ウイルス対策更新プログラムがインストールされていることを](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)確認します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-142">In addition, make sure [Microsoft Defender Antivirus and antimalware updates](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) are installed.</span></span>

- <span data-ttu-id="cd4d8-143">プラットフォームリリースの最小要件: `4.18.2008.9`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-143">Minimum platform release requirement: `4.18.2008.9`</span></span>
- <span data-ttu-id="cd4d8-144">エンジンリリースの最小要件: `1.1.17400.5`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-144">Minimum engine release requirement: `1.1.17400.5`</span></span>

<span data-ttu-id="cd4d8-145">詳細と更新プログラムの取得については [、「Update for Microsoft Defender マルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-145">For more information and to get your updates, see [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).</span></span>

### <a name="cases-where-warn-mode-is-not-supported"></a><span data-ttu-id="cd4d8-146">警告モードがサポートされていない場合</span><span class="sxs-lookup"><span data-stu-id="cd4d8-146">Cases where warn mode is not supported</span></span>

<span data-ttu-id="cd4d8-147">警告モードは、3 つの攻撃表面の縮小ルールを構成するときにサポートMicrosoft エンドポイント マネージャー。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-147">Warn mode is not supported for three attack surface reduction rules when you configure them in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="cd4d8-148">(グループ ポリシーを使用して攻撃表面の縮小ルールを構成する場合は、警告モードがサポートされます)。警告モードを構成するときに警告モードをサポートしない 3 つのMicrosoft エンドポイント マネージャーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-148">(If you use Group Policy to configure your attack surface reduction rules, warn mode is supported.) The three rules that do not support warn mode when you configure them in Microsoft Endpoint Manager are as follows:</span></span>

- <span data-ttu-id="cd4d8-149">[ダウンロードした実行可能コンテンツ (GUID)](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)の起動から JavaScript または VBScript をブロックする `d3e037e1-3eb8-44c8-a917-57927947596d`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-149">[Block JavaScript or VBScript from launching downloaded executable content](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`)</span></span>
- <span data-ttu-id="cd4d8-150">[WMI イベント サブスクリプション (GUID) による永続](#block-persistence-through-wmi-event-subscription) 化をブロック `e6db77e5-3df2-4cf1-b95a-636979351e5b` する</span><span class="sxs-lookup"><span data-stu-id="cd4d8-150">[Block persistence through WMI event subscription](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`)</span></span>
- <span data-ttu-id="cd4d8-151">[ランサムウェアに対する高度な保護を使用](#use-advanced-protection-against-ransomware) する `c1db55ab-c21a-4637-bb3f-a12568109d35` (GUID)</span><span class="sxs-lookup"><span data-stu-id="cd4d8-151">[Use advanced protection against ransomware](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`)</span></span>

<span data-ttu-id="cd4d8-152">さらに、以前のバージョンのバージョンのデバイスで警告モードはサポートWindows。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-152">In addition, warn mode is not supported on devices running older versions of Windows.</span></span> <span data-ttu-id="cd4d8-153">このような場合、警告モードで実行するように構成された攻撃表面の縮小ルールは、ブロック モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-153">In those cases, attack surface reduction rules that are configured to run in warn mode will run in block mode.</span></span>

## <a name="notifications-and-alerts"></a><span data-ttu-id="cd4d8-154">通知とアラート</span><span class="sxs-lookup"><span data-stu-id="cd4d8-154">Notifications and alerts</span></span>

<span data-ttu-id="cd4d8-155">攻撃表面の縮小ルールがトリガーされるたびに、デバイスに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-155">Whenever an attack surface reduction rule is triggered, a notification is displayed on the device.</span></span> <span data-ttu-id="cd4d8-156">会社の詳細や連絡先情報を使用して[通知をカスタマイズ](customize-attack-surface-reduction.md#customize-the-notification)することができます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-156">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span>

<span data-ttu-id="cd4d8-157">さらに、特定の攻撃表面の縮小ルールがトリガーされると、アラートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-157">In addition, when certain attack surface reduction rules are triggered, alerts are generated.</span></span>

<span data-ttu-id="cd4d8-158">通知と生成されたアラートは、Microsoft 365 Defender ポータル ( ) (以前は [https://security.microsoft.com](https://security.microsoft.com) Microsoft Defender セキュリティ センター)[で表示できます](microsoft-defender-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-158">Notifications and any alerts that are generated can be viewed in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) (formerly called the [Microsoft Defender Security Center](microsoft-defender-security-center.md)).</span></span>

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a><span data-ttu-id="cd4d8-159">高度な狩猟と攻撃表面の縮小イベント</span><span class="sxs-lookup"><span data-stu-id="cd4d8-159">Advanced hunting and attack surface reduction events</span></span>

<span data-ttu-id="cd4d8-160">高度な検索を使用して、攻撃表面の縮小イベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-160">You can use advanced hunting to view attack surface reduction events.</span></span> <span data-ttu-id="cd4d8-161">受信データの量を合理化するために、高度な検索では、1 時間ごとに一意のプロセスのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-161">To streamline the volume of incoming data, only unique processes for each hour are viewable with advanced hunting.</span></span> <span data-ttu-id="cd4d8-162">攻撃表面の縮小イベントの時間は、1 時間以内に初めてイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-162">The time of an attack surface reduction event is the first time that event is seen within the hour.</span></span>

<span data-ttu-id="cd4d8-163">たとえば、午後 2 時の間に 10 台のデバイスで攻撃表面の縮小イベントが発生するとします。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-163">For example, suppose that an attack surface reduction event occurs on 10 devices during the 2:00 PM hour.</span></span> <span data-ttu-id="cd4d8-164">最初のイベントが 2:15、最後の 2:45 に発生したとします。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-164">Suppose that the first event occurred at 2:15, and the last at 2:45.</span></span> <span data-ttu-id="cd4d8-165">高度な検索では、そのイベントのインスタンスが 1 つ表示されます (実際には 10 台のデバイスで発生した場合でも)、タイムスタンプは午後 2 時 15 分になります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-165">With advanced hunting, you'll see one instance of that event (even though it actually occurred on 10 devices), and its timestamp will be 2:15 PM.</span></span>

<span data-ttu-id="cd4d8-166">高度な狩猟の詳細については、「高度な狩猟 [を使用して脅威を事前に検出する」を参照してください](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-166">For more information about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="attack-surface-reduction-features-across-windows-versions"></a><span data-ttu-id="cd4d8-167">複数のバージョンの攻撃表面Windows機能</span><span class="sxs-lookup"><span data-stu-id="cd4d8-167">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="cd4d8-168">次のエディションとバージョンのデバイスを実行しているデバイスに対して攻撃表面の縮小ルールをWindows。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-168">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="cd4d8-169">Windows 10 Proバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="cd4d8-169">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="cd4d8-170">Windows 10 Enterpriseバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="cd4d8-170">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="cd4d8-171">Windowsサーバー、[バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803)以降</span><span class="sxs-lookup"><span data-stu-id="cd4d8-171">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="cd4d8-172">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd4d8-172">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="cd4d8-173">攻撃表面の縮小ルールでは[E5](/windows/deployment/deploy-enterprise-licenses)ライセンスをWindows必要とWindows、高度な管理機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-173">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="cd4d8-174">E5 でのみ使用できる高度な機能はWindows含まれます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-174">The advanced capabilities - available only in Windows E5 - include:</span></span>

- <span data-ttu-id="cd4d8-175">Defender for Endpoint で利用できる監視、分析、 [およびワークフロー](microsoft-defender-endpoint.md)</span><span class="sxs-lookup"><span data-stu-id="cd4d8-175">The monitoring, analytics, and workflows available in [Defender for Endpoint](microsoft-defender-endpoint.md)</span></span>
- <span data-ttu-id="cd4d8-176">レポート機能と構成機能は[、Microsoft 365 Defender。](/microsoft-365/security/defender/overview-security-center)</span><span class="sxs-lookup"><span data-stu-id="cd4d8-176">The reporting and configuration capabilities in [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="cd4d8-177">これらの高度な機能は、E3 ライセンスWindows ProfessionalまたはWindows使用できません。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-177">These advanced capabilities aren't available with a Windows Professional or Windows E3 license.</span></span> <span data-ttu-id="cd4d8-178">ただし、これらのライセンスがある場合は、イベント ビューアーとログMicrosoft Defender ウイルス対策を使用して、攻撃表面の縮小ルール イベントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-178">However, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="cd4d8-179">ポータルで攻撃表面の縮小イベントをMicrosoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-179">Review attack surface reduction events in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="cd4d8-180">Defender for Endpoint は、アラート調査シナリオの一環として、イベントとブロックの詳細なレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-180">Defender for Endpoint provides detailed reporting for events and blocks as part of alert investigation scenarios.</span></span>

<span data-ttu-id="cd4d8-181">高度な検索を使用して、Microsoft 365 Defender Defender [for](microsoft-defender-security-center.md) Endpoint データ[をクエリできます](advanced-hunting-query-language.md)。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-181">You can query Defender for Endpoint data in [Microsoft 365 Defender](microsoft-defender-security-center.md) by using [advanced hunting](advanced-hunting-query-language.md).</span></span> <span data-ttu-id="cd4d8-182">監査モードを実行している [場合](audit-windows-defender.md)は、高度な検索を使用して、攻撃表面の縮小ルールが環境に与える影響を理解できます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-182">If you're running [audit mode](audit-windows-defender.md), you can use advanced hunting to understand how attack surface reduction rules might affect your environment.</span></span>

<span data-ttu-id="cd4d8-183">クエリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-183">Here is an example query:</span></span>

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="cd4d8-184">イベント ビューアーで攻撃表面の縮小イベントWindows確認する</span><span class="sxs-lookup"><span data-stu-id="cd4d8-184">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="cd4d8-185">次のイベント ログをWindowsして、攻撃表面の縮小ルールによって生成されたイベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-185">You can review the Windows event log to view events generated by attack surface reduction rules:</span></span>

1. <span data-ttu-id="cd4d8-186">評価パッケージ [をダウンロードし](https://aka.ms/mp7z2w) 、デバイス上 *cfa-events.xmlアクセスしやすい* 場所にファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-186">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>

2. <span data-ttu-id="cd4d8-187">[イベント ビューアー] という *単語* を入力して、スタート メニューを開Windowsします。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-187">Enter the words, *Event Viewer*, into the Start menu to open the Windows Event Viewer.</span></span>

3. <span data-ttu-id="cd4d8-188">[アクション **] で**、[カスタム **ビューのインポート.... を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-188">Under **Actions**, select **Import custom view...**.</span></span>

4. <span data-ttu-id="cd4d8-189">抽出された場所 *cfa-events.xml* ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-189">Select the file *cfa-events.xml* from where it was extracted.</span></span> <span data-ttu-id="cd4d8-190">または [、XML を直接コピーします](event-views.md)。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-190">Alternatively, [copy the XML directly](event-views.md).</span></span>

5. <span data-ttu-id="cd4d8-191">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-191">Select **OK**.</span></span>

<span data-ttu-id="cd4d8-192">イベントをフィルター処理して、次のイベントのみを表示するカスタム ビューを作成できます。そのすべては、フォルダー アクセスの制御に関連しています。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-192">You can create a custom view that filters events to only show the following events, all of which are related to controlled folder access:</span></span>

|<span data-ttu-id="cd4d8-193">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cd4d8-193">Event ID</span></span>|<span data-ttu-id="cd4d8-194">説明</span><span class="sxs-lookup"><span data-stu-id="cd4d8-194">Description</span></span>|
|---|---|
|<span data-ttu-id="cd4d8-195">5007</span><span class="sxs-lookup"><span data-stu-id="cd4d8-195">5007</span></span>|<span data-ttu-id="cd4d8-196">設定が変更された場合のイベント</span><span class="sxs-lookup"><span data-stu-id="cd4d8-196">Event when settings are changed</span></span>|
|<span data-ttu-id="cd4d8-197">1121</span><span class="sxs-lookup"><span data-stu-id="cd4d8-197">1121</span></span>|<span data-ttu-id="cd4d8-198">ブロック モードでルールが発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="cd4d8-198">Event when rule fires in Block-mode</span></span>|
|<span data-ttu-id="cd4d8-199">1122</span><span class="sxs-lookup"><span data-stu-id="cd4d8-199">1122</span></span>|<span data-ttu-id="cd4d8-200">監査モードでルールが発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="cd4d8-200">Event when rule fires in Audit-mode</span></span>|

<span data-ttu-id="cd4d8-201">イベント ログの攻撃表面の縮小イベント用にリストされている "エンジンバージョン" は、オペレーティング システムではなく Defender for Endpoint によって生成されます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-201">The "engine version" listed for attack surface reduction events in the event log, is generated by Defender for Endpoint, not by the operating system.</span></span> <span data-ttu-id="cd4d8-202">Defender for Endpoint は、Windows 10と統合されています。そのため、この機能は、インストールされているすべてのデバイスWindows 10します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-202">Defender for Endpoint is integrated with Windows 10, so this feature works on all devices with Windows 10 installed.</span></span>

## <a name="attack-surface-reduction-rules"></a><span data-ttu-id="cd4d8-203">攻撃面の減少ルール</span><span class="sxs-lookup"><span data-stu-id="cd4d8-203">Attack surface reduction rules</span></span>

<span data-ttu-id="cd4d8-204">次の表とサブセクションでは、16 の攻撃表面の縮小ルールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-204">The following table and subsections describe each of the 16 attack surface reduction rules.</span></span> <span data-ttu-id="cd4d8-205">攻撃表面の縮小ルールは、ルール名によってアルファベット順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-205">The attack surface reduction rules are listed in alphabetical order, by rule name.</span></span>

<span data-ttu-id="cd4d8-206">グループ ポリシーまたは PowerShell を使用して攻撃表面の縮小ルールを構成する場合は、GUID が必要です。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-206">If you are configuring attack surface reduction rules by using Group Policy or PowerShell, you'll need the GUIDs.</span></span> <span data-ttu-id="cd4d8-207">一方、ユーザー設定またはMicrosoft エンドポイント マネージャーをMicrosoft Intune GUID は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-207">On the other hand, if you use Microsoft Endpoint Manager or Microsoft Intune, you do not need the GUIDs.</span></span>

|<span data-ttu-id="cd4d8-208">ルールの名前</span><span class="sxs-lookup"><span data-stu-id="cd4d8-208">Rule name</span></span>|<span data-ttu-id="cd4d8-209">GUID</span><span class="sxs-lookup"><span data-stu-id="cd4d8-209">GUID</span></span>|<span data-ttu-id="cd4d8-210">ファイル&フォルダーの除外</span><span class="sxs-lookup"><span data-stu-id="cd4d8-210">File & folder exclusions</span></span>|<span data-ttu-id="cd4d8-211">サポートされる最小 OS</span><span class="sxs-lookup"><span data-stu-id="cd4d8-211">Minimum OS supported</span></span>|
|---|:---:|---|---|
|[<span data-ttu-id="cd4d8-212">悪用された脆弱な署名済みドライバーの悪用をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-212">Block abuse of exploited vulnerable signed drivers</span></span>](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|<span data-ttu-id="cd4d8-213">サポート済み</span><span class="sxs-lookup"><span data-stu-id="cd4d8-213">Supported</span></span>|<span data-ttu-id="cd4d8-214">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上)</span><span class="sxs-lookup"><span data-stu-id="cd4d8-214">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater)</span></span> |
|[<span data-ttu-id="cd4d8-215">Adobe Reader の子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-215">Block Adobe Reader from creating child processes</span></span>](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|<span data-ttu-id="cd4d8-216">サポート済み</span><span class="sxs-lookup"><span data-stu-id="cd4d8-216">Supported</span></span>|<span data-ttu-id="cd4d8-217">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="cd4d8-217">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="cd4d8-218">すべてのアプリケーションOffice子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-218">Block all Office applications from creating child processes</span></span>](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|<span data-ttu-id="cd4d8-219">サポート済み</span><span class="sxs-lookup"><span data-stu-id="cd4d8-219">Supported</span></span>|<span data-ttu-id="cd4d8-220">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="cd4d8-220">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="cd4d8-221">ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="cd4d8-221">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|<span data-ttu-id="cd4d8-222">サポート済み</span><span class="sxs-lookup"><span data-stu-id="cd4d8-222">Supported</span></span>|<span data-ttu-id="cd4d8-223">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="cd4d8-223">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="cd4d8-224">メール クライアントと Web メールから実行可能なコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-224">Block executable content from email client and webmail</span></span>](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|<span data-ttu-id="cd4d8-225">サポート済み</span><span class="sxs-lookup"><span data-stu-id="cd4d8-225">Supported</span></span>|<span data-ttu-id="cd4d8-226">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="cd4d8-226">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="cd4d8-227">有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-227">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|<span data-ttu-id="cd4d8-228">サポート済み</span><span class="sxs-lookup"><span data-stu-id="cd4d8-228">Supported</span></span>|<span data-ttu-id="cd4d8-229">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="cd4d8-229">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="cd4d8-230">難読化される可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-230">Block execution of potentially obfuscated scripts</span></span>](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|<span data-ttu-id="cd4d8-231">サポート済み</span><span class="sxs-lookup"><span data-stu-id="cd4d8-231">Supported</span></span>|<span data-ttu-id="cd4d8-232">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="cd4d8-232">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="cd4d8-233">JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-233">Block JavaScript or VBScript from launching downloaded executable content</span></span>](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|<span data-ttu-id="cd4d8-234">サポート済み</span><span class="sxs-lookup"><span data-stu-id="cd4d8-234">Supported</span></span>|<span data-ttu-id="cd4d8-235">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="cd4d8-235">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="cd4d8-236">実行可能Office作成するアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="cd4d8-236">Block Office applications from creating executable content</span></span>](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|<span data-ttu-id="cd4d8-237">サポート済み</span><span class="sxs-lookup"><span data-stu-id="cd4d8-237">Supported</span></span>|<span data-ttu-id="cd4d8-238">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="cd4d8-238">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="cd4d8-239">アプリケーションOffice他のプロセスへのコードの挿入をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-239">Block Office applications from injecting code into other processes</span></span>](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|<span data-ttu-id="cd4d8-240">サポート済み</span><span class="sxs-lookup"><span data-stu-id="cd4d8-240">Supported</span></span>|<span data-ttu-id="cd4d8-241">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="cd4d8-241">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="cd4d8-242">通信Officeプロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-242">Block Office communication application from creating child processes</span></span>](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|<span data-ttu-id="cd4d8-243">サポート済み</span><span class="sxs-lookup"><span data-stu-id="cd4d8-243">Supported</span></span>|<span data-ttu-id="cd4d8-244">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="cd4d8-244">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="cd4d8-245">WMI イベント サブスクリプションによる永続化のブロック</span><span class="sxs-lookup"><span data-stu-id="cd4d8-245">Block persistence through WMI event subscription</span></span>](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|<span data-ttu-id="cd4d8-246">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="cd4d8-246">Not supported</span></span>|<span data-ttu-id="cd4d8-247">[Windows 10バージョン 1903](/windows/whats-new/whats-new-windows-10-version-1903) (ビルド 18362) 以上</span><span class="sxs-lookup"><span data-stu-id="cd4d8-247">[Windows 10, version 1903](/windows/whats-new/whats-new-windows-10-version-1903) (build 18362) or greater</span></span>|
|[<span data-ttu-id="cd4d8-248">PSExec および WMI コマンドから発生するプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-248">Block process creations originating from PSExec and WMI commands</span></span>](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|<span data-ttu-id="cd4d8-249">サポート済み</span><span class="sxs-lookup"><span data-stu-id="cd4d8-249">Supported</span></span>|<span data-ttu-id="cd4d8-250">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="cd4d8-250">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="cd4d8-251">USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-251">Block untrusted and unsigned processes that run from USB</span></span>](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|<span data-ttu-id="cd4d8-252">サポート済み</span><span class="sxs-lookup"><span data-stu-id="cd4d8-252">Supported</span></span>|<span data-ttu-id="cd4d8-253">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="cd4d8-253">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="cd4d8-254">Win32 API 呼び出しをブロックOfficeマクロ</span><span class="sxs-lookup"><span data-stu-id="cd4d8-254">Block Win32 API calls from Office macros</span></span>](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|<span data-ttu-id="cd4d8-255">サポート済み</span><span class="sxs-lookup"><span data-stu-id="cd4d8-255">Supported</span></span>|<span data-ttu-id="cd4d8-256">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="cd4d8-256">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="cd4d8-257">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="cd4d8-257">Use advanced protection against ransomware</span></span>](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|<span data-ttu-id="cd4d8-258">サポート済み</span><span class="sxs-lookup"><span data-stu-id="cd4d8-258">Supported</span></span>|<span data-ttu-id="cd4d8-259">[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="cd4d8-259">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a><span data-ttu-id="cd4d8-260">悪用された脆弱な署名済みドライバーの悪用をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-260">Block abuse of exploited vulnerable signed drivers</span></span>

<span data-ttu-id="cd4d8-261">このルールは、アプリケーションが脆弱な署名済みドライバーをディスクに書き込むのを防ぐためです。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-261">This rule prevents an application from writing a vulnerable signed driver to disk.</span></span> <span data-ttu-id="cd4d8-262">インザワイルドで脆弱な署名済みドライバーは、カーネルにアクセスするのに十分な特権を持つローカル アプリケーション \-  \- によって悪用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-262">In-the-wild, vulnerable signed drivers can be exploited by local applications \- _that have sufficient privileges_ \- to gain access to the kernel.</span></span> <span data-ttu-id="cd4d8-263">脆弱な署名付きドライバーを使用すると、攻撃者はセキュリティ ソリューションを無効または回避し、最終的にはシステムの侵害につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-263">Vulnerable signed drivers enable attackers to disable or circumvent security solutions, eventually leading to system compromise.</span></span>

<span data-ttu-id="cd4d8-264">[ **悪用された脆弱な** 署名済みドライバーの悪用をブロックする] ルールは、システム上に既に存在するドライバーの読み込みをブロックしない。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-264">The **Block abuse of exploited vulnerable signed drivers** rule does not block a driver already existing on the system from being loaded.</span></span>

>[!NOTE]
>
> <span data-ttu-id="cd4d8-265">このルールは [、MEM OMA-URI](enable-attack-surface-reduction.md#mem) カスタム ルールのプロシージャ情報に対して MEM OMA-URI を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-265">You can configure this rule using [MEM OMA-URI](enable-attack-surface-reduction.md#mem) for MEM OMA-URI custom rules procedural information.</span></span>
>
> <span data-ttu-id="cd4d8-266">PowerShell を使用してこのルールを [構成できます](enable-attack-surface-reduction.md#powershell)。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-266">You can also configure this rule using [PowerShell](enable-attack-surface-reduction.md#powershell).</span></span>
>
> <span data-ttu-id="cd4d8-267">ドライバーを調べるには、この Web サイトを使用して分析 [用のドライバーを送信します](https://www.microsoft.com/en-us/wdsi/driversubmission)。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-267">To have a driver examined, use this Web site to [Submit a driver for analysis](https://www.microsoft.com/en-us/wdsi/driversubmission).</span></span>

<span data-ttu-id="cd4d8-268">このルールは、ASR がサポートされているすべてのバージョンでサポートされます。これは次の場合です。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-268">This rule is supported in all versions in which ASR is supported; which is:</span></span>

- <span data-ttu-id="cd4d8-269">[Windows 10 Proバージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="cd4d8-269">[Windows 10 Pro, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="cd4d8-270">[Windows 10 Enterpriseバージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="cd4d8-270">[Windows 10 Enterprise, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="cd4d8-271">[Windows Server バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803)以降</span><span class="sxs-lookup"><span data-stu-id="cd4d8-271">[Windows Server, version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="cd4d8-272">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd4d8-272">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="cd4d8-273">Intune 名: `Block abuse of exploited vulnerable signed drivers`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-273">Intune Name: `Block abuse of exploited vulnerable signed drivers`</span></span>

<span data-ttu-id="cd4d8-274">GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-274">GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span></span>

### <a name="block-adobe-reader-from-creating-child-processes"></a><span data-ttu-id="cd4d8-275">Adobe Reader の子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-275">Block Adobe Reader from creating child processes</span></span>

<span data-ttu-id="cd4d8-276">このルールは、Adobe Reader によるプロセスの作成をブロックすることで攻撃を防止します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-276">This rule prevents attacks by blocking Adobe Reader from creating processes.</span></span>

<span data-ttu-id="cd4d8-277">ソーシャル エンジニアリングや悪用を通じて、マルウェアはペイロードをダウンロードして起動し、Adobe Reader から抜け出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-277">Through social engineering or exploits, malware can download and launch payloads, and break out of Adobe Reader.</span></span> <span data-ttu-id="cd4d8-278">Adobe Reader によって子プロセスが生成されるのをブロックすることで、子プロセスをベクターとして使用しようとするマルウェアが拡散を防止します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-278">By blocking child processes from being generated by Adobe Reader, malware attempting to use it as a vector are prevented from spreading.</span></span>

<span data-ttu-id="cd4d8-279">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-279">This rule was introduced in:</span></span>

- [<span data-ttu-id="cd4d8-280">Windows 10 Version 1809</span><span class="sxs-lookup"><span data-stu-id="cd4d8-280">Windows 10, version 1809</span></span>](/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="cd4d8-281">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="cd4d8-281">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="cd4d8-282">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd4d8-282">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="cd4d8-283">Intune 名: `Process creation from Adobe Reader (beta)`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-283">Intune name: `Process creation from Adobe Reader (beta)`</span></span>

<span data-ttu-id="cd4d8-284">Configuration Manager 名: まだ使用できません</span><span class="sxs-lookup"><span data-stu-id="cd4d8-284">Configuration Manager name: Not yet available</span></span>

<span data-ttu-id="cd4d8-285">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-285">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span></span>

### <a name="block-all-office-applications-from-creating-child-processes"></a><span data-ttu-id="cd4d8-286">すべてのアプリケーションOffice子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-286">Block all Office applications from creating child processes</span></span>

<span data-ttu-id="cd4d8-287">このルールは、Officeプロセスの作成をブロックします。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-287">This rule blocks Office apps from creating child processes.</span></span> <span data-ttu-id="cd4d8-288">Officeには、Word、Excel、PowerPoint、OneNote、Access が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-288">Office apps include Word, Excel, PowerPoint, OneNote, and Access.</span></span>

<span data-ttu-id="cd4d8-289">悪意のある子プロセスを作成する方法は、一般的なマルウェア戦略です。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-289">Creating malicious child processes is a common malware strategy.</span></span> <span data-ttu-id="cd4d8-290">マルウェアがベクターとしてOffice、VBA マクロを実行し、コードを悪用して、より多くのペイロードをダウンロードして実行しようとする場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-290">Malware that abuse Office as a vector often run VBA macros and exploit code to download and attempt to run more payloads.</span></span> <span data-ttu-id="cd4d8-291">ただし、一部の正当な業務行アプリケーションでは、良性の目的で子プロセスを生成する場合があります。コマンド プロンプトを生成したり、PowerShell を使用してレジストリ設定を構成したりします。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-291">However, some legitimate line-of-business applications might also generate child processes for benign purposes; such as spawning a command prompt or using PowerShell to configure registry settings.</span></span>

<span data-ttu-id="cd4d8-292">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-292">This rule was introduced in:</span></span>

- [<span data-ttu-id="cd4d8-293">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="cd4d8-293">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="cd4d8-294">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="cd4d8-294">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="cd4d8-295">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd4d8-295">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="cd4d8-296">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="cd4d8-296">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="cd4d8-297">Intune 名: `Office apps launching child processes`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-297">Intune name: `Office apps launching child processes`</span></span>

<span data-ttu-id="cd4d8-298">Configuration Manager 名: `Block Office application from creating child processes`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-298">Configuration Manager name: `Block Office application from creating child processes`</span></span>

<span data-ttu-id="cd4d8-299">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-299">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span></span>

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a><span data-ttu-id="cd4d8-300">ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-300">Block credential stealing from the Windows local security authority subsystem</span></span>

<span data-ttu-id="cd4d8-301">このルールは、ローカル セキュリティ機関サブシステム サービス (LSASS) をロックダウンして資格情報の盗用を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-301">This rule helps prevent credential stealing by locking down Local Security Authority Subsystem Service (LSASS).</span></span>

<span data-ttu-id="cd4d8-302">LSASS は、コンピューターにサインインするユーザーをWindowsします。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-302">LSASS authenticates users who sign in on a Windows computer.</span></span> <span data-ttu-id="cd4d8-303">Microsoft Defender Credential Guard in Windows 10は、通常、LSASS から資格情報を抽出しようとして防止します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-303">Microsoft Defender Credential Guard in Windows 10 normally prevents attempts to extract credentials from LSASS.</span></span> <span data-ttu-id="cd4d8-304">ただし、一部の組織では、カスタム スマートカード ドライバーやローカル セキュリティ機関 (LSA) に読み込む他のプログラムとの互換性の問題により、すべてのコンピューターで Credential Guard を有効にできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-304">However, some organizations can't enable Credential Guard on all of their computers because of compatibility issues with custom smartcard drivers or other programs that load into the Local Security Authority (LSA).</span></span> <span data-ttu-id="cd4d8-305">このような場合、攻撃者は Mimikatz のようなハッキング ツールを使用して、LSASS からクリアテキスト パスワードと NTLM ハッシュをスクレイピングできます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-305">In these cases, attackers can use hack tools like Mimikatz to scrape cleartext passwords and NTLM hashes from LSASS.</span></span>

> [!NOTE]
> <span data-ttu-id="cd4d8-306">一部のアプリでは、実行中のすべてのプロセスを列挙し、網羅的なアクセス許可を使用して開きます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-306">In some apps, the code enumerates all running processes and attempts to open them with exhaustive permissions.</span></span> <span data-ttu-id="cd4d8-307">このルールは、アプリのプロセスのオープン アクションを拒否し、詳細をセキュリティ イベント ログに記録します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-307">This rule denies the app's process open action and logs the details to the security event log.</span></span> <span data-ttu-id="cd4d8-308">このルールでは、多くのノイズが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-308">This rule can generate a lot of noise.</span></span> <span data-ttu-id="cd4d8-309">LSASS を列挙するだけで、機能に実際の影響がないアプリがある場合は、除外リストに追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-309">If you have an app that simply enumerates LSASS, but has no real impact in functionality, there is NO need to add it to the exclusion list.</span></span> <span data-ttu-id="cd4d8-310">それ自体では、このイベント ログ エントリは必ずしも悪意のある脅威を示すとは限りません。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-310">By itself, this event log entry doesn't necessarily indicate a malicious threat.</span></span>

<span data-ttu-id="cd4d8-311">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-311">This rule was introduced in:</span></span>

- [<span data-ttu-id="cd4d8-312">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="cd4d8-312">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="cd4d8-313">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="cd4d8-313">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="cd4d8-314">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd4d8-314">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="cd4d8-315">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="cd4d8-315">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="cd4d8-316">Intune 名: `Flag credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-316">Intune name: `Flag credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="cd4d8-317">Configuration Manager 名: `Block credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-317">Configuration Manager name: `Block credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="cd4d8-318">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-318">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span></span>

### <a name="block-executable-content-from-email-client-and-webmail"></a><span data-ttu-id="cd4d8-319">メール クライアントと Web メールから実行可能なコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-319">Block executable content from email client and webmail</span></span>

<span data-ttu-id="cd4d8-320">このルールは、Microsoft Outlook アプリケーション、または Outlook.com や他の一般的な Web メール プロバイダー内で開いた電子メールから、次の種類のファイルの起動をブロックします。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-320">This rule blocks the following file types from launching from email opened within the Microsoft Outlook application, or Outlook.com and other popular webmail providers:</span></span>

- <span data-ttu-id="cd4d8-321">実行可能ファイル (.exe、.dll.scr など)</span><span class="sxs-lookup"><span data-stu-id="cd4d8-321">Executable files (such as .exe, .dll, or .scr)</span></span>
- <span data-ttu-id="cd4d8-322">スクリプト ファイル (PowerShell .ps、Visual Basic .vbs、JavaScript .js ファイルなど)</span><span class="sxs-lookup"><span data-stu-id="cd4d8-322">Script files (such as a PowerShell .ps, Visual Basic .vbs, or JavaScript .js file)</span></span>

<span data-ttu-id="cd4d8-323">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-323">This rule was introduced in:</span></span>

- [<span data-ttu-id="cd4d8-324">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="cd4d8-324">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="cd4d8-325">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="cd4d8-325">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="cd4d8-326">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd4d8-326">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="cd4d8-327">Microsoft エンドポイント マネージャーCB 1710</span><span class="sxs-lookup"><span data-stu-id="cd4d8-327">Microsoft Endpoint Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="cd4d8-328">Intune 名: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-328">Intune name: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span></span>

<span data-ttu-id="cd4d8-329">Microsoft エンドポイント マネージャー名:`Block executable content from email client and webmail`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-329">Microsoft Endpoint Manager name: `Block executable content from email client and webmail`</span></span>

<span data-ttu-id="cd4d8-330">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-330">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span></span>

> [!NOTE]
> <span data-ttu-id="cd4d8-331">[メール **クライアントと Web メールからの** 実行可能なコンテンツをブロックする] というルールには、使用するアプリケーションに応じて、次の別の説明があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-331">The rule **Block executable content from email client and webmail** has the following alternative descriptions, depending on which application you use:</span></span>
>
> - <span data-ttu-id="cd4d8-332">Intune (構成プロファイル): 電子メール (Web メール/メール クライアント) から削除された実行可能コンテンツ (exe、dll、ps、js、vbs など) の実行 (例外なし)。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-332">Intune (Configuration Profiles): Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions).</span></span>
> - <span data-ttu-id="cd4d8-333">エンドポイント マネージャー: メールおよび Web メール クライアントからの実行可能コンテンツのダウンロードをブロックします。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-333">Endpoint Manager: Block executable content download from email and webmail clients.</span></span>
> - <span data-ttu-id="cd4d8-334">グループ ポリシー: 電子メール クライアントと Web メールから実行可能なコンテンツをブロックします。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-334">Group Policy: Block executable content from email client and webmail.</span></span>

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a><span data-ttu-id="cd4d8-335">有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-335">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>

<span data-ttu-id="cd4d8-336">次の条件が満たされていない限り、.exe、.dll、.scr などの実行可能ファイルが起動をブロックします。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-336">This rule blocks executable files, such as .exe, .dll, or .scr, from launching unless any of the following conditions are met:</span></span>

- <span data-ttu-id="cd4d8-337">有病率: 実行可能ファイルは 1,000 を超えるエンドポイントで検出されます</span><span class="sxs-lookup"><span data-stu-id="cd4d8-337">Prevalence: The executable files are found on more than 1,000 endpoints</span></span>
- <span data-ttu-id="cd4d8-338">Age: 実行可能ファイルは 24 時間以上前にリリースされました</span><span class="sxs-lookup"><span data-stu-id="cd4d8-338">Age: The executable files were released more than 24 hours ago</span></span>
- <span data-ttu-id="cd4d8-339">場所: 実行可能ファイルが信頼できるリストまたは除外リストに含まれている</span><span class="sxs-lookup"><span data-stu-id="cd4d8-339">Location: The executable files are included in a trusted list or an exclusion list</span></span>

<span data-ttu-id="cd4d8-340">信頼されていない実行可能ファイルまたは不明な実行可能ファイルを起動すると、ファイルが悪意のあるものか最初ははっきりしない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-340">Launching untrusted or unknown executable files can be risky, as it might not be initially clear if the files are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd4d8-341">このルールを [使用するには、クラウドによる保護](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-341">You must [enable cloud-delivered protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to use this rule.</span></span>
>
> <span data-ttu-id="cd4d8-342">GUID で **有病率** 、年齢、または信頼できるリスト条件を満たしていない場合、実行可能ファイルの実行をブロックするルールは、Microsoft が所有し、管理者によって `01443614-cd74-433a-b99e-2ecdc07bfc25` 指定されていません。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-342">The rule **Block executable files from running unless they meet a prevalence, age, or trusted list criterion** with GUID `01443614-cd74-433a-b99e-2ecdc07bfc25` is owned by Microsoft and is not specified by admins.</span></span> <span data-ttu-id="cd4d8-343">このルールでは、クラウド配信の保護を使用して、信頼できるリストを定期的に更新します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-343">This rule uses cloud-delivered protection to update its trusted list regularly.</span></span>
>
> <span data-ttu-id="cd4d8-344">個々のファイルまたはフォルダー (フォルダー パスまたは完全修飾リソース名を使用) を指定できますが、適用するルールや除外を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-344">You can specify individual files or folders (using folder paths or fully qualified resource names) but you can't specify which rules or exclusions apply to.</span></span>

<span data-ttu-id="cd4d8-345">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-345">This rule was introduced in:</span></span>

- [<span data-ttu-id="cd4d8-346">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="cd4d8-346">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="cd4d8-347">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="cd4d8-347">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="cd4d8-348">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd4d8-348">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="cd4d8-349">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="cd4d8-349">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="cd4d8-350">Intune 名: `Executables that don't meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-350">Intune name: `Executables that don't meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="cd4d8-351">Configuration Manager 名: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-351">Configuration Manager name: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="cd4d8-352">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-352">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span></span>

### <a name="block-execution-of-potentially-obfuscated-scripts"></a><span data-ttu-id="cd4d8-353">難読化される可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-353">Block execution of potentially obfuscated scripts</span></span>

<span data-ttu-id="cd4d8-354">このルールは、難読化されたスクリプト内の疑わしいプロパティを検出します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-354">This rule detects suspicious properties within an obfuscated script.</span></span>

<span data-ttu-id="cd4d8-355">スクリプト難読化は、マルウェア作成者と正当なアプリケーションの両方が、知的財産を隠したり、スクリプトの読み込み時間を短縮したりするために使用する一般的な手法です。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-355">Script obfuscation is a common technique that both malware authors and legitimate applications use to hide intellectual property or decrease script loading times.</span></span> <span data-ttu-id="cd4d8-356">マルウェアの作成者は難読化を使用して悪意のあるコードを読みにくくし、人間やセキュリティ ソフトウェアによる詳細な調査を防止します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-356">Malware authors also use obfuscation to make malicious code harder to read, which prevents close scrutiny by humans and security software.</span></span>

<span data-ttu-id="cd4d8-357">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-357">This rule was introduced in:</span></span>

- [<span data-ttu-id="cd4d8-358">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="cd4d8-358">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="cd4d8-359">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="cd4d8-359">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="cd4d8-360">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd4d8-360">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="cd4d8-361">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="cd4d8-361">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="cd4d8-362">Intune 名: `Obfuscated js/vbs/ps/macro code`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-362">Intune name: `Obfuscated js/vbs/ps/macro code`</span></span>

<span data-ttu-id="cd4d8-363">Configuration Manager 名: `Block execution of potentially obfuscated scripts`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-363">Configuration Manager name: `Block execution of potentially obfuscated scripts`</span></span>

<span data-ttu-id="cd4d8-364">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-364">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span></span>

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a><span data-ttu-id="cd4d8-365">JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-365">Block JavaScript or VBScript from launching downloaded executable content</span></span>

<span data-ttu-id="cd4d8-366">このルールにより、スクリプトは悪意のあるダウンロードコンテンツを起動できません。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-366">This rule prevents scripts from launching potentially malicious downloaded content.</span></span> <span data-ttu-id="cd4d8-367">JavaScript または VBScript で記述されたマルウェアは、インターネットから他のマルウェアをフェッチして起動するダウンデータとして機能する場合が多い。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-367">Malware written in JavaScript or VBScript often acts as a downloader to fetch and launch other malware from the Internet.</span></span>

<span data-ttu-id="cd4d8-368">一般的ではないが、一般企業向けアプリケーションでは、スクリプトを使用してインストーラーをダウンロードおよび起動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-368">Although not common, line-of-business applications sometimes use scripts to download and launch installers.</span></span>

<span data-ttu-id="cd4d8-369">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-369">This rule was introduced in:</span></span>

- [<span data-ttu-id="cd4d8-370">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="cd4d8-370">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="cd4d8-371">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="cd4d8-371">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="cd4d8-372">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd4d8-372">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="cd4d8-373">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="cd4d8-373">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="cd4d8-374">Intune 名: `js/vbs executing payload downloaded from Internet (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-374">Intune name: `js/vbs executing payload downloaded from Internet (no exceptions)`</span></span>

<span data-ttu-id="cd4d8-375">Configuration Manager 名: `Block JavaScript or VBScript from launching downloaded executable content`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-375">Configuration Manager name: `Block JavaScript or VBScript from launching downloaded executable content`</span></span>

<span data-ttu-id="cd4d8-376">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-376">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span></span>

### <a name="block-office-applications-from-creating-executable-content"></a><span data-ttu-id="cd4d8-377">実行可能Office作成するアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="cd4d8-377">Block Office applications from creating executable content</span></span>

<span data-ttu-id="cd4d8-378">このルール Officeは、悪意のあるコードがディスクに書き込まれるのをブロックすることで、Word、Excel、PowerPoint などのアプリが悪意のある実行可能コンテンツを作成するのを防ぐためです。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-378">This rule prevents Office apps, including Word, Excel, and PowerPoint, from creating potentially malicious executable content, by blocking malicious code from being written to disk.</span></span>

<span data-ttu-id="cd4d8-379">マルウェアは、Officeとして悪用され、悪意のあるOfficeをディスクに保存しようとする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-379">Malware that abuses Office as a vector might attempt to break out of Office and save malicious components to disk.</span></span> <span data-ttu-id="cd4d8-380">これらの悪意のあるコンポーネントは、コンピューターの再起動後も存続し、システム上で保持されます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-380">These malicious components would survive a computer reboot and persist on the system.</span></span> <span data-ttu-id="cd4d8-381">したがって、このルールは一般的な永続化手法に対して防御します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-381">Therefore, this rule defends against a common persistence technique.</span></span>

<span data-ttu-id="cd4d8-382">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-382">This rule was introduced in:</span></span>

- [<span data-ttu-id="cd4d8-383">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="cd4d8-383">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="cd4d8-384">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="cd4d8-384">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="cd4d8-385">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd4d8-385">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- <span data-ttu-id="cd4d8-386">[System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM がMicrosoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="cd4d8-386">[System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM is now Microsoft Endpoint Configuration Manager)</span></span>

<span data-ttu-id="cd4d8-387">Intune 名: `Office apps/macros creating executable content`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-387">Intune name: `Office apps/macros creating executable content`</span></span>

<span data-ttu-id="cd4d8-388">SCCM 名: `Block Office applications from creating executable content`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-388">SCCM name: `Block Office applications from creating executable content`</span></span>

<span data-ttu-id="cd4d8-389">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-389">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span></span>

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a><span data-ttu-id="cd4d8-390">アプリケーションOffice他のプロセスへのコードの挿入をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-390">Block Office applications from injecting code into other processes</span></span>

<span data-ttu-id="cd4d8-391">このルールは、アプリから他のプロセスへのコードOffice試行をブロックします。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-391">This rule blocks code injection attempts from Office apps into other processes.</span></span>

<span data-ttu-id="cd4d8-392">攻撃者は、Officeを使用して、コード挿入を通じて悪意のあるコードを他のプロセスに移行しようとする可能性があります。そのため、コードはクリーン なプロセスとして悪用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-392">Attackers might attempt to use Office apps to migrate malicious code into other processes through code injection, so the code can masquerade as a clean process.</span></span>

<span data-ttu-id="cd4d8-393">コードインジェクションを使用する正当なビジネス上の目的はありません。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-393">There are no known legitimate business purposes for using code injection.</span></span>

<span data-ttu-id="cd4d8-394">このルールは、Word、Excel、およびPowerPoint。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-394">This rule applies to Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="cd4d8-395">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-395">This rule was introduced in:</span></span>

- [<span data-ttu-id="cd4d8-396">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="cd4d8-396">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="cd4d8-397">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="cd4d8-397">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="cd4d8-398">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd4d8-398">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="cd4d8-399">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="cd4d8-399">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="cd4d8-400">Intune 名: `Office apps injecting code into other processes (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-400">Intune name: `Office apps injecting code into other processes (no exceptions)`</span></span>

<span data-ttu-id="cd4d8-401">Configuration Manager 名: `Block Office applications from injecting code into other processes`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-401">Configuration Manager name: `Block Office applications from injecting code into other processes`</span></span>

<span data-ttu-id="cd4d8-402">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-402">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span></span>

### <a name="block-office-communication-application-from-creating-child-processes"></a><span data-ttu-id="cd4d8-403">通信Officeプロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-403">Block Office communication application from creating child processes</span></span>

<span data-ttu-id="cd4d8-404">このルールは、Outlookプロセスを作成する一方で、正当なプロセス機能Outlookします。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-404">This rule prevents Outlook from creating child processes, while still allowing legitimate Outlook functions.</span></span>

<span data-ttu-id="cd4d8-405">このルールは、ソーシャル エンジニアリング攻撃から保護し、コードを悪用して、セキュリティ上の脆弱性を悪用Outlook。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-405">This rule protects against social engineering attacks and prevents exploiting code from abusing vulnerabilities in Outlook.</span></span> <span data-ttu-id="cd4d8-406">また、ユーザーのOutlook[が](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/)侵害された場合に攻撃者が使用する可能性のある、特定のルールやフォームの悪用から保護します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-406">It also protects against [Outlook rules and forms exploits](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) that attackers can use when a user's credentials are compromised.</span></span>

> [!NOTE]
> <span data-ttu-id="cd4d8-407">このルールは、DLP ポリシー のヒントとツール ヒントをブロックOutlook。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-407">This rule blocks DLP policy tips and ToolTips in Outlook.</span></span> <span data-ttu-id="cd4d8-408">このルールは、Outlookおよび Outlook.com にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-408">This rule applies to Outlook and Outlook.com only.</span></span>

<span data-ttu-id="cd4d8-409">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-409">This rule was introduced in:</span></span>

- [<span data-ttu-id="cd4d8-410">Windows 10 Version 1809</span><span class="sxs-lookup"><span data-stu-id="cd4d8-410">Windows 10, version 1809</span></span>](/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="cd4d8-411">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="cd4d8-411">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="cd4d8-412">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd4d8-412">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="cd4d8-413">Intune 名: `Process creation from Office communication products (beta)`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-413">Intune name: `Process creation from Office communication products (beta)`</span></span>

<span data-ttu-id="cd4d8-414">Configuration Manager 名: 使用できません</span><span class="sxs-lookup"><span data-stu-id="cd4d8-414">Configuration Manager name: Not available</span></span>

<span data-ttu-id="cd4d8-415">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-415">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span></span>

### <a name="block-persistence-through-wmi-event-subscription"></a><span data-ttu-id="cd4d8-416">WMI イベント サブスクリプションによる永続化のブロック</span><span class="sxs-lookup"><span data-stu-id="cd4d8-416">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="cd4d8-417">このルールは、デバイス上で WMI を攻撃して永続化を達成するマルウェアを防止します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-417">This rule prevents malware from abusing WMI to attain persistence on a device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd4d8-418">ファイルとフォルダーの除外は、この攻撃表面の縮小ルールには適用されません。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-418">File and folder exclusions don't apply to this attack surface reduction rule.</span></span>

<span data-ttu-id="cd4d8-419">ファイルレスの脅威は、隠し、ファイル システムで見られない、定期的な実行制御を得るために、さまざまな戦術を採用しています。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-419">Fileless threats employ various tactics to stay hidden, to avoid being seen in the file system, and to gain periodic execution control.</span></span> <span data-ttu-id="cd4d8-420">一部の脅威は、WMI リポジトリとイベント モデルを悪用して非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-420">Some threats can abuse the WMI repository and event model to stay hidden.</span></span>

<span data-ttu-id="cd4d8-421">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-421">This rule was introduced in:</span></span>

- [<span data-ttu-id="cd4d8-422">Windows 10バージョン 1903</span><span class="sxs-lookup"><span data-stu-id="cd4d8-422">Windows 10, version 1903</span></span>](/windows/whats-new/whats-new-windows-10-version-1903)
- [<span data-ttu-id="cd4d8-423">Windowsサーバー 1903</span><span class="sxs-lookup"><span data-stu-id="cd4d8-423">Windows Server 1903</span></span>](/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

<span data-ttu-id="cd4d8-424">Intune 名: 使用できません</span><span class="sxs-lookup"><span data-stu-id="cd4d8-424">Intune name: Not available</span></span>

<span data-ttu-id="cd4d8-425">Configuration Manager 名: 使用できません</span><span class="sxs-lookup"><span data-stu-id="cd4d8-425">Configuration Manager name: Not available</span></span>

<span data-ttu-id="cd4d8-426">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-426">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span></span>

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a><span data-ttu-id="cd4d8-427">PSExec および WMI コマンドから発生するプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-427">Block process creations originating from PSExec and WMI commands</span></span>

<span data-ttu-id="cd4d8-428">このルールは [、PsExec](/sysinternals/downloads/psexec) および WMI を介して作成 [されたプロセスの実行](/windows/win32/wmisdk/about-wmi) をブロックします。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-428">This rule blocks processes created through [PsExec](/sysinternals/downloads/psexec) and [WMI](/windows/win32/wmisdk/about-wmi) from running.</span></span> <span data-ttu-id="cd4d8-429">PsExec と WMI の両方がコードをリモートで実行できるので、コマンドと制御の目的でこの機能を不正に使用したり、組織のネットワーク全体に感染を広げる危険性があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-429">Both PsExec and WMI can remotely execute code, so there is a risk of malware abusing this functionality for command and control purposes, or to spread an infection throughout an organization's network.</span></span>

> [!WARNING]
> <span data-ttu-id="cd4d8-430">Intune または別の MDM ソリューションを使用してデバイスを管理する場合にのみ、 [このルールを](/intune) 使用します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-430">Only use this rule if you're managing your devices with [Intune](/intune) or another MDM solution.</span></span> <span data-ttu-id="cd4d8-431">このルールは、Configuration Manager クライアント[が正しく機能するために使用Microsoft Endpoint Configuration Manager](/configmgr) WMI コマンドをブロックします。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-431">This rule is incompatible with management through [Microsoft Endpoint Configuration Manager](/configmgr) because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span>

<span data-ttu-id="cd4d8-432">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-432">This rule was introduced in:</span></span>

- [<span data-ttu-id="cd4d8-433">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="cd4d8-433">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="cd4d8-434">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="cd4d8-434">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="cd4d8-435">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd4d8-435">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="cd4d8-436">Intune 名: `Process creation from PSExec and WMI commands`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-436">Intune name: `Process creation from PSExec and WMI commands`</span></span>

<span data-ttu-id="cd4d8-437">Configuration Manager 名: 該当なし</span><span class="sxs-lookup"><span data-stu-id="cd4d8-437">Configuration Manager name: Not applicable</span></span>

<span data-ttu-id="cd4d8-438">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-438">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span></span>

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a><span data-ttu-id="cd4d8-439">USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="cd4d8-439">Block untrusted and unsigned processes that run from USB</span></span>

<span data-ttu-id="cd4d8-440">このルールを使用すると、管理者は、SD カードを含む USB リムーバブル ドライブから署名されていない実行可能ファイルまたは信頼されていない実行可能ファイルを実行できません。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-440">With this rule, admins can prevent unsigned or untrusted executable files from running from USB removable drives, including SD cards.</span></span> <span data-ttu-id="cd4d8-441">ブロックされたファイルの種類には、実行可能ファイル (.exe、.dll.scr など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-441">Blocked file types include executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="cd4d8-442">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-442">This rule was introduced in:</span></span>

- [<span data-ttu-id="cd4d8-443">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="cd4d8-443">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="cd4d8-444">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="cd4d8-444">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="cd4d8-445">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd4d8-445">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="cd4d8-446">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="cd4d8-446">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="cd4d8-447">Intune 名: `Untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-447">Intune name: `Untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="cd4d8-448">Configuration Manager 名: `Block untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-448">Configuration Manager name: `Block untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="cd4d8-449">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-449">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span></span>

### <a name="block-win32-api-calls-from-office-macros"></a><span data-ttu-id="cd4d8-450">Win32 API 呼び出しをブロックOfficeマクロ</span><span class="sxs-lookup"><span data-stu-id="cd4d8-450">Block Win32 API calls from Office macros</span></span>

<span data-ttu-id="cd4d8-451">このルールは、VBA マクロが Win32 API を呼び出すのを防止します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-451">This rule prevents VBA macros from calling Win32 APIs.</span></span>

<span data-ttu-id="cd4d8-452">OfficeVBA では、Win32 API 呼び出しが有効です。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-452">Office VBA enables Win32 API calls.</span></span> <span data-ttu-id="cd4d8-453">マルウェアは [、Win32 API](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) を呼び出してディスクに直接何も書き込みせずに悪意のあるシェルコードを起動するなど、この機能を悪用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-453">Malware can abuse this capability, such as [calling Win32 APIs to launch malicious shellcode](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) without writing anything directly to disk.</span></span> <span data-ttu-id="cd4d8-454">ほとんどの組織では、他の方法でマクロを使用している場合でも、Win32 API を毎日の機能で呼び出す機能に依存しません。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-454">Most organizations don't rely on the ability to call Win32 APIs in their day-to-day functioning, even if they use macros in other ways.</span></span>

<span data-ttu-id="cd4d8-455">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-455">This rule was introduced in:</span></span>

- [<span data-ttu-id="cd4d8-456">Windows 10バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="cd4d8-456">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="cd4d8-457">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="cd4d8-457">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="cd4d8-458">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd4d8-458">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="cd4d8-459">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="cd4d8-459">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="cd4d8-460">Intune 名: `Win32 imports from Office macro code`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-460">Intune name: `Win32 imports from Office macro code`</span></span>

<span data-ttu-id="cd4d8-461">Configuration Manager 名: `Block Win32 API calls from Office macros`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-461">Configuration Manager name: `Block Win32 API calls from Office macros`</span></span>

<span data-ttu-id="cd4d8-462">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-462">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span></span>

### <a name="use-advanced-protection-against-ransomware"></a><span data-ttu-id="cd4d8-463">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="cd4d8-463">Use advanced protection against ransomware</span></span>

<span data-ttu-id="cd4d8-464">このルールは、ランサムウェアに対する保護の追加層を提供します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-464">This rule provides an extra layer of protection against ransomware.</span></span> <span data-ttu-id="cd4d8-465">クライアントとクラウドの両方のヒューリスティックを使用して、ファイルがランサムウェアに似ているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-465">It uses both client and cloud heuristics to determine whether a file resembles ransomware.</span></span> <span data-ttu-id="cd4d8-466">このルールは、次の 1 つ以上の特性を持つファイルをブロックしない。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-466">This rule does not block files that have one or more of the following characteristics:</span></span>

- <span data-ttu-id="cd4d8-467">このファイルは、Microsoft クラウドで既に無傷である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-467">The file has already been found to be unharmful in the Microsoft cloud.</span></span>
- <span data-ttu-id="cd4d8-468">ファイルは有効な署名付きファイルです。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-468">The file is a valid signed file.</span></span>
- <span data-ttu-id="cd4d8-469">ファイルはランサムウェアと見なされないほど普及しています。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-469">The file is prevalent enough to not be considered as ransomware.</span></span>

<span data-ttu-id="cd4d8-470">このルールは、ランサムウェアを防止するために注意を払う傾向があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-470">The rule tends to err on the side of caution to prevent ransomware.</span></span>

> [!NOTE]
> <span data-ttu-id="cd4d8-471">このルールを [使用するには、クラウドによる保護](enable-cloud-protection-microsoft-defender-antivirus.md) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-471">You must [enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) to use this rule.</span></span>

<span data-ttu-id="cd4d8-472">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cd4d8-472">This rule was introduced in:</span></span>

- [<span data-ttu-id="cd4d8-473">Windows 10バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="cd4d8-473">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="cd4d8-474">Windowsサーバー、バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="cd4d8-474">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="cd4d8-475">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cd4d8-475">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="cd4d8-476">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="cd4d8-476">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="cd4d8-477">Intune 名: `Advanced ransomware protection`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-477">Intune name: `Advanced ransomware protection`</span></span>

<span data-ttu-id="cd4d8-478">Configuration Manager 名: `Use advanced protection against ransomware`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-478">Configuration Manager name: `Use advanced protection against ransomware`</span></span>

<span data-ttu-id="cd4d8-479">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span><span class="sxs-lookup"><span data-stu-id="cd4d8-479">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span></span>
