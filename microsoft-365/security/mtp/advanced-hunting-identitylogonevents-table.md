---
title: 高度な検索スキーマの IdentityLogonEvents テーブル
description: 高度な検索スキーマの IdentityLogonEvents テーブルに Active Directory によって記録される認証イベントについて説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、IdentityLogonEvents、Azure AD、Active Directory、Azure ATP、ID
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
ms.openlocfilehash: 1df1295b3386b94e3737c53ac8226c719c8bfa08
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929924"
---
# <a name="identitylogonevents"></a><span data-ttu-id="9b044-104">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="9b044-104">IdentityLogonEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9b044-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9b044-105">**Applies to:**</span></span>
- <span data-ttu-id="9b044-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b044-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9b044-107">高度な検索スキーマの表には、Microsoft Defender によってキャプチャされたオンプレミスの Active Directory を通じて行われた認証アクティビティに関する情報と、Microsoft Cloud App Security によってキャプチャされた Microsoft オンライン サービスに関連する認証アクティビティが含まれます。 `IdentityLogonEvents` [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9b044-107">The `IdentityLogonEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about authentication activities made through your on-premises Active Directory captured by Microsoft Defender for Identity and authentication activities related to Microsoft online services captured by Microsoft Cloud App Security.</span></span> <span data-ttu-id="9b044-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b044-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="9b044-109">テーブルでサポートされているイベントの種類 ( 値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ `ActionType` リファレンスを使用してください。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="9b044-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

>[!NOTE]
><span data-ttu-id="9b044-110">次の表では、Cloud App Security によって追跡される Azure Active Directory (AD) ログオン アクティビティ、特に ActiveSync や他のレガシ プロトコルを使用した対話型サインインと認証アクティビティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9b044-110">This table covers Azure Active Directory (AD) logon activities tracked by Cloud App Security, specifically interactive sign-ins and authentication activities using ActiveSync and other legacy protocols.</span></span> <span data-ttu-id="9b044-111">この表では使用できない非対話型ログオンは、Azure 管理者監査ログADできます。</span><span class="sxs-lookup"><span data-stu-id="9b044-111">Non-interactive logons that are not available in this table can be viewed in the Azure AD audit log.</span></span> [<span data-ttu-id="9b044-112">Cloud App Security を Microsoft 365 に接続する方法の詳細</span><span class="sxs-lookup"><span data-stu-id="9b044-112">Learn more about connecting Cloud App Security to Microsoft 365</span></span>](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

<span data-ttu-id="9b044-113">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b044-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9b044-114">列名</span><span class="sxs-lookup"><span data-stu-id="9b044-114">Column name</span></span> | <span data-ttu-id="9b044-115">データ型</span><span class="sxs-lookup"><span data-stu-id="9b044-115">Data type</span></span> | <span data-ttu-id="9b044-116">説明</span><span class="sxs-lookup"><span data-stu-id="9b044-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9b044-117">日付型</span><span class="sxs-lookup"><span data-stu-id="9b044-117">datetime</span></span> | <span data-ttu-id="9b044-118">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="9b044-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="9b044-119">string</span><span class="sxs-lookup"><span data-stu-id="9b044-119">string</span></span> | <span data-ttu-id="9b044-120">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="9b044-120">Type of activity that triggered the event.</span></span> <span data-ttu-id="9b044-121">詳細については [、ポータル内スキーマ リファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b044-121">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `LogonType` | <span data-ttu-id="9b044-122">string</span><span class="sxs-lookup"><span data-stu-id="9b044-122">string</span></span> | <span data-ttu-id="9b044-123">ログオン セッションの種類。具体的には次の種類があります。</span><span class="sxs-lookup"><span data-stu-id="9b044-123">Type of logon session, specifically:</span></span><br><br> <span data-ttu-id="9b044-124">- **対話型** - ユーザーがローカルのキーボードと画面を使ってコンピューターと物理的に対話する</span><span class="sxs-lookup"><span data-stu-id="9b044-124">- **Interactive** - User physically interacts with the machine using the local keyboard and screen</span></span><br><br> <span data-ttu-id="9b044-125">- **リモート 対話型 (RDP)** ログオン - ユーザーはリモート デスクトップ、ターミナル サービス、リモート アシスタンス、その他の RDP クライアントを使用してリモートでコンピューターと対話します。</span><span class="sxs-lookup"><span data-stu-id="9b044-125">- **Remote interactive (RDP) logons** - User interacts with the machine remotely using Remote Desktop, Terminal Services, Remote Assistance, or other RDP clients</span></span><br><br> <span data-ttu-id="9b044-126">- **ネットワーク** - PsExec を使用してコンピューターにアクセスするか、プリンターや共有フォルダーなどのコンピューター上の共有リソースにアクセスするときに開始されるセッション</span><span class="sxs-lookup"><span data-stu-id="9b044-126">- **Network** - Session initiated when the machine is accessed using PsExec or when shared resources on the machine, such as printers and shared folders, are accessed</span></span><br><br> <span data-ttu-id="9b044-127">- **Batch** - スケジュールされたタスクによって開始されるセッション</span><span class="sxs-lookup"><span data-stu-id="9b044-127">- **Batch** - Session initiated by scheduled tasks</span></span><br><br> <span data-ttu-id="9b044-128">- **サービス** - サービスの開始時に開始されるセッション</span><span class="sxs-lookup"><span data-stu-id="9b044-128">- **Service** - Session initiated by services as they start</span></span> |
| `Application` | <span data-ttu-id="9b044-129">string</span><span class="sxs-lookup"><span data-stu-id="9b044-129">string</span></span> | <span data-ttu-id="9b044-130">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="9b044-130">Application that performed the recorded action</span></span> |
| `Protocol` | <span data-ttu-id="9b044-131">string</span><span class="sxs-lookup"><span data-stu-id="9b044-131">string</span></span> | <span data-ttu-id="9b044-132">使用されるネットワーク プロトコル</span><span class="sxs-lookup"><span data-stu-id="9b044-132">Network protocol used</span></span> |
| `FailureReason` | <span data-ttu-id="9b044-133">string</span><span class="sxs-lookup"><span data-stu-id="9b044-133">string</span></span> | <span data-ttu-id="9b044-134">記録されたアクションが失敗した理由を説明する情報</span><span class="sxs-lookup"><span data-stu-id="9b044-134">Information explaining why the recorded action failed</span></span> |
| `AccountName` | <span data-ttu-id="9b044-135">string</span><span class="sxs-lookup"><span data-stu-id="9b044-135">string</span></span> | <span data-ttu-id="9b044-136">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="9b044-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="9b044-137">string</span><span class="sxs-lookup"><span data-stu-id="9b044-137">string</span></span> | <span data-ttu-id="9b044-138">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="9b044-138">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="9b044-139">string</span><span class="sxs-lookup"><span data-stu-id="9b044-139">string</span></span> | <span data-ttu-id="9b044-140">アカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="9b044-140">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="9b044-141">string</span><span class="sxs-lookup"><span data-stu-id="9b044-141">string</span></span> | <span data-ttu-id="9b044-142">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="9b044-142">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="9b044-143">string</span><span class="sxs-lookup"><span data-stu-id="9b044-143">string</span></span> | <span data-ttu-id="9b044-144">Azure AD のアカウントの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="9b044-144">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="9b044-145">string</span><span class="sxs-lookup"><span data-stu-id="9b044-145">string</span></span> | <span data-ttu-id="9b044-146">アドレス帳に表示されるアカウント ユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="9b044-146">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="9b044-147">通常、特定の名前または名、ミドル ネームの開始、姓または姓の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="9b044-147">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="9b044-148">string</span><span class="sxs-lookup"><span data-stu-id="9b044-148">string</span></span> | <span data-ttu-id="9b044-149">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="9b044-149">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="9b044-150">string</span><span class="sxs-lookup"><span data-stu-id="9b044-150">string</span></span> | <span data-ttu-id="9b044-151">デバイスの種類</span><span class="sxs-lookup"><span data-stu-id="9b044-151">Type of device</span></span> |
| `OSPlatform` | <span data-ttu-id="9b044-152">string</span><span class="sxs-lookup"><span data-stu-id="9b044-152">string</span></span> | <span data-ttu-id="9b044-153">コンピューターで実行されているオペレーティング システムのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="9b044-153">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="9b044-154">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="9b044-154">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="9b044-155">string</span><span class="sxs-lookup"><span data-stu-id="9b044-155">string</span></span> | <span data-ttu-id="9b044-156">エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="9b044-156">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="9b044-157">string</span><span class="sxs-lookup"><span data-stu-id="9b044-157">string</span></span> | <span data-ttu-id="9b044-158">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの名前</span><span class="sxs-lookup"><span data-stu-id="9b044-158">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="9b044-159">string</span><span class="sxs-lookup"><span data-stu-id="9b044-159">string</span></span> | <span data-ttu-id="9b044-160">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="9b044-160">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="9b044-161">string</span><span class="sxs-lookup"><span data-stu-id="9b044-161">string</span></span> | <span data-ttu-id="9b044-162">記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="9b044-162">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="9b044-163">string</span><span class="sxs-lookup"><span data-stu-id="9b044-163">string</span></span> | <span data-ttu-id="9b044-164">記録されたアクションが適用されたアカウントの表示名</span><span class="sxs-lookup"><span data-stu-id="9b044-164">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="9b044-165">string</span><span class="sxs-lookup"><span data-stu-id="9b044-165">string</span></span> | <span data-ttu-id="9b044-166">イベントに関連付けられている都市、国、その他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="9b044-166">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="9b044-167">string</span><span class="sxs-lookup"><span data-stu-id="9b044-167">string</span></span> | <span data-ttu-id="9b044-168">エンドポイント IP アドレスに関連付けられたインターネット サービス プロバイダー (ISP)</span><span class="sxs-lookup"><span data-stu-id="9b044-168">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="9b044-169">long</span><span class="sxs-lookup"><span data-stu-id="9b044-169">long</span></span> | <span data-ttu-id="9b044-170">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="9b044-170">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="9b044-171">string</span><span class="sxs-lookup"><span data-stu-id="9b044-171">string</span></span> | <span data-ttu-id="9b044-172">エンティティまたはイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="9b044-172">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9b044-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b044-173">Related topics</span></span>
- [<span data-ttu-id="9b044-174">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="9b044-174">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9b044-175">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="9b044-175">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9b044-176">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="9b044-176">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9b044-177">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="9b044-177">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9b044-178">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="9b044-178">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9b044-179">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="9b044-179">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
