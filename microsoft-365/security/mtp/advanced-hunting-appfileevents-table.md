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
ms.openlocfilehash: 385011382d20919b219cf84e13cda4993826691b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197063"
---
# <a name="appfileevents"></a><span data-ttu-id="6c455-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="6c455-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6c455-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6c455-105">**Applies to:**</span></span>
- <span data-ttu-id="6c455-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6c455-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="6c455-107">`AppFileEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、クラウドアプリと Microsoft cloud App Security によって監視されるサービスのファイル関連アクティビティに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6c455-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="6c455-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c455-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="6c455-109">テーブルでサポートされているイベントの種類 (値) の詳細については、 `ActionType` セキュリティセンターで利用可能な [組み込みスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="6c455-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="6c455-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c455-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6c455-111">列名</span><span class="sxs-lookup"><span data-stu-id="6c455-111">Column name</span></span> | <span data-ttu-id="6c455-112">データ型</span><span class="sxs-lookup"><span data-stu-id="6c455-112">Data type</span></span> | <span data-ttu-id="6c455-113">説明</span><span class="sxs-lookup"><span data-stu-id="6c455-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6c455-114">日付型</span><span class="sxs-lookup"><span data-stu-id="6c455-114">datetime</span></span> | <span data-ttu-id="6c455-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="6c455-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="6c455-116">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-116">string</span></span> | <span data-ttu-id="6c455-117">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="6c455-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="6c455-118">詳細については、 [ポータル内のスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c455-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="6c455-119">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-119">string</span></span> | <span data-ttu-id="6c455-120">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="6c455-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="6c455-121">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-121">string</span></span> | <span data-ttu-id="6c455-122">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="6c455-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="6c455-123">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-123">string</span></span> | <span data-ttu-id="6c455-124">記録されたアクションが適用されたファイルを含むフォルダ</span><span class="sxs-lookup"><span data-stu-id="6c455-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="6c455-125">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-125">string</span></span> | <span data-ttu-id="6c455-126">アクションの結果として名前が変更されたファイルの元の名前</span><span class="sxs-lookup"><span data-stu-id="6c455-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="6c455-127">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-127">string</span></span> | <span data-ttu-id="6c455-128">記録されたアクションが適用される前のファイルが含まれている元のフォルダー</span><span class="sxs-lookup"><span data-stu-id="6c455-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="6c455-129">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-129">string</span></span> | <span data-ttu-id="6c455-130">使用されるネットワークプロトコル</span><span class="sxs-lookup"><span data-stu-id="6c455-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="6c455-131">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-131">string</span></span> | <span data-ttu-id="6c455-132">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="6c455-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="6c455-133">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-133">string</span></span> | <span data-ttu-id="6c455-134">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="6c455-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="6c455-135">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-135">string</span></span> | <span data-ttu-id="6c455-136">アカウントのユーザープリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="6c455-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="6c455-137">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-137">string</span></span> | <span data-ttu-id="6c455-138">Azure AD でのアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="6c455-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="6c455-139">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-139">string</span></span> | <span data-ttu-id="6c455-140">アドレス帳に表示されるアカウントユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="6c455-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="6c455-141">通常、指定された名前または名、ミドルネーム、姓の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="6c455-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="6c455-142">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-142">string</span></span> | <span data-ttu-id="6c455-143">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="6c455-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="6c455-144">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-144">string</span></span> | <span data-ttu-id="6c455-145">デバイスの種類</span><span class="sxs-lookup"><span data-stu-id="6c455-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="6c455-146">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-146">string</span></span> | <span data-ttu-id="6c455-147">デバイス上で実行されているオペレーティングシステムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="6c455-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="6c455-148">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="6c455-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="6c455-149">string</span><span class="sxs-lookup"><span data-stu-id="6c455-149">string</span></span> | <span data-ttu-id="6c455-150">エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="6c455-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="6c455-151">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-151">string</span></span> | <span data-ttu-id="6c455-152">記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの名前</span><span class="sxs-lookup"><span data-stu-id="6c455-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="6c455-153">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-153">string</span></span> | <span data-ttu-id="6c455-154">記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="6c455-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="6c455-155">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-155">string</span></span> | <span data-ttu-id="6c455-156">イベントに関連付けられている市区町村、国、またはその他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="6c455-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="6c455-157">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-157">string</span></span> | <span data-ttu-id="6c455-158">エンドポイントの IP アドレスに関連付けられているインターネットサービスプロバイダー (ISP)</span><span class="sxs-lookup"><span data-stu-id="6c455-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="6c455-159">long</span><span class="sxs-lookup"><span data-stu-id="6c455-159">long</span></span> | <span data-ttu-id="6c455-160">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="6c455-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="6c455-161">文字列</span><span class="sxs-lookup"><span data-stu-id="6c455-161">string</span></span> | <span data-ttu-id="6c455-162">エンティティまたはイベントに関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="6c455-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6c455-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c455-163">Related topics</span></span>
- [<span data-ttu-id="6c455-164">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="6c455-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6c455-165">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="6c455-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6c455-166">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="6c455-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6c455-167">デバイス、メール、アプリ、ID 間での捜索</span><span class="sxs-lookup"><span data-stu-id="6c455-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6c455-168">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="6c455-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6c455-169">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="6c455-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
