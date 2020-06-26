---
title: 高度な検索スキーマの [イベント] テーブル
description: 高度な検索スキーマのイベントテーブルの Active Directory によって記録された認証イベントについて説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、identity Logonevents、Azure AD、Active Directory、Azure ATP、id
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
ms.openlocfilehash: 17e12e9095219b7ad7923f7b5664946fff6ce724
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899377"
---
# <a name="identitylogonevents"></a><span data-ttu-id="b46f5-104">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="b46f5-104">IdentityLogonEvents</span></span>

<span data-ttu-id="b46f5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b46f5-105">**Applies to:**</span></span>
- <span data-ttu-id="b46f5-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b46f5-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b46f5-107">`IdentityLogonEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、Azure Active Directory とその他の Microsoft クラウドアプリおよびサービスによって記録された認証アクティビティに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b46f5-107">The `IdentityLogonEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about authentication activities recorded by Azure Active Directory and other Microsoft cloud apps and services.</span></span> <span data-ttu-id="b46f5-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="b46f5-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="b46f5-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b46f5-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b46f5-110">列名</span><span class="sxs-lookup"><span data-stu-id="b46f5-110">Column name</span></span> | <span data-ttu-id="b46f5-111">データ型</span><span class="sxs-lookup"><span data-stu-id="b46f5-111">Data type</span></span> | <span data-ttu-id="b46f5-112">説明</span><span class="sxs-lookup"><span data-stu-id="b46f5-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b46f5-113">日付型</span><span class="sxs-lookup"><span data-stu-id="b46f5-113">datetime</span></span> | <span data-ttu-id="b46f5-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="b46f5-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="b46f5-115">文字列</span><span class="sxs-lookup"><span data-stu-id="b46f5-115">string</span></span> | <span data-ttu-id="b46f5-116">イベントをトリガーしたアクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="b46f5-116">Type of activity that triggered the event</span></span> |
| `LogonType` | <span data-ttu-id="b46f5-117">string</span><span class="sxs-lookup"><span data-stu-id="b46f5-117">string</span></span> | <span data-ttu-id="b46f5-118">ログオンセッションの種類。具体的には次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b46f5-118">Type of logon session, specifically:</span></span><br><br> <span data-ttu-id="b46f5-119">- **Interactive** -ユーザーがローカルのキーボードと画面を使用してコンピューターと物理的に対話する</span><span class="sxs-lookup"><span data-stu-id="b46f5-119">- **Interactive** - User physically interacts with the machine using the local keyboard and screen</span></span><br><br> <span data-ttu-id="b46f5-120">- **リモート対話 (RDP) ログオン**-ユーザーがリモートデスクトップ、ターミナルサービス、リモートアシスタンス、またはその他の RDP クライアントを使用してリモートでコンピューターと対話する</span><span class="sxs-lookup"><span data-stu-id="b46f5-120">- **Remote interactive (RDP) logons** - User interacts with the machine remotely using Remote Desktop, Terminal Services, Remote Assistance, or other RDP clients</span></span><br><br> <span data-ttu-id="b46f5-121">- PsExec を使用してコンピューターにアクセスするとき、またはプリンターや共有フォルダーなどのコンピューター上の共有リソースにアクセスするときに、**ネットワーク**セッションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="b46f5-121">- **Network** - Session initiated when the machine is accessed using PsExec or when shared resources on the machine, such as printers and shared folders, are accessed</span></span><br><br> <span data-ttu-id="b46f5-122">- スケジュールされたタスクによって開始された**バッチ**セッション</span><span class="sxs-lookup"><span data-stu-id="b46f5-122">- **Batch** - Session initiated by scheduled tasks</span></span><br><br> <span data-ttu-id="b46f5-123">- **サービス**-開始時にサービスによって開始されたセッション</span><span class="sxs-lookup"><span data-stu-id="b46f5-123">- **Service** - Session initiated by services as they start</span></span> |
| `Application` | <span data-ttu-id="b46f5-124">string</span><span class="sxs-lookup"><span data-stu-id="b46f5-124">string</span></span> | <span data-ttu-id="b46f5-125">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="b46f5-125">Application that performed the recorded action</span></span> |
| `Protocol` | <span data-ttu-id="b46f5-126">string</span><span class="sxs-lookup"><span data-stu-id="b46f5-126">string</span></span> | <span data-ttu-id="b46f5-127">通信中に使用されるプロトコル</span><span class="sxs-lookup"><span data-stu-id="b46f5-127">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="b46f5-128">string</span><span class="sxs-lookup"><span data-stu-id="b46f5-128">string</span></span> | <span data-ttu-id="b46f5-129">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="b46f5-129">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="b46f5-130">string</span><span class="sxs-lookup"><span data-stu-id="b46f5-130">string</span></span> | <span data-ttu-id="b46f5-131">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="b46f5-131">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="b46f5-132">string</span><span class="sxs-lookup"><span data-stu-id="b46f5-132">string</span></span> | <span data-ttu-id="b46f5-133">アカウントのユーザープリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="b46f5-133">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="b46f5-134">string</span><span class="sxs-lookup"><span data-stu-id="b46f5-134">string</span></span> | <span data-ttu-id="b46f5-135">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="b46f5-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="b46f5-136">string</span><span class="sxs-lookup"><span data-stu-id="b46f5-136">string</span></span> | <span data-ttu-id="b46f5-137">Azure AD でのアカウントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="b46f5-137">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="b46f5-138">string</span><span class="sxs-lookup"><span data-stu-id="b46f5-138">string</span></span> | <span data-ttu-id="b46f5-139">アドレス帳に表示されるアカウントユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="b46f5-139">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="b46f5-140">通常、指定された名前または名、ミドルネーム、姓の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="b46f5-140">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="b46f5-141">string</span><span class="sxs-lookup"><span data-stu-id="b46f5-141">string</span></span> | <span data-ttu-id="b46f5-142">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="b46f5-142">Fully qualified domain name (FQDN) of the machine</span></span> |
| `DeviceType` | <span data-ttu-id="b46f5-143">string</span><span class="sxs-lookup"><span data-stu-id="b46f5-143">string</span></span> | <span data-ttu-id="b46f5-144">デバイスの種類</span><span class="sxs-lookup"><span data-stu-id="b46f5-144">Type of device</span></span> |
| `OSPlatform` | <span data-ttu-id="b46f5-145">string</span><span class="sxs-lookup"><span data-stu-id="b46f5-145">string</span></span> | <span data-ttu-id="b46f5-146">コンピューターで実行されているオペレーティング システムのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="b46f5-146">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="b46f5-147">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="b46f5-147">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="b46f5-148">string</span><span class="sxs-lookup"><span data-stu-id="b46f5-148">string</span></span> | <span data-ttu-id="b46f5-149">エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b46f5-149">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="b46f5-150">string</span><span class="sxs-lookup"><span data-stu-id="b46f5-150">string</span></span> | <span data-ttu-id="b46f5-151">イベントに関連付けられている市区町村、国、またはその他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="b46f5-151">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="b46f5-152">string</span><span class="sxs-lookup"><span data-stu-id="b46f5-152">string</span></span> | <span data-ttu-id="b46f5-153">エンドポイントの IP アドレスに関連付けられているインターネットサービスプロバイダー (ISP)</span><span class="sxs-lookup"><span data-stu-id="b46f5-153">Internet service provider (ISP) associated with the endpoint IP address</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b46f5-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="b46f5-154">Related topics</span></span>
- [<span data-ttu-id="b46f5-155">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="b46f5-155">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b46f5-156">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="b46f5-156">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b46f5-157">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="b46f5-157">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b46f5-158">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="b46f5-158">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b46f5-159">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="b46f5-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b46f5-160">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="b46f5-160">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
