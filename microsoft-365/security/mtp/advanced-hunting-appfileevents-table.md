---
title: 高度な検索スキーマの AppFileEvents テーブル
description: 高度な検索スキーマの AppFileEvents テーブルで、クラウド アプリとサービスに関連するファイル関連のイベントについて説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、AppFileEvents、Cloud App Security、MCAS
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
ms.openlocfilehash: 8406d1f9e3d56555b1699d191933c6f9735c9574
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145489"
---
# <a name="appfileevents"></a><span data-ttu-id="0ec4d-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="0ec4d-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0ec4d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="0ec4d-105">**Applies to:**</span></span>
- <span data-ttu-id="0ec4d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ec4d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0ec4d-107">高度 `AppFileEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、Microsoft Cloud App Security によって監視されるクラウド アプリとサービスでのファイル関連のアクティビティに関する情報が含されています。</span><span class="sxs-lookup"><span data-stu-id="0ec4d-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="0ec4d-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="0ec4d-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="0ec4d-109">テーブルでサポートされているイベントの種類 ( 値) の詳細については、セキュリティ センターで使用可能な組み込みのスキーマ `ActionType` 参照を使用してください。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="0ec4d-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="0ec4d-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ec4d-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0ec4d-111">列名</span><span class="sxs-lookup"><span data-stu-id="0ec4d-111">Column name</span></span> | <span data-ttu-id="0ec4d-112">データ型</span><span class="sxs-lookup"><span data-stu-id="0ec4d-112">Data type</span></span> | <span data-ttu-id="0ec4d-113">説明</span><span class="sxs-lookup"><span data-stu-id="0ec4d-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0ec4d-114">日付型</span><span class="sxs-lookup"><span data-stu-id="0ec4d-114">datetime</span></span> | <span data-ttu-id="0ec4d-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="0ec4d-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="0ec4d-116">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-116">string</span></span> | <span data-ttu-id="0ec4d-117">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="0ec4d-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="0ec4d-118">詳細については [、ポータル内スキーマ リファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ec4d-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="0ec4d-119">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-119">string</span></span> | <span data-ttu-id="0ec4d-120">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="0ec4d-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="0ec4d-121">文字列</span><span class="sxs-lookup"><span data-stu-id="0ec4d-121">string</span></span> | <span data-ttu-id="0ec4d-122">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="0ec4d-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="0ec4d-123">文字列</span><span class="sxs-lookup"><span data-stu-id="0ec4d-123">string</span></span> | <span data-ttu-id="0ec4d-124">記録されたアクションが適用されたファイルを含むフォルダー</span><span class="sxs-lookup"><span data-stu-id="0ec4d-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="0ec4d-125">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-125">string</span></span> | <span data-ttu-id="0ec4d-126">アクションの結果として名前が変更されたファイルの元の名前</span><span class="sxs-lookup"><span data-stu-id="0ec4d-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="0ec4d-127">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-127">string</span></span> | <span data-ttu-id="0ec4d-128">記録されたアクションが適用される前のファイルを含む元のフォルダー</span><span class="sxs-lookup"><span data-stu-id="0ec4d-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="0ec4d-129">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-129">string</span></span> | <span data-ttu-id="0ec4d-130">使用されるネットワーク プロトコル</span><span class="sxs-lookup"><span data-stu-id="0ec4d-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="0ec4d-131">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-131">string</span></span> | <span data-ttu-id="0ec4d-132">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="0ec4d-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="0ec4d-133">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-133">string</span></span> | <span data-ttu-id="0ec4d-134">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="0ec4d-134">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="0ec4d-135">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-135">string</span></span> | <span data-ttu-id="0ec4d-136">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="0ec4d-136">Security Identifier (SID) of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="0ec4d-137">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-137">string</span></span> | <span data-ttu-id="0ec4d-138">アカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="0ec4d-138">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="0ec4d-139">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-139">string</span></span> | <span data-ttu-id="0ec4d-140">Azure AD のアカウントの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="0ec4d-140">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="0ec4d-141">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-141">string</span></span> | <span data-ttu-id="0ec4d-142">アドレス帳に表示されるアカウント ユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="0ec4d-142">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="0ec4d-143">通常、名、ミドル ネーム、姓または姓の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="0ec4d-143">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="0ec4d-144">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-144">string</span></span> | <span data-ttu-id="0ec4d-145">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="0ec4d-145">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="0ec4d-146">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-146">string</span></span> | <span data-ttu-id="0ec4d-147">デバイスの種類</span><span class="sxs-lookup"><span data-stu-id="0ec4d-147">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="0ec4d-148">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-148">string</span></span> | <span data-ttu-id="0ec4d-149">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="0ec4d-149">Platform of the operating system running on the device.</span></span> <span data-ttu-id="0ec4d-150">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="0ec4d-150">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="0ec4d-151">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-151">string</span></span> | <span data-ttu-id="0ec4d-152">エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="0ec4d-152">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="0ec4d-153">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-153">string</span></span> | <span data-ttu-id="0ec4d-154">通信中に使用される TCP ポート</span><span class="sxs-lookup"><span data-stu-id="0ec4d-154">TCP port used during communication</span></span>  |
| `DestinationDeviceName` | <span data-ttu-id="0ec4d-155">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-155">string</span></span> | <span data-ttu-id="0ec4d-156">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの名前</span><span class="sxs-lookup"><span data-stu-id="0ec4d-156">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="0ec4d-157">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-157">string</span></span> | <span data-ttu-id="0ec4d-158">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="0ec4d-158">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="0ec4d-159">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-159">string</span></span> | <span data-ttu-id="0ec4d-160">関連するネットワーク通信の宛先ポート</span><span class="sxs-lookup"><span data-stu-id="0ec4d-160">Destination port of related network communications</span></span> |
| `Location` | <span data-ttu-id="0ec4d-161">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-161">string</span></span> | <span data-ttu-id="0ec4d-162">イベントに関連付けられている都市、国、その他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="0ec4d-162">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="0ec4d-163">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-163">string</span></span> | <span data-ttu-id="0ec4d-164">エンドポイント IP アドレスに関連付けられたインターネット サービス プロバイダー (ISP)</span><span class="sxs-lookup"><span data-stu-id="0ec4d-164">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="0ec4d-165">long</span><span class="sxs-lookup"><span data-stu-id="0ec4d-165">long</span></span> | <span data-ttu-id="0ec4d-166">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="0ec4d-166">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="0ec4d-167">string</span><span class="sxs-lookup"><span data-stu-id="0ec4d-167">string</span></span> | <span data-ttu-id="0ec4d-168">エンティティまたはイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="0ec4d-168">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0ec4d-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ec4d-169">Related topics</span></span>
- [<span data-ttu-id="0ec4d-170">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="0ec4d-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0ec4d-171">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="0ec4d-171">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0ec4d-172">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="0ec4d-172">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0ec4d-173">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="0ec4d-173">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0ec4d-174">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="0ec4d-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0ec4d-175">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="0ec4d-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
