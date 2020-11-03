---
title: Microsoft 365 Defender でカスタム検出ルールを作成および管理する
description: 高度な検索クエリに基づいてカスタムの検出ルールを作成および管理する方法について説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検出、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、ユーザー設定の検出、ルール、スキーマ、kusto、microsoft 365、Microsoft Threat Protection、RBAC、アクセス許可、Microsoft Defender ATP
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
ms.openlocfilehash: 5de4532a1bba809cde16ba6033ab30773a832176
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846774"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="fccbb-104">カスタム検出ルールを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="fccbb-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fccbb-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fccbb-105">**Applies to:**</span></span>
- <span data-ttu-id="fccbb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fccbb-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fccbb-107">カスタム検出ルールは、 [高度な](advanced-hunting-overview.md) 検索クエリを使用して設計および微調整できるルールです。</span><span class="sxs-lookup"><span data-stu-id="fccbb-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="fccbb-108">これらのルールを使用すると、疑いのある違反のアクティビティや不適切なエンドポイントを含む、さまざまなイベントやシステム状態を事前に監視できます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="fccbb-109">それらを定期的に実行するように設定して、一致するものがある場合は警告を生成し、応答アクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="fccbb-110">ユーザー設定の検出を管理するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fccbb-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="fccbb-111">ユーザー設定の検出を管理するには、次のいずれかの役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fccbb-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="fccbb-112">**セキュリティ管理者** —この [Azure Active Directory の役割](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) を持つユーザーは、Microsoft 365 セキュリティセンターおよびその他のポータルおよびサービスのセキュリティ設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-112">**Security administrator** —Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="fccbb-113">**セキュリティオペレーター** -この [Azure Active Directory の役割](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) を持つユーザーは、アラートを管理し、セキュリティ関連機能へのグローバルな読み取り専用アクセス権を持つことができます。これには、Microsoft 365 セキュリティセンターのすべての情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-113">**Security operator** —Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="fccbb-114">この役割は、エンドポイントの Microsoft Defender で役割ベースのアクセス制御 (RBAC) がオフになっている場合にのみ、カスタムの検出を管理するのに十分です。</span><span class="sxs-lookup"><span data-stu-id="fccbb-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="fccbb-115">RBAC を構成している場合は、エンドポイントの Defender の **セキュリティ設定の管理** アクセス許可も必要です。</span><span class="sxs-lookup"><span data-stu-id="fccbb-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="fccbb-116">必要なアクセス許可を管理するには、 **全体管理者** が次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="fccbb-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="fccbb-117">「 **Roles** security admin」の下にある [Microsoft 365 管理センター](https://admin.microsoft.com/)で、 **セキュリティ管理者** または **セキュリティオペレーター** の役割を割り当て  >  **Security admin** ます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="fccbb-118">Microsoft defender [セキュリティセンター](https://securitycenter.windows.com/)のエンドポイントに対する RBAC 設定を [ **設定** の  >  **アクセス許可** の役割] の下で確認  >  **Roles** します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="fccbb-119">対応する役割を選択して、[ **セキュリティ設定の管理** ] アクセス許可を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="fccbb-120">ユーザー設定の検出を管理するために、 **セキュリティオペレーター** は、RBAC が有効になっている場合は、Microsoft Defender のエンドポイントに対する **セキュリティ設定の管理** 権限を必要とします。</span><span class="sxs-lookup"><span data-stu-id="fccbb-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="fccbb-121">カスタム検出ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="fccbb-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="fccbb-122">1. クエリを準備します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-122">1. Prepare the query.</span></span>

<span data-ttu-id="fccbb-123">Microsoft 365 セキュリティセンターで、 **[高度な** 検索] に移動して既存のクエリを選択するか、新しいクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="fccbb-124">新しいクエリを使用する場合は、クエリを実行してエラーを特定し、考えられる結果を理解します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="fccbb-125">サービスによって返される通知が多すぎないようにするために、各ルールは、実行時に常に100通知のみを生成するように制限されています。</span><span class="sxs-lookup"><span data-stu-id="fccbb-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="fccbb-126">ルールを作成する前に、クエリを微調整して、通常の日常的なアクティビティに対する警告が発生しないようにします。</span><span class="sxs-lookup"><span data-stu-id="fccbb-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="fccbb-127">クエリ結果に必要な列</span><span class="sxs-lookup"><span data-stu-id="fccbb-127">Required columns in the query results</span></span>
<span data-ttu-id="fccbb-128">カスタム検出ルールを作成するには、クエリは次の列を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="fccbb-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="fccbb-129">`Timestamp`—生成された通知のタイムスタンプを設定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="fccbb-130">`ReportId`—元のレコードの参照を有効にします。</span><span class="sxs-lookup"><span data-stu-id="fccbb-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="fccbb-131">特定のデバイス、ユーザー、またはメールボックスを識別する次のいずれかの列。</span><span class="sxs-lookup"><span data-stu-id="fccbb-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="fccbb-132">`SenderFromAddress` (エンベロープの送信者または Return-Path アドレス)</span><span class="sxs-lookup"><span data-stu-id="fccbb-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="fccbb-133">`SenderMailFromAddress` (電子メールクライアントによって表示される sender アドレス)</span><span class="sxs-lookup"><span data-stu-id="fccbb-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="fccbb-134">[高度な検索スキーマ](advanced-hunting-schema-tables.md)に新しいテーブルが追加されると、追加のエンティティのサポートが追加されます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="fccbb-135">検索結果をカスタマイズまたは集計するために or 演算子を使用しないような単純なクエリでは、 `project` `summarize` 通常、これらの共通の列が返されます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="fccbb-136">より複雑なクエリでこれらの列が返されるようにするには、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="fccbb-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="fccbb-137">たとえば、などの列の下にあるエンティティで集計およびカウントを行う場合は、そのままにし `DeviceId` `Timestamp` て、それぞれの一意な `ReportId` イベントに関係する最新のイベントから取得することができ `DeviceId` ます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="fccbb-138">以下のサンプルクエリは、ウイルス検出を使用して一意のデバイス () の数をカウント `DeviceId` し、この数を使用して、検出されたデバイスのみを検出します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="fccbb-139">最新のおよび対応するを取得するには、 `Timestamp` `ReportId` 演算子を `summarize` 関数で使用し `arg_max` ます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="fccbb-140">クエリパフォーマンスを向上させるには、ルールの実行頻度と一致する時間フィルターを設定します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="fccbb-141">最も短い頻度は _24 時間ごと_ に行われるため、過去1日のフィルター処理はすべての新しいデータを対象とします。</span><span class="sxs-lookup"><span data-stu-id="fccbb-141">Since the least frequent run is _every 24 hours_ , filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="fccbb-142">2. 新しいルールを作成し、通知の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="fccbb-143">クエリエディターでクエリを実行して、[ **検出ルールの作成** ] を選択し、次の通知の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="fccbb-144">**検出名** —検出ルールの名前</span><span class="sxs-lookup"><span data-stu-id="fccbb-144">**Detection name** —name of the detection rule</span></span>
- <span data-ttu-id="fccbb-145">**頻度** —クエリを実行してアクションを実行する間隔。</span><span class="sxs-lookup"><span data-stu-id="fccbb-145">**Frequency** —interval for running the query and taking action.</span></span> [<span data-ttu-id="fccbb-146">以下の追加のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fccbb-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="fccbb-147">**アラートタイトル** -ルールによってトリガーされたアラートと共に表示されるタイトル</span><span class="sxs-lookup"><span data-stu-id="fccbb-147">**Alert title** —title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="fccbb-148">**重要度** —ルールによって識別されるコンポーネントまたはアクティビティの潜在的なリスク</span><span class="sxs-lookup"><span data-stu-id="fccbb-148">**Severity** —potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="fccbb-149">**カテゴリ** —ルールによって識別される脅威コンポーネントまたはアクティビティ</span><span class="sxs-lookup"><span data-stu-id="fccbb-149">**Category** —threat component or activity identified by the rule</span></span>
- <span data-ttu-id="fccbb-150">**MITRE att&** の「」: [MITRE ATT&](https://attack.mitre.org/)の「」フレームワークに記載されているように、ルールによって識別される1つまたは複数の攻撃手法。</span><span class="sxs-lookup"><span data-stu-id="fccbb-150">**MITRE ATT&CK techniques** —one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="fccbb-151">このセクションは、マルウェア、ランサムウェア、疑わしいアクティビティ、不要なソフトウェアなど、特定のアラートカテゴリでは非表示になります。</span><span class="sxs-lookup"><span data-stu-id="fccbb-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="fccbb-152">**Description** —ルールによって識別されたコンポーネントまたはアクティビティに関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="fccbb-152">**Description** —more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="fccbb-153">**推奨** されるアクション-通知に応答する可能性があるその他のアクション。</span><span class="sxs-lookup"><span data-stu-id="fccbb-153">**Recommended actions** —additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="fccbb-154">ルールの頻度</span><span class="sxs-lookup"><span data-stu-id="fccbb-154">Rule frequency</span></span>
<span data-ttu-id="fccbb-155">新しいルールを保存または編集すると、それが実行され、過去30日間のデータに一致するかどうかがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="fccbb-156">その後、ルールは固定された間隔で再び実行され、選択した頻度に基づいて、継続時間が適用されます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="fccbb-157">**24 時間ごと** : 過去30日間のデータをチェックして、24時間ごとに実行します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-157">**Every 24 hours** —runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="fccbb-158">**12 時間ごと** -過去24時間以内にデータをチェックして、12時間ごとに実行します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-158">**Every 12 hours** —runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="fccbb-159">**3 時間ごと** —過去6時間にデータをチェックして、3時間ごとに実行します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-159">**Every 3 hours** —runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="fccbb-160">毎時に **1 時間ごと** に実行され、過去2時間のデータをチェックします。</span><span class="sxs-lookup"><span data-stu-id="fccbb-160">**Every hour** —runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="fccbb-161">クエリ内の時間フィルターを「いいね!」の継続期間に一致させます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="fccbb-162">元の戻り時間以外の結果は無視されます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="fccbb-163">検出を監視する頻度と一致する頻度を選択します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="fccbb-164">通知に応答するために組織の能力を考慮します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="fccbb-165">3. 影響を受けるエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="fccbb-166">影響を受ける主なエンティティまたは影響を受けるエンティティがあることが予想されるクエリ結果内の列を特定します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="fccbb-167">たとえば、クエリは送信者 ( `SenderFromAddress` または `SenderMailFromAddress` ) と受信者 () のアドレスを返す場合があり `RecipientEmailAddress` ます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="fccbb-168">これらの列のうち、主な影響を受けるエンティティを識別することにより、サービスは関連するアラートの集約、インシデントの関連付け、およびターゲットの応答アクションの実行に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="fccbb-169">エンティティの種類 (メールボックス、ユーザー、またはデバイス) ごとに1つの列のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="fccbb-170">クエリで返されない列は選択できません。</span><span class="sxs-lookup"><span data-stu-id="fccbb-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="fccbb-171">4. アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-171">4. Specify actions.</span></span>
<span data-ttu-id="fccbb-172">カスタム検出ルールは、クエリによって返されるデバイス、ファイル、またはユーザーに対して、自動的にアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="fccbb-173">デバイスに対するアクション</span><span class="sxs-lookup"><span data-stu-id="fccbb-173">Actions on devices</span></span>
<span data-ttu-id="fccbb-174">これらのアクションは `DeviceId` 、クエリ結果の列にあるデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="fccbb-175">**分離デバイス** —エンドポイントに Microsoft Defender を使用して完全なネットワークの分離を適用することで、デバイスがどのアプリケーションまたはサービスにも接続できないようにします。</span><span class="sxs-lookup"><span data-stu-id="fccbb-175">**Isolate device** —uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="fccbb-176">エンドポイントコンピューターの分離に関する Microsoft Defender の詳細情報</span><span class="sxs-lookup"><span data-stu-id="fccbb-176">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="fccbb-177">**収集調査パッケージ** — ZIP ファイル内のデバイス情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-177">**Collect investigation package** —collects device information in a ZIP file.</span></span> [<span data-ttu-id="fccbb-178">エンドポイント調査パッケージの Microsoft Defender に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="fccbb-178">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="fccbb-179">**ウイルス対策スキャンを実行** する—デバイス上で Windows Defender ウイルス対策スキャンを完全に実行します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-179">**Run antivirus scan** —performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="fccbb-180">**開始調査** : デバイスの [自動調査](mtp-autoir.md) を開始します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-180">**Initiate investigation** —initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="fccbb-181">**アプリの実行を制限** する-デバイスに制限を設定して、Microsoft が発行した証明書で署名されたファイルのみを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="fccbb-181">**Restrict app execution** —sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="fccbb-182">エンドポイントの Microsoft Defender のアプリ制限についての詳細情報</span><span class="sxs-lookup"><span data-stu-id="fccbb-182">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="fccbb-183">ファイルに対するアクション</span><span class="sxs-lookup"><span data-stu-id="fccbb-183">Actions on files</span></span>
<span data-ttu-id="fccbb-184">このオプションを選択すると、 **Quarantine file** `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` クエリ結果の、、、または列のファイルに [ファイルの検疫] アクションを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="fccbb-185">この操作は、現在の場所からファイルを削除し、そのコピーを検疫に配置します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="fccbb-186">ユーザーに対するアクション</span><span class="sxs-lookup"><span data-stu-id="fccbb-186">Actions on users</span></span>
<span data-ttu-id="fccbb-187">このチェックボックスをオンにすると、クエリ結果の、、または列にあるユーザーに対して [侵害済みの **ユーザーとしてマーク** ] の操作が実行され `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` ます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="fccbb-188">この操作によって、Azure Active Directory でユーザーのリスクレベルが "高" に設定され、対応する [id 保護ポリシー](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="fccbb-189">カスタム検出ルールのアクションの許可またはブロックは、現在、Microsoft 365 Defender ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fccbb-189">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="fccbb-190">5. ルールの範囲を設定します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-190">5. Set the rule scope.</span></span>
<span data-ttu-id="fccbb-191">ルールに含まれるデバイスを指定するようにスコープを設定します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="fccbb-192">この範囲は、デバイスをチェックするルールに影響し、メールボックスとユーザーアカウントまたは id のみをチェックするルールには影響しません。</span><span class="sxs-lookup"><span data-stu-id="fccbb-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="fccbb-193">スコープを設定するときは、次のオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="fccbb-194">すべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="fccbb-194">All devices</span></span>
- <span data-ttu-id="fccbb-195">特定のデバイスグループ</span><span class="sxs-lookup"><span data-stu-id="fccbb-195">Specific device groups</span></span>

<span data-ttu-id="fccbb-196">範囲内のデバイスからのデータのみが照会されます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="fccbb-197">また、アクションはこれらのデバイスでのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="fccbb-198">6. ルールを確認し、オンにします。</span><span class="sxs-lookup"><span data-stu-id="fccbb-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="fccbb-199">ルールを確認した後、[ **作成** ] を選択して保存します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="fccbb-200">カスタム検出ルールが直ちに実行されます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="fccbb-201">この動作は、構成された頻度に基づいて、一致をチェックし、通知を生成し、応答アクションを実行することによって再度実行します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="fccbb-202">既存のカスタム検出ルールを管理する</span><span class="sxs-lookup"><span data-stu-id="fccbb-202">Manage existing custom detection rules</span></span>
<span data-ttu-id="fccbb-203">既存のカスタム検出ルールの一覧を表示し、以前の実行をチェックして、トリガーされた通知を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-203">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="fccbb-204">また、必要に応じてルールを実行して変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-204">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="fccbb-205">既存のルールを表示する</span><span class="sxs-lookup"><span data-stu-id="fccbb-205">View existing rules</span></span>

<span data-ttu-id="fccbb-206">既存のカスタム検出ルールをすべて表示 **するには** 、[カスタム検出の検索] に移動し  >  **Custom detections** ます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-206">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="fccbb-207">ページには、次の実行情報を含むすべてのルールの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-207">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="fccbb-208">[ **前回の実行** ]-ルールが最後に実行されたときに、クエリの一致をチェックし、通知を生成する</span><span class="sxs-lookup"><span data-stu-id="fccbb-208">**Last run** —when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="fccbb-209">**最終実行状態** —ルールが正常に実行されたかどうか</span><span class="sxs-lookup"><span data-stu-id="fccbb-209">**Last run status** —whether a rule ran successfully</span></span>
- <span data-ttu-id="fccbb-210">**次回の実行** -次のスケジュールされた実行</span><span class="sxs-lookup"><span data-stu-id="fccbb-210">**Next run** —the next scheduled run</span></span>
- <span data-ttu-id="fccbb-211">**状態** : ルールが有効になっているかどうか</span><span class="sxs-lookup"><span data-stu-id="fccbb-211">**Status** —whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="fccbb-212">ルールの詳細、変更ルール、および実行ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="fccbb-212">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="fccbb-213">カスタム検出ルールに関する包括的な情報を表示するには、[ユーザー設定の **検出を検索] に移動** し  >  **Custom detections** て、ルールの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-213">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="fccbb-214">その後、そのルールについての情報 (実行状態やスコープなど) を表示できます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-214">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="fccbb-215">また、このページには、トリガーされた通知とアクションのリストも表示されます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-215">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="fccbb-216">![カスタム検出ルールの詳細ページ](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="fccbb-216">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="fccbb-217">*カスタム検出ルールの詳細*</span><span class="sxs-lookup"><span data-stu-id="fccbb-217">*Custom detection rule details*</span></span>

<span data-ttu-id="fccbb-218">このページでは、ルールに対して次の操作を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-218">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="fccbb-219">**Run** -ルールを直ちに実行します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-219">**Run** —run the rule immediately.</span></span> <span data-ttu-id="fccbb-220">これにより、次の実行の間隔もリセットされます。</span><span class="sxs-lookup"><span data-stu-id="fccbb-220">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="fccbb-221">**編集** —クエリを変更せずにルールを変更する</span><span class="sxs-lookup"><span data-stu-id="fccbb-221">**Edit** —modify the rule without changing the query</span></span>
- <span data-ttu-id="fccbb-222">**クエリの変更** -高度な検索でクエリを編集する</span><span class="sxs-lookup"><span data-stu-id="fccbb-222">**Modify query** —edit the query in advanced hunting</span></span>
- <span data-ttu-id="fccbb-223">**オン**  / **オフ** —ルールを有効にするか、または実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-223">**Turn on** / **Turn off** —enable the rule or stop it from running</span></span>
- <span data-ttu-id="fccbb-224">**削除** —ルールをオフにして削除する</span><span class="sxs-lookup"><span data-stu-id="fccbb-224">**Delete** —turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="fccbb-225">トリガーされた通知の表示と管理</span><span class="sxs-lookup"><span data-stu-id="fccbb-225">View and manage triggered alerts</span></span>

<span data-ttu-id="fccbb-226">[ルールの詳細] 画面 **Hunting** (  >  [ **ユーザー設定の検出** を探し  >  ています **]** ) で、[トリガーされた **アラート** ] に移動します。これは、ルールに一致することによって生成されたアラートを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-226">In the rule details screen ( **Hunting** > **Custom detections** > **[Rule name]** ), go to  **Triggered alerts** , which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="fccbb-227">通知を選択して、それに関する詳細情報を表示し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fccbb-227">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="fccbb-228">状態と分類 (true または false のアラート) を設定してアラートを管理する</span><span class="sxs-lookup"><span data-stu-id="fccbb-228">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="fccbb-229">警告をインシデントにリンクする</span><span class="sxs-lookup"><span data-stu-id="fccbb-229">Link the alert to an incident</span></span>
- <span data-ttu-id="fccbb-230">高度な検索で警告をトリガーしたクエリを実行する</span><span class="sxs-lookup"><span data-stu-id="fccbb-230">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="fccbb-231">アクションを確認する</span><span class="sxs-lookup"><span data-stu-id="fccbb-231">Review actions</span></span>
<span data-ttu-id="fccbb-232">[仕分けルールの詳細] **Hunting** 画面 (  >  **ユーザー設定の検出** を探している場合) で、[トリガーされた  >  **[Rule name]\*\*\*\*アクション** ] に移動します。これは、ルールに一致するものに基づいて実行されたアクションを一覧します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-232">In the rule details screen ( **Hunting** > **Custom detections** > **[Rule name]** ), go to **Triggered actions** , which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="fccbb-233">テーブル内のアイテムに関する情報をすばやく表示し、アクションを実行するには、表の左側にある選択列 [&#10003;] を使用します。</span><span class="sxs-lookup"><span data-stu-id="fccbb-233">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="fccbb-234">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fccbb-234">Related topic</span></span>
- [<span data-ttu-id="fccbb-235">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="fccbb-235">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="fccbb-236">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="fccbb-236">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fccbb-237">高度な捜索のクエリ言語について学習する</span><span class="sxs-lookup"><span data-stu-id="fccbb-237">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
