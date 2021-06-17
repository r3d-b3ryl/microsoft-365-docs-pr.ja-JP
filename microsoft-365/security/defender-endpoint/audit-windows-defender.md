---
title: Microsoft Defender for Endpoint の機能が監査モードで動作する方法をテストする
description: 監査モードは、Microsoft Defender for Endpoint が有効になっている場合にデバイスを保護する方法を確認するのに役立ちます。
keywords: exploit guard, audit, auditing, mode, enabled, disabled, test, demo, evaluate, lab
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 23de13e9a2b0fb02b95c9bb367c3fd99e11e89c8
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985098"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="088cb-104">エンドポイント向け Microsoft Defender の攻撃表面の縮小をテストする</span><span class="sxs-lookup"><span data-stu-id="088cb-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="088cb-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="088cb-105">**Applies to:**</span></span>

- [<span data-ttu-id="088cb-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="088cb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="088cb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="088cb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="088cb-108">組織のセキュリティ チームの一部として、監査モードで実行する攻撃表面の縮小機能を構成して、その動作を確認できます。</span><span class="sxs-lookup"><span data-stu-id="088cb-108">As part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work.</span></span> <span data-ttu-id="088cb-109">監査モードでは、次の機能を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="088cb-109">In audit mode, you can enable:</span></span>

- <span data-ttu-id="088cb-110">攻撃面の減少ルール</span><span class="sxs-lookup"><span data-stu-id="088cb-110">Attack surface reduction rules</span></span>
- <span data-ttu-id="088cb-111">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="088cb-111">Exploit protection</span></span>
- <span data-ttu-id="088cb-112">ネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="088cb-112">Network protection</span></span>
- <span data-ttu-id="088cb-113">監査モードでのフォルダー アクセスの制御</span><span class="sxs-lookup"><span data-stu-id="088cb-113">And controlled folder access in audit mode</span></span>

<span data-ttu-id="088cb-114">監査モードでは、機能を有効にした場合に何が起こったかの記録を確認できます。</span><span class="sxs-lookup"><span data-stu-id="088cb-114">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="088cb-115">機能の動作をテストするときに監査モードを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="088cb-115">You can enable audit mode when testing how the features will work.</span></span> <span data-ttu-id="088cb-116">これにより、一行のアプリが影響を受けずに行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="088cb-116">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="088cb-117">また、一定の期間に発生する疑わしいファイル変更の試行回数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="088cb-117">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="088cb-118">この機能は、アプリ、スクリプト、またはファイルが変更されるのをブロックまたは防止できません。</span><span class="sxs-lookup"><span data-stu-id="088cb-118">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="088cb-119">ただし、イベント ログWindows機能が完全に有効になっている場合と同様にイベントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="088cb-119">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="088cb-120">監査モードを使用すると、イベント ログを確認して、機能が有効になっている場合の影響を確認できます。</span><span class="sxs-lookup"><span data-stu-id="088cb-120">With audit mode, you can review the event log to see what affect the feature would have had if it was enabled.</span></span>

<span data-ttu-id="088cb-121">監査されたエントリを見つけるには、「Applications and Services Microsoft **Windows Windows Defender**  >    >    >    >  **します**。</span><span class="sxs-lookup"><span data-stu-id="088cb-121">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="088cb-122">Defender for Endpoint を使用して、特に攻撃表面の縮小ルールを調査するために、各イベントの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="088cb-122">Use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="088cb-123">Defender for Endpoint コンソールを使用すると、アラートタイムラインと調査シナリオの一部として問題 [を調査できます](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="088cb-123">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="088cb-124">グループ ポリシー、PowerShell、および構成サービス プロバイダー (CSP) を使用して監査モードを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="088cb-124">You can enable audit mode using Group Policy, PowerShell, and configuration service providers (CSPs).</span></span>

> [!TIP]
> <span data-ttu-id="088cb-125">また、テストグラウンドのWindows Defenderに[アクセスして](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)demo.wd.microsoft.com 機能を確認し、機能の動作を確認できます。</span><span class="sxs-lookup"><span data-stu-id="088cb-125">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="088cb-126">監査オプション</span><span class="sxs-lookup"><span data-stu-id="088cb-126">Audit options</span></span> | <span data-ttu-id="088cb-127">監査モードを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="088cb-127">How to enable audit mode</span></span> | <span data-ttu-id="088cb-128">イベントを表示する方法</span><span class="sxs-lookup"><span data-stu-id="088cb-128">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="088cb-129">監査はすべてのイベントに適用されます</span><span class="sxs-lookup"><span data-stu-id="088cb-129">Audit applies to all events</span></span> | [<span data-ttu-id="088cb-130">制御されたフォルダー アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="088cb-130">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="088cb-131">フォルダー アクセスイベントの制御</span><span class="sxs-lookup"><span data-stu-id="088cb-131">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="088cb-132">監査は個々のルールに適用されます</span><span class="sxs-lookup"><span data-stu-id="088cb-132">Audit applies to individual rules</span></span> | [<span data-ttu-id="088cb-133">攻撃面の減少ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="088cb-133">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="088cb-134">攻撃表面の縮小ルール イベント</span><span class="sxs-lookup"><span data-stu-id="088cb-134">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="088cb-135">監査はすべてのイベントに適用されます</span><span class="sxs-lookup"><span data-stu-id="088cb-135">Audit applies to all events</span></span> | [<span data-ttu-id="088cb-136">ネットワーク保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="088cb-136">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="088cb-137">ネットワーク保護イベント</span><span class="sxs-lookup"><span data-stu-id="088cb-137">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="088cb-138">監査は個々の軽減策に適用されます</span><span class="sxs-lookup"><span data-stu-id="088cb-138">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="088cb-139">エクスプロイト保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="088cb-139">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="088cb-140">エクスプロイト保護イベント</span><span class="sxs-lookup"><span data-stu-id="088cb-140">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
