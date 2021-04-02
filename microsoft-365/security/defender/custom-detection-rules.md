---
title: Microsoft 365 Defender でカスタム検出ルールを作成および管理する
description: 高度な検索クエリに基づいてカスタム検出ルールを作成および管理する方法について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、カスタム検出、ルール、スキーマ、kusto、microsoft 365、Microsoft Threat Protection、RBAC、permissions、Microsoft Defender ATP
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
ms.openlocfilehash: 220e4e6546899dd00f3a02bf83039a928be4f8dc
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498847"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="ceb9f-104">カスタム検出ルールを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="ceb9f-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ceb9f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ceb9f-105">**Applies to:**</span></span>
- <span data-ttu-id="ceb9f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ceb9f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ceb9f-107">カスタム検出ルールは、高度な検索クエリを使用して設計および [調整できるルール](advanced-hunting-overview.md) です。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="ceb9f-108">これらのルールを使用すると、侵害の疑いのあるアクティビティや誤った構成されたエンドポイントなど、さまざまなイベントやシステム状態を積極的に監視できます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="ceb9f-109">一定の間隔で実行し、アラートを生成し、一致するたびに応答アクションを実行する設定できます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="ceb9f-110">カスタム検出を管理するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ceb9f-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="ceb9f-111">カスタム検出を管理するには、次のいずれかの役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="ceb9f-112">**セキュリティ管理者**:この [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) ロールを持つユーザーは、Microsoft 365 セキュリティ センターおよび他のポータルおよびサービスのセキュリティ設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-112">**Security administrator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="ceb9f-113">**セキュリティ オペレーター**:この [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) ロールを持つユーザーは、アラートを管理し、Microsoft 365 セキュリティ センターのすべての情報を含む、セキュリティ関連の機能へのグローバルな読み取り専用アクセス権を持つ。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-113">**Security operator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="ceb9f-114">この役割は、Microsoft Defender for Endpoint で役割ベースのアクセス制御 (RBAC) がオフになっている場合にのみ、カスタム検出を管理するのに十分です。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ceb9f-115">RBAC が構成されている場合は、Defender **for** Endpoint のセキュリティ設定の管理アクセス許可も必要です。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="ceb9f-116">必要なアクセス許可を管理するには、グローバル **管理者は次の機能を使用** できます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="ceb9f-117">[役割の **セキュリティ管理者] の** 下にある [Microsoft 365 管理](https://admin.microsoft.com/)センターでセキュリティ管理者またはセキュリティオペレーター **の役割**  >  **を割り当てます**。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="ceb9f-118">Microsoft Defender セキュリティ センターの [設定のアクセス許可の役割] で [、Microsoft Defender](https://securitycenter.windows.com/) for Endpoint の RBAC  >  **設定を確認**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="ceb9f-119">対応する役割を選択して、セキュリティ設定の **管理権限を割り当** てる。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="ceb9f-120">カスタム検出を管理 **するには、RBAC** が有効になっている場合、セキュリティオペレーターは Microsoft Defender for Endpoint のセキュリティ設定の管理権限を必要とします。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="ceb9f-121">カスタム検出ルールの作成</span><span class="sxs-lookup"><span data-stu-id="ceb9f-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="ceb9f-122">1. クエリを準備します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-122">1. Prepare the query.</span></span>

<span data-ttu-id="ceb9f-123">Microsoft 365 セキュリティ センターで、[高度な検索] に **移動し、** 既存のクエリを選択するか、新しいクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="ceb9f-124">新しいクエリを使用する場合は、クエリを実行してエラーを特定し、考えられる結果を理解します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="ceb9f-125">サービスがあまりにも多くのアラートを返さなすぎ防止するために、各ルールは、実行されるたびに 100 件のアラートのみを生成するに制限されます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="ceb9f-126">ルールを作成する前に、クエリを調整して、通常の毎日のアクティビティに対する警告を回避してください。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="ceb9f-127">クエリ結果に必要な列</span><span class="sxs-lookup"><span data-stu-id="ceb9f-127">Required columns in the query results</span></span>
<span data-ttu-id="ceb9f-128">カスタム検出ルールを作成するには、次の列を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="ceb9f-129">`Timestamp`生成されたアラートのタイムスタンプを設定するために使用される</span><span class="sxs-lookup"><span data-stu-id="ceb9f-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="ceb9f-130">`ReportId`—元のレコードの参照を有効にする</span><span class="sxs-lookup"><span data-stu-id="ceb9f-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="ceb9f-131">特定のデバイス、ユーザー、またはメールボックスを識別する次のいずれかの列。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="ceb9f-132">`SenderFromAddress` (封筒の送信者またはReturn-Pathアドレス)</span><span class="sxs-lookup"><span data-stu-id="ceb9f-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="ceb9f-133">`SenderMailFromAddress` (電子メール クライアントによって表示される送信者アドレス)</span><span class="sxs-lookup"><span data-stu-id="ceb9f-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="ceb9f-134">新しいテーブルが高度な狩猟スキーマに追加されるに応じて、追加のエンティティ [のサポートが追加されます](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="ceb9f-135">単純なクエリ (結果をカスタマイズまたは集計するために or 演算子を使用しないクエリなど) は、通常、これらの一般的な `project` `summarize` 列を返します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="ceb9f-136">より複雑なクエリがこれらの列を返すには、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="ceb9f-137">たとえば、次のような列の下のエンティティ別に集計してカウントする場合でも、各一意のイベントを含む最新のイベントから取得 `DeviceId` `Timestamp` `ReportId` できます `DeviceId` 。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="ceb9f-138">以下のサンプル クエリは、ウイルス対策の検出を含む一意のデバイス ( ) の数をカウントし、この数を使用して 5 つを超える検出を持つデバイス `DeviceId` のみを検索します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="ceb9f-139">最新の値と `Timestamp` 対応する値を取得 `ReportId` するには、関数と `summarize` 一緒に演算子を使用 `arg_max` します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="ceb9f-140">クエリのパフォーマンスを向上するには、ルールの目的の実行頻度に一致する時間フィルターを設定します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="ceb9f-141">実行頻度が最も少ないのは _24_ 時間ごとに行われるので、過去 1 日のフィルター処理では、すべての新しいデータがカバーされます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="ceb9f-142">2. 新しいルールを作成し、アラートの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="ceb9f-143">クエリ エディターでクエリを使用して、[検出ルールの作成] **を選択し** 、次のアラートの詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="ceb9f-144">**検出名**—検出ルールの名前</span><span class="sxs-lookup"><span data-stu-id="ceb9f-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="ceb9f-145">**頻度**—クエリを実行してアクションを実行する間隔。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="ceb9f-146">以下のその他のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="ceb9f-147">**アラート タイトル**- ルールによってトリガーされたアラートで表示されるタイトル</span><span class="sxs-lookup"><span data-stu-id="ceb9f-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="ceb9f-148">**重大度**—ルールによって識別されるコンポーネントまたはアクティビティの潜在的なリスク</span><span class="sxs-lookup"><span data-stu-id="ceb9f-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="ceb9f-149">**Category**—ルールによって識別される脅威コンポーネントまたはアクティビティ</span><span class="sxs-lookup"><span data-stu-id="ceb9f-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="ceb9f-150">**MITRE ATT&CK** の手法 (CK フレームワークの [MITRE ATT](https://attack.mitre.org/)に記載されているルールによって識別される 1 つ以上の攻撃&です。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="ceb9f-151">このセクションは、マルウェア、ランサムウェア、疑わしいアクティビティ、望ましくないソフトウェアなど、特定のアラート カテゴリでは非表示になっています。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="ceb9f-152">**Description**—ルールによって識別されるコンポーネントまたはアクティビティの詳細</span><span class="sxs-lookup"><span data-stu-id="ceb9f-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="ceb9f-153">**推奨されるアクション**—応答者がアラートに応答して実行する可能性がある追加のアクション</span><span class="sxs-lookup"><span data-stu-id="ceb9f-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="ceb9f-154">ルールの頻度</span><span class="sxs-lookup"><span data-stu-id="ceb9f-154">Rule frequency</span></span>
<span data-ttu-id="ceb9f-155">新しいルールを保存すると、過去 30 日間のデータの一致が実行され、チェックされます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-155">When you save a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="ceb9f-156">その後、ルールは一定の間隔で再び実行され、選択した頻度に基づいてルックバック期間が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="ceb9f-157">**24 時間ごとに** 実行され、過去 30 日間のデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="ceb9f-158">**12 時間ごとに** 実行され、過去 24 時間のデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="ceb9f-159">**3 時間ごとに** 実行され、過去 6 時間のデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="ceb9f-160">**1 時間** ごとに 1 時間ごとに実行され、過去 2 時間のデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="ceb9f-161">ルールを編集すると、設定した頻度に従ってスケジュールされた次の実行時に適用された変更と一緒に実行されます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-161">When you edit a rule, it will run with the applied changes in the next run time scheduled according to the frequency you set.</span></span>



>[!TIP]
> <span data-ttu-id="ceb9f-162">クエリのタイム フィルターとルックバック期間を一致します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-162">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="ceb9f-163">ルックバック期間外の結果は無視されます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-163">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="ceb9f-164">検出を監視する頻度に一致する頻度を選択します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-164">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="ceb9f-165">通知に応答する組織の容量を検討します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-165">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="ceb9f-166">3. 影響を受け取ったエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-166">3. Choose the impacted entities.</span></span>
<span data-ttu-id="ceb9f-167">影響を受ける主なエンティティまたは影響を受けるエンティティを検索するクエリ結果の列を特定します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-167">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="ceb9f-168">たとえば、クエリが送信者 (または) アドレスと受信者 `SenderFromAddress` `SenderMailFromAddress` ( ) アドレスを `RecipientEmailAddress` 返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-168">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="ceb9f-169">これらの列の中で、影響を受ける主なエンティティを表す列を特定すると、サービスは関連するアラートの集計、インシデントの関連付け、およびターゲット応答アクションの集計に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-169">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="ceb9f-170">エンティティの種類 (メールボックス、ユーザー、またはデバイス) ごとに 1 つの列のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-170">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="ceb9f-171">クエリによって返されない列は選択できません。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-171">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="ceb9f-172">4. アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-172">4. Specify actions.</span></span>
<span data-ttu-id="ceb9f-173">カスタム検出ルールは、クエリによって返されるデバイス、ファイル、またはユーザーに対して自動的にアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-173">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="ceb9f-174">デバイスでのアクション</span><span class="sxs-lookup"><span data-stu-id="ceb9f-174">Actions on devices</span></span>
<span data-ttu-id="ceb9f-175">これらのアクションは、クエリ結果の列 `DeviceId` のデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-175">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="ceb9f-176">**デバイスの分離**—Microsoft Defender for Endpoint を使用して完全なネットワーク分離を適用し、デバイスが任意のアプリケーションまたはサービスに接続できません。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-176">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="ceb9f-177">Microsoft Defender for Endpoint マシンの分離の詳細</span><span class="sxs-lookup"><span data-stu-id="ceb9f-177">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="ceb9f-178">**調査パッケージの収集**— ZIP ファイル内のデバイス情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-178">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="ceb9f-179">Microsoft Defender for Endpoint 調査パッケージの詳細</span><span class="sxs-lookup"><span data-stu-id="ceb9f-179">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="ceb9f-180">**ウイルス対策スキャンの実行**-デバイスでWindows Defenderウイルス対策スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-180">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="ceb9f-181">**調査を開始** する -デバイス [で自動調査](m365d-autoir.md) を開始する</span><span class="sxs-lookup"><span data-stu-id="ceb9f-181">**Initiate investigation**—initiates an [automated investigation](m365d-autoir.md) on the device</span></span>
- <span data-ttu-id="ceb9f-182">**アプリの実行を制限** する :Microsoft 発行の証明書で署名されたファイルのみを実行できるデバイスの制限を設定します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-182">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="ceb9f-183">Microsoft Defender for Endpoint でのアプリ制限の詳細</span><span class="sxs-lookup"><span data-stu-id="ceb9f-183">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="ceb9f-184">ファイルに対するアクション</span><span class="sxs-lookup"><span data-stu-id="ceb9f-184">Actions on files</span></span>
<span data-ttu-id="ceb9f-185">選択すると、クエリ結果の 、または列のファイルに対して [ファイルの検疫] `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` アクションを適用できます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-185">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="ceb9f-186">このアクションでは、ファイルを現在の場所から削除し、コピーを検疫に入れる。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-186">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="ceb9f-187">ユーザーに対するアクション</span><span class="sxs-lookup"><span data-stu-id="ceb9f-187">Actions on users</span></span>
<span data-ttu-id="ceb9f-188">選択すると、クエリ結果の **、、** または列のユーザーに対してユーザーに対して [侵害されたユーザーとしてマーク] `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` アクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-188">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="ceb9f-189">このアクションは、Azure Active Directory でユーザーのリスク レベルを "高" に設定し、対応する ID 保護 [ポリシーをトリガーします](/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-189">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="ceb9f-190">カスタム検出ルールの許可またはブロックアクションは、Microsoft 365 Defender では現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-190">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="ceb9f-191">5. ルールスコープを設定します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-191">5. Set the rule scope.</span></span>
<span data-ttu-id="ceb9f-192">スコープを設定して、ルールの対象となるデバイスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-192">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="ceb9f-193">このスコープは、デバイスをチェックするルールに影響を与え、メールボックスとユーザー アカウントまたは ID のみをチェックするルールには影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-193">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="ceb9f-194">スコープを設定する場合は、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-194">When setting the scope, you can select:</span></span>

- <span data-ttu-id="ceb9f-195">すべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="ceb9f-195">All devices</span></span>
- <span data-ttu-id="ceb9f-196">特定のデバイス グループ</span><span class="sxs-lookup"><span data-stu-id="ceb9f-196">Specific device groups</span></span>

<span data-ttu-id="ceb9f-197">スコープ内のデバイスからのデータだけがクエリされます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-197">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="ceb9f-198">また、これらのデバイスでのみアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-198">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="ceb9f-199">6. ルールを確認して有効にする。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-199">6. Review and turn on the rule.</span></span>
<span data-ttu-id="ceb9f-200">ルールを確認した後、[作成] **を選択して** 保存します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-200">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="ceb9f-201">カスタム検出ルールが直ちに実行されます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-201">The custom detection rule immediately runs.</span></span> <span data-ttu-id="ceb9f-202">構成された頻度に基づいて再び実行され、一致を確認し、アラートを生成し、応答アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-202">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>


>[!Important] 
><span data-ttu-id="ceb9f-203">カスタム検出は、効率と有効性を定期的に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-203">Custom detections should be regularly reviewed for efficiency and effectiveness.</span></span> <span data-ttu-id="ceb9f-204">真のアラートをトリガーする検出を作成するには、「既存のカスタム検出ルールの管理」の手順に従って、既存のカスタム検出を確認する時間 [を取ってください](#manage-existing-custom-detection-rules)。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-204">To make sure you are creating detections that trigger true alerts, take time to review your existing custom detections by following the steps in [Manage existing custom detection rules](#manage-existing-custom-detection-rules).</span></span> <br>  
<span data-ttu-id="ceb9f-205">カスタム検出の広さまたは特定性を制御し、カスタム検出によって生成された誤った通知がルールの特定のパラメーターを変更する必要を示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-205">You maintain control over the broadness or specificity of your custom detections so any false alerts generated by custom detections might indicate a need to modify certain parameters of the rules.</span></span>


## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="ceb9f-206">既存のカスタム検出ルールの管理</span><span class="sxs-lookup"><span data-stu-id="ceb9f-206">Manage existing custom detection rules</span></span>
<span data-ttu-id="ceb9f-207">既存のカスタム検出ルールの一覧を表示し、以前の実行を確認し、トリガーしたアラートを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-207">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="ceb9f-208">必要に応じてルールを実行して変更できます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-208">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="ceb9f-209">既存のルールの表示</span><span class="sxs-lookup"><span data-stu-id="ceb9f-209">View existing rules</span></span>

<span data-ttu-id="ceb9f-210">既存のすべてのカスタム検出ルールを表示するには、[ハンティングカスタム検出  >  **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-210">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="ceb9f-211">ページには、次の実行情報を含むすべてのルールが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-211">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="ceb9f-212">**Last run**—クエリの一致を確認し、アラートを生成するルールが最後に実行された場合</span><span class="sxs-lookup"><span data-stu-id="ceb9f-212">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="ceb9f-213">**最終実行の状態**:ルールが正常に実行されたかどうか</span><span class="sxs-lookup"><span data-stu-id="ceb9f-213">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="ceb9f-214">**次の実行**— 次のスケジュールされた実行</span><span class="sxs-lookup"><span data-stu-id="ceb9f-214">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="ceb9f-215">**Status**—ルールが有効または無効になっているかどうか</span><span class="sxs-lookup"><span data-stu-id="ceb9f-215">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="ceb9f-216">ルールの詳細の表示、ルールの変更、およびルールの実行</span><span class="sxs-lookup"><span data-stu-id="ceb9f-216">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="ceb9f-217">カスタム検出ルールに関する包括的な情報を表示するには、[ハンティング カスタム検出] に移動し、ルールの  >  名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-217">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="ceb9f-218">その後、ルールの実行状態とスコープに関する情報を含む、ルールに関する一般的な情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-218">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="ceb9f-219">このページには、トリガーされたアラートとアクションの一覧も表示されます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-219">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="ceb9f-220">![カスタム検出ルールの詳細ページ](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="ceb9f-220">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="ceb9f-221">*カスタム検出ルールの詳細*</span><span class="sxs-lookup"><span data-stu-id="ceb9f-221">*Custom detection rule details*</span></span>

<span data-ttu-id="ceb9f-222">また、このページからルールに対して次のアクションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-222">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="ceb9f-223">**Run**—ルールを直ちに実行します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-223">**Run**—run the rule immediately.</span></span> <span data-ttu-id="ceb9f-224">これにより、次の実行の間隔もリセットされます。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-224">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="ceb9f-225">**Edit**—クエリを変更せずにルールを変更する</span><span class="sxs-lookup"><span data-stu-id="ceb9f-225">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="ceb9f-226">**クエリの変更**—高度な検索でクエリを編集する</span><span class="sxs-lookup"><span data-stu-id="ceb9f-226">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="ceb9f-227">**有効にする**  / **無効にする**-ルールを有効にするか、ルールの実行を停止する</span><span class="sxs-lookup"><span data-stu-id="ceb9f-227">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="ceb9f-228">**Delete**—ルールをオフにし、削除する</span><span class="sxs-lookup"><span data-stu-id="ceb9f-228">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="ceb9f-229">トリガーされたアラートの表示と管理</span><span class="sxs-lookup"><span data-stu-id="ceb9f-229">View and manage triggered alerts</span></span>

<span data-ttu-id="ceb9f-230">ルールの詳細画面 (**ハンティング** カスタム検出 [ルール名]) で、[トリガーされたアラート] に移動し、ルールに一致して生成されたアラート  >    >  を一覧表示します。 </span><span class="sxs-lookup"><span data-stu-id="ceb9f-230">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="ceb9f-231">アラートを選択して、アラートに関する詳細情報を表示し、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-231">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="ceb9f-232">状態と分類を設定してアラートを管理する (true または false アラート)</span><span class="sxs-lookup"><span data-stu-id="ceb9f-232">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="ceb9f-233">アラートをインシデントにリンクする</span><span class="sxs-lookup"><span data-stu-id="ceb9f-233">Link the alert to an incident</span></span>
- <span data-ttu-id="ceb9f-234">高度な検索でアラートをトリガーしたクエリを実行する</span><span class="sxs-lookup"><span data-stu-id="ceb9f-234">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="ceb9f-235">アクションを確認する</span><span class="sxs-lookup"><span data-stu-id="ceb9f-235">Review actions</span></span>
<span data-ttu-id="ceb9f-236">ルールの詳細画面 (**ハンティング** カスタム検出 [ルール名]) で、[トリガーされたアクション] に移動し、ルールとの一致に基づいて実行されるアクションを  >    >  一覧表示します。 </span><span class="sxs-lookup"><span data-stu-id="ceb9f-236">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="ceb9f-237">テーブル内のアイテムに関する情報をすばやく表示し、アクションを実行するには、表の左側にある [&#10003;] の選択列を使用します。</span><span class="sxs-lookup"><span data-stu-id="ceb9f-237">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="see-also"></a><span data-ttu-id="ceb9f-238">関連項目</span><span class="sxs-lookup"><span data-stu-id="ceb9f-238">See also</span></span>
- [<span data-ttu-id="ceb9f-239">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="ceb9f-239">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="ceb9f-240">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="ceb9f-240">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ceb9f-241">高度な捜索のクエリ言語について学習する</span><span class="sxs-lookup"><span data-stu-id="ceb9f-241">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ceb9f-242">Microsoft Defender for Endpoint から高度なハンティング クエリを移行する</span><span class="sxs-lookup"><span data-stu-id="ceb9f-242">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
