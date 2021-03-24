---
title: ハードウェア ベースの分離 (Windows 10)
ms.reviewer: ''
description: Windows 10 でのハードウェア ベースの分離がマルウェア対策に役立つ方法について学習します。
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: b31db39e03ed23698e71c4b38fb0937d2ba59727
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060952"
---
# <a name="hardware-based-isolation-in-windows-10"></a><span data-ttu-id="85740-103">Windows 10 でのハードウェア ベースの分離</span><span class="sxs-lookup"><span data-stu-id="85740-103">Hardware-based isolation in Windows 10</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="85740-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="85740-104">**Applies to:**</span></span>
- [<span data-ttu-id="85740-105">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="85740-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="85740-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="85740-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="85740-107">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="85740-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="85740-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="85740-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="85740-109">ハードウェア ベースの分離は、Windows 10 のシステム整合性を保護するのに役立ち、Microsoft Defender for Endpoint と統合されています。</span><span class="sxs-lookup"><span data-stu-id="85740-109">Hardware-based isolation helps protect system integrity in Windows 10 and is integrated with Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="85740-110">機能</span><span class="sxs-lookup"><span data-stu-id="85740-110">Feature</span></span> | <span data-ttu-id="85740-111">説明</span><span class="sxs-lookup"><span data-stu-id="85740-111">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="85740-112">Windows Defender Application Guard</span><span class="sxs-lookup"><span data-stu-id="85740-112">Windows Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | <span data-ttu-id="85740-113">Application Guard は、生産性を維持しながら、高度な攻撃からデバイスを保護します。</span><span class="sxs-lookup"><span data-stu-id="85740-113">Application Guard protects your device from advanced attacks while keeping you productive.</span></span> <span data-ttu-id="85740-114">独自のハードウェア ベースの分離アプローチを使用して、信頼されていない Web サイトと PDF ドキュメントを、ネイティブの Windows ハイパーバイザーを介してオペレーティング システムから分離された軽量コンテナー内で分離することです。</span><span class="sxs-lookup"><span data-stu-id="85740-114">Using a unique hardware-based isolation approach, the goal is to isolate untrusted websites and PDF documents inside a lightweight container that is separated from the operating system via the native Windows Hypervisor.</span></span> <span data-ttu-id="85740-115">信頼されていないサイトまたは PDF ドキュメントが悪意のあると判明した場合でも、デスクトップ PC を保護し、攻撃者をエンタープライズ データから遠く離して、Application Guard のセキュリティで保護されたコンテナーに含まれるままです。</span><span class="sxs-lookup"><span data-stu-id="85740-115">If an untrusted site or PDF document turns out to be malicious, it still remains contained within Application Guard’s secure container, keeping the desktop PC protected and the attacker away from your enterprise data.</span></span> |
| [<span data-ttu-id="85740-116">Windows Defender System Guard</span><span class="sxs-lookup"><span data-stu-id="85740-116">Windows Defender System Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | <span data-ttu-id="85740-117">System Guard は、システムの開始および実行後にシステムの整合性を保護および維持し、構成証明を使用してシステムの整合性を検証します。</span><span class="sxs-lookup"><span data-stu-id="85740-117">System Guard protects and maintains the integrity of the system as it starts and after it's running, and validates system integrity by using attestation.</span></span>  |

