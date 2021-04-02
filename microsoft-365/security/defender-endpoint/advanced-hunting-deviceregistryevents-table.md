---
title: 高度な検索スキーマの DeviceRegistryEvents テーブル
description: 高度なハンティング スキーマの DeviceRegistryEvents テーブルからクエリできるレジストリ イベントについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、deviceregistryevents、レジストリ、キー、サブキー、値、RegistryEvents
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
ms.openlocfilehash: 31fe2bb882bc59eb516773c0c319b1f25f56a95e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498761"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="f54d0-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="f54d0-104">DeviceRegistryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f54d0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f54d0-105">**Applies to:**</span></span>
- [<span data-ttu-id="f54d0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f54d0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="f54d0-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="f54d0-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f54d0-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="f54d0-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="f54d0-109">高度 `DeviceRegistryEvents` な検索スキーマ [の表](advanced-hunting-overview.md) には、レジストリ エントリの作成と変更に関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="f54d0-109">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="f54d0-110">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f54d0-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="f54d0-111">高度なハンティング スキーマの他のテーブルの詳細については、高度なハンティング [スキーマリファレンスを参照してください](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="f54d0-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="f54d0-112">列名</span><span class="sxs-lookup"><span data-stu-id="f54d0-112">Column name</span></span> | <span data-ttu-id="f54d0-113">データ型</span><span class="sxs-lookup"><span data-stu-id="f54d0-113">Data type</span></span> | <span data-ttu-id="f54d0-114">説明</span><span class="sxs-lookup"><span data-stu-id="f54d0-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f54d0-115">日付型</span><span class="sxs-lookup"><span data-stu-id="f54d0-115">datetime</span></span> | <span data-ttu-id="f54d0-116">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="f54d0-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="f54d0-117">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-117">string</span></span> | <span data-ttu-id="f54d0-118">サービス内のデバイスの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="f54d0-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f54d0-119">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-119">string</span></span> | <span data-ttu-id="f54d0-120">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="f54d0-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ActionType` | <span data-ttu-id="f54d0-121">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-121">string</span></span> | <span data-ttu-id="f54d0-122">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="f54d0-122">Type of activity that triggered the event</span></span> |
| `RegistryKey` | <span data-ttu-id="f54d0-123">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-123">string</span></span> | <span data-ttu-id="f54d0-124">記録されたアクションが適用されたレジストリ キー</span><span class="sxs-lookup"><span data-stu-id="f54d0-124">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="f54d0-125">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-125">string</span></span> | <span data-ttu-id="f54d0-126">記録されたアクションが適用されたレジストリ値のデータ型 (バイナリや文字列など)</span><span class="sxs-lookup"><span data-stu-id="f54d0-126">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="f54d0-127">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-127">string</span></span> | <span data-ttu-id="f54d0-128">記録されたアクションが適用されたレジストリ値の名前</span><span class="sxs-lookup"><span data-stu-id="f54d0-128">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="f54d0-129">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-129">string</span></span> | <span data-ttu-id="f54d0-130">記録されたアクションが適用されたレジストリ値のデータ</span><span class="sxs-lookup"><span data-stu-id="f54d0-130">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="f54d0-131">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-131">string</span></span> | <span data-ttu-id="f54d0-132">変更前のレジストリ値の元の名前</span><span class="sxs-lookup"><span data-stu-id="f54d0-132">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="f54d0-133">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-133">string</span></span> | <span data-ttu-id="f54d0-134">変更前のレジストリ値の元のデータ</span><span class="sxs-lookup"><span data-stu-id="f54d0-134">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="f54d0-135">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-135">string</span></span> | <span data-ttu-id="f54d0-136">イベントを担当するプロセスを実行したアカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="f54d0-136">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="f54d0-137">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-137">string</span></span> | <span data-ttu-id="f54d0-138">イベントを担当するプロセスを実行したアカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="f54d0-138">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="f54d0-139">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-139">string</span></span> | <span data-ttu-id="f54d0-140">イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="f54d0-140">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="f54d0-141">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-141">string</span></span> | <span data-ttu-id="f54d0-142">イベントを開始したプロセス (イメージ ファイル) の SHA-1</span><span class="sxs-lookup"><span data-stu-id="f54d0-142">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="f54d0-143">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-143">string</span></span> | <span data-ttu-id="f54d0-144">イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="f54d0-144">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="f54d0-145">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-145">string</span></span> | <span data-ttu-id="f54d0-146">イベントを開始したプロセスの名前</span><span class="sxs-lookup"><span data-stu-id="f54d0-146">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="f54d0-147">int</span><span class="sxs-lookup"><span data-stu-id="f54d0-147">int</span></span> | <span data-ttu-id="f54d0-148">イベントを開始したプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="f54d0-148">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="f54d0-149">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-149">string</span></span> | <span data-ttu-id="f54d0-150">イベントを開始したプロセスの実行に使用されるコマンド ライン</span><span class="sxs-lookup"><span data-stu-id="f54d0-150">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="f54d0-151">日付型</span><span class="sxs-lookup"><span data-stu-id="f54d0-151">datetime</span></span> | <span data-ttu-id="f54d0-152">イベントを開始したプロセスが開始された日時</span><span class="sxs-lookup"><span data-stu-id="f54d0-152">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="f54d0-153">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-153">string</span></span> | <span data-ttu-id="f54d0-154">イベントを開始したプロセス (イメージ ファイル) を含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="f54d0-154">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="f54d0-155">int</span><span class="sxs-lookup"><span data-stu-id="f54d0-155">int</span></span> | <span data-ttu-id="f54d0-156">イベントを担当するプロセスを生成した親プロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="f54d0-156">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="f54d0-157">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-157">string</span></span> | <span data-ttu-id="f54d0-158">イベントを担当するプロセスを生成した親プロセスの名前</span><span class="sxs-lookup"><span data-stu-id="f54d0-158">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="f54d0-159">日付型</span><span class="sxs-lookup"><span data-stu-id="f54d0-159">datetime</span></span> | <span data-ttu-id="f54d0-160">イベントを担当するプロセスの親が開始された日時</span><span class="sxs-lookup"><span data-stu-id="f54d0-160">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="f54d0-161">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-161">string</span></span> | <span data-ttu-id="f54d0-162">イベントを開始したプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="f54d0-162">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="f54d0-163">Windows は、インターネットダウンロードから起動された場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="f54d0-163">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="f54d0-164">これらの整合性レベルは、リソースへのアクセス許可に影響を与えます</span><span class="sxs-lookup"><span data-stu-id="f54d0-164">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="f54d0-165">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-165">string</span></span> | <span data-ttu-id="f54d0-166">イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権昇格の有無を示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="f54d0-166">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="f54d0-167">long</span><span class="sxs-lookup"><span data-stu-id="f54d0-167">long</span></span> | <span data-ttu-id="f54d0-168">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="f54d0-168">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="f54d0-169">一意のイベントを識別するには、この列を and 列と組み合わせて `DeviceName` 使用する必要 `Timestamp` があります。</span><span class="sxs-lookup"><span data-stu-id="f54d0-169">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="f54d0-170">文字列</span><span class="sxs-lookup"><span data-stu-id="f54d0-170">string</span></span> | <span data-ttu-id="f54d0-171">ブラウザーのアクティビティを分離するために Application Guard が使用する仮想化コンテナーの識別子</span><span class="sxs-lookup"><span data-stu-id="f54d0-171">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f54d0-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="f54d0-172">Related topics</span></span>
- [<span data-ttu-id="f54d0-173">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="f54d0-173">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f54d0-174">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="f54d0-174">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f54d0-175">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="f54d0-175">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
