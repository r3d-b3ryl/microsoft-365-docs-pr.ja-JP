---
title: 高度な検索スキーマの [identity Queryevents] テーブル
description: 高度な検索スキーマのイベントテーブルの Active Directory クエリイベントについて説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検出、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、identity Queryevents、Azure AD、Active Directory、AzureATP、identity、LDAP クエリ
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
ms.openlocfilehash: b2fc94d6ac6606c97b4824bc556b7299a2bd8ec7
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929273"
---
# <a name="identityqueryevents"></a><span data-ttu-id="717ad-104">Identity Queryevents</span><span class="sxs-lookup"><span data-stu-id="717ad-104">IdentityQueryEvents</span></span>

<span data-ttu-id="717ad-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="717ad-105">**Applies to:**</span></span>
- <span data-ttu-id="717ad-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="717ad-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="717ad-107">`IdentityQueryEvents` [高度な](advanced-hunting-overview.md)検索スキーマの表には、Active Directory オブジェクト (ユーザー、グループ、デバイス、ドメインなど) に対して実行されたクエリに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="717ad-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="717ad-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="717ad-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="717ad-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="717ad-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="717ad-110">列名</span><span class="sxs-lookup"><span data-stu-id="717ad-110">Column name</span></span> | <span data-ttu-id="717ad-111">データ型</span><span class="sxs-lookup"><span data-stu-id="717ad-111">Data type</span></span> | <span data-ttu-id="717ad-112">説明</span><span class="sxs-lookup"><span data-stu-id="717ad-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="717ad-113">日付型</span><span class="sxs-lookup"><span data-stu-id="717ad-113">datetime</span></span> | <span data-ttu-id="717ad-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="717ad-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="717ad-115">string</span><span class="sxs-lookup"><span data-stu-id="717ad-115">string</span></span> | <span data-ttu-id="717ad-116">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="717ad-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="717ad-117">string</span><span class="sxs-lookup"><span data-stu-id="717ad-117">string</span></span> | <span data-ttu-id="717ad-118">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="717ad-118">Application that performed the recorded action</span></span> |
| `Query` | <span data-ttu-id="717ad-119">string</span><span class="sxs-lookup"><span data-stu-id="717ad-119">string</span></span> | <span data-ttu-id="717ad-120">クエリの種類: QueryGroup、Querygroup、または EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="717ad-120">Type of query: QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryObject` | <span data-ttu-id="717ad-121">string</span><span class="sxs-lookup"><span data-stu-id="717ad-121">string</span></span> | <span data-ttu-id="717ad-122">ユーザー、グループ、デバイス、ドメイン、またはその他のクエリ対象のエンティティ型の名前</span><span class="sxs-lookup"><span data-stu-id="717ad-122">Name of the user, group, device, domain, or any other entity type being queried</span></span> |
| `Protocol` | <span data-ttu-id="717ad-123">string</span><span class="sxs-lookup"><span data-stu-id="717ad-123">string</span></span> | <span data-ttu-id="717ad-124">通信中に使用されるプロトコル</span><span class="sxs-lookup"><span data-stu-id="717ad-124">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="717ad-125">string</span><span class="sxs-lookup"><span data-stu-id="717ad-125">string</span></span> | <span data-ttu-id="717ad-126">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="717ad-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="717ad-127">string</span><span class="sxs-lookup"><span data-stu-id="717ad-127">string</span></span> | <span data-ttu-id="717ad-128">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="717ad-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="717ad-129">string</span><span class="sxs-lookup"><span data-stu-id="717ad-129">string</span></span> | <span data-ttu-id="717ad-130">アカウントのユーザープリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="717ad-130">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="717ad-131">string</span><span class="sxs-lookup"><span data-stu-id="717ad-131">string</span></span> | <span data-ttu-id="717ad-132">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="717ad-132">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="717ad-133">string</span><span class="sxs-lookup"><span data-stu-id="717ad-133">string</span></span> | <span data-ttu-id="717ad-134">Azure AD でのアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="717ad-134">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="717ad-135">string</span><span class="sxs-lookup"><span data-stu-id="717ad-135">string</span></span> | <span data-ttu-id="717ad-136">アドレス帳に表示されるアカウントユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="717ad-136">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="717ad-137">通常、指定された名前または名、ミドルネーム、姓の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="717ad-137">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="717ad-138">string</span><span class="sxs-lookup"><span data-stu-id="717ad-138">string</span></span> | <span data-ttu-id="717ad-139">エンドポイントの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="717ad-139">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="717ad-140">string</span><span class="sxs-lookup"><span data-stu-id="717ad-140">string</span></span> | <span data-ttu-id="717ad-141">エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="717ad-141">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="717ad-142">string</span><span class="sxs-lookup"><span data-stu-id="717ad-142">string</span></span> | <span data-ttu-id="717ad-143">イベントに関連付けられている市区町村、国、またはその他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="717ad-143">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="717ad-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="717ad-144">Related topics</span></span>
- [<span data-ttu-id="717ad-145">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="717ad-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="717ad-146">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="717ad-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="717ad-147">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="717ad-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="717ad-148">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="717ad-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="717ad-149">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="717ad-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="717ad-150">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="717ad-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
