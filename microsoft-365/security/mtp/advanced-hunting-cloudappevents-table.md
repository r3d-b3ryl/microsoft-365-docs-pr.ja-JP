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
ms.openlocfilehash: a8ba1f94bc704a5fe99d54b77aa6570c5e43d3f7
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712488"
---
# <a name="cloudappevents"></a><span data-ttu-id="4eb1b-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="4eb1b-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4eb1b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4eb1b-105">**Applies to:**</span></span>
- <span data-ttu-id="4eb1b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4eb1b-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="4eb1b-107">高度 `CloudAppEvents` な検索スキーマ[](advanced-hunting-overview.md)の表には、Microsoft Cloud App Security (特に Dropbox、Exchange Online、OneDrive、Microsoft Teams、SharePoint) でカバーされるさまざまなクラウド アプリとサービスのアクティビティに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security, specifically Dropbox, Exchange Online, OneDrive, Microsoft Teams, and SharePoint.</span></span> <span data-ttu-id="4eb1b-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-108">Use this reference to construct queries that return information from this table.</span></span>

>[!IMPORTANT]
><span data-ttu-id="4eb1b-109">この表には、表で使用できる情報が含 `AppFileEvents` まれています。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-109">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="4eb1b-110">2021 年 3 月 7 日から、この日付以降のクラウド サービスでファイル関連のアクティビティを検索するユーザーは、代わりにテーブルを `CloudAppEvents` 使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-110">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="4eb1b-111">テーブルを引き続き使用するクエリとカスタム検出ルールを検索し、テーブル `AppFileEvents` を使用するために編集 `CloudAppEvents` してください。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-111">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="4eb1b-112">影響を受けるクエリの変換に関する詳細なガイダンスについては [、「Microsoft 365 Defender](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)Advanced hunting を使用したクラウド アプリアクティビティ全体のハント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-112">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="4eb1b-113">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4eb1b-114">列名</span><span class="sxs-lookup"><span data-stu-id="4eb1b-114">Column name</span></span> | <span data-ttu-id="4eb1b-115">データ型</span><span class="sxs-lookup"><span data-stu-id="4eb1b-115">Data type</span></span> | <span data-ttu-id="4eb1b-116">説明</span><span class="sxs-lookup"><span data-stu-id="4eb1b-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="4eb1b-117">日付型</span><span class="sxs-lookup"><span data-stu-id="4eb1b-117">datetime</span></span> | <span data-ttu-id="4eb1b-118">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="4eb1b-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="4eb1b-119">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-119">string</span></span> | <span data-ttu-id="4eb1b-120">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="4eb1b-120">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="4eb1b-121">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-121">string</span></span> | <span data-ttu-id="4eb1b-122">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="4eb1b-122">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="4eb1b-123">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-123">string</span></span> | <span data-ttu-id="4eb1b-124">アプリケーションの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="4eb1b-124">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="4eb1b-125">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-125">string</span></span> | <span data-ttu-id="4eb1b-126">Azure Active Directory のアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="4eb1b-126">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="4eb1b-127">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-127">string</span></span> | <span data-ttu-id="4eb1b-128">アドレス帳に表示されるアカウント ユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-128">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="4eb1b-129">通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-129">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="4eb1b-130">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-130">string</span></span> | <span data-ttu-id="4eb1b-131">アクティビティが管理者によって実行されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-131">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="4eb1b-132">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-132">string</span></span> | <span data-ttu-id="4eb1b-133">目的と機能に基づくデバイスの種類 ("ネットワーク デバイス"、"ワークステーション"、"Server"、"Mobile"、"Gaming console"、"Printer" など)</span><span class="sxs-lookup"><span data-stu-id="4eb1b-133">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="4eb1b-134">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-134">string</span></span> | <span data-ttu-id="4eb1b-135">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-135">Platform of the operating system running on the device.</span></span> <span data-ttu-id="4eb1b-136">この列は、同じファミリ内のバリエーション (Windows 10 や Windows 7 など) を含む特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-136">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="4eb1b-137">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-137">string</span></span> | <span data-ttu-id="4eb1b-138">エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4eb1b-138">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="4eb1b-139">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-139">string</span></span> | <span data-ttu-id="4eb1b-140">IP アドレスが既知の匿名プロキシに属するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-140">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="4eb1b-141">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-141">string</span></span> | <span data-ttu-id="4eb1b-142">クライアント IP アドレスが地理的に位置付けされている国を示す 2 文字のコード</span><span class="sxs-lookup"><span data-stu-id="4eb1b-142">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="4eb1b-143">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-143">string</span></span> | <span data-ttu-id="4eb1b-144">クライアント IP アドレスが地理的に位置付けされている都市</span><span class="sxs-lookup"><span data-stu-id="4eb1b-144">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="4eb1b-145">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-145">string</span></span> | <span data-ttu-id="4eb1b-146">IP アドレスに関連付けられたインターネット サービス プロバイダー (ISP)</span><span class="sxs-lookup"><span data-stu-id="4eb1b-146">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="4eb1b-147">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-147">string</span></span> | <span data-ttu-id="4eb1b-148">Web ブラウザーまたは他のクライアント アプリケーションからのユーザー エージェント情報</span><span class="sxs-lookup"><span data-stu-id="4eb1b-148">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="4eb1b-149">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-149">string</span></span> | <span data-ttu-id="4eb1b-150">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="4eb1b-150">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="4eb1b-151">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-151">string</span></span> | <span data-ttu-id="4eb1b-152">記録されたアクティビティに含まれるファイルやフォルダーなどのオブジェクトの一覧</span><span class="sxs-lookup"><span data-stu-id="4eb1b-152">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="4eb1b-153">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-153">string</span></span> | <span data-ttu-id="4eb1b-154">記録されたアクションが適用されたオブジェクトの名前</span><span class="sxs-lookup"><span data-stu-id="4eb1b-154">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="4eb1b-155">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-155">string</span></span> | <span data-ttu-id="4eb1b-156">記録されたアクションが適用されたオブジェクトの種類 (ファイルやフォルダーなど)</span><span class="sxs-lookup"><span data-stu-id="4eb1b-156">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="4eb1b-157">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-157">string</span></span> | <span data-ttu-id="4eb1b-158">記録されたアクションが適用されたオブジェクトの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="4eb1b-158">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="4eb1b-159">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-159">string</span></span> | <span data-ttu-id="4eb1b-160">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="4eb1b-160">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="4eb1b-161">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-161">string</span></span> | <span data-ttu-id="4eb1b-162">JSON 形式のソース アプリケーションまたはサービスからの生のイベント情報</span><span class="sxs-lookup"><span data-stu-id="4eb1b-162">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="4eb1b-163">string</span><span class="sxs-lookup"><span data-stu-id="4eb1b-163">string</span></span> | <span data-ttu-id="4eb1b-164">エンティティまたはイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="4eb1b-164">Additional information about the entity or event</span></span> |


## <a name="related-topics"></a><span data-ttu-id="4eb1b-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="4eb1b-165">Related topics</span></span>
- [<span data-ttu-id="4eb1b-166">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="4eb1b-166">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4eb1b-167">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="4eb1b-167">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4eb1b-168">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="4eb1b-168">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4eb1b-169">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="4eb1b-169">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4eb1b-170">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="4eb1b-170">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4eb1b-171">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="4eb1b-171">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
