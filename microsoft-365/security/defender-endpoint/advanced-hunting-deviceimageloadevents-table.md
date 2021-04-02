---
title: 高度なハンティング スキーマの DeviceImageLoadEvents テーブル
description: 高度なハンティング スキーマの DeviceImageLoadEvents テーブルの DLL 読み込みイベントについて説明します。
keywords: 高度なハンティング、脅威の検出、サイバー脅威の検出、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、deviceimageloadevents、DLL 読み込み、ライブラリ、ファイル イメージ、ImageLoadEvents
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
ms.openlocfilehash: b47996da16b131d1739acd26519447b9167870ec
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498789"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="a3eda-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="a3eda-104">DeviceImageLoadEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a3eda-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a3eda-105">**Applies to:**</span></span>
- [<span data-ttu-id="a3eda-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a3eda-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="a3eda-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="a3eda-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a3eda-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="a3eda-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="a3eda-109">高度 `DeviceImageLoadEvents` な検索スキーマの [表には](advanced-hunting-overview.md) 、DLL 読み込みイベントに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3eda-109">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="a3eda-110">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3eda-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="a3eda-111">高度なハンティング スキーマの他のテーブルの詳細については、高度なハンティング [スキーマリファレンスを参照してください](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="a3eda-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="a3eda-112">列名</span><span class="sxs-lookup"><span data-stu-id="a3eda-112">Column name</span></span> | <span data-ttu-id="a3eda-113">データ型</span><span class="sxs-lookup"><span data-stu-id="a3eda-113">Data type</span></span> | <span data-ttu-id="a3eda-114">説明</span><span class="sxs-lookup"><span data-stu-id="a3eda-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a3eda-115">日付型</span><span class="sxs-lookup"><span data-stu-id="a3eda-115">datetime</span></span> | <span data-ttu-id="a3eda-116">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="a3eda-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="a3eda-117">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-117">string</span></span> | <span data-ttu-id="a3eda-118">サービス内のデバイスの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="a3eda-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a3eda-119">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-119">string</span></span> | <span data-ttu-id="a3eda-120">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="a3eda-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ActionType` | <span data-ttu-id="a3eda-121">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-121">string</span></span> | <span data-ttu-id="a3eda-122">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="a3eda-122">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="a3eda-123">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-123">string</span></span> | <span data-ttu-id="a3eda-124">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="a3eda-124">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="a3eda-125">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-125">string</span></span> | <span data-ttu-id="a3eda-126">記録されたアクションが適用されたファイルを含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="a3eda-126">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="a3eda-127">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-127">string</span></span> | <span data-ttu-id="a3eda-128">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="a3eda-128">SHA-1 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="a3eda-129">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-129">string</span></span> | <span data-ttu-id="a3eda-130">記録されたアクションが適用されたファイルの MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="a3eda-130">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="a3eda-131">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-131">string</span></span> | <span data-ttu-id="a3eda-132">イベントを担当するプロセスを実行したアカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="a3eda-132">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="a3eda-133">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-133">string</span></span> | <span data-ttu-id="a3eda-134">イベントを担当するプロセスを実行したアカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="a3eda-134">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="a3eda-135">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-135">string</span></span> | <span data-ttu-id="a3eda-136">イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="a3eda-136">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="a3eda-137">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-137">string</span></span> | <span data-ttu-id="a3eda-138">イベントを開始したプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="a3eda-138">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="a3eda-139">Windows は、インターネットダウンロードから起動された場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="a3eda-139">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="a3eda-140">これらの整合性レベルは、リソースへのアクセス許可に影響を与えます</span><span class="sxs-lookup"><span data-stu-id="a3eda-140">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="a3eda-141">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-141">string</span></span> | <span data-ttu-id="a3eda-142">イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権昇格の有無を示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="a3eda-142">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="a3eda-143">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-143">string</span></span> | <span data-ttu-id="a3eda-144">イベントを開始したプロセス (イメージ ファイル) の SHA-1</span><span class="sxs-lookup"><span data-stu-id="a3eda-144">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="a3eda-145">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-145">string</span></span> | <span data-ttu-id="a3eda-146">イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="a3eda-146">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="a3eda-147">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-147">string</span></span> | <span data-ttu-id="a3eda-148">イベントを開始したプロセスの名前</span><span class="sxs-lookup"><span data-stu-id="a3eda-148">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="a3eda-149">int</span><span class="sxs-lookup"><span data-stu-id="a3eda-149">int</span></span> | <span data-ttu-id="a3eda-150">イベントを開始したプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="a3eda-150">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="a3eda-151">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-151">string</span></span> | <span data-ttu-id="a3eda-152">イベントを開始したプロセスの実行に使用されるコマンド ライン</span><span class="sxs-lookup"><span data-stu-id="a3eda-152">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="a3eda-153">日付型</span><span class="sxs-lookup"><span data-stu-id="a3eda-153">datetime</span></span> | <span data-ttu-id="a3eda-154">イベントを開始したプロセスが開始された日時</span><span class="sxs-lookup"><span data-stu-id="a3eda-154">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="a3eda-155">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-155">string</span></span> | <span data-ttu-id="a3eda-156">イベントを開始したプロセス (イメージ ファイル) を含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="a3eda-156">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="a3eda-157">int</span><span class="sxs-lookup"><span data-stu-id="a3eda-157">int</span></span> | <span data-ttu-id="a3eda-158">イベントを担当するプロセスを生成した親プロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="a3eda-158">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="a3eda-159">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-159">string</span></span> | <span data-ttu-id="a3eda-160">イベントを担当するプロセスを生成した親プロセスの名前</span><span class="sxs-lookup"><span data-stu-id="a3eda-160">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="a3eda-161">日付型</span><span class="sxs-lookup"><span data-stu-id="a3eda-161">datetime</span></span> | <span data-ttu-id="a3eda-162">イベントを担当するプロセスの親が開始された日時</span><span class="sxs-lookup"><span data-stu-id="a3eda-162">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="a3eda-163">long</span><span class="sxs-lookup"><span data-stu-id="a3eda-163">long</span></span> | <span data-ttu-id="a3eda-164">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="a3eda-164">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="a3eda-165">一意のイベントを識別するには、この列を and 列と組み合わせて `DeviceName` 使用する必要 `Timestamp` があります。</span><span class="sxs-lookup"><span data-stu-id="a3eda-165">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="a3eda-166">文字列</span><span class="sxs-lookup"><span data-stu-id="a3eda-166">string</span></span> | <span data-ttu-id="a3eda-167">ブラウザーのアクティビティを分離するために Application Guard が使用する仮想化コンテナーの識別子</span><span class="sxs-lookup"><span data-stu-id="a3eda-167">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a3eda-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3eda-168">Related topics</span></span>
- [<span data-ttu-id="a3eda-169">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="a3eda-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a3eda-170">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="a3eda-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a3eda-171">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="a3eda-171">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
