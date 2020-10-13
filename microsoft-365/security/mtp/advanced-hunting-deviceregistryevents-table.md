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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 4d70176e7dbbb6963565c0b6c38699cb09b5cd9b
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429901"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="0c11d-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="0c11d-104">DeviceRegistryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0c11d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="0c11d-105">**Applies to:**</span></span>
- <span data-ttu-id="0c11d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0c11d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0c11d-107">`DeviceRegistryEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、レジストリエントリの作成と変更に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0c11d-107">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="0c11d-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="0c11d-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="0c11d-109">テーブルでサポートされているイベントの種類 (値) の詳細については、 `ActionType` セキュリティセンターで利用可能な [組み込みスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="0c11d-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="0c11d-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c11d-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0c11d-111">列名</span><span class="sxs-lookup"><span data-stu-id="0c11d-111">Column name</span></span> | <span data-ttu-id="0c11d-112">データ型</span><span class="sxs-lookup"><span data-stu-id="0c11d-112">Data type</span></span> | <span data-ttu-id="0c11d-113">説明</span><span class="sxs-lookup"><span data-stu-id="0c11d-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0c11d-114">日付型</span><span class="sxs-lookup"><span data-stu-id="0c11d-114">datetime</span></span> | <span data-ttu-id="0c11d-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="0c11d-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="0c11d-116">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-116">string</span></span> | <span data-ttu-id="0c11d-117">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="0c11d-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="0c11d-118">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-118">string</span></span> | <span data-ttu-id="0c11d-119">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="0c11d-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="0c11d-120">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-120">string</span></span> | <span data-ttu-id="0c11d-121">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="0c11d-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="0c11d-122">詳細については、 [ポータル内のスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c11d-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RegistryKey` | <span data-ttu-id="0c11d-123">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-123">string</span></span> | <span data-ttu-id="0c11d-124">記録済みのアクションが適用されたレジストリキー</span><span class="sxs-lookup"><span data-stu-id="0c11d-124">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="0c11d-125">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-125">string</span></span> | <span data-ttu-id="0c11d-126">記録された操作が適用されたレジストリ値の、バイナリまたは文字列などのデータ型</span><span class="sxs-lookup"><span data-stu-id="0c11d-126">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="0c11d-127">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-127">string</span></span> | <span data-ttu-id="0c11d-128">記録されたアクションが適用されたレジストリ値の名前</span><span class="sxs-lookup"><span data-stu-id="0c11d-128">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="0c11d-129">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-129">string</span></span> | <span data-ttu-id="0c11d-130">記録された操作が適用されたレジストリ値のデータ</span><span class="sxs-lookup"><span data-stu-id="0c11d-130">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="0c11d-131">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-131">string</span></span> | <span data-ttu-id="0c11d-132">変更される前のレジストリ値の元の名前</span><span class="sxs-lookup"><span data-stu-id="0c11d-132">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="0c11d-133">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-133">string</span></span> | <span data-ttu-id="0c11d-134">変更される前のレジストリ値の元のデータ</span><span class="sxs-lookup"><span data-stu-id="0c11d-134">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="0c11d-135">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-135">string</span></span> | <span data-ttu-id="0c11d-136">イベントを担当するプロセスを実行したアカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="0c11d-136">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="0c11d-137">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-137">string</span></span> | <span data-ttu-id="0c11d-138">イベントを担当するプロセスを実行したアカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="0c11d-138">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="0c11d-139">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-139">string</span></span> | <span data-ttu-id="0c11d-140">イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="0c11d-140">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="0c11d-141">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-141">string</span></span> | <span data-ttu-id="0c11d-142">イベントを開始したプロセス (画像ファイル) の SHA-1</span><span class="sxs-lookup"><span data-stu-id="0c11d-142">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="0c11d-143">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-143">string</span></span> | <span data-ttu-id="0c11d-144">イベントを開始したプロセス (イメージファイル) の256。</span><span class="sxs-lookup"><span data-stu-id="0c11d-144">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="0c11d-145">このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="0c11d-145">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="0c11d-146">文字列型</span><span class="sxs-lookup"><span data-stu-id="0c11d-146">string</span></span> | <span data-ttu-id="0c11d-147">イベントを開始したプロセス (画像ファイル) の MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="0c11d-147">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="0c11d-148">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-148">string</span></span> | <span data-ttu-id="0c11d-149">イベントを開始したプロセスの名前</span><span class="sxs-lookup"><span data-stu-id="0c11d-149">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="0c11d-150">int</span><span class="sxs-lookup"><span data-stu-id="0c11d-150">int</span></span> | <span data-ttu-id="0c11d-151">イベントを開始したプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="0c11d-151">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="0c11d-152">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-152">string</span></span> | <span data-ttu-id="0c11d-153">イベントを開始したプロセスを実行するために使用されるコマンドライン</span><span class="sxs-lookup"><span data-stu-id="0c11d-153">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="0c11d-154">日付型</span><span class="sxs-lookup"><span data-stu-id="0c11d-154">datetime</span></span> | <span data-ttu-id="0c11d-155">イベントを開始したプロセスが開始された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="0c11d-155">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="0c11d-156">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-156">string</span></span> | <span data-ttu-id="0c11d-157">イベントを開始したプロセス (画像ファイル) を含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="0c11d-157">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="0c11d-158">int</span><span class="sxs-lookup"><span data-stu-id="0c11d-158">int</span></span> | <span data-ttu-id="0c11d-159">イベントを担当するプロセスを発生させる親プロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="0c11d-159">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="0c11d-160">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-160">string</span></span> | <span data-ttu-id="0c11d-161">イベントを処理するプロセスを生成した親プロセスの名前</span><span class="sxs-lookup"><span data-stu-id="0c11d-161">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="0c11d-162">日付型</span><span class="sxs-lookup"><span data-stu-id="0c11d-162">datetime</span></span> | <span data-ttu-id="0c11d-163">イベントを担当するプロセスの親が開始された日時</span><span class="sxs-lookup"><span data-stu-id="0c11d-163">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="0c11d-164">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-164">string</span></span> | <span data-ttu-id="0c11d-165">イベントを開始したプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="0c11d-165">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="0c11d-166">Windows は、インターネットダウンロードから起動されたかどうかなど、特定の特性に基づいてプロセスに整合性レベルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0c11d-166">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="0c11d-167">これらの整合性レベルは、リソースへのアクセス許可に影響します。</span><span class="sxs-lookup"><span data-stu-id="0c11d-167">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="0c11d-168">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-168">string</span></span> | <span data-ttu-id="0c11d-169">イベントを開始したプロセスに適用されたユーザーアクセス制御 (UAC) 特権昇格が存在するかどうかを示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="0c11d-169">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="0c11d-170">long</span><span class="sxs-lookup"><span data-stu-id="0c11d-170">long</span></span> | <span data-ttu-id="0c11d-171">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="0c11d-171">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="0c11d-172">一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c11d-172">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="0c11d-173">string</span><span class="sxs-lookup"><span data-stu-id="0c11d-173">string</span></span> | <span data-ttu-id="0c11d-174">Application Guard がブラウザーのアクティビティを分離するために使用する仮想化されたコンテナーの識別子</span><span class="sxs-lookup"><span data-stu-id="0c11d-174">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0c11d-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c11d-175">Related topics</span></span>
- [<span data-ttu-id="0c11d-176">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="0c11d-176">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0c11d-177">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="0c11d-177">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0c11d-178">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="0c11d-178">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0c11d-179">デバイス、メール、アプリ、ID 間での捜索</span><span class="sxs-lookup"><span data-stu-id="0c11d-179">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0c11d-180">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="0c11d-180">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0c11d-181">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="0c11d-181">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
