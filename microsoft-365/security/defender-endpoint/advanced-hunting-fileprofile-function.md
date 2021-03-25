---
title: エンドポイント用 Microsoft Defender の高度な検索での FileProfile() 関数
description: FileProfile() を使用して高度な検索クエリ結果のファイルに関する情報を強化する方法について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、mdatp、Microsoft Defender ATP、エンドポイント用 Microsoft Defender、Windows Defender、Windows Defender ATP、Windows Defender Advanced Threat Protection、検索、クエリ、テレメトリ、スキーマ参照、kusto、FileProfile、ファイル プロファイル、関数、エンリッチメント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 668b3fe503268c46e4a1313f0c4cfb8a6a3dd602
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067971"
---
# <a name="fileprofile"></a><span data-ttu-id="212a3-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="212a3-104">FileProfile()</span></span>

<span data-ttu-id="212a3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="212a3-105">**Applies to:**</span></span>
- [<span data-ttu-id="212a3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="212a3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

<span data-ttu-id="212a3-107">この `FileProfile()` 関数は、高度な検索の[](advanced-hunting-overview.md)エンリッチメント関数で、クエリで見つかったファイルに次のデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="212a3-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

<span data-ttu-id="212a3-108">Column</span><span class="sxs-lookup"><span data-stu-id="212a3-108">Column</span></span> | <span data-ttu-id="212a3-109">データ型</span><span class="sxs-lookup"><span data-stu-id="212a3-109">Data type</span></span> | <span data-ttu-id="212a3-110">説明</span><span class="sxs-lookup"><span data-stu-id="212a3-110">Description</span></span>
-|-|-
<span data-ttu-id="212a3-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="212a3-111">SHA1</span></span> | <span data-ttu-id="212a3-112">文字列</span><span class="sxs-lookup"><span data-stu-id="212a3-112">string</span></span> | <span data-ttu-id="212a3-113">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="212a3-113">SHA-1 of the file that the recorded action was applied to</span></span>
<span data-ttu-id="212a3-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="212a3-114">SHA256</span></span> | <span data-ttu-id="212a3-115">string</span><span class="sxs-lookup"><span data-stu-id="212a3-115">string</span></span> | <span data-ttu-id="212a3-116">記録されたアクションが適用されたファイルの SHA-256</span><span class="sxs-lookup"><span data-stu-id="212a3-116">SHA-256 of the file that the recorded action was applied to</span></span>
<span data-ttu-id="212a3-117">MD5</span><span class="sxs-lookup"><span data-stu-id="212a3-117">MD5</span></span> | <span data-ttu-id="212a3-118">string</span><span class="sxs-lookup"><span data-stu-id="212a3-118">string</span></span> | <span data-ttu-id="212a3-119">記録されたアクションが適用されたファイルの MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="212a3-119">MD5 hash of the file that the recorded action was applied to</span></span>
<span data-ttu-id="212a3-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="212a3-120">FileSize</span></span> | <span data-ttu-id="212a3-121">int</span><span class="sxs-lookup"><span data-stu-id="212a3-121">int</span></span> | <span data-ttu-id="212a3-122">ファイルのサイズ (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="212a3-122">Size of the file in bytes</span></span>
<span data-ttu-id="212a3-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="212a3-123">GlobalPrevalence</span></span> | <span data-ttu-id="212a3-124">int</span><span class="sxs-lookup"><span data-stu-id="212a3-124">int</span></span> | <span data-ttu-id="212a3-125">Microsoft がグローバルに観察したエンティティのインスタンス数</span><span class="sxs-lookup"><span data-stu-id="212a3-125">Number of instances of the entity observed by Microsoft globally</span></span>
<span data-ttu-id="212a3-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="212a3-126">GlobalFirstSeen</span></span> | <span data-ttu-id="212a3-127">日付型</span><span class="sxs-lookup"><span data-stu-id="212a3-127">datetime</span></span> | <span data-ttu-id="212a3-128">エンティティが最初に Microsoft によってグローバルに観察された日時</span><span class="sxs-lookup"><span data-stu-id="212a3-128">Date and time when the entity was first observed by Microsoft globally</span></span>
<span data-ttu-id="212a3-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="212a3-129">GlobalLastSeen</span></span> | <span data-ttu-id="212a3-130">日付型</span><span class="sxs-lookup"><span data-stu-id="212a3-130">datetime</span></span> | <span data-ttu-id="212a3-131">エンティティが Microsoft によってグローバルに最後に観察された日時</span><span class="sxs-lookup"><span data-stu-id="212a3-131">Date and time when the entity was last observed by Microsoft globally</span></span>
<span data-ttu-id="212a3-132">署名者</span><span class="sxs-lookup"><span data-stu-id="212a3-132">Signer</span></span> | <span data-ttu-id="212a3-133">string</span><span class="sxs-lookup"><span data-stu-id="212a3-133">string</span></span> | <span data-ttu-id="212a3-134">ファイルの署名者に関する情報</span><span class="sxs-lookup"><span data-stu-id="212a3-134">Information about the signer of the file</span></span>
<span data-ttu-id="212a3-135">発行者</span><span class="sxs-lookup"><span data-stu-id="212a3-135">Issuer</span></span> | <span data-ttu-id="212a3-136">string</span><span class="sxs-lookup"><span data-stu-id="212a3-136">string</span></span> | <span data-ttu-id="212a3-137">発行元証明機関 (CA) に関する情報</span><span class="sxs-lookup"><span data-stu-id="212a3-137">Information about the issuing certificate authority (CA)</span></span>
<span data-ttu-id="212a3-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="212a3-138">SignerHash</span></span> | <span data-ttu-id="212a3-139">string</span><span class="sxs-lookup"><span data-stu-id="212a3-139">string</span></span> | <span data-ttu-id="212a3-140">署名者を識別する一意のハッシュ値</span><span class="sxs-lookup"><span data-stu-id="212a3-140">Unique hash value identifying the signer</span></span>
<span data-ttu-id="212a3-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="212a3-141">IsCertificateValid</span></span> | <span data-ttu-id="212a3-142">boolean</span><span class="sxs-lookup"><span data-stu-id="212a3-142">boolean</span></span> | <span data-ttu-id="212a3-143">ファイルの署名に使用する証明書が有効かどうか</span><span class="sxs-lookup"><span data-stu-id="212a3-143">Whether the certificate used to sign the file is valid</span></span>
<span data-ttu-id="212a3-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="212a3-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="212a3-145">boolean</span><span class="sxs-lookup"><span data-stu-id="212a3-145">boolean</span></span> | <span data-ttu-id="212a3-146">ルート証明書の署名者が Microsoft であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="212a3-146">Indicates whether the signer of the root certificate is Microsoft</span></span>
<span data-ttu-id="212a3-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="212a3-147">IsExecutable</span></span> | <span data-ttu-id="212a3-148">boolean</span><span class="sxs-lookup"><span data-stu-id="212a3-148">boolean</span></span> | <span data-ttu-id="212a3-149">ファイルがポータブル実行可能ファイル (PE) ファイルかどうか</span><span class="sxs-lookup"><span data-stu-id="212a3-149">Whether the file is a Portable Executable (PE) file</span></span>
<span data-ttu-id="212a3-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="212a3-150">ThreatName</span></span> | <span data-ttu-id="212a3-151">string</span><span class="sxs-lookup"><span data-stu-id="212a3-151">string</span></span> | <span data-ttu-id="212a3-152">マルウェアまたは検出された他の脅威の検出名</span><span class="sxs-lookup"><span data-stu-id="212a3-152">Detection name for any malware or other threats found</span></span>
<span data-ttu-id="212a3-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="212a3-153">Publisher</span></span> | <span data-ttu-id="212a3-154">string</span><span class="sxs-lookup"><span data-stu-id="212a3-154">string</span></span> | <span data-ttu-id="212a3-155">ファイルを発行した組織の名前</span><span class="sxs-lookup"><span data-stu-id="212a3-155">Name of the organization that published the file</span></span>
<span data-ttu-id="212a3-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="212a3-156">SoftwareName</span></span> | <span data-ttu-id="212a3-157">string</span><span class="sxs-lookup"><span data-stu-id="212a3-157">string</span></span> | <span data-ttu-id="212a3-158">ソフトウェア製品の名前</span><span class="sxs-lookup"><span data-stu-id="212a3-158">Name of the software product</span></span>

## <a name="syntax"></a><span data-ttu-id="212a3-159">構文</span><span class="sxs-lookup"><span data-stu-id="212a3-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="212a3-160">引数</span><span class="sxs-lookup"><span data-stu-id="212a3-160">Arguments</span></span>

- <span data-ttu-id="212a3-161">**x** — 使用するファイル ID 列: `SHA1` 、、または 、 ; `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` 関数が指定されていない `SHA1` 場合に使用する</span><span class="sxs-lookup"><span data-stu-id="212a3-161">**x** — file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1` or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="212a3-162">**y** - エンリッチするレコードの数に制限、1 ~ 1000。指定されていない場合、関数は 100 を使用します。</span><span class="sxs-lookup"><span data-stu-id="212a3-162">**y** — limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="212a3-163">例</span><span class="sxs-lookup"><span data-stu-id="212a3-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="212a3-164">SHA1 列のみを投影してエンリッチする</span><span class="sxs-lookup"><span data-stu-id="212a3-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="212a3-165">最初の 500 レコードを強化し、低普及率のファイルを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="212a3-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="212a3-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="212a3-166">Related topics</span></span>

- [<span data-ttu-id="212a3-167">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="212a3-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="212a3-168">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="212a3-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="212a3-169">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="212a3-169">Understand the schema</span></span>](advanced-hunting-schema-reference.md)