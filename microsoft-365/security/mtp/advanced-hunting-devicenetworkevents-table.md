---
title: 高度な検索スキーマの DeviceNetworkEvents 孔テーブル
description: 高度な検索スキーマの DeviceNetworkEvents 孔テーブルからクエリできるネットワーク接続イベントについて説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、devicenetworkevents 孔、NetworkCommunicationEvents、network接続、リモート ip、ローカル ip
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
ms.openlocfilehash: 2e7999fef43adb372947d9edf92b84ac67f347fe
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235006"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="d6896-104">DeviceNetworkEvents 孔</span><span class="sxs-lookup"><span data-stu-id="d6896-104">DeviceNetworkEvents</span></span>

<span data-ttu-id="d6896-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d6896-105">**Applies to:**</span></span>
- <span data-ttu-id="d6896-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d6896-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="d6896-107">`DeviceNetworkEvents` [高度な](advanced-hunting-overview.md)検索スキーマの表には、ネットワーク接続と関連イベントに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d6896-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="d6896-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="d6896-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="d6896-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6896-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d6896-110">列名</span><span class="sxs-lookup"><span data-stu-id="d6896-110">Column name</span></span> | <span data-ttu-id="d6896-111">データ型</span><span class="sxs-lookup"><span data-stu-id="d6896-111">Data type</span></span> | <span data-ttu-id="d6896-112">説明</span><span class="sxs-lookup"><span data-stu-id="d6896-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d6896-113">日付型</span><span class="sxs-lookup"><span data-stu-id="d6896-113">datetime</span></span> | <span data-ttu-id="d6896-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="d6896-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="d6896-115">string</span><span class="sxs-lookup"><span data-stu-id="d6896-115">string</span></span> | <span data-ttu-id="d6896-116">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="d6896-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d6896-117">string</span><span class="sxs-lookup"><span data-stu-id="d6896-117">string</span></span> | <span data-ttu-id="d6896-118">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="d6896-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="d6896-119">string</span><span class="sxs-lookup"><span data-stu-id="d6896-119">string</span></span> | <span data-ttu-id="d6896-120">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="d6896-120">Type of activity that triggered the event</span></span> |
| `RemoteIP` | <span data-ttu-id="d6896-121">文字列</span><span class="sxs-lookup"><span data-stu-id="d6896-121">string</span></span> | <span data-ttu-id="d6896-122">に接続されていた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="d6896-122">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="d6896-123">int</span><span class="sxs-lookup"><span data-stu-id="d6896-123">int</span></span> | <span data-ttu-id="d6896-124">接続先のリモートデバイスの TCP ポート</span><span class="sxs-lookup"><span data-stu-id="d6896-124">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="d6896-125">string</span><span class="sxs-lookup"><span data-stu-id="d6896-125">string</span></span> | <span data-ttu-id="d6896-126">に接続されていた URL または完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="d6896-126">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="d6896-127">文字列</span><span class="sxs-lookup"><span data-stu-id="d6896-127">string</span></span> | <span data-ttu-id="d6896-128">通信時に使用されるローカルコンピューターに割り当てられた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="d6896-128">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="d6896-129">int</span><span class="sxs-lookup"><span data-stu-id="d6896-129">int</span></span> | <span data-ttu-id="d6896-130">通信時に使用されるローカルコンピューターの TCP ポート</span><span class="sxs-lookup"><span data-stu-id="d6896-130">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="d6896-131">string</span><span class="sxs-lookup"><span data-stu-id="d6896-131">string</span></span> | <span data-ttu-id="d6896-132">使用されている IP プロトコル (TCP または UDP)</span><span class="sxs-lookup"><span data-stu-id="d6896-132">IP protocol used, whether TCP or UDP</span></span> |
| `LocalIPType` | <span data-ttu-id="d6896-133">string</span><span class="sxs-lookup"><span data-stu-id="d6896-133">string</span></span> | <span data-ttu-id="d6896-134">IP アドレスの種類 (例: Public、Private、Reserved、Loopback、Teredo、FourToSixMapping、ブロードキャスト)</span><span class="sxs-lookup"><span data-stu-id="d6896-134">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="d6896-135">string</span><span class="sxs-lookup"><span data-stu-id="d6896-135">string</span></span> | <span data-ttu-id="d6896-136">IP アドレスの種類 (例: Public、Private、Reserved、Loopback、Teredo、FourToSixMapping、ブロードキャスト)</span><span class="sxs-lookup"><span data-stu-id="d6896-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="d6896-137">string</span><span class="sxs-lookup"><span data-stu-id="d6896-137">string</span></span> | <span data-ttu-id="d6896-138">イベントを開始したプロセス (画像ファイル) の SHA-1</span><span class="sxs-lookup"><span data-stu-id="d6896-138">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="d6896-139">string</span><span class="sxs-lookup"><span data-stu-id="d6896-139">string</span></span> | <span data-ttu-id="d6896-140">イベントを開始したプロセス (画像ファイル) の MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="d6896-140">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="d6896-141">string</span><span class="sxs-lookup"><span data-stu-id="d6896-141">string</span></span> | <span data-ttu-id="d6896-142">イベントを開始したプロセスの名前</span><span class="sxs-lookup"><span data-stu-id="d6896-142">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="d6896-143">int</span><span class="sxs-lookup"><span data-stu-id="d6896-143">int</span></span> | <span data-ttu-id="d6896-144">イベントを開始したプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="d6896-144">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="d6896-145">string</span><span class="sxs-lookup"><span data-stu-id="d6896-145">string</span></span> | <span data-ttu-id="d6896-146">イベントを開始したプロセスを実行するために使用されるコマンドライン</span><span class="sxs-lookup"><span data-stu-id="d6896-146">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="d6896-147">日付型</span><span class="sxs-lookup"><span data-stu-id="d6896-147">datetime</span></span> | <span data-ttu-id="d6896-148">イベントを開始したプロセスが開始された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="d6896-148">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="d6896-149">string</span><span class="sxs-lookup"><span data-stu-id="d6896-149">string</span></span> | <span data-ttu-id="d6896-150">イベントを開始したプロセス (画像ファイル) を含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="d6896-150">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="d6896-151">string</span><span class="sxs-lookup"><span data-stu-id="d6896-151">string</span></span> | <span data-ttu-id="d6896-152">イベントを処理するプロセスを生成した親プロセスの名前</span><span class="sxs-lookup"><span data-stu-id="d6896-152">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="d6896-153">int</span><span class="sxs-lookup"><span data-stu-id="d6896-153">int</span></span> | <span data-ttu-id="d6896-154">イベントを担当するプロセスを発生させる親プロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="d6896-154">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="d6896-155">日付型</span><span class="sxs-lookup"><span data-stu-id="d6896-155">datetime</span></span> | <span data-ttu-id="d6896-156">イベントを担当するプロセスの親が開始された日時</span><span class="sxs-lookup"><span data-stu-id="d6896-156">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="d6896-157">string</span><span class="sxs-lookup"><span data-stu-id="d6896-157">string</span></span> | <span data-ttu-id="d6896-158">イベントを担当するプロセスを実行したアカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="d6896-158">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="d6896-159">string</span><span class="sxs-lookup"><span data-stu-id="d6896-159">string</span></span> | <span data-ttu-id="d6896-160">イベントを担当するプロセスを実行したアカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="d6896-160">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="d6896-161">string</span><span class="sxs-lookup"><span data-stu-id="d6896-161">string</span></span> | <span data-ttu-id="d6896-162">イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="d6896-162">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="d6896-163">string</span><span class="sxs-lookup"><span data-stu-id="d6896-163">string</span></span> | <span data-ttu-id="d6896-164">イベントを開始したプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="d6896-164">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="d6896-165">Windows は、インターネットダウンロードから起動されたかどうかなど、特定の特性に基づいてプロセスに整合性レベルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d6896-165">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="d6896-166">これらの整合性レベルは、リソースへのアクセス許可に影響します。</span><span class="sxs-lookup"><span data-stu-id="d6896-166">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="d6896-167">string</span><span class="sxs-lookup"><span data-stu-id="d6896-167">string</span></span> | <span data-ttu-id="d6896-168">イベントを開始したプロセスに適用されたユーザーアクセス制御 (UAC) 特権昇格が存在するかどうかを示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="d6896-168">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="d6896-169">long</span><span class="sxs-lookup"><span data-stu-id="d6896-169">long</span></span> | <span data-ttu-id="d6896-170">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="d6896-170">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="d6896-171">一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6896-171">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="d6896-172">string</span><span class="sxs-lookup"><span data-stu-id="d6896-172">string</span></span> | <span data-ttu-id="d6896-173">Application Guard がブラウザーのアクティビティを分離するために使用する仮想化されたコンテナーの識別子</span><span class="sxs-lookup"><span data-stu-id="d6896-173">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d6896-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6896-174">Related topics</span></span>
- [<span data-ttu-id="d6896-175">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="d6896-175">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d6896-176">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="d6896-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d6896-177">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="d6896-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d6896-178">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="d6896-178">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d6896-179">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="d6896-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d6896-180">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="d6896-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
