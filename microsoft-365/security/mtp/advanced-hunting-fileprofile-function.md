---
title: Microsoft の脅威保護のための高度な検索の FileProfile () 関数
description: FileProfile () を使用して、高度な検索クエリ結果のファイルに関する情報を表示する方法について説明します。
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、FileProfile、file profile、function、エンリッチメント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 6d627dcf3d6ec8ca1d2aa76eab484361c25b529e
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338419"
---
# <a name="fileprofile"></a><span data-ttu-id="45475-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="45475-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="45475-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="45475-105">**Applies to:**</span></span>
- <span data-ttu-id="45475-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="45475-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="45475-107">この `FileProfile()` 関数は、クエリによって検出されたファイルに次のデータを追加する、 [高度な](advanced-hunting-overview.md) 検索のエンリッチメント関数です。</span><span class="sxs-lookup"><span data-stu-id="45475-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="45475-108">Column</span><span class="sxs-lookup"><span data-stu-id="45475-108">Column</span></span> | <span data-ttu-id="45475-109">データ型</span><span class="sxs-lookup"><span data-stu-id="45475-109">Data type</span></span> | <span data-ttu-id="45475-110">説明</span><span class="sxs-lookup"><span data-stu-id="45475-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="45475-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="45475-111">SHA1</span></span> | <span data-ttu-id="45475-112">文字列</span><span class="sxs-lookup"><span data-stu-id="45475-112">string</span></span> | <span data-ttu-id="45475-113">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="45475-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="45475-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="45475-114">SHA256</span></span> | <span data-ttu-id="45475-115">文字列</span><span class="sxs-lookup"><span data-stu-id="45475-115">string</span></span> | <span data-ttu-id="45475-116">記録された操作が適用されたファイルの256</span><span class="sxs-lookup"><span data-stu-id="45475-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="45475-117">MD5</span><span class="sxs-lookup"><span data-stu-id="45475-117">MD5</span></span> | <span data-ttu-id="45475-118">文字列</span><span class="sxs-lookup"><span data-stu-id="45475-118">string</span></span> | <span data-ttu-id="45475-119">記録されたアクションが適用されたファイルの MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="45475-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="45475-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="45475-120">FileSize</span></span> | <span data-ttu-id="45475-121">int</span><span class="sxs-lookup"><span data-stu-id="45475-121">int</span></span> | <span data-ttu-id="45475-122">ファイルのサイズ (バイト数)</span><span class="sxs-lookup"><span data-stu-id="45475-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="45475-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="45475-123">GlobalPrevalence</span></span> | <span data-ttu-id="45475-124">int</span><span class="sxs-lookup"><span data-stu-id="45475-124">int</span></span> | <span data-ttu-id="45475-125">Microsoft によってグローバルに監視されたエンティティのインスタンスの数</span><span class="sxs-lookup"><span data-stu-id="45475-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="45475-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="45475-126">GlobalFirstSeen</span></span> | <span data-ttu-id="45475-127">日付型</span><span class="sxs-lookup"><span data-stu-id="45475-127">datetime</span></span> | <span data-ttu-id="45475-128">エンティティが最初に Microsoft によって監視された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="45475-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="45475-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="45475-129">GlobalLastSeen</span></span> | <span data-ttu-id="45475-130">日付型</span><span class="sxs-lookup"><span data-stu-id="45475-130">datetime</span></span> | <span data-ttu-id="45475-131">エンティティが最後に Microsoft によって監視された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="45475-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="45475-132">署名者</span><span class="sxs-lookup"><span data-stu-id="45475-132">Signer</span></span> | <span data-ttu-id="45475-133">文字列</span><span class="sxs-lookup"><span data-stu-id="45475-133">string</span></span> | <span data-ttu-id="45475-134">ファイルの署名者に関する情報</span><span class="sxs-lookup"><span data-stu-id="45475-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="45475-135">発行者</span><span class="sxs-lookup"><span data-stu-id="45475-135">Issuer</span></span> | <span data-ttu-id="45475-136">文字列</span><span class="sxs-lookup"><span data-stu-id="45475-136">string</span></span> | <span data-ttu-id="45475-137">発行元の証明機関 (CA) に関する情報</span><span class="sxs-lookup"><span data-stu-id="45475-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="45475-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="45475-138">SignerHash</span></span> | <span data-ttu-id="45475-139">文字列</span><span class="sxs-lookup"><span data-stu-id="45475-139">string</span></span> | <span data-ttu-id="45475-140">署名者を識別する一意のハッシュ値</span><span class="sxs-lookup"><span data-stu-id="45475-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="45475-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="45475-141">IsCertificateValid</span></span> | <span data-ttu-id="45475-142">ブール値</span><span class="sxs-lookup"><span data-stu-id="45475-142">boolean</span></span> | <span data-ttu-id="45475-143">ファイルへの署名に使用された証明書が有効かどうか</span><span class="sxs-lookup"><span data-stu-id="45475-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="45475-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="45475-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="45475-145">ブール値</span><span class="sxs-lookup"><span data-stu-id="45475-145">boolean</span></span> | <span data-ttu-id="45475-146">ルート証明書の署名者が Microsoft であるかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="45475-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="45475-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="45475-147">IsExecutable</span></span> | <span data-ttu-id="45475-148">ブール値</span><span class="sxs-lookup"><span data-stu-id="45475-148">boolean</span></span> | <span data-ttu-id="45475-149">ファイルが移植可能な実行可能 (PE) ファイルであるかどうか</span><span class="sxs-lookup"><span data-stu-id="45475-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="45475-150">Mail.threatname です</span><span class="sxs-lookup"><span data-stu-id="45475-150">ThreatName</span></span> | <span data-ttu-id="45475-151">文字列</span><span class="sxs-lookup"><span data-stu-id="45475-151">string</span></span> | <span data-ttu-id="45475-152">検出されたマルウェアまたは他の脅威の検出名</span><span class="sxs-lookup"><span data-stu-id="45475-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="45475-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="45475-153">Publisher</span></span> | <span data-ttu-id="45475-154">文字列</span><span class="sxs-lookup"><span data-stu-id="45475-154">string</span></span> | <span data-ttu-id="45475-155">ファイルを発行した組織の名前</span><span class="sxs-lookup"><span data-stu-id="45475-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="45475-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="45475-156">SoftwareName</span></span> | <span data-ttu-id="45475-157">string</span><span class="sxs-lookup"><span data-stu-id="45475-157">string</span></span> | <span data-ttu-id="45475-158">ソフトウェア製品の名前</span><span class="sxs-lookup"><span data-stu-id="45475-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="45475-159">構文</span><span class="sxs-lookup"><span data-stu-id="45475-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="45475-160">引数</span><span class="sxs-lookup"><span data-stu-id="45475-160">Arguments</span></span>

- <span data-ttu-id="45475-161">**x**—使用するファイル ID 列: `SHA1` 、 `SHA256` 、 `InitiatingProcessSHA1` 、または `InitiatingProcessSHA256` 関数が `SHA1` 未指定の場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="45475-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="45475-162">**y**—強化するレコード数を1-1000 に制限します。関数は、未指定の場合は100を使用します。</span><span class="sxs-lookup"><span data-stu-id="45475-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="45475-163">例</span><span class="sxs-lookup"><span data-stu-id="45475-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="45475-164">SHA1 列のみをプロジェクトにして、さらに充実します。</span><span class="sxs-lookup"><span data-stu-id="45475-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="45475-165">最初の500レコードを強化し、流行していないファイルを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="45475-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="45475-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="45475-166">Related topics</span></span>
- [<span data-ttu-id="45475-167">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="45475-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="45475-168">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="45475-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="45475-169">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="45475-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="45475-170">その他のクエリの例を取得する</span><span class="sxs-lookup"><span data-stu-id="45475-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
