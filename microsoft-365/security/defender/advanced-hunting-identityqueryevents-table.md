---
title: 高度な検索スキーマの IdentityQueryEvents テーブル
description: 高度なハンティング スキーマの IdentityQueryEvents テーブルの Active Directory クエリ イベントについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、IdentityQueryEvents、Azure AD、Active Directory、Microsoft Defender for Identity、IDENTITY、LDAP クエリ
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
ms.openlocfilehash: 89f6f83112bc6bea57a3b5f7703353adb9d87a30
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935799"
---
# <a name="identityqueryevents"></a><span data-ttu-id="473db-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="473db-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="473db-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="473db-105">**Applies to:**</span></span>
- <span data-ttu-id="473db-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="473db-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="473db-107">高度 `IdentityQueryEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、ユーザー、グループ、デバイス、ドメインなどの Active Directory オブジェクトに対して実行されるクエリに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="473db-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="473db-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="473db-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="473db-109">テーブルでサポートされるイベントの種類 (値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ参照 `ActionType` を使用します。</span><span class="sxs-lookup"><span data-stu-id="473db-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="473db-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="473db-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="473db-111">列名</span><span class="sxs-lookup"><span data-stu-id="473db-111">Column name</span></span> | <span data-ttu-id="473db-112">データ型</span><span class="sxs-lookup"><span data-stu-id="473db-112">Data type</span></span> | <span data-ttu-id="473db-113">説明</span><span class="sxs-lookup"><span data-stu-id="473db-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="473db-114">日付型</span><span class="sxs-lookup"><span data-stu-id="473db-114">datetime</span></span> | <span data-ttu-id="473db-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="473db-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="473db-116">string</span><span class="sxs-lookup"><span data-stu-id="473db-116">string</span></span> | <span data-ttu-id="473db-117">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="473db-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="473db-118">詳細については [、ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="473db-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="473db-119">string</span><span class="sxs-lookup"><span data-stu-id="473db-119">string</span></span> | <span data-ttu-id="473db-120">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="473db-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="473db-121">string</span><span class="sxs-lookup"><span data-stu-id="473db-121">string</span></span> | <span data-ttu-id="473db-122">QueryGroup、QueryUser、または EnumerateUsers などのクエリの種類</span><span class="sxs-lookup"><span data-stu-id="473db-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="473db-123">string</span><span class="sxs-lookup"><span data-stu-id="473db-123">string</span></span> | <span data-ttu-id="473db-124">クエリを実行するユーザー、グループ、デバイス、ドメイン、その他のエンティティ型の名前</span><span class="sxs-lookup"><span data-stu-id="473db-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="473db-125">string</span><span class="sxs-lookup"><span data-stu-id="473db-125">string</span></span> | <span data-ttu-id="473db-126">クエリの実行に使用される文字列</span><span class="sxs-lookup"><span data-stu-id="473db-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="473db-127">string</span><span class="sxs-lookup"><span data-stu-id="473db-127">string</span></span> | <span data-ttu-id="473db-128">通信中に使用されるプロトコル</span><span class="sxs-lookup"><span data-stu-id="473db-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="473db-129">string</span><span class="sxs-lookup"><span data-stu-id="473db-129">string</span></span> | <span data-ttu-id="473db-130">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="473db-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="473db-131">string</span><span class="sxs-lookup"><span data-stu-id="473db-131">string</span></span> | <span data-ttu-id="473db-132">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="473db-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="473db-133">string</span><span class="sxs-lookup"><span data-stu-id="473db-133">string</span></span> | <span data-ttu-id="473db-134">アカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="473db-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="473db-135">string</span><span class="sxs-lookup"><span data-stu-id="473db-135">string</span></span> | <span data-ttu-id="473db-136">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="473db-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="473db-137">string</span><span class="sxs-lookup"><span data-stu-id="473db-137">string</span></span> | <span data-ttu-id="473db-138">Azure アカウントのアカウントの一意AD</span><span class="sxs-lookup"><span data-stu-id="473db-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="473db-139">string</span><span class="sxs-lookup"><span data-stu-id="473db-139">string</span></span> | <span data-ttu-id="473db-140">アドレス帳に表示されるアカウント ユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="473db-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="473db-141">通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="473db-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="473db-142">string</span><span class="sxs-lookup"><span data-stu-id="473db-142">string</span></span> | <span data-ttu-id="473db-143">エンドポイントの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="473db-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="473db-144">string</span><span class="sxs-lookup"><span data-stu-id="473db-144">string</span></span> | <span data-ttu-id="473db-145">エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="473db-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="473db-146">string</span><span class="sxs-lookup"><span data-stu-id="473db-146">string</span></span> | <span data-ttu-id="473db-147">通信中に使用される TCP ポート</span><span class="sxs-lookup"><span data-stu-id="473db-147">TCP port used during communication</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="473db-148">string</span><span class="sxs-lookup"><span data-stu-id="473db-148">string</span></span> | <span data-ttu-id="473db-149">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの名前</span><span class="sxs-lookup"><span data-stu-id="473db-149">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="473db-150">string</span><span class="sxs-lookup"><span data-stu-id="473db-150">string</span></span> | <span data-ttu-id="473db-151">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="473db-151">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="473db-152">string</span><span class="sxs-lookup"><span data-stu-id="473db-152">string</span></span> | <span data-ttu-id="473db-153">関連するネットワーク通信の宛先ポート</span><span class="sxs-lookup"><span data-stu-id="473db-153">Destination port of related network communications</span></span> |
| `TargetDeviceName` | <span data-ttu-id="473db-154">string</span><span class="sxs-lookup"><span data-stu-id="473db-154">string</span></span> | <span data-ttu-id="473db-155">記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="473db-155">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="473db-156">string</span><span class="sxs-lookup"><span data-stu-id="473db-156">string</span></span> | <span data-ttu-id="473db-157">記録されたアクションが適用されたアカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="473db-157">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="473db-158">string</span><span class="sxs-lookup"><span data-stu-id="473db-158">string</span></span> | <span data-ttu-id="473db-159">記録されたアクションが適用されたアカウントの表示名</span><span class="sxs-lookup"><span data-stu-id="473db-159">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="473db-160">string</span><span class="sxs-lookup"><span data-stu-id="473db-160">string</span></span> | <span data-ttu-id="473db-161">イベントに関連付けられている都市、国、その他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="473db-161">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="473db-162">long</span><span class="sxs-lookup"><span data-stu-id="473db-162">long</span></span> | <span data-ttu-id="473db-163">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="473db-163">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="473db-164">string</span><span class="sxs-lookup"><span data-stu-id="473db-164">string</span></span> | <span data-ttu-id="473db-165">エンティティまたはイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="473db-165">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="473db-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="473db-166">Related topics</span></span>
- [<span data-ttu-id="473db-167">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="473db-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="473db-168">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="473db-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="473db-169">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="473db-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="473db-170">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="473db-170">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="473db-171">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="473db-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="473db-172">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="473db-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
