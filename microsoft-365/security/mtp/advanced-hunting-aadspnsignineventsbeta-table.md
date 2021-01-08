---
title: 高度な検索スキーマの AADSpnSignInEventsBeta テーブル
description: 高度な検索スキーマの Azure Active Directory サービス プリンシパルと管理対象 ID サインイン イベント テーブルに関連付けられている情報について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、AlertInfo、アラート、エンティティ、証拠、ファイル、IP アドレス、デバイス、コンピューター、ユーザー、アカウント、ID、AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 42acf24ce9b941fffb1ce0ed4b67216bd8c1de47
ms.sourcegitcommit: 4482c174e0e68e0fbbc7ad9ef6b0e78dc34ac85a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2021
ms.locfileid: "49784301"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="f3cb2-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="f3cb2-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="f3cb2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f3cb2-105">**Applies to:**</span></span>

- <span data-ttu-id="f3cb2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3cb2-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="f3cb2-107">このテーブルは現在ベータ版であり `AADSpnSignInEventsBeta` 、Azure Active Directory (AAD) サービス プリンシパルとマネージ ID サインイン イベントをハントするために、短期的に提供されています。</span><span class="sxs-lookup"><span data-stu-id="f3cb2-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="f3cb2-108">最終的に、すべてのサインイン スキーマ情報をテーブルに移動 `IdentityLogonEvents` します。</span><span class="sxs-lookup"><span data-stu-id="f3cb2-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="f3cb2-109">Azure Security Center の統合 Microsoft Defender for Endpoint ソリューションを通じて Microsoft 365 Defender にアクセスできるが、Office 用 Microsoft Defender、Id 用 Microsoft Defender、または Microsoft Cloud App Security のライセンスを持ってないお客様は、このスキーマを表示できません。</span><span class="sxs-lookup"><span data-stu-id="f3cb2-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="f3cb2-110">高度 `AADSpnSignInEventsBeta` な検索スキーマの表には、Azure Active Directory サービス プリンシパルとマネージ ID サインインに関する情報が含まれます。さまざまな種類のサインインの詳細については、Azure Active Directory サインイン アクティビティ [レポートのプレビューを参照してください](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)。</span><span class="sxs-lookup"><span data-stu-id="f3cb2-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="f3cb2-111">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f3cb2-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="f3cb2-112">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3cb2-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="f3cb2-113">列名</span><span class="sxs-lookup"><span data-stu-id="f3cb2-113">Column name</span></span>     | <span data-ttu-id="f3cb2-114">データ型</span><span class="sxs-lookup"><span data-stu-id="f3cb2-114">Data type</span></span> | <span data-ttu-id="f3cb2-115">説明</span><span class="sxs-lookup"><span data-stu-id="f3cb2-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="f3cb2-116">datetime</span><span class="sxs-lookup"><span data-stu-id="f3cb2-116">datetime</span></span>      | <span data-ttu-id="f3cb2-117">レコードが作成された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="f3cb2-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="f3cb2-118">文字列</span><span class="sxs-lookup"><span data-stu-id="f3cb2-118">string</span></span>        | <span data-ttu-id="f3cb2-119">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="f3cb2-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="f3cb2-120">string</span><span class="sxs-lookup"><span data-stu-id="f3cb2-120">string</span></span>        | <span data-ttu-id="f3cb2-121">アプリケーションの一意識別子</span><span class="sxs-lookup"><span data-stu-id="f3cb2-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="f3cb2-122">ブール値</span><span class="sxs-lookup"><span data-stu-id="f3cb2-122">boolean</span></span>       | <span data-ttu-id="f3cb2-123">サインインが管理 ID によって開始されたかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="f3cb2-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="f3cb2-124">int</span><span class="sxs-lookup"><span data-stu-id="f3cb2-124">int</span></span>        | <span data-ttu-id="f3cb2-125">サインイン エラーが発生した場合のエラー コードを含む。</span><span class="sxs-lookup"><span data-stu-id="f3cb2-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="f3cb2-126">特定のエラー コードの説明を見つけるには、次のページを参照してください <https://aka.ms/AADsigninsErrorCodes> 。</span><span class="sxs-lookup"><span data-stu-id="f3cb2-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="f3cb2-127">string</span><span class="sxs-lookup"><span data-stu-id="f3cb2-127">string</span></span>        | <span data-ttu-id="f3cb2-128">サインイン イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="f3cb2-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="f3cb2-129">string</span><span class="sxs-lookup"><span data-stu-id="f3cb2-129">string</span></span>        | <span data-ttu-id="f3cb2-130">サインインを開始したサービス プリンシパルの名前</span><span class="sxs-lookup"><span data-stu-id="f3cb2-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="f3cb2-131">string</span><span class="sxs-lookup"><span data-stu-id="f3cb2-131">string</span></span>        | <span data-ttu-id="f3cb2-132">サインインを開始したサービス プリンシパルの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="f3cb2-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="f3cb2-133">string</span><span class="sxs-lookup"><span data-stu-id="f3cb2-133">string</span></span>        | <span data-ttu-id="f3cb2-134">アクセスされたリソースの表示名</span><span class="sxs-lookup"><span data-stu-id="f3cb2-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="f3cb2-135">string</span><span class="sxs-lookup"><span data-stu-id="f3cb2-135">string</span></span>        | <span data-ttu-id="f3cb2-136">アクセスされるリソースの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="f3cb2-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="f3cb2-137">string</span><span class="sxs-lookup"><span data-stu-id="f3cb2-137">string</span></span>        | <span data-ttu-id="f3cb2-138">アクセスされたリソースのテナントの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="f3cb2-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="f3cb2-139">string</span><span class="sxs-lookup"><span data-stu-id="f3cb2-139">string</span></span>        | <span data-ttu-id="f3cb2-140">エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f3cb2-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `CountryCode`          | <span data-ttu-id="f3cb2-141">string</span><span class="sxs-lookup"><span data-stu-id="f3cb2-141">string</span></span>        | <span data-ttu-id="f3cb2-142">クライアント IP アドレスが地理的に位置する国を示す 2 文字のコード</span><span class="sxs-lookup"><span data-stu-id="f3cb2-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="f3cb2-143">string</span><span class="sxs-lookup"><span data-stu-id="f3cb2-143">string</span></span>        | <span data-ttu-id="f3cb2-144">サインインが発生した状態 (使用可能な場合)</span><span class="sxs-lookup"><span data-stu-id="f3cb2-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="f3cb2-145">string</span><span class="sxs-lookup"><span data-stu-id="f3cb2-145">string</span></span>        | <span data-ttu-id="f3cb2-146">アカウント ユーザーが位置する市区町町ラ</span><span class="sxs-lookup"><span data-stu-id="f3cb2-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="f3cb2-147">string</span><span class="sxs-lookup"><span data-stu-id="f3cb2-147">string</span></span>        | <span data-ttu-id="f3cb2-148">サインイン場所の北から南の座標</span><span class="sxs-lookup"><span data-stu-id="f3cb2-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="f3cb2-149">string</span><span class="sxs-lookup"><span data-stu-id="f3cb2-149">string</span></span>        | <span data-ttu-id="f3cb2-150">サインイン位置の東から西への座標</span><span class="sxs-lookup"><span data-stu-id="f3cb2-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="f3cb2-151">string</span><span class="sxs-lookup"><span data-stu-id="f3cb2-151">string</span></span>        | <span data-ttu-id="f3cb2-152">要求の一意識別子</span><span class="sxs-lookup"><span data-stu-id="f3cb2-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="f3cb2-153">string</span><span class="sxs-lookup"><span data-stu-id="f3cb2-153">string</span></span> | <span data-ttu-id="f3cb2-154">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="f3cb2-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="f3cb2-155">関連記事</span><span class="sxs-lookup"><span data-stu-id="f3cb2-155">Related articles</span></span>

-   [<span data-ttu-id="f3cb2-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="f3cb2-156">AADSignInEventsBeta</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [<span data-ttu-id="f3cb2-157">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="f3cb2-157">Advanced hunting overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="f3cb2-158">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="f3cb2-158">Learn the query language</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="f3cb2-159">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="f3cb2-159">Understand the schema</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

