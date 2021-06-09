---
title: フィードバック ループのブロック
description: フィードバック ループのブロック (高速保護とも呼ばれる) は、Microsoft Defender for Endpoint の動作ブロックおよび格納機能の一部です。
keywords: 動作ブロック、迅速な保護、フィードバックブロック、Microsoft Defender for Endpoint
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
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: 7319ff5a89a20529eed7d36aa0d0b1522013abd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842460"
---
# <a name="feedback-loop-blocking"></a><span data-ttu-id="cd7d7-104">フィードバック ループのブロック</span><span class="sxs-lookup"><span data-stu-id="cd7d7-104">Feedback-loop blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cd7d7-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cd7d7-105">**Applies to:**</span></span>
- [<span data-ttu-id="cd7d7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cd7d7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a><span data-ttu-id="cd7d7-107">概要</span><span class="sxs-lookup"><span data-stu-id="cd7d7-107">Overview</span></span>

<span data-ttu-id="cd7d7-108">フィードバック ループブロックは、高速保護とも呼ばれますが、Microsoft Defender [](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) for Endpoint の動作ブロックおよび格納機能の[コンポーネントです](/windows/security/threat-protection/)。</span><span class="sxs-lookup"><span data-stu-id="cd7d7-108">Feedback-loop blocking, also referred to as rapid protection, is a component of [behavioral blocking and containment capabilities](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in [Microsoft Defender for Endpoint](/windows/security/threat-protection/).</span></span> <span data-ttu-id="cd7d7-109">フィードバック ループブロックを使用すると、組織全体のデバイスが攻撃から保護されます。</span><span class="sxs-lookup"><span data-stu-id="cd7d7-109">With feedback-loop blocking, devices across your organization are better protected from attacks.</span></span> 

## <a name="how-feedback-loop-blocking-works"></a><span data-ttu-id="cd7d7-110">フィードバック ループのブロックのしくみ</span><span class="sxs-lookup"><span data-stu-id="cd7d7-110">How feedback-loop blocking works</span></span>

<span data-ttu-id="cd7d7-111">不審な動作やファイルが検出された場合 (Microsoft Defender ウイルス対策など[](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10))、その成果物に関する情報が複数の分類子に送信されます。</span><span class="sxs-lookup"><span data-stu-id="cd7d7-111">When a suspicious behavior or file is detected, such as by [Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), information about that artifact is sent to multiple classifiers.</span></span> <span data-ttu-id="cd7d7-112">高速保護ループ エンジンは、情報を検査し、他の信号と関連付け、ファイルをブロックするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="cd7d7-112">The rapid protection loop engine inspects and correlates the information with other signals to arrive at a decision as to whether to block a file.</span></span> <span data-ttu-id="cd7d7-113">アーティファクトのチェックと分類は、迅速に行います。</span><span class="sxs-lookup"><span data-stu-id="cd7d7-113">Checking and classifying artifacts happens quickly.</span></span> <span data-ttu-id="cd7d7-114">その結果、確認されたマルウェアが急速にブロックされ、エコシステム全体の保護が強化されます。</span><span class="sxs-lookup"><span data-stu-id="cd7d7-114">It results in rapid blocking of confirmed malware, and drives protection across the entire ecosystem.</span></span> 

<span data-ttu-id="cd7d7-115">迅速な保護を実施すると、攻撃が足場を広げろとして、デバイス、組織内の他のデバイス、および他の組織のデバイスで攻撃を停止できます。</span><span class="sxs-lookup"><span data-stu-id="cd7d7-115">With rapid protection in place, an attack can be stopped on a device, other devices in the organization, and devices in other organizations, as an attack attempts to broaden its foothold.</span></span>


## <a name="configuring-feedback-loop-blocking"></a><span data-ttu-id="cd7d7-116">フィードバック ループブロックの構成</span><span class="sxs-lookup"><span data-stu-id="cd7d7-116">Configuring feedback-loop blocking</span></span>

<span data-ttu-id="cd7d7-117">組織で Defender for Endpoint を使用している場合、フィードバック ループブロックは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="cd7d7-117">If your organization is using Defender for Endpoint, feedback-loop blocking is enabled by default.</span></span> <span data-ttu-id="cd7d7-118">ただし、Defender for Endpoint 機能、機械学習保護機能、および Microsoft セキュリティ サービス全体でのシグナル共有を組み合わせて、迅速な保護が行われます。</span><span class="sxs-lookup"><span data-stu-id="cd7d7-118">However, rapid protection occurs through a combination of Defender for Endpoint capabilities, machine learning protection features, and signal-sharing across Microsoft security services.</span></span> <span data-ttu-id="cd7d7-119">Defender for Endpoint の次の機能が有効で構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd7d7-119">Make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="cd7d7-120">エンドポイントベースライン用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cd7d7-120">Microsoft Defender for Endpoint baselines</span></span>](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="cd7d7-121">Microsoft Defender for Endpoint にオンボードされているデバイス</span><span class="sxs-lookup"><span data-stu-id="cd7d7-121">Devices onboarded to Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="cd7d7-122">ブロック モードの EDR</span><span class="sxs-lookup"><span data-stu-id="cd7d7-122">EDR in block mode</span></span>](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="cd7d7-123">攻撃面の減少</span><span class="sxs-lookup"><span data-stu-id="cd7d7-123">Attack surface reduction</span></span>](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="cd7d7-124">[次世代保護](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (ウイルス対策)</span><span class="sxs-lookup"><span data-stu-id="cd7d7-124">[Next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="cd7d7-125">関連資料</span><span class="sxs-lookup"><span data-stu-id="cd7d7-125">Related articles</span></span>

- [<span data-ttu-id="cd7d7-126">動作ブロックと封じ込め</span><span class="sxs-lookup"><span data-stu-id="cd7d7-126">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="cd7d7-127">(ブログ)動作のブロックと格納: 光学を保護に変換する</span><span class="sxs-lookup"><span data-stu-id="cd7d7-127">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="cd7d7-128">エンドポイントのリソースに役立つ Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cd7d7-128">Helpful Microsoft Defender for Endpoint resources</span></span>](/microsoft-365/security/defender-endpoint/helpful-resources)
