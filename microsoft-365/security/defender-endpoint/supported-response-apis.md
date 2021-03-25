---
title: サポートされている Microsoft Defender Advanced Threat Protection 応答 API
description: 特定の応答関連の Microsoft Defender Advanced Threat Protection API 呼び出しについて説明します。
keywords: 応答 API、グラフ API、サポートされている API、アクター、アラート、デバイス、ユーザー、ドメイン、IP、ファイル
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: a290c431f6d81b23896ddf77e7c7a47de378de22
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185553"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a><span data-ttu-id="a1c69-104">サポートされている Microsoft Defender for Endpoint クエリ API</span><span class="sxs-lookup"><span data-stu-id="a1c69-104">Supported Microsoft Defender for Endpoint query APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a1c69-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a1c69-105">**Applies to:**</span></span>
- [<span data-ttu-id="a1c69-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a1c69-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> <span data-ttu-id="a1c69-107">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="a1c69-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a1c69-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="a1c69-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

<span data-ttu-id="a1c69-109">実行できるサポートされる応答関連 API 呼び出しと、必要な要求ヘッダー、呼び出しからの予期される応答などの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-109">Learn about the supported response-related API calls you can run and details such as the required request headers, and expected response from the calls.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a1c69-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a1c69-110">In this section</span></span>
<span data-ttu-id="a1c69-111">トピック</span><span class="sxs-lookup"><span data-stu-id="a1c69-111">Topic</span></span> | <span data-ttu-id="a1c69-112">説明</span><span class="sxs-lookup"><span data-stu-id="a1c69-112">Description</span></span>
:---|:---
<span data-ttu-id="a1c69-113">調査パッケージの収集</span><span class="sxs-lookup"><span data-stu-id="a1c69-113">Collect investigation package</span></span> | <span data-ttu-id="a1c69-114">この API を実行して、デバイスから調査パッケージを収集します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-114">Run this API to collect an investigation package from a device.</span></span>
<span data-ttu-id="a1c69-115">デバイスの分離</span><span class="sxs-lookup"><span data-stu-id="a1c69-115">Isolate device</span></span> | <span data-ttu-id="a1c69-116">ネットワークからデバイスを分離するには、この API を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-116">Run this API to isolate a device from the network.</span></span>
<span data-ttu-id="a1c69-117">Unisolate デバイス</span><span class="sxs-lookup"><span data-stu-id="a1c69-117">Unisolate device</span></span> | <span data-ttu-id="a1c69-118">デバイスを分離から削除します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-118">Remove a device from isolation.</span></span> 
<span data-ttu-id="a1c69-119">コードの実行を制限する</span><span class="sxs-lookup"><span data-stu-id="a1c69-119">Restrict code execution</span></span> | <span data-ttu-id="a1c69-120">悪意のあるプロセスを停止して攻撃を含めるには、この API を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-120">Run this API to contain an attack by stopping malicious processes.</span></span> <span data-ttu-id="a1c69-121">デバイスをロックダウンして、悪意のある可能性のあるプログラムの後続の試行が実行されるのを防ぐことも可能です。</span><span class="sxs-lookup"><span data-stu-id="a1c69-121">You can also lock down a device and prevent subsequent attempts of potentially malicious programs from running.</span></span>
<span data-ttu-id="a1c69-122">無制限のコード実行</span><span class="sxs-lookup"><span data-stu-id="a1c69-122">Unrestrict code execution</span></span> | <span data-ttu-id="a1c69-123">侵害されたデバイスが修復されたと確認した後、アプリケーション ポリシーの制限を取り消す場合は、これを実行します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-123">Run this to reverse the restriction of applications policy after you have verified that the compromised device has been remediated.</span></span>
<span data-ttu-id="a1c69-124">ウイルス対策スキャンの実行</span><span class="sxs-lookup"><span data-stu-id="a1c69-124">Run antivirus scan</span></span> | <span data-ttu-id="a1c69-125">ウイルス対策スキャンをリモートで開始して、侵害されたデバイスに存在する可能性のあるマルウェアを特定して修復します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-125">Remotely initiate an antivirus scan to help identify and remediate malware that might be present on a compromised device.</span></span>
<span data-ttu-id="a1c69-126">ファイルの停止と検疫</span><span class="sxs-lookup"><span data-stu-id="a1c69-126">Stop and quarantine file</span></span> |  <span data-ttu-id="a1c69-127">この呼び出しを実行して、プロセスの実行を停止し、ファイルを検疫し、レジストリ キーなどの永続性を削除します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-127">Run this call to stop running processes, quarantine  files, and delete persistency such as registry keys.</span></span>
<span data-ttu-id="a1c69-128">要求サンプル</span><span class="sxs-lookup"><span data-stu-id="a1c69-128">Request sample</span></span> | <span data-ttu-id="a1c69-129">この呼び出しを実行して、特定のデバイスからファイルのサンプルを要求します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-129">Run this call to request a sample of a file from a specific device.</span></span> <span data-ttu-id="a1c69-130">ファイルはデバイスから収集され、セキュリティで保護された記憶域にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="a1c69-130">The file will be collected from the device and uploaded to a secure storage.</span></span>
<span data-ttu-id="a1c69-131">ブロック ファイル</span><span class="sxs-lookup"><span data-stu-id="a1c69-131">Block file</span></span> | <span data-ttu-id="a1c69-132">この API を実行して、悪意のある可能性のあるファイルやマルウェアの疑いを禁止して、組織内の攻撃をさらに伝播防止します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-132">Run this API to prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 
<span data-ttu-id="a1c69-133">ファイルのブロックを解除する</span><span class="sxs-lookup"><span data-stu-id="a1c69-133">Unblock file</span></span> | <span data-ttu-id="a1c69-134">Microsoft Defender ウイルス対策を使用して組織内でファイルの実行を許可します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-134">Allow a file run in the organization using Microsoft Defender Antivirus.</span></span>
<span data-ttu-id="a1c69-135">パッケージ SAS URI の取得</span><span class="sxs-lookup"><span data-stu-id="a1c69-135">Get package SAS URI</span></span> | <span data-ttu-id="a1c69-136">この API を実行して、調査パッケージのダウンロードを許可する URI を取得します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-136">Run this API to get a URI that allows downloading an investigation package.</span></span>
<span data-ttu-id="a1c69-137">MachineAction オブジェクトの取得</span><span class="sxs-lookup"><span data-stu-id="a1c69-137">Get MachineAction object</span></span> | <span data-ttu-id="a1c69-138">この API を実行して MachineAction オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-138">Run this API to get MachineAction object.</span></span>
<span data-ttu-id="a1c69-139">MachineActions コレクションの取得</span><span class="sxs-lookup"><span data-stu-id="a1c69-139">Get MachineActions collection</span></span> | <span data-ttu-id="a1c69-140">MachineAction コレクションを取得するには、これを実行します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-140">Run this to get MachineAction collection.</span></span>
<span data-ttu-id="a1c69-141">Get FileActions コレクション</span><span class="sxs-lookup"><span data-stu-id="a1c69-141">Get FileActions collection</span></span> | <span data-ttu-id="a1c69-142">FileActions コレクションを取得するには、この API を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-142">Run this API to get FileActions collection.</span></span>
<span data-ttu-id="a1c69-143">Get FileMachineAction オブジェクト</span><span class="sxs-lookup"><span data-stu-id="a1c69-143">Get FileMachineAction object</span></span> | <span data-ttu-id="a1c69-144">FileMachineAction オブジェクトを取得するには、この API を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-144">Run this API to get FileMachineAction object.</span></span>
<span data-ttu-id="a1c69-145">Get FileMachineActions コレクション</span><span class="sxs-lookup"><span data-stu-id="a1c69-145">Get FileMachineActions collection</span></span> | <span data-ttu-id="a1c69-146">FileMachineAction コレクションを取得するには、この API を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1c69-146">Run this API to get FileMachineAction collection.</span></span>