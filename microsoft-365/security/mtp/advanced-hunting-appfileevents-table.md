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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 663dc2a3de676fa2daeab3d9621254e956d42fc4
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204757"
---
# <a name="appfileevents"></a><span data-ttu-id="f9a04-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="f9a04-104">AppFileEvents</span></span>

<span data-ttu-id="f9a04-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f9a04-105">**Applies to:**</span></span>
- <span data-ttu-id="f9a04-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f9a04-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="f9a04-107">`AppFileEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、クラウドアプリと Microsoft cloud App Security によって監視されるサービスのファイル関連アクティビティに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9a04-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="f9a04-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9a04-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="f9a04-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9a04-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f9a04-110">列名</span><span class="sxs-lookup"><span data-stu-id="f9a04-110">Column name</span></span> | <span data-ttu-id="f9a04-111">データ型</span><span class="sxs-lookup"><span data-stu-id="f9a04-111">Data type</span></span> | <span data-ttu-id="f9a04-112">説明</span><span class="sxs-lookup"><span data-stu-id="f9a04-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f9a04-113">日付型</span><span class="sxs-lookup"><span data-stu-id="f9a04-113">datetime</span></span> | <span data-ttu-id="f9a04-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="f9a04-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="f9a04-115">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-115">string</span></span> | <span data-ttu-id="f9a04-116">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="f9a04-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="f9a04-117">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-117">string</span></span> | <span data-ttu-id="f9a04-118">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="f9a04-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="f9a04-119">文字列</span><span class="sxs-lookup"><span data-stu-id="f9a04-119">string</span></span> | <span data-ttu-id="f9a04-120">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="f9a04-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="f9a04-121">文字列</span><span class="sxs-lookup"><span data-stu-id="f9a04-121">string</span></span> | <span data-ttu-id="f9a04-122">記録されたアクションが適用されたファイルを含むフォルダ</span><span class="sxs-lookup"><span data-stu-id="f9a04-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="f9a04-123">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-123">string</span></span> | <span data-ttu-id="f9a04-124">アクションの結果として名前が変更されたファイルの元の名前</span><span class="sxs-lookup"><span data-stu-id="f9a04-124">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="f9a04-125">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-125">string</span></span> | <span data-ttu-id="f9a04-126">記録されたアクションが適用される前のファイルが含まれている元のフォルダー</span><span class="sxs-lookup"><span data-stu-id="f9a04-126">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="f9a04-127">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-127">string</span></span> | <span data-ttu-id="f9a04-128">使用されるネットワークプロトコル</span><span class="sxs-lookup"><span data-stu-id="f9a04-128">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="f9a04-129">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-129">string</span></span> | <span data-ttu-id="f9a04-130">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="f9a04-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="f9a04-131">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-131">string</span></span> | <span data-ttu-id="f9a04-132">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="f9a04-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="f9a04-133">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-133">string</span></span> | <span data-ttu-id="f9a04-134">アカウントのユーザープリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="f9a04-134">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="f9a04-135">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-135">string</span></span> | <span data-ttu-id="f9a04-136">Azure AD でのアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="f9a04-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="f9a04-137">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-137">string</span></span> | <span data-ttu-id="f9a04-138">アドレス帳に表示されるアカウントユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="f9a04-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="f9a04-139">通常、指定された名前または名、ミドルネーム、姓の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="f9a04-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="f9a04-140">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-140">string</span></span> | <span data-ttu-id="f9a04-141">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="f9a04-141">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="f9a04-142">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-142">string</span></span> | <span data-ttu-id="f9a04-143">デバイスの種類</span><span class="sxs-lookup"><span data-stu-id="f9a04-143">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="f9a04-144">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-144">string</span></span> | <span data-ttu-id="f9a04-145">デバイス上で実行されているオペレーティングシステムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="f9a04-145">Platform of the operating system running on the device.</span></span> <span data-ttu-id="f9a04-146">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="f9a04-146">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="f9a04-147">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-147">string</span></span> | <span data-ttu-id="f9a04-148">エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f9a04-148">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="f9a04-149">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-149">string</span></span> | <span data-ttu-id="f9a04-150">記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの名前</span><span class="sxs-lookup"><span data-stu-id="f9a04-150">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="f9a04-151">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-151">string</span></span> | <span data-ttu-id="f9a04-152">記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f9a04-152">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="f9a04-153">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-153">string</span></span> | <span data-ttu-id="f9a04-154">イベントに関連付けられている市区町村、国、またはその他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="f9a04-154">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="f9a04-155">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-155">string</span></span> | <span data-ttu-id="f9a04-156">エンドポイントの IP アドレスに関連付けられているインターネットサービスプロバイダー (ISP)</span><span class="sxs-lookup"><span data-stu-id="f9a04-156">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="f9a04-157">long</span><span class="sxs-lookup"><span data-stu-id="f9a04-157">long</span></span> | <span data-ttu-id="f9a04-158">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="f9a04-158">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="f9a04-159">string</span><span class="sxs-lookup"><span data-stu-id="f9a04-159">string</span></span> | <span data-ttu-id="f9a04-160">エンティティまたはイベントに関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="f9a04-160">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f9a04-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9a04-161">Related topics</span></span>
- [<span data-ttu-id="f9a04-162">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="f9a04-162">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f9a04-163">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="f9a04-163">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f9a04-164">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="f9a04-164">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f9a04-165">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="f9a04-165">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f9a04-166">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="f9a04-166">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f9a04-167">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="f9a04-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
