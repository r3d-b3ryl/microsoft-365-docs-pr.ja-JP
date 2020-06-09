---
title: 高度な検索スキーマの DeviceRegistryEvents テーブル
description: 高度な検索スキーマの DeviceRegistryEvents テーブルからクエリを実行できるレジストリイベントについて説明します。
keywords: 高度な検索、脅威の探し、サイバーの脅威の検出、microsoft の脅威の防止、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、registryevents、registry、DeviceRegistryEvents、key、subkey、value
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
ms.openlocfilehash: 610cdebaf4e010c78d7356286901fb18c5d740d1
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616492"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="ab561-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="ab561-104">DeviceRegistryEvents</span></span>

<span data-ttu-id="ab561-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ab561-105">**Applies to:**</span></span>
- <span data-ttu-id="ab561-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ab561-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="ab561-107">`DeviceRegistryEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、レジストリエントリの作成と変更に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab561-107">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="ab561-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab561-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="ab561-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab561-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ab561-110">列名</span><span class="sxs-lookup"><span data-stu-id="ab561-110">Column name</span></span> | <span data-ttu-id="ab561-111">データ型</span><span class="sxs-lookup"><span data-stu-id="ab561-111">Data type</span></span> | <span data-ttu-id="ab561-112">説明</span><span class="sxs-lookup"><span data-stu-id="ab561-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ab561-113">日付型</span><span class="sxs-lookup"><span data-stu-id="ab561-113">datetime</span></span> | <span data-ttu-id="ab561-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="ab561-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="ab561-115">文字列</span><span class="sxs-lookup"><span data-stu-id="ab561-115">string</span></span> | <span data-ttu-id="ab561-116">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="ab561-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="ab561-117">string</span><span class="sxs-lookup"><span data-stu-id="ab561-117">string</span></span> | <span data-ttu-id="ab561-118">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="ab561-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="ab561-119">string</span><span class="sxs-lookup"><span data-stu-id="ab561-119">string</span></span> | <span data-ttu-id="ab561-120">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="ab561-120">Type of activity that triggered the event</span></span> |
| `RegistryKey` | <span data-ttu-id="ab561-121">string</span><span class="sxs-lookup"><span data-stu-id="ab561-121">string</span></span> | <span data-ttu-id="ab561-122">記録済みのアクションが適用されたレジストリキー</span><span class="sxs-lookup"><span data-stu-id="ab561-122">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="ab561-123">string</span><span class="sxs-lookup"><span data-stu-id="ab561-123">string</span></span> | <span data-ttu-id="ab561-124">記録された操作が適用されたレジストリ値の、バイナリまたは文字列などのデータ型</span><span class="sxs-lookup"><span data-stu-id="ab561-124">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="ab561-125">string</span><span class="sxs-lookup"><span data-stu-id="ab561-125">string</span></span> | <span data-ttu-id="ab561-126">記録されたアクションが適用されたレジストリ値の名前</span><span class="sxs-lookup"><span data-stu-id="ab561-126">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="ab561-127">string</span><span class="sxs-lookup"><span data-stu-id="ab561-127">string</span></span> | <span data-ttu-id="ab561-128">記録された操作が適用されたレジストリ値のデータ</span><span class="sxs-lookup"><span data-stu-id="ab561-128">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="ab561-129">string</span><span class="sxs-lookup"><span data-stu-id="ab561-129">string</span></span> | <span data-ttu-id="ab561-130">変更される前のレジストリ値の元の名前</span><span class="sxs-lookup"><span data-stu-id="ab561-130">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="ab561-131">string</span><span class="sxs-lookup"><span data-stu-id="ab561-131">string</span></span> | <span data-ttu-id="ab561-132">変更される前のレジストリ値の元のデータ</span><span class="sxs-lookup"><span data-stu-id="ab561-132">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="ab561-133">string</span><span class="sxs-lookup"><span data-stu-id="ab561-133">string</span></span> | <span data-ttu-id="ab561-134">イベントを担当するプロセスを実行したアカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="ab561-134">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="ab561-135">string</span><span class="sxs-lookup"><span data-stu-id="ab561-135">string</span></span> | <span data-ttu-id="ab561-136">イベントを担当するプロセスを実行したアカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="ab561-136">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="ab561-137">string</span><span class="sxs-lookup"><span data-stu-id="ab561-137">string</span></span> | <span data-ttu-id="ab561-138">イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="ab561-138">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="ab561-139">string</span><span class="sxs-lookup"><span data-stu-id="ab561-139">string</span></span> | <span data-ttu-id="ab561-140">イベントを開始したプロセス (画像ファイル) の SHA-1</span><span class="sxs-lookup"><span data-stu-id="ab561-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="ab561-141">string</span><span class="sxs-lookup"><span data-stu-id="ab561-141">string</span></span> | <span data-ttu-id="ab561-142">イベントを開始したプロセス (イメージファイル) の256。</span><span class="sxs-lookup"><span data-stu-id="ab561-142">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="ab561-143">このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="ab561-143">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="ab561-144">文字列型</span><span class="sxs-lookup"><span data-stu-id="ab561-144">string</span></span> | <span data-ttu-id="ab561-145">イベントを開始したプロセス (画像ファイル) の MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="ab561-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="ab561-146">string</span><span class="sxs-lookup"><span data-stu-id="ab561-146">string</span></span> | <span data-ttu-id="ab561-147">イベントを開始したプロセスの名前</span><span class="sxs-lookup"><span data-stu-id="ab561-147">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="ab561-148">int</span><span class="sxs-lookup"><span data-stu-id="ab561-148">int</span></span> | <span data-ttu-id="ab561-149">イベントを開始したプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="ab561-149">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="ab561-150">string</span><span class="sxs-lookup"><span data-stu-id="ab561-150">string</span></span> | <span data-ttu-id="ab561-151">イベントを開始したプロセスを実行するために使用されるコマンドライン</span><span class="sxs-lookup"><span data-stu-id="ab561-151">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="ab561-152">日付型</span><span class="sxs-lookup"><span data-stu-id="ab561-152">datetime</span></span> | <span data-ttu-id="ab561-153">イベントを開始したプロセスが開始された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="ab561-153">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="ab561-154">string</span><span class="sxs-lookup"><span data-stu-id="ab561-154">string</span></span> | <span data-ttu-id="ab561-155">イベントを開始したプロセス (画像ファイル) を含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="ab561-155">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="ab561-156">int</span><span class="sxs-lookup"><span data-stu-id="ab561-156">int</span></span> | <span data-ttu-id="ab561-157">イベントを担当するプロセスを発生させる親プロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="ab561-157">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="ab561-158">string</span><span class="sxs-lookup"><span data-stu-id="ab561-158">string</span></span> | <span data-ttu-id="ab561-159">イベントを処理するプロセスを生成した親プロセスの名前</span><span class="sxs-lookup"><span data-stu-id="ab561-159">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="ab561-160">日付型</span><span class="sxs-lookup"><span data-stu-id="ab561-160">datetime</span></span> | <span data-ttu-id="ab561-161">イベントを担当するプロセスの親が開始された日時</span><span class="sxs-lookup"><span data-stu-id="ab561-161">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="ab561-162">string</span><span class="sxs-lookup"><span data-stu-id="ab561-162">string</span></span> | <span data-ttu-id="ab561-163">イベントを開始したプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="ab561-163">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="ab561-164">Windows は、インターネットダウンロードから起動されたかどうかなど、特定の特性に基づいてプロセスに整合性レベルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ab561-164">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="ab561-165">これらの整合性レベルは、リソースへのアクセス許可に影響します。</span><span class="sxs-lookup"><span data-stu-id="ab561-165">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="ab561-166">string</span><span class="sxs-lookup"><span data-stu-id="ab561-166">string</span></span> | <span data-ttu-id="ab561-167">イベントを開始したプロセスに適用されたユーザーアクセス制御 (UAC) 特権昇格が存在するかどうかを示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="ab561-167">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="ab561-168">long</span><span class="sxs-lookup"><span data-stu-id="ab561-168">long</span></span> | <span data-ttu-id="ab561-169">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="ab561-169">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="ab561-170">一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab561-170">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="ab561-171">string</span><span class="sxs-lookup"><span data-stu-id="ab561-171">string</span></span> | <span data-ttu-id="ab561-172">Application Guard がブラウザーのアクティビティを分離するために使用する仮想化されたコンテナーの識別子</span><span class="sxs-lookup"><span data-stu-id="ab561-172">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ab561-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab561-173">Related topics</span></span>
- [<span data-ttu-id="ab561-174">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="ab561-174">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ab561-175">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="ab561-175">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ab561-176">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="ab561-176">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ab561-177">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="ab561-177">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ab561-178">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="ab561-178">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ab561-179">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="ab561-179">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
