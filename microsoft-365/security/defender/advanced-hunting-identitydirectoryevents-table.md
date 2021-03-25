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
ms.openlocfilehash: ba63bdeb215c24e68d0e507d99e026c5b2695cb0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068324"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="ec394-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="ec394-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ec394-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ec394-105">**Applies to:**</span></span>
- <span data-ttu-id="ec394-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec394-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ec394-107">高度 `IdentityDirectoryEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、Active Directory を実行しているオンプレミスのドメイン コントローラー (AD) が含AD。</span><span class="sxs-lookup"><span data-stu-id="ec394-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="ec394-108">次の表は、パスワードの変更、パスワードの有効期限、ユーザー プリンシパル名 (UPN) の変更など、さまざまな ID 関連のイベントをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="ec394-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="ec394-109">また、タスクのスケジュール設定や PowerShell アクティビティなど、ドメイン コントローラー上のシステム イベントもキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="ec394-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="ec394-110">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="ec394-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="ec394-111">テーブルでサポートされるイベントの種類 (値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ参照 `ActionType` を使用します。</span><span class="sxs-lookup"><span data-stu-id="ec394-111">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="ec394-112">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec394-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ec394-113">列名</span><span class="sxs-lookup"><span data-stu-id="ec394-113">Column name</span></span> | <span data-ttu-id="ec394-114">データ型</span><span class="sxs-lookup"><span data-stu-id="ec394-114">Data type</span></span> | <span data-ttu-id="ec394-115">説明</span><span class="sxs-lookup"><span data-stu-id="ec394-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ec394-116">日付型</span><span class="sxs-lookup"><span data-stu-id="ec394-116">datetime</span></span> | <span data-ttu-id="ec394-117">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="ec394-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="ec394-118">string</span><span class="sxs-lookup"><span data-stu-id="ec394-118">string</span></span> | <span data-ttu-id="ec394-119">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="ec394-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="ec394-120">詳細については [、ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec394-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="ec394-121">string</span><span class="sxs-lookup"><span data-stu-id="ec394-121">string</span></span> | <span data-ttu-id="ec394-122">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="ec394-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="ec394-123">string</span><span class="sxs-lookup"><span data-stu-id="ec394-123">string</span></span> | <span data-ttu-id="ec394-124">記録されたアクションが適用されたアカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="ec394-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="ec394-125">string</span><span class="sxs-lookup"><span data-stu-id="ec394-125">string</span></span> | <span data-ttu-id="ec394-126">記録されたアクションが適用されたアカウントの表示名</span><span class="sxs-lookup"><span data-stu-id="ec394-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="ec394-127">string</span><span class="sxs-lookup"><span data-stu-id="ec394-127">string</span></span> | <span data-ttu-id="ec394-128">記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="ec394-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="ec394-129">string</span><span class="sxs-lookup"><span data-stu-id="ec394-129">string</span></span> | <span data-ttu-id="ec394-130">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの名前</span><span class="sxs-lookup"><span data-stu-id="ec394-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="ec394-131">string</span><span class="sxs-lookup"><span data-stu-id="ec394-131">string</span></span> | <span data-ttu-id="ec394-132">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="ec394-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="ec394-133">string</span><span class="sxs-lookup"><span data-stu-id="ec394-133">string</span></span> | <span data-ttu-id="ec394-134">アクティビティの宛先ポート</span><span class="sxs-lookup"><span data-stu-id="ec394-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="ec394-135">string</span><span class="sxs-lookup"><span data-stu-id="ec394-135">string</span></span> | <span data-ttu-id="ec394-136">通信中に使用されるプロトコル</span><span class="sxs-lookup"><span data-stu-id="ec394-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="ec394-137">string</span><span class="sxs-lookup"><span data-stu-id="ec394-137">string</span></span> | <span data-ttu-id="ec394-138">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="ec394-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="ec394-139">string</span><span class="sxs-lookup"><span data-stu-id="ec394-139">string</span></span> | <span data-ttu-id="ec394-140">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="ec394-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="ec394-141">string</span><span class="sxs-lookup"><span data-stu-id="ec394-141">string</span></span> | <span data-ttu-id="ec394-142">アカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="ec394-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="ec394-143">string</span><span class="sxs-lookup"><span data-stu-id="ec394-143">string</span></span> | <span data-ttu-id="ec394-144">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="ec394-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="ec394-145">string</span><span class="sxs-lookup"><span data-stu-id="ec394-145">string</span></span> | <span data-ttu-id="ec394-146">Azure Active Directory のアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="ec394-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="ec394-147">string</span><span class="sxs-lookup"><span data-stu-id="ec394-147">string</span></span> | <span data-ttu-id="ec394-148">アドレス帳に表示されるアカウント ユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="ec394-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="ec394-149">通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="ec394-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="ec394-150">string</span><span class="sxs-lookup"><span data-stu-id="ec394-150">string</span></span> | <span data-ttu-id="ec394-151">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="ec394-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="ec394-152">string</span><span class="sxs-lookup"><span data-stu-id="ec394-152">string</span></span> | <span data-ttu-id="ec394-153">通信中にデバイスに割り当てられた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="ec394-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="ec394-154">string</span><span class="sxs-lookup"><span data-stu-id="ec394-154">string</span></span> | <span data-ttu-id="ec394-155">通信中に使用される TCP ポート</span><span class="sxs-lookup"><span data-stu-id="ec394-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="ec394-156">string</span><span class="sxs-lookup"><span data-stu-id="ec394-156">string</span></span> | <span data-ttu-id="ec394-157">イベントに関連付けられている都市、国、その他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="ec394-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="ec394-158">string</span><span class="sxs-lookup"><span data-stu-id="ec394-158">string</span></span> | <span data-ttu-id="ec394-159">IP アドレスに関連付けられたインターネット サービス プロバイダー</span><span class="sxs-lookup"><span data-stu-id="ec394-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="ec394-160">long</span><span class="sxs-lookup"><span data-stu-id="ec394-160">long</span></span> | <span data-ttu-id="ec394-161">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="ec394-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="ec394-162">string</span><span class="sxs-lookup"><span data-stu-id="ec394-162">string</span></span> | <span data-ttu-id="ec394-163">エンティティまたはイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="ec394-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ec394-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec394-164">Related topics</span></span>
- [<span data-ttu-id="ec394-165">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="ec394-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ec394-166">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="ec394-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ec394-167">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="ec394-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ec394-168">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="ec394-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ec394-169">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="ec394-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ec394-170">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="ec394-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
