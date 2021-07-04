---
title: クライアントの動作ブロック
description: クライアントの動作ブロックは、Microsoft Defender for Endpoint の動作ブロックと格納機能の一部です。
keywords: 動作のブロック、迅速な保護、クライアントの動作、Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 83f269a13a54ee38b7e7a464d794d87ddbd7b520
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289933"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="bf8d7-104">クライアントの動作ブロック</span><span class="sxs-lookup"><span data-stu-id="bf8d7-104">Client behavioral blocking</span></span>

<span data-ttu-id="bf8d7-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bf8d7-105">**Applies to:**</span></span>
- [<span data-ttu-id="bf8d7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bf8d7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bf8d7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf8d7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bf8d7-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="bf8d7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bf8d7-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="bf8d7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="bf8d7-110">概要</span><span class="sxs-lookup"><span data-stu-id="bf8d7-110">Overview</span></span>

<span data-ttu-id="bf8d7-111">クライアントの動作ブロックは、Defender [](behavioral-blocking-containment.md) for Endpoint の動作ブロックと格納機能のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="bf8d7-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](behavioral-blocking-containment.md) in Defender for Endpoint.</span></span> <span data-ttu-id="bf8d7-112">デバイス (クライアントまたはエンドポイントとも呼ばれます) で疑わしい動作が検出されると、アーティファクト (ファイルやアプリケーションなど) が自動的にブロック、チェック、修復されます。</span><span class="sxs-lookup"><span data-stu-id="bf8d7-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="クラウドとクライアントの保護":::

<span data-ttu-id="bf8d7-114">ウイルス対策保護は、クラウド保護と組み合わせた場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="bf8d7-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="bf8d7-115">クライアントの動作のブロックのしくみ</span><span class="sxs-lookup"><span data-stu-id="bf8d7-115">How client behavioral blocking works</span></span>

<span data-ttu-id="bf8d7-116">[Microsoft Defender ウイルス対策、](microsoft-defender-antivirus-in-windows-10.md)不審な動作、悪意のあるコード、ファイルレス攻撃やメモリ内攻撃など、デバイスで検出できます。</span><span class="sxs-lookup"><span data-stu-id="bf8d7-116">[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="bf8d7-117">疑わしい動作が検出されると、Microsoft Defender ウイルス対策動作とそのプロセス ツリーを監視し、クラウド保護サービスに送信します。</span><span class="sxs-lookup"><span data-stu-id="bf8d7-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="bf8d7-118">機械学習は、悪意のあるアプリケーションと適切な動作をミリ秒単位で区別し、各成果物を分類します。</span><span class="sxs-lookup"><span data-stu-id="bf8d7-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="bf8d7-119">ほぼリアルタイムで、アーティファクトが悪意のあると判明すると、デバイス上でブロックされます。</span><span class="sxs-lookup"><span data-stu-id="bf8d7-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="bf8d7-120">疑わしい動作が検出されると、アラートが生成[](alerts-queue.md)され、Microsoft 365 Defender ポータル[(以前](microsoft-defender-security-center.md)は Microsoft Defender セキュリティ センター) に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf8d7-120">Whenever a suspicious behavior is detected, an [alert](alerts-queue.md) is generated, and is visible in the [Microsoft 365 Defender portal](microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center).</span></span>

<span data-ttu-id="bf8d7-121">クライアントの動作ブロックは、攻撃の開始を防ぐだけでなく、実行を開始した攻撃を停止するのに役立つため、効果的です。</span><span class="sxs-lookup"><span data-stu-id="bf8d7-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="bf8d7-122">また、フィードバック [ループブロック](feedback-loop-blocking.md) (別の動作ブロックと格納機能) を使用すると、組織内の他のデバイスに対する攻撃が防止されます。</span><span class="sxs-lookup"><span data-stu-id="bf8d7-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="bf8d7-123">動作ベースの検出</span><span class="sxs-lookup"><span data-stu-id="bf8d7-123">Behavior-based detections</span></span>

<span data-ttu-id="bf8d7-124">動作ベースの検出の名前は[、MITRE ATT](https://attack.mitre.org/matrices/enterprise)&CK マトリックスに従Enterprise。</span><span class="sxs-lookup"><span data-stu-id="bf8d7-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="bf8d7-125">名前付け規則は、悪意のある動作が観察された攻撃段階を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bf8d7-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>

|<span data-ttu-id="bf8d7-126">戦術</span><span class="sxs-lookup"><span data-stu-id="bf8d7-126">Tactic</span></span> | <span data-ttu-id="bf8d7-127">検出の脅威名</span><span class="sxs-lookup"><span data-stu-id="bf8d7-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="bf8d7-128">初期アクセス</span><span class="sxs-lookup"><span data-stu-id="bf8d7-128">Initial Access</span></span> | `Behavior:Win32/InitialAccess.*!ml` |
|<span data-ttu-id="bf8d7-129">実行</span><span class="sxs-lookup"><span data-stu-id="bf8d7-129">Execution</span></span> | `Behavior:Win32/Execution.*!ml` |
|<span data-ttu-id="bf8d7-130">永続性</span><span class="sxs-lookup"><span data-stu-id="bf8d7-130">Persistence</span></span> | `Behavior:Win32/Persistence.*!ml` |
|<span data-ttu-id="bf8d7-131">特権エスカレーション</span><span class="sxs-lookup"><span data-stu-id="bf8d7-131">Privilege Escalation</span></span> | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|<span data-ttu-id="bf8d7-132">Defense Evasion</span><span class="sxs-lookup"><span data-stu-id="bf8d7-132">Defense Evasion</span></span> | `Behavior:Win32/DefenseEvasion.*!ml` |
|<span data-ttu-id="bf8d7-133">資格情報アクセス</span><span class="sxs-lookup"><span data-stu-id="bf8d7-133">Credential Access</span></span> | `Behavior:Win32/CredentialAccess.*!ml` |
|<span data-ttu-id="bf8d7-134">Discovery</span><span class="sxs-lookup"><span data-stu-id="bf8d7-134">Discovery</span></span> | `Behavior:Win32/Discovery.*!ml` |
|<span data-ttu-id="bf8d7-135">横方向の動き</span><span class="sxs-lookup"><span data-stu-id="bf8d7-135">Lateral Movement</span></span> | `Behavior:Win32/LateralMovement.*!ml` |
|<span data-ttu-id="bf8d7-136">Collection</span><span class="sxs-lookup"><span data-stu-id="bf8d7-136">Collection</span></span> | `Behavior:Win32/Collection.*!ml` |
|<span data-ttu-id="bf8d7-137">コマンドとコントロール</span><span class="sxs-lookup"><span data-stu-id="bf8d7-137">Command and Control</span></span> | `Behavior:Win32/CommandAndControl.*!ml` |
|<span data-ttu-id="bf8d7-138">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="bf8d7-138">Exfiltration</span></span> | `Behavior:Win32/Exfiltration.*!ml` |
|<span data-ttu-id="bf8d7-139">影響</span><span class="sxs-lookup"><span data-stu-id="bf8d7-139">Impact</span></span> | `Behavior:Win32/Impact.*!ml` |
|<span data-ttu-id="bf8d7-140">未分類</span><span class="sxs-lookup"><span data-stu-id="bf8d7-140">Uncategorized</span></span> | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> <span data-ttu-id="bf8d7-141">特定の脅威の詳細については、「最近のグローバル脅威 **[アクティビティ」を参照してください](https://www.microsoft.com/wdsi/threats)**。</span><span class="sxs-lookup"><span data-stu-id="bf8d7-141">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>

## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="bf8d7-142">クライアントの動作ブロックの構成</span><span class="sxs-lookup"><span data-stu-id="bf8d7-142">Configuring client behavioral blocking</span></span>

<span data-ttu-id="bf8d7-143">組織で Defender for Endpoint を使用している場合、クライアントの動作ブロックは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="bf8d7-143">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="bf8d7-144">ただし、動作ブロックや格納を含むすべての Defender [](behavioral-blocking-containment.md)for Endpoint 機能を利用するには、Defender for Endpoint の次の機能が有効で構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bf8d7-144">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="bf8d7-145">Defender for Endpoint baselines</span><span class="sxs-lookup"><span data-stu-id="bf8d7-145">Defender for Endpoint baselines</span></span>](configure-machines-security-baseline.md)

- [<span data-ttu-id="bf8d7-146">Defender for Endpoint にオンボードされているデバイス</span><span class="sxs-lookup"><span data-stu-id="bf8d7-146">Devices onboarded to Defender for Endpoint</span></span>](onboard-configure.md)

- [<span data-ttu-id="bf8d7-147">ブロック モードの EDR</span><span class="sxs-lookup"><span data-stu-id="bf8d7-147">EDR in block mode</span></span>](edr-in-block-mode.md)

- [<span data-ttu-id="bf8d7-148">攻撃面の減少</span><span class="sxs-lookup"><span data-stu-id="bf8d7-148">Attack surface reduction</span></span>](attack-surface-reduction.md)

- <span data-ttu-id="bf8d7-149">[次世代保護](configure-microsoft-defender-antivirus-features.md) (ウイルス対策、マルウェア対策、その他の脅威保護機能)</span><span class="sxs-lookup"><span data-stu-id="bf8d7-149">[Next-generation protection](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware, and other threat protection capabilities)</span></span>
