---
title: 高度な検索スキーマの AlertEvidence テーブル
description: 高度な検索スキーマの AlertEvidence テーブルのアラートに関連する情報について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、AlertInfo、アラート、エンティティ、証拠、ファイル、IP アドレス、デバイス、コンピューター、ユーザー、アカウント
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
ms.openlocfilehash: c01b0aae1eff3d9b4add632aff0f13cb56941a30
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932306"
---
# <a name="alertevidence"></a><span data-ttu-id="02cbe-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="02cbe-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="02cbe-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="02cbe-105">**Applies to:**</span></span>
- <span data-ttu-id="02cbe-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02cbe-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="02cbe-107">高度な検索スキーマの表には `AlertEvidence` 、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security、および Microsoft Defender for Identity からのアラートに関連付けられたさまざまなエンティティ (ファイル、IP[](advanced-hunting-overview.md)アドレス、URL、ユーザー、デバイス) に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="02cbe-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="02cbe-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="02cbe-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="02cbe-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02cbe-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="02cbe-110">列名</span><span class="sxs-lookup"><span data-stu-id="02cbe-110">Column name</span></span> | <span data-ttu-id="02cbe-111">データ型</span><span class="sxs-lookup"><span data-stu-id="02cbe-111">Data type</span></span> | <span data-ttu-id="02cbe-112">説明</span><span class="sxs-lookup"><span data-stu-id="02cbe-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="02cbe-113">日付型</span><span class="sxs-lookup"><span data-stu-id="02cbe-113">datetime</span></span> | <span data-ttu-id="02cbe-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="02cbe-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="02cbe-115">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-115">string</span></span> | <span data-ttu-id="02cbe-116">アラートの一意識別子</span><span class="sxs-lookup"><span data-stu-id="02cbe-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="02cbe-117">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-117">string</span></span> | <span data-ttu-id="02cbe-118">アラート情報を提供した製品またはサービス</span><span class="sxs-lookup"><span data-stu-id="02cbe-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="02cbe-119">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-119">string</span></span> | <span data-ttu-id="02cbe-120">ファイル、プロセス、デバイス、ユーザーなどのオブジェクトの種類</span><span class="sxs-lookup"><span data-stu-id="02cbe-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="02cbe-121">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-121">string</span></span> | <span data-ttu-id="02cbe-122">エンティティがアラートに関与する方法(影響を受け取ったのか、単に関連しているだけなのかを示す)</span><span class="sxs-lookup"><span data-stu-id="02cbe-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="02cbe-123">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-123">string</span></span> | <span data-ttu-id="02cbe-124">エンティティがネットワーク接続の送信元か宛先かを示します。</span><span class="sxs-lookup"><span data-stu-id="02cbe-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="02cbe-125">文字列</span><span class="sxs-lookup"><span data-stu-id="02cbe-125">string</span></span> | <span data-ttu-id="02cbe-126">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="02cbe-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="02cbe-127">文字列</span><span class="sxs-lookup"><span data-stu-id="02cbe-127">string</span></span> | <span data-ttu-id="02cbe-128">記録されたアクションが適用されたファイルを含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="02cbe-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="02cbe-129">文字列</span><span class="sxs-lookup"><span data-stu-id="02cbe-129">string</span></span> | <span data-ttu-id="02cbe-130">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="02cbe-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="02cbe-131">文字列</span><span class="sxs-lookup"><span data-stu-id="02cbe-131">string</span></span> | <span data-ttu-id="02cbe-132">記録されたアクションが適用されたファイルの SHA-256</span><span class="sxs-lookup"><span data-stu-id="02cbe-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="02cbe-133">このフィールドは、通常は入力されません。使用可能な場合は、SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="02cbe-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="02cbe-134">int</span><span class="sxs-lookup"><span data-stu-id="02cbe-134">int</span></span> | <span data-ttu-id="02cbe-135">ファイルのサイズ (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="02cbe-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="02cbe-136">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-136">string</span></span> | <span data-ttu-id="02cbe-137">疑わしいファイルまたは悪意のあるファイルまたはプロセスが分類されたマルウェア ファミリ</span><span class="sxs-lookup"><span data-stu-id="02cbe-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="02cbe-138">文字列</span><span class="sxs-lookup"><span data-stu-id="02cbe-138">string</span></span> | <span data-ttu-id="02cbe-139">に接続されていた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="02cbe-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="02cbe-140">文字列</span><span class="sxs-lookup"><span data-stu-id="02cbe-140">string</span></span> | <span data-ttu-id="02cbe-141">に接続されていた URL または完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="02cbe-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="02cbe-142">文字列</span><span class="sxs-lookup"><span data-stu-id="02cbe-142">string</span></span> | <span data-ttu-id="02cbe-143">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="02cbe-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="02cbe-144">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-144">string</span></span> | <span data-ttu-id="02cbe-145">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="02cbe-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="02cbe-146">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-146">string</span></span> | <span data-ttu-id="02cbe-147">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="02cbe-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="02cbe-148">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-148">string</span></span> | <span data-ttu-id="02cbe-149">Azure Active Directory のアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="02cbe-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="02cbe-150">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-150">string</span></span> | <span data-ttu-id="02cbe-151">サービス内のデバイスの一意識別子</span><span class="sxs-lookup"><span data-stu-id="02cbe-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="02cbe-152">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-152">string</span></span> | <span data-ttu-id="02cbe-153">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="02cbe-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="02cbe-154">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-154">string</span></span> | <span data-ttu-id="02cbe-155">通信中に使用されるローカル デバイスに割り当てられた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="02cbe-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="02cbe-156">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-156">string</span></span> | <span data-ttu-id="02cbe-157">Office 365 により生成されたメールの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="02cbe-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="02cbe-158">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-158">string</span></span> | <span data-ttu-id="02cbe-159">メールの件名</span><span class="sxs-lookup"><span data-stu-id="02cbe-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="02cbe-160">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-160">string</span></span> | <span data-ttu-id="02cbe-161">アプリケーションの一意識別子</span><span class="sxs-lookup"><span data-stu-id="02cbe-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="02cbe-162">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-162">string</span></span> | <span data-ttu-id="02cbe-163">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="02cbe-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="02cbe-164">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-164">string</span></span> | <span data-ttu-id="02cbe-165">新しいプロセスの作成に使用するコマンド ライン</span><span class="sxs-lookup"><span data-stu-id="02cbe-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="02cbe-166">string</span><span class="sxs-lookup"><span data-stu-id="02cbe-166">string</span></span> | <span data-ttu-id="02cbe-167">JSON 配列形式でのイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="02cbe-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="02cbe-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="02cbe-168">Related topics</span></span>
- [<span data-ttu-id="02cbe-169">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="02cbe-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="02cbe-170">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="02cbe-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="02cbe-171">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="02cbe-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="02cbe-172">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="02cbe-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="02cbe-173">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="02cbe-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="02cbe-174">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="02cbe-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
