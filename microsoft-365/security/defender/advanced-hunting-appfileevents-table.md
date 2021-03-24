---
title: 高度な検索スキーマの AppFileEvents テーブル
description: 高度なハンティング スキーマの AppFileEvents テーブルで、クラウド アプリとサービスに関連付けられているファイル関連のイベントについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、AppFileEvents、Cloud App Security、MCAS
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
ms.openlocfilehash: f25570916692c4568a6d09d92faaf57b0c155029
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063603"
---
# <a name="appfileevents"></a><span data-ttu-id="cfada-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="cfada-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cfada-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cfada-105">**Applies to:**</span></span>
- <span data-ttu-id="cfada-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cfada-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="cfada-107">高度 `AppFileEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、Microsoft Cloud App Security によって監視されるクラウド アプリおよびサービスにおけるファイル関連のアクティビティに関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="cfada-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="cfada-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="cfada-108">Use this reference to construct queries that return information from this table.</span></span>

>[!WARNING]
><span data-ttu-id="cfada-109">このテーブルは近日廃止されます。</span><span class="sxs-lookup"><span data-stu-id="cfada-109">This table will be retired soon.</span></span> <span data-ttu-id="cfada-110">2021 年 3 月 7 日現在、テーブル `AppFileEvents` はレコードをログに記録しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="cfada-110">As of March 7, 2021, the `AppFileEvents` table is no longer logging records.</span></span> <span data-ttu-id="cfada-111">クラウド サービスのファイル関連のアクティビティを検索するユーザーは、その日付以降に、 [代わりに CloudAppEvents](advanced-hunting-cloudappevents-table.md) テーブルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfada-111">Users hunting through file-related activities in cloud services on and beyond the said date should use the [CloudAppEvents](advanced-hunting-cloudappevents-table.md) table instead.</span></span> <br><br><span data-ttu-id="cfada-112">テーブルを引き続き使用するクエリとカスタム検出ルールを検索し、テーブル `AppFileEvents` を使用するために編集 `CloudAppEvents` してください。</span><span class="sxs-lookup"><span data-stu-id="cfada-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="cfada-113">影響を受けるクエリの変換に関する詳細なガイダンスについては [、「Microsoft 365 Defender](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)Advanced hunting を使用したクラウド アプリアクティビティ全体のハント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfada-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="cfada-114">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfada-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="cfada-115">列名</span><span class="sxs-lookup"><span data-stu-id="cfada-115">Column name</span></span> | <span data-ttu-id="cfada-116">データ型</span><span class="sxs-lookup"><span data-stu-id="cfada-116">Data type</span></span> | <span data-ttu-id="cfada-117">説明</span><span class="sxs-lookup"><span data-stu-id="cfada-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="cfada-118">日付型</span><span class="sxs-lookup"><span data-stu-id="cfada-118">datetime</span></span> | <span data-ttu-id="cfada-119">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="cfada-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="cfada-120">string</span><span class="sxs-lookup"><span data-stu-id="cfada-120">string</span></span> | <span data-ttu-id="cfada-121">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="cfada-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="cfada-122">詳細については [、ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfada-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="cfada-123">string</span><span class="sxs-lookup"><span data-stu-id="cfada-123">string</span></span> | <span data-ttu-id="cfada-124">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="cfada-124">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="cfada-125">文字列</span><span class="sxs-lookup"><span data-stu-id="cfada-125">string</span></span> | <span data-ttu-id="cfada-126">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="cfada-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="cfada-127">文字列</span><span class="sxs-lookup"><span data-stu-id="cfada-127">string</span></span> | <span data-ttu-id="cfada-128">記録されたアクションが適用されたファイルを含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="cfada-128">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="cfada-129">string</span><span class="sxs-lookup"><span data-stu-id="cfada-129">string</span></span> | <span data-ttu-id="cfada-130">アクションの結果として名前が変更されたファイルの元の名前</span><span class="sxs-lookup"><span data-stu-id="cfada-130">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="cfada-131">string</span><span class="sxs-lookup"><span data-stu-id="cfada-131">string</span></span> | <span data-ttu-id="cfada-132">記録されたアクションが適用される前のファイルを含む元のフォルダー</span><span class="sxs-lookup"><span data-stu-id="cfada-132">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="cfada-133">string</span><span class="sxs-lookup"><span data-stu-id="cfada-133">string</span></span> | <span data-ttu-id="cfada-134">使用されるネットワーク プロトコル</span><span class="sxs-lookup"><span data-stu-id="cfada-134">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="cfada-135">string</span><span class="sxs-lookup"><span data-stu-id="cfada-135">string</span></span> | <span data-ttu-id="cfada-136">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="cfada-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="cfada-137">string</span><span class="sxs-lookup"><span data-stu-id="cfada-137">string</span></span> | <span data-ttu-id="cfada-138">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="cfada-138">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="cfada-139">string</span><span class="sxs-lookup"><span data-stu-id="cfada-139">string</span></span> | <span data-ttu-id="cfada-140">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="cfada-140">Security Identifier (SID) of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="cfada-141">string</span><span class="sxs-lookup"><span data-stu-id="cfada-141">string</span></span> | <span data-ttu-id="cfada-142">アカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="cfada-142">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="cfada-143">string</span><span class="sxs-lookup"><span data-stu-id="cfada-143">string</span></span> | <span data-ttu-id="cfada-144">Azure アカウントのアカウントの一意AD</span><span class="sxs-lookup"><span data-stu-id="cfada-144">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="cfada-145">string</span><span class="sxs-lookup"><span data-stu-id="cfada-145">string</span></span> | <span data-ttu-id="cfada-146">アドレス帳に表示されるアカウント ユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="cfada-146">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="cfada-147">通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="cfada-147">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="cfada-148">string</span><span class="sxs-lookup"><span data-stu-id="cfada-148">string</span></span> | <span data-ttu-id="cfada-149">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="cfada-149">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="cfada-150">string</span><span class="sxs-lookup"><span data-stu-id="cfada-150">string</span></span> | <span data-ttu-id="cfada-151">デバイスの種類</span><span class="sxs-lookup"><span data-stu-id="cfada-151">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="cfada-152">string</span><span class="sxs-lookup"><span data-stu-id="cfada-152">string</span></span> | <span data-ttu-id="cfada-153">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="cfada-153">Platform of the operating system running on the device.</span></span> <span data-ttu-id="cfada-154">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="cfada-154">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="cfada-155">string</span><span class="sxs-lookup"><span data-stu-id="cfada-155">string</span></span> | <span data-ttu-id="cfada-156">エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="cfada-156">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="cfada-157">string</span><span class="sxs-lookup"><span data-stu-id="cfada-157">string</span></span> | <span data-ttu-id="cfada-158">通信中に使用される TCP ポート</span><span class="sxs-lookup"><span data-stu-id="cfada-158">TCP port used during communication</span></span>  |
| `DestinationDeviceName` | <span data-ttu-id="cfada-159">string</span><span class="sxs-lookup"><span data-stu-id="cfada-159">string</span></span> | <span data-ttu-id="cfada-160">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの名前</span><span class="sxs-lookup"><span data-stu-id="cfada-160">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="cfada-161">string</span><span class="sxs-lookup"><span data-stu-id="cfada-161">string</span></span> | <span data-ttu-id="cfada-162">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="cfada-162">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="cfada-163">string</span><span class="sxs-lookup"><span data-stu-id="cfada-163">string</span></span> | <span data-ttu-id="cfada-164">関連するネットワーク通信の宛先ポート</span><span class="sxs-lookup"><span data-stu-id="cfada-164">Destination port of related network communications</span></span> |
| `Location` | <span data-ttu-id="cfada-165">string</span><span class="sxs-lookup"><span data-stu-id="cfada-165">string</span></span> | <span data-ttu-id="cfada-166">イベントに関連付けられている都市、国、その他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="cfada-166">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="cfada-167">string</span><span class="sxs-lookup"><span data-stu-id="cfada-167">string</span></span> | <span data-ttu-id="cfada-168">エンドポイント IP アドレスに関連付けられたインターネット サービス プロバイダー (ISP)</span><span class="sxs-lookup"><span data-stu-id="cfada-168">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="cfada-169">long</span><span class="sxs-lookup"><span data-stu-id="cfada-169">long</span></span> | <span data-ttu-id="cfada-170">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="cfada-170">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="cfada-171">string</span><span class="sxs-lookup"><span data-stu-id="cfada-171">string</span></span> | <span data-ttu-id="cfada-172">エンティティまたはイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="cfada-172">Additional information about the entity or event</span></span> |

>[!TIP]
> <span data-ttu-id="cfada-173">テーブルでサポートされるイベントの種類 (値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ参照 `ActionType` を使用します。</span><span class="sxs-lookup"><span data-stu-id="cfada-173">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>


## <a name="related-topics"></a><span data-ttu-id="cfada-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfada-174">Related topics</span></span>
- [<span data-ttu-id="cfada-175">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="cfada-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cfada-176">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="cfada-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cfada-177">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="cfada-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="cfada-178">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="cfada-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="cfada-179">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="cfada-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="cfada-180">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="cfada-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
