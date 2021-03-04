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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f2e92967b8951cd0f5a3c394a537404db1d53819
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50424025"
---
# <a name="fileprofile"></a><span data-ttu-id="32216-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="32216-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="32216-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="32216-105">**Applies to:**</span></span>
- <span data-ttu-id="32216-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="32216-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="32216-107">この `FileProfile()` 関数は、高度な検索の[](advanced-hunting-overview.md)エンリッチメント関数で、クエリで見つかったファイルに次のデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="32216-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="32216-108">列</span><span class="sxs-lookup"><span data-stu-id="32216-108">Column</span></span> | <span data-ttu-id="32216-109">データ型</span><span class="sxs-lookup"><span data-stu-id="32216-109">Data type</span></span> | <span data-ttu-id="32216-110">説明</span><span class="sxs-lookup"><span data-stu-id="32216-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="32216-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="32216-111">SHA1</span></span> | <span data-ttu-id="32216-112">文字列</span><span class="sxs-lookup"><span data-stu-id="32216-112">string</span></span> | <span data-ttu-id="32216-113">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="32216-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="32216-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="32216-114">SHA256</span></span> | <span data-ttu-id="32216-115">string</span><span class="sxs-lookup"><span data-stu-id="32216-115">string</span></span> | <span data-ttu-id="32216-116">記録されたアクションが適用されたファイルの SHA-256</span><span class="sxs-lookup"><span data-stu-id="32216-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="32216-117">MD5</span><span class="sxs-lookup"><span data-stu-id="32216-117">MD5</span></span> | <span data-ttu-id="32216-118">string</span><span class="sxs-lookup"><span data-stu-id="32216-118">string</span></span> | <span data-ttu-id="32216-119">記録されたアクションが適用されたファイルの MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="32216-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="32216-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="32216-120">FileSize</span></span> | <span data-ttu-id="32216-121">int</span><span class="sxs-lookup"><span data-stu-id="32216-121">int</span></span> | <span data-ttu-id="32216-122">ファイルのサイズ (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="32216-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="32216-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="32216-123">GlobalPrevalence</span></span> | <span data-ttu-id="32216-124">int</span><span class="sxs-lookup"><span data-stu-id="32216-124">int</span></span> | <span data-ttu-id="32216-125">Microsoft がグローバルに観察したエンティティのインスタンス数</span><span class="sxs-lookup"><span data-stu-id="32216-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="32216-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="32216-126">GlobalFirstSeen</span></span> | <span data-ttu-id="32216-127">日付型</span><span class="sxs-lookup"><span data-stu-id="32216-127">datetime</span></span> | <span data-ttu-id="32216-128">エンティティが最初に Microsoft によってグローバルに観察された日時</span><span class="sxs-lookup"><span data-stu-id="32216-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="32216-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="32216-129">GlobalLastSeen</span></span> | <span data-ttu-id="32216-130">日付型</span><span class="sxs-lookup"><span data-stu-id="32216-130">datetime</span></span> | <span data-ttu-id="32216-131">エンティティが Microsoft によってグローバルに最後に観察された日時</span><span class="sxs-lookup"><span data-stu-id="32216-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="32216-132">署名者</span><span class="sxs-lookup"><span data-stu-id="32216-132">Signer</span></span> | <span data-ttu-id="32216-133">string</span><span class="sxs-lookup"><span data-stu-id="32216-133">string</span></span> | <span data-ttu-id="32216-134">ファイルの署名者に関する情報</span><span class="sxs-lookup"><span data-stu-id="32216-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="32216-135">発行者</span><span class="sxs-lookup"><span data-stu-id="32216-135">Issuer</span></span> | <span data-ttu-id="32216-136">string</span><span class="sxs-lookup"><span data-stu-id="32216-136">string</span></span> | <span data-ttu-id="32216-137">発行元証明機関 (CA) に関する情報</span><span class="sxs-lookup"><span data-stu-id="32216-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="32216-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="32216-138">SignerHash</span></span> | <span data-ttu-id="32216-139">string</span><span class="sxs-lookup"><span data-stu-id="32216-139">string</span></span> | <span data-ttu-id="32216-140">署名者を識別する一意のハッシュ値</span><span class="sxs-lookup"><span data-stu-id="32216-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="32216-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="32216-141">IsCertificateValid</span></span> | <span data-ttu-id="32216-142">boolean</span><span class="sxs-lookup"><span data-stu-id="32216-142">boolean</span></span> | <span data-ttu-id="32216-143">ファイルの署名に使用する証明書が有効かどうか</span><span class="sxs-lookup"><span data-stu-id="32216-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="32216-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="32216-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="32216-145">boolean</span><span class="sxs-lookup"><span data-stu-id="32216-145">boolean</span></span> | <span data-ttu-id="32216-146">ルート証明書の署名者が Microsoft であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="32216-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="32216-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="32216-147">IsExecutable</span></span> | <span data-ttu-id="32216-148">boolean</span><span class="sxs-lookup"><span data-stu-id="32216-148">boolean</span></span> | <span data-ttu-id="32216-149">ファイルがポータブル実行可能ファイル (PE) ファイルかどうか</span><span class="sxs-lookup"><span data-stu-id="32216-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="32216-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="32216-150">ThreatName</span></span> | <span data-ttu-id="32216-151">string</span><span class="sxs-lookup"><span data-stu-id="32216-151">string</span></span> | <span data-ttu-id="32216-152">マルウェアまたは検出された他の脅威の検出名</span><span class="sxs-lookup"><span data-stu-id="32216-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="32216-153">発行者</span><span class="sxs-lookup"><span data-stu-id="32216-153">Publisher</span></span> | <span data-ttu-id="32216-154">string</span><span class="sxs-lookup"><span data-stu-id="32216-154">string</span></span> | <span data-ttu-id="32216-155">ファイルを発行した組織の名前</span><span class="sxs-lookup"><span data-stu-id="32216-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="32216-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="32216-156">SoftwareName</span></span> | <span data-ttu-id="32216-157">string</span><span class="sxs-lookup"><span data-stu-id="32216-157">string</span></span> | <span data-ttu-id="32216-158">ソフトウェア製品の名前</span><span class="sxs-lookup"><span data-stu-id="32216-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="32216-159">構文</span><span class="sxs-lookup"><span data-stu-id="32216-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="32216-160">引数</span><span class="sxs-lookup"><span data-stu-id="32216-160">Arguments</span></span>

- <span data-ttu-id="32216-161">**x**—使用するファイル ID 列: 、、 を使用する関数は `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` 、指定されていない場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="32216-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="32216-162">**y**—エンリッチするレコードの数に制限、1 ~ 1000。指定されていない場合、関数は 100 を使用します。</span><span class="sxs-lookup"><span data-stu-id="32216-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="32216-163">エンリッチメント関数は、利用可能な場合にのみ補足情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="32216-163">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="32216-164">情報の可用性はさまざまで、多くの要因に依存します。</span><span class="sxs-lookup"><span data-stu-id="32216-164">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="32216-165">クエリで FileProfile() を使用する場合、またはカスタム検出を作成する場合は、この点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="32216-165">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="32216-166">最良の結果を得る場合は、SHA1 で FileProfile() 関数を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="32216-166">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="32216-167">例</span><span class="sxs-lookup"><span data-stu-id="32216-167">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="32216-168">SHA1 列のみを投影してエンリッチする</span><span class="sxs-lookup"><span data-stu-id="32216-168">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="32216-169">最初の 500 レコードを強化し、低普及率のファイルを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="32216-169">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="32216-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="32216-170">Related topics</span></span>
- [<span data-ttu-id="32216-171">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="32216-171">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="32216-172">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="32216-172">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="32216-173">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="32216-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="32216-174">クエリの例を追加する</span><span class="sxs-lookup"><span data-stu-id="32216-174">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
