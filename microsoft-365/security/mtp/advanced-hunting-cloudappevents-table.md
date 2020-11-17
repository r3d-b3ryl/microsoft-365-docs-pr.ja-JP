---
title: 高度な検索スキーマの CloudAppEvents テーブル
description: 高度な検索スキーマの CloudAppEvents テーブルにあるクラウドアプリおよびサービスからのイベントについて説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検出、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、CloudAppEvents、Cloud App Security、MCAS
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087772"
---
# <a name="cloudappevents"></a><span data-ttu-id="a623b-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="a623b-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a623b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a623b-105">**Applies to:**</span></span>
- <span data-ttu-id="a623b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a623b-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="a623b-107">現在プレビューで利用可能ですが、 `CloudAppEvents` [高度な](advanced-hunting-overview.md) 検索スキーマの表には、さまざまなクラウドアプリおよびサービスのアクティビティに関する情報、特に Microsoft Teams と Exchange Online が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a623b-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="a623b-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a623b-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="a623b-109">この表を拡張して、Microsoft Cloud App Security によって監視されるアクティビティを増やします。</span><span class="sxs-lookup"><span data-stu-id="a623b-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="a623b-110">最終的に、この表には [Appfileevents](advanced-hunting-appfileevents-table.md) テーブルに現在格納されているファイルアクティビティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a623b-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="a623b-111">Microsoft は、この表へのデータの移動に関する追加のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="a623b-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="a623b-112">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a623b-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a623b-113">列名</span><span class="sxs-lookup"><span data-stu-id="a623b-113">Column name</span></span> | <span data-ttu-id="a623b-114">データ型</span><span class="sxs-lookup"><span data-stu-id="a623b-114">Data type</span></span> | <span data-ttu-id="a623b-115">説明</span><span class="sxs-lookup"><span data-stu-id="a623b-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a623b-116">日付型</span><span class="sxs-lookup"><span data-stu-id="a623b-116">datetime</span></span> | <span data-ttu-id="a623b-117">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="a623b-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="a623b-118">string</span><span class="sxs-lookup"><span data-stu-id="a623b-118">string</span></span> | <span data-ttu-id="a623b-119">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="a623b-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="a623b-120">string</span><span class="sxs-lookup"><span data-stu-id="a623b-120">string</span></span> | <span data-ttu-id="a623b-121">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="a623b-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="a623b-122">string</span><span class="sxs-lookup"><span data-stu-id="a623b-122">string</span></span> | <span data-ttu-id="a623b-123">アプリケーションの一意識別子</span><span class="sxs-lookup"><span data-stu-id="a623b-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="a623b-124">string</span><span class="sxs-lookup"><span data-stu-id="a623b-124">string</span></span> | <span data-ttu-id="a623b-125">Azure Active Directory のアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="a623b-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="a623b-126">string</span><span class="sxs-lookup"><span data-stu-id="a623b-126">string</span></span> | <span data-ttu-id="a623b-127">アドレス帳に表示されるアカウントユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="a623b-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="a623b-128">通常、指定された名前または名、ミドルネーム、姓の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="a623b-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="a623b-129">string</span><span class="sxs-lookup"><span data-stu-id="a623b-129">string</span></span> | <span data-ttu-id="a623b-130">アクティビティが管理者によって実行されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a623b-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="a623b-131">string</span><span class="sxs-lookup"><span data-stu-id="a623b-131">string</span></span> | <span data-ttu-id="a623b-132">目的と機能に基づいたデバイスの種類 ("ネットワークデバイス"、"ワークステーション"、"サーバー"、"モバイル"、"ゲームコンソール"、"プリンター" など)</span><span class="sxs-lookup"><span data-stu-id="a623b-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="a623b-133">string</span><span class="sxs-lookup"><span data-stu-id="a623b-133">string</span></span> | <span data-ttu-id="a623b-134">デバイス上で実行されているオペレーティングシステムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="a623b-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="a623b-135">この列は、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="a623b-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="a623b-136">string</span><span class="sxs-lookup"><span data-stu-id="a623b-136">string</span></span> | <span data-ttu-id="a623b-137">エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a623b-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="a623b-138">string</span><span class="sxs-lookup"><span data-stu-id="a623b-138">string</span></span> | <span data-ttu-id="a623b-139">IP アドレスが既知の匿名プロキシに属するかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="a623b-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="a623b-140">string</span><span class="sxs-lookup"><span data-stu-id="a623b-140">string</span></span> | <span data-ttu-id="a623b-141">クライアント IP アドレスが geolocated する国を示す2文字のコード</span><span class="sxs-lookup"><span data-stu-id="a623b-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="a623b-142">string</span><span class="sxs-lookup"><span data-stu-id="a623b-142">string</span></span> | <span data-ttu-id="a623b-143">クライアント IP アドレスが geolocated する市区町村</span><span class="sxs-lookup"><span data-stu-id="a623b-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="a623b-144">string</span><span class="sxs-lookup"><span data-stu-id="a623b-144">string</span></span> | <span data-ttu-id="a623b-145">IP アドレスに関連付けられているインターネットサービスプロバイダー (ISP)</span><span class="sxs-lookup"><span data-stu-id="a623b-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="a623b-146">string</span><span class="sxs-lookup"><span data-stu-id="a623b-146">string</span></span> | <span data-ttu-id="a623b-147">Web ブラウザーまたは他のクライアントアプリケーションからのユーザーエージェント情報</span><span class="sxs-lookup"><span data-stu-id="a623b-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="a623b-148">string</span><span class="sxs-lookup"><span data-stu-id="a623b-148">string</span></span> | <span data-ttu-id="a623b-149">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="a623b-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="a623b-150">string</span><span class="sxs-lookup"><span data-stu-id="a623b-150">string</span></span> | <span data-ttu-id="a623b-151">記録されたアクティビティに関係したオブジェクト (ファイルまたはフォルダーなど) のリスト</span><span class="sxs-lookup"><span data-stu-id="a623b-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="a623b-152">string</span><span class="sxs-lookup"><span data-stu-id="a623b-152">string</span></span> | <span data-ttu-id="a623b-153">記録されたアクションが適用されたオブジェクトの名前</span><span class="sxs-lookup"><span data-stu-id="a623b-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="a623b-154">string</span><span class="sxs-lookup"><span data-stu-id="a623b-154">string</span></span> | <span data-ttu-id="a623b-155">記録された操作が適用されたオブジェクトの種類 (ファイルやフォルダーなど)</span><span class="sxs-lookup"><span data-stu-id="a623b-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="a623b-156">string</span><span class="sxs-lookup"><span data-stu-id="a623b-156">string</span></span> | <span data-ttu-id="a623b-157">記録されたアクションが適用されたオブジェクトの一意識別子</span><span class="sxs-lookup"><span data-stu-id="a623b-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="a623b-158">string</span><span class="sxs-lookup"><span data-stu-id="a623b-158">string</span></span> | <span data-ttu-id="a623b-159">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="a623b-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="a623b-160">string</span><span class="sxs-lookup"><span data-stu-id="a623b-160">string</span></span> | <span data-ttu-id="a623b-161">JSON 形式でのソースアプリケーションまたはサービスからの生イベント情報</span><span class="sxs-lookup"><span data-stu-id="a623b-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="a623b-162">string</span><span class="sxs-lookup"><span data-stu-id="a623b-162">string</span></span> | <span data-ttu-id="a623b-163">エンティティまたはイベントに関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="a623b-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a623b-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="a623b-164">Related topics</span></span>
- [<span data-ttu-id="a623b-165">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="a623b-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a623b-166">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="a623b-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a623b-167">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="a623b-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a623b-168">デバイス、メール、アプリ、ID 全体で捜索する</span><span class="sxs-lookup"><span data-stu-id="a623b-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a623b-169">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="a623b-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a623b-170">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="a623b-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
