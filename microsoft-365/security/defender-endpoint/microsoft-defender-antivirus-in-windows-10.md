---
title: 次世代の保護
description: Microsoft Defender Antivirus、組み込みのマルウェア対策、ウイルス対策保護を管理、構成、および使用する方法について説明します。
keywords: Microsoft Defender ウイルス対策、Windows Defender、マルウェア対策、scep、システム センター エンドポイント保護、システム センター構成マネージャー、ウイルス、マルウェア、脅威、検出、保護、セキュリティ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 9d8ab5be45e671fb07df0d9d1f46eb626d9dd149
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690962"
---
# <a name="next-generation-protection"></a><span data-ttu-id="8f082-104">次世代の保護</span><span class="sxs-lookup"><span data-stu-id="8f082-104">Next-generation protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8f082-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8f082-105">**Applies to:**</span></span>

- [<span data-ttu-id="8f082-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8f082-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

## <a name="microsoft-defender-antivirus-your-next-generation-protection"></a><span data-ttu-id="8f082-107">Microsoft Defender ウイルス対策: 次世代の保護</span><span class="sxs-lookup"><span data-stu-id="8f082-107">Microsoft Defender Antivirus: Your next-generation protection</span></span>

<span data-ttu-id="8f082-108">Microsoft Defender Antivirus は、Microsoft Defender for Endpoint の次世代保護コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="8f082-108">Microsoft Defender Antivirus is the next-generation protection component of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="8f082-109">この保護により、機械学習、ビッグ データ分析、詳細な脅威耐性調査、Microsoft クラウド インフラストラクチャが統合され、企業組織内のデバイスを保護できます。</span><span class="sxs-lookup"><span data-stu-id="8f082-109">This protection brings together machine learning, big-data analysis, in-depth threat resistance research, and the Microsoft cloud infrastructure to protect devices in your enterprise organization.</span></span> <span data-ttu-id="8f082-110">次世代の保護サービスには、次の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f082-110">Your next-generation protection services include the following capabilities:</span></span>

- <span data-ttu-id="8f082-111">[動作ベース、](configure-protection-features-microsoft-defender-antivirus.md)ヒューリスティック、リアルタイムのウイルス対策保護 。これには、ファイルとプロセスの動作監視を使用した常時スキャンと、その他のヒューリスティック (リアルタイム保護とも呼 *ばれる)* が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f082-111">[Behavior-based, heuristic, and real-time antivirus protection](configure-protection-features-microsoft-defender-antivirus.md), which includes always-on scanning using file and process behavior monitoring and other heuristics (also known as *real-time protection*).</span></span> <span data-ttu-id="8f082-112">また、安全ではないと見なされるが、マルウェアとして検出されない可能性があるアプリの検出とブロックも含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f082-112">It also includes detecting and blocking apps that are deemed unsafe, but might not be detected as malware.</span></span>
- <span data-ttu-id="8f082-113">[クラウドによって提供される保護](cloud-protection-microsoft-defender-antivirus.md)。これには、新しい脅威や新しい脅威のほぼ瞬時の検出とブロックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f082-113">[Cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md), which includes near-instant detection and blocking of new and emerging threats.</span></span>
- <span data-ttu-id="8f082-114">[専用の保護と製品の更新](manage-updates-baselines-microsoft-defender-antivirus.md)プログラム (Microsoft Defender ウイルス対策を最新の状態に保つことに関連する更新プログラムを含む)。</span><span class="sxs-lookup"><span data-stu-id="8f082-114">[Dedicated protection and product updates](manage-updates-baselines-microsoft-defender-antivirus.md), which includes updates related to keeping Microsoft Defender Antivirus up to date.</span></span>

## <a name="try-a-demo"></a><span data-ttu-id="8f082-115">デモをお試しください。</span><span class="sxs-lookup"><span data-stu-id="8f082-115">Try a demo!</span></span>

<span data-ttu-id="8f082-116">Microsoft [Defender for Endpoint のデモ Web サイトにアクセス](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) して、次の保護機能が機能しているのを確認し、デモ シナリオを使用してそれらを確認します。</span><span class="sxs-lookup"><span data-stu-id="8f082-116">Visit the [Microsoft Defender for Endpoint demo website](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following protection features are working and explore them using demo scenarios:</span></span>
- <span data-ttu-id="8f082-117">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="8f082-117">Cloud-delivered protection</span></span>
- <span data-ttu-id="8f082-118">一目でブロックする (BAFS) 保護</span><span class="sxs-lookup"><span data-stu-id="8f082-118">Block at first sight (BAFS) protection</span></span>
- <span data-ttu-id="8f082-119">望ましくない可能性のあるアプリケーション (PUA) 保護</span><span class="sxs-lookup"><span data-stu-id="8f082-119">Potentially unwanted applications (PUA) protection</span></span>

## <a name="minimum-system-requirements"></a><span data-ttu-id="8f082-120">最小システム要件</span><span class="sxs-lookup"><span data-stu-id="8f082-120">Minimum system requirements</span></span>

<span data-ttu-id="8f082-121">Microsoft Defender ウイルス対策には、Windows 10 と同じハードウェア要件があります。</span><span class="sxs-lookup"><span data-stu-id="8f082-121">Microsoft Defender Antivirus has the same hardware requirements as of Windows 10.</span></span> <span data-ttu-id="8f082-122">詳細については、以下の資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f082-122">For more information, see the following resources:</span></span>

- [<span data-ttu-id="8f082-123">ハードウェアの最小要件</span><span class="sxs-lookup"><span data-stu-id="8f082-123">Minimum hardware requirements</span></span>](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [<span data-ttu-id="8f082-124">ハードウェア コンポーネントのガイドライン</span><span class="sxs-lookup"><span data-stu-id="8f082-124">Hardware component guidelines</span></span>](/windows-hardware/design/component-guidelines/components)

## <a name="configure-next-generation-protection-services"></a><span data-ttu-id="8f082-125">次世代保護サービスの構成</span><span class="sxs-lookup"><span data-stu-id="8f082-125">Configure next-generation protection services</span></span>

<span data-ttu-id="8f082-126">次世代保護サービスを構成する方法の詳細については [、「Configure Microsoft Defender Antivirus features」を参照してください](configure-microsoft-defender-antivirus-features.md)。</span><span class="sxs-lookup"><span data-stu-id="8f082-126">For information on how to configure next-generation protection services, see [Configure Microsoft Defender Antivirus features](configure-microsoft-defender-antivirus-features.md).</span></span>

> [!Note]  
> <span data-ttu-id="8f082-127">構成と管理は、Microsoft Defender ウイルス対策を実行している間、Windows Server 2016 と Windows Server 2019 で大きく同じです。ただし、いくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="8f082-127">Configuration and management is largely the same in Windows Server 2016 and Windows Server 2019, while running Microsoft Defender Antivirus; however, there are some differences.</span></span> <span data-ttu-id="8f082-128">詳細については [、「Microsoft Defender Antivirus on Windows Server 2016 and 2019」を参照してください](microsoft-defender-antivirus-on-windows-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8f082-128">To learn more, see [Microsoft Defender Antivirus on Windows Server 2016 and 2019](microsoft-defender-antivirus-on-windows-server.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8f082-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f082-129">See also</span></span>

- [<span data-ttu-id="8f082-130">Windows Server 2016 および 2019 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="8f082-130">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="8f082-131">Microsoft Defender ウイルス対策の管理と構成</span><span class="sxs-lookup"><span data-stu-id="8f082-131">Microsoft Defender Antivirus management and configuration</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8f082-132">Microsoft Defender ウイルス対策の保護を評価する</span><span class="sxs-lookup"><span data-stu-id="8f082-132">Evaluate Microsoft Defender Antivirus protection</span></span>](evaluate-microsoft-defender-antivirus.md)