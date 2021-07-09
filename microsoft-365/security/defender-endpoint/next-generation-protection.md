---
title: Microsoft Defender for Endpoint の次世代保護の概要
description: Microsoft Defender for Endpoint の次世代保護の概要をご覧ください。 あらゆる種類の新たな脅威を捕らえるように設計された次世代保護を使用して、ネットワークのセキュリティ境界を強化します。
keywords: Microsoft Defender ウイルス対策、Windows Defender、マルウェア対策、ウイルス、マルウェア、脅威、検出、保護、セキュリティ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 5fdb1d7498fb35ac38638a75bd3656fae8206ea0
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323271"
---
# <a name="next-generation-protection-overview"></a><span data-ttu-id="3f1f8-105">次世代保護の概要</span><span class="sxs-lookup"><span data-stu-id="3f1f8-105">Next-generation protection overview</span></span>

<span data-ttu-id="3f1f8-106">Microsoft Defender for Endpoint には、ネットワークのセキュリティ境界を強化するための次世代保護が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3f1f8-106">Microsoft Defender for Endpoint includes next-generation protection to reinforce the security perimeter of your network.</span></span> <span data-ttu-id="3f1f8-107">次世代保護は、あらゆる種類の新たな脅威を捕らえるように設計されました。</span><span class="sxs-lookup"><span data-stu-id="3f1f8-107">Next-generation protection was designed to catch all types of emerging threats.</span></span> <span data-ttu-id="3f1f8-108">Microsoft Defender ウイルス対策に加えて、次世代保護サービスには以下の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3f1f8-108">In addition to Microsoft Defender Antivirus, your next-generation protection services include the following capabilities:</span></span>

- <span data-ttu-id="3f1f8-109">[挙動ベースおよびヒューリスティックのリアルタイム ウイルス対策保護](configure-protection-features-microsoft-defender-antivirus.md)。これには、ファイルとプロセスの動作監視およびその他のヒューリスティックを使用した常時オンのスキャンが含まれています (「*リアルタイム保護*」とも呼ばれています)。</span><span class="sxs-lookup"><span data-stu-id="3f1f8-109">[Behavior-based, heuristic, and real-time antivirus protection](configure-protection-features-microsoft-defender-antivirus.md), which includes always-on scanning using file and process behavior monitoring and other heuristics (also known as *real-time protection*).</span></span> <span data-ttu-id="3f1f8-110">安全ではないと見なされているもののマルウェアとして検出されない可能性のあるアプリの検出とブロックも含まれています。</span><span class="sxs-lookup"><span data-stu-id="3f1f8-110">It also includes detecting and blocking apps that are deemed unsafe, but might not be detected as malware.</span></span>
- <span data-ttu-id="3f1f8-111">[クラウドによる保護](cloud-protection-microsoft-defender-antivirus.md)。これには、新たに出現する脅威のほぼ瞬時の検出とブロックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3f1f8-111">[Cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md), which includes near-instant detection and blocking of new and emerging threats.</span></span>
- <span data-ttu-id="3f1f8-112">[専用の保護および製品の更新プログラム](manage-updates-baselines-microsoft-defender-antivirus.md)。これには、Microsoft Defender ウイルス対策を最新状態に維持することに関連する更新プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3f1f8-112">[Dedicated protection and product updates](manage-updates-baselines-microsoft-defender-antivirus.md), which includes updates related to keeping Microsoft Defender Antivirus up to date.</span></span>

## <a name="try-a-demo"></a><span data-ttu-id="3f1f8-113">デモを試す</span><span class="sxs-lookup"><span data-stu-id="3f1f8-113">Try a demo!</span></span>

<span data-ttu-id="3f1f8-114">[Microsoft Defender for Endpoint のデモ用 Web サイト](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)にアクセスし、以下の保護機能が動作していることを確認したり、デモのシナリオを使用して検証したりしましょう。</span><span class="sxs-lookup"><span data-stu-id="3f1f8-114">Visit the [Microsoft Defender for Endpoint demo website](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following protection features are working and explore them using demo scenarios:</span></span>

- <span data-ttu-id="3f1f8-115">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="3f1f8-115">Cloud-delivered protection</span></span>
- <span data-ttu-id="3f1f8-116">事前ブロック (BAFS) 保護</span><span class="sxs-lookup"><span data-stu-id="3f1f8-116">Block at first sight (BAFS) protection</span></span>
- <span data-ttu-id="3f1f8-117">望ましくない可能性のあるアプリケーション (PUA) 保護</span><span class="sxs-lookup"><span data-stu-id="3f1f8-117">Potentially unwanted applications (PUA) protection</span></span>

## <a name="configure-next-generation-protection-services"></a><span data-ttu-id="3f1f8-118">次世代の保護サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="3f1f8-118">Configure next-generation protection services</span></span>

<span data-ttu-id="3f1f8-119">次世代の保護サービスを構成する方法の詳細については、「[Microsoft Defender ウイルス対策機能を構成する](configure-microsoft-defender-antivirus-features.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f1f8-119">For information on how to configure next-generation protection services, see [Configure Microsoft Defender Antivirus features](configure-microsoft-defender-antivirus-features.md).</span></span>

> [!Note]  
> <span data-ttu-id="3f1f8-120">構成と管理は、Windows Server と Windows クライアントでほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="3f1f8-120">Configuration and management is largely the same in Windows Server as in Windows clients.</span></span> <span data-ttu-id="3f1f8-121">ただし、いくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="3f1f8-121">However, there are some differences.</span></span> <span data-ttu-id="3f1f8-122">詳細については、「[Windows Server 上の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f1f8-122">To learn more, see [Microsoft Defender Antivirus on Windows Server](microsoft-defender-antivirus-on-windows-server.md).</span></span>
