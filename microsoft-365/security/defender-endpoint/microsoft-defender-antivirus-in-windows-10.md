---
title: 次世代の保護
description: 組み込みのマルウェア対策とウイルス対策の保護機能である Microsoft Defender ウイルス対策を管理、構成、使用する方法について説明します。
keywords: Microsoft Defender ウイルス対策, windows defender, マルウェア対策, scep, システム センター エンドポイント保護, システム センター構成マネージャー, ウイルス, マルウェア, 脅威, 検出, 保護, セキュリティ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: c4a0e40f3f6e6728af3d8c7a6da29485f1fad3fd
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269602"
---
# <a name="next-generation-protection"></a><span data-ttu-id="46836-104">次世代の保護</span><span class="sxs-lookup"><span data-stu-id="46836-104">Next-generation protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="46836-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="46836-105">**Applies to:**</span></span>

- [<span data-ttu-id="46836-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="46836-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

## <a name="microsoft-defender-antivirus-your-next-generation-protection"></a><span data-ttu-id="46836-107">Microsoft Defender ウイルス対策: 次世代の保護</span><span class="sxs-lookup"><span data-stu-id="46836-107">Microsoft Defender Antivirus: Your next-generation protection</span></span>

<span data-ttu-id="46836-108">Microsoft Defender ウイルス対策は、Microsoft Defender for Endpoint の次世代保護コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="46836-108">Microsoft Defender Antivirus is the next-generation protection component of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="46836-109">この保護は、機械学習、ビッグデータ分析、脅威耐性に関する詳細な調査、Microsoft のクラウド インフラストラクチャを組み合わせて、企業組織内のデバイスを保護します。</span><span class="sxs-lookup"><span data-stu-id="46836-109">This protection brings together machine learning, big-data analysis, in-depth threat resistance research, and the Microsoft cloud infrastructure to protect devices in your enterprise organization.</span></span> <span data-ttu-id="46836-110">次世代の保護サービスには以下の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="46836-110">Your next-generation protection services include the following capabilities:</span></span>

- <span data-ttu-id="46836-111">[挙動ベースおよびヒューリスティックのリアルタイム ウイルス対策保護](configure-protection-features-microsoft-defender-antivirus.md)。これには、ファイルとプロセスの動作監視およびその他のヒューリスティックを使用した常時オンのスキャンが含まれています (「*リアルタイム保護*」とも呼ばれています)。</span><span class="sxs-lookup"><span data-stu-id="46836-111">[Behavior-based, heuristic, and real-time antivirus protection](configure-protection-features-microsoft-defender-antivirus.md), which includes always-on scanning using file and process behavior monitoring and other heuristics (also known as *real-time protection*).</span></span> <span data-ttu-id="46836-112">安全ではないと見なされているもののマルウェアとして検出されない可能性のあるアプリの検出とブロックも含まれています。</span><span class="sxs-lookup"><span data-stu-id="46836-112">It also includes detecting and blocking apps that are deemed unsafe, but might not be detected as malware.</span></span>
- <span data-ttu-id="46836-113">[クラウドによる保護](cloud-protection-microsoft-defender-antivirus.md)。これには、新たに出現する脅威のほぼ瞬時の検出とブロックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="46836-113">[Cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md), which includes near-instant detection and blocking of new and emerging threats.</span></span>
- <span data-ttu-id="46836-114">[専用の保護および製品の更新プログラム](manage-updates-baselines-microsoft-defender-antivirus.md)。これには、Microsoft Defender ウイルス対策を最新状態に維持することに関連する更新プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="46836-114">[Dedicated protection and product updates](manage-updates-baselines-microsoft-defender-antivirus.md), which includes updates related to keeping Microsoft Defender Antivirus up to date.</span></span>

## <a name="try-a-demo"></a><span data-ttu-id="46836-115">デモを試す</span><span class="sxs-lookup"><span data-stu-id="46836-115">Try a demo!</span></span>

<span data-ttu-id="46836-116">[Microsoft Defender for Endpoint のデモ用 Web サイト](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)にアクセスし、以下の保護機能が動作していることを確認したり、デモのシナリオを使用して検証したりしましょう。</span><span class="sxs-lookup"><span data-stu-id="46836-116">Visit the [Microsoft Defender for Endpoint demo website](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following protection features are working and explore them using demo scenarios:</span></span>
- <span data-ttu-id="46836-117">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="46836-117">Cloud-delivered protection</span></span>
- <span data-ttu-id="46836-118">事前ブロック (BAFS) 保護</span><span class="sxs-lookup"><span data-stu-id="46836-118">Block at first sight (BAFS) protection</span></span>
- <span data-ttu-id="46836-119">望ましくない可能性のあるアプリケーション (PUA) 保護</span><span class="sxs-lookup"><span data-stu-id="46836-119">Potentially unwanted applications (PUA) protection</span></span>

## <a name="minimum-system-requirements"></a><span data-ttu-id="46836-120">最小システム要件</span><span class="sxs-lookup"><span data-stu-id="46836-120">Minimum system requirements</span></span>

<span data-ttu-id="46836-121">Microsoft Defender ウイルス対策のハードウェア要件は、Windows 10 と同じです。</span><span class="sxs-lookup"><span data-stu-id="46836-121">Microsoft Defender Antivirus has the same hardware requirements as of Windows 10.</span></span> <span data-ttu-id="46836-122">詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="46836-122">For more information, see the following resources:</span></span>

- [<span data-ttu-id="46836-123">ハードウェアの最小要件</span><span class="sxs-lookup"><span data-stu-id="46836-123">Minimum hardware requirements</span></span>](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [<span data-ttu-id="46836-124">ハードウェア コンポーネントのガイドライン</span><span class="sxs-lookup"><span data-stu-id="46836-124">Hardware component guidelines</span></span>](/windows-hardware/design/component-guidelines/components)

## <a name="configure-next-generation-protection-services"></a><span data-ttu-id="46836-125">次世代の保護サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="46836-125">Configure next-generation protection services</span></span>

<span data-ttu-id="46836-126">次世代の保護サービスを構成する方法の詳細については、「[Microsoft Defender ウイルス対策機能を構成する](configure-microsoft-defender-antivirus-features.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46836-126">For information on how to configure next-generation protection services, see [Configure Microsoft Defender Antivirus features](configure-microsoft-defender-antivirus-features.md).</span></span>

> [!Note]  
> <span data-ttu-id="46836-127">Microsoft Defender ウイルス対策の実行中、構成と管理は Windows Server 2016 と Windows Server 2019 でほぼ同じです。ただし、いくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="46836-127">Configuration and management is largely the same in Windows Server 2016 and Windows Server 2019, while running Microsoft Defender Antivirus; however, there are some differences.</span></span> <span data-ttu-id="46836-128">詳細については、「[Windows Server 2016 および 2019 上の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46836-128">To learn more, see [Microsoft Defender Antivirus on Windows Server 2016 and 2019](microsoft-defender-antivirus-on-windows-server.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="46836-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="46836-129">See also</span></span>

- [<span data-ttu-id="46836-130">Windows Server 2016 および 2019 上の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="46836-130">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="46836-131">Microsoft Defender ウイルス対策の管理および構成</span><span class="sxs-lookup"><span data-stu-id="46836-131">Microsoft Defender Antivirus management and configuration</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="46836-132">Microsoft Defender ウイルス対策を評価する</span><span class="sxs-lookup"><span data-stu-id="46836-132">Evaluate Microsoft Defender Antivirus protection</span></span>](evaluate-microsoft-defender-antivirus.md)
