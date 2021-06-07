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
ms.technology: mde
ms.date: 06/02/2021
ms.topic: article
ms.openlocfilehash: 10351d97ba72945f929e042dc72a37724a1df291
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769607"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="46b6e-104">エンドポイント向け Microsoft Defender の攻撃表面の縮小をテストする</span><span class="sxs-lookup"><span data-stu-id="46b6e-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="46b6e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="46b6e-105">**Applies to:**</span></span>
- [<span data-ttu-id="46b6e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="46b6e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="46b6e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="46b6e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="46b6e-108">組織のセキュリティ チームの一員である場合は、監査モードで実行する攻撃表面の縮小機能を構成して、組織での動作を確認できます。</span><span class="sxs-lookup"><span data-stu-id="46b6e-108">If you're part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work in your organization.</span></span> <span data-ttu-id="46b6e-109">特に、監査モードで攻撃表面の縮小ルール、エクスプロイト保護、ネットワーク保護、およびフォルダー アクセスの制御を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="46b6e-109">In particular, you can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="46b6e-110">監査モードでは、機能を有効にした場合に何が起こったかの記録を確認できます。</span><span class="sxs-lookup"><span data-stu-id="46b6e-110">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="46b6e-111">組織での機能の動作をテストするときに、監査モードを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="46b6e-111">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="46b6e-112">これにより、一行のアプリが影響を受けずに行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="46b6e-112">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="46b6e-113">また、一定の期間に発生する疑わしいファイル変更の試行回数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="46b6e-113">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="46b6e-114">この機能は、アプリ、スクリプト、またはファイルが変更されるのをブロックまたは防止できません。</span><span class="sxs-lookup"><span data-stu-id="46b6e-114">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="46b6e-115">ただし、イベント ログWindows機能が完全に有効になっている場合と同様にイベントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="46b6e-115">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="46b6e-116">監査モードでは、イベント ログを確認して、機能が有効な場合にどのような影響を与えたかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="46b6e-116">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="46b6e-117">監査されたエントリを見つけるには、「Applications and Services Microsoft **Windows Windows Defender**  >    >    >    >  **します**。</span><span class="sxs-lookup"><span data-stu-id="46b6e-117">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="46b6e-118">Defender for Endpoint を使用すると、特に攻撃表面の縮小ルールを調査するために、各イベントの詳細を取得できます。</span><span class="sxs-lookup"><span data-stu-id="46b6e-118">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="46b6e-119">Defender for Endpoint コンソールを使用すると、アラートタイムラインと調査シナリオの一部として問題 [を調査できます](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="46b6e-119">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="46b6e-120">グループ ポリシー、PowerShell、および構成サービス プロバイダー (CSP) を使用して監査モードを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="46b6e-120">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="46b6e-121">また、テストグラウンドのWindows Defenderに[アクセスして](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)demo.wd.microsoft.com 機能を確認し、機能の動作を確認できます。</span><span class="sxs-lookup"><span data-stu-id="46b6e-121">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="46b6e-122">**監査オプション**</span><span class="sxs-lookup"><span data-stu-id="46b6e-122">**Audit options**</span></span> | <span data-ttu-id="46b6e-123">**監査モードを有効にする方法**</span><span class="sxs-lookup"><span data-stu-id="46b6e-123">**How to enable audit mode**</span></span> | <span data-ttu-id="46b6e-124">**イベントを表示する方法**</span><span class="sxs-lookup"><span data-stu-id="46b6e-124">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="46b6e-125">監査はすべてのイベントに適用されます</span><span class="sxs-lookup"><span data-stu-id="46b6e-125">Audit applies to all events</span></span> | [<span data-ttu-id="46b6e-126">制御されたフォルダー アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="46b6e-126">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="46b6e-127">フォルダー アクセスイベントの制御</span><span class="sxs-lookup"><span data-stu-id="46b6e-127">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="46b6e-128">監査は個々のルールに適用されます</span><span class="sxs-lookup"><span data-stu-id="46b6e-128">Audit applies to individual rules</span></span> | [<span data-ttu-id="46b6e-129">攻撃面の減少ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="46b6e-129">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="46b6e-130">攻撃表面の縮小ルール イベント</span><span class="sxs-lookup"><span data-stu-id="46b6e-130">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="46b6e-131">監査はすべてのイベントに適用されます</span><span class="sxs-lookup"><span data-stu-id="46b6e-131">Audit applies to all events</span></span> | [<span data-ttu-id="46b6e-132">ネットワーク保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="46b6e-132">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="46b6e-133">ネットワーク保護イベント</span><span class="sxs-lookup"><span data-stu-id="46b6e-133">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="46b6e-134">監査は個々の軽減策に適用されます</span><span class="sxs-lookup"><span data-stu-id="46b6e-134">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="46b6e-135">エクスプロイト保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="46b6e-135">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="46b6e-136">エクスプロイト保護イベント</span><span class="sxs-lookup"><span data-stu-id="46b6e-136">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)


