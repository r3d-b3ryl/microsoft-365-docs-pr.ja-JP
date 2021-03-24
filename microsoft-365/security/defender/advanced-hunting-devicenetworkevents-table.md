---
title: 高度なハンティング スキーマの DeviceNetworkEvents テーブル
description: 高度な検索スキーマの DeviceNetworkEvents テーブルからクエリできるネットワーク接続イベントについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、devicenetworkevents、NetworkCommunicationEvents、ネットワーク接続、リモート IP、ローカル IP
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
ms.openlocfilehash: 3e09ace7130e5a58d3c386a57951dbf2ea5f5f2a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063516"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="071bb-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="071bb-104">DeviceNetworkEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="071bb-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="071bb-105">**Applies to:**</span></span>
- <span data-ttu-id="071bb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="071bb-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="071bb-107">高度 `DeviceNetworkEvents` な検索スキーマの [表には](advanced-hunting-overview.md) 、ネットワーク接続と関連イベントに関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="071bb-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="071bb-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="071bb-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="071bb-109">テーブルでサポートされるイベントの種類 (値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ参照 `ActionType` を使用します。</span><span class="sxs-lookup"><span data-stu-id="071bb-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="071bb-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="071bb-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="071bb-111">列名</span><span class="sxs-lookup"><span data-stu-id="071bb-111">Column name</span></span> | <span data-ttu-id="071bb-112">データ型</span><span class="sxs-lookup"><span data-stu-id="071bb-112">Data type</span></span> | <span data-ttu-id="071bb-113">説明</span><span class="sxs-lookup"><span data-stu-id="071bb-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="071bb-114">日付型</span><span class="sxs-lookup"><span data-stu-id="071bb-114">datetime</span></span> | <span data-ttu-id="071bb-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="071bb-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="071bb-116">string</span><span class="sxs-lookup"><span data-stu-id="071bb-116">string</span></span> | <span data-ttu-id="071bb-117">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="071bb-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="071bb-118">string</span><span class="sxs-lookup"><span data-stu-id="071bb-118">string</span></span> | <span data-ttu-id="071bb-119">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="071bb-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="071bb-120">string</span><span class="sxs-lookup"><span data-stu-id="071bb-120">string</span></span> | <span data-ttu-id="071bb-121">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="071bb-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="071bb-122">詳細については [、ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="071bb-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RemoteIP` | <span data-ttu-id="071bb-123">文字列</span><span class="sxs-lookup"><span data-stu-id="071bb-123">string</span></span> | <span data-ttu-id="071bb-124">に接続されていた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="071bb-124">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="071bb-125">int</span><span class="sxs-lookup"><span data-stu-id="071bb-125">int</span></span> | <span data-ttu-id="071bb-126">接続されているリモート デバイスの TCP ポート</span><span class="sxs-lookup"><span data-stu-id="071bb-126">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="071bb-127">文字列</span><span class="sxs-lookup"><span data-stu-id="071bb-127">string</span></span> | <span data-ttu-id="071bb-128">に接続されていた URL または完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="071bb-128">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="071bb-129">文字列</span><span class="sxs-lookup"><span data-stu-id="071bb-129">string</span></span> | <span data-ttu-id="071bb-130">通信中に使用されるローカル コンピューターに割り当てられた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="071bb-130">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="071bb-131">int</span><span class="sxs-lookup"><span data-stu-id="071bb-131">int</span></span> | <span data-ttu-id="071bb-132">通信中に使用されるローカル コンピューター上の TCP ポート</span><span class="sxs-lookup"><span data-stu-id="071bb-132">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="071bb-133">string</span><span class="sxs-lookup"><span data-stu-id="071bb-133">string</span></span> | <span data-ttu-id="071bb-134">通信中に使用されるプロトコル</span><span class="sxs-lookup"><span data-stu-id="071bb-134">Protocol used during the communication</span></span> |
| `LocalIPType` | <span data-ttu-id="071bb-135">string</span><span class="sxs-lookup"><span data-stu-id="071bb-135">string</span></span> | <span data-ttu-id="071bb-136">IP アドレスの種類 (パブリック、プライベート、予約済み、ループバック、Teredo、FourToSixMapping、ブロードキャストなど)</span><span class="sxs-lookup"><span data-stu-id="071bb-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="071bb-137">string</span><span class="sxs-lookup"><span data-stu-id="071bb-137">string</span></span> | <span data-ttu-id="071bb-138">IP アドレスの種類 (パブリック、プライベート、予約済み、ループバック、Teredo、FourToSixMapping、ブロードキャストなど)</span><span class="sxs-lookup"><span data-stu-id="071bb-138">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="071bb-139">string</span><span class="sxs-lookup"><span data-stu-id="071bb-139">string</span></span> | <span data-ttu-id="071bb-140">イベントを開始したプロセス (イメージ ファイル) の SHA-1</span><span class="sxs-lookup"><span data-stu-id="071bb-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="071bb-141">string</span><span class="sxs-lookup"><span data-stu-id="071bb-141">string</span></span> | <span data-ttu-id="071bb-142">イベントを開始したプロセス (イメージ ファイル) の SHA-256。</span><span class="sxs-lookup"><span data-stu-id="071bb-142">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="071bb-143">このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="071bb-143">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="071bb-144">文字列型</span><span class="sxs-lookup"><span data-stu-id="071bb-144">string</span></span> | <span data-ttu-id="071bb-145">イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="071bb-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="071bb-146">string</span><span class="sxs-lookup"><span data-stu-id="071bb-146">string</span></span> | <span data-ttu-id="071bb-147">イベントを開始したプロセスの名前</span><span class="sxs-lookup"><span data-stu-id="071bb-147">Name of the process that initiated the event</span></span> |
| `InitiatingProcessFileSize` | <span data-ttu-id="071bb-148">long</span><span class="sxs-lookup"><span data-stu-id="071bb-148">long</span></span> | <span data-ttu-id="071bb-149">イベントの処理を実行したファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="071bb-149">Size of the file that ran the process responsible for the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="071bb-150">int</span><span class="sxs-lookup"><span data-stu-id="071bb-150">int</span></span> | <span data-ttu-id="071bb-151">イベントを開始したプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="071bb-151">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="071bb-152">string</span><span class="sxs-lookup"><span data-stu-id="071bb-152">string</span></span> | <span data-ttu-id="071bb-153">イベントを開始したプロセスの実行に使用されるコマンド ライン</span><span class="sxs-lookup"><span data-stu-id="071bb-153">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="071bb-154">日付型</span><span class="sxs-lookup"><span data-stu-id="071bb-154">datetime</span></span> | <span data-ttu-id="071bb-155">イベントを開始したプロセスが開始された日時</span><span class="sxs-lookup"><span data-stu-id="071bb-155">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="071bb-156">string</span><span class="sxs-lookup"><span data-stu-id="071bb-156">string</span></span> | <span data-ttu-id="071bb-157">イベントを開始したプロセス (イメージ ファイル) を含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="071bb-157">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="071bb-158">string</span><span class="sxs-lookup"><span data-stu-id="071bb-158">string</span></span> | <span data-ttu-id="071bb-159">イベントを担当するプロセスを生成した親プロセスの名前</span><span class="sxs-lookup"><span data-stu-id="071bb-159">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="071bb-160">int</span><span class="sxs-lookup"><span data-stu-id="071bb-160">int</span></span> | <span data-ttu-id="071bb-161">イベントを担当するプロセスを生成した親プロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="071bb-161">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="071bb-162">日付型</span><span class="sxs-lookup"><span data-stu-id="071bb-162">datetime</span></span> | <span data-ttu-id="071bb-163">イベントを担当するプロセスの親が開始された日時</span><span class="sxs-lookup"><span data-stu-id="071bb-163">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="071bb-164">string</span><span class="sxs-lookup"><span data-stu-id="071bb-164">string</span></span> | <span data-ttu-id="071bb-165">イベントを担当するプロセスを実行したアカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="071bb-165">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="071bb-166">string</span><span class="sxs-lookup"><span data-stu-id="071bb-166">string</span></span> | <span data-ttu-id="071bb-167">イベントを担当するプロセスを実行したアカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="071bb-167">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="071bb-168">string</span><span class="sxs-lookup"><span data-stu-id="071bb-168">string</span></span> | <span data-ttu-id="071bb-169">イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="071bb-169">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountUpn` | <span data-ttu-id="071bb-170">string</span><span class="sxs-lookup"><span data-stu-id="071bb-170">string</span></span> | <span data-ttu-id="071bb-171">イベントを担当するプロセスを実行したアカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="071bb-171">User principal name (UPN) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="071bb-172">string</span><span class="sxs-lookup"><span data-stu-id="071bb-172">string</span></span> | <span data-ttu-id="071bb-173">イベントを開始したプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="071bb-173">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="071bb-174">Windows は、インターネットダウンロードから起動された場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="071bb-174">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="071bb-175">これらの整合性レベルは、リソースへのアクセス許可に影響を与えます</span><span class="sxs-lookup"><span data-stu-id="071bb-175">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="071bb-176">string</span><span class="sxs-lookup"><span data-stu-id="071bb-176">string</span></span> | <span data-ttu-id="071bb-177">イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権昇格の有無を示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="071bb-177">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="071bb-178">long</span><span class="sxs-lookup"><span data-stu-id="071bb-178">long</span></span> | <span data-ttu-id="071bb-179">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="071bb-179">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="071bb-180">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="071bb-180">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="071bb-181">string</span><span class="sxs-lookup"><span data-stu-id="071bb-181">string</span></span> | <span data-ttu-id="071bb-182">ブラウザーのアクティビティを分離するために Application Guard が使用する仮想化コンテナーの識別子</span><span class="sxs-lookup"><span data-stu-id="071bb-182">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |
| `AdditionalFields` | <span data-ttu-id="071bb-183">string</span><span class="sxs-lookup"><span data-stu-id="071bb-183">string</span></span> | <span data-ttu-id="071bb-184">JSON 配列形式のイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="071bb-184">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="071bb-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="071bb-185">Related topics</span></span>
- [<span data-ttu-id="071bb-186">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="071bb-186">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="071bb-187">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="071bb-187">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="071bb-188">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="071bb-188">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="071bb-189">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="071bb-189">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="071bb-190">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="071bb-190">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="071bb-191">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="071bb-191">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
