---
title: 攻撃面の減少の概要
ms.reviewer: ''
description: Microsoft Defender for Endpoint の攻撃表面の縮小機能について説明します。
keywords: asr, 攻撃表面の縮小, microsoft Defender atp, エンドポイント用の microsoft Defender, microsoft Defender, ウイルス対策, av, Windows Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: asr
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 60efae91e4b65c5977bd2aebf111d9174d7c1042
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893555"
---
# <a name="overview-of-attack-surface-reduction"></a><span data-ttu-id="3d665-104">攻撃面の減少の概要</span><span class="sxs-lookup"><span data-stu-id="3d665-104">Overview of attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3d665-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3d665-105">**Applies to:**</span></span>
- [<span data-ttu-id="3d665-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3d665-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3d665-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3d665-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3d665-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="3d665-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3d665-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="3d665-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="3d665-110">組織がサイバー脅威や攻撃に対して脆弱な場所を最小限に抑えることによって、攻撃の表面を減らすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3d665-110">Help reduce your attack surfaces, by minimizing the places where your organization is vulnerable to cyberthreats and attacks.</span></span> <span data-ttu-id="3d665-111">組織のデバイスとアプリケーションの保護を構成するには、次のリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d665-111">Use the following resources to configure protection for the devices and applications in your organization.</span></span>


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]


<span data-ttu-id="3d665-112">記事</span><span class="sxs-lookup"><span data-stu-id="3d665-112">Article</span></span> | <span data-ttu-id="3d665-113">説明</span><span class="sxs-lookup"><span data-stu-id="3d665-113">Description</span></span>
-|-
[<span data-ttu-id="3d665-114">攻撃面の減少</span><span class="sxs-lookup"><span data-stu-id="3d665-114">Attack surface reduction</span></span>](./attack-surface-reduction.md) | <span data-ttu-id="3d665-115">マルウェアの阻止に役立つインテリジェントなルールを使用して、アプリケーションの脆弱性 (攻撃面) を減らします。</span><span class="sxs-lookup"><span data-stu-id="3d665-115">Reduce vulnerabilities (attack surfaces) in your applications with intelligent rules that help stop malware.</span></span> <span data-ttu-id="3d665-116">(Microsoft Defender ウイルス対策が必要です)。</span><span class="sxs-lookup"><span data-stu-id="3d665-116">(Requires Microsoft Defender Antivirus).</span></span>
[<span data-ttu-id="3d665-117">ハードウェア ベースの分離</span><span class="sxs-lookup"><span data-stu-id="3d665-117">Hardware-based isolation</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | <span data-ttu-id="3d665-118">システムの開始と実行中のシステムの整合性を保護し、維持します。</span><span class="sxs-lookup"><span data-stu-id="3d665-118">Protect and maintain the integrity of a system as it starts and while it's running.</span></span> <span data-ttu-id="3d665-119">ローカル構成証明とリモート構成証明を使用してシステムの整合性を検証します。</span><span class="sxs-lookup"><span data-stu-id="3d665-119">Validate system integrity through local and remote attestation.</span></span> <span data-ttu-id="3d665-120">また、Microsoft Edge のコンテナー分離を使用して、悪意のある Web サイトから保護します。</span><span class="sxs-lookup"><span data-stu-id="3d665-120">And, use container isolation for Microsoft Edge to help guard against malicious websites.</span></span>
[<span data-ttu-id="3d665-121">アプリケーション制御</span><span class="sxs-lookup"><span data-stu-id="3d665-121">Application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | <span data-ttu-id="3d665-122">アプリケーション制御を使用して、アプリケーションを実行するために信頼を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d665-122">Use application control so that your applications must earn trust in order to run.</span></span>
[<span data-ttu-id="3d665-123">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="3d665-123">Exploit protection</span></span>](./exploit-protection.md) | <span data-ttu-id="3d665-124">組織が使用するオペレーティング システムとアプリが悪用されるのを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3d665-124">Help protect operating systems and apps your organization uses from being exploited.</span></span> <span data-ttu-id="3d665-125">エクスプロイト保護は、サードパーティのウイルス対策ソリューションでも機能します。</span><span class="sxs-lookup"><span data-stu-id="3d665-125">Exploit protection also works with third-party antivirus solutions.</span></span>
[<span data-ttu-id="3d665-126">ネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="3d665-126">Network protection</span></span>](./network-protection.md) | <span data-ttu-id="3d665-127">組織のデバイス上のネットワーク トラフィックと接続に対する保護を拡張します。</span><span class="sxs-lookup"><span data-stu-id="3d665-127">Extend protection to your network traffic and connectivity on your organization's devices.</span></span> <span data-ttu-id="3d665-128">(Microsoft Defender ウイルス対策が必要)</span><span class="sxs-lookup"><span data-stu-id="3d665-128">(Requires Microsoft Defender Antivirus)</span></span>
[<span data-ttu-id="3d665-129">Web 保護</span><span class="sxs-lookup"><span data-stu-id="3d665-129">Web protection</span></span>](./web-protection-overview.md) | <span data-ttu-id="3d665-130">Web の脅威からデバイスを保護し、望ましくないコンテンツを規制するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3d665-130">Secure your devices against web threats and help you regulate unwanted content.</span></span>
[<span data-ttu-id="3d665-131">制御されたフォルダー アクセス</span><span class="sxs-lookup"><span data-stu-id="3d665-131">Controlled folder access</span></span>](./controlled-folders.md) | <span data-ttu-id="3d665-132">悪意のあるアプリや疑わしいアプリ (ファイル暗号化ランサムウェア マルウェアを含む) がキー システム フォルダー内のファイルに変更を加えるのを防ぐ (Microsoft Defender ウイルス対策が必要)</span><span class="sxs-lookup"><span data-stu-id="3d665-132">Help prevent malicious or suspicious apps (including file-encrypting ransomware malware) from making changes to files in your key system folders (Requires Microsoft Defender Antivirus)</span></span>
[<span data-ttu-id="3d665-133">ネットワーク ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="3d665-133">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) | <span data-ttu-id="3d665-134">2 方向ネットワーク トラフィック フィルターを使用して、組織のデバイスとの間で不正なトラフィックが流れるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="3d665-134">Prevent unauthorized traffic from flowing to or from your organization's devices with two-way network traffic filtering.</span></span>
[<span data-ttu-id="3d665-135">攻撃面の減少の FAQ</span><span class="sxs-lookup"><span data-stu-id="3d665-135">Attack surface reduction FAQ</span></span>](./attack-surface-reduction-faq.md) | <span data-ttu-id="3d665-136">攻撃表面の縮小ルール、ライセンスなどについてよく寄せられる質問。</span><span class="sxs-lookup"><span data-stu-id="3d665-136">Frequently asked questions about Attack surface reduction rules, licensing, and more.</span></span>
