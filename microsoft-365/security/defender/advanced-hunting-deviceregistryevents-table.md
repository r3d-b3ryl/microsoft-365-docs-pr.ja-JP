---
title: 高度な検索スキーマの DeviceRegistryEvents テーブル
description: 高度なハンティング スキーマの DeviceRegistryEvents テーブルからクエリできるレジストリ イベントについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、registryevents、レジストリ、DeviceRegistryEvents、キー、サブキー、値
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
ms.openlocfilehash: b9bb95f8220327e3be7cc2598f2f49fd868d1b89
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063467"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="abada-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="abada-104">DeviceRegistryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="abada-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="abada-105">**Applies to:**</span></span>
- <span data-ttu-id="abada-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="abada-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="abada-107">高度 `DeviceRegistryEvents` な検索スキーマ [の表](advanced-hunting-overview.md) には、レジストリ エントリの作成と変更に関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="abada-107">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="abada-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="abada-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="abada-109">テーブルでサポートされるイベントの種類 (値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ参照 `ActionType` を使用します。</span><span class="sxs-lookup"><span data-stu-id="abada-109">For detailed information about the events types (`ActionType` values) supported by a table, use the  built-in schema reference available in the security center.</span></span>

<span data-ttu-id="abada-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abada-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="abada-111">列名</span><span class="sxs-lookup"><span data-stu-id="abada-111">Column name</span></span> | <span data-ttu-id="abada-112">データ型</span><span class="sxs-lookup"><span data-stu-id="abada-112">Data type</span></span> | <span data-ttu-id="abada-113">説明</span><span class="sxs-lookup"><span data-stu-id="abada-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="abada-114">日付型</span><span class="sxs-lookup"><span data-stu-id="abada-114">datetime</span></span> | <span data-ttu-id="abada-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="abada-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="abada-116">string</span><span class="sxs-lookup"><span data-stu-id="abada-116">string</span></span> | <span data-ttu-id="abada-117">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="abada-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="abada-118">string</span><span class="sxs-lookup"><span data-stu-id="abada-118">string</span></span> | <span data-ttu-id="abada-119">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="abada-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="abada-120">string</span><span class="sxs-lookup"><span data-stu-id="abada-120">string</span></span> | <span data-ttu-id="abada-121">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="abada-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="abada-122">詳細については [、ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abada-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RegistryKey` | <span data-ttu-id="abada-123">string</span><span class="sxs-lookup"><span data-stu-id="abada-123">string</span></span> | <span data-ttu-id="abada-124">記録されたアクションが適用されたレジストリ キー</span><span class="sxs-lookup"><span data-stu-id="abada-124">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="abada-125">string</span><span class="sxs-lookup"><span data-stu-id="abada-125">string</span></span> | <span data-ttu-id="abada-126">記録されたアクションが適用されたレジストリ値のデータ型 (バイナリや文字列など)</span><span class="sxs-lookup"><span data-stu-id="abada-126">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="abada-127">string</span><span class="sxs-lookup"><span data-stu-id="abada-127">string</span></span> | <span data-ttu-id="abada-128">記録されたアクションが適用されたレジストリ値の名前</span><span class="sxs-lookup"><span data-stu-id="abada-128">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="abada-129">string</span><span class="sxs-lookup"><span data-stu-id="abada-129">string</span></span> | <span data-ttu-id="abada-130">記録されたアクションが適用されたレジストリ値のデータ</span><span class="sxs-lookup"><span data-stu-id="abada-130">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryKey` | <span data-ttu-id="abada-131">string</span><span class="sxs-lookup"><span data-stu-id="abada-131">string</span></span> | <span data-ttu-id="abada-132">変更前のレジストリ値の元のレジストリ キー</span><span class="sxs-lookup"><span data-stu-id="abada-132">Original registry key of the registry value before it was modified</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="abada-133">string</span><span class="sxs-lookup"><span data-stu-id="abada-133">string</span></span> | <span data-ttu-id="abada-134">変更前のレジストリ値の元の名前</span><span class="sxs-lookup"><span data-stu-id="abada-134">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="abada-135">string</span><span class="sxs-lookup"><span data-stu-id="abada-135">string</span></span> | <span data-ttu-id="abada-136">変更前のレジストリ値の元のデータ</span><span class="sxs-lookup"><span data-stu-id="abada-136">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="abada-137">string</span><span class="sxs-lookup"><span data-stu-id="abada-137">string</span></span> | <span data-ttu-id="abada-138">イベントを担当するプロセスを実行したアカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="abada-138">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="abada-139">string</span><span class="sxs-lookup"><span data-stu-id="abada-139">string</span></span> | <span data-ttu-id="abada-140">イベントを担当するプロセスを実行したアカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="abada-140">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="abada-141">string</span><span class="sxs-lookup"><span data-stu-id="abada-141">string</span></span> | <span data-ttu-id="abada-142">イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="abada-142">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountUpn` | <span data-ttu-id="abada-143">string</span><span class="sxs-lookup"><span data-stu-id="abada-143">string</span></span> | <span data-ttu-id="abada-144">イベントを担当するプロセスを実行したアカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="abada-144">User principal name (UPN) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountObjectId` | <span data-ttu-id="abada-145">string</span><span class="sxs-lookup"><span data-stu-id="abada-145">string</span></span> | <span data-ttu-id="abada-146">Azure ADを実行したユーザー アカウントのオブジェクト ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="abada-146">Azure AD object ID of the user account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="abada-147">string</span><span class="sxs-lookup"><span data-stu-id="abada-147">string</span></span> | <span data-ttu-id="abada-148">イベントを開始したプロセス (イメージ ファイル) の SHA-1</span><span class="sxs-lookup"><span data-stu-id="abada-148">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="abada-149">string</span><span class="sxs-lookup"><span data-stu-id="abada-149">string</span></span> | <span data-ttu-id="abada-150">イベントを開始したプロセス (イメージ ファイル) の SHA-256。</span><span class="sxs-lookup"><span data-stu-id="abada-150">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="abada-151">このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="abada-151">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="abada-152">文字列型</span><span class="sxs-lookup"><span data-stu-id="abada-152">string</span></span> | <span data-ttu-id="abada-153">イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="abada-153">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="abada-154">string</span><span class="sxs-lookup"><span data-stu-id="abada-154">string</span></span> | <span data-ttu-id="abada-155">イベントを開始したプロセスの名前</span><span class="sxs-lookup"><span data-stu-id="abada-155">Name of the process that initiated the event</span></span> |
| `InitiatingProcessFileSize` | <span data-ttu-id="abada-156">long</span><span class="sxs-lookup"><span data-stu-id="abada-156">long</span></span> | <span data-ttu-id="abada-157">イベントの処理を実行したファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="abada-157">Size of the file that ran the process responsible for the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="abada-158">int</span><span class="sxs-lookup"><span data-stu-id="abada-158">int</span></span> | <span data-ttu-id="abada-159">イベントを開始したプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="abada-159">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="abada-160">string</span><span class="sxs-lookup"><span data-stu-id="abada-160">string</span></span> | <span data-ttu-id="abada-161">イベントを開始したプロセスの実行に使用されるコマンド ライン</span><span class="sxs-lookup"><span data-stu-id="abada-161">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="abada-162">日付型</span><span class="sxs-lookup"><span data-stu-id="abada-162">datetime</span></span> | <span data-ttu-id="abada-163">イベントを開始したプロセスが開始された日時</span><span class="sxs-lookup"><span data-stu-id="abada-163">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="abada-164">string</span><span class="sxs-lookup"><span data-stu-id="abada-164">string</span></span> | <span data-ttu-id="abada-165">イベントを開始したプロセス (イメージ ファイル) を含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="abada-165">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="abada-166">int</span><span class="sxs-lookup"><span data-stu-id="abada-166">int</span></span> | <span data-ttu-id="abada-167">イベントを担当するプロセスを生成した親プロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="abada-167">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="abada-168">string</span><span class="sxs-lookup"><span data-stu-id="abada-168">string</span></span> | <span data-ttu-id="abada-169">イベントを担当するプロセスを生成した親プロセスの名前</span><span class="sxs-lookup"><span data-stu-id="abada-169">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="abada-170">日付型</span><span class="sxs-lookup"><span data-stu-id="abada-170">datetime</span></span> | <span data-ttu-id="abada-171">イベントを担当するプロセスの親が開始された日時</span><span class="sxs-lookup"><span data-stu-id="abada-171">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="abada-172">string</span><span class="sxs-lookup"><span data-stu-id="abada-172">string</span></span> | <span data-ttu-id="abada-173">イベントを開始したプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="abada-173">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="abada-174">Windows は、インターネットダウンロードから起動された場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="abada-174">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="abada-175">これらの整合性レベルは、リソースへのアクセス許可に影響を与えます</span><span class="sxs-lookup"><span data-stu-id="abada-175">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="abada-176">string</span><span class="sxs-lookup"><span data-stu-id="abada-176">string</span></span> | <span data-ttu-id="abada-177">イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権昇格の有無を示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="abada-177">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="abada-178">long</span><span class="sxs-lookup"><span data-stu-id="abada-178">long</span></span> | <span data-ttu-id="abada-179">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="abada-179">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="abada-180">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abada-180">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="abada-181">string</span><span class="sxs-lookup"><span data-stu-id="abada-181">string</span></span> | <span data-ttu-id="abada-182">ブラウザーのアクティビティを分離するために Application Guard が使用する仮想化コンテナーの識別子</span><span class="sxs-lookup"><span data-stu-id="abada-182">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="abada-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="abada-183">Related topics</span></span>
- [<span data-ttu-id="abada-184">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="abada-184">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="abada-185">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="abada-185">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="abada-186">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="abada-186">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="abada-187">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="abada-187">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="abada-188">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="abada-188">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="abada-189">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="abada-189">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
