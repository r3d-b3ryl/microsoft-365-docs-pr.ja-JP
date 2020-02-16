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
ms.openlocfilehash: 5d43584ed9af9a0ac6154d593f4517d0a4152023
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087966"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="22ef9-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="22ef9-104">DeviceRegistryEvents</span></span>

<span data-ttu-id="22ef9-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="22ef9-105">**Applies to:**</span></span>
- <span data-ttu-id="22ef9-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="22ef9-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="22ef9-107">`DeviceRegistryEvents` [高度な](advanced-hunting-overview.md)検索スキーマの表には、レジストリエントリの作成と変更に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="22ef9-107">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="22ef9-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="22ef9-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="22ef9-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22ef9-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="22ef9-110">列名</span><span class="sxs-lookup"><span data-stu-id="22ef9-110">Column name</span></span> | <span data-ttu-id="22ef9-111">データ型</span><span class="sxs-lookup"><span data-stu-id="22ef9-111">Data type</span></span> | <span data-ttu-id="22ef9-112">説明</span><span class="sxs-lookup"><span data-stu-id="22ef9-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="22ef9-113">日付型</span><span class="sxs-lookup"><span data-stu-id="22ef9-113">datetime</span></span> | <span data-ttu-id="22ef9-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="22ef9-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="22ef9-115">文字列</span><span class="sxs-lookup"><span data-stu-id="22ef9-115">string</span></span> | <span data-ttu-id="22ef9-116">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="22ef9-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="22ef9-117">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-117">string</span></span> | <span data-ttu-id="22ef9-118">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="22ef9-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="22ef9-119">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-119">string</span></span> | <span data-ttu-id="22ef9-120">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="22ef9-120">Type of activity that triggered the event</span></span> |
| `RegistryKey` | <span data-ttu-id="22ef9-121">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-121">string</span></span> | <span data-ttu-id="22ef9-122">記録済みのアクションが適用されたレジストリキー</span><span class="sxs-lookup"><span data-stu-id="22ef9-122">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="22ef9-123">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-123">string</span></span> | <span data-ttu-id="22ef9-124">記録された操作が適用されたレジストリ値の、バイナリまたは文字列などのデータ型</span><span class="sxs-lookup"><span data-stu-id="22ef9-124">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="22ef9-125">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-125">string</span></span> | <span data-ttu-id="22ef9-126">記録されたアクションが適用されたレジストリ値の名前</span><span class="sxs-lookup"><span data-stu-id="22ef9-126">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="22ef9-127">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-127">string</span></span> | <span data-ttu-id="22ef9-128">記録された操作が適用されたレジストリ値のデータ</span><span class="sxs-lookup"><span data-stu-id="22ef9-128">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="22ef9-129">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-129">string</span></span> | <span data-ttu-id="22ef9-130">変更される前のレジストリ値の元の名前</span><span class="sxs-lookup"><span data-stu-id="22ef9-130">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="22ef9-131">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-131">string</span></span> | <span data-ttu-id="22ef9-132">変更される前のレジストリ値の元のデータ</span><span class="sxs-lookup"><span data-stu-id="22ef9-132">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="22ef9-133">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-133">string</span></span> | <span data-ttu-id="22ef9-134">イベントを担当するプロセスを実行したアカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="22ef9-134">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="22ef9-135">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-135">string</span></span> | <span data-ttu-id="22ef9-136">イベントを担当するプロセスを実行したアカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="22ef9-136">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="22ef9-137">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-137">string</span></span> | <span data-ttu-id="22ef9-138">イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="22ef9-138">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="22ef9-139">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-139">string</span></span> | <span data-ttu-id="22ef9-140">イベントを開始したプロセス (画像ファイル) の SHA-1</span><span class="sxs-lookup"><span data-stu-id="22ef9-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="22ef9-141">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-141">string</span></span> | <span data-ttu-id="22ef9-142">イベントを開始したプロセス (画像ファイル) の MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="22ef9-142">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="22ef9-143">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-143">string</span></span> | <span data-ttu-id="22ef9-144">イベントを開始したプロセスの名前</span><span class="sxs-lookup"><span data-stu-id="22ef9-144">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="22ef9-145">int</span><span class="sxs-lookup"><span data-stu-id="22ef9-145">int</span></span> | <span data-ttu-id="22ef9-146">イベントを開始したプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="22ef9-146">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="22ef9-147">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-147">string</span></span> | <span data-ttu-id="22ef9-148">イベントを開始したプロセスを実行するために使用されるコマンドライン</span><span class="sxs-lookup"><span data-stu-id="22ef9-148">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="22ef9-149">日付型</span><span class="sxs-lookup"><span data-stu-id="22ef9-149">datetime</span></span> | <span data-ttu-id="22ef9-150">イベントを開始したプロセスが開始された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="22ef9-150">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="22ef9-151">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-151">string</span></span> | <span data-ttu-id="22ef9-152">イベントを開始したプロセス (画像ファイル) を含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="22ef9-152">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="22ef9-153">int</span><span class="sxs-lookup"><span data-stu-id="22ef9-153">int</span></span> | <span data-ttu-id="22ef9-154">イベントを担当するプロセスを発生させる親プロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="22ef9-154">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="22ef9-155">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-155">string</span></span> | <span data-ttu-id="22ef9-156">イベントを処理するプロセスを生成した親プロセスの名前</span><span class="sxs-lookup"><span data-stu-id="22ef9-156">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="22ef9-157">日付型</span><span class="sxs-lookup"><span data-stu-id="22ef9-157">datetime</span></span> | <span data-ttu-id="22ef9-158">イベントを担当するプロセスの親が開始された日時</span><span class="sxs-lookup"><span data-stu-id="22ef9-158">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="22ef9-159">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-159">string</span></span> | <span data-ttu-id="22ef9-160">イベントを開始したプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="22ef9-160">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="22ef9-161">Windows は、インターネットダウンロードから起動されたかどうかなど、特定の特性に基づいてプロセスに整合性レベルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="22ef9-161">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="22ef9-162">これらの整合性レベルは、リソースへのアクセス許可に影響します。</span><span class="sxs-lookup"><span data-stu-id="22ef9-162">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="22ef9-163">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-163">string</span></span> | <span data-ttu-id="22ef9-164">イベントを開始したプロセスに適用されたユーザーアクセス制御 (UAC) 特権昇格が存在するかどうかを示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="22ef9-164">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="22ef9-165">long</span><span class="sxs-lookup"><span data-stu-id="22ef9-165">long</span></span> | <span data-ttu-id="22ef9-166">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="22ef9-166">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="22ef9-167">一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22ef9-167">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="22ef9-168">string</span><span class="sxs-lookup"><span data-stu-id="22ef9-168">string</span></span> | <span data-ttu-id="22ef9-169">Application Guard がブラウザーのアクティビティを分離するために使用する仮想化されたコンテナーの識別子</span><span class="sxs-lookup"><span data-stu-id="22ef9-169">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="22ef9-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="22ef9-170">Related topics</span></span>
- [<span data-ttu-id="22ef9-171">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="22ef9-171">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="22ef9-172">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="22ef9-172">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="22ef9-173">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="22ef9-173">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="22ef9-174">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="22ef9-174">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="22ef9-175">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="22ef9-175">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="22ef9-176">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="22ef9-176">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
