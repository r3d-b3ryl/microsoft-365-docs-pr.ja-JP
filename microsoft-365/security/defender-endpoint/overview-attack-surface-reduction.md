---
title: 攻撃面の減少の概要
ms.reviewer: ''
description: Microsoft Defender for Endpoint の攻撃表面の縮小機能について説明します。
keywords: asr, 攻撃表面の縮小, Microsoft Defender for Endpoint, microsoft Defender, ウイルス対策, av, Windows Defender
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
ms.date: 06/02/2021
ms.openlocfilehash: b6fb9bb327816b7e166a443a0d07932d30421a19
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771695"
---
# <a name="overview-of-attack-surface-reduction-capabilities"></a><span data-ttu-id="3955b-104">攻撃表面の縮小機能の概要</span><span class="sxs-lookup"><span data-stu-id="3955b-104">Overview of attack surface reduction capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3955b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3955b-105">**Applies to:**</span></span>
- [<span data-ttu-id="3955b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3955b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3955b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3955b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="3955b-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="3955b-108">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="3955b-109">[無料試用版にサインアップします](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="3955b-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink).</span></span>

<span data-ttu-id="3955b-110">攻撃の表面は、組織がサイバー脅威や攻撃に対して脆弱なすべての場所です。</span><span class="sxs-lookup"><span data-stu-id="3955b-110">Your attack surfaces are all the places where your organization is vulnerable to cyberthreats and attacks.</span></span> <span data-ttu-id="3955b-111">Defender for Endpoint には、攻撃の表面を減らすのに役立ついくつかの機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3955b-111">Defender for Endpoint includes several capabilities to help reduce your attack surfaces.</span></span> <span data-ttu-id="3955b-112">攻撃表面の縮小の詳細については、次のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3955b-112">Watch the following video to learn more about attack surface reduction.</span></span><p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]

## <a name="resources-to-learn-more-about-attack-surface-reduction"></a><span data-ttu-id="3955b-113">攻撃表面の縮小について詳しくは、リソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3955b-113">Resources to learn more about attack surface reduction</span></span>

<span data-ttu-id="3955b-114">ビデオで説明したように、Defender for Endpoint には、いくつかの攻撃表面の縮小機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3955b-114">As mentioned in the video, Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="3955b-115">詳細については、次のリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="3955b-115">Use the following resources to learn more:</span></span>

| <span data-ttu-id="3955b-116">記事</span><span class="sxs-lookup"><span data-stu-id="3955b-116">Article</span></span> | <span data-ttu-id="3955b-117">説明</span><span class="sxs-lookup"><span data-stu-id="3955b-117">Description</span></span> |
|:---|:---|
| [<span data-ttu-id="3955b-118">ハードウェア ベースの分離</span><span class="sxs-lookup"><span data-stu-id="3955b-118">Hardware-based isolation</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | <span data-ttu-id="3955b-119">システムの開始と実行中のシステムの整合性を保護し、維持します。</span><span class="sxs-lookup"><span data-stu-id="3955b-119">Protect and maintain the integrity of a system as it starts and while it's running.</span></span> <span data-ttu-id="3955b-120">ローカル構成証明とリモート構成証明を使用してシステムの整合性を検証します。</span><span class="sxs-lookup"><span data-stu-id="3955b-120">Validate system integrity through local and remote attestation.</span></span> <span data-ttu-id="3955b-121">また、悪意のある web サイトから保護するためにMicrosoft Edgeコンテナーの分離を使用します。</span><span class="sxs-lookup"><span data-stu-id="3955b-121">And, use container isolation for Microsoft Edge to help guard against malicious websites.</span></span> |
| [<span data-ttu-id="3955b-122">アプリケーション制御</span><span class="sxs-lookup"><span data-stu-id="3955b-122">Application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | <span data-ttu-id="3955b-123">アプリケーション制御を使用して、アプリケーションを実行するために信頼を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="3955b-123">Use application control so that your applications must earn trust in order to run.</span></span> |
| [<span data-ttu-id="3955b-124">制御されたフォルダー アクセス</span><span class="sxs-lookup"><span data-stu-id="3955b-124">Controlled folder access</span></span>](controlled-folders.md) | <span data-ttu-id="3955b-125">悪意のあるアプリや疑わしいアプリ (ファイル暗号化ランサムウェア マルウェアを含む) がキー システム フォルダー内のファイルに変更を加えるのを防ぐのに役立ちます (Microsoft Defender ウイルス対策)</span><span class="sxs-lookup"><span data-stu-id="3955b-125">Help prevent malicious or suspicious apps (including file-encrypting ransomware malware) from making changes to files in your key system folders (Requires Microsoft Defender Antivirus)</span></span> |
| [<span data-ttu-id="3955b-126">ネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="3955b-126">Network protection</span></span>](network-protection.md) | <span data-ttu-id="3955b-127">組織のデバイス上のネットワーク トラフィックと接続に対する保護を拡張します。</span><span class="sxs-lookup"><span data-stu-id="3955b-127">Extend protection to your network traffic and connectivity on your organization's devices.</span></span> <span data-ttu-id="3955b-128">(必要なMicrosoft Defender ウイルス対策)</span><span class="sxs-lookup"><span data-stu-id="3955b-128">(Requires Microsoft Defender Antivirus)</span></span> |
| [<span data-ttu-id="3955b-129">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="3955b-129">Exploit protection</span></span>](exploit-protection.md) | <span data-ttu-id="3955b-130">組織が使用するオペレーティング システムとアプリが悪用されるのを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3955b-130">Help protect operating systems and apps your organization uses from being exploited.</span></span> <span data-ttu-id="3955b-131">エクスプロイト保護は、サードパーティのウイルス対策ソリューションでも機能します。</span><span class="sxs-lookup"><span data-stu-id="3955b-131">Exploit protection also works with third-party antivirus solutions.</span></span> |
| [<span data-ttu-id="3955b-132">攻撃面の減少ルール</span><span class="sxs-lookup"><span data-stu-id="3955b-132">Attack surface reduction rules</span></span>](attack-surface-reduction.md) | <span data-ttu-id="3955b-133">マルウェアの阻止に役立つインテリジェントなルールを使用して、アプリケーションの脆弱性 (攻撃面) を減らします。</span><span class="sxs-lookup"><span data-stu-id="3955b-133">Reduce vulnerabilities (attack surfaces) in your applications with intelligent rules that help stop malware.</span></span> <span data-ttu-id="3955b-134">(必要なMicrosoft Defender ウイルス対策)。</span><span class="sxs-lookup"><span data-stu-id="3955b-134">(Requires Microsoft Defender Antivirus).</span></span> |
| [<span data-ttu-id="3955b-135">デバイス コントロール</span><span class="sxs-lookup"><span data-stu-id="3955b-135">Device control</span></span>](device-control-report.md) | <span data-ttu-id="3955b-136">組織内のリムーバブル ストレージや USB ドライブなどのデバイスで使用されるメディアを監視および制御することにより、データ損失から保護します。</span><span class="sxs-lookup"><span data-stu-id="3955b-136">Protects against data loss by monitoring and controlling media used on devices, such as removable storage and USB drives, in your organization.</span></span> |