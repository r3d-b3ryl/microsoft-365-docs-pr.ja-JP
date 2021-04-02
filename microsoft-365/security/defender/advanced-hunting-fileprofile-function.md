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
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ea4f22b70e607b42155342dde1ac16b1ad640981
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498458"
---
# <a name="fileprofile"></a><span data-ttu-id="604c4-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="604c4-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="604c4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="604c4-105">**Applies to:**</span></span>
- <span data-ttu-id="604c4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="604c4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="604c4-107">この `FileProfile()` 関数は、高度な検索の[](advanced-hunting-overview.md)エンリッチメント関数で、クエリで見つかったファイルに次のデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="604c4-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="604c4-108">Column</span><span class="sxs-lookup"><span data-stu-id="604c4-108">Column</span></span> | <span data-ttu-id="604c4-109">データ型</span><span class="sxs-lookup"><span data-stu-id="604c4-109">Data type</span></span> | <span data-ttu-id="604c4-110">説明</span><span class="sxs-lookup"><span data-stu-id="604c4-110">Description</span></span> |
|------------|---------------|-------------|
| `SHA1` | <span data-ttu-id="604c4-111">文字列</span><span class="sxs-lookup"><span data-stu-id="604c4-111">string</span></span> | <span data-ttu-id="604c4-112">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="604c4-112">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="604c4-113">文字列</span><span class="sxs-lookup"><span data-stu-id="604c4-113">string</span></span> | <span data-ttu-id="604c4-114">記録されたアクションが適用されたファイルの SHA-256</span><span class="sxs-lookup"><span data-stu-id="604c4-114">SHA-256 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="604c4-115">文字列</span><span class="sxs-lookup"><span data-stu-id="604c4-115">string</span></span> | <span data-ttu-id="604c4-116">記録されたアクションが適用されたファイルの MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="604c4-116">MD5 hash of the file that the recorded action was applied to</span></span> |
| `FileSize` | <span data-ttu-id="604c4-117">int</span><span class="sxs-lookup"><span data-stu-id="604c4-117">int</span></span> | <span data-ttu-id="604c4-118">ファイルのサイズ (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="604c4-118">Size of the file in bytes</span></span> |
| `GlobalPrevalence` | <span data-ttu-id="604c4-119">int</span><span class="sxs-lookup"><span data-stu-id="604c4-119">int</span></span> | <span data-ttu-id="604c4-120">Microsoft がグローバルに観察したエンティティのインスタンス数</span><span class="sxs-lookup"><span data-stu-id="604c4-120">Number of instances of the entity observed by Microsoft globally</span></span> |
| `GlobalFirstSeen` | <span data-ttu-id="604c4-121">日付型</span><span class="sxs-lookup"><span data-stu-id="604c4-121">datetime</span></span> | <span data-ttu-id="604c4-122">エンティティが最初に Microsoft によってグローバルに観察された日時</span><span class="sxs-lookup"><span data-stu-id="604c4-122">Date and time when the entity was first observed by Microsoft globally</span></span> |
| `GlobalLastSeen` | <span data-ttu-id="604c4-123">日付型</span><span class="sxs-lookup"><span data-stu-id="604c4-123">datetime</span></span> | <span data-ttu-id="604c4-124">エンティティが Microsoft によってグローバルに最後に観察された日時</span><span class="sxs-lookup"><span data-stu-id="604c4-124">Date and time when the entity was last observed by Microsoft globally</span></span> |
| `Signer` | <span data-ttu-id="604c4-125">文字列</span><span class="sxs-lookup"><span data-stu-id="604c4-125">string</span></span> | <span data-ttu-id="604c4-126">ファイルの署名者に関する情報</span><span class="sxs-lookup"><span data-stu-id="604c4-126">Information about the signer of the file</span></span> |
| `Issuer` | <span data-ttu-id="604c4-127">文字列</span><span class="sxs-lookup"><span data-stu-id="604c4-127">string</span></span> | <span data-ttu-id="604c4-128">発行元証明機関 (CA) に関する情報</span><span class="sxs-lookup"><span data-stu-id="604c4-128">Information about the issuing certificate authority (CA)</span></span> |
| `SignerHash` | <span data-ttu-id="604c4-129">文字列</span><span class="sxs-lookup"><span data-stu-id="604c4-129">string</span></span> | <span data-ttu-id="604c4-130">署名者を識別する一意のハッシュ値</span><span class="sxs-lookup"><span data-stu-id="604c4-130">Unique hash value identifying the signer</span></span> |
| `IsCertificateValid` | <span data-ttu-id="604c4-131">boolean</span><span class="sxs-lookup"><span data-stu-id="604c4-131">boolean</span></span> | <span data-ttu-id="604c4-132">ファイルの署名に使用する証明書が有効かどうか</span><span class="sxs-lookup"><span data-stu-id="604c4-132">Whether the certificate used to sign the file is valid</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="604c4-133">boolean</span><span class="sxs-lookup"><span data-stu-id="604c4-133">boolean</span></span> | <span data-ttu-id="604c4-134">ルート証明書の署名者が Microsoft であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="604c4-134">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `SignatureState` | <span data-ttu-id="604c4-135">文字列</span><span class="sxs-lookup"><span data-stu-id="604c4-135">string</span></span> | <span data-ttu-id="604c4-136">ファイル署名の状態: SignedValid - ファイルは有効な署名で署名されています。SignedInvalid - ファイルは署名されますが、証明書は無効です。Signeded - ファイルは署名されていない、不明 - ファイルに関する情報を取得できません</span><span class="sxs-lookup"><span data-stu-id="604c4-136">State of the file signature: SignedValid - the file is signed with a valid signature, SignedInvalid - the file is signed but the certificate is invalid, Unsigned - the file is not signed, Unknown - information about the file cannot be retrieved</span></span>
| `IsExecutable` | <span data-ttu-id="604c4-137">boolean</span><span class="sxs-lookup"><span data-stu-id="604c4-137">boolean</span></span> | <span data-ttu-id="604c4-138">ファイルがポータブル実行可能ファイル (PE) ファイルかどうか</span><span class="sxs-lookup"><span data-stu-id="604c4-138">Whether the file is a Portable Executable (PE) file</span></span> |
| `ThreatName` | <span data-ttu-id="604c4-139">文字列</span><span class="sxs-lookup"><span data-stu-id="604c4-139">string</span></span> | <span data-ttu-id="604c4-140">マルウェアまたは検出された他の脅威の検出名</span><span class="sxs-lookup"><span data-stu-id="604c4-140">Detection name for any malware or other threats found</span></span> |
| `Publisher` | <span data-ttu-id="604c4-141">文字列</span><span class="sxs-lookup"><span data-stu-id="604c4-141">string</span></span> | <span data-ttu-id="604c4-142">ファイルを発行した組織の名前</span><span class="sxs-lookup"><span data-stu-id="604c4-142">Name of the organization that published the file</span></span> |
| `SoftwareName` | <span data-ttu-id="604c4-143">string</span><span class="sxs-lookup"><span data-stu-id="604c4-143">string</span></span> | <span data-ttu-id="604c4-144">ソフトウェア製品の名前</span><span class="sxs-lookup"><span data-stu-id="604c4-144">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="604c4-145">構文</span><span class="sxs-lookup"><span data-stu-id="604c4-145">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="604c4-146">引数</span><span class="sxs-lookup"><span data-stu-id="604c4-146">Arguments</span></span>

- <span data-ttu-id="604c4-147">**x**—使用するファイル ID 列: 、、 を使用する関数は `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` 、指定されていない場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="604c4-147">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="604c4-148">**y**—エンリッチするレコードの数に制限、1 ~ 1000。指定されていない場合、関数は 100 を使用します。</span><span class="sxs-lookup"><span data-stu-id="604c4-148">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="604c4-149">エンリッチメント関数は、利用可能な場合にのみ補足情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="604c4-149">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="604c4-150">情報の可用性はさまざまで、多くの要因に依存します。</span><span class="sxs-lookup"><span data-stu-id="604c4-150">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="604c4-151">クエリで FileProfile() を使用する場合、またはカスタム検出を作成する場合は、この点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="604c4-151">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="604c4-152">最良の結果を得る場合は、SHA1 で FileProfile() 関数を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="604c4-152">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="604c4-153">例</span><span class="sxs-lookup"><span data-stu-id="604c4-153">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="604c4-154">SHA1 列のみを投影してエンリッチする</span><span class="sxs-lookup"><span data-stu-id="604c4-154">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="604c4-155">最初の 500 レコードを強化し、低普及率のファイルを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="604c4-155">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="604c4-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="604c4-156">Related topics</span></span>
- [<span data-ttu-id="604c4-157">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="604c4-157">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="604c4-158">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="604c4-158">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="604c4-159">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="604c4-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="604c4-160">クエリの例を追加する</span><span class="sxs-lookup"><span data-stu-id="604c4-160">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
