---
title: 高度な検索スキーマの IdentityQueryEvents テーブル
description: 高度な検索スキーマの IdentityQueryEvents テーブルの Active Directory クエリ イベントについて説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、IdentityQueryEvents、Azure AD、Active Directory、Azure ATP、ID、LDAP クエリ
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
ms.openlocfilehash: 48a1520e9fc6239fd3105f01a32a03e5e58df174
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145297"
---
# <a name="identityqueryevents"></a><span data-ttu-id="e71e4-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="e71e4-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e71e4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e71e4-105">**Applies to:**</span></span>
- <span data-ttu-id="e71e4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e71e4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e71e4-107">高度 `IdentityQueryEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、ユーザー、グループ、デバイス、ドメインなど、Active Directory オブジェクトに対して実行されたクエリに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e71e4-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="e71e4-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e71e4-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="e71e4-109">テーブルでサポートされているイベントの種類 ( 値) の詳細については、セキュリティ センターで使用可能な組み込みのスキーマ `ActionType` 参照を使用してください。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="e71e4-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="e71e4-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71e4-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e71e4-111">列名</span><span class="sxs-lookup"><span data-stu-id="e71e4-111">Column name</span></span> | <span data-ttu-id="e71e4-112">データ型</span><span class="sxs-lookup"><span data-stu-id="e71e4-112">Data type</span></span> | <span data-ttu-id="e71e4-113">説明</span><span class="sxs-lookup"><span data-stu-id="e71e4-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e71e4-114">日付型</span><span class="sxs-lookup"><span data-stu-id="e71e4-114">datetime</span></span> | <span data-ttu-id="e71e4-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="e71e4-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="e71e4-116">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-116">string</span></span> | <span data-ttu-id="e71e4-117">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="e71e4-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="e71e4-118">詳細については [、ポータル内スキーマ リファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71e4-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="e71e4-119">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-119">string</span></span> | <span data-ttu-id="e71e4-120">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="e71e4-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="e71e4-121">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-121">string</span></span> | <span data-ttu-id="e71e4-122">QueryGroup、QueryUser、EnumerateUsers などのクエリの種類</span><span class="sxs-lookup"><span data-stu-id="e71e4-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="e71e4-123">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-123">string</span></span> | <span data-ttu-id="e71e4-124">クエリを実行しているユーザー、グループ、デバイス、ドメイン、その他のエンティティの種類の名前</span><span class="sxs-lookup"><span data-stu-id="e71e4-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="e71e4-125">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-125">string</span></span> | <span data-ttu-id="e71e4-126">クエリの実行に使用する文字列</span><span class="sxs-lookup"><span data-stu-id="e71e4-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="e71e4-127">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-127">string</span></span> | <span data-ttu-id="e71e4-128">通信中に使用されるプロトコル</span><span class="sxs-lookup"><span data-stu-id="e71e4-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="e71e4-129">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-129">string</span></span> | <span data-ttu-id="e71e4-130">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="e71e4-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="e71e4-131">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-131">string</span></span> | <span data-ttu-id="e71e4-132">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="e71e4-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="e71e4-133">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-133">string</span></span> | <span data-ttu-id="e71e4-134">アカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="e71e4-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="e71e4-135">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-135">string</span></span> | <span data-ttu-id="e71e4-136">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="e71e4-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="e71e4-137">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-137">string</span></span> | <span data-ttu-id="e71e4-138">Azure AD のアカウントの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="e71e4-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="e71e4-139">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-139">string</span></span> | <span data-ttu-id="e71e4-140">アドレス帳に表示されるアカウント ユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="e71e4-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="e71e4-141">通常、名、ミドル ネーム、姓または姓の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="e71e4-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="e71e4-142">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-142">string</span></span> | <span data-ttu-id="e71e4-143">エンドポイントの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="e71e4-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="e71e4-144">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-144">string</span></span> | <span data-ttu-id="e71e4-145">エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="e71e4-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="e71e4-146">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-146">string</span></span> | <span data-ttu-id="e71e4-147">通信中に使用される TCP ポート</span><span class="sxs-lookup"><span data-stu-id="e71e4-147">TCP port used during communication</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="e71e4-148">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-148">string</span></span> | <span data-ttu-id="e71e4-149">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの名前</span><span class="sxs-lookup"><span data-stu-id="e71e4-149">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="e71e4-150">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-150">string</span></span> | <span data-ttu-id="e71e4-151">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="e71e4-151">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="e71e4-152">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-152">string</span></span> | <span data-ttu-id="e71e4-153">関連するネットワーク通信の宛先ポート</span><span class="sxs-lookup"><span data-stu-id="e71e4-153">Destination port of related network communications</span></span> |
| `TargetDeviceName` | <span data-ttu-id="e71e4-154">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-154">string</span></span> | <span data-ttu-id="e71e4-155">記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="e71e4-155">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="e71e4-156">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-156">string</span></span> | <span data-ttu-id="e71e4-157">記録されたアクションが適用されたアカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="e71e4-157">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="e71e4-158">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-158">string</span></span> | <span data-ttu-id="e71e4-159">記録されたアクションが適用されたアカウントの表示名</span><span class="sxs-lookup"><span data-stu-id="e71e4-159">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="e71e4-160">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-160">string</span></span> | <span data-ttu-id="e71e4-161">イベントに関連付けられている都市、国、その他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="e71e4-161">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="e71e4-162">long</span><span class="sxs-lookup"><span data-stu-id="e71e4-162">long</span></span> | <span data-ttu-id="e71e4-163">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="e71e4-163">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="e71e4-164">string</span><span class="sxs-lookup"><span data-stu-id="e71e4-164">string</span></span> | <span data-ttu-id="e71e4-165">エンティティまたはイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="e71e4-165">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e71e4-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="e71e4-166">Related topics</span></span>
- [<span data-ttu-id="e71e4-167">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="e71e4-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e71e4-168">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="e71e4-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e71e4-169">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="e71e4-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e71e4-170">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="e71e4-170">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e71e4-171">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="e71e4-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e71e4-172">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="e71e4-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
