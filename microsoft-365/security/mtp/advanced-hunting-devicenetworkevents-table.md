---
title: 高度な検索スキーマの DeviceNetworkEvents 孔テーブル
description: 高度な検索スキーマの DeviceNetworkEvents 孔テーブルからクエリできるネットワーク接続イベントについて説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、devicenetworkevents、NetworkCommunicationEvents、ネットワーク接続、リモート ip、ローカル ip
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
ms.openlocfilehash: 6d962d558246c60d1910a8c574bbb52bdd10b926
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429937"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="e037d-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="e037d-104">DeviceNetworkEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e037d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e037d-105">**Applies to:**</span></span>
- <span data-ttu-id="e037d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e037d-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="e037d-107">`DeviceNetworkEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、ネットワーク接続と関連イベントに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e037d-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="e037d-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e037d-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="e037d-109">テーブルでサポートされているイベントの種類 (値) の詳細については、 `ActionType` セキュリティセンターで利用可能な [組み込みスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="e037d-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="e037d-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e037d-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e037d-111">列名</span><span class="sxs-lookup"><span data-stu-id="e037d-111">Column name</span></span> | <span data-ttu-id="e037d-112">データ型</span><span class="sxs-lookup"><span data-stu-id="e037d-112">Data type</span></span> | <span data-ttu-id="e037d-113">説明</span><span class="sxs-lookup"><span data-stu-id="e037d-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e037d-114">日付型</span><span class="sxs-lookup"><span data-stu-id="e037d-114">datetime</span></span> | <span data-ttu-id="e037d-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="e037d-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="e037d-116">string</span><span class="sxs-lookup"><span data-stu-id="e037d-116">string</span></span> | <span data-ttu-id="e037d-117">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="e037d-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e037d-118">string</span><span class="sxs-lookup"><span data-stu-id="e037d-118">string</span></span> | <span data-ttu-id="e037d-119">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="e037d-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="e037d-120">string</span><span class="sxs-lookup"><span data-stu-id="e037d-120">string</span></span> | <span data-ttu-id="e037d-121">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="e037d-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="e037d-122">詳細については、 [ポータル内のスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e037d-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RemoteIP` | <span data-ttu-id="e037d-123">文字列</span><span class="sxs-lookup"><span data-stu-id="e037d-123">string</span></span> | <span data-ttu-id="e037d-124">に接続されていた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="e037d-124">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="e037d-125">int</span><span class="sxs-lookup"><span data-stu-id="e037d-125">int</span></span> | <span data-ttu-id="e037d-126">接続先のリモートデバイスの TCP ポート</span><span class="sxs-lookup"><span data-stu-id="e037d-126">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="e037d-127">文字列</span><span class="sxs-lookup"><span data-stu-id="e037d-127">string</span></span> | <span data-ttu-id="e037d-128">に接続されていた URL または完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="e037d-128">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="e037d-129">文字列</span><span class="sxs-lookup"><span data-stu-id="e037d-129">string</span></span> | <span data-ttu-id="e037d-130">通信時に使用されるローカルコンピューターに割り当てられた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="e037d-130">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="e037d-131">int</span><span class="sxs-lookup"><span data-stu-id="e037d-131">int</span></span> | <span data-ttu-id="e037d-132">通信時に使用されるローカルコンピューターの TCP ポート</span><span class="sxs-lookup"><span data-stu-id="e037d-132">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="e037d-133">string</span><span class="sxs-lookup"><span data-stu-id="e037d-133">string</span></span> | <span data-ttu-id="e037d-134">通信中に使用されるプロトコル</span><span class="sxs-lookup"><span data-stu-id="e037d-134">Protocol used during the communication</span></span> |
| `LocalIPType` | <span data-ttu-id="e037d-135">string</span><span class="sxs-lookup"><span data-stu-id="e037d-135">string</span></span> | <span data-ttu-id="e037d-136">IP アドレスの種類 (例: Public、Private、Reserved、Loopback、Teredo、FourToSixMapping、ブロードキャスト)</span><span class="sxs-lookup"><span data-stu-id="e037d-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="e037d-137">string</span><span class="sxs-lookup"><span data-stu-id="e037d-137">string</span></span> | <span data-ttu-id="e037d-138">IP アドレスの種類 (例: Public、Private、Reserved、Loopback、Teredo、FourToSixMapping、ブロードキャスト)</span><span class="sxs-lookup"><span data-stu-id="e037d-138">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="e037d-139">string</span><span class="sxs-lookup"><span data-stu-id="e037d-139">string</span></span> | <span data-ttu-id="e037d-140">イベントを開始したプロセス (画像ファイル) の SHA-1</span><span class="sxs-lookup"><span data-stu-id="e037d-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="e037d-141">string</span><span class="sxs-lookup"><span data-stu-id="e037d-141">string</span></span> | <span data-ttu-id="e037d-142">イベントを開始したプロセス (イメージファイル) の256。</span><span class="sxs-lookup"><span data-stu-id="e037d-142">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="e037d-143">このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="e037d-143">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="e037d-144">文字列型</span><span class="sxs-lookup"><span data-stu-id="e037d-144">string</span></span> | <span data-ttu-id="e037d-145">イベントを開始したプロセス (画像ファイル) の MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="e037d-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="e037d-146">string</span><span class="sxs-lookup"><span data-stu-id="e037d-146">string</span></span> | <span data-ttu-id="e037d-147">イベントを開始したプロセスの名前</span><span class="sxs-lookup"><span data-stu-id="e037d-147">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="e037d-148">int</span><span class="sxs-lookup"><span data-stu-id="e037d-148">int</span></span> | <span data-ttu-id="e037d-149">イベントを開始したプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="e037d-149">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="e037d-150">string</span><span class="sxs-lookup"><span data-stu-id="e037d-150">string</span></span> | <span data-ttu-id="e037d-151">イベントを開始したプロセスを実行するために使用されるコマンドライン</span><span class="sxs-lookup"><span data-stu-id="e037d-151">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="e037d-152">日付型</span><span class="sxs-lookup"><span data-stu-id="e037d-152">datetime</span></span> | <span data-ttu-id="e037d-153">イベントを開始したプロセスが開始された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="e037d-153">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="e037d-154">string</span><span class="sxs-lookup"><span data-stu-id="e037d-154">string</span></span> | <span data-ttu-id="e037d-155">イベントを開始したプロセス (画像ファイル) を含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="e037d-155">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="e037d-156">string</span><span class="sxs-lookup"><span data-stu-id="e037d-156">string</span></span> | <span data-ttu-id="e037d-157">イベントを処理するプロセスを生成した親プロセスの名前</span><span class="sxs-lookup"><span data-stu-id="e037d-157">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="e037d-158">int</span><span class="sxs-lookup"><span data-stu-id="e037d-158">int</span></span> | <span data-ttu-id="e037d-159">イベントを担当するプロセスを発生させる親プロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="e037d-159">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="e037d-160">日付型</span><span class="sxs-lookup"><span data-stu-id="e037d-160">datetime</span></span> | <span data-ttu-id="e037d-161">イベントを担当するプロセスの親が開始された日時</span><span class="sxs-lookup"><span data-stu-id="e037d-161">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="e037d-162">string</span><span class="sxs-lookup"><span data-stu-id="e037d-162">string</span></span> | <span data-ttu-id="e037d-163">イベントを担当するプロセスを実行したアカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="e037d-163">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="e037d-164">string</span><span class="sxs-lookup"><span data-stu-id="e037d-164">string</span></span> | <span data-ttu-id="e037d-165">イベントを担当するプロセスを実行したアカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="e037d-165">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="e037d-166">string</span><span class="sxs-lookup"><span data-stu-id="e037d-166">string</span></span> | <span data-ttu-id="e037d-167">イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="e037d-167">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="e037d-168">string</span><span class="sxs-lookup"><span data-stu-id="e037d-168">string</span></span> | <span data-ttu-id="e037d-169">イベントを開始したプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="e037d-169">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="e037d-170">Windows は、インターネットダウンロードから起動されたかどうかなど、特定の特性に基づいてプロセスに整合性レベルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e037d-170">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="e037d-171">これらの整合性レベルは、リソースへのアクセス許可に影響します。</span><span class="sxs-lookup"><span data-stu-id="e037d-171">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="e037d-172">string</span><span class="sxs-lookup"><span data-stu-id="e037d-172">string</span></span> | <span data-ttu-id="e037d-173">イベントを開始したプロセスに適用されたユーザーアクセス制御 (UAC) 特権昇格が存在するかどうかを示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="e037d-173">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="e037d-174">long</span><span class="sxs-lookup"><span data-stu-id="e037d-174">long</span></span> | <span data-ttu-id="e037d-175">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="e037d-175">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="e037d-176">一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e037d-176">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="e037d-177">string</span><span class="sxs-lookup"><span data-stu-id="e037d-177">string</span></span> | <span data-ttu-id="e037d-178">Application Guard がブラウザーのアクティビティを分離するために使用する仮想化されたコンテナーの識別子</span><span class="sxs-lookup"><span data-stu-id="e037d-178">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e037d-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="e037d-179">Related topics</span></span>
- [<span data-ttu-id="e037d-180">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="e037d-180">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e037d-181">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="e037d-181">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e037d-182">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="e037d-182">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e037d-183">デバイス、メール、アプリ、ID 間での捜索</span><span class="sxs-lookup"><span data-stu-id="e037d-183">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e037d-184">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="e037d-184">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e037d-185">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="e037d-185">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
