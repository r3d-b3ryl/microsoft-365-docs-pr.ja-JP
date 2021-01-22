---
title: 高度な検索スキーマの DeviceNetworkEvents テーブル
description: 高度な検索スキーマの DeviceNetworkEvents テーブルからクエリできるネットワーク接続イベントについて説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、devicenetworkevents、NetworkCommunicationEvents、ネットワーク接続、リモート IP、ローカル IP
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
ms.openlocfilehash: 0ed696f36737a4102895369e1254b4215cad4def
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931220"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="45257-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="45257-104">DeviceNetworkEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="45257-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="45257-105">**Applies to:**</span></span>
- <span data-ttu-id="45257-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45257-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="45257-107">高度 `DeviceNetworkEvents` な検索スキーマの [表には](advanced-hunting-overview.md) 、ネットワーク接続と関連イベントに関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="45257-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="45257-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="45257-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="45257-109">テーブルでサポートされているイベントの種類 ( 値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ `ActionType` リファレンスを使用してください。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="45257-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="45257-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45257-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="45257-111">列名</span><span class="sxs-lookup"><span data-stu-id="45257-111">Column name</span></span> | <span data-ttu-id="45257-112">データ型</span><span class="sxs-lookup"><span data-stu-id="45257-112">Data type</span></span> | <span data-ttu-id="45257-113">説明</span><span class="sxs-lookup"><span data-stu-id="45257-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="45257-114">日付型</span><span class="sxs-lookup"><span data-stu-id="45257-114">datetime</span></span> | <span data-ttu-id="45257-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="45257-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="45257-116">string</span><span class="sxs-lookup"><span data-stu-id="45257-116">string</span></span> | <span data-ttu-id="45257-117">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="45257-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="45257-118">string</span><span class="sxs-lookup"><span data-stu-id="45257-118">string</span></span> | <span data-ttu-id="45257-119">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="45257-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="45257-120">string</span><span class="sxs-lookup"><span data-stu-id="45257-120">string</span></span> | <span data-ttu-id="45257-121">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="45257-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="45257-122">詳細については [、ポータル内スキーマ リファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45257-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RemoteIP` | <span data-ttu-id="45257-123">文字列</span><span class="sxs-lookup"><span data-stu-id="45257-123">string</span></span> | <span data-ttu-id="45257-124">に接続されていた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="45257-124">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="45257-125">int</span><span class="sxs-lookup"><span data-stu-id="45257-125">int</span></span> | <span data-ttu-id="45257-126">接続されているリモート デバイス上の TCP ポート</span><span class="sxs-lookup"><span data-stu-id="45257-126">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="45257-127">文字列</span><span class="sxs-lookup"><span data-stu-id="45257-127">string</span></span> | <span data-ttu-id="45257-128">に接続されていた URL または完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="45257-128">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="45257-129">文字列</span><span class="sxs-lookup"><span data-stu-id="45257-129">string</span></span> | <span data-ttu-id="45257-130">通信中に使用されるローカル コンピューターに割り当てられた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="45257-130">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="45257-131">int</span><span class="sxs-lookup"><span data-stu-id="45257-131">int</span></span> | <span data-ttu-id="45257-132">通信中に使用されるローカル コンピューター上の TCP ポート</span><span class="sxs-lookup"><span data-stu-id="45257-132">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="45257-133">string</span><span class="sxs-lookup"><span data-stu-id="45257-133">string</span></span> | <span data-ttu-id="45257-134">通信中に使用されるプロトコル</span><span class="sxs-lookup"><span data-stu-id="45257-134">Protocol used during the communication</span></span> |
| `LocalIPType` | <span data-ttu-id="45257-135">string</span><span class="sxs-lookup"><span data-stu-id="45257-135">string</span></span> | <span data-ttu-id="45257-136">IP アドレスの種類 (パブリック、プライベート、予約済み、ループバック、Teredo、FourToSixMapping、ブロードキャストなど)</span><span class="sxs-lookup"><span data-stu-id="45257-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="45257-137">string</span><span class="sxs-lookup"><span data-stu-id="45257-137">string</span></span> | <span data-ttu-id="45257-138">IP アドレスの種類 (パブリック、プライベート、予約済み、ループバック、Teredo、FourToSixMapping、ブロードキャストなど)</span><span class="sxs-lookup"><span data-stu-id="45257-138">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="45257-139">string</span><span class="sxs-lookup"><span data-stu-id="45257-139">string</span></span> | <span data-ttu-id="45257-140">イベントを開始したプロセス (イメージ ファイル) の SHA-1</span><span class="sxs-lookup"><span data-stu-id="45257-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="45257-141">string</span><span class="sxs-lookup"><span data-stu-id="45257-141">string</span></span> | <span data-ttu-id="45257-142">イベントを開始したプロセス (イメージ ファイル) の SHA-256。</span><span class="sxs-lookup"><span data-stu-id="45257-142">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="45257-143">このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="45257-143">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="45257-144">文字列型</span><span class="sxs-lookup"><span data-stu-id="45257-144">string</span></span> | <span data-ttu-id="45257-145">イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="45257-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="45257-146">string</span><span class="sxs-lookup"><span data-stu-id="45257-146">string</span></span> | <span data-ttu-id="45257-147">イベントを開始したプロセスの名前</span><span class="sxs-lookup"><span data-stu-id="45257-147">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="45257-148">int</span><span class="sxs-lookup"><span data-stu-id="45257-148">int</span></span> | <span data-ttu-id="45257-149">イベントを開始したプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="45257-149">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="45257-150">string</span><span class="sxs-lookup"><span data-stu-id="45257-150">string</span></span> | <span data-ttu-id="45257-151">イベントを開始したプロセスの実行に使用されるコマンド ライン</span><span class="sxs-lookup"><span data-stu-id="45257-151">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="45257-152">日付型</span><span class="sxs-lookup"><span data-stu-id="45257-152">datetime</span></span> | <span data-ttu-id="45257-153">イベントを開始したプロセスが開始された日時</span><span class="sxs-lookup"><span data-stu-id="45257-153">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="45257-154">string</span><span class="sxs-lookup"><span data-stu-id="45257-154">string</span></span> | <span data-ttu-id="45257-155">イベントを開始したプロセス (イメージ ファイル) を含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="45257-155">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="45257-156">string</span><span class="sxs-lookup"><span data-stu-id="45257-156">string</span></span> | <span data-ttu-id="45257-157">イベントを処理するプロセスを生成した親プロセスの名前</span><span class="sxs-lookup"><span data-stu-id="45257-157">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="45257-158">int</span><span class="sxs-lookup"><span data-stu-id="45257-158">int</span></span> | <span data-ttu-id="45257-159">イベントを処理するプロセスを生成した親プロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="45257-159">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="45257-160">日付型</span><span class="sxs-lookup"><span data-stu-id="45257-160">datetime</span></span> | <span data-ttu-id="45257-161">イベントを担当するプロセスの親が開始された日時</span><span class="sxs-lookup"><span data-stu-id="45257-161">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="45257-162">string</span><span class="sxs-lookup"><span data-stu-id="45257-162">string</span></span> | <span data-ttu-id="45257-163">イベントを処理するプロセスを実行したアカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="45257-163">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="45257-164">string</span><span class="sxs-lookup"><span data-stu-id="45257-164">string</span></span> | <span data-ttu-id="45257-165">イベントを処理するプロセスを実行したアカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="45257-165">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="45257-166">string</span><span class="sxs-lookup"><span data-stu-id="45257-166">string</span></span> | <span data-ttu-id="45257-167">イベントを処理するプロセスを実行したアカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="45257-167">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="45257-168">string</span><span class="sxs-lookup"><span data-stu-id="45257-168">string</span></span> | <span data-ttu-id="45257-169">イベントを開始したプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="45257-169">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="45257-170">Windows は、インターネット ダウンロードから起動された場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="45257-170">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="45257-171">これらの整合性レベルは、リソースへのアクセス許可に影響します。</span><span class="sxs-lookup"><span data-stu-id="45257-171">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="45257-172">string</span><span class="sxs-lookup"><span data-stu-id="45257-172">string</span></span> | <span data-ttu-id="45257-173">イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権の昇格の有無を示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="45257-173">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="45257-174">long</span><span class="sxs-lookup"><span data-stu-id="45257-174">long</span></span> | <span data-ttu-id="45257-175">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="45257-175">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="45257-176">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45257-176">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="45257-177">string</span><span class="sxs-lookup"><span data-stu-id="45257-177">string</span></span> | <span data-ttu-id="45257-178">ブラウザーの動作を分離するために Application Guard によって使用される仮想化コンテナーの識別子</span><span class="sxs-lookup"><span data-stu-id="45257-178">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="45257-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="45257-179">Related topics</span></span>
- [<span data-ttu-id="45257-180">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="45257-180">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="45257-181">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="45257-181">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="45257-182">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="45257-182">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="45257-183">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="45257-183">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="45257-184">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="45257-184">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="45257-185">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="45257-185">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
