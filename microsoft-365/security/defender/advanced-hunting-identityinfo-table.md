---
title: 高度な検索スキーマの IdentityInfo テーブル
description: 高度なハンティング スキーマの IdentityInfo テーブルのユーザー アカウント情報について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft の脅威の保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、AccountInfo、IdentityInfo、アカウント
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e3e5410c868336308b1ecb34ba4326bf2dc5796f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064739"
---
# <a name="identityinfo"></a><span data-ttu-id="5f63d-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="5f63d-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5f63d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5f63d-105">**Applies to:**</span></span>
- <span data-ttu-id="5f63d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f63d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5f63d-107">高度 `IdentityInfo` な検索スキーマの [表](advanced-hunting-overview.md) には、Azure Active Directory を含むさまざまなサービスから取得したユーザー アカウントに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5f63d-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="5f63d-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="5f63d-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="5f63d-109">このテーブルはから名前が変更されました `AccountInfo` 。</span><span class="sxs-lookup"><span data-stu-id="5f63d-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="5f63d-110">名前の変更中に、ポータルに保存されているクエリはすべて自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="5f63d-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="5f63d-111">他の場所に保存したクエリを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f63d-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="5f63d-112">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f63d-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5f63d-113">列名</span><span class="sxs-lookup"><span data-stu-id="5f63d-113">Column name</span></span> | <span data-ttu-id="5f63d-114">データ型</span><span class="sxs-lookup"><span data-stu-id="5f63d-114">Data type</span></span> | <span data-ttu-id="5f63d-115">説明</span><span class="sxs-lookup"><span data-stu-id="5f63d-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="5f63d-116">string</span><span class="sxs-lookup"><span data-stu-id="5f63d-116">string</span></span> | <span data-ttu-id="5f63d-117">Azure アカウントのアカウントの一意AD</span><span class="sxs-lookup"><span data-stu-id="5f63d-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="5f63d-118">string</span><span class="sxs-lookup"><span data-stu-id="5f63d-118">string</span></span> | <span data-ttu-id="5f63d-119">アカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="5f63d-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="5f63d-120">string</span><span class="sxs-lookup"><span data-stu-id="5f63d-120">string</span></span> | <span data-ttu-id="5f63d-121">アカウントのオンプレミスセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="5f63d-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="5f63d-122">string</span><span class="sxs-lookup"><span data-stu-id="5f63d-122">string</span></span> | <span data-ttu-id="5f63d-123">アカウントのクラウド セキュリティ識別子</span><span class="sxs-lookup"><span data-stu-id="5f63d-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="5f63d-124">string</span><span class="sxs-lookup"><span data-stu-id="5f63d-124">string</span></span> | <span data-ttu-id="5f63d-125">アカウント ユーザーの名前または名を指定する</span><span class="sxs-lookup"><span data-stu-id="5f63d-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="5f63d-126">string</span><span class="sxs-lookup"><span data-stu-id="5f63d-126">string</span></span> | <span data-ttu-id="5f63d-127">アカウント ユーザーの姓、ファミリ名、または姓</span><span class="sxs-lookup"><span data-stu-id="5f63d-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="5f63d-128">string</span><span class="sxs-lookup"><span data-stu-id="5f63d-128">string</span></span> | <span data-ttu-id="5f63d-129">アドレス帳に表示されるアカウント ユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="5f63d-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="5f63d-130">通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="5f63d-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="5f63d-131">string</span><span class="sxs-lookup"><span data-stu-id="5f63d-131">string</span></span> | <span data-ttu-id="5f63d-132">アカウント ユーザーが属する部署の名前</span><span class="sxs-lookup"><span data-stu-id="5f63d-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="5f63d-133">string</span><span class="sxs-lookup"><span data-stu-id="5f63d-133">string</span></span> | <span data-ttu-id="5f63d-134">アカウント ユーザーの役職</span><span class="sxs-lookup"><span data-stu-id="5f63d-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="5f63d-135">string</span><span class="sxs-lookup"><span data-stu-id="5f63d-135">string</span></span> | <span data-ttu-id="5f63d-136">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="5f63d-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="5f63d-137">string</span><span class="sxs-lookup"><span data-stu-id="5f63d-137">string</span></span> | <span data-ttu-id="5f63d-138">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="5f63d-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="5f63d-139">string</span><span class="sxs-lookup"><span data-stu-id="5f63d-139">string</span></span> | <span data-ttu-id="5f63d-140">アカウントの SMTP アドレス</span><span class="sxs-lookup"><span data-stu-id="5f63d-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="5f63d-141">string</span><span class="sxs-lookup"><span data-stu-id="5f63d-141">string</span></span> | <span data-ttu-id="5f63d-142">アカウントのボイス オーバー IP (VOIP) セッション開始プロトコル (SIP) アドレス</span><span class="sxs-lookup"><span data-stu-id="5f63d-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="5f63d-143">string</span><span class="sxs-lookup"><span data-stu-id="5f63d-143">string</span></span> | <span data-ttu-id="5f63d-144">アカウント ユーザーが保存されている都市</span><span class="sxs-lookup"><span data-stu-id="5f63d-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="5f63d-145">string</span><span class="sxs-lookup"><span data-stu-id="5f63d-145">string</span></span> | <span data-ttu-id="5f63d-146">アカウント ユーザーが保存されている国/地域</span><span class="sxs-lookup"><span data-stu-id="5f63d-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="5f63d-147">boolean</span><span class="sxs-lookup"><span data-stu-id="5f63d-147">boolean</span></span> | <span data-ttu-id="5f63d-148">アカウントが有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="5f63d-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5f63d-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f63d-149">Related topics</span></span>
- [<span data-ttu-id="5f63d-150">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="5f63d-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5f63d-151">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="5f63d-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5f63d-152">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="5f63d-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5f63d-153">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="5f63d-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5f63d-154">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="5f63d-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5f63d-155">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="5f63d-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
