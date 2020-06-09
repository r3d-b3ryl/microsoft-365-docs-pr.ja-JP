---
title: 高度な検索スキーマの DeviceImageLoadEvents テーブル
description: 高度な検索スキーマの DeviceImageLoadEvents テーブルでの DLL 読み込みイベントについて説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検出、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、imageloadevents、DeviceImageLoadEvents、DLL の読み込み、ライブラリ、ファイルイメージ
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
ms.openlocfilehash: 98aac3d231e2c8630cb4721ee8012054ab90feef
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617142"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="67766-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="67766-104">DeviceImageLoadEvents</span></span>

<span data-ttu-id="67766-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="67766-105">**Applies to:**</span></span>
- <span data-ttu-id="67766-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="67766-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="67766-107">`DeviceImageLoadEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、DLL 読み込みイベントに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67766-107">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="67766-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="67766-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="67766-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67766-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="67766-110">列名</span><span class="sxs-lookup"><span data-stu-id="67766-110">Column name</span></span> | <span data-ttu-id="67766-111">データ型</span><span class="sxs-lookup"><span data-stu-id="67766-111">Data type</span></span> | <span data-ttu-id="67766-112">説明</span><span class="sxs-lookup"><span data-stu-id="67766-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="67766-113">日付型</span><span class="sxs-lookup"><span data-stu-id="67766-113">datetime</span></span> | <span data-ttu-id="67766-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="67766-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="67766-115">string</span><span class="sxs-lookup"><span data-stu-id="67766-115">string</span></span> | <span data-ttu-id="67766-116">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="67766-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="67766-117">string</span><span class="sxs-lookup"><span data-stu-id="67766-117">string</span></span> | <span data-ttu-id="67766-118">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="67766-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="67766-119">string</span><span class="sxs-lookup"><span data-stu-id="67766-119">string</span></span> | <span data-ttu-id="67766-120">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="67766-120">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="67766-121">string</span><span class="sxs-lookup"><span data-stu-id="67766-121">string</span></span> | <span data-ttu-id="67766-122">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="67766-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="67766-123">string</span><span class="sxs-lookup"><span data-stu-id="67766-123">string</span></span> | <span data-ttu-id="67766-124">記録されたアクションが適用されたファイルを含むフォルダ</span><span class="sxs-lookup"><span data-stu-id="67766-124">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="67766-125">文字列</span><span class="sxs-lookup"><span data-stu-id="67766-125">string</span></span> | <span data-ttu-id="67766-126">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="67766-126">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="67766-127">文字列</span><span class="sxs-lookup"><span data-stu-id="67766-127">string</span></span> | <span data-ttu-id="67766-128">記録されたアクションが適用されたファイルの SHA-256</span><span class="sxs-lookup"><span data-stu-id="67766-128">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="67766-129">このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="67766-129">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `MD5` | <span data-ttu-id="67766-130">文字列型</span><span class="sxs-lookup"><span data-stu-id="67766-130">string</span></span> | <span data-ttu-id="67766-131">記録されたアクションが適用されたファイルの MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="67766-131">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="67766-132">string</span><span class="sxs-lookup"><span data-stu-id="67766-132">string</span></span> | <span data-ttu-id="67766-133">イベントを担当するプロセスを実行したアカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="67766-133">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="67766-134">string</span><span class="sxs-lookup"><span data-stu-id="67766-134">string</span></span> | <span data-ttu-id="67766-135">イベントを担当するプロセスを実行したアカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="67766-135">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="67766-136">string</span><span class="sxs-lookup"><span data-stu-id="67766-136">string</span></span> | <span data-ttu-id="67766-137">イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="67766-137">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="67766-138">string</span><span class="sxs-lookup"><span data-stu-id="67766-138">string</span></span> | <span data-ttu-id="67766-139">イベントを開始したプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="67766-139">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="67766-140">Windows は、インターネットダウンロードから起動されたかどうかなど、特定の特性に基づいてプロセスに整合性レベルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="67766-140">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="67766-141">これらの整合性レベルは、リソースへのアクセス許可に影響します。</span><span class="sxs-lookup"><span data-stu-id="67766-141">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="67766-142">string</span><span class="sxs-lookup"><span data-stu-id="67766-142">string</span></span> | <span data-ttu-id="67766-143">イベントを開始したプロセスに適用されたユーザーアクセス制御 (UAC) 特権昇格が存在するかどうかを示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="67766-143">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="67766-144">string</span><span class="sxs-lookup"><span data-stu-id="67766-144">string</span></span> | <span data-ttu-id="67766-145">イベントを開始したプロセス (画像ファイル) の SHA-1</span><span class="sxs-lookup"><span data-stu-id="67766-145">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="67766-146">string</span><span class="sxs-lookup"><span data-stu-id="67766-146">string</span></span> | <span data-ttu-id="67766-147">イベントを開始したプロセス (イメージファイル) の256。</span><span class="sxs-lookup"><span data-stu-id="67766-147">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="67766-148">このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="67766-148">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="67766-149">文字列型</span><span class="sxs-lookup"><span data-stu-id="67766-149">string</span></span> | <span data-ttu-id="67766-150">イベントを開始したプロセス (画像ファイル) の MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="67766-150">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="67766-151">string</span><span class="sxs-lookup"><span data-stu-id="67766-151">string</span></span> | <span data-ttu-id="67766-152">イベントを開始したプロセスの名前</span><span class="sxs-lookup"><span data-stu-id="67766-152">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="67766-153">int</span><span class="sxs-lookup"><span data-stu-id="67766-153">int</span></span> | <span data-ttu-id="67766-154">イベントを開始したプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="67766-154">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="67766-155">string</span><span class="sxs-lookup"><span data-stu-id="67766-155">string</span></span> | <span data-ttu-id="67766-156">イベントを開始したプロセスを実行するために使用されるコマンドライン</span><span class="sxs-lookup"><span data-stu-id="67766-156">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="67766-157">日付型</span><span class="sxs-lookup"><span data-stu-id="67766-157">datetime</span></span> | <span data-ttu-id="67766-158">イベントを開始したプロセスが開始された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="67766-158">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="67766-159">string</span><span class="sxs-lookup"><span data-stu-id="67766-159">string</span></span> | <span data-ttu-id="67766-160">イベントを開始したプロセス (画像ファイル) を含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="67766-160">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="67766-161">int</span><span class="sxs-lookup"><span data-stu-id="67766-161">int</span></span> | <span data-ttu-id="67766-162">イベントを担当するプロセスを発生させる親プロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="67766-162">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="67766-163">string</span><span class="sxs-lookup"><span data-stu-id="67766-163">string</span></span> | <span data-ttu-id="67766-164">イベントを処理するプロセスを生成した親プロセスの名前</span><span class="sxs-lookup"><span data-stu-id="67766-164">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="67766-165">日付型</span><span class="sxs-lookup"><span data-stu-id="67766-165">datetime</span></span> | <span data-ttu-id="67766-166">イベントを担当するプロセスの親が開始された日時</span><span class="sxs-lookup"><span data-stu-id="67766-166">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="67766-167">long</span><span class="sxs-lookup"><span data-stu-id="67766-167">long</span></span> | <span data-ttu-id="67766-168">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="67766-168">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="67766-169">一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67766-169">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="67766-170">string</span><span class="sxs-lookup"><span data-stu-id="67766-170">string</span></span> | <span data-ttu-id="67766-171">Application Guard がブラウザーのアクティビティを分離するために使用する仮想化されたコンテナーの識別子</span><span class="sxs-lookup"><span data-stu-id="67766-171">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="67766-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="67766-172">Related topics</span></span>
- [<span data-ttu-id="67766-173">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="67766-173">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="67766-174">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="67766-174">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="67766-175">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="67766-175">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="67766-176">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="67766-176">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="67766-177">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="67766-177">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="67766-178">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="67766-178">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
