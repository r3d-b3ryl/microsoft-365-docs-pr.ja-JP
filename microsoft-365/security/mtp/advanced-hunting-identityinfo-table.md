---
title: 高度な検索スキーマの [情報] テーブル
description: 高度な検索スキーマの id 情報の表にあるユーザーアカウント情報について説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検出、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、AccountInfo、identity Info、account
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
ms.openlocfilehash: b384e76439ae706520725e7193fa64224b724be0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898959"
---
# <a name="identityinfo"></a><span data-ttu-id="ae5a8-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="ae5a8-104">IdentityInfo</span></span>

<span data-ttu-id="ae5a8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ae5a8-105">**Applies to:**</span></span>
- <span data-ttu-id="ae5a8-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ae5a8-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="ae5a8-107">`IdentityInfo`[高度な](advanced-hunting-overview.md)検索スキーマの表には、Azure Active Directory などのさまざまなサービスから取得したユーザーアカウントに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ae5a8-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="ae5a8-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae5a8-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="ae5a8-109">このテーブルはから名前が変更されました `AccountInfo` 。</span><span class="sxs-lookup"><span data-stu-id="ae5a8-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="ae5a8-110">名前を変更すると、ポータルに保存されているすべてのクエリが自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="ae5a8-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="ae5a8-111">他の場所に保存されたクエリをチェックします。</span><span class="sxs-lookup"><span data-stu-id="ae5a8-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="ae5a8-112">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae5a8-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ae5a8-113">列名</span><span class="sxs-lookup"><span data-stu-id="ae5a8-113">Column name</span></span> | <span data-ttu-id="ae5a8-114">データ型</span><span class="sxs-lookup"><span data-stu-id="ae5a8-114">Data type</span></span> | <span data-ttu-id="ae5a8-115">説明</span><span class="sxs-lookup"><span data-stu-id="ae5a8-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="ae5a8-116">string</span><span class="sxs-lookup"><span data-stu-id="ae5a8-116">string</span></span> | <span data-ttu-id="ae5a8-117">Azure AD でのアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="ae5a8-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="ae5a8-118">string</span><span class="sxs-lookup"><span data-stu-id="ae5a8-118">string</span></span> | <span data-ttu-id="ae5a8-119">アカウントのユーザープリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="ae5a8-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="ae5a8-120">string</span><span class="sxs-lookup"><span data-stu-id="ae5a8-120">string</span></span> | <span data-ttu-id="ae5a8-121">アカウントの社内セキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="ae5a8-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="ae5a8-122">string</span><span class="sxs-lookup"><span data-stu-id="ae5a8-122">string</span></span> | <span data-ttu-id="ae5a8-123">アカウントのクラウドセキュリティ識別子</span><span class="sxs-lookup"><span data-stu-id="ae5a8-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="ae5a8-124">string</span><span class="sxs-lookup"><span data-stu-id="ae5a8-124">string</span></span> | <span data-ttu-id="ae5a8-125">アカウントユーザーの名前または名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae5a8-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="ae5a8-126">string</span><span class="sxs-lookup"><span data-stu-id="ae5a8-126">string</span></span> | <span data-ttu-id="ae5a8-127">アカウントユーザーの姓、家族名、または姓</span><span class="sxs-lookup"><span data-stu-id="ae5a8-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="ae5a8-128">string</span><span class="sxs-lookup"><span data-stu-id="ae5a8-128">string</span></span> | <span data-ttu-id="ae5a8-129">アドレス帳に表示されるアカウントユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="ae5a8-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="ae5a8-130">通常、指定された名前または名、ミドルネーム、姓の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="ae5a8-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="ae5a8-131">string</span><span class="sxs-lookup"><span data-stu-id="ae5a8-131">string</span></span> | <span data-ttu-id="ae5a8-132">アカウントユーザーが属する部署の名前</span><span class="sxs-lookup"><span data-stu-id="ae5a8-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="ae5a8-133">string</span><span class="sxs-lookup"><span data-stu-id="ae5a8-133">string</span></span> | <span data-ttu-id="ae5a8-134">アカウントユーザーの役職</span><span class="sxs-lookup"><span data-stu-id="ae5a8-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="ae5a8-135">string</span><span class="sxs-lookup"><span data-stu-id="ae5a8-135">string</span></span> | <span data-ttu-id="ae5a8-136">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="ae5a8-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="ae5a8-137">string</span><span class="sxs-lookup"><span data-stu-id="ae5a8-137">string</span></span> | <span data-ttu-id="ae5a8-138">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="ae5a8-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="ae5a8-139">string</span><span class="sxs-lookup"><span data-stu-id="ae5a8-139">string</span></span> | <span data-ttu-id="ae5a8-140">アカウントの SMTP アドレス</span><span class="sxs-lookup"><span data-stu-id="ae5a8-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="ae5a8-141">string</span><span class="sxs-lookup"><span data-stu-id="ae5a8-141">string</span></span> | <span data-ttu-id="ae5a8-142">アカウントのボイスオーバー IP (VOIP) セッション開始プロトコル (SIP) アドレス</span><span class="sxs-lookup"><span data-stu-id="ae5a8-142">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="ae5a8-143">string</span><span class="sxs-lookup"><span data-stu-id="ae5a8-143">string</span></span> | <span data-ttu-id="ae5a8-144">アカウントユーザーが配置されている市区町村</span><span class="sxs-lookup"><span data-stu-id="ae5a8-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="ae5a8-145">string</span><span class="sxs-lookup"><span data-stu-id="ae5a8-145">string</span></span> | <span data-ttu-id="ae5a8-146">アカウントユーザーが配置されている国/地域</span><span class="sxs-lookup"><span data-stu-id="ae5a8-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="ae5a8-147">boolean</span><span class="sxs-lookup"><span data-stu-id="ae5a8-147">boolean</span></span> | <span data-ttu-id="ae5a8-148">アカウントが有効であるかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="ae5a8-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ae5a8-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae5a8-149">Related topics</span></span>
- [<span data-ttu-id="ae5a8-150">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="ae5a8-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ae5a8-151">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="ae5a8-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ae5a8-152">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="ae5a8-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ae5a8-153">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="ae5a8-153">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ae5a8-154">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="ae5a8-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ae5a8-155">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="ae5a8-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
