---
title: 高度な検索スキーマの [identity Queryevents] テーブル
description: 高度な検索スキーマのイベントテーブルの Active Directory クエリイベントについて説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検出、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、ユーザー Queryevents、Azure AD、Active Directory、Azure ATP、id、LDAP クエリ
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
ms.openlocfilehash: 436c4d7306f9f5febd614489090a0a10929ba3c9
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204877"
---
# <a name="identityqueryevents"></a><span data-ttu-id="2f0bd-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="2f0bd-104">IdentityQueryEvents</span></span>

<span data-ttu-id="2f0bd-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2f0bd-105">**Applies to:**</span></span>
- <span data-ttu-id="2f0bd-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2f0bd-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2f0bd-107">`IdentityQueryEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、Active Directory オブジェクト (ユーザー、グループ、デバイス、ドメインなど) に対して実行されたクエリに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f0bd-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="2f0bd-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f0bd-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="2f0bd-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f0bd-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2f0bd-110">列名</span><span class="sxs-lookup"><span data-stu-id="2f0bd-110">Column name</span></span> | <span data-ttu-id="2f0bd-111">データ型</span><span class="sxs-lookup"><span data-stu-id="2f0bd-111">Data type</span></span> | <span data-ttu-id="2f0bd-112">説明</span><span class="sxs-lookup"><span data-stu-id="2f0bd-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2f0bd-113">日付型</span><span class="sxs-lookup"><span data-stu-id="2f0bd-113">datetime</span></span> | <span data-ttu-id="2f0bd-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="2f0bd-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="2f0bd-115">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-115">string</span></span> | <span data-ttu-id="2f0bd-116">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="2f0bd-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="2f0bd-117">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-117">string</span></span> | <span data-ttu-id="2f0bd-118">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="2f0bd-118">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="2f0bd-119">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-119">string</span></span> | <span data-ttu-id="2f0bd-120">クエリの種類 (QueryGroup、Querygroup、EnumerateUsers など)</span><span class="sxs-lookup"><span data-stu-id="2f0bd-120">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="2f0bd-121">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-121">string</span></span> | <span data-ttu-id="2f0bd-122">ユーザー、グループ、デバイス、ドメイン、またはその他のクエリ対象のエンティティ型の名前</span><span class="sxs-lookup"><span data-stu-id="2f0bd-122">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="2f0bd-123">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-123">string</span></span> | <span data-ttu-id="2f0bd-124">クエリの実行に使用される文字列</span><span class="sxs-lookup"><span data-stu-id="2f0bd-124">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="2f0bd-125">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-125">string</span></span> | <span data-ttu-id="2f0bd-126">通信中に使用されるプロトコル</span><span class="sxs-lookup"><span data-stu-id="2f0bd-126">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="2f0bd-127">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-127">string</span></span> | <span data-ttu-id="2f0bd-128">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="2f0bd-128">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="2f0bd-129">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-129">string</span></span> | <span data-ttu-id="2f0bd-130">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="2f0bd-130">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="2f0bd-131">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-131">string</span></span> | <span data-ttu-id="2f0bd-132">アカウントのユーザープリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="2f0bd-132">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="2f0bd-133">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-133">string</span></span> | <span data-ttu-id="2f0bd-134">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="2f0bd-134">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="2f0bd-135">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-135">string</span></span> | <span data-ttu-id="2f0bd-136">Azure AD でのアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="2f0bd-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="2f0bd-137">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-137">string</span></span> | <span data-ttu-id="2f0bd-138">アドレス帳に表示されるアカウントユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="2f0bd-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="2f0bd-139">通常、指定された名前または名、ミドルネーム、姓の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="2f0bd-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="2f0bd-140">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-140">string</span></span> | <span data-ttu-id="2f0bd-141">エンドポイントの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="2f0bd-141">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="2f0bd-142">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-142">string</span></span> | <span data-ttu-id="2f0bd-143">エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="2f0bd-143">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="2f0bd-144">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-144">string</span></span> | <span data-ttu-id="2f0bd-145">記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの名前</span><span class="sxs-lookup"><span data-stu-id="2f0bd-145">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="2f0bd-146">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-146">string</span></span> | <span data-ttu-id="2f0bd-147">記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="2f0bd-147">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="2f0bd-148">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-148">string</span></span> | <span data-ttu-id="2f0bd-149">記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="2f0bd-149">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="2f0bd-150">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-150">string</span></span> | <span data-ttu-id="2f0bd-151">記録されたアクションが適用されたアカウントのユーザープリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="2f0bd-151">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="2f0bd-152">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-152">string</span></span> | <span data-ttu-id="2f0bd-153">記録済みのアクションが適用されたアカウントの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="2f0bd-153">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="2f0bd-154">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-154">string</span></span> | <span data-ttu-id="2f0bd-155">イベントに関連付けられている市区町村、国、またはその他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="2f0bd-155">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="2f0bd-156">long</span><span class="sxs-lookup"><span data-stu-id="2f0bd-156">long</span></span> | <span data-ttu-id="2f0bd-157">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="2f0bd-157">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="2f0bd-158">string</span><span class="sxs-lookup"><span data-stu-id="2f0bd-158">string</span></span> | <span data-ttu-id="2f0bd-159">エンティティまたはイベントに関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="2f0bd-159">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2f0bd-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f0bd-160">Related topics</span></span>
- [<span data-ttu-id="2f0bd-161">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="2f0bd-161">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2f0bd-162">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="2f0bd-162">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2f0bd-163">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="2f0bd-163">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2f0bd-164">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="2f0bd-164">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2f0bd-165">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="2f0bd-165">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2f0bd-166">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="2f0bd-166">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
