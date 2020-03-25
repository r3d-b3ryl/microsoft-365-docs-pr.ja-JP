---
title: 高度な検索スキーマの AccountInfo テーブル
description: 高度な検索スキーマの AccountInfo テーブルにあるユーザーアカウント情報について説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、AlertInfo、alert、entities、エビデンス、file、IP address、デバイス、コンピューター、ユーザー、アカウント
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
ms.openlocfilehash: 9e4503ab297c7a584a548faa36ca6102c1b8dda6
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929530"
---
# <a name="accountinfo"></a><span data-ttu-id="c8f25-104">AccountInfo</span><span class="sxs-lookup"><span data-stu-id="c8f25-104">AccountInfo</span></span>

<span data-ttu-id="c8f25-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c8f25-105">**Applies to:**</span></span>
- <span data-ttu-id="c8f25-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c8f25-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c8f25-107">`AccountInfo` [高度な](advanced-hunting-overview.md)検索スキーマの表には、Azure Active Directory などのさまざまなサービスから取得したユーザーアカウントに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c8f25-107">The `AccountInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="c8f25-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8f25-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c8f25-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f25-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c8f25-110">列名</span><span class="sxs-lookup"><span data-stu-id="c8f25-110">Column name</span></span> | <span data-ttu-id="c8f25-111">データ型</span><span class="sxs-lookup"><span data-stu-id="c8f25-111">Data type</span></span> | <span data-ttu-id="c8f25-112">説明</span><span class="sxs-lookup"><span data-stu-id="c8f25-112">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="c8f25-113">string</span><span class="sxs-lookup"><span data-stu-id="c8f25-113">string</span></span> | <span data-ttu-id="c8f25-114">Azure AD でのアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="c8f25-114">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="c8f25-115">string</span><span class="sxs-lookup"><span data-stu-id="c8f25-115">string</span></span> | <span data-ttu-id="c8f25-116">アカウントのユーザープリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="c8f25-116">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="c8f25-117">string</span><span class="sxs-lookup"><span data-stu-id="c8f25-117">string</span></span> | <span data-ttu-id="c8f25-118">アカウントの社内セキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="c8f25-118">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="c8f25-119">string</span><span class="sxs-lookup"><span data-stu-id="c8f25-119">string</span></span> | <span data-ttu-id="c8f25-120">アカウントのクラウドセキュリティ識別子</span><span class="sxs-lookup"><span data-stu-id="c8f25-120">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="c8f25-121">string</span><span class="sxs-lookup"><span data-stu-id="c8f25-121">string</span></span> | <span data-ttu-id="c8f25-122">アカウントユーザーの名前または名を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8f25-122">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="c8f25-123">string</span><span class="sxs-lookup"><span data-stu-id="c8f25-123">string</span></span> | <span data-ttu-id="c8f25-124">アカウントユーザーの姓、家族名、または姓</span><span class="sxs-lookup"><span data-stu-id="c8f25-124">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="c8f25-125">string</span><span class="sxs-lookup"><span data-stu-id="c8f25-125">string</span></span> | <span data-ttu-id="c8f25-126">アドレス帳に表示されるアカウントユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="c8f25-126">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="c8f25-127">通常、指定された名前または名、ミドルネーム、姓の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="c8f25-127">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="c8f25-128">string</span><span class="sxs-lookup"><span data-stu-id="c8f25-128">string</span></span> | <span data-ttu-id="c8f25-129">アカウントユーザーが属する部署の名前</span><span class="sxs-lookup"><span data-stu-id="c8f25-129">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="c8f25-130">string</span><span class="sxs-lookup"><span data-stu-id="c8f25-130">string</span></span> | <span data-ttu-id="c8f25-131">アカウントユーザーの役職</span><span class="sxs-lookup"><span data-stu-id="c8f25-131">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="c8f25-132">string</span><span class="sxs-lookup"><span data-stu-id="c8f25-132">string</span></span> | <span data-ttu-id="c8f25-133">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="c8f25-133">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="c8f25-134">string</span><span class="sxs-lookup"><span data-stu-id="c8f25-134">string</span></span> | <span data-ttu-id="c8f25-135">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="c8f25-135">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="c8f25-136">string</span><span class="sxs-lookup"><span data-stu-id="c8f25-136">string</span></span> | <span data-ttu-id="c8f25-137">アカウントの SMTP アドレス</span><span class="sxs-lookup"><span data-stu-id="c8f25-137">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="c8f25-138">string</span><span class="sxs-lookup"><span data-stu-id="c8f25-138">string</span></span> | <span data-ttu-id="c8f25-139">アカウントのボイスオーバー IP (VOIP) セッション開始プロトコル (SIP) アドレス</span><span class="sxs-lookup"><span data-stu-id="c8f25-139">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="c8f25-140">string</span><span class="sxs-lookup"><span data-stu-id="c8f25-140">string</span></span> | <span data-ttu-id="c8f25-141">アカウントユーザーが配置されている市区町村</span><span class="sxs-lookup"><span data-stu-id="c8f25-141">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="c8f25-142">string</span><span class="sxs-lookup"><span data-stu-id="c8f25-142">string</span></span> | <span data-ttu-id="c8f25-143">アカウントユーザーが配置されている国/地域</span><span class="sxs-lookup"><span data-stu-id="c8f25-143">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="c8f25-144">ブール値</span><span class="sxs-lookup"><span data-stu-id="c8f25-144">boolean</span></span> | <span data-ttu-id="c8f25-145">アカウントが有効であるかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="c8f25-145">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c8f25-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8f25-146">Related topics</span></span>
- [<span data-ttu-id="c8f25-147">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="c8f25-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c8f25-148">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="c8f25-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c8f25-149">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="c8f25-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c8f25-150">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="c8f25-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c8f25-151">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="c8f25-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c8f25-152">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="c8f25-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
