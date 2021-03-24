---
title: Microsoft 365 Defender の高度な検索での FileProfile() 関数
description: FileProfile() を使用して高度な検索クエリ結果のファイルに関する情報を強化する方法について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、FileProfile、ファイル プロファイル、関数、エンリッチメント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e511c12240512af772b3552f63ad9ed98ff105af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062083"
---
# <a name="fileprofile"></a><span data-ttu-id="8b65d-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="8b65d-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8b65d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8b65d-105">**Applies to:**</span></span>
- <span data-ttu-id="8b65d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b65d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8b65d-107">この `FileProfile()` 関数は、高度な検索の[](advanced-hunting-overview.md)エンリッチメント関数で、クエリで見つかったファイルに次のデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="8b65d-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="8b65d-108">Column</span><span class="sxs-lookup"><span data-stu-id="8b65d-108">Column</span></span> | <span data-ttu-id="8b65d-109">データ型</span><span class="sxs-lookup"><span data-stu-id="8b65d-109">Data type</span></span> | <span data-ttu-id="8b65d-110">説明</span><span class="sxs-lookup"><span data-stu-id="8b65d-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="8b65d-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="8b65d-111">SHA1</span></span> | <span data-ttu-id="8b65d-112">文字列</span><span class="sxs-lookup"><span data-stu-id="8b65d-112">string</span></span> | <span data-ttu-id="8b65d-113">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="8b65d-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="8b65d-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="8b65d-114">SHA256</span></span> | <span data-ttu-id="8b65d-115">string</span><span class="sxs-lookup"><span data-stu-id="8b65d-115">string</span></span> | <span data-ttu-id="8b65d-116">記録されたアクションが適用されたファイルの SHA-256</span><span class="sxs-lookup"><span data-stu-id="8b65d-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="8b65d-117">MD5</span><span class="sxs-lookup"><span data-stu-id="8b65d-117">MD5</span></span> | <span data-ttu-id="8b65d-118">string</span><span class="sxs-lookup"><span data-stu-id="8b65d-118">string</span></span> | <span data-ttu-id="8b65d-119">記録されたアクションが適用されたファイルの MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="8b65d-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="8b65d-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="8b65d-120">FileSize</span></span> | <span data-ttu-id="8b65d-121">int</span><span class="sxs-lookup"><span data-stu-id="8b65d-121">int</span></span> | <span data-ttu-id="8b65d-122">ファイルのサイズ (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="8b65d-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="8b65d-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="8b65d-123">GlobalPrevalence</span></span> | <span data-ttu-id="8b65d-124">int</span><span class="sxs-lookup"><span data-stu-id="8b65d-124">int</span></span> | <span data-ttu-id="8b65d-125">Microsoft がグローバルに観察したエンティティのインスタンス数</span><span class="sxs-lookup"><span data-stu-id="8b65d-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="8b65d-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="8b65d-126">GlobalFirstSeen</span></span> | <span data-ttu-id="8b65d-127">日付型</span><span class="sxs-lookup"><span data-stu-id="8b65d-127">datetime</span></span> | <span data-ttu-id="8b65d-128">エンティティが最初に Microsoft によってグローバルに観察された日時</span><span class="sxs-lookup"><span data-stu-id="8b65d-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="8b65d-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="8b65d-129">GlobalLastSeen</span></span> | <span data-ttu-id="8b65d-130">日付型</span><span class="sxs-lookup"><span data-stu-id="8b65d-130">datetime</span></span> | <span data-ttu-id="8b65d-131">エンティティが Microsoft によってグローバルに最後に観察された日時</span><span class="sxs-lookup"><span data-stu-id="8b65d-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="8b65d-132">署名者</span><span class="sxs-lookup"><span data-stu-id="8b65d-132">Signer</span></span> | <span data-ttu-id="8b65d-133">string</span><span class="sxs-lookup"><span data-stu-id="8b65d-133">string</span></span> | <span data-ttu-id="8b65d-134">ファイルの署名者に関する情報</span><span class="sxs-lookup"><span data-stu-id="8b65d-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="8b65d-135">発行者</span><span class="sxs-lookup"><span data-stu-id="8b65d-135">Issuer</span></span> | <span data-ttu-id="8b65d-136">string</span><span class="sxs-lookup"><span data-stu-id="8b65d-136">string</span></span> | <span data-ttu-id="8b65d-137">発行元証明機関 (CA) に関する情報</span><span class="sxs-lookup"><span data-stu-id="8b65d-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="8b65d-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="8b65d-138">SignerHash</span></span> | <span data-ttu-id="8b65d-139">string</span><span class="sxs-lookup"><span data-stu-id="8b65d-139">string</span></span> | <span data-ttu-id="8b65d-140">署名者を識別する一意のハッシュ値</span><span class="sxs-lookup"><span data-stu-id="8b65d-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="8b65d-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="8b65d-141">IsCertificateValid</span></span> | <span data-ttu-id="8b65d-142">boolean</span><span class="sxs-lookup"><span data-stu-id="8b65d-142">boolean</span></span> | <span data-ttu-id="8b65d-143">ファイルの署名に使用する証明書が有効かどうか</span><span class="sxs-lookup"><span data-stu-id="8b65d-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="8b65d-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="8b65d-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="8b65d-145">boolean</span><span class="sxs-lookup"><span data-stu-id="8b65d-145">boolean</span></span> | <span data-ttu-id="8b65d-146">ルート証明書の署名者が Microsoft であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="8b65d-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="8b65d-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="8b65d-147">IsExecutable</span></span> | <span data-ttu-id="8b65d-148">boolean</span><span class="sxs-lookup"><span data-stu-id="8b65d-148">boolean</span></span> | <span data-ttu-id="8b65d-149">ファイルがポータブル実行可能ファイル (PE) ファイルかどうか</span><span class="sxs-lookup"><span data-stu-id="8b65d-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="8b65d-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="8b65d-150">ThreatName</span></span> | <span data-ttu-id="8b65d-151">string</span><span class="sxs-lookup"><span data-stu-id="8b65d-151">string</span></span> | <span data-ttu-id="8b65d-152">マルウェアまたは検出された他の脅威の検出名</span><span class="sxs-lookup"><span data-stu-id="8b65d-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="8b65d-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="8b65d-153">Publisher</span></span> | <span data-ttu-id="8b65d-154">string</span><span class="sxs-lookup"><span data-stu-id="8b65d-154">string</span></span> | <span data-ttu-id="8b65d-155">ファイルを発行した組織の名前</span><span class="sxs-lookup"><span data-stu-id="8b65d-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="8b65d-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="8b65d-156">SoftwareName</span></span> | <span data-ttu-id="8b65d-157">string</span><span class="sxs-lookup"><span data-stu-id="8b65d-157">string</span></span> | <span data-ttu-id="8b65d-158">ソフトウェア製品の名前</span><span class="sxs-lookup"><span data-stu-id="8b65d-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="8b65d-159">構文</span><span class="sxs-lookup"><span data-stu-id="8b65d-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="8b65d-160">引数</span><span class="sxs-lookup"><span data-stu-id="8b65d-160">Arguments</span></span>

- <span data-ttu-id="8b65d-161">**x**—使用するファイル ID 列: 、、 を使用する関数は `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` 、指定されていない場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="8b65d-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="8b65d-162">**y**—エンリッチするレコードの数に制限、1 ~ 1000。指定されていない場合、関数は 100 を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b65d-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="8b65d-163">エンリッチメント関数は、利用可能な場合にのみ補足情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="8b65d-163">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="8b65d-164">情報の可用性はさまざまで、多くの要因に依存します。</span><span class="sxs-lookup"><span data-stu-id="8b65d-164">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="8b65d-165">クエリで FileProfile() を使用する場合、またはカスタム検出を作成する場合は、この点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="8b65d-165">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="8b65d-166">最良の結果を得る場合は、SHA1 で FileProfile() 関数を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8b65d-166">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="8b65d-167">例</span><span class="sxs-lookup"><span data-stu-id="8b65d-167">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="8b65d-168">SHA1 列のみを投影してエンリッチする</span><span class="sxs-lookup"><span data-stu-id="8b65d-168">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="8b65d-169">最初の 500 レコードを強化し、低普及率のファイルを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="8b65d-169">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="8b65d-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b65d-170">Related topics</span></span>
- [<span data-ttu-id="8b65d-171">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="8b65d-171">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8b65d-172">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="8b65d-172">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8b65d-173">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="8b65d-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8b65d-174">クエリの例を追加する</span><span class="sxs-lookup"><span data-stu-id="8b65d-174">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
