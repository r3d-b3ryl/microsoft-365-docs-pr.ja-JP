---
title: 保護機能を有効Microsoft Defender ウイルス対策構成する
description: Microsoft Defender AV で動作ベース、ヒューリスティック、およびリアルタイム保護を有効にする。
keywords: ヒューリスティック、機械学習、動作モニター、リアルタイム保護、常時オン、Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 53b1e1474e0870388ec1cfaf214190eb0bdf7beb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274610"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a><span data-ttu-id="3292b-104">行動、ヒューリスティック、リアルタイム保護を構成する</span><span class="sxs-lookup"><span data-stu-id="3292b-104">Configure behavioral, heuristic, and real-time protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3292b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3292b-105">**Applies to:**</span></span>

- [<span data-ttu-id="3292b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3292b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="3292b-107">Microsoft Defender ウイルス対策を使用して脅威保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="3292b-107">Microsoft Defender Antivirus uses several methods to provide threat protection:</span></span>

- <span data-ttu-id="3292b-108">新しい脅威や新しい脅威のほぼ瞬時の検出とブロックのためのクラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="3292b-108">Cloud-delivered protection for near-instant detection and blocking of new and emerging threats</span></span>
- <span data-ttu-id="3292b-109">ファイルとプロセスの動作の監視、その他のヒューリスティックを使用した常時スキャン ("リアルタイム保護" とも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="3292b-109">Always-on scanning, using file and process behavior monitoring and other heuristics (also known as "real-time protection")</span></span>
- <span data-ttu-id="3292b-110">機械学習、手動および自動のビッグデータ分析、徹底した脅威耐性調査に基づいた専用の保護の更新</span><span class="sxs-lookup"><span data-stu-id="3292b-110">Dedicated protection updates based on machine-learning, human and automated big-data analysis, and in-depth threat resistance research</span></span>

<span data-ttu-id="3292b-111">グループ ポリシー、Microsoft Defender ウイルス対策 System Center構成管理、PowerShell コマンドレット、および WINDOWS 管理インストルメンテーション (WMI) を使用して、これらのメソッドWindows構成できます。</span><span class="sxs-lookup"><span data-stu-id="3292b-111">You can configure how Microsoft Defender Antivirus uses these methods with Group Policy, System Center Configuration Manage, PowerShell cmdlets, and Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="3292b-112">このセクションでは、安全ではないと見なされるがマルウェアとして検出されない可能性があるアプリを検出およびブロックする方法など、常時スキャンの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="3292b-112">This section covers configuration for always-on scanning, including how to detect and block apps that are deemed unsafe, but may not be detected as malware.</span></span>

<span data-ttu-id="3292b-113">クラウド[配信保護を](cloud-protection-microsoft-defender-antivirus.md)有効にして構成するMicrosoft Defender ウイルス対策保護を通じて次世代のテクノロジを使用するMicrosoft Defender ウイルス対策を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3292b-113">See [Use next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3292b-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3292b-114">In this section</span></span>

 <span data-ttu-id="3292b-115">トピック</span><span class="sxs-lookup"><span data-stu-id="3292b-115">Topic</span></span> | <span data-ttu-id="3292b-116">説明</span><span class="sxs-lookup"><span data-stu-id="3292b-116">Description</span></span>
---|---
[<span data-ttu-id="3292b-117">望ましくない可能性のあるアプリケーションを検出してブロックする</span><span class="sxs-lookup"><span data-stu-id="3292b-117">Detect and block potentially unwanted applications</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | <span data-ttu-id="3292b-118">アドウェア、ブラウザー修飾子、ツール バー、不正なウイルス対策アプリや偽のウイルス対策アプリなど、ネットワークで望ましくない可能性があるアプリを検出してブロックする</span><span class="sxs-lookup"><span data-stu-id="3292b-118">Detect and block apps that may be unwanted in your network, such as adware, browser modifiers and toolbars, and rogue or fake antivirus apps</span></span>
[<span data-ttu-id="3292b-119">保護機能を有効Microsoft Defender ウイルス対策構成する</span><span class="sxs-lookup"><span data-stu-id="3292b-119">Enable and configure Microsoft Defender Antivirus protection capabilities</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md) | <span data-ttu-id="3292b-120">リアルタイム保護、ヒューリスティック、その他の常時監視機能を有効Microsoft Defender ウイルス対策構成する</span><span class="sxs-lookup"><span data-stu-id="3292b-120">Enable and configure real-time protection, heuristics, and other always-on Microsoft Defender Antivirus monitoring features</span></span>