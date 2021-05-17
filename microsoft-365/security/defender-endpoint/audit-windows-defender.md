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
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ce652d58be2d9ff28d82c088d5471a7bffdf6dc
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570974"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a><span data-ttu-id="4fd9e-104">Microsoft Defender for Endpoint の機能が監査モードで動作する方法をテストする</span><span class="sxs-lookup"><span data-stu-id="4fd9e-104">Test how Microsoft Defender for Endpoint features work in audit mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4fd9e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4fd9e-105">**Applies to:**</span></span>
- [<span data-ttu-id="4fd9e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4fd9e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="4fd9e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4fd9e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="4fd9e-108">監査モードでは、攻撃表面の縮小ルール、エクスプロイト保護、ネットワーク保護、およびフォルダー アクセスの制御を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4fd9e-108">You can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="4fd9e-109">監査モードでは、機能を有効にした場合に何が起こったかの記録を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4fd9e-109">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="4fd9e-110">組織での機能の動作をテストするときに、監査モードを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4fd9e-110">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="4fd9e-111">これにより、一行のアプリが影響を受けずに行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4fd9e-111">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="4fd9e-112">また、一定の期間に発生する疑わしいファイル変更の試行回数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4fd9e-112">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="4fd9e-113">この機能は、アプリ、スクリプト、またはファイルが変更されるのをブロックまたは防止できません。</span><span class="sxs-lookup"><span data-stu-id="4fd9e-113">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="4fd9e-114">ただし、イベント ログWindows機能が完全に有効になっている場合と同様にイベントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="4fd9e-114">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="4fd9e-115">監査モードでは、イベント ログを確認して、機能が有効な場合にどのような影響を与えたかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4fd9e-115">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="4fd9e-116">監査されたエントリを見つけるには、「Applications and Services Microsoft **Windows Windows Defender**  >    >    >    >  **します**。</span><span class="sxs-lookup"><span data-stu-id="4fd9e-116">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="4fd9e-117">Defender for Endpoint を使用すると、特に攻撃表面の縮小ルールを調査するために、各イベントの詳細を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4fd9e-117">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="4fd9e-118">Defender for Endpoint コンソールを使用すると、アラートタイムラインと調査シナリオの一部として問題 [を調査できます](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="4fd9e-118">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="4fd9e-119">グループ ポリシー、PowerShell、および構成サービス プロバイダー (CSP) を使用して監査モードを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4fd9e-119">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="4fd9e-120">また、テストグラウンドのWindows Defenderに[アクセスして](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)demo.wd.microsoft.com 機能を確認し、機能の動作を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4fd9e-120">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="4fd9e-121">**監査オプション**</span><span class="sxs-lookup"><span data-stu-id="4fd9e-121">**Audit options**</span></span> | <span data-ttu-id="4fd9e-122">**監査モードを有効にする方法**</span><span class="sxs-lookup"><span data-stu-id="4fd9e-122">**How to enable audit mode**</span></span> | <span data-ttu-id="4fd9e-123">**イベントを表示する方法**</span><span class="sxs-lookup"><span data-stu-id="4fd9e-123">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="4fd9e-124">監査はすべてのイベントに適用されます</span><span class="sxs-lookup"><span data-stu-id="4fd9e-124">Audit applies to all events</span></span> | [<span data-ttu-id="4fd9e-125">制御されたフォルダー アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="4fd9e-125">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="4fd9e-126">フォルダー アクセスイベントの制御</span><span class="sxs-lookup"><span data-stu-id="4fd9e-126">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="4fd9e-127">監査は個々のルールに適用されます</span><span class="sxs-lookup"><span data-stu-id="4fd9e-127">Audit applies to individual rules</span></span> | [<span data-ttu-id="4fd9e-128">攻撃面の減少ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="4fd9e-128">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="4fd9e-129">攻撃表面の縮小ルール イベント</span><span class="sxs-lookup"><span data-stu-id="4fd9e-129">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="4fd9e-130">監査はすべてのイベントに適用されます</span><span class="sxs-lookup"><span data-stu-id="4fd9e-130">Audit applies to all events</span></span> | [<span data-ttu-id="4fd9e-131">ネットワーク保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="4fd9e-131">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="4fd9e-132">ネットワーク保護イベント</span><span class="sxs-lookup"><span data-stu-id="4fd9e-132">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="4fd9e-133">監査は個々の軽減策に適用されます</span><span class="sxs-lookup"><span data-stu-id="4fd9e-133">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="4fd9e-134">エクスプロイト保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="4fd9e-134">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="4fd9e-135">エクスプロイト保護イベント</span><span class="sxs-lookup"><span data-stu-id="4fd9e-135">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a><span data-ttu-id="4fd9e-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="4fd9e-136">Related topics</span></span>

* [<span data-ttu-id="4fd9e-137">エクスプロイトからデバイスを保護する</span><span class="sxs-lookup"><span data-stu-id="4fd9e-137">Protect devices from exploits</span></span>](exploit-protection.md)
* [<span data-ttu-id="4fd9e-138">攻撃表面の縮小ルールを使用して攻撃表面を削減する</span><span class="sxs-lookup"><span data-stu-id="4fd9e-138">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="4fd9e-139">ネットワークを保護する</span><span class="sxs-lookup"><span data-stu-id="4fd9e-139">Protect your network</span></span>](network-protection.md)
* [<span data-ttu-id="4fd9e-140">重要なフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="4fd9e-140">Protect important folders</span></span>](controlled-folders.md)
