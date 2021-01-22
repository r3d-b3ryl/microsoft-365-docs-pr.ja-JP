---
title: 高度な検索スキーマの CloudAppEvents テーブル
description: 高度な検索スキーマの CloudAppEvents テーブルにあるクラウド アプリとサービスからのイベントについて説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、CloudAppEvents、Cloud App Security、MCAS
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
ms.openlocfilehash: 021a8210bbe5886021e980b33ade0b9e2ded7b5b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928455"
---
# <a name="cloudappevents"></a><span data-ttu-id="5fc5e-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="5fc5e-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5fc5e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5fc5e-105">**Applies to:**</span></span>
- <span data-ttu-id="5fc5e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fc5e-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="5fc5e-107">現在プレビューで利用可能な高度な検索スキーマの表には、さまざまなクラウド アプリとサービス、特に Microsoft Teams と Exchange Online のアクティビティに関する情報 `CloudAppEvents` が含されています。 [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5fc5e-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="5fc5e-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="5fc5e-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="5fc5e-109">次の表は、Microsoft Cloud App Security によって監視されるその他のアクティビティを含む拡張されます。</span><span class="sxs-lookup"><span data-stu-id="5fc5e-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="5fc5e-110">最終的に、このテーブルには [、AppFileEvents](advanced-hunting-appfileevents-table.md) テーブルに現在格納されているファイル アクティビティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5fc5e-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="5fc5e-111">Microsoft では、この表に移動するデータの数が多い場合に、追加のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5fc5e-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="5fc5e-112">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fc5e-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5fc5e-113">列名</span><span class="sxs-lookup"><span data-stu-id="5fc5e-113">Column name</span></span> | <span data-ttu-id="5fc5e-114">データ型</span><span class="sxs-lookup"><span data-stu-id="5fc5e-114">Data type</span></span> | <span data-ttu-id="5fc5e-115">説明</span><span class="sxs-lookup"><span data-stu-id="5fc5e-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="5fc5e-116">日付型</span><span class="sxs-lookup"><span data-stu-id="5fc5e-116">datetime</span></span> | <span data-ttu-id="5fc5e-117">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="5fc5e-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="5fc5e-118">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-118">string</span></span> | <span data-ttu-id="5fc5e-119">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="5fc5e-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="5fc5e-120">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-120">string</span></span> | <span data-ttu-id="5fc5e-121">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="5fc5e-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="5fc5e-122">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-122">string</span></span> | <span data-ttu-id="5fc5e-123">アプリケーションの一意識別子</span><span class="sxs-lookup"><span data-stu-id="5fc5e-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="5fc5e-124">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-124">string</span></span> | <span data-ttu-id="5fc5e-125">Azure Active Directory のアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="5fc5e-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="5fc5e-126">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-126">string</span></span> | <span data-ttu-id="5fc5e-127">アドレス帳に表示されるアカウント ユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="5fc5e-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="5fc5e-128">通常、特定の名前または名、ミドル ネームの開始、姓または姓の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="5fc5e-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="5fc5e-129">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-129">string</span></span> | <span data-ttu-id="5fc5e-130">アクティビティが管理者によって実行されたかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="5fc5e-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="5fc5e-131">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-131">string</span></span> | <span data-ttu-id="5fc5e-132">目的と機能に基づくデバイスの種類 ("ネットワーク デバイス"、"Workstation"、"Server"、"Mobile"、"Gaming console"、"Printer" など)</span><span class="sxs-lookup"><span data-stu-id="5fc5e-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="5fc5e-133">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-133">string</span></span> | <span data-ttu-id="5fc5e-134">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="5fc5e-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="5fc5e-135">この列は、Windows 10 や Windows 7 など、同じファミリ内のバリエーションなど、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="5fc5e-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="5fc5e-136">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-136">string</span></span> | <span data-ttu-id="5fc5e-137">エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="5fc5e-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="5fc5e-138">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-138">string</span></span> | <span data-ttu-id="5fc5e-139">IP アドレスが既知の匿名プロキシに属するかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="5fc5e-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="5fc5e-140">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-140">string</span></span> | <span data-ttu-id="5fc5e-141">クライアント IP アドレスが地理的に位置する国を示す 2 文字のコード</span><span class="sxs-lookup"><span data-stu-id="5fc5e-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="5fc5e-142">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-142">string</span></span> | <span data-ttu-id="5fc5e-143">クライアント IP アドレスが地理的に位置する市区町地</span><span class="sxs-lookup"><span data-stu-id="5fc5e-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="5fc5e-144">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-144">string</span></span> | <span data-ttu-id="5fc5e-145">IP アドレスに関連付けられているインターネット サービス プロバイダー (ISP)</span><span class="sxs-lookup"><span data-stu-id="5fc5e-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="5fc5e-146">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-146">string</span></span> | <span data-ttu-id="5fc5e-147">Web ブラウザーまたは他のクライアント アプリケーションからのユーザー エージェント情報</span><span class="sxs-lookup"><span data-stu-id="5fc5e-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="5fc5e-148">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-148">string</span></span> | <span data-ttu-id="5fc5e-149">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="5fc5e-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="5fc5e-150">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-150">string</span></span> | <span data-ttu-id="5fc5e-151">記録されたアクティビティに関係したオブジェクト (ファイルやフォルダーなど) のリスト</span><span class="sxs-lookup"><span data-stu-id="5fc5e-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="5fc5e-152">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-152">string</span></span> | <span data-ttu-id="5fc5e-153">記録されたアクションが適用されたオブジェクトの名前</span><span class="sxs-lookup"><span data-stu-id="5fc5e-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="5fc5e-154">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-154">string</span></span> | <span data-ttu-id="5fc5e-155">記録されたアクションが適用されたオブジェクトの種類 (ファイルやフォルダーなど)</span><span class="sxs-lookup"><span data-stu-id="5fc5e-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="5fc5e-156">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-156">string</span></span> | <span data-ttu-id="5fc5e-157">記録されたアクションが適用されたオブジェクトの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="5fc5e-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="5fc5e-158">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-158">string</span></span> | <span data-ttu-id="5fc5e-159">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="5fc5e-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="5fc5e-160">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-160">string</span></span> | <span data-ttu-id="5fc5e-161">JSON 形式のソース アプリケーションまたはサービスからの生のイベント情報</span><span class="sxs-lookup"><span data-stu-id="5fc5e-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="5fc5e-162">string</span><span class="sxs-lookup"><span data-stu-id="5fc5e-162">string</span></span> | <span data-ttu-id="5fc5e-163">エンティティまたはイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="5fc5e-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5fc5e-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fc5e-164">Related topics</span></span>
- [<span data-ttu-id="5fc5e-165">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="5fc5e-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5fc5e-166">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="5fc5e-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5fc5e-167">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="5fc5e-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5fc5e-168">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="5fc5e-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5fc5e-169">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="5fc5e-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5fc5e-170">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="5fc5e-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
