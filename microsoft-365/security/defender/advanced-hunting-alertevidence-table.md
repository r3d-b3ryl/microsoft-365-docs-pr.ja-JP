---
title: 高度な検索スキーマの AlertEvidence テーブル
description: 高度な検索スキーマの AlertEvidence テーブルのアラートに関連付けられている情報について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、AlertInfo、アラート、エンティティ、証拠、ファイル、IP アドレス、デバイス、コンピューター、ユーザー、アカウント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5ecab217a6181096e4689d78fa2bdddc0a767d0d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932585"
---
# <a name="alertevidence"></a><span data-ttu-id="644e5-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="644e5-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="644e5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="644e5-105">**Applies to:**</span></span>
- <span data-ttu-id="644e5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="644e5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="644e5-107">高度な検索スキーマの表には `AlertEvidence` 、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security、および Microsoft Defender for Identity からのアラートに関連付けられたさまざまなエンティティ (ファイル[](advanced-hunting-overview.md)、IP アドレス、URL、ユーザー、またはデバイス) に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="644e5-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="644e5-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="644e5-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="644e5-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="644e5-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="644e5-110">列名</span><span class="sxs-lookup"><span data-stu-id="644e5-110">Column name</span></span> | <span data-ttu-id="644e5-111">データ型</span><span class="sxs-lookup"><span data-stu-id="644e5-111">Data type</span></span> | <span data-ttu-id="644e5-112">説明</span><span class="sxs-lookup"><span data-stu-id="644e5-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="644e5-113">日付型</span><span class="sxs-lookup"><span data-stu-id="644e5-113">datetime</span></span> | <span data-ttu-id="644e5-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="644e5-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="644e5-115">string</span><span class="sxs-lookup"><span data-stu-id="644e5-115">string</span></span> | <span data-ttu-id="644e5-116">アラートの一意識別子</span><span class="sxs-lookup"><span data-stu-id="644e5-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="644e5-117">string</span><span class="sxs-lookup"><span data-stu-id="644e5-117">string</span></span> | <span data-ttu-id="644e5-118">アラート情報を提供した製品またはサービス</span><span class="sxs-lookup"><span data-stu-id="644e5-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="644e5-119">string</span><span class="sxs-lookup"><span data-stu-id="644e5-119">string</span></span> | <span data-ttu-id="644e5-120">ファイル、プロセス、デバイス、ユーザーなどのオブジェクトの種類</span><span class="sxs-lookup"><span data-stu-id="644e5-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="644e5-121">string</span><span class="sxs-lookup"><span data-stu-id="644e5-121">string</span></span> | <span data-ttu-id="644e5-122">エンティティがアラートに関与する方法 (影響を受け取ったのか、単に関連付けなのかを示す)</span><span class="sxs-lookup"><span data-stu-id="644e5-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="644e5-123">string</span><span class="sxs-lookup"><span data-stu-id="644e5-123">string</span></span> | <span data-ttu-id="644e5-124">エンティティがネットワーク接続の送信元か宛先かを示します。</span><span class="sxs-lookup"><span data-stu-id="644e5-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="644e5-125">文字列</span><span class="sxs-lookup"><span data-stu-id="644e5-125">string</span></span> | <span data-ttu-id="644e5-126">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="644e5-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="644e5-127">文字列</span><span class="sxs-lookup"><span data-stu-id="644e5-127">string</span></span> | <span data-ttu-id="644e5-128">記録されたアクションが適用されたファイルを含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="644e5-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="644e5-129">文字列</span><span class="sxs-lookup"><span data-stu-id="644e5-129">string</span></span> | <span data-ttu-id="644e5-130">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="644e5-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="644e5-131">文字列</span><span class="sxs-lookup"><span data-stu-id="644e5-131">string</span></span> | <span data-ttu-id="644e5-132">記録されたアクションが適用されたファイルの SHA-256</span><span class="sxs-lookup"><span data-stu-id="644e5-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="644e5-133">このフィールドは、通常は入力されません。使用可能な場合は SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="644e5-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="644e5-134">int</span><span class="sxs-lookup"><span data-stu-id="644e5-134">int</span></span> | <span data-ttu-id="644e5-135">ファイルのサイズ (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="644e5-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="644e5-136">string</span><span class="sxs-lookup"><span data-stu-id="644e5-136">string</span></span> | <span data-ttu-id="644e5-137">疑わしいファイルまたは悪意のあるファイルまたはプロセスが分類されたマルウェア ファミリは、</span><span class="sxs-lookup"><span data-stu-id="644e5-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="644e5-138">文字列</span><span class="sxs-lookup"><span data-stu-id="644e5-138">string</span></span> | <span data-ttu-id="644e5-139">に接続されていた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="644e5-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="644e5-140">文字列</span><span class="sxs-lookup"><span data-stu-id="644e5-140">string</span></span> | <span data-ttu-id="644e5-141">に接続されていた URL または完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="644e5-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="644e5-142">文字列</span><span class="sxs-lookup"><span data-stu-id="644e5-142">string</span></span> | <span data-ttu-id="644e5-143">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="644e5-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="644e5-144">string</span><span class="sxs-lookup"><span data-stu-id="644e5-144">string</span></span> | <span data-ttu-id="644e5-145">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="644e5-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="644e5-146">string</span><span class="sxs-lookup"><span data-stu-id="644e5-146">string</span></span> | <span data-ttu-id="644e5-147">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="644e5-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="644e5-148">string</span><span class="sxs-lookup"><span data-stu-id="644e5-148">string</span></span> | <span data-ttu-id="644e5-149">アカウントの一意の識別子は、Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="644e5-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountUpn` | <span data-ttu-id="644e5-150">string</span><span class="sxs-lookup"><span data-stu-id="644e5-150">string</span></span> | <span data-ttu-id="644e5-151">アカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="644e5-151">User principal name (UPN) of the account</span></span> |
| `DeviceId` | <span data-ttu-id="644e5-152">string</span><span class="sxs-lookup"><span data-stu-id="644e5-152">string</span></span> | <span data-ttu-id="644e5-153">サービス内のデバイスの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="644e5-153">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="644e5-154">string</span><span class="sxs-lookup"><span data-stu-id="644e5-154">string</span></span> | <span data-ttu-id="644e5-155">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="644e5-155">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="644e5-156">string</span><span class="sxs-lookup"><span data-stu-id="644e5-156">string</span></span> | <span data-ttu-id="644e5-157">通信中に使用されるローカル デバイスに割り当てられた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="644e5-157">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="644e5-158">string</span><span class="sxs-lookup"><span data-stu-id="644e5-158">string</span></span> | <span data-ttu-id="644e5-159">Office 365 により生成されたメールの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="644e5-159">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="644e5-160">string</span><span class="sxs-lookup"><span data-stu-id="644e5-160">string</span></span> | <span data-ttu-id="644e5-161">メールの件名</span><span class="sxs-lookup"><span data-stu-id="644e5-161">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="644e5-162">string</span><span class="sxs-lookup"><span data-stu-id="644e5-162">string</span></span> | <span data-ttu-id="644e5-163">アプリケーションの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="644e5-163">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="644e5-164">string</span><span class="sxs-lookup"><span data-stu-id="644e5-164">string</span></span> | <span data-ttu-id="644e5-165">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="644e5-165">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="644e5-166">string</span><span class="sxs-lookup"><span data-stu-id="644e5-166">string</span></span> | <span data-ttu-id="644e5-167">新しいプロセスの作成に使用するコマンド ライン</span><span class="sxs-lookup"><span data-stu-id="644e5-167">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="644e5-168">string</span><span class="sxs-lookup"><span data-stu-id="644e5-168">string</span></span> | <span data-ttu-id="644e5-169">JSON 配列形式のイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="644e5-169">Additional information about the event in JSON array format</span></span> |
| `RegistryKey` |<span data-ttu-id="644e5-170">string</span><span class="sxs-lookup"><span data-stu-id="644e5-170">string</span></span> | <span data-ttu-id="644e5-171">記録されたアクションが適用されたレジストリ キー</span><span class="sxs-lookup"><span data-stu-id="644e5-171">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueName` |<span data-ttu-id="644e5-172">string</span><span class="sxs-lookup"><span data-stu-id="644e5-172">string</span></span> | <span data-ttu-id="644e5-173">記録されたアクションが適用されたレジストリ値の名前</span><span class="sxs-lookup"><span data-stu-id="644e5-173">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` |<span data-ttu-id="644e5-174">string</span><span class="sxs-lookup"><span data-stu-id="644e5-174">string</span></span> | <span data-ttu-id="644e5-175">記録されたアクションが適用されたレジストリ値のデータ</span><span class="sxs-lookup"><span data-stu-id="644e5-175">Data of the registry value that the recorded action was applied to</span></span> |

## <a name="related-topics"></a><span data-ttu-id="644e5-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="644e5-176">Related topics</span></span>
- [<span data-ttu-id="644e5-177">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="644e5-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="644e5-178">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="644e5-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="644e5-179">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="644e5-179">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="644e5-180">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="644e5-180">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="644e5-181">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="644e5-181">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="644e5-182">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="644e5-182">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
