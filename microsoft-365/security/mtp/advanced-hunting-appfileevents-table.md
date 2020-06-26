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
ms.openlocfilehash: da3b331d4f607aa0961e275db9444aadbec4fcf2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899341"
---
# <a name="appfileevents"></a><span data-ttu-id="fe42a-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="fe42a-104">AppFileEvents</span></span>

<span data-ttu-id="fe42a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fe42a-105">**Applies to:**</span></span>
- <span data-ttu-id="fe42a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fe42a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="fe42a-107">`AppFileEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、クラウドアプリと Microsoft cloud App Security によって監視されるサービスのファイル関連アクティビティに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe42a-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="fe42a-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe42a-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="fe42a-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe42a-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="fe42a-110">列名</span><span class="sxs-lookup"><span data-stu-id="fe42a-110">Column name</span></span> | <span data-ttu-id="fe42a-111">データ型</span><span class="sxs-lookup"><span data-stu-id="fe42a-111">Data type</span></span> | <span data-ttu-id="fe42a-112">説明</span><span class="sxs-lookup"><span data-stu-id="fe42a-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="fe42a-113">日付型</span><span class="sxs-lookup"><span data-stu-id="fe42a-113">datetime</span></span> | <span data-ttu-id="fe42a-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="fe42a-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="fe42a-115">string</span><span class="sxs-lookup"><span data-stu-id="fe42a-115">string</span></span> | <span data-ttu-id="fe42a-116">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="fe42a-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="fe42a-117">string</span><span class="sxs-lookup"><span data-stu-id="fe42a-117">string</span></span> | <span data-ttu-id="fe42a-118">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="fe42a-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="fe42a-119">文字列</span><span class="sxs-lookup"><span data-stu-id="fe42a-119">string</span></span> | <span data-ttu-id="fe42a-120">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="fe42a-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="fe42a-121">文字列</span><span class="sxs-lookup"><span data-stu-id="fe42a-121">string</span></span> | <span data-ttu-id="fe42a-122">記録されたアクションが適用されたファイルを含むフォルダ</span><span class="sxs-lookup"><span data-stu-id="fe42a-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="fe42a-123">string</span><span class="sxs-lookup"><span data-stu-id="fe42a-123">string</span></span> | <span data-ttu-id="fe42a-124">アクションの結果として名前が変更されたファイルの元の名前</span><span class="sxs-lookup"><span data-stu-id="fe42a-124">Original name of the file that was renamed as a result of the action</span></span> |
| `AccountName` | <span data-ttu-id="fe42a-125">string</span><span class="sxs-lookup"><span data-stu-id="fe42a-125">string</span></span> | <span data-ttu-id="fe42a-126">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="fe42a-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="fe42a-127">string</span><span class="sxs-lookup"><span data-stu-id="fe42a-127">string</span></span> | <span data-ttu-id="fe42a-128">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="fe42a-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="fe42a-129">string</span><span class="sxs-lookup"><span data-stu-id="fe42a-129">string</span></span> | <span data-ttu-id="fe42a-130">アカウントのユーザープリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="fe42a-130">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="fe42a-131">string</span><span class="sxs-lookup"><span data-stu-id="fe42a-131">string</span></span> | <span data-ttu-id="fe42a-132">Azure AD でのアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="fe42a-132">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="fe42a-133">string</span><span class="sxs-lookup"><span data-stu-id="fe42a-133">string</span></span> | <span data-ttu-id="fe42a-134">アドレス帳に表示されるアカウントユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="fe42a-134">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="fe42a-135">通常、指定された名前または名、ミドルネーム、姓の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="fe42a-135">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IPAddress` | <span data-ttu-id="fe42a-136">string</span><span class="sxs-lookup"><span data-stu-id="fe42a-136">string</span></span> | <span data-ttu-id="fe42a-137">エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="fe42a-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="fe42a-138">string</span><span class="sxs-lookup"><span data-stu-id="fe42a-138">string</span></span> | <span data-ttu-id="fe42a-139">イベントに関連付けられている市区町村、国、またはその他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="fe42a-139">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="fe42a-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe42a-140">Related topics</span></span>
- [<span data-ttu-id="fe42a-141">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="fe42a-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fe42a-142">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="fe42a-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fe42a-143">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="fe42a-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="fe42a-144">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="fe42a-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="fe42a-145">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="fe42a-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="fe42a-146">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="fe42a-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
