---
title: Microsoft 365 Defender でカスタム検出ルールを作成および管理する
description: 高度な検索クエリに基づいてカスタム検出ルールを作成および管理する方法について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、カスタム検出、ルール、スキーマ、kusto、Microsoft 365、Microsoft Threat Protection、RBAC、アクセス許可、Microsoft Defender ATP
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
ms.openlocfilehash: d58292f658446259bfab5b1b55c8b462d081421c
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080625"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="3bb65-104">カスタム検出ルールを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="3bb65-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3bb65-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3bb65-105">**Applies to:**</span></span>
- <span data-ttu-id="3bb65-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3bb65-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3bb65-107">カスタム検出ルールは、高度なハンティング クエリを使用して設計および [調整できるルール](advanced-hunting-overview.md) です。</span><span class="sxs-lookup"><span data-stu-id="3bb65-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="3bb65-108">これらのルールを使用すると、侵害の疑いのあるアクティビティやエンドポイントの構成ミスなど、さまざまなイベントやシステム状態を事前に監視できます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="3bb65-109">一致する場合は常に、一定の間隔で実行し、アラートを生成し、対応アクションを実行する設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="3bb65-110">カスタム検出を管理するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="3bb65-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="3bb65-111">カスタム検出を管理するには、次の役割のいずれかを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bb65-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="3bb65-112">**セキュリティ管理者**— この [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) ロールを持つユーザーは、Microsoft 365 セキュリティ センターや他のポータルやサービスでセキュリティ設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-112">**Security administrator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="3bb65-113">**セキュリティ オペレーター**— この [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) ロールを持つユーザーは、アラートを管理し、Microsoft 365 セキュリティ センターのすべての情報を含む、セキュリティ関連の機能へのグローバルな読み取り専用アクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="3bb65-113">**Security operator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="3bb65-114">この役割は、Microsoft Defender for Endpoint で役割ベースのアクセス制御 (RBAC) がオフになっている場合にのみ、カスタム検出を管理するのに十分です。</span><span class="sxs-lookup"><span data-stu-id="3bb65-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="3bb65-115">RBAC を構成している場合は、エンドポイント用 Defender のセキュリティ設定 **の** 管理アクセス許可も必要です。</span><span class="sxs-lookup"><span data-stu-id="3bb65-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="3bb65-116">必要なアクセス許可を管理するには、グローバル **管理者は次の方法を実行** できます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="3bb65-117">ロール セキュリティ **管理者の下で**[、Microsoft 365](https://admin.microsoft.com/)管理センターでセキュリティ管理者またはセキュリティオペレーター **の役割**  >  **を割り当てます**。</span><span class="sxs-lookup"><span data-stu-id="3bb65-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="3bb65-118">Microsoft Defender セキュリティ センターの [設定のアクセス許可の役割] で [、Microsoft Defender](https://securitycenter.windows.com/) for Endpoint の RBAC **設定**  >  **を確認**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="3bb65-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="3bb65-119">対応する役割を選択して、セキュリティ設定の **管理アクセス許可を割り当** てる。</span><span class="sxs-lookup"><span data-stu-id="3bb65-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="3bb65-120">カスタム検出を管理するには、RBAC が有効になっている場合、セキュリティオペレーターは Microsoft Defender for Endpoint のセキュリティ設定の管理アクセス許可を必要とします。 </span><span class="sxs-lookup"><span data-stu-id="3bb65-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="3bb65-121">カスタム検出ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="3bb65-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="3bb65-122">1. クエリを準備します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-122">1. Prepare the query.</span></span>

<span data-ttu-id="3bb65-123">Microsoft 365 セキュリティ センターで、[高度な検索] に移動 **し、既存** のクエリを選択するか、新しいクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="3bb65-124">新しいクエリを使用する場合は、クエリを実行してエラーを特定し、考えられる結果を把握します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="3bb65-125">サービスが返すアラートの数が多すぎるのを防ぐため、各ルールは、実行されるたびに生成されるアラートを 100 件に制限しています。</span><span class="sxs-lookup"><span data-stu-id="3bb65-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="3bb65-126">ルールを作成する前に、通常の毎日のアクティビティに対する警告を回避するためにクエリを調整してください。</span><span class="sxs-lookup"><span data-stu-id="3bb65-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="3bb65-127">クエリ結果に必要な列</span><span class="sxs-lookup"><span data-stu-id="3bb65-127">Required columns in the query results</span></span>
<span data-ttu-id="3bb65-128">カスタム検出ルールを作成するには、クエリが次の列を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bb65-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="3bb65-129">`Timestamp`— 生成されたアラートのタイムスタンプを設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="3bb65-130">`ReportId`—元のレコードの参照を有効にする</span><span class="sxs-lookup"><span data-stu-id="3bb65-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="3bb65-131">特定のデバイス、ユーザー、またはメールボックスを識別する次のいずれかの列:</span><span class="sxs-lookup"><span data-stu-id="3bb65-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="3bb65-132">`SenderFromAddress` (エンベロープ送信者またはReturn-Pathアドレス)</span><span class="sxs-lookup"><span data-stu-id="3bb65-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="3bb65-133">`SenderMailFromAddress` (メール クライアントによって表示される送信者アドレス)</span><span class="sxs-lookup"><span data-stu-id="3bb65-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="3bb65-134">新しいテーブルが高度な検索スキーマに追加された場合、追加のエンティティ [のサポートが追加されます](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="3bb65-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="3bb65-135">結果のカスタマイズや集計に演算子を使用しないクエリなどの単純なクエリは、通常、これらの一般的な列 `project` `summarize` を返します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="3bb65-136">より複雑なクエリがこれらの列を返すのを確実にするためのさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="3bb65-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="3bb65-137">たとえば、次のような列の下のエンティティで集計してカウントする場合でも、一意の各イベントが関係する最新のイベントから取得して取得 `DeviceId` `Timestamp` `ReportId` できます `DeviceId` 。</span><span class="sxs-lookup"><span data-stu-id="3bb65-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="3bb65-138">次のサンプル クエリでは、ウイルス対策が検出された一意のデバイス ( ) の数をカウントし、このカウントを使用して、5 つを超える検出を持つデバイスのみを `DeviceId` 検索します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="3bb65-139">最新の関数と `Timestamp` 対応する関数を返す場合は `ReportId` 、 `summarize` 演算子を使用 `arg_max` します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="3bb65-140">クエリのパフォーマンスを向上するには、ルールの実行頻度に一致する時間フィルターを設定します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="3bb65-141">実行頻度が最も少ないのは _24_ 時間ごとに行われるので、過去 1 日のフィルター処理ではすべての新しいデータが処理されます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="3bb65-142">2. 新しいルールを作成し、アラートの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="3bb65-143">クエリ エディターでクエリを使用して、[検出ルールの作成] を選択 **し、次** のアラートの詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="3bb65-144">**検出名**— 検出ルールの名前</span><span class="sxs-lookup"><span data-stu-id="3bb65-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="3bb65-145">**頻度**— クエリを実行してアクションを実行する間隔。</span><span class="sxs-lookup"><span data-stu-id="3bb65-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="3bb65-146">以下の追加のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bb65-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="3bb65-147">**アラートタイトル**- ルールによってトリガーされたアラートと一緒に表示されるタイトル</span><span class="sxs-lookup"><span data-stu-id="3bb65-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="3bb65-148">**重大度 —** ルールによって識別されるコンポーネントまたはアクティビティの潜在的なリスク</span><span class="sxs-lookup"><span data-stu-id="3bb65-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="3bb65-149">**カテゴリ**— ルールによって識別される脅威コンポーネントまたはアクティビティ</span><span class="sxs-lookup"><span data-stu-id="3bb65-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="3bb65-150">**MITRE ATT&CK** の手法 [—MITRE ATT](https://attack.mitre.org/)と CK フレームワークに記載されているルールによって識別される 1 つ以上の攻撃&手法です。</span><span class="sxs-lookup"><span data-stu-id="3bb65-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="3bb65-151">このセクションは、マルウェア、ランサムウェア、疑わしいアクティビティ、望ましくないソフトウェアなど、特定のアラート カテゴリでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="3bb65-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="3bb65-152">**説明**— ルールによって識別されるコンポーネントまたはアクティビティに関する詳細</span><span class="sxs-lookup"><span data-stu-id="3bb65-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="3bb65-153">**推奨されるアクション**— アラートに応答してレスポンダーが実行する可能性がある追加のアクション</span><span class="sxs-lookup"><span data-stu-id="3bb65-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="3bb65-154">ルールの頻度</span><span class="sxs-lookup"><span data-stu-id="3bb65-154">Rule frequency</span></span>
<span data-ttu-id="3bb65-155">新しいルールを保存または編集すると、そのルールが実行され、過去 30 日間のデータの一致が確認されます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="3bb65-156">その後、ルールは一定の間隔で再び実行され、選択した頻度に基づいてルックバック期間が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="3bb65-157">**24 時間** ごとに -24 時間ごとに実行され、過去 30 日間のデータをチェックします</span><span class="sxs-lookup"><span data-stu-id="3bb65-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="3bb65-158">**12 時間ごとに**-12 時間ごとに実行され、過去 24 時間のデータをチェックします</span><span class="sxs-lookup"><span data-stu-id="3bb65-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="3bb65-159">**3 時間ごとに**-3 時間ごとに実行され、過去 6 時間のデータをチェックします</span><span class="sxs-lookup"><span data-stu-id="3bb65-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="3bb65-160">**1 時間** ごとに実行され、過去 2 時間のデータをチェックします。</span><span class="sxs-lookup"><span data-stu-id="3bb65-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="3bb65-161">クエリ内の時間フィルターを、ルックバック期間と一致します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="3bb65-162">ルックバック期間外の結果は無視されます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="3bb65-163">検出を監視する頻度と一致する頻度を選択します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="3bb65-164">アラートに対応する組織の能力を考慮します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="3bb65-165">3. 影響を受け取るエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="3bb65-166">影響を受ける主なエンティティまたは影響を受けるエンティティを検索すると予想されるクエリ結果の列を特定します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="3bb65-167">たとえば、クエリは送信者 (または) アドレスと受信者 ( ) アドレス `SenderFromAddress` `SenderMailFromAddress` `RecipientEmailAddress` を返します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="3bb65-168">影響を受ける主なエンティティを表す列を特定すると、サービスが関連するアラートの集計、インシデントの関連付け、および対象の対応アクションを行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="3bb65-169">エンティティの種類 (メールボックス、ユーザー、またはデバイス) ごとに 1 つの列のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="3bb65-170">クエリによって返されない列は選択できません。</span><span class="sxs-lookup"><span data-stu-id="3bb65-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="3bb65-171">4. アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-171">4. Specify actions.</span></span>
<span data-ttu-id="3bb65-172">カスタム検出ルールは、クエリによって返されるデバイス、ファイル、またはユーザーに対して自動的にアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="3bb65-173">デバイスでのアクション</span><span class="sxs-lookup"><span data-stu-id="3bb65-173">Actions on devices</span></span>
<span data-ttu-id="3bb65-174">これらのアクションは、クエリ結果の列にある `DeviceId` デバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="3bb65-175">**デバイスの分離**— Microsoft Defender for Endpoint を使用して完全なネットワーク分離を適用し、デバイスがアプリケーションまたはサービスに接続しなくします。</span><span class="sxs-lookup"><span data-stu-id="3bb65-175">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="3bb65-176">Microsoft Defender for Endpoint コンピューターの分離の詳細</span><span class="sxs-lookup"><span data-stu-id="3bb65-176">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="3bb65-177">**調査パッケージの収集**- ZIP ファイル内のデバイス情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="3bb65-178">Microsoft Defender for Endpoint 調査パッケージの詳細</span><span class="sxs-lookup"><span data-stu-id="3bb65-178">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="3bb65-179">**ウイルス対策スキャンの** 実行 - デバイスでフル Windows Defenderウイルス対策スキャンを実行します</span><span class="sxs-lookup"><span data-stu-id="3bb65-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="3bb65-180">**調査の開始**- デバイスで [自動調査](mtp-autoir.md) を開始する</span><span class="sxs-lookup"><span data-stu-id="3bb65-180">**Initiate investigation**—initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="3bb65-181">**アプリの実行を** 制限する - Microsoft が発行する証明書で署名されたファイルのみを実行できるデバイスの制限を設定します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="3bb65-182">Microsoft Defender for Endpoint でのアプリの制限について詳しくは、次をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3bb65-182">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="3bb65-183">ファイルに対するアクション</span><span class="sxs-lookup"><span data-stu-id="3bb65-183">Actions on files</span></span>
<span data-ttu-id="3bb65-184">選択すると、クエリ結果の [,  , ] () 列にあるファイルに検疫ファイルアクション `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` を適用できます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="3bb65-185">この操作により、ファイルが現在の場所から削除され、コピーが検疫されます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="3bb65-186">ユーザーに対するアクション</span><span class="sxs-lookup"><span data-stu-id="3bb65-186">Actions on users</span></span>
<span data-ttu-id="3bb65-187">このオプションを選択すると、クエリ **結果** の [, ] 列にあるユーザーに対して [侵害されたユーザーとしてマークする `AccountObjectId` ] `InitiatingProcessAccountObjectId` `RecipientObjectId` アクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="3bb65-188">このアクションは、Azure Active Directory でユーザーのリスク レベルを "高" に設定し、対応する ID 保護ポリシー [をトリガーします](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="3bb65-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="3bb65-189">カスタム検出ルールの許可またはブロックのアクションは、Microsoft 365 Defender では現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3bb65-189">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="3bb65-190">5. ルールの範囲を設定します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-190">5. Set the rule scope.</span></span>
<span data-ttu-id="3bb65-191">ルールの対象となるデバイスを指定するスコープを設定します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="3bb65-192">このスコープは、デバイスをチェックするルールに影響し、メールボックスとユーザー アカウントまたは ID のみをチェックするルールには影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="3bb65-193">スコープを設定する場合は、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="3bb65-194">すべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="3bb65-194">All devices</span></span>
- <span data-ttu-id="3bb65-195">特定のデバイス グループ</span><span class="sxs-lookup"><span data-stu-id="3bb65-195">Specific device groups</span></span>

<span data-ttu-id="3bb65-196">範囲内のデバイスからのデータのみを照会します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="3bb65-197">また、これらのデバイスでのみアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="3bb65-198">6. ルールを確認して有効にする。</span><span class="sxs-lookup"><span data-stu-id="3bb65-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="3bb65-199">ルールを確認した後、[作成] を **選択して** 保存します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="3bb65-200">カスタム検出ルールが直ちに実行されます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="3bb65-201">一致を確認し、アラートを生成し、対応アクションを実行するように構成された頻度に基づいて、再び実行されます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="3bb65-202">既存のカスタム検出ルールを管理する</span><span class="sxs-lookup"><span data-stu-id="3bb65-202">Manage existing custom detection rules</span></span>
<span data-ttu-id="3bb65-203">既存のカスタム検出ルールの一覧の表示、以前の実行の確認、トリガーされたアラートの確認を行えます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-203">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="3bb65-204">必要に応じてルールを実行して変更できます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-204">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="3bb65-205">既存のルールを表示する</span><span class="sxs-lookup"><span data-stu-id="3bb65-205">View existing rules</span></span>

<span data-ttu-id="3bb65-206">既存のすべてのカスタム検出ルールを表示するには、[**ハン** ティング カスタム検出  >  **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="3bb65-206">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="3bb65-207">このページには、次の実行情報を含むすべてのルールが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-207">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="3bb65-208">**最後の実行**- クエリの一致をチェックしてアラートを生成するルールが最後に実行された場合</span><span class="sxs-lookup"><span data-stu-id="3bb65-208">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="3bb65-209">**最終実行状態**— ルールが正常に実行されたかどうか</span><span class="sxs-lookup"><span data-stu-id="3bb65-209">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="3bb65-210">**次の実行**— 次にスケジュールされた実行</span><span class="sxs-lookup"><span data-stu-id="3bb65-210">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="3bb65-211">**状態**- ルールが有効または無効になっているかどうか</span><span class="sxs-lookup"><span data-stu-id="3bb65-211">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="3bb65-212">ルールの詳細の表示、ルールの変更、およびルールの実行</span><span class="sxs-lookup"><span data-stu-id="3bb65-212">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="3bb65-213">カスタム検出ルールに関する包括的な情報を表示するには、[**検索** カスタム検出] に移動し、ルール  >  の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-213">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="3bb65-214">その後、ルールに関する一般的な情報 (実行状態や範囲に関する情報など) を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-214">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="3bb65-215">このページには、トリガーされたアラートとアクションの一覧も表示されます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-215">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="3bb65-216">![カスタム検出ルールの詳細ページ](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="3bb65-216">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="3bb65-217">*カスタム検出ルールの詳細*</span><span class="sxs-lookup"><span data-stu-id="3bb65-217">*Custom detection rule details*</span></span>

<span data-ttu-id="3bb65-218">このページからルールに対して次のアクションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-218">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="3bb65-219">**Run**-run the rule immediately.</span><span class="sxs-lookup"><span data-stu-id="3bb65-219">**Run**—run the rule immediately.</span></span> <span data-ttu-id="3bb65-220">これにより、次の実行の間隔もリセットされます。</span><span class="sxs-lookup"><span data-stu-id="3bb65-220">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="3bb65-221">**Edit**- クエリを変更せずにルールを変更する</span><span class="sxs-lookup"><span data-stu-id="3bb65-221">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="3bb65-222">**クエリの変更**- 高度な検索でクエリを編集する</span><span class="sxs-lookup"><span data-stu-id="3bb65-222">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="3bb65-223">**オンにする**  / **無効にする**- ルールを有効にするか、ルールの実行を停止する</span><span class="sxs-lookup"><span data-stu-id="3bb65-223">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="3bb65-224">**削除**- ルールをオフにし、削除する</span><span class="sxs-lookup"><span data-stu-id="3bb65-224">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="3bb65-225">トリガーされたアラートの表示と管理</span><span class="sxs-lookup"><span data-stu-id="3bb65-225">View and manage triggered alerts</span></span>

<span data-ttu-id="3bb65-226">In the rule details screen (**Hunting**  >  **Custom detections**  >  **[Rule name]**), go to **Triggered alerts,** which lists the alerts generated by matches to the rule.</span><span class="sxs-lookup"><span data-stu-id="3bb65-226">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="3bb65-227">アラートを選択してアラートに関する詳細情報を表示し、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-227">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="3bb65-228">アラートの状態と分類を設定してアラートを管理する (true または false のアラート)</span><span class="sxs-lookup"><span data-stu-id="3bb65-228">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="3bb65-229">アラートをインシデントにリンクする</span><span class="sxs-lookup"><span data-stu-id="3bb65-229">Link the alert to an incident</span></span>
- <span data-ttu-id="3bb65-230">高度な検索でアラートをトリガーしたクエリを実行する</span><span class="sxs-lookup"><span data-stu-id="3bb65-230">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="3bb65-231">アクションを確認する</span><span class="sxs-lookup"><span data-stu-id="3bb65-231">Review actions</span></span>
<span data-ttu-id="3bb65-232">In the rule details screen (**Hunting**  >  **Custom detections**  >  **[Rule name]**), go to **Triggered actions,** which lists the actions taken based on matches to the rule.</span><span class="sxs-lookup"><span data-stu-id="3bb65-232">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="3bb65-233">テーブル内のアイテムに関する情報をすばやく表示してアクションを実行するには、表の左側にある選択列 [&#10003;] を使用します。</span><span class="sxs-lookup"><span data-stu-id="3bb65-233">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="see-also"></a><span data-ttu-id="3bb65-234">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bb65-234">See also</span></span>
- [<span data-ttu-id="3bb65-235">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="3bb65-235">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="3bb65-236">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="3bb65-236">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3bb65-237">高度な捜索のクエリ言語について学習する</span><span class="sxs-lookup"><span data-stu-id="3bb65-237">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3bb65-238">Microsoft Defender for Endpoint から高度な検索クエリを移行する</span><span class="sxs-lookup"><span data-stu-id="3bb65-238">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mdatp.md)
