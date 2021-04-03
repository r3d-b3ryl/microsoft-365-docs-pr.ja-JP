---
title: 高度なハンティング スキーマの DeviceNetworkEvents テーブル
description: 高度な検索スキーマの DeviceNetworkEvents テーブルからクエリできるネットワーク接続イベントについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、devicenetworkevents、ネットワーク接続、リモート IP、ローカル IP、NetworkCommunicationEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: de31cb923a0584f45cb92340cf7e1c6b5ca5e9a0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500771"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="731eb-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="731eb-104">DeviceNetworkEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="731eb-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="731eb-105">**Applies to:**</span></span>
- [<span data-ttu-id="731eb-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="731eb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="731eb-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="731eb-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="731eb-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="731eb-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="731eb-109">高度 `DeviceNetworkEvents` な検索スキーマの [表には](advanced-hunting-overview.md) 、ネットワーク接続と関連イベントに関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="731eb-109">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="731eb-110">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="731eb-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="731eb-111">高度なハンティング スキーマの他のテーブルの詳細については、高度なハンティング [スキーマリファレンスを参照してください](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="731eb-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="731eb-112">列名</span><span class="sxs-lookup"><span data-stu-id="731eb-112">Column name</span></span> | <span data-ttu-id="731eb-113">データ型</span><span class="sxs-lookup"><span data-stu-id="731eb-113">Data type</span></span> | <span data-ttu-id="731eb-114">説明</span><span class="sxs-lookup"><span data-stu-id="731eb-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="731eb-115">日付型</span><span class="sxs-lookup"><span data-stu-id="731eb-115">datetime</span></span> | <span data-ttu-id="731eb-116">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="731eb-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="731eb-117">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-117">string</span></span> | <span data-ttu-id="731eb-118">サービス内のデバイスの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="731eb-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="731eb-119">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-119">string</span></span> | <span data-ttu-id="731eb-120">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="731eb-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ActionType` | <span data-ttu-id="731eb-121">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-121">string</span></span> | <span data-ttu-id="731eb-122">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="731eb-122">Type of activity that triggered the event</span></span> |
| `RemoteIP` | <span data-ttu-id="731eb-123">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-123">string</span></span> | <span data-ttu-id="731eb-124">に接続されていた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="731eb-124">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="731eb-125">int</span><span class="sxs-lookup"><span data-stu-id="731eb-125">int</span></span> | <span data-ttu-id="731eb-126">接続されているリモート デバイスの TCP ポート</span><span class="sxs-lookup"><span data-stu-id="731eb-126">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="731eb-127">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-127">string</span></span> | <span data-ttu-id="731eb-128">に接続されていた URL または完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="731eb-128">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="731eb-129">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-129">string</span></span> | <span data-ttu-id="731eb-130">通信中に使用されるローカル デバイスに割り当てられた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="731eb-130">IP address assigned to the local device used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="731eb-131">int</span><span class="sxs-lookup"><span data-stu-id="731eb-131">int</span></span> | <span data-ttu-id="731eb-132">通信中に使用されるローカル デバイス上の TCP ポート</span><span class="sxs-lookup"><span data-stu-id="731eb-132">TCP port on the local device used during communication</span></span> |
| `Protocol` | <span data-ttu-id="731eb-133">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-133">string</span></span> | <span data-ttu-id="731eb-134">TCP または UDP に関して使用される IP プロトコル</span><span class="sxs-lookup"><span data-stu-id="731eb-134">IP protocol used, whether TCP or UDP</span></span> |
| `LocalIPType` | <span data-ttu-id="731eb-135">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-135">string</span></span> | <span data-ttu-id="731eb-136">IP アドレスの種類 (パブリック、プライベート、予約済み、ループバック、Teredo、FourToSixMapping、ブロードキャストなど)</span><span class="sxs-lookup"><span data-stu-id="731eb-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="731eb-137">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-137">string</span></span> | <span data-ttu-id="731eb-138">IP アドレスの種類 (パブリック、プライベート、予約済み、ループバック、Teredo、FourToSixMapping、ブロードキャストなど)</span><span class="sxs-lookup"><span data-stu-id="731eb-138">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="731eb-139">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-139">string</span></span> | <span data-ttu-id="731eb-140">イベントを開始したプロセス (イメージ ファイル) の SHA-1</span><span class="sxs-lookup"><span data-stu-id="731eb-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="731eb-141">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-141">string</span></span> | <span data-ttu-id="731eb-142">イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="731eb-142">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="731eb-143">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-143">string</span></span> | <span data-ttu-id="731eb-144">イベントを開始したプロセスの名前</span><span class="sxs-lookup"><span data-stu-id="731eb-144">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="731eb-145">int</span><span class="sxs-lookup"><span data-stu-id="731eb-145">int</span></span> | <span data-ttu-id="731eb-146">イベントを開始したプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="731eb-146">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="731eb-147">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-147">string</span></span> | <span data-ttu-id="731eb-148">イベントを開始したプロセスの実行に使用されるコマンド ライン</span><span class="sxs-lookup"><span data-stu-id="731eb-148">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="731eb-149">日付型</span><span class="sxs-lookup"><span data-stu-id="731eb-149">datetime</span></span> | <span data-ttu-id="731eb-150">イベントを開始したプロセスが開始された日時</span><span class="sxs-lookup"><span data-stu-id="731eb-150">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="731eb-151">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-151">string</span></span> | <span data-ttu-id="731eb-152">イベントを開始したプロセス (イメージ ファイル) を含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="731eb-152">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="731eb-153">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-153">string</span></span> | <span data-ttu-id="731eb-154">イベントを担当するプロセスを生成した親プロセスの名前</span><span class="sxs-lookup"><span data-stu-id="731eb-154">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="731eb-155">int</span><span class="sxs-lookup"><span data-stu-id="731eb-155">int</span></span> | <span data-ttu-id="731eb-156">イベントを担当するプロセスを生成した親プロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="731eb-156">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="731eb-157">日付型</span><span class="sxs-lookup"><span data-stu-id="731eb-157">datetime</span></span> | <span data-ttu-id="731eb-158">イベントを担当するプロセスの親が開始された日時</span><span class="sxs-lookup"><span data-stu-id="731eb-158">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="731eb-159">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-159">string</span></span> | <span data-ttu-id="731eb-160">イベントを担当するプロセスを実行したアカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="731eb-160">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="731eb-161">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-161">string</span></span> | <span data-ttu-id="731eb-162">イベントを担当するプロセスを実行したアカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="731eb-162">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="731eb-163">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-163">string</span></span> | <span data-ttu-id="731eb-164">イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="731eb-164">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="731eb-165">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-165">string</span></span> | <span data-ttu-id="731eb-166">イベントを開始したプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="731eb-166">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="731eb-167">Windows は、インターネットダウンロードから起動された場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="731eb-167">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="731eb-168">これらの整合性レベルは、リソースへのアクセス許可に影響を与えます</span><span class="sxs-lookup"><span data-stu-id="731eb-168">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="731eb-169">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-169">string</span></span> | <span data-ttu-id="731eb-170">イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権昇格の有無を示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="731eb-170">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="731eb-171">long</span><span class="sxs-lookup"><span data-stu-id="731eb-171">long</span></span> | <span data-ttu-id="731eb-172">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="731eb-172">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="731eb-173">一意のイベントを識別するには、この列を and 列と組み合わせて `DeviceName` 使用する必要 `Timestamp` があります。</span><span class="sxs-lookup"><span data-stu-id="731eb-173">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="731eb-174">文字列</span><span class="sxs-lookup"><span data-stu-id="731eb-174">string</span></span> | <span data-ttu-id="731eb-175">ブラウザーのアクティビティを分離するために Application Guard が使用する仮想化コンテナーの識別子</span><span class="sxs-lookup"><span data-stu-id="731eb-175">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="731eb-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="731eb-176">Related topics</span></span>
- [<span data-ttu-id="731eb-177">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="731eb-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="731eb-178">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="731eb-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="731eb-179">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="731eb-179">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
