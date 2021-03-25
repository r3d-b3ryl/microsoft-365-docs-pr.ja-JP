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
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: dda0e58e587add2693f8448dd0833ce17706786c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067355"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a><span data-ttu-id="79ed4-104">Microsoft Defender for Endpoint の機能が監査モードで動作する方法をテストする</span><span class="sxs-lookup"><span data-stu-id="79ed4-104">Test how Microsoft Defender for Endpoint features work in audit mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="79ed4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="79ed4-105">**Applies to:**</span></span>
- [<span data-ttu-id="79ed4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="79ed4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="79ed4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79ed4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="79ed4-108">監査モードでは、攻撃表面の縮小ルール、エクスプロイト保護、ネットワーク保護、およびフォルダー アクセスの制御を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="79ed4-108">You can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="79ed4-109">監査モードでは、機能を有効にした場合に何が起こったかの記録を確認できます。</span><span class="sxs-lookup"><span data-stu-id="79ed4-109">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="79ed4-110">組織での機能の動作をテストするときに、監査モードを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="79ed4-110">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="79ed4-111">これにより、一行のアプリが影響を受けずに行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="79ed4-111">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="79ed4-112">また、一定の期間に発生する疑わしいファイル変更の試行回数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="79ed4-112">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="79ed4-113">この機能は、アプリ、スクリプト、またはファイルが変更されるのをブロックまたは防止できません。</span><span class="sxs-lookup"><span data-stu-id="79ed4-113">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="79ed4-114">ただし、Windows イベント ログは、機能が完全に有効になっているかのようにイベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="79ed4-114">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="79ed4-115">監査モードでは、イベント ログを確認して、機能が有効な場合にどのような影響を与えたかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="79ed4-115">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="79ed4-116">監査されたエントリを見つけるには **、「Applications and Services** Microsoft Windows Windows Defender  >    >    >  」**を**  >  **参照してください**。</span><span class="sxs-lookup"><span data-stu-id="79ed4-116">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="79ed4-117">Defender for Endpoint を使用すると、特に攻撃表面の縮小ルールを調査するために、各イベントの詳細を取得できます。</span><span class="sxs-lookup"><span data-stu-id="79ed4-117">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="79ed4-118">Defender for Endpoint コンソールを使用すると、アラートタイムラインと調査シナリオの一部として問題 [を調査できます](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="79ed4-118">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="79ed4-119">グループ ポリシー、PowerShell、および構成サービス プロバイダー (CSP) を使用して監査モードを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="79ed4-119">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="79ed4-120">また、テストグラウンドの [Windows Defenderにアクセス](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) して demo.wd.microsoft.com 機能を確認し、機能の動作を確認できます。</span><span class="sxs-lookup"><span data-stu-id="79ed4-120">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="79ed4-121">**監査オプション**</span><span class="sxs-lookup"><span data-stu-id="79ed4-121">**Audit options**</span></span> | <span data-ttu-id="79ed4-122">**監査モードを有効にする方法**</span><span class="sxs-lookup"><span data-stu-id="79ed4-122">**How to enable audit mode**</span></span> | <span data-ttu-id="79ed4-123">**イベントを表示する方法**</span><span class="sxs-lookup"><span data-stu-id="79ed4-123">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="79ed4-124">監査はすべてのイベントに適用されます</span><span class="sxs-lookup"><span data-stu-id="79ed4-124">Audit applies to all events</span></span> | [<span data-ttu-id="79ed4-125">フォルダー アクセスの制御を有効にする</span><span class="sxs-lookup"><span data-stu-id="79ed4-125">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="79ed4-126">フォルダー アクセスイベントの制御</span><span class="sxs-lookup"><span data-stu-id="79ed4-126">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="79ed4-127">監査は個々のルールに適用されます</span><span class="sxs-lookup"><span data-stu-id="79ed4-127">Audit applies to individual rules</span></span> | [<span data-ttu-id="79ed4-128">攻撃表面の縮小ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="79ed4-128">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="79ed4-129">攻撃表面の縮小ルール イベント</span><span class="sxs-lookup"><span data-stu-id="79ed4-129">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="79ed4-130">監査はすべてのイベントに適用されます</span><span class="sxs-lookup"><span data-stu-id="79ed4-130">Audit applies to all events</span></span> | [<span data-ttu-id="79ed4-131">ネットワーク保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="79ed4-131">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="79ed4-132">ネットワーク保護イベント</span><span class="sxs-lookup"><span data-stu-id="79ed4-132">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="79ed4-133">監査は個々の軽減策に適用されます</span><span class="sxs-lookup"><span data-stu-id="79ed4-133">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="79ed4-134">エクスプロイト保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="79ed4-134">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="79ed4-135">エクスプロイト保護イベント</span><span class="sxs-lookup"><span data-stu-id="79ed4-135">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a><span data-ttu-id="79ed4-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="79ed4-136">Related topics</span></span>

* [<span data-ttu-id="79ed4-137">デバイスを悪用から保護する</span><span class="sxs-lookup"><span data-stu-id="79ed4-137">Protect devices from exploits</span></span>](exploit-protection.md)
* [<span data-ttu-id="79ed4-138">攻撃表面の縮小ルールを使用して攻撃表面を削減する</span><span class="sxs-lookup"><span data-stu-id="79ed4-138">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="79ed4-139">ネットワークを保護する</span><span class="sxs-lookup"><span data-stu-id="79ed4-139">Protect your network</span></span>](network-protection.md)
* [<span data-ttu-id="79ed4-140">重要なフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="79ed4-140">Protect important folders</span></span>](controlled-folders.md)