---
title: 高度な検索スキーマの DeviceImageLoadEvents テーブル
description: 高度な検索スキーマの DeviceImageLoadEvents テーブルでの DLL 読み込みイベントについて説明します。
keywords: 高度な検索、脅威の探し、サイバーの脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、imageloadevents、DeviceImageLoadEvents、DLL の読み込み、ライブラリ、ファイルイメージ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: d2ff86977343aac1fdb5c201e3eb786bf968e545
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210459"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="e3308-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="e3308-104">DeviceImageLoadEvents</span></span>

<span data-ttu-id="e3308-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e3308-105">**Applies to:**</span></span>
- <span data-ttu-id="e3308-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e3308-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="e3308-107">`DeviceImageLoadEvents` [高度な](advanced-hunting-overview.md)検索スキーマの表には、DLL 読み込みイベントに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e3308-107">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="e3308-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3308-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="e3308-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3308-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e3308-110">列名</span><span class="sxs-lookup"><span data-stu-id="e3308-110">Column name</span></span> | <span data-ttu-id="e3308-111">データ型</span><span class="sxs-lookup"><span data-stu-id="e3308-111">Data type</span></span> | <span data-ttu-id="e3308-112">説明</span><span class="sxs-lookup"><span data-stu-id="e3308-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e3308-113">日付型</span><span class="sxs-lookup"><span data-stu-id="e3308-113">datetime</span></span> | <span data-ttu-id="e3308-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="e3308-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="e3308-115">string</span><span class="sxs-lookup"><span data-stu-id="e3308-115">string</span></span> | <span data-ttu-id="e3308-116">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="e3308-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e3308-117">string</span><span class="sxs-lookup"><span data-stu-id="e3308-117">string</span></span> | <span data-ttu-id="e3308-118">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="e3308-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="e3308-119">string</span><span class="sxs-lookup"><span data-stu-id="e3308-119">string</span></span> | <span data-ttu-id="e3308-120">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="e3308-120">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="e3308-121">文字列型</span><span class="sxs-lookup"><span data-stu-id="e3308-121">string</span></span> | <span data-ttu-id="e3308-122">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="e3308-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="e3308-123">文字列型</span><span class="sxs-lookup"><span data-stu-id="e3308-123">string</span></span> | <span data-ttu-id="e3308-124">記録されたアクションが適用されたファイルを含むフォルダ</span><span class="sxs-lookup"><span data-stu-id="e3308-124">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="e3308-125">文字列</span><span class="sxs-lookup"><span data-stu-id="e3308-125">string</span></span> | <span data-ttu-id="e3308-126">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="e3308-126">SHA-1 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="e3308-127">文字列</span><span class="sxs-lookup"><span data-stu-id="e3308-127">string</span></span> | <span data-ttu-id="e3308-128">記録されたアクションが適用されたファイルの MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="e3308-128">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="e3308-129">string</span><span class="sxs-lookup"><span data-stu-id="e3308-129">string</span></span> | <span data-ttu-id="e3308-130">イベントを担当するプロセスを実行したアカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="e3308-130">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="e3308-131">string</span><span class="sxs-lookup"><span data-stu-id="e3308-131">string</span></span> | <span data-ttu-id="e3308-132">イベントを担当するプロセスを実行したアカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="e3308-132">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="e3308-133">string</span><span class="sxs-lookup"><span data-stu-id="e3308-133">string</span></span> | <span data-ttu-id="e3308-134">イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="e3308-134">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="e3308-135">string</span><span class="sxs-lookup"><span data-stu-id="e3308-135">string</span></span> | <span data-ttu-id="e3308-136">イベントを開始したプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="e3308-136">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="e3308-137">Windows は、インターネットダウンロードから起動されたかどうかなど、特定の特性に基づいてプロセスに整合性レベルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e3308-137">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="e3308-138">これらの整合性レベルは、リソースへのアクセス許可に影響します。</span><span class="sxs-lookup"><span data-stu-id="e3308-138">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="e3308-139">string</span><span class="sxs-lookup"><span data-stu-id="e3308-139">string</span></span> | <span data-ttu-id="e3308-140">イベントを開始したプロセスに適用されたユーザーアクセス制御 (UAC) 特権昇格が存在するかどうかを示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="e3308-140">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="e3308-141">string</span><span class="sxs-lookup"><span data-stu-id="e3308-141">string</span></span> | <span data-ttu-id="e3308-142">イベントを開始したプロセス (画像ファイル) の SHA-1</span><span class="sxs-lookup"><span data-stu-id="e3308-142">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="e3308-143">string</span><span class="sxs-lookup"><span data-stu-id="e3308-143">string</span></span> | <span data-ttu-id="e3308-144">イベントを開始したプロセス (画像ファイル) の MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="e3308-144">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="e3308-145">string</span><span class="sxs-lookup"><span data-stu-id="e3308-145">string</span></span> | <span data-ttu-id="e3308-146">イベントを開始したプロセスの名前</span><span class="sxs-lookup"><span data-stu-id="e3308-146">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="e3308-147">int</span><span class="sxs-lookup"><span data-stu-id="e3308-147">int</span></span> | <span data-ttu-id="e3308-148">イベントを開始したプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="e3308-148">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="e3308-149">string</span><span class="sxs-lookup"><span data-stu-id="e3308-149">string</span></span> | <span data-ttu-id="e3308-150">イベントを開始したプロセスを実行するために使用されるコマンドライン</span><span class="sxs-lookup"><span data-stu-id="e3308-150">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="e3308-151">日付型</span><span class="sxs-lookup"><span data-stu-id="e3308-151">datetime</span></span> | <span data-ttu-id="e3308-152">イベントを開始したプロセスが開始された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="e3308-152">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="e3308-153">string</span><span class="sxs-lookup"><span data-stu-id="e3308-153">string</span></span> | <span data-ttu-id="e3308-154">イベントを開始したプロセス (画像ファイル) を含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="e3308-154">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="e3308-155">int</span><span class="sxs-lookup"><span data-stu-id="e3308-155">int</span></span> | <span data-ttu-id="e3308-156">イベントを担当するプロセスを発生させる親プロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="e3308-156">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="e3308-157">string</span><span class="sxs-lookup"><span data-stu-id="e3308-157">string</span></span> | <span data-ttu-id="e3308-158">イベントを処理するプロセスを生成した親プロセスの名前</span><span class="sxs-lookup"><span data-stu-id="e3308-158">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="e3308-159">日付型</span><span class="sxs-lookup"><span data-stu-id="e3308-159">datetime</span></span> | <span data-ttu-id="e3308-160">イベントを担当するプロセスの親が開始された日時</span><span class="sxs-lookup"><span data-stu-id="e3308-160">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="e3308-161">long</span><span class="sxs-lookup"><span data-stu-id="e3308-161">long</span></span> | <span data-ttu-id="e3308-162">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="e3308-162">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="e3308-163">一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3308-163">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="e3308-164">string</span><span class="sxs-lookup"><span data-stu-id="e3308-164">string</span></span> | <span data-ttu-id="e3308-165">Application Guard がブラウザーのアクティビティを分離するために使用する仮想化されたコンテナーの識別子</span><span class="sxs-lookup"><span data-stu-id="e3308-165">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e3308-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3308-166">Related topics</span></span>
- [<span data-ttu-id="e3308-167">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="e3308-167">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e3308-168">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="e3308-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e3308-169">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="e3308-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e3308-170">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="e3308-170">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e3308-171">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="e3308-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e3308-172">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="e3308-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
