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
ms.openlocfilehash: b5238ca32cdf9050391ef69bae3be0914b93f452
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797806"
---
# <a name="identityqueryevents"></a><span data-ttu-id="3f044-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="3f044-104">IdentityQueryEvents</span></span>

<span data-ttu-id="3f044-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3f044-105">**Applies to:**</span></span>
- <span data-ttu-id="3f044-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3f044-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="3f044-107">`IdentityQueryEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、Active Directory オブジェクト (ユーザー、グループ、デバイス、ドメインなど) に対して実行されたクエリに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3f044-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="3f044-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3f044-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="3f044-109">テーブルでサポートされているイベントの種類 (値) の詳細については、 `ActionType` セキュリティセンターで利用可能な [組み込みスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="3f044-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="3f044-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f044-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3f044-111">列名</span><span class="sxs-lookup"><span data-stu-id="3f044-111">Column name</span></span> | <span data-ttu-id="3f044-112">データ型</span><span class="sxs-lookup"><span data-stu-id="3f044-112">Data type</span></span> | <span data-ttu-id="3f044-113">説明</span><span class="sxs-lookup"><span data-stu-id="3f044-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="3f044-114">日付型</span><span class="sxs-lookup"><span data-stu-id="3f044-114">datetime</span></span> | <span data-ttu-id="3f044-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="3f044-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="3f044-116">string</span><span class="sxs-lookup"><span data-stu-id="3f044-116">string</span></span> | <span data-ttu-id="3f044-117">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="3f044-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="3f044-118">詳細については、 [ポータル内のスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f044-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="3f044-119">string</span><span class="sxs-lookup"><span data-stu-id="3f044-119">string</span></span> | <span data-ttu-id="3f044-120">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="3f044-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="3f044-121">string</span><span class="sxs-lookup"><span data-stu-id="3f044-121">string</span></span> | <span data-ttu-id="3f044-122">クエリの種類 (QueryGroup、Querygroup、EnumerateUsers など)</span><span class="sxs-lookup"><span data-stu-id="3f044-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="3f044-123">string</span><span class="sxs-lookup"><span data-stu-id="3f044-123">string</span></span> | <span data-ttu-id="3f044-124">ユーザー、グループ、デバイス、ドメイン、またはその他のクエリ対象のエンティティ型の名前</span><span class="sxs-lookup"><span data-stu-id="3f044-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="3f044-125">string</span><span class="sxs-lookup"><span data-stu-id="3f044-125">string</span></span> | <span data-ttu-id="3f044-126">クエリの実行に使用される文字列</span><span class="sxs-lookup"><span data-stu-id="3f044-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="3f044-127">string</span><span class="sxs-lookup"><span data-stu-id="3f044-127">string</span></span> | <span data-ttu-id="3f044-128">通信中に使用されるプロトコル</span><span class="sxs-lookup"><span data-stu-id="3f044-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="3f044-129">string</span><span class="sxs-lookup"><span data-stu-id="3f044-129">string</span></span> | <span data-ttu-id="3f044-130">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="3f044-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="3f044-131">string</span><span class="sxs-lookup"><span data-stu-id="3f044-131">string</span></span> | <span data-ttu-id="3f044-132">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="3f044-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="3f044-133">string</span><span class="sxs-lookup"><span data-stu-id="3f044-133">string</span></span> | <span data-ttu-id="3f044-134">アカウントのユーザープリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="3f044-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="3f044-135">string</span><span class="sxs-lookup"><span data-stu-id="3f044-135">string</span></span> | <span data-ttu-id="3f044-136">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="3f044-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="3f044-137">string</span><span class="sxs-lookup"><span data-stu-id="3f044-137">string</span></span> | <span data-ttu-id="3f044-138">Azure AD でのアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="3f044-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="3f044-139">string</span><span class="sxs-lookup"><span data-stu-id="3f044-139">string</span></span> | <span data-ttu-id="3f044-140">アドレス帳に表示されるアカウントユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="3f044-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="3f044-141">通常、指定された名前または名、ミドルネーム、姓の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="3f044-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="3f044-142">string</span><span class="sxs-lookup"><span data-stu-id="3f044-142">string</span></span> | <span data-ttu-id="3f044-143">エンドポイントの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="3f044-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="3f044-144">string</span><span class="sxs-lookup"><span data-stu-id="3f044-144">string</span></span> | <span data-ttu-id="3f044-145">エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f044-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="3f044-146">string</span><span class="sxs-lookup"><span data-stu-id="3f044-146">string</span></span> | <span data-ttu-id="3f044-147">記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの名前</span><span class="sxs-lookup"><span data-stu-id="3f044-147">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="3f044-148">string</span><span class="sxs-lookup"><span data-stu-id="3f044-148">string</span></span> | <span data-ttu-id="3f044-149">記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f044-149">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="3f044-150">string</span><span class="sxs-lookup"><span data-stu-id="3f044-150">string</span></span> | <span data-ttu-id="3f044-151">記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="3f044-151">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="3f044-152">string</span><span class="sxs-lookup"><span data-stu-id="3f044-152">string</span></span> | <span data-ttu-id="3f044-153">記録されたアクションが適用されたアカウントのユーザープリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="3f044-153">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="3f044-154">string</span><span class="sxs-lookup"><span data-stu-id="3f044-154">string</span></span> | <span data-ttu-id="3f044-155">記録済みのアクションが適用されたアカウントの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="3f044-155">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="3f044-156">string</span><span class="sxs-lookup"><span data-stu-id="3f044-156">string</span></span> | <span data-ttu-id="3f044-157">イベントに関連付けられている市区町村、国、またはその他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="3f044-157">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="3f044-158">long</span><span class="sxs-lookup"><span data-stu-id="3f044-158">long</span></span> | <span data-ttu-id="3f044-159">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="3f044-159">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="3f044-160">string</span><span class="sxs-lookup"><span data-stu-id="3f044-160">string</span></span> | <span data-ttu-id="3f044-161">エンティティまたはイベントに関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="3f044-161">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3f044-162">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3f044-162">Related topics</span></span>
- [<span data-ttu-id="3f044-163">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="3f044-163">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3f044-164">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="3f044-164">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3f044-165">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="3f044-165">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3f044-166">デバイス、メール、アプリ、ID 間での捜索</span><span class="sxs-lookup"><span data-stu-id="3f044-166">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3f044-167">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="3f044-167">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3f044-168">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="3f044-168">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
