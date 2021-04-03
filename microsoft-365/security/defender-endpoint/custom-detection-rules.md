---
title: Microsoft Defender ATP でカスタム検出ルールを作成する
ms.reviewer: ''
description: 高度な検索クエリに基づいてカスタム検出ルールを作成する方法について説明します。
keywords: カスタム検出、作成、管理、アラート、編集、オンデマンドでの実行、頻度、間隔、検出ルール、高度な狩猟、ハント、クエリ、応答アクション、mdatp、microsoft Defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 15dec5396a5ba95fe3ec7af5f9a72bbf15e07140
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500497"
---
# <a name="create-custom-detection-rules"></a><span data-ttu-id="b53ec-104">検出ルールの作成</span><span class="sxs-lookup"><span data-stu-id="b53ec-104">Create custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b53ec-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b53ec-105">**Applies to:**</span></span>
- [<span data-ttu-id="b53ec-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b53ec-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b53ec-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b53ec-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b53ec-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="b53ec-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b53ec-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="b53ec-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="b53ec-110">高度な検索クエリから[](advanced-hunting-overview.md)構築されたカスタム検出ルールを使用すると、侵害アクティビティの疑いやデバイスの構成ミスなど、さまざまなイベントやシステム状態を積極的に監視できます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-110">Custom detection rules built from [advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="b53ec-111">一定の間隔で実行し、アラートを生成し、一致するたびに応答アクションを実行する設定できます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="b53ec-112">新しいカスタム検出ルールを作成する方法については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b53ec-112">Read this article to learn how to create new custom detection rules.</span></span> <span data-ttu-id="b53ec-113">または [、既存のルールの表示と管理を参照してください](custom-detections-manage.md)。</span><span class="sxs-lookup"><span data-stu-id="b53ec-113">Or [see viewing and managing existing rules](custom-detections-manage.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b53ec-114">カスタム検出を作成または管理するには、 [役割に](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) セキュリティ設定の管理権限 **が必要** です。</span><span class="sxs-lookup"><span data-stu-id="b53ec-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="1-prepare-the-query"></a><span data-ttu-id="b53ec-115">1. クエリを準備します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-115">1. Prepare the query.</span></span>

<span data-ttu-id="b53ec-116">Microsoft Defender セキュリティ センターで、[高度な検索] **に** 移動し、既存のクエリを選択するか、新しいクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-116">In Microsoft Defender Security Center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="b53ec-117">新しいクエリを使用する場合は、クエリを実行してエラーを特定し、考えられる結果を理解します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-117">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="b53ec-118">サービスがあまりにも多くのアラートを返さなすぎ防止するために、各ルールは、実行されるたびに 100 件のアラートのみを生成するに制限されます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-118">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="b53ec-119">ルールを作成する前に、クエリを調整して、通常の毎日のアクティビティに対する警告を回避してください。</span><span class="sxs-lookup"><span data-stu-id="b53ec-119">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>

### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="b53ec-120">クエリ結果に必要な列</span><span class="sxs-lookup"><span data-stu-id="b53ec-120">Required columns in the query results</span></span>

<span data-ttu-id="b53ec-121">カスタム検出ルールにクエリを使用するには、次の列を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b53ec-121">To use a query for a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- `DeviceId`
- `ReportId`

<span data-ttu-id="b53ec-122">単純なクエリ (結果をカスタマイズまたは集計するために or 演算子を使用しないクエリなど) は、通常、これらの一般的な `project` `summarize` 列を返します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-122">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="b53ec-123">より複雑なクエリがこれらの列を返すには、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="b53ec-123">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="b53ec-124">たとえば、集計とカウントを行う場合は、各デバイスに関連する最新のイベントから取得して取得 `DeviceId` `Timestamp` `ReportId` できます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-124">For example, if you prefer to aggregate and count by `DeviceId`, you can still return `Timestamp` and `ReportId` by getting them from the most recent event involving each device.</span></span>

<span data-ttu-id="b53ec-125">以下のサンプル クエリは、ウイルス対策検出を含む一意のデバイス ( ) の数をカウントし、これを使用して 5 つを超える検出を持つデバイス `DeviceId` のみを検索します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-125">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this to find only those devices with more than five detections.</span></span> <span data-ttu-id="b53ec-126">最新の値と `Timestamp` 対応する値を取得 `ReportId` するには、関数と `summarize` 一緒に演算子を使用 `arg_max` します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-126">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="b53ec-127">クエリのパフォーマンスを向上するには、ルールの目的の実行頻度に一致する時間フィルターを設定します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-127">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="b53ec-128">実行頻度が最も少ないのは 24 時間ごとに行われるので、過去 1 日のフィルター処理では、すべての新しいデータがカバーされます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-128">Since the least frequent run is every 24 hours, filtering for the past day will cover all new data.</span></span>

## <a name="2-create-a-new-rule-and-provide-alert-details"></a><span data-ttu-id="b53ec-129">2. 新しいルールを作成し、アラートの詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-129">2. Create a new rule and provide alert details.</span></span>

<span data-ttu-id="b53ec-130">クエリ エディターでクエリを使用して、[検出ルールの作成] **を選択し** 、次のアラートの詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-130">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="b53ec-131">**検出名**—検出ルールの名前</span><span class="sxs-lookup"><span data-stu-id="b53ec-131">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="b53ec-132">**頻度**—クエリを実行してアクションを実行する間隔。</span><span class="sxs-lookup"><span data-stu-id="b53ec-132">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="b53ec-133">以下のその他のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b53ec-133">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="b53ec-134">**アラート タイトル**- ルールによってトリガーされたアラートで表示されるタイトル</span><span class="sxs-lookup"><span data-stu-id="b53ec-134">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="b53ec-135">**重大度 —** ルールによって識別されるコンポーネントまたはアクティビティの潜在的なリスク。</span><span class="sxs-lookup"><span data-stu-id="b53ec-135">**Severity**—potential risk of the component or activity identified by the rule.</span></span> [<span data-ttu-id="b53ec-136">アラートの重大度について読む</span><span class="sxs-lookup"><span data-stu-id="b53ec-136">Read about alert severities</span></span>](alerts-queue.md#severity)
- <span data-ttu-id="b53ec-137">**Category**—脅威コンポーネントまたはアクティビティの種類 (その場合)。</span><span class="sxs-lookup"><span data-stu-id="b53ec-137">**Category**—type of threat component or activity, if any.</span></span> [<span data-ttu-id="b53ec-138">アラート カテゴリについて読む</span><span class="sxs-lookup"><span data-stu-id="b53ec-138">Read about alert categories</span></span>](alerts-queue.md#understanding-alert-categories)
- <span data-ttu-id="b53ec-139">**MITRE ATT&CK** の手法 (CK フレームワークの MITRE ATT に記載されているルールで識別される 1 つ以上の攻撃&です。</span><span class="sxs-lookup"><span data-stu-id="b53ec-139">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the MITRE ATT&CK framework.</span></span> <span data-ttu-id="b53ec-140">このセクションは、マルウェア、ランサムウェア、疑わしいアクティビティ、望ましくないソフトウェアなど、特定のアラート カテゴリでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="b53ec-140">This section is not available with certain alert categories, such as malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="b53ec-141">**Description**—ルールによって識別されるコンポーネントまたはアクティビティの詳細</span><span class="sxs-lookup"><span data-stu-id="b53ec-141">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="b53ec-142">**推奨されるアクション**—応答者がアラートに応答して実行する可能性がある追加のアクション</span><span class="sxs-lookup"><span data-stu-id="b53ec-142">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

<span data-ttu-id="b53ec-143">アラートの詳細の表示方法の詳細については、「アラート キュー [」を参照してください](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="b53ec-143">For more information about how alert details are displayed, [read about the alert queue](alerts-queue.md).</span></span>

### <a name="rule-frequency"></a><span data-ttu-id="b53ec-144">ルールの頻度</span><span class="sxs-lookup"><span data-stu-id="b53ec-144">Rule frequency</span></span>

<span data-ttu-id="b53ec-145">保存すると、新しいカスタム検出ルールが直ちに実行され、過去 30 日間のデータからの一致がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-145">When saved, a new custom detection rule immediately runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="b53ec-146">次に、ルールは、選択した頻度に基づいて、固定間隔とルックバック期間で再度実行されます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-146">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="b53ec-147">**24 時間ごとに** 実行され、過去 30 日間のデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-147">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="b53ec-148">**12 時間ごとに** 実行され、過去 24 時間のデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-148">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="b53ec-149">**3 時間ごとに** 実行され、過去 6 時間のデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-149">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="b53ec-150">**1 時間** ごとに 1 時間ごとに実行され、過去 2 時間のデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-150">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="b53ec-151">ルールを編集すると、設定した頻度に従ってスケジュールされた次の実行時に適用された変更と一緒に実行されます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-151">When you edit a rule, it will run with the applied changes in the next run time scheduled according to the frequency you set.</span></span>


> [!TIP]
> <span data-ttu-id="b53ec-152">クエリのタイム フィルターとルックバック期間を一致します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-152">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="b53ec-153">ルックバック期間外の結果は無視されます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-153">Results outside of the lookback duration are ignored.</span></span>

<span data-ttu-id="b53ec-154">検出を監視する頻度に一致する頻度を選択し、通知に応答する組織の容量を検討します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-154">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

## <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="b53ec-155">3. 影響を受け取ったエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-155">3. Choose the impacted entities.</span></span>

<span data-ttu-id="b53ec-156">影響を受ける主なエンティティまたは影響を受けるエンティティを検索するクエリ結果の列を特定します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-156">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="b53ec-157">たとえば、クエリはデバイス ID とユーザー ID の両方を返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="b53ec-157">For example, a query might return both device and user IDs.</span></span> <span data-ttu-id="b53ec-158">これらの列の中で、影響を受ける主なエンティティを表す列を特定すると、サービスは関連するアラートの集計、インシデントの関連付け、およびターゲット応答アクションの集計に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-158">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="b53ec-159">エンティティの種類ごとに 1 つの列のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-159">You can select only one column for each entity type.</span></span> <span data-ttu-id="b53ec-160">クエリによって返されない列は選択できません。</span><span class="sxs-lookup"><span data-stu-id="b53ec-160">Columns that are not returned by your query can't be selected.</span></span>

## <a name="4-specify-actions"></a><span data-ttu-id="b53ec-161">4. アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-161">4. Specify actions.</span></span>

<span data-ttu-id="b53ec-162">カスタム検出ルールは、クエリによって返されるファイルまたはデバイスに対して自動的にアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-162">Your custom detection rule can automatically take actions on files or devices that are returned by the query.</span></span>

### <a name="actions-on-devices"></a><span data-ttu-id="b53ec-163">デバイスでのアクション</span><span class="sxs-lookup"><span data-stu-id="b53ec-163">Actions on devices</span></span>

<span data-ttu-id="b53ec-164">これらのアクションは、クエリ結果の列 `DeviceId` のデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-164">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>

- <span data-ttu-id="b53ec-165">**デバイスの分離**—完全なネットワーク分離を適用し、Defender for Endpoint サービスを除くすべてのアプリケーションまたはサービスにデバイスが接続できません。</span><span class="sxs-lookup"><span data-stu-id="b53ec-165">**Isolate device**—applies full network isolation, preventing the device from connecting to any application or service, except for the Defender for Endpoint service.</span></span> [<span data-ttu-id="b53ec-166">デバイスの分離の詳細</span><span class="sxs-lookup"><span data-stu-id="b53ec-166">Learn more about device isolation</span></span>](respond-machine-alerts.md#isolate-devices-from-the-network)
- <span data-ttu-id="b53ec-167">**調査パッケージの収集**— ZIP ファイル内のデバイス情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-167">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="b53ec-168">調査パッケージの詳細</span><span class="sxs-lookup"><span data-stu-id="b53ec-168">Learn more about the investigation package</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- <span data-ttu-id="b53ec-169">**ウイルス対策スキャンの実行**-デバイスで Microsoft Defender ウイルス対策スキャン全体を実行する</span><span class="sxs-lookup"><span data-stu-id="b53ec-169">**Run antivirus scan**—performs a full Microsoft Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="b53ec-170">**調査の開始**- デバイスで [自動調査](automated-investigations.md) を開始する</span><span class="sxs-lookup"><span data-stu-id="b53ec-170">**Initiate investigation**—starts an [automated investigation](automated-investigations.md) on the device</span></span>
- <span data-ttu-id="b53ec-171">**アプリの実行を制限** する :Microsoft 発行の証明書で署名されたファイルのみを実行できるデバイスの制限を設定します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-171">**Restrict app execution**—sets restrictions on the device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="b53ec-172">アプリの実行を制限する方法の詳細</span><span class="sxs-lookup"><span data-stu-id="b53ec-172">Learn more about restricting app execution</span></span>](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a><span data-ttu-id="b53ec-173">ファイルに対するアクション</span><span class="sxs-lookup"><span data-stu-id="b53ec-173">Actions on files</span></span>

<span data-ttu-id="b53ec-174">これらのアクションは、クエリ結果の列または列内 `SHA1` `InitiatingProcessSHA1` のファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-174">These actions are applied to files in the `SHA1` or the `InitiatingProcessSHA1` column of the query results:</span></span>

- <span data-ttu-id="b53ec-175">**Allow/Block**—ファイルをカスタム インジケーター [](manage-indicators.md)リストに自動的に追加して、常に実行を許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="b53ec-175">**Allow/Block**—automatically adds the file to your [custom indicator list](manage-indicators.md) so that it is always allowed to run or blocked from running.</span></span> <span data-ttu-id="b53ec-176">このアクションの範囲を設定して、選択したデバイス グループでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-176">You can set the scope of this action so that it is taken only on selected device groups.</span></span> <span data-ttu-id="b53ec-177">このスコープは、ルールのスコープとは独立しています。</span><span class="sxs-lookup"><span data-stu-id="b53ec-177">This scope is independent of the scope of the rule.</span></span>
- <span data-ttu-id="b53ec-178">**検疫ファイル**— ファイルを現在の場所から削除し、コピーを検疫に入れる</span><span class="sxs-lookup"><span data-stu-id="b53ec-178">**Quarantine file**—deletes the file from its current location and places a copy in quarantine</span></span>

### <a name="actions-on-users"></a><span data-ttu-id="b53ec-179">ユーザーに対するアクション</span><span class="sxs-lookup"><span data-stu-id="b53ec-179">Actions on users</span></span>

- <span data-ttu-id="b53ec-180">**ユーザーを侵害済み** としてマークする —Azure Active Directory でユーザーのリスク レベルを "高" に設定し、対応する ID 保護ポリシーを [トリガーします](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)。</span><span class="sxs-lookup"><span data-stu-id="b53ec-180">**Mark user as compromised**—sets the user's risk level to "high" in Azure Active Directory, triggering the corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels).</span></span>

## <a name="5-set-the-rule-scope"></a><span data-ttu-id="b53ec-181">5. ルールスコープを設定します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-181">5. Set the rule scope.</span></span>

<span data-ttu-id="b53ec-182">ルールの対象となるデバイスを指定するスコープを設定します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-182">Set the scope to specify which devices are covered by the rule:</span></span>

- <span data-ttu-id="b53ec-183">すべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="b53ec-183">All devices</span></span>
- <span data-ttu-id="b53ec-184">特定のデバイス グループ</span><span class="sxs-lookup"><span data-stu-id="b53ec-184">Specific device groups</span></span>

<span data-ttu-id="b53ec-185">スコープ内のデバイスからのデータだけがクエリされます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-185">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="b53ec-186">また、これらのデバイスでのみアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-186">Also, actions will be taken only on those devices.</span></span>

## <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="b53ec-187">6. ルールを確認して有効にする。</span><span class="sxs-lookup"><span data-stu-id="b53ec-187">6. Review and turn on the rule.</span></span>

<span data-ttu-id="b53ec-188">ルールを確認した後、[作成] **を選択して** 保存します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-188">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="b53ec-189">カスタム検出ルールが直ちに実行されます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-189">The custom detection rule immediately runs.</span></span> <span data-ttu-id="b53ec-190">構成された頻度に基づいて再び実行され、一致を確認し、アラートを生成し、応答アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b53ec-190">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

<span data-ttu-id="b53ec-191">カスタム検出 [ルールを表示および管理し、](custom-detections-manage.md)以前の実行を確認し、トリガーしたアラートを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-191">You can [view and manage custom detection rules](custom-detections-manage.md), check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="b53ec-192">必要に応じてルールを実行して変更できます。</span><span class="sxs-lookup"><span data-stu-id="b53ec-192">You can also run a rule on demand and modify it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b53ec-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="b53ec-193">Related topics</span></span>

- [<span data-ttu-id="b53ec-194">検出ルールの表示と管理</span><span class="sxs-lookup"><span data-stu-id="b53ec-194">View and manage custom detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="b53ec-195">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="b53ec-195">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="b53ec-196">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="b53ec-196">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b53ec-197">高度な捜索のクエリ言語について学習する</span><span class="sxs-lookup"><span data-stu-id="b53ec-197">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b53ec-198">アラートの表示と整理</span><span class="sxs-lookup"><span data-stu-id="b53ec-198">View and organize alerts</span></span>](alerts-queue.md)
