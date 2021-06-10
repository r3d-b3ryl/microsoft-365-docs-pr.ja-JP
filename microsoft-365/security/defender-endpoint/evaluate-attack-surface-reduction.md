---
title: 攻撃面の減少ルールを評価する
description: カスタム デモ ツールを使用して攻撃をブロックおよび防止する攻撃表面の縮小方法について説明します。
keywords: 攻撃表面の縮小、腰、ホスト侵入防止システム、保護ルール、悪用防止、脆弱性対策、悪用、感染防止、評価、テスト、デモ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5d3cd7893af4c91807782c269231a280b413733e
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861224"
---
# <a name="evaluate-attack-surface-reduction-rules"></a><span data-ttu-id="9ea9e-104">攻撃面の減少ルールを評価する</span><span class="sxs-lookup"><span data-stu-id="9ea9e-104">Evaluate attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9ea9e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9ea9e-105">**Applies to:**</span></span>

- [<span data-ttu-id="9ea9e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9ea9e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="9ea9e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ea9e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9ea9e-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="9ea9e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9ea9e-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="9ea9e-110">攻撃表面の縮小ルールは、デバイスやネットワークを侵害するためにマルウェアが通常使用するアクションを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span></span> <span data-ttu-id="9ea9e-111">攻撃表面の縮小ルールは、マルウェアやランサムウェアで使用される一般的なエントリ ポイントの多くを閉じるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-111">Attack surface reduction rules help close off many of the common entry points used by malware and ransomware.</span></span> 

<span data-ttu-id="9ea9e-112">次のエディションとバージョンのデバイスを実行しているデバイスに対して攻撃表面の縮小ルールを設定Windows。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-112">Set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="9ea9e-113">Windows 10 Proバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="9ea9e-113">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="9ea9e-114">Windows 10 Enterpriseバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="9ea9e-114">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="9ea9e-115">Windowsサーバー、[バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803)以降</span><span class="sxs-lookup"><span data-stu-id="9ea9e-115">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="9ea9e-116">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="9ea9e-116">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

> [!WARNING]
> <span data-ttu-id="9ea9e-117">攻撃サービスの削減ルールを有効にすると、Windows Server 2016予期しない結果が発生し、サーバーのパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-117">Enabling attack service reduction rules on Windows Server 2016 may lead to unexpected results and impact server performance.</span></span> <span data-ttu-id="9ea9e-118">サポートされていないプラットフォームに対して攻撃表面の縮小ルールを有効または展開はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-118">We do not recommend enabling or deploying attack surface reduction rules to unsupported platforms.</span></span>

<span data-ttu-id="9ea9e-119">監査モードで組織の機能を直接テストすることで、攻撃表面の縮小ルールを評価する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-119">Learn how to evaluate attack surface reduction rules by enabling audit mode to test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="9ea9e-120">また、Microsoft Defender for Endpoint のデモ シナリオ web サイト demo.wd.microsoft.com 機能 [が](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 動作し、動作を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-120">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="9ea9e-121">監査モードを使用して影響を測定する</span><span class="sxs-lookup"><span data-stu-id="9ea9e-121">Use audit mode to measure impact</span></span>

<span data-ttu-id="9ea9e-122">監査モードで攻撃表面の縮小ルールを有効にして、機能が完全に有効になっている場合にブロックされた可能性があるアプリのレコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-122">Enable attack surface reduction rules in audit mode to view a record of apps that would have been blocked if the feature was fully enabled.</span></span> <span data-ttu-id="9ea9e-123">組織で機能がどのように機能されるかをテストして、その機能が業務上のアプリに影響を与えなかねない方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-123">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="9ea9e-124">また、通常の使用中にルールが発生する頻度を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-124">You can also get an idea of how often the rules will fire during normal use.</span></span>

<span data-ttu-id="9ea9e-125">監査モードで攻撃表面の縮小ルールを有効にするには、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-125">To enable an attack surface reduction rule in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

<span data-ttu-id="9ea9e-126">攻撃 `<rule ID>` 表面の [縮小ルールの GUID 値はここで指定します](attack-surface-reduction.md#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-126">Where `<rule ID>` is a [GUID value of the attack surface reduction rule](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

<span data-ttu-id="9ea9e-127">監査モードで追加された攻撃表面の縮小ルールを有効にするには、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-127">To enable all the added attack surface reduction rules in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> <span data-ttu-id="9ea9e-128">組織内での攻撃表面の縮小ルールの動作を完全に監査する場合は、管理ツールを使用して、ネットワーク内のデバイスにこの設定を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-128">If you want to fully audit how attack surface reduction rules will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>

<span data-ttu-id="9ea9e-129">グループ ポリシー、Intune、またはモバイル デバイス管理 (MDM) 構成サービス プロバイダー (CSP) を使用して、設定を構成および展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-129">You can also use Group Policy, Intune, or mobile device management (MDM) configuration service providers (CSPs) to configure and deploy the setting.</span></span> <span data-ttu-id="9ea9e-130">詳しくは、「攻撃表面の [縮小ルール」のメイン記事を参照](attack-surface-reduction.md) してください。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-130">Learn more in the main [Attack surface reduction rules](attack-surface-reduction.md) article.</span></span>

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="9ea9e-131">イベント ビューアーで攻撃表面の縮小イベントWindows確認する</span><span class="sxs-lookup"><span data-stu-id="9ea9e-131">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="9ea9e-132">ブロックされているアプリを確認するには、Microsoft-Windows-Windows Defender/運用ログでイベント ビューアーを開き、イベント ID 1121 をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-132">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1121 in the Microsoft-Windows-Windows Defender/Operational log.</span></span> <span data-ttu-id="9ea9e-133">次の表に、すべてのネットワーク保護イベントを示します。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-133">The following table lists all network protection events.</span></span>

<span data-ttu-id="9ea9e-134">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9ea9e-134">Event ID</span></span> | <span data-ttu-id="9ea9e-135">説明</span><span class="sxs-lookup"><span data-stu-id="9ea9e-135">Description</span></span>
-|-
 <span data-ttu-id="9ea9e-136">5007</span><span class="sxs-lookup"><span data-stu-id="9ea9e-136">5007</span></span> | <span data-ttu-id="9ea9e-137">設定が変更された場合のイベント</span><span class="sxs-lookup"><span data-stu-id="9ea9e-137">Event when settings are changed</span></span>
 <span data-ttu-id="9ea9e-138">1121</span><span class="sxs-lookup"><span data-stu-id="9ea9e-138">1121</span></span> | <span data-ttu-id="9ea9e-139">ブロック モードで攻撃表面の縮小ルールが発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="9ea9e-139">Event when an attack surface reduction rule fires in block mode</span></span>
 <span data-ttu-id="9ea9e-140">1122</span><span class="sxs-lookup"><span data-stu-id="9ea9e-140">1122</span></span> | <span data-ttu-id="9ea9e-141">監査モードで攻撃表面の縮小ルールが発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="9ea9e-141">Event when an attack surface reduction rule fires in audit mode</span></span>

## <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="9ea9e-142">攻撃面の減少ルールをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="9ea9e-142">Customize attack surface reduction rules</span></span>

<span data-ttu-id="9ea9e-143">評価中に、各ルールを個別に構成したり、特定のファイルやプロセスが機能によって評価されるのを除外したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-143">During your evaluation, you may wish to configure each rule individually or exclude certain files and processes from being evaluated by the feature.</span></span>

<span data-ttu-id="9ea9e-144">グループ [ポリシーと](customize-attack-surface-reduction.md) MDM CSP ポリシーを含む管理ツールを使用して機能を構成する方法については、「攻撃表面の縮小ルールをカスタマイズする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ea9e-144">See [Customize attack surface reduction rules](customize-attack-surface-reduction.md) for information on configuring the feature with management tools, including Group Policy and MDM CSP policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ea9e-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ea9e-145">See also</span></span>

* [<span data-ttu-id="9ea9e-146">攻撃表面の縮小ルールを使用して攻撃表面を削減する</span><span class="sxs-lookup"><span data-stu-id="9ea9e-146">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="9ea9e-147">監査モードを使用して、監査Windows Defender</span><span class="sxs-lookup"><span data-stu-id="9ea9e-147">Use audit mode to evaluate Windows Defender</span></span>](audit-windows-defender.md)
* [<span data-ttu-id="9ea9e-148">攻撃面の減少の FAQ</span><span class="sxs-lookup"><span data-stu-id="9ea9e-148">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
