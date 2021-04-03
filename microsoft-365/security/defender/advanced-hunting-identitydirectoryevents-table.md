---
title: 高度なハンティング スキーマの IdentityDirectoryEvents テーブル
description: 高度なハンティング スキーマの IdentityDirectoryEvents テーブルのドメイン コントローラーイベントと Active Directory イベントについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、IdentityDirectoryEvents、ドメイン コントローラー、Active Directory、Azure ATP、ID
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 73018bb65c011d10234ec9c02fc61bfb93fa125a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501125"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="9234a-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="9234a-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9234a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9234a-105">**Applies to:**</span></span>
- <span data-ttu-id="9234a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9234a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9234a-107">高度 `IdentityDirectoryEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、Active Directory を実行しているオンプレミスのドメイン コントローラー (AD) が含AD。</span><span class="sxs-lookup"><span data-stu-id="9234a-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="9234a-108">次の表は、パスワードの変更、パスワードの有効期限、ユーザー プリンシパル名 (UPN) の変更など、さまざまな ID 関連のイベントをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="9234a-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="9234a-109">また、タスクのスケジュール設定や PowerShell アクティビティなど、ドメイン コントローラー上のシステム イベントもキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="9234a-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="9234a-110">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="9234a-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="9234a-111">テーブルでサポートされるイベントの種類 (値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ参照 `ActionType` を使用します。</span><span class="sxs-lookup"><span data-stu-id="9234a-111">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="9234a-112">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9234a-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9234a-113">列名</span><span class="sxs-lookup"><span data-stu-id="9234a-113">Column name</span></span> | <span data-ttu-id="9234a-114">データ型</span><span class="sxs-lookup"><span data-stu-id="9234a-114">Data type</span></span> | <span data-ttu-id="9234a-115">説明</span><span class="sxs-lookup"><span data-stu-id="9234a-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9234a-116">日付型</span><span class="sxs-lookup"><span data-stu-id="9234a-116">datetime</span></span> | <span data-ttu-id="9234a-117">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="9234a-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="9234a-118">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-118">string</span></span> | <span data-ttu-id="9234a-119">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="9234a-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="9234a-120">詳細については [、ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9234a-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="9234a-121">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-121">string</span></span> | <span data-ttu-id="9234a-122">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="9234a-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="9234a-123">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-123">string</span></span> | <span data-ttu-id="9234a-124">記録されたアクションが適用されたアカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="9234a-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="9234a-125">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-125">string</span></span> | <span data-ttu-id="9234a-126">記録されたアクションが適用されたアカウントの表示名</span><span class="sxs-lookup"><span data-stu-id="9234a-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="9234a-127">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-127">string</span></span> | <span data-ttu-id="9234a-128">記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="9234a-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="9234a-129">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-129">string</span></span> | <span data-ttu-id="9234a-130">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの名前</span><span class="sxs-lookup"><span data-stu-id="9234a-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="9234a-131">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-131">string</span></span> | <span data-ttu-id="9234a-132">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="9234a-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="9234a-133">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-133">string</span></span> | <span data-ttu-id="9234a-134">アクティビティの宛先ポート</span><span class="sxs-lookup"><span data-stu-id="9234a-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="9234a-135">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-135">string</span></span> | <span data-ttu-id="9234a-136">通信中に使用されるプロトコル</span><span class="sxs-lookup"><span data-stu-id="9234a-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="9234a-137">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-137">string</span></span> | <span data-ttu-id="9234a-138">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="9234a-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="9234a-139">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-139">string</span></span> | <span data-ttu-id="9234a-140">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="9234a-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="9234a-141">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-141">string</span></span> | <span data-ttu-id="9234a-142">アカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="9234a-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="9234a-143">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-143">string</span></span> | <span data-ttu-id="9234a-144">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="9234a-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="9234a-145">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-145">string</span></span> | <span data-ttu-id="9234a-146">Azure Active Directory のアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="9234a-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="9234a-147">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-147">string</span></span> | <span data-ttu-id="9234a-148">アドレス帳に表示されるアカウント ユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="9234a-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="9234a-149">通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="9234a-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="9234a-150">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-150">string</span></span> | <span data-ttu-id="9234a-151">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="9234a-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="9234a-152">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-152">string</span></span> | <span data-ttu-id="9234a-153">通信中にデバイスに割り当てられた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="9234a-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="9234a-154">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-154">string</span></span> | <span data-ttu-id="9234a-155">通信中に使用される TCP ポート</span><span class="sxs-lookup"><span data-stu-id="9234a-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="9234a-156">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-156">string</span></span> | <span data-ttu-id="9234a-157">イベントに関連付けられている都市、国、その他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="9234a-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="9234a-158">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-158">string</span></span> | <span data-ttu-id="9234a-159">IP アドレスに関連付けられたインターネット サービス プロバイダー</span><span class="sxs-lookup"><span data-stu-id="9234a-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="9234a-160">long</span><span class="sxs-lookup"><span data-stu-id="9234a-160">long</span></span> | <span data-ttu-id="9234a-161">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="9234a-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="9234a-162">文字列</span><span class="sxs-lookup"><span data-stu-id="9234a-162">string</span></span> | <span data-ttu-id="9234a-163">エンティティまたはイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="9234a-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9234a-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="9234a-164">Related topics</span></span>
- [<span data-ttu-id="9234a-165">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="9234a-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9234a-166">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="9234a-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9234a-167">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="9234a-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9234a-168">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="9234a-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9234a-169">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="9234a-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9234a-170">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="9234a-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
