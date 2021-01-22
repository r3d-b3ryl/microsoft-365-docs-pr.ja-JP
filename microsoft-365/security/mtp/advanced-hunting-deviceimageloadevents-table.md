---
title: 高度な検索スキーマの DeviceImageLoadEvents テーブル
description: 高度な検索スキーマの DeviceImageLoadEvents テーブルの DLL 読み込みイベントについて説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、imageloadevents、DeviceImageLoadEvents、DLL 読み込み、ライブラリ、ファイル イメージ
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
ms.openlocfilehash: 924d465d90086bcfffe29660b7f281ff3d5b07aa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931292"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="4ec59-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="4ec59-104">DeviceImageLoadEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4ec59-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4ec59-105">**Applies to:**</span></span>
- <span data-ttu-id="4ec59-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ec59-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="4ec59-107">高度 `DeviceImageLoadEvents` な検索スキーマの [表には](advanced-hunting-overview.md) 、DLL 読み込みイベントに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4ec59-107">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="4ec59-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4ec59-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="4ec59-109">テーブルでサポートされているイベントの種類 ( 値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ `ActionType` リファレンスを使用してください。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="4ec59-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="4ec59-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ec59-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4ec59-111">列名</span><span class="sxs-lookup"><span data-stu-id="4ec59-111">Column name</span></span> | <span data-ttu-id="4ec59-112">データ型</span><span class="sxs-lookup"><span data-stu-id="4ec59-112">Data type</span></span> | <span data-ttu-id="4ec59-113">説明</span><span class="sxs-lookup"><span data-stu-id="4ec59-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="4ec59-114">日付型</span><span class="sxs-lookup"><span data-stu-id="4ec59-114">datetime</span></span> | <span data-ttu-id="4ec59-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="4ec59-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="4ec59-116">string</span><span class="sxs-lookup"><span data-stu-id="4ec59-116">string</span></span> | <span data-ttu-id="4ec59-117">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="4ec59-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="4ec59-118">string</span><span class="sxs-lookup"><span data-stu-id="4ec59-118">string</span></span> | <span data-ttu-id="4ec59-119">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="4ec59-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="4ec59-120">string</span><span class="sxs-lookup"><span data-stu-id="4ec59-120">string</span></span> | <span data-ttu-id="4ec59-121">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="4ec59-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="4ec59-122">詳細については [、ポータル内スキーマ リファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ec59-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `FileName` | <span data-ttu-id="4ec59-123">文字列</span><span class="sxs-lookup"><span data-stu-id="4ec59-123">string</span></span> | <span data-ttu-id="4ec59-124">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="4ec59-124">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="4ec59-125">文字列</span><span class="sxs-lookup"><span data-stu-id="4ec59-125">string</span></span> | <span data-ttu-id="4ec59-126">記録されたアクションが適用されたファイルを含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="4ec59-126">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="4ec59-127">文字列</span><span class="sxs-lookup"><span data-stu-id="4ec59-127">string</span></span> | <span data-ttu-id="4ec59-128">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="4ec59-128">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="4ec59-129">文字列</span><span class="sxs-lookup"><span data-stu-id="4ec59-129">string</span></span> | <span data-ttu-id="4ec59-130">記録されたアクションが適用されたファイルの SHA-256</span><span class="sxs-lookup"><span data-stu-id="4ec59-130">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="4ec59-131">このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="4ec59-131">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `MD5` | <span data-ttu-id="4ec59-132">文字列型</span><span class="sxs-lookup"><span data-stu-id="4ec59-132">string</span></span> | <span data-ttu-id="4ec59-133">記録されたアクションが適用されたファイルの MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="4ec59-133">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="4ec59-134">string</span><span class="sxs-lookup"><span data-stu-id="4ec59-134">string</span></span> | <span data-ttu-id="4ec59-135">イベントを処理するプロセスを実行したアカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="4ec59-135">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="4ec59-136">string</span><span class="sxs-lookup"><span data-stu-id="4ec59-136">string</span></span> | <span data-ttu-id="4ec59-137">イベントを処理するプロセスを実行したアカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="4ec59-137">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="4ec59-138">string</span><span class="sxs-lookup"><span data-stu-id="4ec59-138">string</span></span> | <span data-ttu-id="4ec59-139">イベントを処理するプロセスを実行したアカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="4ec59-139">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="4ec59-140">string</span><span class="sxs-lookup"><span data-stu-id="4ec59-140">string</span></span> | <span data-ttu-id="4ec59-141">イベントを開始したプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="4ec59-141">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="4ec59-142">Windows は、インターネット ダウンロードから起動された場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="4ec59-142">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="4ec59-143">これらの整合性レベルは、リソースへのアクセス許可に影響します。</span><span class="sxs-lookup"><span data-stu-id="4ec59-143">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="4ec59-144">string</span><span class="sxs-lookup"><span data-stu-id="4ec59-144">string</span></span> | <span data-ttu-id="4ec59-145">イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権の昇格の有無を示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="4ec59-145">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="4ec59-146">string</span><span class="sxs-lookup"><span data-stu-id="4ec59-146">string</span></span> | <span data-ttu-id="4ec59-147">イベントを開始したプロセス (イメージ ファイル) の SHA-1</span><span class="sxs-lookup"><span data-stu-id="4ec59-147">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="4ec59-148">string</span><span class="sxs-lookup"><span data-stu-id="4ec59-148">string</span></span> | <span data-ttu-id="4ec59-149">イベントを開始したプロセス (イメージ ファイル) の SHA-256。</span><span class="sxs-lookup"><span data-stu-id="4ec59-149">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="4ec59-150">このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="4ec59-150">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="4ec59-151">文字列型</span><span class="sxs-lookup"><span data-stu-id="4ec59-151">string</span></span> | <span data-ttu-id="4ec59-152">イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="4ec59-152">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="4ec59-153">string</span><span class="sxs-lookup"><span data-stu-id="4ec59-153">string</span></span> | <span data-ttu-id="4ec59-154">イベントを開始したプロセスの名前</span><span class="sxs-lookup"><span data-stu-id="4ec59-154">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="4ec59-155">int</span><span class="sxs-lookup"><span data-stu-id="4ec59-155">int</span></span> | <span data-ttu-id="4ec59-156">イベントを開始したプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="4ec59-156">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="4ec59-157">string</span><span class="sxs-lookup"><span data-stu-id="4ec59-157">string</span></span> | <span data-ttu-id="4ec59-158">イベントを開始したプロセスの実行に使用されるコマンド ライン</span><span class="sxs-lookup"><span data-stu-id="4ec59-158">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="4ec59-159">日付型</span><span class="sxs-lookup"><span data-stu-id="4ec59-159">datetime</span></span> | <span data-ttu-id="4ec59-160">イベントを開始したプロセスが開始された日時</span><span class="sxs-lookup"><span data-stu-id="4ec59-160">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="4ec59-161">string</span><span class="sxs-lookup"><span data-stu-id="4ec59-161">string</span></span> | <span data-ttu-id="4ec59-162">イベントを開始したプロセス (イメージ ファイル) を含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="4ec59-162">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="4ec59-163">int</span><span class="sxs-lookup"><span data-stu-id="4ec59-163">int</span></span> | <span data-ttu-id="4ec59-164">イベントを処理するプロセスを生成した親プロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="4ec59-164">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="4ec59-165">string</span><span class="sxs-lookup"><span data-stu-id="4ec59-165">string</span></span> | <span data-ttu-id="4ec59-166">イベントを処理するプロセスを生成した親プロセスの名前</span><span class="sxs-lookup"><span data-stu-id="4ec59-166">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="4ec59-167">日付型</span><span class="sxs-lookup"><span data-stu-id="4ec59-167">datetime</span></span> | <span data-ttu-id="4ec59-168">イベントを担当するプロセスの親が開始された日時</span><span class="sxs-lookup"><span data-stu-id="4ec59-168">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="4ec59-169">long</span><span class="sxs-lookup"><span data-stu-id="4ec59-169">long</span></span> | <span data-ttu-id="4ec59-170">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="4ec59-170">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="4ec59-171">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ec59-171">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="4ec59-172">string</span><span class="sxs-lookup"><span data-stu-id="4ec59-172">string</span></span> | <span data-ttu-id="4ec59-173">ブラウザーの動作を分離するために Application Guard によって使用される仮想化コンテナーの識別子</span><span class="sxs-lookup"><span data-stu-id="4ec59-173">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4ec59-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ec59-174">Related topics</span></span>
- [<span data-ttu-id="4ec59-175">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="4ec59-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4ec59-176">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="4ec59-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4ec59-177">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="4ec59-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4ec59-178">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="4ec59-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4ec59-179">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="4ec59-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4ec59-180">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="4ec59-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
