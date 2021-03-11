---
title: 高度なハンティング スキーマの IdentityLogonEvents テーブル
description: 高度なハンティング スキーマの IdentityLogonEvents テーブルで Active Directory によって記録される認証イベントについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、IdentityLogonEvents、Azure AD、Active Directory、Azure ATP、ID
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
ms.openlocfilehash: 08dd78c7648126717113066e3c87b05e624f57d0
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712356"
---
# <a name="identitylogonevents"></a><span data-ttu-id="9bcbf-104">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="9bcbf-104">IdentityLogonEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9bcbf-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9bcbf-105">**Applies to:**</span></span>
- <span data-ttu-id="9bcbf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bcbf-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9bcbf-107">高度な検索スキーマの表には、Microsoft Defender for Identity によってキャプチャされたオンプレミスの Active Directory を介して行われた認証アクティビティと、Microsoft Cloud App Security によってキャプチャされた Microsoft オンライン サービスに関連する認証アクティビティに関する情報が含まれます。 `IdentityLogonEvents` [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9bcbf-107">The `IdentityLogonEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about authentication activities made through your on-premises Active Directory captured by Microsoft Defender for Identity and authentication activities related to Microsoft online services captured by Microsoft Cloud App Security.</span></span> <span data-ttu-id="9bcbf-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="9bcbf-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="9bcbf-109">テーブルでサポートされるイベントの種類 (値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ参照 `ActionType` を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bcbf-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference  available in the security center.</span></span>

>[!NOTE]
><span data-ttu-id="9bcbf-110">この表では、Cloud App Security によって追跡される Azure Active Directory (AD) ログオン アクティビティ、特に ActiveSync などのレガシ プロトコルを使用した対話型サインインと認証アクティビティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9bcbf-110">This table covers Azure Active Directory (AD) logon activities tracked by Cloud App Security, specifically interactive sign-ins and authentication activities using ActiveSync and other legacy protocols.</span></span> <span data-ttu-id="9bcbf-111">この表では使用できない非対話型ログオンは、Azure 監査ログADできます。</span><span class="sxs-lookup"><span data-stu-id="9bcbf-111">Non-interactive logons that are not available in this table can be viewed in the Azure AD audit log.</span></span> [<span data-ttu-id="9bcbf-112">Cloud App Security を Microsoft 365 に接続する方法の詳細</span><span class="sxs-lookup"><span data-stu-id="9bcbf-112">Learn more about connecting Cloud App Security to Microsoft 365</span></span>](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

<span data-ttu-id="9bcbf-113">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bcbf-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9bcbf-114">列名</span><span class="sxs-lookup"><span data-stu-id="9bcbf-114">Column name</span></span> | <span data-ttu-id="9bcbf-115">データ型</span><span class="sxs-lookup"><span data-stu-id="9bcbf-115">Data type</span></span> | <span data-ttu-id="9bcbf-116">説明</span><span class="sxs-lookup"><span data-stu-id="9bcbf-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9bcbf-117">日付型</span><span class="sxs-lookup"><span data-stu-id="9bcbf-117">datetime</span></span> | <span data-ttu-id="9bcbf-118">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="9bcbf-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="9bcbf-119">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-119">string</span></span> | <span data-ttu-id="9bcbf-120">イベントをトリガーしたアクティビティの種類。</span><span class="sxs-lookup"><span data-stu-id="9bcbf-120">Type of activity that triggered the event.</span></span> <span data-ttu-id="9bcbf-121">詳細については [、ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bcbf-121">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `LogonType` | <span data-ttu-id="9bcbf-122">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-122">string</span></span> | <span data-ttu-id="9bcbf-123">ログオン セッションの種類(具体的には次の場合):</span><span class="sxs-lookup"><span data-stu-id="9bcbf-123">Type of logon session, specifically:</span></span><br><br> <span data-ttu-id="9bcbf-124">- **対話型** - ユーザーがローカル キーボードと画面を使用してコンピューターと物理的に対話する</span><span class="sxs-lookup"><span data-stu-id="9bcbf-124">- **Interactive** - User physically interacts with the machine using the local keyboard and screen</span></span><br><br> <span data-ttu-id="9bcbf-125">- **リモート 対話型 (RDP) ログオン** - ユーザーはリモート デスクトップ、ターミナル サービス、リモート アシスタンス、または他の RDP クライアントを使用してコンピューターをリモート操作します。</span><span class="sxs-lookup"><span data-stu-id="9bcbf-125">- **Remote interactive (RDP) logons** - User interacts with the machine remotely using Remote Desktop, Terminal Services, Remote Assistance, or other RDP clients</span></span><br><br> <span data-ttu-id="9bcbf-126">- **ネットワーク** - PsExec を使用してコンピューターにアクセスした場合、またはコンピューター上の共有リソース (プリンターや共有フォルダーなど) にアクセスするときに開始されるセッション</span><span class="sxs-lookup"><span data-stu-id="9bcbf-126">- **Network** - Session initiated when the machine is accessed using PsExec or when shared resources on the machine, such as printers and shared folders, are accessed</span></span><br><br> <span data-ttu-id="9bcbf-127">- **Batch** - スケジュールされたタスクによって開始されるセッション</span><span class="sxs-lookup"><span data-stu-id="9bcbf-127">- **Batch** - Session initiated by scheduled tasks</span></span><br><br> <span data-ttu-id="9bcbf-128">- **サービス** - サービスが開始するセッション</span><span class="sxs-lookup"><span data-stu-id="9bcbf-128">- **Service** - Session initiated by services as they start</span></span> |
| `Application` | <span data-ttu-id="9bcbf-129">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-129">string</span></span> | <span data-ttu-id="9bcbf-130">記録されたアクションを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="9bcbf-130">Application that performed the recorded action</span></span> |
| `Protocol` | <span data-ttu-id="9bcbf-131">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-131">string</span></span> | <span data-ttu-id="9bcbf-132">使用されるネットワーク プロトコル</span><span class="sxs-lookup"><span data-stu-id="9bcbf-132">Network protocol used</span></span> |
| `FailureReason` | <span data-ttu-id="9bcbf-133">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-133">string</span></span> | <span data-ttu-id="9bcbf-134">記録されたアクションが失敗した理由を説明する情報</span><span class="sxs-lookup"><span data-stu-id="9bcbf-134">Information explaining why the recorded action failed</span></span> |
| `AccountName` | <span data-ttu-id="9bcbf-135">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-135">string</span></span> | <span data-ttu-id="9bcbf-136">アカウントのユーザー名</span><span class="sxs-lookup"><span data-stu-id="9bcbf-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="9bcbf-137">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-137">string</span></span> | <span data-ttu-id="9bcbf-138">アカウントのドメイン</span><span class="sxs-lookup"><span data-stu-id="9bcbf-138">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="9bcbf-139">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-139">string</span></span> | <span data-ttu-id="9bcbf-140">アカウントのユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="9bcbf-140">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="9bcbf-141">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-141">string</span></span> | <span data-ttu-id="9bcbf-142">アカウントのセキュリティ識別子 (SID)</span><span class="sxs-lookup"><span data-stu-id="9bcbf-142">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="9bcbf-143">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-143">string</span></span> | <span data-ttu-id="9bcbf-144">Azure アカウントのアカウントの一意AD</span><span class="sxs-lookup"><span data-stu-id="9bcbf-144">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="9bcbf-145">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-145">string</span></span> | <span data-ttu-id="9bcbf-146">アドレス帳に表示されるアカウント ユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="9bcbf-146">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="9bcbf-147">通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="9bcbf-147">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="9bcbf-148">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-148">string</span></span> | <span data-ttu-id="9bcbf-149">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="9bcbf-149">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="9bcbf-150">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-150">string</span></span> | <span data-ttu-id="9bcbf-151">デバイスの種類</span><span class="sxs-lookup"><span data-stu-id="9bcbf-151">Type of device</span></span> |
| `OSPlatform` | <span data-ttu-id="9bcbf-152">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-152">string</span></span> | <span data-ttu-id="9bcbf-153">コンピューターで実行されているオペレーティング システムのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="9bcbf-153">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="9bcbf-154">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="9bcbf-154">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="9bcbf-155">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-155">string</span></span> | <span data-ttu-id="9bcbf-156">エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="9bcbf-156">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="9bcbf-157">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-157">string</span></span> | <span data-ttu-id="9bcbf-158">通信中に使用される TCP ポート</span><span class="sxs-lookup"><span data-stu-id="9bcbf-158">TCP port used during communication</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="9bcbf-159">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-159">string</span></span> | <span data-ttu-id="9bcbf-160">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの名前</span><span class="sxs-lookup"><span data-stu-id="9bcbf-160">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="9bcbf-161">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-161">string</span></span> | <span data-ttu-id="9bcbf-162">記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="9bcbf-162">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="9bcbf-163">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-163">string</span></span> | <span data-ttu-id="9bcbf-164">関連するネットワーク通信の宛先ポート</span><span class="sxs-lookup"><span data-stu-id="9bcbf-164">Destination port of related network communications</span></span> |
| `TargetDeviceName` | <span data-ttu-id="9bcbf-165">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-165">string</span></span> | <span data-ttu-id="9bcbf-166">記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="9bcbf-166">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="9bcbf-167">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-167">string</span></span> | <span data-ttu-id="9bcbf-168">記録されたアクションが適用されたアカウントの表示名</span><span class="sxs-lookup"><span data-stu-id="9bcbf-168">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="9bcbf-169">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-169">string</span></span> | <span data-ttu-id="9bcbf-170">イベントに関連付けられている都市、国、その他の地理的な場所</span><span class="sxs-lookup"><span data-stu-id="9bcbf-170">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="9bcbf-171">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-171">string</span></span> | <span data-ttu-id="9bcbf-172">エンドポイント IP アドレスに関連付けられたインターネット サービス プロバイダー (ISP)</span><span class="sxs-lookup"><span data-stu-id="9bcbf-172">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="9bcbf-173">long</span><span class="sxs-lookup"><span data-stu-id="9bcbf-173">long</span></span> | <span data-ttu-id="9bcbf-174">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="9bcbf-174">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="9bcbf-175">string</span><span class="sxs-lookup"><span data-stu-id="9bcbf-175">string</span></span> | <span data-ttu-id="9bcbf-176">エンティティまたはイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="9bcbf-176">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9bcbf-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bcbf-177">Related topics</span></span>
- [<span data-ttu-id="9bcbf-178">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="9bcbf-178">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9bcbf-179">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="9bcbf-179">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9bcbf-180">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="9bcbf-180">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9bcbf-181">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="9bcbf-181">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9bcbf-182">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="9bcbf-182">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9bcbf-183">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="9bcbf-183">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
