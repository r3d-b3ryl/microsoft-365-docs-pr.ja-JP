---
title: 高度な検索スキーマの AppFileEvents テーブル
description: 高度な検索スキーマの AppFileEvents テーブルで、クラウド アプリとサービスに関連するファイル関連のイベントについて説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、AppFileEvents、Cloud App Security、MCAS
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
ms.openlocfilehash: 59e9affc53398f2a1b06fbab9774e4b53e146425
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932876"
---
# <a name="appfileevents"></a><span data-ttu-id="6fa4e-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="6fa4e-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6fa4e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6fa4e-105">**Applies to:**</span></span>
- <span data-ttu-id="6fa4e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6fa4e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6fa4e-107">高度 `AppFileEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、Microsoft Cloud App Security によって監視されるクラウド アプリおよびサービスにおけるファイル関連のアクティビティに関する情報が含されています。</span><span class="sxs-lookup"><span data-stu-id="6fa4e-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="6fa4e-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="6fa4e-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="6fa4e-109">テーブルでサポートされているイベントの種類 ( 値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ `ActionType` リファレンスを使用してください。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="6fa4e-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="6fa4e-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fa4e-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6fa4e-111">列名</span><span class="sxs-lookup"><span data-stu-id="6fa4e-111">Column name</span></span> | <span data-ttu-id="6fa4e-112">データ型</span><span class="sxs-lookup"><span data-stu-id="6fa4e-112">Data type</span></span> | <span data-ttu-id="6fa4e-113">説明</span><span class="sxs-lookup"><span data-stu-id="6fa4e-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6fa4e-114">日付型</span><span class="sxs-lookup"><span data-stu-id="6fa4e-114">datetime</span></span> | <span data-ttu-id="6fa4e-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="6fa4e-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="6fa4e-116">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-116">string</span></span> | <span data-ttu-id="6fa4e-117">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="6fa4e-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="6fa4e-118">詳細については [、ポータル内スキーマ リファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fa4e-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="6fa4e-119">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-119">string</span></span> | <span data-ttu-id="6fa4e-120">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="6fa4e-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="6fa4e-121">文字列</span><span class="sxs-lookup"><span data-stu-id="6fa4e-121">string</span></span> | <span data-ttu-id="6fa4e-122">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="6fa4e-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="6fa4e-123">文字列</span><span class="sxs-lookup"><span data-stu-id="6fa4e-123">string</span></span> | <span data-ttu-id="6fa4e-124">記録されたアクションが適用されたファイルを含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="6fa4e-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="6fa4e-125">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-125">string</span></span> | <span data-ttu-id="6fa4e-126">アクションの結果として名前が変更されたファイルの元の名前</span><span class="sxs-lookup"><span data-stu-id="6fa4e-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="6fa4e-127">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-127">string</span></span> | <span data-ttu-id="6fa4e-128">記録されたアクションが適用される前のファイルを含む元のフォルダー</span><span class="sxs-lookup"><span data-stu-id="6fa4e-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="6fa4e-129">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-129">string</span></span> | <span data-ttu-id="6fa4e-130">使用されるネットワーク プロトコル</span><span class="sxs-lookup"><span data-stu-id="6fa4e-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="6fa4e-131">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-131">string</span></span> | <span data-ttu-id="6fa4e-132">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="6fa4e-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="6fa4e-133">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-133">string</span></span> | <span data-ttu-id="6fa4e-134">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="6fa4e-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="6fa4e-135">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-135">string</span></span> | <span data-ttu-id="6fa4e-136">アカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="6fa4e-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="6fa4e-137">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-137">string</span></span> | <span data-ttu-id="6fa4e-138">Azure AD のアカウントの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="6fa4e-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="6fa4e-139">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-139">string</span></span> | <span data-ttu-id="6fa4e-140">アドレス帳に表示されるアカウント ユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="6fa4e-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="6fa4e-141">通常、特定の名前または名、ミドル ネームの開始、姓または姓の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="6fa4e-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="6fa4e-142">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-142">string</span></span> | <span data-ttu-id="6fa4e-143">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="6fa4e-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="6fa4e-144">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-144">string</span></span> | <span data-ttu-id="6fa4e-145">デバイスの種類</span><span class="sxs-lookup"><span data-stu-id="6fa4e-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="6fa4e-146">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-146">string</span></span> | <span data-ttu-id="6fa4e-147">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="6fa4e-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="6fa4e-148">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="6fa4e-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="6fa4e-149">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-149">string</span></span> | <span data-ttu-id="6fa4e-150">エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="6fa4e-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="6fa4e-151">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-151">string</span></span> | <span data-ttu-id="6fa4e-152">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの名前</span><span class="sxs-lookup"><span data-stu-id="6fa4e-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="6fa4e-153">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-153">string</span></span> | <span data-ttu-id="6fa4e-154">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="6fa4e-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="6fa4e-155">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-155">string</span></span> | <span data-ttu-id="6fa4e-156">イベントに関連付けられている都市、国、その他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="6fa4e-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="6fa4e-157">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-157">string</span></span> | <span data-ttu-id="6fa4e-158">エンドポイント IP アドレスに関連付けられたインターネット サービス プロバイダー (ISP)</span><span class="sxs-lookup"><span data-stu-id="6fa4e-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="6fa4e-159">long</span><span class="sxs-lookup"><span data-stu-id="6fa4e-159">long</span></span> | <span data-ttu-id="6fa4e-160">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="6fa4e-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="6fa4e-161">string</span><span class="sxs-lookup"><span data-stu-id="6fa4e-161">string</span></span> | <span data-ttu-id="6fa4e-162">エンティティまたはイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="6fa4e-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6fa4e-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fa4e-163">Related topics</span></span>
- [<span data-ttu-id="6fa4e-164">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="6fa4e-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6fa4e-165">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="6fa4e-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6fa4e-166">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="6fa4e-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6fa4e-167">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="6fa4e-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6fa4e-168">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="6fa4e-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6fa4e-169">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="6fa4e-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
