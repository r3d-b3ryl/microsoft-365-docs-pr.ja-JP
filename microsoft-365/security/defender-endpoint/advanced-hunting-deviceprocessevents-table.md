---
title: 高度なハンティング スキーマの DeviceProcessEvents テーブル
description: 高度なハンティング スキーマの DeviceProcessEvents テーブルのプロセスの生成イベントまたは作成イベントについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、deviceprocessevents、process id、command line、ProcessCreationEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7fc2d6ecda35535f6af67aaaf90036ee44b9b79b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067051"
---
# <a name="deviceprocessevents"></a><span data-ttu-id="e2394-104">DeviceProcessEvents</span><span class="sxs-lookup"><span data-stu-id="e2394-104">DeviceProcessEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e2394-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e2394-105">**Applies to:**</span></span>
- [<span data-ttu-id="e2394-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e2394-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="e2394-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="e2394-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e2394-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="e2394-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="e2394-109">高度 `DeviceProcessEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、プロセスの作成と関連イベントに関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="e2394-109">The `DeviceProcessEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about process creation and related events.</span></span> <span data-ttu-id="e2394-110">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2394-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="e2394-111">高度なハンティング スキーマの他のテーブルの詳細については、高度なハンティング [スキーマリファレンスを参照してください](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="e2394-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="e2394-112">列名</span><span class="sxs-lookup"><span data-stu-id="e2394-112">Column name</span></span> | <span data-ttu-id="e2394-113">データ型</span><span class="sxs-lookup"><span data-stu-id="e2394-113">Data type</span></span> | <span data-ttu-id="e2394-114">説明</span><span class="sxs-lookup"><span data-stu-id="e2394-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e2394-115">日付型</span><span class="sxs-lookup"><span data-stu-id="e2394-115">datetime</span></span> | <span data-ttu-id="e2394-116">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="e2394-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="e2394-117">string</span><span class="sxs-lookup"><span data-stu-id="e2394-117">string</span></span> | <span data-ttu-id="e2394-118">サービス内のデバイスの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="e2394-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e2394-119">string</span><span class="sxs-lookup"><span data-stu-id="e2394-119">string</span></span> | <span data-ttu-id="e2394-120">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="e2394-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ActionType` | <span data-ttu-id="e2394-121">string</span><span class="sxs-lookup"><span data-stu-id="e2394-121">string</span></span> | <span data-ttu-id="e2394-122">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="e2394-122">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="e2394-123">文字列</span><span class="sxs-lookup"><span data-stu-id="e2394-123">string</span></span> | <span data-ttu-id="e2394-124">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="e2394-124">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="e2394-125">文字列</span><span class="sxs-lookup"><span data-stu-id="e2394-125">string</span></span> | <span data-ttu-id="e2394-126">記録されたアクションが適用されたファイルを含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="e2394-126">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="e2394-127">文字列</span><span class="sxs-lookup"><span data-stu-id="e2394-127">string</span></span> | <span data-ttu-id="e2394-128">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="e2394-128">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="e2394-129">文字列</span><span class="sxs-lookup"><span data-stu-id="e2394-129">string</span></span> | <span data-ttu-id="e2394-130">記録されたアクションが適用されたファイルの SHA-256</span><span class="sxs-lookup"><span data-stu-id="e2394-130">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="e2394-131">このフィールドは、通常は入力されません。使用可能な場合は SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2394-131">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `MD5` | <span data-ttu-id="e2394-132">string</span><span class="sxs-lookup"><span data-stu-id="e2394-132">string</span></span> | <span data-ttu-id="e2394-133">記録されたアクションが適用されたファイルの MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="e2394-133">MD5 hash of the file that the recorded action was applied to</span></span> |
| `ProcessId` | <span data-ttu-id="e2394-134">int</span><span class="sxs-lookup"><span data-stu-id="e2394-134">int</span></span> | <span data-ttu-id="e2394-135">新しく作成されたプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="e2394-135">Process ID (PID) of the newly created process</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="e2394-136">string</span><span class="sxs-lookup"><span data-stu-id="e2394-136">string</span></span> | <span data-ttu-id="e2394-137">新しいプロセスの作成に使用するコマンド ライン</span><span class="sxs-lookup"><span data-stu-id="e2394-137">Command line used to create the new process</span></span> |
| `ProcessIntegrityLevel` | <span data-ttu-id="e2394-138">string</span><span class="sxs-lookup"><span data-stu-id="e2394-138">string</span></span> | <span data-ttu-id="e2394-139">新しく作成されたプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="e2394-139">Integrity level of the newly created process.</span></span> <span data-ttu-id="e2394-140">Windows は、ダウンロードしたインターネットから起動された場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="e2394-140">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet downloaded.</span></span> <span data-ttu-id="e2394-141">これらの整合性レベルは、リソースへのアクセス許可に影響を与えます</span><span class="sxs-lookup"><span data-stu-id="e2394-141">These integrity levels influence permissions to resources</span></span> |
| `ProcessTokenElevation` | <span data-ttu-id="e2394-142">string</span><span class="sxs-lookup"><span data-stu-id="e2394-142">string</span></span> | <span data-ttu-id="e2394-143">新しく作成されたプロセスに適用されるユーザー アクセス制御 (UAC) 特権昇格の有無を示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="e2394-143">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the newly created process</span></span> |
| `ProcessCreationTime` | <span data-ttu-id="e2394-144">日付型</span><span class="sxs-lookup"><span data-stu-id="e2394-144">datetime</span></span> | <span data-ttu-id="e2394-145">プロセスが作成された日時</span><span class="sxs-lookup"><span data-stu-id="e2394-145">Date and time the process was created</span></span> |
| `AccountDomain` | <span data-ttu-id="e2394-146">string</span><span class="sxs-lookup"><span data-stu-id="e2394-146">string</span></span> | <span data-ttu-id="e2394-147">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="e2394-147">Domain of the account</span></span> |
| `AccountName` | <span data-ttu-id="e2394-148">string</span><span class="sxs-lookup"><span data-stu-id="e2394-148">string</span></span> | <span data-ttu-id="e2394-149">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="e2394-149">User name of the account</span></span> |
| `AccountSid` | <span data-ttu-id="e2394-150">string</span><span class="sxs-lookup"><span data-stu-id="e2394-150">string</span></span> | <span data-ttu-id="e2394-151">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="e2394-151">Security Identifier (SID) of the account</span></span> |
| `LogonId` | <span data-ttu-id="e2394-152">string</span><span class="sxs-lookup"><span data-stu-id="e2394-152">string</span></span> | <span data-ttu-id="e2394-153">ログオン セッションの識別子。</span><span class="sxs-lookup"><span data-stu-id="e2394-153">Identifier for a logon session.</span></span> <span data-ttu-id="e2394-154">この識別子は、再起動の間にのみ同じデバイスで一意です</span><span class="sxs-lookup"><span data-stu-id="e2394-154">This identifier is unique on the same device only between restarts</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="e2394-155">string</span><span class="sxs-lookup"><span data-stu-id="e2394-155">string</span></span> | <span data-ttu-id="e2394-156">イベントを担当するプロセスを実行したアカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="e2394-156">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="e2394-157">string</span><span class="sxs-lookup"><span data-stu-id="e2394-157">string</span></span> | <span data-ttu-id="e2394-158">イベントを担当するプロセスを実行したアカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="e2394-158">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="e2394-159">string</span><span class="sxs-lookup"><span data-stu-id="e2394-159">string</span></span> | <span data-ttu-id="e2394-160">イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="e2394-160">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessLogonId` | <span data-ttu-id="e2394-161">string</span><span class="sxs-lookup"><span data-stu-id="e2394-161">string</span></span> | <span data-ttu-id="e2394-162">イベントを開始したプロセスのログオン セッションの識別子。</span><span class="sxs-lookup"><span data-stu-id="e2394-162">Identifier for a logon session of the process that initiated the event.</span></span> <span data-ttu-id="e2394-163">この識別子は、再起動の間にのみ同じデバイスで一意です。</span><span class="sxs-lookup"><span data-stu-id="e2394-163">This identifier is unique on the same device only between restarts.</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="e2394-164">string</span><span class="sxs-lookup"><span data-stu-id="e2394-164">string</span></span> | <span data-ttu-id="e2394-165">イベントを開始したプロセスの整合性レベル。</span><span class="sxs-lookup"><span data-stu-id="e2394-165">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="e2394-166">Windows は、インターネットダウンロードから起動された場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="e2394-166">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="e2394-167">これらの整合性レベルは、リソースへのアクセス許可に影響を与えます</span><span class="sxs-lookup"><span data-stu-id="e2394-167">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="e2394-168">string</span><span class="sxs-lookup"><span data-stu-id="e2394-168">string</span></span> | <span data-ttu-id="e2394-169">イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権昇格の有無を示すトークンの種類</span><span class="sxs-lookup"><span data-stu-id="e2394-169">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="e2394-170">string</span><span class="sxs-lookup"><span data-stu-id="e2394-170">string</span></span> | <span data-ttu-id="e2394-171">イベントを開始したプロセス (イメージ ファイル) の SHA-1</span><span class="sxs-lookup"><span data-stu-id="e2394-171">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="e2394-172">string</span><span class="sxs-lookup"><span data-stu-id="e2394-172">string</span></span> | <span data-ttu-id="e2394-173">イベントを開始したプロセス (イメージ ファイル) の SHA-256。</span><span class="sxs-lookup"><span data-stu-id="e2394-173">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="e2394-174">このフィールドは、通常は設定されません。使用可能な場合は SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2394-174">This field is usually not populated—use the SHA1 column when available</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="e2394-175">string</span><span class="sxs-lookup"><span data-stu-id="e2394-175">string</span></span> | <span data-ttu-id="e2394-176">イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="e2394-176">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="e2394-177">string</span><span class="sxs-lookup"><span data-stu-id="e2394-177">string</span></span> | <span data-ttu-id="e2394-178">イベントを開始したプロセスの名前</span><span class="sxs-lookup"><span data-stu-id="e2394-178">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="e2394-179">int</span><span class="sxs-lookup"><span data-stu-id="e2394-179">int</span></span> | <span data-ttu-id="e2394-180">イベントを開始したプロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="e2394-180">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="e2394-181">string</span><span class="sxs-lookup"><span data-stu-id="e2394-181">string</span></span> | <span data-ttu-id="e2394-182">イベントを開始したプロセスの実行に使用されるコマンド ライン</span><span class="sxs-lookup"><span data-stu-id="e2394-182">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="e2394-183">日付型</span><span class="sxs-lookup"><span data-stu-id="e2394-183">datetime</span></span> | <span data-ttu-id="e2394-184">イベントを開始したプロセスが開始された日時</span><span class="sxs-lookup"><span data-stu-id="e2394-184">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="e2394-185">string</span><span class="sxs-lookup"><span data-stu-id="e2394-185">string</span></span> | <span data-ttu-id="e2394-186">イベントを開始したプロセス (イメージ ファイル) を含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="e2394-186">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="e2394-187">int</span><span class="sxs-lookup"><span data-stu-id="e2394-187">int</span></span> | <span data-ttu-id="e2394-188">イベントを担当するプロセスを生成した親プロセスのプロセス ID (PID)</span><span class="sxs-lookup"><span data-stu-id="e2394-188">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="e2394-189">string</span><span class="sxs-lookup"><span data-stu-id="e2394-189">string</span></span> | <span data-ttu-id="e2394-190">イベントを担当するプロセスを生成した親プロセスの名前</span><span class="sxs-lookup"><span data-stu-id="e2394-190">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="e2394-191">日付型</span><span class="sxs-lookup"><span data-stu-id="e2394-191">datetime</span></span> | <span data-ttu-id="e2394-192">イベントを担当するプロセスの親が開始された日時</span><span class="sxs-lookup"><span data-stu-id="e2394-192">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="e2394-193">long</span><span class="sxs-lookup"><span data-stu-id="e2394-193">long</span></span> | <span data-ttu-id="e2394-194">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="e2394-194">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="e2394-195">一意のイベントを識別するには、この列を and 列と組み合わせて `DeviceName` 使用する必要 `Timestamp` があります。</span><span class="sxs-lookup"><span data-stu-id="e2394-195">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="e2394-196">string</span><span class="sxs-lookup"><span data-stu-id="e2394-196">string</span></span> | <span data-ttu-id="e2394-197">ブラウザーのアクティビティを分離するために Application Guard が使用する仮想化コンテナーの識別子</span><span class="sxs-lookup"><span data-stu-id="e2394-197">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e2394-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2394-198">Related topics</span></span>
- [<span data-ttu-id="e2394-199">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="e2394-199">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e2394-200">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="e2394-200">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e2394-201">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="e2394-201">Understand the schema</span></span>](advanced-hunting-schema-reference.md)