---
title: 高度なハンティング スキーマの CloudAppEvents テーブル
description: 高度なハンティング スキーマの CloudAppEvents テーブルで、クラウド アプリとサービスからのイベントについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、CloudAppEvents、Cloud App Security、MCAS
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
ms.openlocfilehash: 17f424d368c0df2f07cda41917f005e4163e5750
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935871"
---
# <a name="cloudappevents"></a><span data-ttu-id="e98da-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="e98da-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e98da-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e98da-105">**Applies to:**</span></span>
- <span data-ttu-id="e98da-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e98da-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="e98da-107">高度 `CloudAppEvents` な検索スキーマの[表](advanced-hunting-overview.md)には、さまざまなクラウド アプリとサービスのアクティビティに関する情報が含Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="e98da-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security.</span></span> <span data-ttu-id="e98da-108">完全なリストについては、「対象のアプリ [とサービス」に移動します](#apps-and-services-covered)。</span><span class="sxs-lookup"><span data-stu-id="e98da-108">For a complete list, jump to [Apps and services covered](#apps-and-services-covered).</span></span> <span data-ttu-id="e98da-109">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e98da-109">Use this reference to construct queries that return information from this table.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="e98da-110">この表には、表で使用できる情報が含 `AppFileEvents` まれています。</span><span class="sxs-lookup"><span data-stu-id="e98da-110">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="e98da-111">2021 年 3 月 7 日から、この日付以降のクラウド サービスでファイル関連のアクティビティを検索するユーザーは、代わりにテーブルを `CloudAppEvents` 使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e98da-111">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="e98da-112">テーブルを引き続き使用するクエリとカスタム検出ルールを検索し、テーブル `AppFileEvents` を使用するために編集 `CloudAppEvents` してください。</span><span class="sxs-lookup"><span data-stu-id="e98da-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="e98da-113">影響を受けるクエリの変換に関する詳細なガイダンスについては、「Defender Advanced hunting を使用したクラウド アプリアクティビティMicrosoft 365[ハント」を参照してください](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)。</span><span class="sxs-lookup"><span data-stu-id="e98da-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="e98da-114">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e98da-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e98da-115">列名</span><span class="sxs-lookup"><span data-stu-id="e98da-115">Column name</span></span> | <span data-ttu-id="e98da-116">データ型</span><span class="sxs-lookup"><span data-stu-id="e98da-116">Data type</span></span> | <span data-ttu-id="e98da-117">説明</span><span class="sxs-lookup"><span data-stu-id="e98da-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e98da-118">日付型</span><span class="sxs-lookup"><span data-stu-id="e98da-118">datetime</span></span> | <span data-ttu-id="e98da-119">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="e98da-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="e98da-120">string</span><span class="sxs-lookup"><span data-stu-id="e98da-120">string</span></span> | <span data-ttu-id="e98da-121">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="e98da-121">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="e98da-122">string</span><span class="sxs-lookup"><span data-stu-id="e98da-122">string</span></span> | <span data-ttu-id="e98da-123">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="e98da-123">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="e98da-124">string</span><span class="sxs-lookup"><span data-stu-id="e98da-124">string</span></span> | <span data-ttu-id="e98da-125">アプリケーションの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="e98da-125">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="e98da-126">string</span><span class="sxs-lookup"><span data-stu-id="e98da-126">string</span></span> | <span data-ttu-id="e98da-127">アカウントの一意の識別子は、Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e98da-127">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="e98da-128">string</span><span class="sxs-lookup"><span data-stu-id="e98da-128">string</span></span> | <span data-ttu-id="e98da-129">アドレス帳に表示されるアカウント ユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="e98da-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="e98da-130">通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="e98da-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="e98da-131">string</span><span class="sxs-lookup"><span data-stu-id="e98da-131">string</span></span> | <span data-ttu-id="e98da-132">アクティビティが管理者によって実行されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e98da-132">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="e98da-133">string</span><span class="sxs-lookup"><span data-stu-id="e98da-133">string</span></span> | <span data-ttu-id="e98da-134">目的と機能に基づくデバイスの種類 ("ネットワーク デバイス"、"ワークステーション"、"Server"、"Mobile"、"Gaming console"、"Printer" など)</span><span class="sxs-lookup"><span data-stu-id="e98da-134">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="e98da-135">string</span><span class="sxs-lookup"><span data-stu-id="e98da-135">string</span></span> | <span data-ttu-id="e98da-136">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="e98da-136">Platform of the operating system running on the device.</span></span> <span data-ttu-id="e98da-137">この列は、特定のオペレーティング システム (同じファミリ内のバリエーション (Windows 10 7 など) をWindowsします。</span><span class="sxs-lookup"><span data-stu-id="e98da-137">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="e98da-138">string</span><span class="sxs-lookup"><span data-stu-id="e98da-138">string</span></span> | <span data-ttu-id="e98da-139">エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="e98da-139">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="e98da-140">string</span><span class="sxs-lookup"><span data-stu-id="e98da-140">string</span></span> | <span data-ttu-id="e98da-141">IP アドレスが既知の匿名プロキシに属するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e98da-141">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="e98da-142">string</span><span class="sxs-lookup"><span data-stu-id="e98da-142">string</span></span> | <span data-ttu-id="e98da-143">クライアント IP アドレスが地理的に位置付けされている国を示す 2 文字のコード</span><span class="sxs-lookup"><span data-stu-id="e98da-143">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="e98da-144">string</span><span class="sxs-lookup"><span data-stu-id="e98da-144">string</span></span> | <span data-ttu-id="e98da-145">クライアント IP アドレスが地理的に位置付けされている都市</span><span class="sxs-lookup"><span data-stu-id="e98da-145">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="e98da-146">string</span><span class="sxs-lookup"><span data-stu-id="e98da-146">string</span></span> | <span data-ttu-id="e98da-147">IP アドレスに関連付けられたインターネット サービス プロバイダー (ISP)</span><span class="sxs-lookup"><span data-stu-id="e98da-147">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="e98da-148">string</span><span class="sxs-lookup"><span data-stu-id="e98da-148">string</span></span> | <span data-ttu-id="e98da-149">Web ブラウザーまたは他のクライアント アプリケーションからのユーザー エージェント情報</span><span class="sxs-lookup"><span data-stu-id="e98da-149">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="e98da-150">string</span><span class="sxs-lookup"><span data-stu-id="e98da-150">string</span></span> | <span data-ttu-id="e98da-151">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="e98da-151">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="e98da-152">string</span><span class="sxs-lookup"><span data-stu-id="e98da-152">string</span></span> | <span data-ttu-id="e98da-153">記録されたアクティビティに含まれるファイルやフォルダーなどのオブジェクトの一覧</span><span class="sxs-lookup"><span data-stu-id="e98da-153">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="e98da-154">string</span><span class="sxs-lookup"><span data-stu-id="e98da-154">string</span></span> | <span data-ttu-id="e98da-155">記録されたアクションが適用されたオブジェクトの名前</span><span class="sxs-lookup"><span data-stu-id="e98da-155">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="e98da-156">string</span><span class="sxs-lookup"><span data-stu-id="e98da-156">string</span></span> | <span data-ttu-id="e98da-157">記録されたアクションが適用されたオブジェクトの種類 (ファイルやフォルダーなど)</span><span class="sxs-lookup"><span data-stu-id="e98da-157">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="e98da-158">string</span><span class="sxs-lookup"><span data-stu-id="e98da-158">string</span></span> | <span data-ttu-id="e98da-159">記録されたアクションが適用されたオブジェクトの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="e98da-159">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="e98da-160">string</span><span class="sxs-lookup"><span data-stu-id="e98da-160">string</span></span> | <span data-ttu-id="e98da-161">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="e98da-161">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="e98da-162">string</span><span class="sxs-lookup"><span data-stu-id="e98da-162">string</span></span> | <span data-ttu-id="e98da-163">JSON 形式のソース アプリケーションまたはサービスからの生のイベント情報</span><span class="sxs-lookup"><span data-stu-id="e98da-163">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="e98da-164">string</span><span class="sxs-lookup"><span data-stu-id="e98da-164">string</span></span> | <span data-ttu-id="e98da-165">エンティティまたはイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="e98da-165">Additional information about the entity or event</span></span> |

## <a name="apps-and-services-covered"></a><span data-ttu-id="e98da-166">対象となるアプリとサービス</span><span class="sxs-lookup"><span data-stu-id="e98da-166">Apps and services covered</span></span>

- <span data-ttu-id="e98da-167">Dropbox</span><span class="sxs-lookup"><span data-stu-id="e98da-167">Dropbox</span></span>
- <span data-ttu-id="e98da-168">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e98da-168">Dynamics 365</span></span>
- <span data-ttu-id="e98da-169">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e98da-169">Exchange Online</span></span>
- <span data-ttu-id="e98da-170">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e98da-170">Microsoft Teams</span></span>
- <span data-ttu-id="e98da-171">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="e98da-171">OneDrive for Business</span></span>
- <span data-ttu-id="e98da-172">Power Automate</span><span class="sxs-lookup"><span data-stu-id="e98da-172">Power Automate</span></span>
- <span data-ttu-id="e98da-173">Power BI</span><span class="sxs-lookup"><span data-stu-id="e98da-173">Power BI</span></span>
- <span data-ttu-id="e98da-174">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e98da-174">SharePoint Online</span></span>
- <span data-ttu-id="e98da-175">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e98da-175">Skype for Business</span></span>
- <span data-ttu-id="e98da-176">Office 365</span><span class="sxs-lookup"><span data-stu-id="e98da-176">Office 365</span></span>
- <span data-ttu-id="e98da-177">Yammer</span><span class="sxs-lookup"><span data-stu-id="e98da-177">Yammer</span></span> 

## <a name="related-topics"></a><span data-ttu-id="e98da-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="e98da-178">Related topics</span></span>
- [<span data-ttu-id="e98da-179">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="e98da-179">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e98da-180">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="e98da-180">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e98da-181">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="e98da-181">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e98da-182">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="e98da-182">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e98da-183">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="e98da-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e98da-184">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="e98da-184">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
