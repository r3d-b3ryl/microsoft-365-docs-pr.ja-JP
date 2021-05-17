---
title: ファイル リソースの種類
description: ファイルに関連する最近の Microsoft Defender for Endpoint アラートを取得します。
keywords: apis, graph api, supported apis, get, alerts, recent
search.product: eADQiWindows 10XVcnh
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9079a47dcc078b582586370b322502b74ce3838c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199983"
---
# <a name="file-resource-type"></a><span data-ttu-id="dbf6e-104">ファイル リソースの種類</span><span class="sxs-lookup"><span data-stu-id="dbf6e-104">File resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="dbf6e-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="dbf6e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="dbf6e-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="dbf6e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dbf6e-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="dbf6e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="dbf6e-108">Defender for Endpoint のファイル エンティティを表します。</span><span class="sxs-lookup"><span data-stu-id="dbf6e-108">Represent a file entity in Defender for Endpoint.</span></span>

## <a name="methods"></a><span data-ttu-id="dbf6e-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="dbf6e-109">Methods</span></span>
<span data-ttu-id="dbf6e-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="dbf6e-110">Method</span></span>|<span data-ttu-id="dbf6e-111">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="dbf6e-111">Return Type</span></span> |<span data-ttu-id="dbf6e-112">説明</span><span class="sxs-lookup"><span data-stu-id="dbf6e-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="dbf6e-113">ファイルの取得</span><span class="sxs-lookup"><span data-stu-id="dbf6e-113">Get file</span></span>](get-file-information.md) | [<span data-ttu-id="dbf6e-114">file</span><span class="sxs-lookup"><span data-stu-id="dbf6e-114">file</span></span>](files.md) | <span data-ttu-id="dbf6e-115">1 つのファイルを取得する</span><span class="sxs-lookup"><span data-stu-id="dbf6e-115">Get a single file</span></span> 
[<span data-ttu-id="dbf6e-116">ファイル関連のアラートを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="dbf6e-116">List file related alerts</span></span>](get-file-related-alerts.md) | <span data-ttu-id="dbf6e-117">[alert](alerts.md) コレクション</span><span class="sxs-lookup"><span data-stu-id="dbf6e-117">[alert](alerts.md) collection</span></span> | <span data-ttu-id="dbf6e-118">ファイルに [関連](alerts.md) 付けられているアラート エンティティを取得します。</span><span class="sxs-lookup"><span data-stu-id="dbf6e-118">Get the [alert](alerts.md) entities that are associated with the file.</span></span>
[<span data-ttu-id="dbf6e-119">ファイル関連のコンピューターを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="dbf6e-119">List file related machines</span></span>](get-file-related-machines.md) | <span data-ttu-id="dbf6e-120">[machine](machine.md) コレクション</span><span class="sxs-lookup"><span data-stu-id="dbf6e-120">[machine](machine.md) collection</span></span> | <span data-ttu-id="dbf6e-121">アラートに [関連付](machine.md) けられたコンピューター エンティティを取得します。</span><span class="sxs-lookup"><span data-stu-id="dbf6e-121">Get the [machine](machine.md) entities associated with the alert.</span></span>
[<span data-ttu-id="dbf6e-122">ファイルの統計情報</span><span class="sxs-lookup"><span data-stu-id="dbf6e-122">file statistics</span></span>](get-file-statistics.md) | <span data-ttu-id="dbf6e-123">統計情報の概要</span><span class="sxs-lookup"><span data-stu-id="dbf6e-123">Statistics summary</span></span> | <span data-ttu-id="dbf6e-124">指定したファイルの有病率を取得します。</span><span class="sxs-lookup"><span data-stu-id="dbf6e-124">Retrieves the prevalence for the given file.</span></span>


## <a name="properties"></a><span data-ttu-id="dbf6e-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="dbf6e-125">Properties</span></span>
|<span data-ttu-id="dbf6e-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="dbf6e-126">Property</span></span> | <span data-ttu-id="dbf6e-127">型</span><span class="sxs-lookup"><span data-stu-id="dbf6e-127">Type</span></span>    |   <span data-ttu-id="dbf6e-128">説明</span><span class="sxs-lookup"><span data-stu-id="dbf6e-128">Description</span></span> |
|:---|:---|:---|
|<span data-ttu-id="dbf6e-129">sha1</span><span class="sxs-lookup"><span data-stu-id="dbf6e-129">sha1</span></span> | <span data-ttu-id="dbf6e-130">String</span><span class="sxs-lookup"><span data-stu-id="dbf6e-130">String</span></span> | <span data-ttu-id="dbf6e-131">ファイル コンテンツの Sha1 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="dbf6e-131">Sha1 hash of the file content</span></span> |
|<span data-ttu-id="dbf6e-132">sha256</span><span class="sxs-lookup"><span data-stu-id="dbf6e-132">sha256</span></span> | <span data-ttu-id="dbf6e-133">String</span><span class="sxs-lookup"><span data-stu-id="dbf6e-133">String</span></span> | <span data-ttu-id="dbf6e-134">ファイル コンテンツの Sha256 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="dbf6e-134">Sha256 hash of the file content</span></span> |
|<span data-ttu-id="dbf6e-135">globalPrevalence</span><span class="sxs-lookup"><span data-stu-id="dbf6e-135">globalPrevalence</span></span> | <span data-ttu-id="dbf6e-136">Null 許容長</span><span class="sxs-lookup"><span data-stu-id="dbf6e-136">Nullable long</span></span> | <span data-ttu-id="dbf6e-137">組織全体でのファイルの普及率</span><span class="sxs-lookup"><span data-stu-id="dbf6e-137">File prevalence across organization</span></span> |
|<span data-ttu-id="dbf6e-138">globalFirstObserved</span><span class="sxs-lookup"><span data-stu-id="dbf6e-138">globalFirstObserved</span></span> | <span data-ttu-id="dbf6e-139">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="dbf6e-139">DateTimeOffset</span></span> | <span data-ttu-id="dbf6e-140">ファイルが初めて観察された場合</span><span class="sxs-lookup"><span data-stu-id="dbf6e-140">First time the file was observed</span></span> |
|<span data-ttu-id="dbf6e-141">globalLastObserved</span><span class="sxs-lookup"><span data-stu-id="dbf6e-141">globalLastObserved</span></span> | <span data-ttu-id="dbf6e-142">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="dbf6e-142">DateTimeOffset</span></span> | <span data-ttu-id="dbf6e-143">ファイルが最後に観察された時刻</span><span class="sxs-lookup"><span data-stu-id="dbf6e-143">Last time the file was observed</span></span> |
|<span data-ttu-id="dbf6e-144">size</span><span class="sxs-lookup"><span data-stu-id="dbf6e-144">size</span></span> | <span data-ttu-id="dbf6e-145">Null 許容長</span><span class="sxs-lookup"><span data-stu-id="dbf6e-145">Nullable long</span></span> | <span data-ttu-id="dbf6e-146">ファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="dbf6e-146">Size of the file</span></span> |
|<span data-ttu-id="dbf6e-147">fileType</span><span class="sxs-lookup"><span data-stu-id="dbf6e-147">fileType</span></span> | <span data-ttu-id="dbf6e-148">String</span><span class="sxs-lookup"><span data-stu-id="dbf6e-148">String</span></span> | <span data-ttu-id="dbf6e-149">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="dbf6e-149">Type of the file</span></span> |
|<span data-ttu-id="dbf6e-150">isPeFile</span><span class="sxs-lookup"><span data-stu-id="dbf6e-150">isPeFile</span></span> | <span data-ttu-id="dbf6e-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="dbf6e-151">Boolean</span></span> | <span data-ttu-id="dbf6e-152">ファイルが移植可能な実行可能ファイルの場合は true ("DLL"、"EXE"など)</span><span class="sxs-lookup"><span data-stu-id="dbf6e-152">true if the file is portable executable (e.g. "DLL", "EXE", etc.)</span></span> |
|<span data-ttu-id="dbf6e-153">filePublisher</span><span class="sxs-lookup"><span data-stu-id="dbf6e-153">filePublisher</span></span> | <span data-ttu-id="dbf6e-154">String</span><span class="sxs-lookup"><span data-stu-id="dbf6e-154">String</span></span> | <span data-ttu-id="dbf6e-155">ファイル発行元</span><span class="sxs-lookup"><span data-stu-id="dbf6e-155">File publisher</span></span> |
|<span data-ttu-id="dbf6e-156">fileProductName</span><span class="sxs-lookup"><span data-stu-id="dbf6e-156">fileProductName</span></span> | <span data-ttu-id="dbf6e-157">String</span><span class="sxs-lookup"><span data-stu-id="dbf6e-157">String</span></span> | <span data-ttu-id="dbf6e-158">製品名</span><span class="sxs-lookup"><span data-stu-id="dbf6e-158">Product name</span></span> |
|<span data-ttu-id="dbf6e-159">署名者</span><span class="sxs-lookup"><span data-stu-id="dbf6e-159">signer</span></span> | <span data-ttu-id="dbf6e-160">String</span><span class="sxs-lookup"><span data-stu-id="dbf6e-160">String</span></span> | <span data-ttu-id="dbf6e-161">ファイル署名者</span><span class="sxs-lookup"><span data-stu-id="dbf6e-161">File signer</span></span> |
|<span data-ttu-id="dbf6e-162">issuer</span><span class="sxs-lookup"><span data-stu-id="dbf6e-162">issuer</span></span> | <span data-ttu-id="dbf6e-163">String</span><span class="sxs-lookup"><span data-stu-id="dbf6e-163">String</span></span> | <span data-ttu-id="dbf6e-164">ファイル発行者</span><span class="sxs-lookup"><span data-stu-id="dbf6e-164">File issuer</span></span> |
|<span data-ttu-id="dbf6e-165">signerHash</span><span class="sxs-lookup"><span data-stu-id="dbf6e-165">signerHash</span></span> | <span data-ttu-id="dbf6e-166">String</span><span class="sxs-lookup"><span data-stu-id="dbf6e-166">String</span></span> | <span data-ttu-id="dbf6e-167">署名証明書のハッシュ</span><span class="sxs-lookup"><span data-stu-id="dbf6e-167">Hash of the signing certificate</span></span> |
|<span data-ttu-id="dbf6e-168">isValidCertificate</span><span class="sxs-lookup"><span data-stu-id="dbf6e-168">isValidCertificate</span></span> | <span data-ttu-id="dbf6e-169">Boolean</span><span class="sxs-lookup"><span data-stu-id="dbf6e-169">Boolean</span></span> | <span data-ttu-id="dbf6e-170">Microsoft Defender for Endpoint エージェントによって証明書の署名が正常に確認されました</span><span class="sxs-lookup"><span data-stu-id="dbf6e-170">Was signing certificate successfully verified by Microsoft Defender for Endpoint agent</span></span> |
|<span data-ttu-id="dbf6e-171">determinationType</span><span class="sxs-lookup"><span data-stu-id="dbf6e-171">determinationType</span></span> | <span data-ttu-id="dbf6e-172">String</span><span class="sxs-lookup"><span data-stu-id="dbf6e-172">String</span></span> | <span data-ttu-id="dbf6e-173">ファイルの決定の種類</span><span class="sxs-lookup"><span data-stu-id="dbf6e-173">The determination type of the file</span></span> |
|<span data-ttu-id="dbf6e-174">determinationValue</span><span class="sxs-lookup"><span data-stu-id="dbf6e-174">determinationValue</span></span> | <span data-ttu-id="dbf6e-175">String</span><span class="sxs-lookup"><span data-stu-id="dbf6e-175">String</span></span> | <span data-ttu-id="dbf6e-176">判定値</span><span class="sxs-lookup"><span data-stu-id="dbf6e-176">Determination value</span></span> |


## <a name="json-representation"></a><span data-ttu-id="dbf6e-177">Json 表記</span><span class="sxs-lookup"><span data-stu-id="dbf6e-177">Json representation</span></span>

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
