---
title: 高度なハンティング スキーマの CloudAppEvents テーブル
description: 高度なハンティング スキーマの CloudAppEvents テーブルで、クラウド アプリとサービスからのイベントについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、CloudAppEvents、CloudAppEvents、Cloud App Security、MCAS
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
ms.openlocfilehash: 83b9eec37648ba48aa8e6931e836e8a5e22458c8
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760028"
---
# <a name="cloudappevents"></a><span data-ttu-id="3c5ed-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="3c5ed-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3c5ed-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3c5ed-105">**Applies to:**</span></span>
- <span data-ttu-id="3c5ed-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c5ed-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="3c5ed-107">高度 `CloudAppEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、Microsoft Cloud App Security でカバーされるさまざまなクラウド アプリとサービスのアクティビティに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c5ed-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security.</span></span> <span data-ttu-id="3c5ed-108">完全なリストについては、「対象のアプリ [とサービス」に移動します](#apps-and-services-covered)。</span><span class="sxs-lookup"><span data-stu-id="3c5ed-108">For a complete list, jump to [Apps and services covered](#apps-and-services-covered).</span></span> <span data-ttu-id="3c5ed-109">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c5ed-109">Use this reference to construct queries that return information from this table.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="3c5ed-110">この表には、表で使用できる情報が含 `AppFileEvents` まれています。</span><span class="sxs-lookup"><span data-stu-id="3c5ed-110">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="3c5ed-111">2021 年 3 月 7 日から、この日付以降のクラウド サービスでファイル関連のアクティビティを検索するユーザーは、代わりにテーブルを `CloudAppEvents` 使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c5ed-111">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="3c5ed-112">テーブルを引き続き使用するクエリとカスタム検出ルールを検索し、テーブル `AppFileEvents` を使用するために編集 `CloudAppEvents` してください。</span><span class="sxs-lookup"><span data-stu-id="3c5ed-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="3c5ed-113">影響を受けるクエリの変換に関する詳細なガイダンスについては [、「Microsoft 365 Defender](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)Advanced hunting を使用したクラウド アプリアクティビティ全体のハント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c5ed-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="3c5ed-114">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c5ed-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3c5ed-115">列名</span><span class="sxs-lookup"><span data-stu-id="3c5ed-115">Column name</span></span> | <span data-ttu-id="3c5ed-116">データ型</span><span class="sxs-lookup"><span data-stu-id="3c5ed-116">Data type</span></span> | <span data-ttu-id="3c5ed-117">説明</span><span class="sxs-lookup"><span data-stu-id="3c5ed-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="3c5ed-118">日付型</span><span class="sxs-lookup"><span data-stu-id="3c5ed-118">datetime</span></span> | <span data-ttu-id="3c5ed-119">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="3c5ed-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="3c5ed-120">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-120">string</span></span> | <span data-ttu-id="3c5ed-121">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="3c5ed-121">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="3c5ed-122">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-122">string</span></span> | <span data-ttu-id="3c5ed-123">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="3c5ed-123">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="3c5ed-124">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-124">string</span></span> | <span data-ttu-id="3c5ed-125">アプリケーションの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="3c5ed-125">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="3c5ed-126">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-126">string</span></span> | <span data-ttu-id="3c5ed-127">Azure Active Directory のアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="3c5ed-127">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="3c5ed-128">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-128">string</span></span> | <span data-ttu-id="3c5ed-129">アドレス帳に表示されるアカウント ユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="3c5ed-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="3c5ed-130">通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="3c5ed-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="3c5ed-131">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-131">string</span></span> | <span data-ttu-id="3c5ed-132">アクティビティが管理者によって実行されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3c5ed-132">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="3c5ed-133">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-133">string</span></span> | <span data-ttu-id="3c5ed-134">目的と機能に基づくデバイスの種類 ("ネットワーク デバイス"、"ワークステーション"、"Server"、"Mobile"、"Gaming console"、"Printer" など)</span><span class="sxs-lookup"><span data-stu-id="3c5ed-134">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="3c5ed-135">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-135">string</span></span> | <span data-ttu-id="3c5ed-136">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="3c5ed-136">Platform of the operating system running on the device.</span></span> <span data-ttu-id="3c5ed-137">この列は、同じファミリ内のバリエーション (Windows 10 や Windows 7 など) を含む特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="3c5ed-137">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="3c5ed-138">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-138">string</span></span> | <span data-ttu-id="3c5ed-139">エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3c5ed-139">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="3c5ed-140">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-140">string</span></span> | <span data-ttu-id="3c5ed-141">IP アドレスが既知の匿名プロキシに属するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3c5ed-141">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="3c5ed-142">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-142">string</span></span> | <span data-ttu-id="3c5ed-143">クライアント IP アドレスが地理的に位置付けされている国を示す 2 文字のコード</span><span class="sxs-lookup"><span data-stu-id="3c5ed-143">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="3c5ed-144">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-144">string</span></span> | <span data-ttu-id="3c5ed-145">クライアント IP アドレスが地理的に位置付けされている都市</span><span class="sxs-lookup"><span data-stu-id="3c5ed-145">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="3c5ed-146">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-146">string</span></span> | <span data-ttu-id="3c5ed-147">IP アドレスに関連付けられたインターネット サービス プロバイダー (ISP)</span><span class="sxs-lookup"><span data-stu-id="3c5ed-147">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="3c5ed-148">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-148">string</span></span> | <span data-ttu-id="3c5ed-149">Web ブラウザーまたは他のクライアント アプリケーションからのユーザー エージェント情報</span><span class="sxs-lookup"><span data-stu-id="3c5ed-149">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="3c5ed-150">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-150">string</span></span> | <span data-ttu-id="3c5ed-151">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="3c5ed-151">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="3c5ed-152">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-152">string</span></span> | <span data-ttu-id="3c5ed-153">記録されたアクティビティに含まれるファイルやフォルダーなどのオブジェクトの一覧</span><span class="sxs-lookup"><span data-stu-id="3c5ed-153">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="3c5ed-154">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-154">string</span></span> | <span data-ttu-id="3c5ed-155">記録されたアクションが適用されたオブジェクトの名前</span><span class="sxs-lookup"><span data-stu-id="3c5ed-155">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="3c5ed-156">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-156">string</span></span> | <span data-ttu-id="3c5ed-157">記録されたアクションが適用されたオブジェクトの種類 (ファイルやフォルダーなど)</span><span class="sxs-lookup"><span data-stu-id="3c5ed-157">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="3c5ed-158">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-158">string</span></span> | <span data-ttu-id="3c5ed-159">記録されたアクションが適用されたオブジェクトの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="3c5ed-159">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="3c5ed-160">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-160">string</span></span> | <span data-ttu-id="3c5ed-161">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="3c5ed-161">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="3c5ed-162">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-162">string</span></span> | <span data-ttu-id="3c5ed-163">JSON 形式のソース アプリケーションまたはサービスからの生のイベント情報</span><span class="sxs-lookup"><span data-stu-id="3c5ed-163">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="3c5ed-164">string</span><span class="sxs-lookup"><span data-stu-id="3c5ed-164">string</span></span> | <span data-ttu-id="3c5ed-165">エンティティまたはイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="3c5ed-165">Additional information about the entity or event</span></span> |

## <a name="apps-and-services-covered"></a><span data-ttu-id="3c5ed-166">対象となるアプリとサービス</span><span class="sxs-lookup"><span data-stu-id="3c5ed-166">Apps and services covered</span></span>

- <span data-ttu-id="3c5ed-167">Dropbox</span><span class="sxs-lookup"><span data-stu-id="3c5ed-167">Dropbox</span></span>
- <span data-ttu-id="3c5ed-168">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3c5ed-168">Dynamics 365</span></span>
- <span data-ttu-id="3c5ed-169">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3c5ed-169">Exchange Online</span></span>
- <span data-ttu-id="3c5ed-170">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3c5ed-170">Microsoft Teams</span></span>
- <span data-ttu-id="3c5ed-171">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="3c5ed-171">OneDrive for Business</span></span>
- <span data-ttu-id="3c5ed-172">Power Automate</span><span class="sxs-lookup"><span data-stu-id="3c5ed-172">Power Automate</span></span>
- <span data-ttu-id="3c5ed-173">Power BI</span><span class="sxs-lookup"><span data-stu-id="3c5ed-173">Power BI</span></span>
- <span data-ttu-id="3c5ed-174">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3c5ed-174">SharePoint Online</span></span>
- <span data-ttu-id="3c5ed-175">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3c5ed-175">Skype for Business</span></span>
- <span data-ttu-id="3c5ed-176">Office 365</span><span class="sxs-lookup"><span data-stu-id="3c5ed-176">Office 365</span></span>
- <span data-ttu-id="3c5ed-177">Yammer</span><span class="sxs-lookup"><span data-stu-id="3c5ed-177">Yammer</span></span> 

## <a name="related-topics"></a><span data-ttu-id="3c5ed-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c5ed-178">Related topics</span></span>
- [<span data-ttu-id="3c5ed-179">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="3c5ed-179">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3c5ed-180">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="3c5ed-180">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3c5ed-181">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="3c5ed-181">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3c5ed-182">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="3c5ed-182">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3c5ed-183">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="3c5ed-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3c5ed-184">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="3c5ed-184">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
