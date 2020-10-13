---
title: 高度な検索スキーマの AppFileEvents テーブル
description: 高度な検索スキーマの AppFileEvents テーブルでクラウドアプリおよびサービスに関連付けられているファイル関連イベントについて説明します。
keywords: 高度な検索、脅威の探し、サイバーの脅威の検出、microsoft の脅威の防止、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、AppFileEvents、Cloud App Security、MCAS
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
ms.openlocfilehash: 5cab6e3fe7a3b4b74989dde360c03d58e0bad46f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430153"
---
# <a name="appfileevents"></a><span data-ttu-id="8b460-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="8b460-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8b460-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8b460-105">**Applies to:**</span></span>
- <span data-ttu-id="8b460-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8b460-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="8b460-107">`AppFileEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、クラウドアプリと Microsoft cloud App Security によって監視されるサービスのファイル関連アクティビティに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8b460-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="8b460-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b460-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="8b460-109">テーブルでサポートされているイベントの種類 (値) の詳細については、 `ActionType` セキュリティセンターで利用可能な [組み込みスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="8b460-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="8b460-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b460-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8b460-111">列名</span><span class="sxs-lookup"><span data-stu-id="8b460-111">Column name</span></span> | <span data-ttu-id="8b460-112">データ型</span><span class="sxs-lookup"><span data-stu-id="8b460-112">Data type</span></span> | <span data-ttu-id="8b460-113">説明</span><span class="sxs-lookup"><span data-stu-id="8b460-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="8b460-114">日付型</span><span class="sxs-lookup"><span data-stu-id="8b460-114">datetime</span></span> | <span data-ttu-id="8b460-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="8b460-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="8b460-116">string</span><span class="sxs-lookup"><span data-stu-id="8b460-116">string</span></span> | <span data-ttu-id="8b460-117">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="8b460-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="8b460-118">詳細については、 [ポータル内のスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b460-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="8b460-119">string</span><span class="sxs-lookup"><span data-stu-id="8b460-119">string</span></span> | <span data-ttu-id="8b460-120">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="8b460-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="8b460-121">文字列</span><span class="sxs-lookup"><span data-stu-id="8b460-121">string</span></span> | <span data-ttu-id="8b460-122">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="8b460-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="8b460-123">文字列</span><span class="sxs-lookup"><span data-stu-id="8b460-123">string</span></span> | <span data-ttu-id="8b460-124">記録されたアクションが適用されたファイルを含むフォルダ</span><span class="sxs-lookup"><span data-stu-id="8b460-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="8b460-125">string</span><span class="sxs-lookup"><span data-stu-id="8b460-125">string</span></span> | <span data-ttu-id="8b460-126">アクションの結果として名前が変更されたファイルの元の名前</span><span class="sxs-lookup"><span data-stu-id="8b460-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="8b460-127">string</span><span class="sxs-lookup"><span data-stu-id="8b460-127">string</span></span> | <span data-ttu-id="8b460-128">記録されたアクションが適用される前のファイルが含まれている元のフォルダー</span><span class="sxs-lookup"><span data-stu-id="8b460-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="8b460-129">string</span><span class="sxs-lookup"><span data-stu-id="8b460-129">string</span></span> | <span data-ttu-id="8b460-130">使用されるネットワークプロトコル</span><span class="sxs-lookup"><span data-stu-id="8b460-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="8b460-131">string</span><span class="sxs-lookup"><span data-stu-id="8b460-131">string</span></span> | <span data-ttu-id="8b460-132">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="8b460-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="8b460-133">string</span><span class="sxs-lookup"><span data-stu-id="8b460-133">string</span></span> | <span data-ttu-id="8b460-134">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="8b460-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="8b460-135">string</span><span class="sxs-lookup"><span data-stu-id="8b460-135">string</span></span> | <span data-ttu-id="8b460-136">アカウントのユーザープリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="8b460-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="8b460-137">string</span><span class="sxs-lookup"><span data-stu-id="8b460-137">string</span></span> | <span data-ttu-id="8b460-138">Azure AD でのアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="8b460-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="8b460-139">string</span><span class="sxs-lookup"><span data-stu-id="8b460-139">string</span></span> | <span data-ttu-id="8b460-140">アドレス帳に表示されるアカウントユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="8b460-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="8b460-141">通常、指定された名前または名、ミドルネーム、姓の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="8b460-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="8b460-142">string</span><span class="sxs-lookup"><span data-stu-id="8b460-142">string</span></span> | <span data-ttu-id="8b460-143">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="8b460-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="8b460-144">string</span><span class="sxs-lookup"><span data-stu-id="8b460-144">string</span></span> | <span data-ttu-id="8b460-145">デバイスの種類</span><span class="sxs-lookup"><span data-stu-id="8b460-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="8b460-146">string</span><span class="sxs-lookup"><span data-stu-id="8b460-146">string</span></span> | <span data-ttu-id="8b460-147">デバイス上で実行されているオペレーティングシステムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="8b460-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="8b460-148">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="8b460-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="8b460-149">string</span><span class="sxs-lookup"><span data-stu-id="8b460-149">string</span></span> | <span data-ttu-id="8b460-150">エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="8b460-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="8b460-151">string</span><span class="sxs-lookup"><span data-stu-id="8b460-151">string</span></span> | <span data-ttu-id="8b460-152">記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの名前</span><span class="sxs-lookup"><span data-stu-id="8b460-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="8b460-153">string</span><span class="sxs-lookup"><span data-stu-id="8b460-153">string</span></span> | <span data-ttu-id="8b460-154">記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="8b460-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="8b460-155">string</span><span class="sxs-lookup"><span data-stu-id="8b460-155">string</span></span> | <span data-ttu-id="8b460-156">イベントに関連付けられている市区町村、国、またはその他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="8b460-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="8b460-157">string</span><span class="sxs-lookup"><span data-stu-id="8b460-157">string</span></span> | <span data-ttu-id="8b460-158">エンドポイントの IP アドレスに関連付けられているインターネットサービスプロバイダー (ISP)</span><span class="sxs-lookup"><span data-stu-id="8b460-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="8b460-159">long</span><span class="sxs-lookup"><span data-stu-id="8b460-159">long</span></span> | <span data-ttu-id="8b460-160">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="8b460-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="8b460-161">string</span><span class="sxs-lookup"><span data-stu-id="8b460-161">string</span></span> | <span data-ttu-id="8b460-162">エンティティまたはイベントに関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="8b460-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8b460-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b460-163">Related topics</span></span>
- [<span data-ttu-id="8b460-164">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="8b460-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8b460-165">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="8b460-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8b460-166">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="8b460-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8b460-167">デバイス、メール、アプリ、ID 間での捜索</span><span class="sxs-lookup"><span data-stu-id="8b460-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8b460-168">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="8b460-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8b460-169">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="8b460-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
