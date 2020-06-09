---
title: 高度な検索スキーマの AlertEvidence テーブル
description: 高度な検索スキーマの AlertEvidence テーブルで生成される警告に関連付けられているファイル、ネットワークアドレス、ユーザー、またはデバイスの情報について説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、AlertInfo、alert、entities、エビデンス、file、IP address、device、machine、user、account
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
ms.openlocfilehash: da6e84725aa391e4cb6056fadd327fdba2436214
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617088"
---
# <a name="alertevidence"></a><span data-ttu-id="aae65-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="aae65-104">AlertEvidence</span></span>

<span data-ttu-id="aae65-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="aae65-105">**Applies to:**</span></span>
- <span data-ttu-id="aae65-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="aae65-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="aae65-107">`AlertEvidence`[高度な](advanced-hunting-overview.md)検索スキーマの表には、さまざまなエンティティ (ファイル、IP アドレス、url、ユーザー、またはデバイス) に関する情報が含まれています。この情報には、microsoft Defender ATP、Office 365 ATP、Microsoft Cloud App Security、および Azure ATP からのアラートに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="aae65-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities — files, IP addresses, URLs, users, or devices — associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="aae65-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="aae65-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="aae65-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aae65-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="aae65-110">列名</span><span class="sxs-lookup"><span data-stu-id="aae65-110">Column name</span></span> | <span data-ttu-id="aae65-111">データ型</span><span class="sxs-lookup"><span data-stu-id="aae65-111">Data type</span></span> | <span data-ttu-id="aae65-112">説明</span><span class="sxs-lookup"><span data-stu-id="aae65-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="aae65-113">日付型</span><span class="sxs-lookup"><span data-stu-id="aae65-113">datetime</span></span> | <span data-ttu-id="aae65-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="aae65-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="aae65-115">string</span><span class="sxs-lookup"><span data-stu-id="aae65-115">string</span></span> | <span data-ttu-id="aae65-116">アラートの一意識別子</span><span class="sxs-lookup"><span data-stu-id="aae65-116">Unique identifier for the alert</span></span> |
| `EntityType` | <span data-ttu-id="aae65-117">string</span><span class="sxs-lookup"><span data-stu-id="aae65-117">string</span></span> | <span data-ttu-id="aae65-118">オブジェクトの種類 (ファイル、プロセス、デバイス、ユーザーなど)</span><span class="sxs-lookup"><span data-stu-id="aae65-118">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="aae65-119">string</span><span class="sxs-lookup"><span data-stu-id="aae65-119">string</span></span> | <span data-ttu-id="aae65-120">エンティティが通知に関与する方法。そのエンティティが影響を受けているか、または単に関連しているかを示します。</span><span class="sxs-lookup"><span data-stu-id="aae65-120">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `SHA1` | <span data-ttu-id="aae65-121">string</span><span class="sxs-lookup"><span data-stu-id="aae65-121">string</span></span> | <span data-ttu-id="aae65-122">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="aae65-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="aae65-123">文字列型</span><span class="sxs-lookup"><span data-stu-id="aae65-123">string</span></span> | <span data-ttu-id="aae65-124">記録されたアクションが適用されたファイルの SHA-256</span><span class="sxs-lookup"><span data-stu-id="aae65-124">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="aae65-125">このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="aae65-125">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `RemoteIP` | <span data-ttu-id="aae65-126">文字列</span><span class="sxs-lookup"><span data-stu-id="aae65-126">string</span></span> | <span data-ttu-id="aae65-127">に接続されていた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="aae65-127">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="aae65-128">string</span><span class="sxs-lookup"><span data-stu-id="aae65-128">string</span></span> | <span data-ttu-id="aae65-129">に接続されていた URL または完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="aae65-129">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="aae65-130">文字列</span><span class="sxs-lookup"><span data-stu-id="aae65-130">string</span></span> | <span data-ttu-id="aae65-131">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="aae65-131">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="aae65-132">string</span><span class="sxs-lookup"><span data-stu-id="aae65-132">string</span></span> | <span data-ttu-id="aae65-133">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="aae65-133">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="aae65-134">string</span><span class="sxs-lookup"><span data-stu-id="aae65-134">string</span></span> | <span data-ttu-id="aae65-135">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="aae65-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="aae65-136">string</span><span class="sxs-lookup"><span data-stu-id="aae65-136">string</span></span> | <span data-ttu-id="aae65-137">Azure AD でのアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="aae65-137">Unique identifier for the account in Azure AD</span></span> |
| `DeviceId` | <span data-ttu-id="aae65-138">string</span><span class="sxs-lookup"><span data-stu-id="aae65-138">string</span></span> | <span data-ttu-id="aae65-139">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="aae65-139">Unique identifier for the machine in the service</span></span> |
| `ThreatFamily` | <span data-ttu-id="aae65-140">string</span><span class="sxs-lookup"><span data-stu-id="aae65-140">string</span></span> | <span data-ttu-id="aae65-141">疑わしいまたは悪意のあるファイルまたはプロセスが分類されたマルウェアファミリ</span><span class="sxs-lookup"><span data-stu-id="aae65-141">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `EvidenceDirection` | <span data-ttu-id="aae65-142">string</span><span class="sxs-lookup"><span data-stu-id="aae65-142">string</span></span> | <span data-ttu-id="aae65-143">エンティティがネットワーク接続のソースまたは宛先であるかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="aae65-143">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `AdditionalFields` | <span data-ttu-id="aae65-144">string</span><span class="sxs-lookup"><span data-stu-id="aae65-144">string</span></span> | <span data-ttu-id="aae65-145">JSON 配列形式でのイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="aae65-145">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="aae65-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="aae65-146">Related topics</span></span>
- [<span data-ttu-id="aae65-147">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="aae65-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="aae65-148">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="aae65-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="aae65-149">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="aae65-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="aae65-150">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="aae65-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="aae65-151">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="aae65-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="aae65-152">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="aae65-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
