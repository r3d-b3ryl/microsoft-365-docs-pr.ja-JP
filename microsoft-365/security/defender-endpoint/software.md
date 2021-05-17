---
title: ソフトウェア メソッドとプロパティ
description: 最近使用した上位のアラートを取得します。
keywords: apis, graph api, supported apis, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9bfec2c4e65a390189556c14347eaf17236fb95e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187201"
---
# <a name="software-resource-type"></a><span data-ttu-id="297f8-104">ソフトウェア リソースの種類</span><span class="sxs-lookup"><span data-stu-id="297f8-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="297f8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="297f8-105">**Applies to:**</span></span>
- [<span data-ttu-id="297f8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="297f8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="297f8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="297f8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="297f8-108">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="297f8-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="297f8-109">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="297f8-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="297f8-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="297f8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="297f8-111">メソッド</span><span class="sxs-lookup"><span data-stu-id="297f8-111">Methods</span></span>

<span data-ttu-id="297f8-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="297f8-112">Method</span></span> |<span data-ttu-id="297f8-113">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="297f8-113">Return Type</span></span> |<span data-ttu-id="297f8-114">説明</span><span class="sxs-lookup"><span data-stu-id="297f8-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="297f8-115">ソフトウェアの一覧表示</span><span class="sxs-lookup"><span data-stu-id="297f8-115">List software</span></span>](get-software.md) | <span data-ttu-id="297f8-116">ソフトウェア コレクション</span><span class="sxs-lookup"><span data-stu-id="297f8-116">Software collection</span></span> | <span data-ttu-id="297f8-117">組織のソフトウェア インベントリを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="297f8-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="297f8-118">ID でソフトウェアを取得する</span><span class="sxs-lookup"><span data-stu-id="297f8-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="297f8-119">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="297f8-119">Software</span></span> | <span data-ttu-id="297f8-120">ソフトウェア ID で特定のソフトウェアを取得します。</span><span class="sxs-lookup"><span data-stu-id="297f8-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="297f8-121">ソフトウェア バージョンの配布を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="297f8-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="297f8-122">配布コレクション</span><span class="sxs-lookup"><span data-stu-id="297f8-122">Distribution collection</span></span> | <span data-ttu-id="297f8-123">ソフトウェアのバージョンの配布をソフトウェア ID で一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="297f8-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="297f8-124">ソフトウェアによるマシンの一覧表示</span><span class="sxs-lookup"><span data-stu-id="297f8-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="297f8-125">MachineRef コレクション</span><span class="sxs-lookup"><span data-stu-id="297f8-125">MachineRef collection</span></span> | <span data-ttu-id="297f8-126">ソフトウェア ID に関連付けられているデバイスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="297f8-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="297f8-127">ソフトウェアによる脆弱性の一覧表示</span><span class="sxs-lookup"><span data-stu-id="297f8-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="297f8-128">[脆弱性の](vulnerability.md) コレクション</span><span class="sxs-lookup"><span data-stu-id="297f8-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="297f8-129">ソフトウェア ID に関連付けられている脆弱性の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="297f8-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="297f8-130">不足している KB を取得する</span><span class="sxs-lookup"><span data-stu-id="297f8-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="297f8-131">KB コレクション</span><span class="sxs-lookup"><span data-stu-id="297f8-131">KB collection</span></span> | <span data-ttu-id="297f8-132">ソフトウェア ID に関連付けられている不足している KB の一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="297f8-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="297f8-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="297f8-133">Properties</span></span>

<span data-ttu-id="297f8-134">プロパティ</span><span class="sxs-lookup"><span data-stu-id="297f8-134">Property</span></span> |   <span data-ttu-id="297f8-135">型</span><span class="sxs-lookup"><span data-stu-id="297f8-135">Type</span></span>   |   <span data-ttu-id="297f8-136">説明</span><span class="sxs-lookup"><span data-stu-id="297f8-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="297f8-137">id</span><span class="sxs-lookup"><span data-stu-id="297f8-137">id</span></span> | <span data-ttu-id="297f8-138">String</span><span class="sxs-lookup"><span data-stu-id="297f8-138">String</span></span> | <span data-ttu-id="297f8-139">ソフトウェア ID</span><span class="sxs-lookup"><span data-stu-id="297f8-139">Software ID</span></span>
<span data-ttu-id="297f8-140">名前</span><span class="sxs-lookup"><span data-stu-id="297f8-140">Name</span></span> | <span data-ttu-id="297f8-141">String</span><span class="sxs-lookup"><span data-stu-id="297f8-141">String</span></span> | <span data-ttu-id="297f8-142">ソフトウェア名</span><span class="sxs-lookup"><span data-stu-id="297f8-142">Software name</span></span>
<span data-ttu-id="297f8-143">ベンダー</span><span class="sxs-lookup"><span data-stu-id="297f8-143">Vendor</span></span> | <span data-ttu-id="297f8-144">String</span><span class="sxs-lookup"><span data-stu-id="297f8-144">String</span></span> | <span data-ttu-id="297f8-145">ソフトウェア ベンダー名</span><span class="sxs-lookup"><span data-stu-id="297f8-145">Software vendor name</span></span>
<span data-ttu-id="297f8-146">弱点</span><span class="sxs-lookup"><span data-stu-id="297f8-146">Weaknesses</span></span> | <span data-ttu-id="297f8-147">Long</span><span class="sxs-lookup"><span data-stu-id="297f8-147">Long</span></span> | <span data-ttu-id="297f8-148">検出された脆弱性の数</span><span class="sxs-lookup"><span data-stu-id="297f8-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="297f8-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="297f8-149">publicExploit</span></span> | <span data-ttu-id="297f8-150">Boolean</span><span class="sxs-lookup"><span data-stu-id="297f8-150">Boolean</span></span> | <span data-ttu-id="297f8-151">一部の脆弱性に対してパブリックエクスプロイトが存在する</span><span class="sxs-lookup"><span data-stu-id="297f8-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="297f8-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="297f8-152">activeAlert</span></span> | <span data-ttu-id="297f8-153">Boolean</span><span class="sxs-lookup"><span data-stu-id="297f8-153">Boolean</span></span> | <span data-ttu-id="297f8-154">アクティブアラートは、このソフトウェアに関連付けられている</span><span class="sxs-lookup"><span data-stu-id="297f8-154">Active alert is associated with this software</span></span>
<span data-ttu-id="297f8-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="297f8-155">exposedMachines</span></span> | <span data-ttu-id="297f8-156">Long</span><span class="sxs-lookup"><span data-stu-id="297f8-156">Long</span></span> | <span data-ttu-id="297f8-157">公開されているデバイスの数</span><span class="sxs-lookup"><span data-stu-id="297f8-157">Number of exposed devices</span></span>
<span data-ttu-id="297f8-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="297f8-158">impactScore</span></span> | <span data-ttu-id="297f8-159">Double</span><span class="sxs-lookup"><span data-stu-id="297f8-159">Double</span></span> | <span data-ttu-id="297f8-160">このソフトウェアの露出スコアの影響</span><span class="sxs-lookup"><span data-stu-id="297f8-160">Exposure score impact of this software</span></span>
