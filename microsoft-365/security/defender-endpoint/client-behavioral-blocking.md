---
title: クライアントの動作ブロック
description: クライアントの動作ブロックは、Microsoft Defender for Endpoint の動作ブロックと格納機能の一部です。
keywords: 動作ブロック、迅速な保護、クライアントの動作、Microsoft Defender ATP
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
ms.openlocfilehash: 9fcff96b2583c6ef6bec05429ec50a71f3872e43
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587109"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="cc621-104">クライアントの動作ブロック</span><span class="sxs-lookup"><span data-stu-id="cc621-104">Client behavioral blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cc621-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cc621-105">**Applies to:**</span></span>
- [<span data-ttu-id="cc621-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cc621-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cc621-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc621-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="cc621-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="cc621-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cc621-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="cc621-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="cc621-110">概要</span><span class="sxs-lookup"><span data-stu-id="cc621-110">Overview</span></span>

<span data-ttu-id="cc621-111">クライアントの動作ブロックは、Defender [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) for Endpoint の動作ブロックと格納機能のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="cc621-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in Defender for Endpoint.</span></span> <span data-ttu-id="cc621-112">デバイス (クライアントまたはエンドポイントとも呼ばれます) で疑わしい動作が検出されると、アーティファクト (ファイルやアプリケーションなど) が自動的にブロック、チェック、修復されます。</span><span class="sxs-lookup"><span data-stu-id="cc621-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="クラウドとクライアントの保護":::

<span data-ttu-id="cc621-114">ウイルス対策保護は、クラウド保護と組み合わせた場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="cc621-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="cc621-115">クライアントの動作のブロックのしくみ</span><span class="sxs-lookup"><span data-stu-id="cc621-115">How client behavioral blocking works</span></span>

<span data-ttu-id="cc621-116">[Microsoft Defender ウイルス対策では](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 、デバイス上で疑わしい動作、悪意のあるコード、ファイルレス攻撃やメモリ内攻撃を検出できます。</span><span class="sxs-lookup"><span data-stu-id="cc621-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="cc621-117">疑わしい動作が検出されると、Microsoft Defender ウイルス対策は、疑わしい動作とそのプロセス ツリーを監視し、クラウド保護サービスに送信します。</span><span class="sxs-lookup"><span data-stu-id="cc621-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="cc621-118">機械学習は、悪意のあるアプリケーションと適切な動作をミリ秒単位で区別し、各成果物を分類します。</span><span class="sxs-lookup"><span data-stu-id="cc621-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="cc621-119">ほぼリアルタイムで、アーティファクトが悪意のあると判明すると、デバイス上でブロックされます。</span><span class="sxs-lookup"><span data-stu-id="cc621-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="cc621-120">疑わしい動作が検出されると、 [アラートが生成](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) され、Microsoft Defender セキュリティ センター () に表示されます [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="cc621-120">Whenever a suspicious behavior is detected, an [alert](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="cc621-121">クライアントの動作ブロックは、攻撃の開始を防ぐだけでなく、実行を開始した攻撃を停止するのに役立つため、効果的です。</span><span class="sxs-lookup"><span data-stu-id="cc621-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="cc621-122">また、フィードバック [ループブロック](feedback-loop-blocking.md) (別の動作ブロックと格納機能) を使用すると、組織内の他のデバイスに対する攻撃が防止されます。</span><span class="sxs-lookup"><span data-stu-id="cc621-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="cc621-123">動作ベースの検出</span><span class="sxs-lookup"><span data-stu-id="cc621-123">Behavior-based detections</span></span>

<span data-ttu-id="cc621-124">動作ベースの検出の名前は [、MITRE ATT](https://attack.mitre.org/matrices/enterprise)&CK Matrix for Enterprise に従います。</span><span class="sxs-lookup"><span data-stu-id="cc621-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="cc621-125">名前付け規則は、悪意のある動作が観察された攻撃段階を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cc621-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="cc621-126">戦術</span><span class="sxs-lookup"><span data-stu-id="cc621-126">Tactic</span></span> |   <span data-ttu-id="cc621-127">検出の脅威名</span><span class="sxs-lookup"><span data-stu-id="cc621-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="cc621-128">初期アクセス</span><span class="sxs-lookup"><span data-stu-id="cc621-128">Initial Access</span></span> | <span data-ttu-id="cc621-129">動作:Win32/InitialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="cc621-129">Behavior:Win32/InitialAccess.\*!ml</span></span> |
|<span data-ttu-id="cc621-130">実行</span><span class="sxs-lookup"><span data-stu-id="cc621-130">Execution</span></span>  | <span data-ttu-id="cc621-131">動作:Win32/Execution.\*!ml</span><span class="sxs-lookup"><span data-stu-id="cc621-131">Behavior:Win32/Execution.\*!ml</span></span> |
|<span data-ttu-id="cc621-132">永続性</span><span class="sxs-lookup"><span data-stu-id="cc621-132">Persistence</span></span>    | <span data-ttu-id="cc621-133">動作:Win32/Persistence.\*!ml</span><span class="sxs-lookup"><span data-stu-id="cc621-133">Behavior:Win32/Persistence.\*!ml</span></span> |
|<span data-ttu-id="cc621-134">特権エスカレーション</span><span class="sxs-lookup"><span data-stu-id="cc621-134">Privilege Escalation</span></span>   | <span data-ttu-id="cc621-135">動作:Win32/PrivilegeEscalation.\*!ml</span><span class="sxs-lookup"><span data-stu-id="cc621-135">Behavior:Win32/PrivilegeEscalation.\*!ml</span></span> |
|<span data-ttu-id="cc621-136">Defense Evasion</span><span class="sxs-lookup"><span data-stu-id="cc621-136">Defense Evasion</span></span>    | <span data-ttu-id="cc621-137">動作:Win32/DefenseEvasion.\*!ml</span><span class="sxs-lookup"><span data-stu-id="cc621-137">Behavior:Win32/DefenseEvasion.\*!ml</span></span> |
|<span data-ttu-id="cc621-138">資格情報アクセス</span><span class="sxs-lookup"><span data-stu-id="cc621-138">Credential Access</span></span>  | <span data-ttu-id="cc621-139">動作:Win32/CredentialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="cc621-139">Behavior:Win32/CredentialAccess.\*!ml</span></span> |
|<span data-ttu-id="cc621-140">検出</span><span class="sxs-lookup"><span data-stu-id="cc621-140">Discovery</span></span>  | <span data-ttu-id="cc621-141">動作:Win32/Discovery.\*!ml</span><span class="sxs-lookup"><span data-stu-id="cc621-141">Behavior:Win32/Discovery.\*!ml</span></span> |
|<span data-ttu-id="cc621-142">横方向の動き</span><span class="sxs-lookup"><span data-stu-id="cc621-142">Lateral Movement</span></span> | <span data-ttu-id="cc621-143">動作:Win32/LateralMovement.\*!ml</span><span class="sxs-lookup"><span data-stu-id="cc621-143">Behavior:Win32/LateralMovement.\*!ml</span></span> |
|<span data-ttu-id="cc621-144">Collection</span><span class="sxs-lookup"><span data-stu-id="cc621-144">Collection</span></span> |   <span data-ttu-id="cc621-145">動作:Win32/Collection.\*!ml</span><span class="sxs-lookup"><span data-stu-id="cc621-145">Behavior:Win32/Collection.\*!ml</span></span> |
|<span data-ttu-id="cc621-146">コマンドとコントロール</span><span class="sxs-lookup"><span data-stu-id="cc621-146">Command and Control</span></span> | <span data-ttu-id="cc621-147">動作:Win32/CommandAndControl.\*!ml</span><span class="sxs-lookup"><span data-stu-id="cc621-147">Behavior:Win32/CommandAndControl.\*!ml</span></span> |
|<span data-ttu-id="cc621-148">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="cc621-148">Exfiltration</span></span>   | <span data-ttu-id="cc621-149">動作:Win32/Exfiltration.\*!ml</span><span class="sxs-lookup"><span data-stu-id="cc621-149">Behavior:Win32/Exfiltration.\*!ml</span></span> |
|<span data-ttu-id="cc621-150">影響</span><span class="sxs-lookup"><span data-stu-id="cc621-150">Impact</span></span> | <span data-ttu-id="cc621-151">動作:Win32/Impact.\*!ml</span><span class="sxs-lookup"><span data-stu-id="cc621-151">Behavior:Win32/Impact.\*!ml</span></span> |
|<span data-ttu-id="cc621-152">未分類</span><span class="sxs-lookup"><span data-stu-id="cc621-152">Uncategorized</span></span>  | <span data-ttu-id="cc621-153">動作:Win32/Generic.\*!ml</span><span class="sxs-lookup"><span data-stu-id="cc621-153">Behavior:Win32/Generic.\*!ml</span></span> |

> [!TIP]
> <span data-ttu-id="cc621-154">特定の脅威の詳細については、「最近のグローバル脅威 **[アクティビティ」を参照してください](https://www.microsoft.com/wdsi/threats)**。</span><span class="sxs-lookup"><span data-stu-id="cc621-154">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="cc621-155">クライアントの動作ブロックの構成</span><span class="sxs-lookup"><span data-stu-id="cc621-155">Configuring client behavioral blocking</span></span>

<span data-ttu-id="cc621-156">組織で Defender for Endpoint を使用している場合、クライアントの動作ブロックは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="cc621-156">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="cc621-157">ただし、動作ブロックや格納を含むすべての Defender [](behavioral-blocking-containment.md)for Endpoint 機能を利用するには、Defender for Endpoint の次の機能が有効で構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cc621-157">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="cc621-158">Defender for Endpoint baselines</span><span class="sxs-lookup"><span data-stu-id="cc621-158">Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="cc621-159">Defender for Endpoint にオンボードされているデバイス</span><span class="sxs-lookup"><span data-stu-id="cc621-159">Devices onboarded to Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="cc621-160">ブロック モードの EDR</span><span class="sxs-lookup"><span data-stu-id="cc621-160">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="cc621-161">攻撃面の減少</span><span class="sxs-lookup"><span data-stu-id="cc621-161">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="cc621-162">[次世代保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (ウイルス対策)</span><span class="sxs-lookup"><span data-stu-id="cc621-162">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="cc621-163">関連記事</span><span class="sxs-lookup"><span data-stu-id="cc621-163">Related articles</span></span>

- [<span data-ttu-id="cc621-164">動作ブロックと封じ込め</span><span class="sxs-lookup"><span data-stu-id="cc621-164">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="cc621-165">フィードバック ループのブロック</span><span class="sxs-lookup"><span data-stu-id="cc621-165">Feedback-loop blocking</span></span>](feedback-loop-blocking.md)

- [<span data-ttu-id="cc621-166">(ブログ)動作のブロックと格納: 光学を保護に変換する</span><span class="sxs-lookup"><span data-stu-id="cc621-166">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="cc621-167">エンドポイントのリソースに役立つ Defender</span><span class="sxs-lookup"><span data-stu-id="cc621-167">Helpful Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
