---
title: 高度な検索スキーマの AlertEvidence テーブル
description: 高度な検索スキーマの AlertEvidence テーブルで通知に関連付けられている情報について説明します。
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ec6fe3d080efb396ce0ecacadd3d5d9a8fa9f8d1
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413200"
---
# <a name="alertevidence"></a><span data-ttu-id="b6fe0-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="b6fe0-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b6fe0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b6fe0-105">**Applies to:**</span></span>
- <span data-ttu-id="b6fe0-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b6fe0-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b6fe0-107">`AlertEvidence`[高度な](advanced-hunting-overview.md)検索スキーマの表には、さまざまなエンティティ (ファイル、IP アドレス、url、ユーザー、またはデバイス) に関する情報が含まれています。この情報には、microsoft Defender ATP、Office 365 ATP、Microsoft Cloud App Security、および Azure ATP からのアラートに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="b6fe0-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="b6fe0-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="b6fe0-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="b6fe0-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6fe0-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b6fe0-110">列名</span><span class="sxs-lookup"><span data-stu-id="b6fe0-110">Column name</span></span> | <span data-ttu-id="b6fe0-111">データ型</span><span class="sxs-lookup"><span data-stu-id="b6fe0-111">Data type</span></span> | <span data-ttu-id="b6fe0-112">説明</span><span class="sxs-lookup"><span data-stu-id="b6fe0-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b6fe0-113">日付型</span><span class="sxs-lookup"><span data-stu-id="b6fe0-113">datetime</span></span> | <span data-ttu-id="b6fe0-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="b6fe0-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="b6fe0-115">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-115">string</span></span> | <span data-ttu-id="b6fe0-116">アラートの一意識別子</span><span class="sxs-lookup"><span data-stu-id="b6fe0-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="b6fe0-117">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-117">string</span></span> | <span data-ttu-id="b6fe0-118">通知情報を提供した製品またはサービス</span><span class="sxs-lookup"><span data-stu-id="b6fe0-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="b6fe0-119">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-119">string</span></span> | <span data-ttu-id="b6fe0-120">オブジェクトの種類 (ファイル、プロセス、デバイス、ユーザーなど)</span><span class="sxs-lookup"><span data-stu-id="b6fe0-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="b6fe0-121">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-121">string</span></span> | <span data-ttu-id="b6fe0-122">エンティティが通知に関与する方法。そのエンティティが影響を受けているか、または単に関連しているかを示します。</span><span class="sxs-lookup"><span data-stu-id="b6fe0-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="b6fe0-123">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-123">string</span></span> | <span data-ttu-id="b6fe0-124">エンティティがネットワーク接続のソースまたは宛先であるかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="b6fe0-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="b6fe0-125">文字列</span><span class="sxs-lookup"><span data-stu-id="b6fe0-125">string</span></span> | <span data-ttu-id="b6fe0-126">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="b6fe0-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="b6fe0-127">文字列</span><span class="sxs-lookup"><span data-stu-id="b6fe0-127">string</span></span> | <span data-ttu-id="b6fe0-128">記録されたアクションが適用されたファイルを含むフォルダ</span><span class="sxs-lookup"><span data-stu-id="b6fe0-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="b6fe0-129">文字列</span><span class="sxs-lookup"><span data-stu-id="b6fe0-129">string</span></span> | <span data-ttu-id="b6fe0-130">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="b6fe0-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="b6fe0-131">文字列</span><span class="sxs-lookup"><span data-stu-id="b6fe0-131">string</span></span> | <span data-ttu-id="b6fe0-132">記録されたアクションが適用されたファイルの SHA-256</span><span class="sxs-lookup"><span data-stu-id="b6fe0-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="b6fe0-133">このフィールドには通常、値が設定されていません。使用可能な場合は SHA1 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="b6fe0-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="b6fe0-134">int</span><span class="sxs-lookup"><span data-stu-id="b6fe0-134">int</span></span> | <span data-ttu-id="b6fe0-135">ファイルのサイズ (バイト数)</span><span class="sxs-lookup"><span data-stu-id="b6fe0-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="b6fe0-136">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-136">string</span></span> | <span data-ttu-id="b6fe0-137">疑わしいまたは悪意のあるファイルまたはプロセスが分類されたマルウェアファミリ</span><span class="sxs-lookup"><span data-stu-id="b6fe0-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="b6fe0-138">文字列</span><span class="sxs-lookup"><span data-stu-id="b6fe0-138">string</span></span> | <span data-ttu-id="b6fe0-139">に接続されていた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b6fe0-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="b6fe0-140">文字列</span><span class="sxs-lookup"><span data-stu-id="b6fe0-140">string</span></span> | <span data-ttu-id="b6fe0-141">に接続されていた URL または完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="b6fe0-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="b6fe0-142">文字列</span><span class="sxs-lookup"><span data-stu-id="b6fe0-142">string</span></span> | <span data-ttu-id="b6fe0-143">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="b6fe0-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="b6fe0-144">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-144">string</span></span> | <span data-ttu-id="b6fe0-145">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="b6fe0-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="b6fe0-146">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-146">string</span></span> | <span data-ttu-id="b6fe0-147">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="b6fe0-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="b6fe0-148">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-148">string</span></span> | <span data-ttu-id="b6fe0-149">Azure Active Directory のアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="b6fe0-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="b6fe0-150">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-150">string</span></span> | <span data-ttu-id="b6fe0-151">サービス内のデバイスの一意識別子</span><span class="sxs-lookup"><span data-stu-id="b6fe0-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b6fe0-152">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-152">string</span></span> | <span data-ttu-id="b6fe0-153">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="b6fe0-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="b6fe0-154">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-154">string</span></span> | <span data-ttu-id="b6fe0-155">通信時に使用されるローカルデバイスに割り当てられた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b6fe0-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="b6fe0-156">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-156">string</span></span> | <span data-ttu-id="b6fe0-157">Office 365 により生成されたメールの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="b6fe0-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="b6fe0-158">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-158">string</span></span> | <span data-ttu-id="b6fe0-159">メールの件名</span><span class="sxs-lookup"><span data-stu-id="b6fe0-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="b6fe0-160">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-160">string</span></span> | <span data-ttu-id="b6fe0-161">アプリケーションの一意識別子</span><span class="sxs-lookup"><span data-stu-id="b6fe0-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="b6fe0-162">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-162">string</span></span> | <span data-ttu-id="b6fe0-163">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="b6fe0-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="b6fe0-164">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-164">string</span></span> | <span data-ttu-id="b6fe0-165">新しいプロセスを作成するために使用されるコマンドライン</span><span class="sxs-lookup"><span data-stu-id="b6fe0-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="b6fe0-166">string</span><span class="sxs-lookup"><span data-stu-id="b6fe0-166">string</span></span> | <span data-ttu-id="b6fe0-167">JSON 配列形式でのイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="b6fe0-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b6fe0-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6fe0-168">Related topics</span></span>
- [<span data-ttu-id="b6fe0-169">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="b6fe0-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b6fe0-170">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="b6fe0-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b6fe0-171">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="b6fe0-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b6fe0-172">デバイス、メール、アプリ、ID 間での捜索</span><span class="sxs-lookup"><span data-stu-id="b6fe0-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b6fe0-173">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="b6fe0-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b6fe0-174">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="b6fe0-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
