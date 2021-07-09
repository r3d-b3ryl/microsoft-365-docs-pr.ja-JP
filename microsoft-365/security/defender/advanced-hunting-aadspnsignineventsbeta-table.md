---
title: 高度なハンティング スキーマの AADSpnSignInEventsBeta テーブル
description: 高度なハンティング スキーマの Azure Active Directory サービス プリンシパルおよびマネージ ID サインイン イベント テーブルに関連付けられている情報について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、AlertInfo、アラート、エンティティ、証拠、ファイル、IP アドレス、デバイス、コンピューター、ユーザー、アカウント、ID、AAD
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
ms.openlocfilehash: 6aa709fe4534bf049c6f8c097bc4bd85a9d6793b
ms.sourcegitcommit: 93eeaefc0d509c75e4c2210029155298ecca7583
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53347909"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="d19e0-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="d19e0-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="d19e0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d19e0-105">**Applies to:**</span></span>

- <span data-ttu-id="d19e0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d19e0-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="d19e0-107">このテーブルは現在ベータ版で、Azure Active Directory (AAD) サービス プリンシパルとマネージ ID サインイン イベントをハントするために、短期的に提供されています `AADSpnSignInEventsBeta` 。</span><span class="sxs-lookup"><span data-stu-id="d19e0-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="d19e0-108">最終的に、すべてのサインイン スキーマ情報をテーブルに移動 `IdentityLogonEvents` します。</span><span class="sxs-lookup"><span data-stu-id="d19e0-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span>



<span data-ttu-id="d19e0-109">高度 `AADSpnSignInEventsBeta` な検索スキーマの表には、サービス プリンシパルAzure Active Directoryマネージド ID サインインに関する情報が含まれている。さまざまな種類のサインインの詳細については、「Azure Active Directoryアクティビティ レポート - プレビュー」を[参照してください](/azure/active-directory/reports-monitoring/concept-all-sign-ins)。</span><span class="sxs-lookup"><span data-stu-id="d19e0-109">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="d19e0-110">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="d19e0-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="d19e0-111">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d19e0-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="d19e0-112">列名</span><span class="sxs-lookup"><span data-stu-id="d19e0-112">Column name</span></span> | <span data-ttu-id="d19e0-113">データ型</span><span class="sxs-lookup"><span data-stu-id="d19e0-113">Data type</span></span> | <span data-ttu-id="d19e0-114">説明</span><span class="sxs-lookup"><span data-stu-id="d19e0-114">Description</span></span> |
|-----|-----|-----|
| `Timestamp` | <span data-ttu-id="d19e0-115">datetime</span><span class="sxs-lookup"><span data-stu-id="d19e0-115">datetime</span></span> | <span data-ttu-id="d19e0-116">レコードが作成された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="d19e0-116">Date and time when the record was generated</span></span> |
| `Application` | <span data-ttu-id="d19e0-117">文字列</span><span class="sxs-lookup"><span data-stu-id="d19e0-117">string</span></span> | <span data-ttu-id="d19e0-118">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="d19e0-118">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="d19e0-119">文字列</span><span class="sxs-lookup"><span data-stu-id="d19e0-119">string</span></span> | <span data-ttu-id="d19e0-120">アプリケーションの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="d19e0-120">Unique identifier for the application</span></span> |
| `IsManagedIdentity`    | <span data-ttu-id="d19e0-121">ブール値</span><span class="sxs-lookup"><span data-stu-id="d19e0-121">boolean</span></span>       | <span data-ttu-id="d19e0-122">マネージ ID によってサインインが開始されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d19e0-122">Indicates whether the sign-in was initiated by a managed identity</span></span> |
| `ErrorCode`    | <span data-ttu-id="d19e0-123">整数</span><span class="sxs-lookup"><span data-stu-id="d19e0-123">int</span></span> | <span data-ttu-id="d19e0-124">サインイン エラーが発生した場合のエラー コードを格納します。</span><span class="sxs-lookup"><span data-stu-id="d19e0-124">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="d19e0-125">特定のエラー コードの説明を見つけるには、 を参照してください <https://aka.ms/AADsigninsErrorCodes> 。</span><span class="sxs-lookup"><span data-stu-id="d19e0-125">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="d19e0-126">文字列</span><span class="sxs-lookup"><span data-stu-id="d19e0-126">string</span></span>        | <span data-ttu-id="d19e0-127">サインイン イベントの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="d19e0-127">Unique identifier of the sign-in event</span></span> |
| `ServicePrincipalName` | <span data-ttu-id="d19e0-128">文字列</span><span class="sxs-lookup"><span data-stu-id="d19e0-128">string</span></span>        | <span data-ttu-id="d19e0-129">サインインを開始したサービス プリンシパルの名前</span><span class="sxs-lookup"><span data-stu-id="d19e0-129">Name of the service principal that initiated the sign-in</span></span>  |
| `ServicePrincipalId`   | <span data-ttu-id="d19e0-130">文字列</span><span class="sxs-lookup"><span data-stu-id="d19e0-130">string</span></span>        | <span data-ttu-id="d19e0-131">サインインを開始したサービス プリンシパルの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="d19e0-131">Unique identifier of the service principal that initiated the sign-in</span></span>  |
| `ResourceDisplayName`  | <span data-ttu-id="d19e0-132">文字列</span><span class="sxs-lookup"><span data-stu-id="d19e0-132">string</span></span>        | <span data-ttu-id="d19e0-133">アクセスされたリソースの表示名</span><span class="sxs-lookup"><span data-stu-id="d19e0-133">Display name of the resource accessed</span></span>  |
| `ResourceId`           | <span data-ttu-id="d19e0-134">文字列</span><span class="sxs-lookup"><span data-stu-id="d19e0-134">string</span></span>        | <span data-ttu-id="d19e0-135">アクセスされるリソースの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="d19e0-135">Unique identifier of the resource accessed</span></span>  |
| `ResourceTenantId`     | <span data-ttu-id="d19e0-136">文字列</span><span class="sxs-lookup"><span data-stu-id="d19e0-136">string</span></span>        | <span data-ttu-id="d19e0-137">アクセスされるリソースのテナントの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="d19e0-137">Unique identifier of the tenant of the resource accessed</span></span> |
| `IPAddress`            | <span data-ttu-id="d19e0-138">文字列</span><span class="sxs-lookup"><span data-stu-id="d19e0-138">string</span></span>        | <span data-ttu-id="d19e0-139">エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="d19e0-139">IP address assigned to the endpoint and used during related network communications</span></span>  |
| `Country`          | <span data-ttu-id="d19e0-140">文字列</span><span class="sxs-lookup"><span data-stu-id="d19e0-140">string</span></span>        | <span data-ttu-id="d19e0-141">クライアント IP アドレスが地理的に位置付けされている国を示す 2 文字のコード</span><span class="sxs-lookup"><span data-stu-id="d19e0-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `State`                | <span data-ttu-id="d19e0-142">文字列</span><span class="sxs-lookup"><span data-stu-id="d19e0-142">string</span></span>        | <span data-ttu-id="d19e0-143">使用可能な場合は、サインインが発生した状態</span><span class="sxs-lookup"><span data-stu-id="d19e0-143">State where the sign-in occurred, if available</span></span> |
| `City`                 | <span data-ttu-id="d19e0-144">文字列</span><span class="sxs-lookup"><span data-stu-id="d19e0-144">string</span></span>        | <span data-ttu-id="d19e0-145">アカウント ユーザーが保存されている都市</span><span class="sxs-lookup"><span data-stu-id="d19e0-145">City where the account user is located</span></span>  |
| `Latitude`             | <span data-ttu-id="d19e0-146">文字列</span><span class="sxs-lookup"><span data-stu-id="d19e0-146">string</span></span>        | <span data-ttu-id="d19e0-147">サインイン場所の北から南の座標</span><span class="sxs-lookup"><span data-stu-id="d19e0-147">The north to south coordinates of the sign-in location</span></span> |
| `Longitude`            | <span data-ttu-id="d19e0-148">文字列</span><span class="sxs-lookup"><span data-stu-id="d19e0-148">string</span></span>        | <span data-ttu-id="d19e0-149">サインイン場所の東から西への座標</span><span class="sxs-lookup"><span data-stu-id="d19e0-149">The east to west coordinates of the sign-in location</span></span> |
| `RequestId`            | <span data-ttu-id="d19e0-150">文字列</span><span class="sxs-lookup"><span data-stu-id="d19e0-150">string</span></span>        | <span data-ttu-id="d19e0-151">要求の一意の識別子</span><span class="sxs-lookup"><span data-stu-id="d19e0-151">Unique identifier of the request</span></span> |
|`ReportId` | <span data-ttu-id="d19e0-152">文字列</span><span class="sxs-lookup"><span data-stu-id="d19e0-152">string</span></span> | <span data-ttu-id="d19e0-153">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="d19e0-153">Unique identifier for the event</span></span> |

 

## <a name="related-articles"></a><span data-ttu-id="d19e0-154">関連記事</span><span class="sxs-lookup"><span data-stu-id="d19e0-154">Related articles</span></span>

-   [<span data-ttu-id="d19e0-155">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="d19e0-155">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="d19e0-156">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="d19e0-156">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="d19e0-157">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="d19e0-157">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="d19e0-158">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="d19e0-158">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
