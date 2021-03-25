---
title: 攻撃表面の縮小ルールを使用してマルウェアの感染を防止する
description: 攻撃表面の縮小ルールは、悪用がアプリやスクリプトを使用してデバイスにマルウェアに感染するのを防ぐのに役立ちます。
keywords: 攻撃表面の縮小ルール、asr、hips、ホスト侵入防止システム、保護ルール、悪用防止、脆弱性対策、悪用、感染防止、Microsoft Defender for Endpoint、Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: 62f1f5f2d47482f642f00c870b3e0f3112f5f639
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185769"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a><span data-ttu-id="38d33-104">攻撃表面の縮小ルールを使用してマルウェアの感染を防止する</span><span class="sxs-lookup"><span data-stu-id="38d33-104">Use attack surface reduction rules to prevent malware infection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="38d33-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="38d33-105">**Applies to:**</span></span>
- [<span data-ttu-id="38d33-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="38d33-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="38d33-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38d33-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



## <a name="why-attack-surface-reduction-rules-are-important"></a><span data-ttu-id="38d33-108">攻撃表面の縮小ルールが重要な理由</span><span class="sxs-lookup"><span data-stu-id="38d33-108">Why attack surface reduction rules are important</span></span>

<span data-ttu-id="38d33-109">組織の攻撃表面には、攻撃者が組織のデバイスやネットワークを侵害する可能性があるすべての場所が含まれています。</span><span class="sxs-lookup"><span data-stu-id="38d33-109">Your organization's attack surface includes all the places where an attacker could compromise your organization's devices or networks.</span></span> <span data-ttu-id="38d33-110">攻撃の表面を減らすことは、組織のデバイスとネットワークを保護する手段であり、攻撃者は攻撃を実行する方法が少なくなっています。</span><span class="sxs-lookup"><span data-stu-id="38d33-110">Reducing your attack surface means protecting your organization's devices and network, which leaves attackers with fewer ways to perform attacks.</span></span> <span data-ttu-id="38d33-111">Microsoft Defender for Endpoint で攻撃表面の縮小ルールを構成すると役立ちます。</span><span class="sxs-lookup"><span data-stu-id="38d33-111">Configuring attack surface reduction rules in Microsoft Defender for Endpoint can help!</span></span>

<span data-ttu-id="38d33-112">攻撃表面の縮小ルールは、次のような特定のソフトウェア動作を対象とします。</span><span class="sxs-lookup"><span data-stu-id="38d33-112">Attack surface reduction rules target certain software behaviors, such as:</span></span>

- <span data-ttu-id="38d33-113">ファイルのダウンロードまたは実行を試みる実行可能ファイルとスクリプトを起動する。</span><span class="sxs-lookup"><span data-stu-id="38d33-113">Launching executable files and scripts that attempt to download or run files;</span></span>
- <span data-ttu-id="38d33-114">難読化されたスクリプトまたはその他の疑わしいスクリプトを実行する。そして</span><span class="sxs-lookup"><span data-stu-id="38d33-114">Running obfuscated or otherwise suspicious scripts; and</span></span> 
- <span data-ttu-id="38d33-115">通常の毎日の作業中にアプリが開始しない動作を実行します。</span><span class="sxs-lookup"><span data-stu-id="38d33-115">Performing behaviors that apps don't usually initiate during normal day-to-day work.</span></span>

<span data-ttu-id="38d33-116">このようなソフトウェアの動作は、正当なアプリケーションで見られる場合があります。ただし、これらの動作は、マルウェアを介して攻撃者によって悪用されるのが一般的なので、リスクが高いと見なされる場合が多い。</span><span class="sxs-lookup"><span data-stu-id="38d33-116">Such software behaviors are sometimes seen in legitimate applications; however, these behaviors are often considered risky because they are commonly abused by attackers through malware.</span></span> <span data-ttu-id="38d33-117">攻撃表面の縮小ルールは、リスクの高い動作を制限し、組織を安全に保つのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="38d33-117">Attack surface reduction rules can constrain risky behaviors and help keep your organization safe.</span></span>

<span data-ttu-id="38d33-118">攻撃表面の縮小ルールの構成の詳細については、「攻撃表面の縮小ルールを有効 [にする」を参照してください](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="38d33-118">For more information about configuring attack surface reduction rules, see [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

## <a name="assess-rule-impact-before-deployment"></a><span data-ttu-id="38d33-119">展開前にルールへの影響を評価する</span><span class="sxs-lookup"><span data-stu-id="38d33-119">Assess rule impact before deployment</span></span>  

<span data-ttu-id="38d33-120">攻撃表面の縮小ルールがネットワークに与える影響を評価するには、脅威と脆弱性の管理で、そのルールのセキュリティ推奨事項 [を開きます](https://docs.microsoft.com/windows/security/threat-protection/#tvm)。</span><span class="sxs-lookup"><span data-stu-id="38d33-120">You can assess how an attack surface reduction rule might affect your network by opening the security recommendation for that rule in [threat and vulnerability management](https://docs.microsoft.com/windows/security/threat-protection/#tvm).</span></span> 

:::image type="content" source="images/asrrecommendation.png" alt-text="攻撃表面の縮小ルールのセキュリティ reco":::

<span data-ttu-id="38d33-122">[推奨事項の詳細] ウィンドウで、ユーザーの影響を確認して、生産性に悪影響を及ぼさずに、ブロック モードでルールを有効にする新しいポリシーを受け入れ可能なデバイスの割合を確認します。</span><span class="sxs-lookup"><span data-stu-id="38d33-122">In the recommendation details pane, check for user impact to determine what percentage of your devices can accept a new policy enabling the rule in blocking mode without adversely affecting productivity.</span></span>

## <a name="audit-mode-for-evaluation"></a><span data-ttu-id="38d33-123">評価の監査モード</span><span class="sxs-lookup"><span data-stu-id="38d33-123">Audit mode for evaluation</span></span>

<span data-ttu-id="38d33-124">監査 [モードを使用して](audit-windows-defender.md) 、攻撃表面の縮小ルールが有効になっている場合に組織に与える影響を評価します。</span><span class="sxs-lookup"><span data-stu-id="38d33-124">Use [audit mode](audit-windows-defender.md) to evaluate how attack surface reduction rules would affect your organization if they were enabled.</span></span> <span data-ttu-id="38d33-125">監査モードですべてのルールを最初に実行して、そのルールがビジネスライン アプリケーションに与える影響を理解できます。</span><span class="sxs-lookup"><span data-stu-id="38d33-125">Run all rules in audit mode first so you can understand how they affect your line-of-business applications.</span></span> <span data-ttu-id="38d33-126">多くの業務用アプリケーションは、限られたセキュリティ上の懸念を持って記述され、マルウェアに似た方法でタスクを実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38d33-126">Many line-of-business applications are written with limited security concerns, and they might perform tasks in ways that seem similar to malware.</span></span> <span data-ttu-id="38d33-127">監査データを監視し、必要なアプリケーションの [除外](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) を追加することで、生産性を低下させずに攻撃表面の縮小ルールを展開できます。</span><span class="sxs-lookup"><span data-stu-id="38d33-127">By monitoring audit data and [adding exclusions](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) for necessary applications, you can deploy attack surface reduction rules without reducing productivity.</span></span>

## <a name="warn-mode-for-users"></a><span data-ttu-id="38d33-128">ユーザーの警告モード</span><span class="sxs-lookup"><span data-stu-id="38d33-128">Warn mode for users</span></span>

<span data-ttu-id="38d33-129">(**NEW**!)警告モード機能の前に、有効になっている攻撃表面の縮小ルールを監査モードまたはブロック モードに設定できます。</span><span class="sxs-lookup"><span data-stu-id="38d33-129">(**NEW**!) Prior to warn mode capabilities, attack surface reduction rules that are enabled could be set to either audit mode or block mode.</span></span> <span data-ttu-id="38d33-130">新しい警告モードでは、攻撃表面の縮小ルールによってコンテンツがブロックされるたびに、コンテンツがブロックされたかどうかを示すダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38d33-130">With the new warn mode, whenever content is blocked by an attack surface reduction rule, users see a dialog box that indicates the content is blocked.</span></span> <span data-ttu-id="38d33-131">ダイアログ ボックスには、コンテンツのブロックを解除するオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="38d33-131">The dialog box also offers the user an option to unblock the content.</span></span> <span data-ttu-id="38d33-132">その後、ユーザーはアクションを再試行し、操作が完了します。</span><span class="sxs-lookup"><span data-stu-id="38d33-132">The user can then retry their action, and the operation completes.</span></span> <span data-ttu-id="38d33-133">ユーザーがコンテンツのブロックを解除すると、コンテンツは 24 時間ブロック解除されたままで、その後ブロックが再開されます。</span><span class="sxs-lookup"><span data-stu-id="38d33-133">When a user unblocks content, the content remains unblocked for 24 hours, and then blocking resumes.</span></span>

<span data-ttu-id="38d33-134">警告モードは、ユーザーが自分のタスクを実行するために必要なコンテンツにアクセスするのを防ぐことなく、組織が攻撃表面の縮小ルールを設定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="38d33-134">Warn mode helps your organization have attack surface reduction rules in place without preventing users from accessing the content they need to perform their tasks.</span></span> 

### <a name="requirements-for-warn-mode-to-work"></a><span data-ttu-id="38d33-135">警告モードが機能する要件</span><span class="sxs-lookup"><span data-stu-id="38d33-135">Requirements for warn mode to work</span></span>

<span data-ttu-id="38d33-136">警告モードは、次のバージョンの Windows を実行しているデバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="38d33-136">Warn mode is supported on devices running the following versions of Windows:</span></span>
- <span data-ttu-id="38d33-137">[Windows 10 バージョン 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) 以降</span><span class="sxs-lookup"><span data-stu-id="38d33-137">[Windows 10, version 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) or later</span></span>
- <span data-ttu-id="38d33-138">[Windows Server バージョン 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809) 以降</span><span class="sxs-lookup"><span data-stu-id="38d33-138">[Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809) or later</span></span>
 
<span data-ttu-id="38d33-139">Microsoft Defender ウイルス対策は、アクティブ モードでリアルタイム保護を使用して [実行されている必要があります](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)。</span><span class="sxs-lookup"><span data-stu-id="38d33-139">Microsoft Defender Antivirus must be running with real-time protection in [Active mode](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state).</span></span>

<span data-ttu-id="38d33-140">さらに [、Microsoft Defender ウイルス対策とマルウェア対策の更新プログラムがインストールされていることを](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) 確認します。</span><span class="sxs-lookup"><span data-stu-id="38d33-140">In addition, make sure [Microsoft Defender Antivirus and antimalware updates](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) are installed.</span></span>
- <span data-ttu-id="38d33-141">プラットフォームリリースの最小要件: `4.18.2008.9`</span><span class="sxs-lookup"><span data-stu-id="38d33-141">Minimum platform release requirement: `4.18.2008.9`</span></span>  
- <span data-ttu-id="38d33-142">エンジンリリースの最小要件: `1.1.17400.5`</span><span class="sxs-lookup"><span data-stu-id="38d33-142">Minimum engine release requirement: `1.1.17400.5`</span></span>

<span data-ttu-id="38d33-143">詳細と更新プログラムの取得については [、「Update for Microsoft Defender マルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="38d33-143">For more information and to get your updates, see [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).</span></span>

### <a name="cases-where-warn-mode-is-not-supported"></a><span data-ttu-id="38d33-144">警告モードがサポートされていない場合</span><span class="sxs-lookup"><span data-stu-id="38d33-144">Cases where warn mode is not supported</span></span>

<span data-ttu-id="38d33-145">警告モードは、次の攻撃表面縮小ルールではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="38d33-145">Warn mode is not supported for the following attack surface reduction rules:</span></span>

- <span data-ttu-id="38d33-146">[ダウンロードした実行可能コンテンツ (GUID)](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)の起動から JavaScript または VBScript をブロックする `d3e037e1-3eb8-44c8-a917-57927947596d`</span><span class="sxs-lookup"><span data-stu-id="38d33-146">[Block JavaScript or VBScript from launching downloaded executable content](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`)</span></span>
- <span data-ttu-id="38d33-147">[WMI イベント サブスクリプション (GUID) による永続](#block-persistence-through-wmi-event-subscription) 化をブロック `e6db77e5-3df2-4cf1-b95a-636979351e5b` する</span><span class="sxs-lookup"><span data-stu-id="38d33-147">[Block persistence through WMI event subscription](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`)</span></span>
- <span data-ttu-id="38d33-148">[ランサムウェアに対する高度な保護を使用](#use-advanced-protection-against-ransomware) する `c1db55ab-c21a-4637-bb3f-a12568109d35` (GUID)</span><span class="sxs-lookup"><span data-stu-id="38d33-148">[Use advanced protection against ransomware](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`)</span></span>

<span data-ttu-id="38d33-149">また、以前のバージョンの Windows を実行しているデバイスでは、警告モードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="38d33-149">In addition, warn mode is not supported on devices running older versions of Windows.</span></span> <span data-ttu-id="38d33-150">このような場合、警告モードで実行するように構成された攻撃表面の縮小ルールは、ブロック モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="38d33-150">In those cases, attack surface reduction rules that are configured to run in warn mode will run in block mode.</span></span>

## <a name="notifications-and-alerts"></a><span data-ttu-id="38d33-151">通知とアラート</span><span class="sxs-lookup"><span data-stu-id="38d33-151">Notifications and alerts</span></span>

<span data-ttu-id="38d33-152">攻撃表面の縮小ルールがトリガーされるたびに、デバイスに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38d33-152">Whenever an attack surface reduction rule is triggered, a notification is displayed on the device.</span></span> <span data-ttu-id="38d33-153">通知は [、会社の詳細](customize-attack-surface-reduction.md#customize-the-notification) と連絡先情報でカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="38d33-153">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span>

<span data-ttu-id="38d33-154">さらに、特定の攻撃表面の縮小ルールがトリガーされると、アラートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="38d33-154">In addition, when certain attack surface reduction rules are triggered, alerts are generated.</span></span> 

<span data-ttu-id="38d33-155">通知と生成されるアラートは、Microsoft Defender セキュリティ センター ( ) と Microsoft 365 セキュリティ センター [https://securitycenter.windows.com](https://securitycenter.windows.com) ( ) で表示できます [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="38d33-155">Notifications and any alerts that are generated can be viewed in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and in the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span>

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a><span data-ttu-id="38d33-156">高度な狩猟と攻撃表面の縮小イベント</span><span class="sxs-lookup"><span data-stu-id="38d33-156">Advanced hunting and attack surface reduction events</span></span>

<span data-ttu-id="38d33-157">高度な検索を使用して、攻撃表面の縮小イベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="38d33-157">You can use advanced hunting to view attack surface reduction events.</span></span> <span data-ttu-id="38d33-158">受信データの量を合理化するために、高度な検索では、1 時間ごとに一意のプロセスのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="38d33-158">To streamline the volume of incoming data, only unique processes for each hour are viewable with advanced hunting.</span></span> <span data-ttu-id="38d33-159">攻撃表面の縮小イベントの時間は、1 時間以内に初めてイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38d33-159">The time of an attack surface reduction event is the first time that event is seen within the hour.</span></span>

<span data-ttu-id="38d33-160">たとえば、午後 2 時の間に 10 台のデバイスで攻撃表面の縮小イベントが発生するとします。</span><span class="sxs-lookup"><span data-stu-id="38d33-160">For example, suppose that an attack surface reduction event occurs on 10 devices during the 2:00 PM hour.</span></span> <span data-ttu-id="38d33-161">最初のイベントが 2:15、最後の 2:45 に発生したとします。</span><span class="sxs-lookup"><span data-stu-id="38d33-161">Suppose that the first event occurred at 2:15, and the last at 2:45.</span></span> <span data-ttu-id="38d33-162">高度な検索では、そのイベントのインスタンスが 1 つ表示されます (実際には 10 台のデバイスで発生した場合でも)、タイムスタンプは午後 2 時 15 分になります。</span><span class="sxs-lookup"><span data-stu-id="38d33-162">With advanced hunting, you'll see one instance of that event (even though it actually occurred on 10 devices), and its timestamp will be 2:15 PM.</span></span> 

<span data-ttu-id="38d33-163">高度な狩猟の詳細については、「高度な狩猟 [を使用して脅威を事前に検出する」を参照してください](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="38d33-163">For more information about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="attack-surface-reduction-features-across-windows-versions"></a><span data-ttu-id="38d33-164">Windows バージョン全体の攻撃表面の縮小機能</span><span class="sxs-lookup"><span data-stu-id="38d33-164">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="38d33-165">次のエディションとバージョンの Windows を実行しているデバイスに対して攻撃表面の縮小ルールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="38d33-165">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="38d33-166">Windows 10 Pro [バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 以降</span><span class="sxs-lookup"><span data-stu-id="38d33-166">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="38d33-167">Windows 10 Enterprise バージョン [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 以降</span><span class="sxs-lookup"><span data-stu-id="38d33-167">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="38d33-168">Windows Server バージョン [1803 (半期チャネル)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) 以降</span><span class="sxs-lookup"><span data-stu-id="38d33-168">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="38d33-169">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="38d33-169">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="38d33-170">攻撃表面の縮小ルールは [Windows E5](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses)ライセンスを必要としますが、Windows E5 を使用している場合は、高度な管理機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="38d33-170">Although attack surface reduction rules don't require a [Windows E5 license](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="38d33-171">Windows E5 でのみ使用できるこれらの機能には [、Defender for Endpoint](microsoft-defender-endpoint.md)で使用できる監視、分析、ワークフロー、 [および Microsoft 365](https://docs.microsoft.com/microsoft-365/security/defender/overview-security-center)セキュリティ センターのレポート機能と構成機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="38d33-171">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in [Defender for Endpoint](microsoft-defender-endpoint.md), as well as reporting and configuration capabilities in the [Microsoft 365 security center](https://docs.microsoft.com/microsoft-365/security/defender/overview-security-center).</span></span> <span data-ttu-id="38d33-172">これらの高度な機能は、Windows Professional または Windows E3 ライセンスでは使用できません。ただし、これらのライセンスがある場合は、イベント ビューアーと Microsoft Defender ウイルス対策ログを使用して攻撃表面の縮小ルール イベントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="38d33-172">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

## <a name="review-attack-surface-reduction-events-in-the-microsoft-defender-security-center"></a><span data-ttu-id="38d33-173">Microsoft Defender セキュリティ センターで攻撃表面の縮小イベントを確認する</span><span class="sxs-lookup"><span data-stu-id="38d33-173">Review attack surface reduction events in the Microsoft Defender Security Center</span></span>

<span data-ttu-id="38d33-174">Defender for Endpoint は、アラート調査シナリオの一環として、イベントとブロックの詳細なレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="38d33-174">Defender for Endpoint provides detailed reporting for events and blocks as part of alert investigation scenarios.</span></span>

<span data-ttu-id="38d33-175">高度な検索を使用して Defender for Endpoint データ [を照会できます](advanced-hunting-query-language.md)。</span><span class="sxs-lookup"><span data-stu-id="38d33-175">You can query Defender for Endpoint data by using [advanced hunting](advanced-hunting-query-language.md).</span></span> <span data-ttu-id="38d33-176">監査モードを実行している [場合](audit-windows-defender.md)は、高度な検索を使用して、攻撃表面の縮小ルールが環境に与える影響を理解できます。</span><span class="sxs-lookup"><span data-stu-id="38d33-176">If you're running [audit mode](audit-windows-defender.md), you can use advanced hunting to understand how attack surface reduction rules could affect your environment.</span></span>

<span data-ttu-id="38d33-177">クエリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="38d33-177">Here is an example query:</span></span>

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="38d33-178">Windows イベント ビューアーで攻撃表面の縮小イベントを確認する</span><span class="sxs-lookup"><span data-stu-id="38d33-178">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="38d33-179">Windows イベント ログを確認して、攻撃表面の縮小ルールによって生成されたイベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="38d33-179">You can review the Windows event log to view events generated by attack surface reduction rules:</span></span>

1. <span data-ttu-id="38d33-180">評価パッケージ [をダウンロードし](https://aka.ms/mp7z2w) 、デバイス上 *cfa-events.xmlアクセスしやすい* 場所にファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="38d33-180">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>
2. <span data-ttu-id="38d33-181">[スタート] メニューに *「イベント ビューアー*」という単語を入力して、Windows イベント ビューアーを開きます。</span><span class="sxs-lookup"><span data-stu-id="38d33-181">Enter the words, *Event Viewer*, into the Start menu to open the Windows Event Viewer.</span></span>
3. <span data-ttu-id="38d33-182">[アクション **] で**、[カスタム **ビューのインポート.... を選択します**。</span><span class="sxs-lookup"><span data-stu-id="38d33-182">Under **Actions**, select **Import custom view...**.</span></span>
4. <span data-ttu-id="38d33-183">抽出された場所 *cfa-events.xml* ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="38d33-183">Select the file *cfa-events.xml* from where it was extracted.</span></span> <span data-ttu-id="38d33-184">または [、XML を直接コピーします](event-views.md)。</span><span class="sxs-lookup"><span data-stu-id="38d33-184">Alternatively, [copy the XML directly](event-views.md).</span></span>
5. <span data-ttu-id="38d33-185">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38d33-185">Select **OK**.</span></span>

<span data-ttu-id="38d33-186">イベントをフィルター処理して、次のイベントのみを表示するカスタム ビューを作成できます。そのすべては、フォルダー アクセスの制御に関連しています。</span><span class="sxs-lookup"><span data-stu-id="38d33-186">You can create a custom view that filters events to only show the following events, all of which are related to controlled folder access:</span></span>

|<span data-ttu-id="38d33-187">イベント ID</span><span class="sxs-lookup"><span data-stu-id="38d33-187">Event ID</span></span> | <span data-ttu-id="38d33-188">説明</span><span class="sxs-lookup"><span data-stu-id="38d33-188">Description</span></span> |
|:---|:---|
|<span data-ttu-id="38d33-189">5007</span><span class="sxs-lookup"><span data-stu-id="38d33-189">5007</span></span> | <span data-ttu-id="38d33-190">設定が変更された場合のイベント</span><span class="sxs-lookup"><span data-stu-id="38d33-190">Event when settings are changed</span></span> |
|<span data-ttu-id="38d33-191">1121</span><span class="sxs-lookup"><span data-stu-id="38d33-191">1121</span></span> | <span data-ttu-id="38d33-192">ブロック モードでルールが発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="38d33-192">Event when rule fires in Block-mode</span></span> |
|<span data-ttu-id="38d33-193">1122</span><span class="sxs-lookup"><span data-stu-id="38d33-193">1122</span></span> | <span data-ttu-id="38d33-194">監査モードでルールが発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="38d33-194">Event when rule fires in Audit-mode</span></span> |

<span data-ttu-id="38d33-195">イベント ログの攻撃表面の縮小イベント用にリストされている "エンジンバージョン" は、オペレーティング システムではなく Defender for Endpoint によって生成されます。</span><span class="sxs-lookup"><span data-stu-id="38d33-195">The "engine version" listed for attack surface reduction events in the event log, is generated by Defender for Endpoint, not by the operating system.</span></span> <span data-ttu-id="38d33-196">Defender for Endpoint は Windows 10 と統合されています。そのため、この機能は Windows 10 がインストールされているすべてのデバイスで動作します。</span><span class="sxs-lookup"><span data-stu-id="38d33-196">Defender for Endpoint is integrated with Windows 10, so this feature works on all devices with Windows 10 installed.</span></span>

## <a name="attack-surface-reduction-rules"></a><span data-ttu-id="38d33-197">攻撃面の減少ルール</span><span class="sxs-lookup"><span data-stu-id="38d33-197">Attack surface reduction rules</span></span>

<span data-ttu-id="38d33-198">次の表とサブセクションでは、15 の攻撃表面の縮小ルールのそれぞれについて説明します。</span><span class="sxs-lookup"><span data-stu-id="38d33-198">The following table and subsections describe each of the 15 attack surface reduction rules.</span></span> <span data-ttu-id="38d33-199">攻撃表面の縮小ルールは、ルール名によってアルファベット順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="38d33-199">The attack surface reduction rules are listed in alphabetical order, by rule name.</span></span> 

<span data-ttu-id="38d33-200">グループ ポリシーまたは PowerShell を使用して攻撃表面の縮小ルールを構成する場合は、GUID が必要です。</span><span class="sxs-lookup"><span data-stu-id="38d33-200">If you are configuring attack surface reduction rules by using Group Policy or PowerShell, you'll need the GUIDs.</span></span> <span data-ttu-id="38d33-201">一方、Microsoft Endpoint Manager または Microsoft Intune を使用する場合は、GUID は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="38d33-201">On the other hand, if you use Microsoft Endpoint Manager or Microsoft Intune, you do not need the GUIDs.</span></span>


| <span data-ttu-id="38d33-202">ルールの名前</span><span class="sxs-lookup"><span data-stu-id="38d33-202">Rule name</span></span> | <span data-ttu-id="38d33-203">GUID</span><span class="sxs-lookup"><span data-stu-id="38d33-203">GUID</span></span> | <span data-ttu-id="38d33-204">ファイル&フォルダーの除外</span><span class="sxs-lookup"><span data-stu-id="38d33-204">File & folder exclusions</span></span> | <span data-ttu-id="38d33-205">サポートされる最小 OS</span><span class="sxs-lookup"><span data-stu-id="38d33-205">Minimum OS supported</span></span> |
|:-----|:-----:|:-----|:-----|
|[<span data-ttu-id="38d33-206">Adobe Reader の子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-206">Block Adobe Reader from creating child processes</span></span>](#block-adobe-reader-from-creating-child-processes) | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` | <span data-ttu-id="38d33-207">サポート済み</span><span class="sxs-lookup"><span data-stu-id="38d33-207">Supported</span></span> | <span data-ttu-id="38d33-208">[Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="38d33-208">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="38d33-209">すべてのアプリケーションOffice子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-209">Block all Office applications from creating child processes</span></span>](#block-all-office-applications-from-creating-child-processes) | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` | <span data-ttu-id="38d33-210">サポート済み</span><span class="sxs-lookup"><span data-stu-id="38d33-210">Supported</span></span> | <span data-ttu-id="38d33-211">[Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="38d33-211">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="38d33-212">Windows ローカル セキュリティ機関サブシステムからの資格情報の盗用をブロックする (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="38d33-212">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` | <span data-ttu-id="38d33-213">サポート済み</span><span class="sxs-lookup"><span data-stu-id="38d33-213">Supported</span></span> | <span data-ttu-id="38d33-214">[Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="38d33-214">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="38d33-215">メール クライアントと Web メールから実行可能なコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-215">Block executable content from email client and webmail</span></span>](#block-executable-content-from-email-client-and-webmail) | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` | <span data-ttu-id="38d33-216">サポート済み</span><span class="sxs-lookup"><span data-stu-id="38d33-216">Supported</span></span> | <span data-ttu-id="38d33-217">[Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="38d33-217">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="38d33-218">有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-218">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | `01443614-cd74-433a-b99e-2ecdc07bfc25` | <span data-ttu-id="38d33-219">サポート済み</span><span class="sxs-lookup"><span data-stu-id="38d33-219">Supported</span></span> | <span data-ttu-id="38d33-220">[Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="38d33-220">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="38d33-221">難読化される可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-221">Block execution of potentially obfuscated scripts</span></span>](#block-execution-of-potentially-obfuscated-scripts) | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` | <span data-ttu-id="38d33-222">サポート済み</span><span class="sxs-lookup"><span data-stu-id="38d33-222">Supported</span></span> | <span data-ttu-id="38d33-223">[Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="38d33-223">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="38d33-224">JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-224">Block JavaScript or VBScript from launching downloaded executable content</span></span>](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | `D3E037E1-3EB8-44C8-A917-57927947596D` | <span data-ttu-id="38d33-225">サポート済み</span><span class="sxs-lookup"><span data-stu-id="38d33-225">Supported</span></span> | <span data-ttu-id="38d33-226">[Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="38d33-226">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="38d33-227">実行可能Office作成するアプリケーションをブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-227">Block Office applications from creating executable content</span></span>](#block-office-applications-from-creating-executable-content) | `3B576869-A4EC-4529-8536-B80A7769E899` | <span data-ttu-id="38d33-228">サポート済み</span><span class="sxs-lookup"><span data-stu-id="38d33-228">Supported</span></span> | <span data-ttu-id="38d33-229">[Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="38d33-229">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="38d33-230">アプリケーションOffice他のプロセスへのコードの挿入をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-230">Block Office applications from injecting code into other processes</span></span>](#block-office-applications-from-injecting-code-into-other-processes) | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` | <span data-ttu-id="38d33-231">サポート済み</span><span class="sxs-lookup"><span data-stu-id="38d33-231">Supported</span></span> | <span data-ttu-id="38d33-232">[Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="38d33-232">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="38d33-233">通信Office子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-233">Block Office communication application from creating child processes</span></span>](#block-office-communication-application-from-creating-child-processes) |`26190899-1602-49e8-8b27-eb1d0a1ce869` |<span data-ttu-id="38d33-234">サポート済み</span><span class="sxs-lookup"><span data-stu-id="38d33-234">Supported</span></span> |<span data-ttu-id="38d33-235">[Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="38d33-235">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>  |
|[<span data-ttu-id="38d33-236">WMI イベント サブスクリプションによる永続化のブロック</span><span class="sxs-lookup"><span data-stu-id="38d33-236">Block persistence through WMI event subscription</span></span>](#block-persistence-through-wmi-event-subscription) | `e6db77e5-3df2-4cf1-b95a-636979351e5b` | <span data-ttu-id="38d33-237">非サポート</span><span class="sxs-lookup"><span data-stu-id="38d33-237">Not supported</span></span> | <span data-ttu-id="38d33-238">[Windows 10 バージョン 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) (ビルド 18362) 以上</span><span class="sxs-lookup"><span data-stu-id="38d33-238">[Windows 10, version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) (build 18362) or greater</span></span> |
|[<span data-ttu-id="38d33-239">PSExec および WMI コマンドから発生するプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-239">Block process creations originating from PSExec and WMI commands</span></span>](#block-process-creations-originating-from-psexec-and-wmi-commands) | `d1e49aac-8f56-4280-b9ba-993a6d77406c` | <span data-ttu-id="38d33-240">サポート済み</span><span class="sxs-lookup"><span data-stu-id="38d33-240">Supported</span></span> | <span data-ttu-id="38d33-241">[Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="38d33-241">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="38d33-242">USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-242">Block untrusted and unsigned processes that run from USB</span></span>](#block-untrusted-and-unsigned-processes-that-run-from-usb) | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` | <span data-ttu-id="38d33-243">サポート済み</span><span class="sxs-lookup"><span data-stu-id="38d33-243">Supported</span></span> | <span data-ttu-id="38d33-244">[Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="38d33-244">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="38d33-245">Win32 API 呼び出しをブロックOfficeマクロ</span><span class="sxs-lookup"><span data-stu-id="38d33-245">Block Win32 API calls from Office macros</span></span>](#block-win32-api-calls-from-office-macros) | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` | <span data-ttu-id="38d33-246">サポート済み</span><span class="sxs-lookup"><span data-stu-id="38d33-246">Supported</span></span> | <span data-ttu-id="38d33-247">[Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="38d33-247">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |
|[<span data-ttu-id="38d33-248">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="38d33-248">Use advanced protection against ransomware</span></span>](#use-advanced-protection-against-ransomware) | `c1db55ab-c21a-4637-bb3f-a12568109d35` | <span data-ttu-id="38d33-249">サポート済み</span><span class="sxs-lookup"><span data-stu-id="38d33-249">Supported</span></span> | <span data-ttu-id="38d33-250">[Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上</span><span class="sxs-lookup"><span data-stu-id="38d33-250">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span> |

### <a name="block-adobe-reader-from-creating-child-processes"></a><span data-ttu-id="38d33-251">Adobe Reader の子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-251">Block Adobe Reader from creating child processes</span></span>

<span data-ttu-id="38d33-252">このルールは、Adobe Reader によるプロセスの作成をブロックすることで攻撃を防止します。</span><span class="sxs-lookup"><span data-stu-id="38d33-252">This rule prevents attacks by blocking Adobe Reader from creating processes.</span></span>

<span data-ttu-id="38d33-253">ソーシャル エンジニアリングや悪用を通じて、マルウェアはペイロードをダウンロードして起動し、Adobe Reader から抜け出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38d33-253">Through social engineering or exploits, malware can download and launch payloads, and break out of Adobe Reader.</span></span> <span data-ttu-id="38d33-254">Adobe Reader によって子プロセスが生成されるのをブロックすることで、子プロセスをベクターとして使用しようとするマルウェアが拡散を防止します。</span><span class="sxs-lookup"><span data-stu-id="38d33-254">By blocking child processes from being generated by Adobe Reader, malware attempting to use it as a vector are prevented from spreading.</span></span>

<span data-ttu-id="38d33-255">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="38d33-255">This rule was introduced in:</span></span> 
- [<span data-ttu-id="38d33-256">Windows 10 バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="38d33-256">Windows 10, version 1809</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="38d33-257">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="38d33-257">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="38d33-258">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="38d33-258">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="38d33-259">Intune 名: `Process creation from Adobe Reader (beta)`</span><span class="sxs-lookup"><span data-stu-id="38d33-259">Intune name: `Process creation from Adobe Reader (beta)`</span></span>

<span data-ttu-id="38d33-260">Configuration Manager 名: まだ使用できません</span><span class="sxs-lookup"><span data-stu-id="38d33-260">Configuration Manager name: Not yet available</span></span>

<span data-ttu-id="38d33-261">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span><span class="sxs-lookup"><span data-stu-id="38d33-261">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span></span>

### <a name="block-all-office-applications-from-creating-child-processes"></a><span data-ttu-id="38d33-262">すべてのアプリケーションOffice子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-262">Block all Office applications from creating child processes</span></span>

<span data-ttu-id="38d33-263">このルールは、Officeプロセスの作成をブロックします。</span><span class="sxs-lookup"><span data-stu-id="38d33-263">This rule blocks Office apps from creating child processes.</span></span> <span data-ttu-id="38d33-264">Officeには、Word、Excel、PowerPoint、OneNote、Access が含まれます。</span><span class="sxs-lookup"><span data-stu-id="38d33-264">Office apps include Word, Excel, PowerPoint, OneNote, and Access.</span></span>

<span data-ttu-id="38d33-265">悪意のある子プロセスを作成する方法は、一般的なマルウェア戦略です。</span><span class="sxs-lookup"><span data-stu-id="38d33-265">Creating malicious child processes is a common malware strategy.</span></span> <span data-ttu-id="38d33-266">マルウェアがベクターとしてOfficeマルウェアは、VBA マクロを実行し、コードを悪用して、より多くのペイロードをダウンロードして実行しようとする場合が多い。</span><span class="sxs-lookup"><span data-stu-id="38d33-266">Malware that abuse Office as a vector often run VBA macros and exploit code to download and attempt to run more payloads.</span></span> <span data-ttu-id="38d33-267">ただし、一部の正当な業務行アプリケーションでは、コマンド プロンプトの生成や PowerShell を使用してレジストリ設定を構成するなどの、適切な目的で子プロセスを生成する場合があります。</span><span class="sxs-lookup"><span data-stu-id="38d33-267">However, some legitimate line-of-business applications might also generate child processes for benign purposes, such as spawning a command prompt or using PowerShell to configure registry settings.</span></span>

<span data-ttu-id="38d33-268">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="38d33-268">This rule was introduced in:</span></span> 
- [<span data-ttu-id="38d33-269">Windows 10 バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="38d33-269">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="38d33-270">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="38d33-270">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="38d33-271">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="38d33-271">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="38d33-272">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="38d33-272">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="38d33-273">Intune 名: `Office apps launching child processes`</span><span class="sxs-lookup"><span data-stu-id="38d33-273">Intune name: `Office apps launching child processes`</span></span>

<span data-ttu-id="38d33-274">Configuration Manager 名: `Block Office application from creating child processes`</span><span class="sxs-lookup"><span data-stu-id="38d33-274">Configuration Manager name: `Block Office application from creating child processes`</span></span>

<span data-ttu-id="38d33-275">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span><span class="sxs-lookup"><span data-stu-id="38d33-275">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span></span>

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a><span data-ttu-id="38d33-276">Windows ローカル セキュリティ機関サブシステムからの資格情報の盗用をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-276">Block credential stealing from the Windows local security authority subsystem</span></span>

<span data-ttu-id="38d33-277">このルールは、ローカル セキュリティ機関サブシステム サービス (LSASS) をロックダウンすることで、資格情報の盗用を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="38d33-277">This rule helps prevent credential stealing, by locking down Local Security Authority Subsystem Service (LSASS).</span></span>

<span data-ttu-id="38d33-278">LSASS は、Windows コンピューターでサインインするユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="38d33-278">LSASS authenticates users who sign in on a Windows computer.</span></span> <span data-ttu-id="38d33-279">Windows 10 の Microsoft Defender Credential Guard は、通常、LSASS から資格情報を抽出しようとする試みを防止します。</span><span class="sxs-lookup"><span data-stu-id="38d33-279">Microsoft Defender Credential Guard in Windows 10 normally prevents attempts to extract credentials from LSASS.</span></span> <span data-ttu-id="38d33-280">ただし、一部の組織では、カスタム スマートカード ドライバーやローカル セキュリティ機関 (LSA) に読み込む他のプログラムとの互換性の問題により、すべてのコンピューターで Credential Guard を有効にできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="38d33-280">However, some organizations can't enable Credential Guard on all of their computers because of compatibility issues with custom smartcard drivers or other programs that load into the Local Security Authority (LSA).</span></span> <span data-ttu-id="38d33-281">このような場合、攻撃者は Mimikatz のようなハッキング ツールを使用して、LSASS からクリアテキスト パスワードと NTLM ハッシュをスクレイピングできます。</span><span class="sxs-lookup"><span data-stu-id="38d33-281">In these cases, attackers can use hack tools like Mimikatz to scrape cleartext passwords and NTLM hashes from LSASS.</span></span>

> [!NOTE]
> <span data-ttu-id="38d33-282">一部のアプリでは、実行中のすべてのプロセスを列挙し、網羅的なアクセス許可を使用して開きます。</span><span class="sxs-lookup"><span data-stu-id="38d33-282">In some apps, the code enumerates all running processes and attempts to open them with exhaustive permissions.</span></span> <span data-ttu-id="38d33-283">このルールは、アプリのプロセスのオープン アクションを拒否し、詳細をセキュリティ イベント ログに記録します。</span><span class="sxs-lookup"><span data-stu-id="38d33-283">This rule denies the app's process open action and logs the details to the security event log.</span></span> <span data-ttu-id="38d33-284">このルールでは、多くのノイズが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38d33-284">This rule can generate a lot of noise.</span></span> <span data-ttu-id="38d33-285">LSASS を列挙するだけで、機能に実際の影響がないアプリがある場合は、除外リストに追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="38d33-285">If you have an app that simply enumerates LSASS, but has no real impact in functionality, there is NO need to add it to the exclusion list.</span></span> <span data-ttu-id="38d33-286">それ自体では、このイベント ログ エントリは必ずしも悪意のある脅威を示すとは限りません。</span><span class="sxs-lookup"><span data-stu-id="38d33-286">By itself, this event log entry doesn't necessarily indicate a malicious threat.</span></span>

<span data-ttu-id="38d33-287">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="38d33-287">This rule was introduced in:</span></span>
- [<span data-ttu-id="38d33-288">Windows 10 バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="38d33-288">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="38d33-289">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="38d33-289">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="38d33-290">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="38d33-290">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="38d33-291">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="38d33-291">Configuration Manager CB 1802</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="38d33-292">Intune 名: `Flag credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="38d33-292">Intune name: `Flag credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="38d33-293">Configuration Manager 名: `Block credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="38d33-293">Configuration Manager name: `Block credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="38d33-294">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span><span class="sxs-lookup"><span data-stu-id="38d33-294">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span></span>

### <a name="block-executable-content-from-email-client-and-webmail"></a><span data-ttu-id="38d33-295">メール クライアントと Web メールから実行可能なコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-295">Block executable content from email client and webmail</span></span>

<span data-ttu-id="38d33-296">このルールは、次のファイルの種類が、Microsoft Outlook アプリケーション内で開いた電子メール、または他の一般的な webmail プロバイダー Outlook.com から起動をブロックします。</span><span class="sxs-lookup"><span data-stu-id="38d33-296">This rule blocks the following file types from launching from email opened within the Microsoft Outlook application, or Outlook.com and other popular webmail providers:</span></span>

- <span data-ttu-id="38d33-297">実行可能ファイル (.exe、.dll、.scr など)</span><span class="sxs-lookup"><span data-stu-id="38d33-297">Executable files (such as .exe, .dll, or .scr)</span></span>
- <span data-ttu-id="38d33-298">スクリプト ファイル (PowerShell .ps、Visual Basic .vbs、JavaScript .js ファイルなど)</span><span class="sxs-lookup"><span data-stu-id="38d33-298">Script files (such as a PowerShell .ps, Visual Basic .vbs, or JavaScript .js file)</span></span>

<span data-ttu-id="38d33-299">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="38d33-299">This rule was introduced in:</span></span> 
- [<span data-ttu-id="38d33-300">Windows 10 バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="38d33-300">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="38d33-301">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="38d33-301">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="38d33-302">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="38d33-302">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="38d33-303">Microsoft Endpoint Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="38d33-303">Microsoft Endpoint Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="38d33-304">Intune 名: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="38d33-304">Intune name: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span></span>

<span data-ttu-id="38d33-305">Microsoft Endpoint Manager 名: `Block executable content from email client and webmail`</span><span class="sxs-lookup"><span data-stu-id="38d33-305">Microsoft Endpoint Manager name: `Block executable content from email client and webmail`</span></span>

<span data-ttu-id="38d33-306">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span><span class="sxs-lookup"><span data-stu-id="38d33-306">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span></span>

> [!NOTE]
> <span data-ttu-id="38d33-307">[メール **クライアントと Web メールからの** 実行可能なコンテンツをブロックする] というルールには、使用するアプリケーションに応じて、次の別の説明があります。</span><span class="sxs-lookup"><span data-stu-id="38d33-307">The rule **Block executable content from email client and webmail** has the following alternative descriptions, depending on which application you use:</span></span>
> - <span data-ttu-id="38d33-308">Intune (構成プロファイル): 電子メール (Web メール/メール クライアント) から削除された実行可能コンテンツ (exe、dll、ps、js、vbs など) の実行 (例外なし)。</span><span class="sxs-lookup"><span data-stu-id="38d33-308">Intune (Configuration Profiles): Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions).</span></span>
> - <span data-ttu-id="38d33-309">エンドポイント マネージャー: 電子メールおよび Web メール クライアントからの実行可能なコンテンツのダウンロードをブロックします。</span><span class="sxs-lookup"><span data-stu-id="38d33-309">Endpoint Manager: Block executable content download from email and webmail clients.</span></span>
> - <span data-ttu-id="38d33-310">グループ ポリシー: 電子メール クライアントと Web メールから実行可能なコンテンツをブロックします。</span><span class="sxs-lookup"><span data-stu-id="38d33-310">Group Policy: Block executable content from email client and webmail.</span></span>

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a><span data-ttu-id="38d33-311">有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-311">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>

<span data-ttu-id="38d33-312">このルールは、有病率や年齢の条件を満たしたり、信頼できるリストまたは除外リストに含めない限り、次の種類のファイルの起動をブロックします。</span><span class="sxs-lookup"><span data-stu-id="38d33-312">This rule blocks the following file types from launching unless they meet prevalence or age criteria, or they're in a trusted list or an exclusion list:</span></span>

- <span data-ttu-id="38d33-313">実行可能ファイル (.exe、.dll、.scr など)</span><span class="sxs-lookup"><span data-stu-id="38d33-313">Executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="38d33-314">信頼されていない実行可能ファイルまたは不明な実行可能ファイルを起動すると、ファイルが悪意のある場合、最初は明確にできない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38d33-314">Launching untrusted or unknown executable files can be risky, as it may not be initially clear if the files are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38d33-315">このルールを [使用するには、クラウドによる保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="38d33-315">You must [enable cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to use this rule.</span></span> <br/><br/> <span data-ttu-id="38d33-316">GUID で **有病率** 、年齢、または信頼できるリスト条件を満たしていない場合、実行可能ファイルの実行をブロックするルールは、Microsoft が所有し、管理者によって `01443614-cd74-433a-b99e-2ecdc07bfc25` 指定されていません。</span><span class="sxs-lookup"><span data-stu-id="38d33-316">The rule **Block executable files from running unless they meet a prevalence, age, or trusted list criterion** with GUID `01443614-cd74-433a-b99e-2ecdc07bfc25` is owned by Microsoft and is not specified by admins.</span></span> <span data-ttu-id="38d33-317">このルールでは、クラウド配信の保護を使用して、信頼できるリストを定期的に更新します。</span><span class="sxs-lookup"><span data-stu-id="38d33-317">This rule uses cloud-delivered protection to update its trusted list regularly.</span></span>
>
><span data-ttu-id="38d33-318">個々のファイルまたはフォルダー (フォルダー パスまたは完全修飾リソース名を使用) を指定できますが、適用するルールや除外を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="38d33-318">You can specify individual files or folders (using folder paths or fully qualified resource names) but you can't specify which rules or exclusions apply to.</span></span>

<span data-ttu-id="38d33-319">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="38d33-319">This rule was introduced in:</span></span> 
- [<span data-ttu-id="38d33-320">Windows 10 バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="38d33-320">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="38d33-321">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="38d33-321">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="38d33-322">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="38d33-322">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="38d33-323">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="38d33-323">Configuration Manager CB 1802</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="38d33-324">Intune 名: `Executables that don't meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="38d33-324">Intune name: `Executables that don't meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="38d33-325">Configuration Manager 名: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="38d33-325">Configuration Manager name: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="38d33-326">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span><span class="sxs-lookup"><span data-stu-id="38d33-326">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span></span>

### <a name="block-execution-of-potentially-obfuscated-scripts"></a><span data-ttu-id="38d33-327">難読化される可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-327">Block execution of potentially obfuscated scripts</span></span>

<span data-ttu-id="38d33-328">このルールは、難読化されたスクリプト内の疑わしいプロパティを検出します。</span><span class="sxs-lookup"><span data-stu-id="38d33-328">This rule detects suspicious properties within an obfuscated script.</span></span>

<span data-ttu-id="38d33-329">スクリプト難読化は、マルウェア作成者と正当なアプリケーションの両方が、知的財産を隠したり、スクリプトの読み込み時間を短縮したりするために使用する一般的な手法です。</span><span class="sxs-lookup"><span data-stu-id="38d33-329">Script obfuscation is a common technique that both malware authors and legitimate applications use to hide intellectual property or decrease script loading times.</span></span> <span data-ttu-id="38d33-330">マルウェアの作成者は難読化を使用して悪意のあるコードを読みにくくし、人間やセキュリティ ソフトウェアによる詳細な調査を防止します。</span><span class="sxs-lookup"><span data-stu-id="38d33-330">Malware authors also use obfuscation to make malicious code harder to read, which prevents close scrutiny by humans and security software.</span></span>

<span data-ttu-id="38d33-331">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="38d33-331">This rule was introduced in:</span></span>
- [<span data-ttu-id="38d33-332">Windows 10 バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="38d33-332">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="38d33-333">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="38d33-333">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="38d33-334">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="38d33-334">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="38d33-335">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="38d33-335">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="38d33-336">Intune 名: `Obfuscated js/vbs/ps/macro code`</span><span class="sxs-lookup"><span data-stu-id="38d33-336">Intune name: `Obfuscated js/vbs/ps/macro code`</span></span>

<span data-ttu-id="38d33-337">Configuration Manager 名: `Block execution of potentially obfuscated scripts`</span><span class="sxs-lookup"><span data-stu-id="38d33-337">Configuration Manager name: `Block execution of potentially obfuscated scripts`</span></span>

<span data-ttu-id="38d33-338">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span><span class="sxs-lookup"><span data-stu-id="38d33-338">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span></span>

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a><span data-ttu-id="38d33-339">JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-339">Block JavaScript or VBScript from launching downloaded executable content</span></span>

<span data-ttu-id="38d33-340">このルールにより、スクリプトは悪意のあるダウンロードコンテンツを起動できません。</span><span class="sxs-lookup"><span data-stu-id="38d33-340">This rule prevents scripts from launching potentially malicious downloaded content.</span></span> <span data-ttu-id="38d33-341">JavaScript または VBScript で記述されたマルウェアは、インターネットから他のマルウェアをフェッチして起動するダウンデータとして機能する場合が多い。</span><span class="sxs-lookup"><span data-stu-id="38d33-341">Malware written in JavaScript or VBScript often acts as a downloader to fetch and launch other malware from the Internet.</span></span>

<span data-ttu-id="38d33-342">一般的ではないが、一般企業向けアプリケーションでは、スクリプトを使用してインストーラーをダウンロードおよび起動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="38d33-342">Although not common, line-of-business applications sometimes use scripts to download and launch installers.</span></span>

<span data-ttu-id="38d33-343">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="38d33-343">This rule was introduced in:</span></span>  
- [<span data-ttu-id="38d33-344">Windows 10 バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="38d33-344">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="38d33-345">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="38d33-345">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="38d33-346">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="38d33-346">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="38d33-347">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="38d33-347">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="38d33-348">Intune 名: `js/vbs executing payload downloaded from Internet (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="38d33-348">Intune name: `js/vbs executing payload downloaded from Internet (no exceptions)`</span></span>

<span data-ttu-id="38d33-349">Configuration Manager 名: `Block JavaScript or VBScript from launching downloaded executable content`</span><span class="sxs-lookup"><span data-stu-id="38d33-349">Configuration Manager name: `Block JavaScript or VBScript from launching downloaded executable content`</span></span>

<span data-ttu-id="38d33-350">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span><span class="sxs-lookup"><span data-stu-id="38d33-350">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span></span>

### <a name="block-office-applications-from-creating-executable-content"></a><span data-ttu-id="38d33-351">実行可能Office作成するアプリケーションをブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-351">Block Office applications from creating executable content</span></span>

<span data-ttu-id="38d33-352">このルールは、悪意のあるOfficeコードがディスクに書き込まれるのをブロックすることで、Word、Excel、PowerPoint などのアプリによる悪意のある実行可能コンテンツの作成を防止します。</span><span class="sxs-lookup"><span data-stu-id="38d33-352">This rule prevents Office apps, including Word, Excel, and PowerPoint, from creating potentially malicious executable content, by blocking malicious code from being written to disk.</span></span>

<span data-ttu-id="38d33-353">マルウェアは、Officeとして悪用され、悪意のあるOfficeをディスクに保存しようとする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38d33-353">Malware that abuses Office as a vector may attempt to break out of Office and save malicious components to disk.</span></span> <span data-ttu-id="38d33-354">これらの悪意のあるコンポーネントは、コンピューターの再起動後も存続し、システム上で保持されます。</span><span class="sxs-lookup"><span data-stu-id="38d33-354">These malicious components would survive a computer reboot and persist on the system.</span></span> <span data-ttu-id="38d33-355">したがって、このルールは一般的な永続化手法に対して防御します。</span><span class="sxs-lookup"><span data-stu-id="38d33-355">Therefore, this rule defends against a common persistence technique.</span></span>

<span data-ttu-id="38d33-356">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="38d33-356">This rule was introduced in:</span></span> 
- [<span data-ttu-id="38d33-357">Windows 10 バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="38d33-357">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="38d33-358">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="38d33-358">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="38d33-359">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="38d33-359">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- <span data-ttu-id="38d33-360">[System Center Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM は現在 Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="38d33-360">[System Center Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM is now Microsoft Endpoint Configuration Manager)</span></span>

<span data-ttu-id="38d33-361">Intune 名: `Office apps/macros creating executable content`</span><span class="sxs-lookup"><span data-stu-id="38d33-361">Intune name: `Office apps/macros creating executable content`</span></span>

<span data-ttu-id="38d33-362">SCCM 名: `Block Office applications from creating executable content`</span><span class="sxs-lookup"><span data-stu-id="38d33-362">SCCM name: `Block Office applications from creating executable content`</span></span>

<span data-ttu-id="38d33-363">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span><span class="sxs-lookup"><span data-stu-id="38d33-363">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span></span>

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a><span data-ttu-id="38d33-364">アプリケーションOffice他のプロセスへのコードの挿入をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-364">Block Office applications from injecting code into other processes</span></span>

<span data-ttu-id="38d33-365">このルールは、アプリから他のプロセスへのコードOffice試行をブロックします。</span><span class="sxs-lookup"><span data-stu-id="38d33-365">This rule blocks code injection attempts from Office apps into other processes.</span></span>

<span data-ttu-id="38d33-366">攻撃者は、Officeを使用して、コード挿入を通じて悪意のあるコードを他のプロセスに移行しようとする可能性があります。そのため、コードはクリーン なプロセスとして悪用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38d33-366">Attackers might attempt to use Office apps to migrate malicious code into other processes through code injection, so the code can masquerade as a clean process.</span></span>

<span data-ttu-id="38d33-367">コードインジェクションを使用する正当なビジネス上の目的はありません。</span><span class="sxs-lookup"><span data-stu-id="38d33-367">There are no known legitimate business purposes for using code injection.</span></span>

<span data-ttu-id="38d33-368">このルールは、Word、Excel、および PowerPoint に適用されます。</span><span class="sxs-lookup"><span data-stu-id="38d33-368">This rule applies to Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="38d33-369">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="38d33-369">This rule was introduced in:</span></span> 
- [<span data-ttu-id="38d33-370">Windows 10 バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="38d33-370">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="38d33-371">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="38d33-371">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="38d33-372">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="38d33-372">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="38d33-373">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="38d33-373">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="38d33-374">Intune 名: `Office apps injecting code into other processes (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="38d33-374">Intune name: `Office apps injecting code into other processes (no exceptions)`</span></span>

<span data-ttu-id="38d33-375">Configuration Manager 名: `Block Office applications from injecting code into other processes`</span><span class="sxs-lookup"><span data-stu-id="38d33-375">Configuration Manager name: `Block Office applications from injecting code into other processes`</span></span>

<span data-ttu-id="38d33-376">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span><span class="sxs-lookup"><span data-stu-id="38d33-376">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span></span>

### <a name="block-office-communication-application-from-creating-child-processes"></a><span data-ttu-id="38d33-377">通信Office子プロセスの作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-377">Block Office communication application from creating child processes</span></span>

<span data-ttu-id="38d33-378">このルールは、Outlook が子プロセスを作成することを妨げる一方で、正当な Outlook 関数を許可します。</span><span class="sxs-lookup"><span data-stu-id="38d33-378">This rule prevents Outlook from creating child processes, while still allowing legitimate Outlook functions.</span></span>

<span data-ttu-id="38d33-379">このルールは、ソーシャル エンジニアリング攻撃から保護し、Outlook の脆弱性を悪用するコードの悪用を防止します。</span><span class="sxs-lookup"><span data-stu-id="38d33-379">This rule protects against social engineering attacks and prevents exploiting code from abusing vulnerabilities in Outlook.</span></span> <span data-ttu-id="38d33-380">また、ユーザーの [資格情報が侵害された](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) 場合に攻撃者が使用できる Outlook ルールやフォームの悪用から保護します。</span><span class="sxs-lookup"><span data-stu-id="38d33-380">It also protects against [Outlook rules and forms exploits](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) that attackers can use when a user's credentials are compromised.</span></span>

> [!NOTE]
> <span data-ttu-id="38d33-381">このルールは、Outlook および Outlook Outlook.com 適用されます。</span><span class="sxs-lookup"><span data-stu-id="38d33-381">This rule applies to Outlook and Outlook.com only.</span></span>

<span data-ttu-id="38d33-382">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="38d33-382">This rule was introduced in:</span></span> 
- [<span data-ttu-id="38d33-383">Windows 10 バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="38d33-383">Windows 10, version 1809</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="38d33-384">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="38d33-384">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="38d33-385">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="38d33-385">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="38d33-386">Intune 名: `Process creation from Office communication products (beta)`</span><span class="sxs-lookup"><span data-stu-id="38d33-386">Intune name: `Process creation from Office communication products (beta)`</span></span>

<span data-ttu-id="38d33-387">Configuration Manager 名: 使用できません</span><span class="sxs-lookup"><span data-stu-id="38d33-387">Configuration Manager name: Not available</span></span>

<span data-ttu-id="38d33-388">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span><span class="sxs-lookup"><span data-stu-id="38d33-388">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span></span>

### <a name="block-persistence-through-wmi-event-subscription"></a><span data-ttu-id="38d33-389">WMI イベント サブスクリプションによる永続化のブロック</span><span class="sxs-lookup"><span data-stu-id="38d33-389">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="38d33-390">このルールは、デバイス上で WMI を攻撃して永続化を達成するマルウェアを防止します。</span><span class="sxs-lookup"><span data-stu-id="38d33-390">This rule prevents malware from abusing WMI to attain persistence on a device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38d33-391">ファイルとフォルダーの除外は、この攻撃表面の縮小ルールには適用されません。</span><span class="sxs-lookup"><span data-stu-id="38d33-391">File and folder exclusions don't apply to this attack surface reduction rule.</span></span>

<span data-ttu-id="38d33-392">ファイルレスの脅威は、隠し、ファイル システムで見られない、定期的な実行制御を得るために、さまざまな戦術を採用しています。</span><span class="sxs-lookup"><span data-stu-id="38d33-392">Fileless threats employ various tactics to stay hidden, to avoid being seen in the file system, and to gain periodic execution control.</span></span> <span data-ttu-id="38d33-393">一部の脅威は、WMI リポジトリとイベント モデルを悪用して非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="38d33-393">Some threats can abuse the WMI repository and event model to stay hidden.</span></span>

<span data-ttu-id="38d33-394">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="38d33-394">This rule was introduced in:</span></span> 
- [<span data-ttu-id="38d33-395">Windows 10 バージョン 1903</span><span class="sxs-lookup"><span data-stu-id="38d33-395">Windows 10, version 1903</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903)
- [<span data-ttu-id="38d33-396">Windows Server 1903</span><span class="sxs-lookup"><span data-stu-id="38d33-396">Windows Server 1903</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

<span data-ttu-id="38d33-397">Intune 名: 使用できません</span><span class="sxs-lookup"><span data-stu-id="38d33-397">Intune name: Not available</span></span>

<span data-ttu-id="38d33-398">Configuration Manager 名: 使用できません</span><span class="sxs-lookup"><span data-stu-id="38d33-398">Configuration Manager name: Not available</span></span>

<span data-ttu-id="38d33-399">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span><span class="sxs-lookup"><span data-stu-id="38d33-399">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span></span>

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a><span data-ttu-id="38d33-400">PSExec および WMI コマンドから発生するプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-400">Block process creations originating from PSExec and WMI commands</span></span>

<span data-ttu-id="38d33-401">このルールは [、PsExec](https://docs.microsoft.com/sysinternals/downloads/psexec) および WMI を介して作成 [されたプロセスの実行](https://docs.microsoft.com/windows/win32/wmisdk/about-wmi) をブロックします。</span><span class="sxs-lookup"><span data-stu-id="38d33-401">This rule blocks processes created through [PsExec](https://docs.microsoft.com/sysinternals/downloads/psexec) and [WMI](https://docs.microsoft.com/windows/win32/wmisdk/about-wmi) from running.</span></span> <span data-ttu-id="38d33-402">PsExec と WMI の両方がコードをリモートで実行できるので、コマンドと制御の目的でこの機能を不正に使用したり、組織のネットワーク全体に感染を広げる危険性があります。</span><span class="sxs-lookup"><span data-stu-id="38d33-402">Both PsExec and WMI can remotely execute code, so there is a risk of malware abusing this functionality for command and control purposes, or to spread an infection throughout an organization's network.</span></span>

> [!WARNING]
> <span data-ttu-id="38d33-403">Intune または別の MDM ソリューションを使用してデバイスを管理する場合にのみ、 [このルールを](https://docs.microsoft.com/intune) 使用します。</span><span class="sxs-lookup"><span data-stu-id="38d33-403">Only use this rule if you're managing your devices with [Intune](https://docs.microsoft.com/intune) or another MDM solution.</span></span> <span data-ttu-id="38d33-404">このルールは [、Configuration Manager](https://docs.microsoft.com/configmgr) クライアントが正しく機能するために使用する WMI コマンドをブロックする Microsoft Endpoint Configuration Manager による管理と互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="38d33-404">This rule is incompatible with management through [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr) because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span>

<span data-ttu-id="38d33-405">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="38d33-405">This rule was introduced in:</span></span> 
- [<span data-ttu-id="38d33-406">Windows 10 バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="38d33-406">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="38d33-407">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="38d33-407">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="38d33-408">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="38d33-408">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="38d33-409">Intune 名: `Process creation from PSExec and WMI commands`</span><span class="sxs-lookup"><span data-stu-id="38d33-409">Intune name: `Process creation from PSExec and WMI commands`</span></span>

<span data-ttu-id="38d33-410">Configuration Manager 名: 該当なし</span><span class="sxs-lookup"><span data-stu-id="38d33-410">Configuration Manager name: Not applicable</span></span>

<span data-ttu-id="38d33-411">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span><span class="sxs-lookup"><span data-stu-id="38d33-411">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span></span>

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a><span data-ttu-id="38d33-412">USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="38d33-412">Block untrusted and unsigned processes that run from USB</span></span>

<span data-ttu-id="38d33-413">このルールを使用すると、管理者は、SD カードを含む USB リムーバブル ドライブから署名されていない実行可能ファイルまたは信頼されていない実行可能ファイルを実行できません。</span><span class="sxs-lookup"><span data-stu-id="38d33-413">With this rule, admins can prevent unsigned or untrusted executable files from running from USB removable drives, including SD cards.</span></span> <span data-ttu-id="38d33-414">ブロックされたファイルの種類には、実行可能ファイル (.exe、.dll、.scr など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="38d33-414">Blocked file types include executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="38d33-415">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="38d33-415">This rule was introduced in:</span></span> 
- [<span data-ttu-id="38d33-416">Windows 10 バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="38d33-416">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="38d33-417">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="38d33-417">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="38d33-418">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="38d33-418">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="38d33-419">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="38d33-419">Configuration Manager CB 1802</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="38d33-420">Intune 名: `Untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="38d33-420">Intune name: `Untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="38d33-421">Configuration Manager 名: `Block untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="38d33-421">Configuration Manager name: `Block untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="38d33-422">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span><span class="sxs-lookup"><span data-stu-id="38d33-422">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span></span>

### <a name="block-win32-api-calls-from-office-macros"></a><span data-ttu-id="38d33-423">Win32 API 呼び出しをブロックOfficeマクロ</span><span class="sxs-lookup"><span data-stu-id="38d33-423">Block Win32 API calls from Office macros</span></span>

<span data-ttu-id="38d33-424">このルールは、VBA マクロが Win32 API を呼び出すのを防止します。</span><span class="sxs-lookup"><span data-stu-id="38d33-424">This rule prevents VBA macros from calling Win32 APIs.</span></span>

<span data-ttu-id="38d33-425">Office VBA では、Win32 API 呼び出しが有効です。</span><span class="sxs-lookup"><span data-stu-id="38d33-425">Office VBA enables Win32 API calls.</span></span> <span data-ttu-id="38d33-426">マルウェアは [、Win32 API](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) を呼び出してディスクに直接何も書き込みせずに悪意のあるシェルコードを起動するなど、この機能を悪用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38d33-426">Malware can abuse this capability, such as [calling Win32 APIs to launch malicious shellcode](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) without writing anything directly to disk.</span></span> <span data-ttu-id="38d33-427">ほとんどの組織では、他の方法でマクロを使用している場合でも、Win32 API を毎日の機能で呼び出す機能に依存しません。</span><span class="sxs-lookup"><span data-stu-id="38d33-427">Most organizations don't rely on the ability to call Win32 APIs in their day-to-day functioning, even if they use macros in other ways.</span></span>

<span data-ttu-id="38d33-428">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="38d33-428">This rule was introduced in:</span></span>
- [<span data-ttu-id="38d33-429">Windows 10 バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="38d33-429">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="38d33-430">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="38d33-430">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="38d33-431">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="38d33-431">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="38d33-432">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="38d33-432">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="38d33-433">Intune 名: `Win32 imports from Office macro code`</span><span class="sxs-lookup"><span data-stu-id="38d33-433">Intune name: `Win32 imports from Office macro code`</span></span>

<span data-ttu-id="38d33-434">Configuration Manager 名: `Block Win32 API calls from Office macros`</span><span class="sxs-lookup"><span data-stu-id="38d33-434">Configuration Manager name: `Block Win32 API calls from Office macros`</span></span>

<span data-ttu-id="38d33-435">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span><span class="sxs-lookup"><span data-stu-id="38d33-435">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span></span>

### <a name="use-advanced-protection-against-ransomware"></a><span data-ttu-id="38d33-436">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="38d33-436">Use advanced protection against ransomware</span></span>

<span data-ttu-id="38d33-437">このルールは、ランサムウェアに対する保護の追加層を提供します。</span><span class="sxs-lookup"><span data-stu-id="38d33-437">This rule provides an extra layer of protection against ransomware.</span></span> <span data-ttu-id="38d33-438">システムに入る実行可能ファイルをスキャンして、信頼できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="38d33-438">It scans executable files entering the system to determine whether they're trustworthy.</span></span> <span data-ttu-id="38d33-439">ファイルがランサムウェアと密接に似ている場合、このルールは、信頼できるリストまたは除外リストに含まれる場合を含め、ファイルの実行をブロックします。</span><span class="sxs-lookup"><span data-stu-id="38d33-439">If the files closely resemble ransomware, this rule blocks them from running, unless they're in a trusted list or an exclusion list.</span></span>

> [!NOTE]
> <span data-ttu-id="38d33-440">このルールを [使用するには、クラウドによる保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="38d33-440">You must [enable cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to use this rule.</span></span>

<span data-ttu-id="38d33-441">このルールは次の中で導入されました。</span><span class="sxs-lookup"><span data-stu-id="38d33-441">This rule was introduced in:</span></span> 
- [<span data-ttu-id="38d33-442">Windows 10 バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="38d33-442">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="38d33-443">Windows Server バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="38d33-443">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="38d33-444">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="38d33-444">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="38d33-445">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="38d33-445">Configuration Manager CB 1802</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="38d33-446">Intune 名: `Advanced ransomware protection`</span><span class="sxs-lookup"><span data-stu-id="38d33-446">Intune name: `Advanced ransomware protection`</span></span>

<span data-ttu-id="38d33-447">Configuration Manager 名: `Use advanced protection against ransomware`</span><span class="sxs-lookup"><span data-stu-id="38d33-447">Configuration Manager name: `Use advanced protection against ransomware`</span></span>

<span data-ttu-id="38d33-448">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span><span class="sxs-lookup"><span data-stu-id="38d33-448">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span></span>

## <a name="see-also"></a><span data-ttu-id="38d33-449">関連項目</span><span class="sxs-lookup"><span data-stu-id="38d33-449">See also</span></span>

- [<span data-ttu-id="38d33-450">攻撃表面の縮小に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="38d33-450">Attack surface reduction FAQ</span></span>](attack-surface-reduction-faq.md)
- [<span data-ttu-id="38d33-451">攻撃表面の縮小ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="38d33-451">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)
- [<span data-ttu-id="38d33-452">攻撃表面の縮小ルールを評価する</span><span class="sxs-lookup"><span data-stu-id="38d33-452">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
- [<span data-ttu-id="38d33-453">Microsoft Defender Antivirus と他のウイルス対策/マルウェア対策ソリューションとの互換性</span><span class="sxs-lookup"><span data-stu-id="38d33-453">Compatibility of Microsoft Defender Antivirus with other antivirus/antimalware solutions</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
