---
title: 高度な検索スキーマの [イベント] テーブル
description: 高度な検索スキーマのイベントテーブルのドメインコントローライベントと Active Directory イベントについて説明します。
keywords: 高度な検索、脅威の調査、サイバー脅威の調査、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、identity Directoryevents、domain controller、Active Directory、Azure ATP、id
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
ms.openlocfilehash: 4a698bc0d6a7c1ebadec44357b932e9b56dc0a3c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196847"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="a18a5-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="a18a5-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a18a5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a18a5-105">**Applies to:**</span></span>
- <span data-ttu-id="a18a5-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a18a5-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="a18a5-107">`IdentityDirectoryEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表に、ACTIVE Directory (AD) を実行しているオンプレミスのドメインコントローラーに関連するイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a18a5-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="a18a5-108">このテーブルは、パスワードの変更、パスワードの有効期限、ユーザープリンシパル名 (UPN) の変更など、さまざまな id 関連イベントをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="a18a5-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="a18a5-109">また、タスクのスケジューリングや PowerShell アクティビティなど、ドメインコントローラーのシステムイベントもキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="a18a5-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="a18a5-110">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a18a5-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="a18a5-111">テーブルでサポートされているイベントの種類 (値) の詳細については、 `ActionType` セキュリティセンターで利用可能な [組み込みスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a18a5-111">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="a18a5-112">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a18a5-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a18a5-113">列名</span><span class="sxs-lookup"><span data-stu-id="a18a5-113">Column name</span></span> | <span data-ttu-id="a18a5-114">データ型</span><span class="sxs-lookup"><span data-stu-id="a18a5-114">Data type</span></span> | <span data-ttu-id="a18a5-115">説明</span><span class="sxs-lookup"><span data-stu-id="a18a5-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a18a5-116">日付型</span><span class="sxs-lookup"><span data-stu-id="a18a5-116">datetime</span></span> | <span data-ttu-id="a18a5-117">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="a18a5-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="a18a5-118">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-118">string</span></span> | <span data-ttu-id="a18a5-119">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="a18a5-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="a18a5-120">詳細については、 [ポータル内のスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a18a5-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="a18a5-121">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-121">string</span></span> | <span data-ttu-id="a18a5-122">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="a18a5-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="a18a5-123">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-123">string</span></span> | <span data-ttu-id="a18a5-124">記録されたアクションが適用されたアカウントのユーザープリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="a18a5-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="a18a5-125">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-125">string</span></span> | <span data-ttu-id="a18a5-126">記録済みのアクションが適用されたアカウントの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="a18a5-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="a18a5-127">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-127">string</span></span> | <span data-ttu-id="a18a5-128">記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="a18a5-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="a18a5-129">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-129">string</span></span> | <span data-ttu-id="a18a5-130">記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの名前</span><span class="sxs-lookup"><span data-stu-id="a18a5-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="a18a5-131">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-131">string</span></span> | <span data-ttu-id="a18a5-132">記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a18a5-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="a18a5-133">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-133">string</span></span> | <span data-ttu-id="a18a5-134">アクティビティの宛先ポート</span><span class="sxs-lookup"><span data-stu-id="a18a5-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="a18a5-135">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-135">string</span></span> | <span data-ttu-id="a18a5-136">通信中に使用されるプロトコル</span><span class="sxs-lookup"><span data-stu-id="a18a5-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="a18a5-137">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-137">string</span></span> | <span data-ttu-id="a18a5-138">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="a18a5-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="a18a5-139">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-139">string</span></span> | <span data-ttu-id="a18a5-140">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="a18a5-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="a18a5-141">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-141">string</span></span> | <span data-ttu-id="a18a5-142">アカウントのユーザープリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="a18a5-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="a18a5-143">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-143">string</span></span> | <span data-ttu-id="a18a5-144">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="a18a5-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="a18a5-145">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-145">string</span></span> | <span data-ttu-id="a18a5-146">Azure AD でのアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="a18a5-146">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="a18a5-147">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-147">string</span></span> | <span data-ttu-id="a18a5-148">アドレス帳に表示されるアカウントユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="a18a5-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="a18a5-149">通常、指定された名前または名、ミドルネーム、姓の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="a18a5-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="a18a5-150">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-150">string</span></span> | <span data-ttu-id="a18a5-151">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="a18a5-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="a18a5-152">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-152">string</span></span> | <span data-ttu-id="a18a5-153">通信中にデバイスに割り当てられた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a18a5-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="a18a5-154">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-154">string</span></span> | <span data-ttu-id="a18a5-155">通信中に使用される TCP ポート</span><span class="sxs-lookup"><span data-stu-id="a18a5-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="a18a5-156">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-156">string</span></span> | <span data-ttu-id="a18a5-157">イベントに関連付けられている市区町村、国、またはその他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="a18a5-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="a18a5-158">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-158">string</span></span> | <span data-ttu-id="a18a5-159">IP アドレスに関連付けられているインターネットサービスプロバイダー</span><span class="sxs-lookup"><span data-stu-id="a18a5-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="a18a5-160">long</span><span class="sxs-lookup"><span data-stu-id="a18a5-160">long</span></span> | <span data-ttu-id="a18a5-161">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="a18a5-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="a18a5-162">文字列</span><span class="sxs-lookup"><span data-stu-id="a18a5-162">string</span></span> | <span data-ttu-id="a18a5-163">エンティティまたはイベントに関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="a18a5-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a18a5-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="a18a5-164">Related topics</span></span>
- [<span data-ttu-id="a18a5-165">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="a18a5-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a18a5-166">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="a18a5-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a18a5-167">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="a18a5-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a18a5-168">デバイス、メール、アプリ、ID 間での捜索</span><span class="sxs-lookup"><span data-stu-id="a18a5-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a18a5-169">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="a18a5-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a18a5-170">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="a18a5-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
