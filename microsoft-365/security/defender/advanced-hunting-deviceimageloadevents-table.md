---
title: 高度なハンティング スキーマの DeviceImageLoadEvents テーブル
description: 高度なハンティング スキーマの DeviceImageLoadEvents テーブルの DLL 読み込みイベントについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、imageloadevents、DeviceImageLoadEvents、DLL 読み込み、ライブラリ、ファイル イメージ
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
ms.openlocfilehash: c2cc0fe7746c7574b427e3f546050ab4756fb525
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063531"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="04679-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="04679-104">DeviceImageLoadEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="04679-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="04679-105">**Applies to:**</span></span>
- <span data-ttu-id="04679-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04679-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="04679-107">高度 `DeviceImageLoadEvents` な検索スキーマの [表には](advanced-hunting-overview.md) 、DLL 読み込みイベントに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="04679-107">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="04679-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="04679-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="04679-109">テーブルでサポートされるイベントの種類 (値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ参照 `ActionType` を使用します。</span><span class="sxs-lookup"><span data-stu-id="04679-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="04679-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04679-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="04679-111">列名</span><span class="sxs-lookup"><span data-stu-id="04679-111">Column name</span></span> | <span data-ttu-id="04679-112">データ型</span><span class="sxs-lookup"><span data-stu-id="04679-112">Data type</span></span> | <span data-ttu-id="04679-113">説明</span><span class="sxs-lookup"><span data-stu-id="04679-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="04679-114">日付型</span><span class="sxs-lookup"><span data-stu-id="04679-114">datetime</span></span> | <span data-ttu-id="04679-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="04679-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="04679-116">string</span><span class="sxs-lookup"><span data-stu-id="04679-116">string</span></span> | <span data-ttu-id="04679-117">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="04679-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="04679-118">string</span><span class="sxs-lookup"><span data-stu-id="04679-118">string</span></span> | <span data-ttu-id="04679-119">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="04679-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="04679-120">string</span><span class="sxs-lookup"><span data-stu-id="04679-120">string</span></span> | <span data-ttu-id="04679-121">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="04679-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="04679-122">詳細については [、ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04679-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `FileName` | <span data-ttu-id="04679-123">文字列</span><span class="sxs-lookup"><span data-stu-id="04679-123">string</span></span> | <span data-ttu-id="04679-124">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="04679-124">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="04679-125">文字列</span><span class="sxs-lookup"><span data-stu-id="04679-125">string</span></span> | <span data-ttu-id="04679-126">記録されたアクションが適用されたファイルを含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="04679-126">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="04679-127">文字列</span><span class="sxs-lookup"><span data-stu-id="04679-127">string</span></span> | <span data-ttu-id="04679-128">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="04679-128">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="04679-129">文字列</span><span class="sxs-lookup"><span data-stu-id="04679-129">string</span></span> | <span data-ttu-id="04679-130">記録されたアクションが適用されたファイルの SHA-256</span><span class="sxs-lookup"><span data-stu-id="04679-130">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="04679-131">このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="04679-131">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `MD5` | <span data-ttu-id="04679-132">文字列型</span><span class="sxs-lookup"><span data-stu-id="04679-132">string</span></span> | <span data-ttu-id="04679-133">記録されたアクションが適用されたファイルの MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="04679-133">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="04679-134">string</span><span class="sxs-lookup"><span data-stu-id="04679-134">string</span></span> | <span data-ttu-id="04679-135">イベントを担当するプロセスを実行したアカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="04679-135">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="04679-136">string</span><span class="sxs-lookup"><span data-stu-id="04679-136">string</span></span> | <span data-ttu-id="04679-137">イベントを担当するプロセスを実行したアカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="04679-137">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="04679-138">string</span><span class="sxs-lookup"><span data-stu-id="04679-138">string</span></span> | <span data-ttu-id="04679-139">イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="04679-139">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountUpn` | <span data-ttu-id="04679-140">string</span><span class="sxs-lookup"><span data-stu-id="04679-140">string</span></span> | <span data-ttu-id="04679-141">イベントを担当するプロセスを実行したアカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="04679-141">User principal name (UPN) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountObjectId` | <span data-ttu-id="04679-142">string</span><span class="sxs-lookup"><span data-stu-id="04679-142">string</span></span> | <span data-ttu-id="04679-143">Azure ADを実行したユーザー アカウントのオブジェクト ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="04679-143">Azure AD object ID of the user account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="04679-144">string</span><span class="sxs-lookup"><span data-stu-id="04679-144">string</span></span> | <span data-ttu-id="04679-145">イベントを開始したプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="04679-145">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="04679-146">Windows は、インターネットダウンロードから起動された場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="04679-146">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="04679-147">これらの整合性レベルは、リソースへのアクセス許可に影響を与えます</span><span class="sxs-lookup"><span data-stu-id="04679-147">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="04679-148">string</span><span class="sxs-lookup"><span data-stu-id="04679-148">string</span></span> | <span data-ttu-id="04679-149">イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権昇格の有無を示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="04679-149">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="04679-150">string</span><span class="sxs-lookup"><span data-stu-id="04679-150">string</span></span> | <span data-ttu-id="04679-151">イベントを開始したプロセス (イメージ ファイル) の SHA-1</span><span class="sxs-lookup"><span data-stu-id="04679-151">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="04679-152">string</span><span class="sxs-lookup"><span data-stu-id="04679-152">string</span></span> | <span data-ttu-id="04679-153">イベントを開始したプロセス (イメージ ファイル) の SHA-256。</span><span class="sxs-lookup"><span data-stu-id="04679-153">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="04679-154">このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="04679-154">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="04679-155">文字列型</span><span class="sxs-lookup"><span data-stu-id="04679-155">string</span></span> | <span data-ttu-id="04679-156">イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="04679-156">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="04679-157">string</span><span class="sxs-lookup"><span data-stu-id="04679-157">string</span></span> | <span data-ttu-id="04679-158">イベントを開始したプロセスの名前</span><span class="sxs-lookup"><span data-stu-id="04679-158">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="04679-159">int</span><span class="sxs-lookup"><span data-stu-id="04679-159">int</span></span> | <span data-ttu-id="04679-160">イベントを開始したプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="04679-160">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="04679-161">string</span><span class="sxs-lookup"><span data-stu-id="04679-161">string</span></span> | <span data-ttu-id="04679-162">イベントを開始したプロセスの実行に使用されるコマンド ライン</span><span class="sxs-lookup"><span data-stu-id="04679-162">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="04679-163">日付型</span><span class="sxs-lookup"><span data-stu-id="04679-163">datetime</span></span> | <span data-ttu-id="04679-164">イベントを開始したプロセスが開始された日時</span><span class="sxs-lookup"><span data-stu-id="04679-164">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="04679-165">string</span><span class="sxs-lookup"><span data-stu-id="04679-165">string</span></span> | <span data-ttu-id="04679-166">イベントを開始したプロセス (イメージ ファイル) を含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="04679-166">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="04679-167">int</span><span class="sxs-lookup"><span data-stu-id="04679-167">int</span></span> | <span data-ttu-id="04679-168">イベントを担当するプロセスを生成した親プロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="04679-168">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="04679-169">string</span><span class="sxs-lookup"><span data-stu-id="04679-169">string</span></span> | <span data-ttu-id="04679-170">イベントを担当するプロセスを生成した親プロセスの名前</span><span class="sxs-lookup"><span data-stu-id="04679-170">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="04679-171">日付型</span><span class="sxs-lookup"><span data-stu-id="04679-171">datetime</span></span> | <span data-ttu-id="04679-172">イベントを担当するプロセスの親が開始された日時</span><span class="sxs-lookup"><span data-stu-id="04679-172">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="04679-173">long</span><span class="sxs-lookup"><span data-stu-id="04679-173">long</span></span> | <span data-ttu-id="04679-174">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="04679-174">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="04679-175">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04679-175">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="04679-176">string</span><span class="sxs-lookup"><span data-stu-id="04679-176">string</span></span> | <span data-ttu-id="04679-177">ブラウザーのアクティビティを分離するために Application Guard が使用する仮想化コンテナーの識別子</span><span class="sxs-lookup"><span data-stu-id="04679-177">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |
| `InitiatingProcessFileSize` | <span data-ttu-id="04679-178">long</span><span class="sxs-lookup"><span data-stu-id="04679-178">long</span></span> | <span data-ttu-id="04679-179">イベントの処理を実行したファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="04679-179">Size of the file that ran the process responsible for the event</span></span> |
| `FileSize` | <span data-ttu-id="04679-180">long</span><span class="sxs-lookup"><span data-stu-id="04679-180">long</span></span> | <span data-ttu-id="04679-181">ファイルのサイズ (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="04679-181">Size of the file in bytes</span></span> |

## <a name="related-topics"></a><span data-ttu-id="04679-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="04679-182">Related topics</span></span>
- [<span data-ttu-id="04679-183">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="04679-183">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="04679-184">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="04679-184">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="04679-185">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="04679-185">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="04679-186">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="04679-186">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="04679-187">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="04679-187">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="04679-188">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="04679-188">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
