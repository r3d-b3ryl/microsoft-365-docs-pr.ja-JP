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
ms.openlocfilehash: 7457084d49c5a9fef4ef79abc7702c6b473efcd2
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145303"
---
# <a name="alertevidence"></a><span data-ttu-id="2b556-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="2b556-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2b556-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2b556-105">**Applies to:**</span></span>
- <span data-ttu-id="2b556-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b556-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2b556-107">高度な検索スキーマの表には `AlertEvidence` 、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security、および Microsoft Defender for Identity からのアラートに関連付けられたさまざまなエンティティ (ファイル、IP[](advanced-hunting-overview.md)アドレス、URL、ユーザー、またはデバイス) に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b556-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="2b556-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="2b556-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="2b556-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b556-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2b556-110">列名</span><span class="sxs-lookup"><span data-stu-id="2b556-110">Column name</span></span> | <span data-ttu-id="2b556-111">データ型</span><span class="sxs-lookup"><span data-stu-id="2b556-111">Data type</span></span> | <span data-ttu-id="2b556-112">説明</span><span class="sxs-lookup"><span data-stu-id="2b556-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2b556-113">日付型</span><span class="sxs-lookup"><span data-stu-id="2b556-113">datetime</span></span> | <span data-ttu-id="2b556-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="2b556-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="2b556-115">string</span><span class="sxs-lookup"><span data-stu-id="2b556-115">string</span></span> | <span data-ttu-id="2b556-116">アラートの一意識別子</span><span class="sxs-lookup"><span data-stu-id="2b556-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="2b556-117">string</span><span class="sxs-lookup"><span data-stu-id="2b556-117">string</span></span> | <span data-ttu-id="2b556-118">アラート情報を提供した製品またはサービス</span><span class="sxs-lookup"><span data-stu-id="2b556-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="2b556-119">string</span><span class="sxs-lookup"><span data-stu-id="2b556-119">string</span></span> | <span data-ttu-id="2b556-120">ファイル、プロセス、デバイス、ユーザーなどのオブジェクトの種類</span><span class="sxs-lookup"><span data-stu-id="2b556-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="2b556-121">string</span><span class="sxs-lookup"><span data-stu-id="2b556-121">string</span></span> | <span data-ttu-id="2b556-122">エンティティがアラートに関与する方法(影響を受け取ったのか、単に関連しているだけなのかを示す)</span><span class="sxs-lookup"><span data-stu-id="2b556-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="2b556-123">string</span><span class="sxs-lookup"><span data-stu-id="2b556-123">string</span></span> | <span data-ttu-id="2b556-124">エンティティがネットワーク接続の送信元か宛先かを示します。</span><span class="sxs-lookup"><span data-stu-id="2b556-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="2b556-125">文字列</span><span class="sxs-lookup"><span data-stu-id="2b556-125">string</span></span> | <span data-ttu-id="2b556-126">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="2b556-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="2b556-127">文字列</span><span class="sxs-lookup"><span data-stu-id="2b556-127">string</span></span> | <span data-ttu-id="2b556-128">記録されたアクションが適用されたファイルを含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="2b556-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="2b556-129">文字列</span><span class="sxs-lookup"><span data-stu-id="2b556-129">string</span></span> | <span data-ttu-id="2b556-130">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="2b556-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="2b556-131">文字列</span><span class="sxs-lookup"><span data-stu-id="2b556-131">string</span></span> | <span data-ttu-id="2b556-132">記録されたアクションが適用されたファイルの SHA-256</span><span class="sxs-lookup"><span data-stu-id="2b556-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="2b556-133">このフィールドは、通常は入力されません。使用可能な場合は、SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="2b556-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="2b556-134">int</span><span class="sxs-lookup"><span data-stu-id="2b556-134">int</span></span> | <span data-ttu-id="2b556-135">ファイルのサイズ (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="2b556-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="2b556-136">string</span><span class="sxs-lookup"><span data-stu-id="2b556-136">string</span></span> | <span data-ttu-id="2b556-137">疑わしいファイルまたは悪意のあるファイルまたはプロセスが分類されたマルウェア ファミリ</span><span class="sxs-lookup"><span data-stu-id="2b556-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="2b556-138">文字列</span><span class="sxs-lookup"><span data-stu-id="2b556-138">string</span></span> | <span data-ttu-id="2b556-139">に接続されていた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="2b556-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="2b556-140">文字列</span><span class="sxs-lookup"><span data-stu-id="2b556-140">string</span></span> | <span data-ttu-id="2b556-141">に接続されていた URL または完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="2b556-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="2b556-142">文字列</span><span class="sxs-lookup"><span data-stu-id="2b556-142">string</span></span> | <span data-ttu-id="2b556-143">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="2b556-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="2b556-144">string</span><span class="sxs-lookup"><span data-stu-id="2b556-144">string</span></span> | <span data-ttu-id="2b556-145">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="2b556-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="2b556-146">string</span><span class="sxs-lookup"><span data-stu-id="2b556-146">string</span></span> | <span data-ttu-id="2b556-147">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="2b556-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="2b556-148">string</span><span class="sxs-lookup"><span data-stu-id="2b556-148">string</span></span> | <span data-ttu-id="2b556-149">Azure Active Directory のアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="2b556-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountUpn` | <span data-ttu-id="2b556-150">string</span><span class="sxs-lookup"><span data-stu-id="2b556-150">string</span></span> | <span data-ttu-id="2b556-151">アカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="2b556-151">User principal name (UPN) of the account</span></span> |
| `DeviceId` | <span data-ttu-id="2b556-152">string</span><span class="sxs-lookup"><span data-stu-id="2b556-152">string</span></span> | <span data-ttu-id="2b556-153">サービス内のデバイスの一意識別子</span><span class="sxs-lookup"><span data-stu-id="2b556-153">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2b556-154">string</span><span class="sxs-lookup"><span data-stu-id="2b556-154">string</span></span> | <span data-ttu-id="2b556-155">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="2b556-155">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="2b556-156">string</span><span class="sxs-lookup"><span data-stu-id="2b556-156">string</span></span> | <span data-ttu-id="2b556-157">通信中に使用されるローカル デバイスに割り当てられた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="2b556-157">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="2b556-158">string</span><span class="sxs-lookup"><span data-stu-id="2b556-158">string</span></span> | <span data-ttu-id="2b556-159">Office 365 により生成されたメールの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="2b556-159">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="2b556-160">string</span><span class="sxs-lookup"><span data-stu-id="2b556-160">string</span></span> | <span data-ttu-id="2b556-161">メールの件名</span><span class="sxs-lookup"><span data-stu-id="2b556-161">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="2b556-162">string</span><span class="sxs-lookup"><span data-stu-id="2b556-162">string</span></span> | <span data-ttu-id="2b556-163">アプリケーションの一意識別子</span><span class="sxs-lookup"><span data-stu-id="2b556-163">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="2b556-164">string</span><span class="sxs-lookup"><span data-stu-id="2b556-164">string</span></span> | <span data-ttu-id="2b556-165">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="2b556-165">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="2b556-166">string</span><span class="sxs-lookup"><span data-stu-id="2b556-166">string</span></span> | <span data-ttu-id="2b556-167">新しいプロセスの作成に使用するコマンド ライン</span><span class="sxs-lookup"><span data-stu-id="2b556-167">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="2b556-168">string</span><span class="sxs-lookup"><span data-stu-id="2b556-168">string</span></span> | <span data-ttu-id="2b556-169">JSON 配列形式でのイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="2b556-169">Additional information about the event in JSON array format</span></span> |
| `RegistryKey` |<span data-ttu-id="2b556-170">string</span><span class="sxs-lookup"><span data-stu-id="2b556-170">string</span></span> | <span data-ttu-id="2b556-171">記録されたアクションが適用されたレジストリ キー</span><span class="sxs-lookup"><span data-stu-id="2b556-171">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueName` |<span data-ttu-id="2b556-172">string</span><span class="sxs-lookup"><span data-stu-id="2b556-172">string</span></span> | <span data-ttu-id="2b556-173">記録されたアクションが適用されたレジストリ値の名前</span><span class="sxs-lookup"><span data-stu-id="2b556-173">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` |<span data-ttu-id="2b556-174">string</span><span class="sxs-lookup"><span data-stu-id="2b556-174">string</span></span> | <span data-ttu-id="2b556-175">記録されたアクションが適用されたレジストリ値のデータ</span><span class="sxs-lookup"><span data-stu-id="2b556-175">Data of the registry value that the recorded action was applied to</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2b556-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b556-176">Related topics</span></span>
- [<span data-ttu-id="2b556-177">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="2b556-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2b556-178">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="2b556-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2b556-179">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="2b556-179">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2b556-180">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="2b556-180">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2b556-181">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="2b556-181">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2b556-182">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="2b556-182">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
