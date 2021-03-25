---
title: 攻撃表面の縮小を構成する
description: 攻撃表面の縮小を構成するには、Microsoft Intune、Microsoft Endpoint Configuration Manager、PowerShell コマンドレット、およびグループ ポリシーを使用します。
keywords: asr, 攻撃表面の縮小, Windows Defender, microsoft Defender, ウイルス対策, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6129fb889e2bd42f177c4e3be30f676854119f91
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166167"
---
# <a name="configure-attack-surface-reduction"></a><span data-ttu-id="e0240-104">攻撃表面の縮小を構成する</span><span class="sxs-lookup"><span data-stu-id="e0240-104">Configure attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e0240-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e0240-105">**Applies to:**</span></span>
- [<span data-ttu-id="e0240-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e0240-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e0240-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0240-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e0240-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="e0240-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e0240-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="e0240-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="e0240-110">攻撃表面の縮小は、以下を含む多くのツールで構成できます。</span><span class="sxs-lookup"><span data-stu-id="e0240-110">You can configure attack surface reduction with many tools, including:</span></span>

* <span data-ttu-id="e0240-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e0240-111">Microsoft Intune</span></span>
* <span data-ttu-id="e0240-112">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e0240-112">Microsoft Endpoint Configuration Manager</span></span>
* <span data-ttu-id="e0240-113">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="e0240-113">Group Policy</span></span>
* <span data-ttu-id="e0240-114">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="e0240-114">PowerShell cmdlets</span></span>

<span data-ttu-id="e0240-115">記事</span><span class="sxs-lookup"><span data-stu-id="e0240-115">Article</span></span> | <span data-ttu-id="e0240-116">説明</span><span class="sxs-lookup"><span data-stu-id="e0240-116">Description</span></span>
-|-
[<span data-ttu-id="e0240-117">Microsoft Edge のハードウェア ベースの分離を有効にする</span><span class="sxs-lookup"><span data-stu-id="e0240-117">Enable hardware-based isolation for Microsoft Edge</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard) | <span data-ttu-id="e0240-118">ハードウェア要件とソフトウェア要件を含む Application Guard の準備とインストール方法</span><span class="sxs-lookup"><span data-stu-id="e0240-118">How to prepare for and install Application Guard, including hardware and software requirements</span></span>
[<span data-ttu-id="e0240-119">アプリケーション制御を有効にする</span><span class="sxs-lookup"><span data-stu-id="e0240-119">Enable application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)|<span data-ttu-id="e0240-120">ユーザーが実行するアプリケーションを制御し、カーネル モード プロセスを保護する方法</span><span class="sxs-lookup"><span data-stu-id="e0240-120">How to control applications run by users and protect kernel mode processes</span></span>
[<span data-ttu-id="e0240-121">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="e0240-121">Exploit protection</span></span>](./enable-exploit-protection.md)|<span data-ttu-id="e0240-122">オペレーティング システム プロセスと個々のアプリの両方に悪用軽減手法を自動的に適用する方法</span><span class="sxs-lookup"><span data-stu-id="e0240-122">How to automatically apply exploit mitigation techniques on both operating system processes and on individual apps</span></span>
[<span data-ttu-id="e0240-123">ネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="e0240-123">Network protection</span></span>](./enable-network-protection.md)|<span data-ttu-id="e0240-124">ユーザーが危険なドメインにアクセスするためにアプリを使用するのを防ぐ方法</span><span class="sxs-lookup"><span data-stu-id="e0240-124">How to prevent users from using any apps to access dangerous domains</span></span>
[<span data-ttu-id="e0240-125">フォルダー アクセスの制御</span><span class="sxs-lookup"><span data-stu-id="e0240-125">Controlled folder access</span></span>](./enable-controlled-folders.md)|<span data-ttu-id="e0240-126">悪意のあるアプリから貴重なデータを保護する方法</span><span class="sxs-lookup"><span data-stu-id="e0240-126">How to protect valuable data from malicious apps</span></span>
[<span data-ttu-id="e0240-127">攻撃面の縮小</span><span class="sxs-lookup"><span data-stu-id="e0240-127">Attack surface reduction</span></span>](./enable-attack-surface-reduction.md)|<span data-ttu-id="e0240-128">悪用を求めるマルウェアによって通常使用されるアクションとアプリを防止する方法</span><span class="sxs-lookup"><span data-stu-id="e0240-128">How to prevent actions and apps that are typically used by exploit-seeking malware</span></span>
[<span data-ttu-id="e0240-129">ネットワーク ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="e0240-129">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)|<span data-ttu-id="e0240-130">ネットワーク全体のデバイスとデータを保護する方法</span><span class="sxs-lookup"><span data-stu-id="e0240-130">How to protect devices and data across a network</span></span>

