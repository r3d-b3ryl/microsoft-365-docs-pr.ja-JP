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
author: dansimp
ms.author: dansimp
ms.reviewer: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 73b23427ff401f2a37c399131d6aa01330ff9de5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245302"
---
# <a name="evaluate-attack-surface-reduction-rules"></a><span data-ttu-id="6e14c-104">攻撃面の減少ルールを評価する</span><span class="sxs-lookup"><span data-stu-id="6e14c-104">Evaluate attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6e14c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6e14c-105">**Applies to:**</span></span>

- [<span data-ttu-id="6e14c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6e14c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6e14c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6e14c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6e14c-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="6e14c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6e14c-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="6e14c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="6e14c-110">攻撃表面の縮小ルールは、デバイスやネットワークを侵害するためにマルウェアが通常使用するアクションを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6e14c-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span></span> <span data-ttu-id="6e14c-111">攻撃表面の縮小ルールは、マルウェアやランサムウェアで使用される一般的なエントリ ポイントの多くを閉じるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6e14c-111">Attack surface reduction rules help close off many of the common entry points used by malware and ransomware.</span></span> 

<span data-ttu-id="6e14c-112">次のエディションとバージョンのデバイスを実行しているデバイスに対して攻撃表面の縮小ルールを設定Windows。</span><span class="sxs-lookup"><span data-stu-id="6e14c-112">Set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="6e14c-113">Windows 10 Proバージョン[1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="6e14c-113">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="6e14c-114">Windows 10 Enterpriseバージョン[1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="6e14c-114">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="6e14c-115">Windowsサーバー、[バージョン 1803 (半期チャネル)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)以降</span><span class="sxs-lookup"><span data-stu-id="6e14c-115">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="6e14c-116">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="6e14c-116">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="6e14c-117">監査モードで組織の機能を直接テストすることで、攻撃表面の縮小ルールを評価する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="6e14c-117">Learn how to evaluate attack surface reduction rules by enabling audit mode to test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="6e14c-118">また、Microsoft Defender for Endpoint のデモ シナリオ web サイト demo.wd.microsoft.com 機能 [が](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 動作し、動作を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e14c-118">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="6e14c-119">監査モードを使用して影響を測定する</span><span class="sxs-lookup"><span data-stu-id="6e14c-119">Use audit mode to measure impact</span></span>

<span data-ttu-id="6e14c-120">監査モードで攻撃表面の縮小ルールを有効にして、機能が完全に有効になっている場合にブロックされた可能性があるアプリのレコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="6e14c-120">Enable attack surface reduction rules in audit mode to view a record of apps that would have been blocked if the feature was fully enabled.</span></span> <span data-ttu-id="6e14c-121">組織で機能がどのように機能されるかをテストして、その機能が業務上のアプリに影響を与えなかねない方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="6e14c-121">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="6e14c-122">また、通常の使用中にルールが発生する頻度を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e14c-122">You can also get an idea of how often the rules will fire during normal use.</span></span>

<span data-ttu-id="6e14c-123">監査モードで攻撃表面の縮小ルールを有効にするには、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e14c-123">To enable an attack surface reduction rule in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

<span data-ttu-id="6e14c-124">攻撃 `<rule ID>` 表面の [縮小ルールの GUID 値はここで指定します](attack-surface-reduction.md#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="6e14c-124">Where `<rule ID>` is a [GUID value of the attack surface reduction rule](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

<span data-ttu-id="6e14c-125">監査モードで追加された攻撃表面の縮小ルールを有効にするには、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e14c-125">To enable all the added attack surface reduction rules in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> <span data-ttu-id="6e14c-126">組織内での攻撃表面の縮小ルールの動作を完全に監査する場合は、管理ツールを使用して、ネットワーク内のデバイスにこの設定を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e14c-126">If you want to fully audit how attack surface reduction rules will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>

<span data-ttu-id="6e14c-127">グループ ポリシー、Intune、またはモバイル デバイス管理 (MDM) 構成サービス プロバイダー (CSP) を使用して、設定を構成および展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e14c-127">You can also use Group Policy, Intune, or mobile device management (MDM) configuration service providers (CSPs) to configure and deploy the setting.</span></span> <span data-ttu-id="6e14c-128">詳しくは、「攻撃表面の [縮小ルール」のメイン記事を参照](attack-surface-reduction.md) してください。</span><span class="sxs-lookup"><span data-stu-id="6e14c-128">Learn more in the main [Attack surface reduction rules](attack-surface-reduction.md) article.</span></span>

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="6e14c-129">イベント ビューアーで攻撃表面の縮小イベントWindows確認する</span><span class="sxs-lookup"><span data-stu-id="6e14c-129">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="6e14c-130">ブロックされているアプリを確認するには、Microsoft-Windows-Windows Defender/運用ログでイベント ビューアーを開き、イベント ID 1121 をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="6e14c-130">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1121 in the Microsoft-Windows-Windows Defender/Operational log.</span></span> <span data-ttu-id="6e14c-131">次の表に、すべてのネットワーク保護イベントを示します。</span><span class="sxs-lookup"><span data-stu-id="6e14c-131">The following table lists all network protection events.</span></span>

<span data-ttu-id="6e14c-132">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6e14c-132">Event ID</span></span> | <span data-ttu-id="6e14c-133">説明</span><span class="sxs-lookup"><span data-stu-id="6e14c-133">Description</span></span>
-|-
 <span data-ttu-id="6e14c-134">5007</span><span class="sxs-lookup"><span data-stu-id="6e14c-134">5007</span></span> | <span data-ttu-id="6e14c-135">設定が変更された場合のイベント</span><span class="sxs-lookup"><span data-stu-id="6e14c-135">Event when settings are changed</span></span>
 <span data-ttu-id="6e14c-136">1121</span><span class="sxs-lookup"><span data-stu-id="6e14c-136">1121</span></span> | <span data-ttu-id="6e14c-137">ブロック モードで攻撃表面の縮小ルールが発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="6e14c-137">Event when an attack surface reduction rule fires in block mode</span></span>
 <span data-ttu-id="6e14c-138">1122</span><span class="sxs-lookup"><span data-stu-id="6e14c-138">1122</span></span> | <span data-ttu-id="6e14c-139">監査モードで攻撃表面の縮小ルールが発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="6e14c-139">Event when an attack surface reduction rule fires in audit mode</span></span>

## <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="6e14c-140">攻撃面の減少ルールをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="6e14c-140">Customize attack surface reduction rules</span></span>

<span data-ttu-id="6e14c-141">評価中に、各ルールを個別に構成したり、特定のファイルやプロセスが機能によって評価されるのを除外したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6e14c-141">During your evaluation, you may wish to configure each rule individually or exclude certain files and processes from being evaluated by the feature.</span></span>

<span data-ttu-id="6e14c-142">グループ [ポリシーと](customize-attack-surface-reduction.md) MDM CSP ポリシーを含む管理ツールを使用して機能を構成する方法については、「攻撃表面の縮小ルールをカスタマイズする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e14c-142">See [Customize attack surface reduction rules](customize-attack-surface-reduction.md) for information on configuring the feature with management tools, including Group Policy and MDM CSP policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e14c-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e14c-143">See also</span></span>

* [<span data-ttu-id="6e14c-144">攻撃表面の縮小ルールを使用して攻撃表面を削減する</span><span class="sxs-lookup"><span data-stu-id="6e14c-144">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="6e14c-145">監査モードを使用して、監査Windows Defender</span><span class="sxs-lookup"><span data-stu-id="6e14c-145">Use audit mode to evaluate Windows Defender</span></span>](audit-windows-defender.md)
* [<span data-ttu-id="6e14c-146">攻撃面の減少の FAQ</span><span class="sxs-lookup"><span data-stu-id="6e14c-146">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
