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
ms.openlocfilehash: d7e1ad4d10c3b71a04421d92304dc2bfcb6147da
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498209"
---
# <a name="identityinfo"></a><span data-ttu-id="cc0f9-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="cc0f9-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cc0f9-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cc0f9-105">**Applies to:**</span></span>
- <span data-ttu-id="cc0f9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc0f9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="cc0f9-107">高度 `IdentityInfo` な検索スキーマの [表](advanced-hunting-overview.md) には、Azure Active Directory を含むさまざまなサービスから取得したユーザー アカウントに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cc0f9-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="cc0f9-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="cc0f9-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="cc0f9-109">このテーブルはから名前が変更されました `AccountInfo` 。</span><span class="sxs-lookup"><span data-stu-id="cc0f9-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="cc0f9-110">名前の変更中に、ポータルに保存されているクエリはすべて自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="cc0f9-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="cc0f9-111">他の場所に保存したクエリを確認します。</span><span class="sxs-lookup"><span data-stu-id="cc0f9-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="cc0f9-112">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc0f9-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="cc0f9-113">列名</span><span class="sxs-lookup"><span data-stu-id="cc0f9-113">Column name</span></span> | <span data-ttu-id="cc0f9-114">データ型</span><span class="sxs-lookup"><span data-stu-id="cc0f9-114">Data type</span></span> | <span data-ttu-id="cc0f9-115">説明</span><span class="sxs-lookup"><span data-stu-id="cc0f9-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="cc0f9-116">string</span><span class="sxs-lookup"><span data-stu-id="cc0f9-116">string</span></span> | <span data-ttu-id="cc0f9-117">Azure アカウントのアカウントの一意AD</span><span class="sxs-lookup"><span data-stu-id="cc0f9-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="cc0f9-118">文字列</span><span class="sxs-lookup"><span data-stu-id="cc0f9-118">string</span></span> | <span data-ttu-id="cc0f9-119">アカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="cc0f9-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="cc0f9-120">文字列</span><span class="sxs-lookup"><span data-stu-id="cc0f9-120">string</span></span> | <span data-ttu-id="cc0f9-121">アカウントのオンプレミスセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="cc0f9-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="cc0f9-122">文字列</span><span class="sxs-lookup"><span data-stu-id="cc0f9-122">string</span></span> | <span data-ttu-id="cc0f9-123">アカウントのクラウド セキュリティ識別子</span><span class="sxs-lookup"><span data-stu-id="cc0f9-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="cc0f9-124">文字列</span><span class="sxs-lookup"><span data-stu-id="cc0f9-124">string</span></span> | <span data-ttu-id="cc0f9-125">アカウント ユーザーの名前または名を指定する</span><span class="sxs-lookup"><span data-stu-id="cc0f9-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="cc0f9-126">文字列</span><span class="sxs-lookup"><span data-stu-id="cc0f9-126">string</span></span> | <span data-ttu-id="cc0f9-127">アカウント ユーザーの姓、ファミリ名、または姓</span><span class="sxs-lookup"><span data-stu-id="cc0f9-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="cc0f9-128">文字列</span><span class="sxs-lookup"><span data-stu-id="cc0f9-128">string</span></span> | <span data-ttu-id="cc0f9-129">アドレス帳に表示されるアカウント ユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="cc0f9-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="cc0f9-130">通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="cc0f9-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="cc0f9-131">文字列</span><span class="sxs-lookup"><span data-stu-id="cc0f9-131">string</span></span> | <span data-ttu-id="cc0f9-132">アカウント ユーザーが属する部署の名前</span><span class="sxs-lookup"><span data-stu-id="cc0f9-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="cc0f9-133">文字列</span><span class="sxs-lookup"><span data-stu-id="cc0f9-133">string</span></span> | <span data-ttu-id="cc0f9-134">アカウント ユーザーの役職</span><span class="sxs-lookup"><span data-stu-id="cc0f9-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="cc0f9-135">文字列</span><span class="sxs-lookup"><span data-stu-id="cc0f9-135">string</span></span> | <span data-ttu-id="cc0f9-136">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="cc0f9-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="cc0f9-137">文字列</span><span class="sxs-lookup"><span data-stu-id="cc0f9-137">string</span></span> | <span data-ttu-id="cc0f9-138">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="cc0f9-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="cc0f9-139">文字列</span><span class="sxs-lookup"><span data-stu-id="cc0f9-139">string</span></span> | <span data-ttu-id="cc0f9-140">アカウントの SMTP アドレス</span><span class="sxs-lookup"><span data-stu-id="cc0f9-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="cc0f9-141">文字列</span><span class="sxs-lookup"><span data-stu-id="cc0f9-141">string</span></span> | <span data-ttu-id="cc0f9-142">アカウントのボイス オーバー IP (VOIP) セッション開始プロトコル (SIP) アドレス</span><span class="sxs-lookup"><span data-stu-id="cc0f9-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="cc0f9-143">文字列</span><span class="sxs-lookup"><span data-stu-id="cc0f9-143">string</span></span> | <span data-ttu-id="cc0f9-144">アカウント ユーザーが保存されている都市</span><span class="sxs-lookup"><span data-stu-id="cc0f9-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="cc0f9-145">文字列</span><span class="sxs-lookup"><span data-stu-id="cc0f9-145">string</span></span> | <span data-ttu-id="cc0f9-146">アカウント ユーザーが保存されている国/地域</span><span class="sxs-lookup"><span data-stu-id="cc0f9-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="cc0f9-147">boolean</span><span class="sxs-lookup"><span data-stu-id="cc0f9-147">boolean</span></span> | <span data-ttu-id="cc0f9-148">アカウントが有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="cc0f9-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="cc0f9-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc0f9-149">Related topics</span></span>
- [<span data-ttu-id="cc0f9-150">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="cc0f9-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cc0f9-151">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="cc0f9-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cc0f9-152">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="cc0f9-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="cc0f9-153">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="cc0f9-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="cc0f9-154">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="cc0f9-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="cc0f9-155">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="cc0f9-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
