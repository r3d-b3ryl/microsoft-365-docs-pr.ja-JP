---
title: Microsoft Defender ウイルス対策の機能を有効にして構成する
description: Microsoft Defender AV で動作ベース、ヒューリスティック、およびリアルタイム保護を有効にする。
keywords: ヒューリスティック、機械学習、動作モニター、リアルタイム保護、Always-on、Microsoft Defender Antivirus、マルウェア対策、セキュリティ、防御
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 9fc51682b659670a21c3c293ea8996beb228802a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765073"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a><span data-ttu-id="640ae-104">動作、ヒューリスティック、およびリアルタイムの保護を構成する</span><span class="sxs-lookup"><span data-stu-id="640ae-104">Configure behavioral, heuristic, and real-time protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="640ae-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="640ae-105">**Applies to:**</span></span>

- [<span data-ttu-id="640ae-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="640ae-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="640ae-107">Microsoft Defender ウイルス対策は、脅威保護を提供するためにいくつかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="640ae-107">Microsoft Defender Antivirus uses several methods to provide threat protection:</span></span>

- <span data-ttu-id="640ae-108">新しい脅威や新しい脅威のほぼ瞬時の検出とブロックのためのクラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="640ae-108">Cloud-delivered protection for near-instant detection and blocking of new and emerging threats</span></span>
- <span data-ttu-id="640ae-109">ファイルとプロセスの動作の監視、その他のヒューリスティックを使用した常時スキャン ("リアルタイム保護" とも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="640ae-109">Always-on scanning, using file and process behavior monitoring and other heuristics (also known as "real-time protection")</span></span>
- <span data-ttu-id="640ae-110">機械学習、手動および自動のビッグデータ分析、徹底した脅威耐性調査に基づいた専用の保護の更新</span><span class="sxs-lookup"><span data-stu-id="640ae-110">Dedicated protection updates based on machine-learning, human and automated big-data analysis, and in-depth threat resistance research</span></span>

<span data-ttu-id="640ae-111">グループ ポリシー、System Center Configuration Manage、PowerShell コマンドレット、および Windows 管理インストルメンテーション (WMI) を使用して、Microsoft Defender Antivirus がこれらのメソッドを使用する方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="640ae-111">You can configure how Microsoft Defender Antivirus uses these methods with Group Policy, System Center Configuration Manage, PowerShell cmdlets, and Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="640ae-112">このセクションでは、安全ではないと見なされるがマルウェアとして検出されない可能性があるアプリを検出およびブロックする方法など、常時スキャンの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="640ae-112">This section covers configuration for always-on scanning, including how to detect and block apps that are deemed unsafe, but may not be detected as malware.</span></span>

<span data-ttu-id="640ae-113">Microsoft Defender ウイルス [対策クラウド配信](cloud-protection-microsoft-defender-antivirus.md) 保護を有効にして構成する方法については、「クラウド提供の保護を通じて次世代の Microsoft Defender ウイルス対策テクノロジを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="640ae-113">See [Use next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="640ae-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="640ae-114">In this section</span></span>

 <span data-ttu-id="640ae-115">トピック</span><span class="sxs-lookup"><span data-stu-id="640ae-115">Topic</span></span> | <span data-ttu-id="640ae-116">説明</span><span class="sxs-lookup"><span data-stu-id="640ae-116">Description</span></span>
---|---
[<span data-ttu-id="640ae-117">望ましくない可能性のあるアプリケーションの検出とブロック</span><span class="sxs-lookup"><span data-stu-id="640ae-117">Detect and block potentially unwanted applications</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | <span data-ttu-id="640ae-118">アドウェア、ブラウザー修飾子、ツール バー、不正なウイルス対策アプリや偽のウイルス対策アプリなど、ネットワークで望ましくない可能性があるアプリを検出してブロックする</span><span class="sxs-lookup"><span data-stu-id="640ae-118">Detect and block apps that may be unwanted in your network, such as adware, browser modifiers and toolbars, and rogue or fake antivirus apps</span></span>
[<span data-ttu-id="640ae-119">Microsoft Defender ウイルス対策保護機能を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="640ae-119">Enable and configure Microsoft Defender Antivirus protection capabilities</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md) | <span data-ttu-id="640ae-120">リアルタイム保護、ヒューリスティック、その他の常時オンの Microsoft Defender ウイルス対策監視機能を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="640ae-120">Enable and configure real-time protection, heuristics, and other always-on Microsoft Defender Antivirus monitoring features</span></span>