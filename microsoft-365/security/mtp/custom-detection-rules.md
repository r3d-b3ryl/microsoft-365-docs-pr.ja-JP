---
title: Microsoft の脅威保護でカスタムの検出ルールを作成および管理する
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: cdfc23f34d90c9d725ec6fb314728553a987c025
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034866"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="c489f-104">カスタムの検出ルールを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="c489f-104">Create and manage custom detections rules</span></span>

<span data-ttu-id="c489f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c489f-105">**Applies to:**</span></span>
- <span data-ttu-id="c489f-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c489f-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="c489f-107">[高度な](advanced-hunting-overview.md)検索クエリから構築されたカスタム検出ルールを使用すると、疑いのある違反のアクティビティや不適切なエンドポイントを含む、さまざまなイベントやシステム状態を事前に監視できます。</span><span class="sxs-lookup"><span data-stu-id="c489f-107">Custom detection rules built from [Advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="c489f-108">それらを定期的に実行するように設定して、一致するものがある場合は警告を生成し、応答アクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="c489f-108">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="c489f-109">ユーザー設定の検出を管理するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="c489f-109">Required permissions for managing custom detections</span></span>

<span data-ttu-id="c489f-110">ユーザー設定の検出を管理するには、次のいずれかの役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c489f-110">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="c489f-111">**セキュリティ管理者**: セキュリティ管理者またはセキュリティ管理者の役割は、Microsoft 365 セキュリティセンターとさまざまなポータルおよびサービスのさまざまなセキュリティ設定を管理するための[Azure Active Directory の役割](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator)です。</span><span class="sxs-lookup"><span data-stu-id="c489f-111">**Security administrator** — the security administrator or security admin role is an [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) for managing various security settings in Microsoft 365 security center and various portals and services.</span></span>

- <span data-ttu-id="c489f-112">**セキュリティオペレーター** —セキュリティオペレーターの役割は、通知を管理するための[Azure Active Directory の役割](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator)で、Microsoft 365 セキュリティセンターのすべての情報を含む、セキュリティ関連の機能に対するグローバルな読み取り専用アクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="c489f-112">**Security operator** —  the security operator role is an [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) for managing alerts and has global read-only access on security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="c489f-113">この役割は、Microsoft Defender ATP で役割ベースのアクセス制御 (RBAC) がオフになっている場合にのみ、カスタムの検出を管理するのに十分です。</span><span class="sxs-lookup"><span data-stu-id="c489f-113">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender ATP.</span></span> <span data-ttu-id="c489f-114">RBAC を構成している場合は、Microsoft Defender ATP の [**セキュリティ設定の管理**] アクセス許可も必要です。</span><span class="sxs-lookup"><span data-stu-id="c489f-114">If you have RBAC configured, you also need the **manage security settings** permission for Microsoft Defender ATP.</span></span>

<span data-ttu-id="c489f-115">必要なアクセス許可を管理するために、**全体管理者**は次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c489f-115">To manage required permissions, a **global administrator** can do the following:</span></span>

- <span data-ttu-id="c489f-116">「 **Roles**Roles > **security admin**」の下にある[Microsoft 365 管理センター](https://admin.microsoft.com/)で、**セキュリティ管理者**または**セキュリティオペレーター**の役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c489f-116">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="c489f-117">[ > **アクセス**許可 > の**役割**の**設定**] の下の microsoft defender の[セキュリティセンター](https://securitycenter.windows.com/)で、microsoft defender ATP の RBAC 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="c489f-117">Check RBAC settings for Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="c489f-118">対応する役割を選択して、[**セキュリティ設定の管理**] アクセス許可を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c489f-118">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="c489f-119">ユーザー設定の検出を管理するために、**セキュリティオペレーター**は、RBAC が有効になっている場合、MICROSOFT Defender ATP の**セキュリティ設定の管理**権限を必要とします。</span><span class="sxs-lookup"><span data-stu-id="c489f-119">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender ATP if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="c489f-120">カスタム検出ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="c489f-120">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="c489f-121">1. クエリを準備します。</span><span class="sxs-lookup"><span data-stu-id="c489f-121">1. Prepare the query.</span></span>

<span data-ttu-id="c489f-122">Microsoft 365 セキュリティセンターで、 **[高度な**検索] に移動して既存のクエリを選択するか、新しいクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c489f-122">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="c489f-123">新しいクエリを使用する場合は、クエリを実行してエラーを特定し、考えられる結果を理解します。</span><span class="sxs-lookup"><span data-stu-id="c489f-123">When using a new query, run the query to identify errors and understand possible results.</span></span>

#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="c489f-124">クエリ結果に必要な列</span><span class="sxs-lookup"><span data-stu-id="c489f-124">Required columns in the query results</span></span>
<span data-ttu-id="c489f-125">カスタム検出ルールを作成するには、クエリは次の列を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c489f-125">To create a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- <span data-ttu-id="c489f-126">次のいずれかのデバイス、ユーザー、またはメールボックスの列。</span><span class="sxs-lookup"><span data-stu-id="c489f-126">One of the following device, user, or mailbox columns:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="c489f-127">`SenderFromAddress`(エンベロープ送信者またはリターンパスアドレス)</span><span class="sxs-lookup"><span data-stu-id="c489f-127">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="c489f-128">`SenderMailFromAddress`(電子メールクライアントによって表示される sender アドレス)</span><span class="sxs-lookup"><span data-stu-id="c489f-128">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountSid`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
><span data-ttu-id="c489f-129">[高度な検索スキーマ](advanced-hunting-schema-tables.md)に新しいテーブルが追加されると、追加のエンティティのサポートが追加されます。</span><span class="sxs-lookup"><span data-stu-id="c489f-129">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="c489f-130">検索結果をカスタマイズまたは集計するために`project` or `summarize`演算子を使用しないような単純なクエリでは、通常、これらの共通の列が返されます。</span><span class="sxs-lookup"><span data-stu-id="c489f-130">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="c489f-131">より複雑なクエリでこれらの列が返されるようにするには、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="c489f-131">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="c489f-132">たとえば`DeviceId`、などの列の下にあるエンティティで集計およびカウントを行う場合は、それぞれの一意`Timestamp` `DeviceId`に関係する最新のイベントから取得することによって返すことができます。</span><span class="sxs-lookup"><span data-stu-id="c489f-132">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="c489f-133">以下のサンプルクエリは、ウイルス検出を使用し`DeviceId`て一意のコンピューターの数 () をカウントし、この数を使用して、5個を超える検出があるコンピューターのみを検出します。</span><span class="sxs-lookup"><span data-stu-id="c489f-133">The sample query below counts the number of unique machines (`DeviceId`) with antivirus detections and uses this count to find only the machines with more than five detections.</span></span> <span data-ttu-id="c489f-134">最新`Timestamp`のを返すには、 `summarize`演算子を`arg_max`関数で使用します。</span><span class="sxs-lookup"><span data-stu-id="c489f-134">To return the latest `Timestamp`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId
| where count_ > 5
```
### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="c489f-135">2. 新しいルールを作成し、通知の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="c489f-135">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="c489f-136">クエリエディターでクエリを実行して、[**検出ルールの作成**] を選択し、次の通知の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="c489f-136">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="c489f-137">**検出名**—検出ルールの名前</span><span class="sxs-lookup"><span data-stu-id="c489f-137">**Detection name** — name of the detection rule</span></span>
- <span data-ttu-id="c489f-138">**頻度**—クエリを実行してアクションを実行する間隔。</span><span class="sxs-lookup"><span data-stu-id="c489f-138">**Frequency** — interval for running the query and taking action.</span></span> [<span data-ttu-id="c489f-139">以下の追加のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c489f-139">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="c489f-140">**アラートタイトル**-ルールによってトリガーされたアラートと共に表示されるタイトル</span><span class="sxs-lookup"><span data-stu-id="c489f-140">**Alert title** — title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="c489f-141">**重要度**—ルールによって識別されるコンポーネントまたはアクティビティの潜在的なリスク</span><span class="sxs-lookup"><span data-stu-id="c489f-141">**Severity** — potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="c489f-142">**カテゴリ**—ルールによって識別される脅威コンポーネントまたはアクティビティ</span><span class="sxs-lookup"><span data-stu-id="c489f-142">**Category** — threat component or activity identified by the rule</span></span>
- <span data-ttu-id="c489f-143">**MITRE att&** の小は、 [MITRE at&t&](https://attack.mitre.org/)の「」フレームワークで文書化されているように、ルールによって識別される1つまたは複数の攻撃手法です。</span><span class="sxs-lookup"><span data-stu-id="c489f-143">**MITRE ATT&CK techniques** — one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/)</span></span>
- <span data-ttu-id="c489f-144">**Description** —ルールによって識別されたコンポーネントまたはアクティビティに関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="c489f-144">**Description** — more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="c489f-145">**推奨**されるアクション-通知に応答する可能性があるその他のアクション。</span><span class="sxs-lookup"><span data-stu-id="c489f-145">**Recommended actions** — additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="c489f-146">ルールの頻度</span><span class="sxs-lookup"><span data-stu-id="c489f-146">Rule frequency</span></span>
<span data-ttu-id="c489f-147">保存すると、新しいまたは編集されたカスタム検出ルールが直ちに実行され、過去30日間のデータが一致するかどうかがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="c489f-147">When saved, a new or edited custom detection rule immediately runs and checks for matches from  the past 30 days of data.</span></span> <span data-ttu-id="c489f-148">その後、ルールは固定された間隔で再び実行され、選択した頻度に基づいて、継続時間を確認します。</span><span class="sxs-lookup"><span data-stu-id="c489f-148">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="c489f-149">**24 時間ごと**: 過去30日間のデータをチェックして、24時間ごとに実行します。</span><span class="sxs-lookup"><span data-stu-id="c489f-149">**Every 24 hours** — runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="c489f-150">**12 時間ごと**-過去24時間以内にデータをチェックして、12時間ごとに実行します。</span><span class="sxs-lookup"><span data-stu-id="c489f-150">**Every 12 hours** — runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="c489f-151">**3 時間ごと**—過去6時間にデータをチェックして、3時間ごとに実行します。</span><span class="sxs-lookup"><span data-stu-id="c489f-151">**Every 3 hours** — runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="c489f-152">毎時に**1 時間ごと**に実行され、過去2時間のデータをチェックします。</span><span class="sxs-lookup"><span data-stu-id="c489f-152">**Every hour** — runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="c489f-153">検出を監視する頻度と一致する頻度を選択し、通知に応答するために組織の能力を考慮します。</span><span class="sxs-lookup"><span data-stu-id="c489f-153">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="c489f-154">3. 影響を受けるエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="c489f-154">3. Choose the impacted entities.</span></span>
<span data-ttu-id="c489f-155">影響を受ける主なエンティティまたは影響を受けるエンティティがあることが予想されるクエリ結果内の列を特定します。</span><span class="sxs-lookup"><span data-stu-id="c489f-155">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="c489f-156">たとえば、クエリは送信者 (`SenderFromAddress`または`SenderMailFromAddress`) と受信者 (`RecipientEmailAddress`) のアドレスを返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="c489f-156">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="c489f-157">これらの列のうち、主な影響を受けるエンティティを識別することにより、サービスは関連するアラートの集約、インシデントの関連付け、およびターゲットの応答アクションの実行に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="c489f-157">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="c489f-158">エンティティの種類 (メールボックス、ユーザー、またはデバイス) ごとに1つの列のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c489f-158">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="c489f-159">クエリで返されない列は選択できません。</span><span class="sxs-lookup"><span data-stu-id="c489f-159">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions-on-files-or-machines"></a><span data-ttu-id="c489f-160">4. ファイルまたはコンピューターに対するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c489f-160">4. Specify actions on files or machines.</span></span>
<span data-ttu-id="c489f-161">カスタム検出ルールは、クエリによって返されるファイルまたはコンピューターに対して、自動的にアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c489f-161">Your custom detection rule can automatically take actions on files or machines that are returned by the query.</span></span>

#### <a name="actions-on-machines"></a><span data-ttu-id="c489f-162">コンピューター上のアクション</span><span class="sxs-lookup"><span data-stu-id="c489f-162">Actions on machines</span></span>
<span data-ttu-id="c489f-163">これらのアクションは、クエリ結果の`DeviceId`列にあるマシンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c489f-163">These actions are applied to machines in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="c489f-164">**分離マシン**— MICROSOFT Defender ATP を使用して完全なネットワークの分離を適用し、コンピューターがアプリケーションやサービスに接続できないようにします。</span><span class="sxs-lookup"><span data-stu-id="c489f-164">**Isolate machine** — uses Microsoft Defender ATP to apply full network isolation, preventing the machine from connecting to any application or service.</span></span> [<span data-ttu-id="c489f-165">Microsoft Defender ATP コンピューターの分離の詳細情報</span><span class="sxs-lookup"><span data-stu-id="c489f-165">Learn more about Microsoft Defender ATP machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-machines-from-the-network)
- <span data-ttu-id="c489f-166">**収集調査パッケージ**—コンピューター情報を ZIP ファイルで収集します。</span><span class="sxs-lookup"><span data-stu-id="c489f-166">**Collect investigation package** — collects machine information in a ZIP file.</span></span> [<span data-ttu-id="c489f-167">Microsoft Defender ATP 調査パッケージの詳細情報</span><span class="sxs-lookup"><span data-stu-id="c489f-167">Learn more about the Microsoft Defender ATP investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-machines)
- <span data-ttu-id="c489f-168">**ウイルス対策スキャンを実行**する—コンピューター上で Windows Defender ウイルス対策スキャンを完全に実行します。</span><span class="sxs-lookup"><span data-stu-id="c489f-168">**Run antivirus scan** — performs a full Windows Defender Antivirus scan on the machine</span></span>
- <span data-ttu-id="c489f-169">**調査の開始**—コンピューターの[自動調査](mtp-autoir.md)を開始します。</span><span class="sxs-lookup"><span data-stu-id="c489f-169">**Initiate investigation** — initiates an [automated investigation](mtp-autoir.md) on the machine</span></span>

#### <a name="actions-on-files"></a><span data-ttu-id="c489f-170">ファイルに対するアクション</span><span class="sxs-lookup"><span data-stu-id="c489f-170">Actions on files</span></span>
<span data-ttu-id="c489f-171">選択すると、[**ファイルの検疫**] アクションは、クエリ`SHA1`結果`InitiatingProcessSHA1`の`SHA256`、、 `InitiatingProcessSHA256` 、または列のファイルに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="c489f-171">When selected, the **Quarantine file** action is taken on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="c489f-172">この操作は、現在の場所からファイルを削除し、そのコピーを検疫に配置します。</span><span class="sxs-lookup"><span data-stu-id="c489f-172">This action deletes the file from its current location and places a copy in quarantine.</span></span>

> [!NOTE]
> <span data-ttu-id="c489f-173">カスタム検出ルールのアクションの許可またはブロックは、現在、Microsoft の脅威保護ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c489f-173">The allow or block action for custom detection rules is currently not supported on Microsoft Threat Protection.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="c489f-174">5. ルールの範囲を設定します。</span><span class="sxs-lookup"><span data-stu-id="c489f-174">5. Set the rule scope.</span></span>
<span data-ttu-id="c489f-175">ルールに含まれるデバイスを指定するようにスコープを設定します。</span><span class="sxs-lookup"><span data-stu-id="c489f-175">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="c489f-176">この範囲は、デバイスをチェックするルールに影響し、メールボックスとユーザーアカウントまたは id のみをチェックするルールには影響しません。</span><span class="sxs-lookup"><span data-stu-id="c489f-176">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="c489f-177">スコープを設定するときは、次のオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c489f-177">When setting the scope, you can select:</span></span>

- <span data-ttu-id="c489f-178">すべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="c489f-178">All devices</span></span>
- <span data-ttu-id="c489f-179">特定のデバイスグループ</span><span class="sxs-lookup"><span data-stu-id="c489f-179">Specific device groups</span></span>

<span data-ttu-id="c489f-180">範囲内のデバイスからのデータのみが照会されます。</span><span class="sxs-lookup"><span data-stu-id="c489f-180">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="c489f-181">また、アクションはこれらのデバイスでのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="c489f-181">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="c489f-182">6. ルールを確認し、オンにします。</span><span class="sxs-lookup"><span data-stu-id="c489f-182">6. Review and turn on the rule.</span></span>
<span data-ttu-id="c489f-183">ルールを確認した後、[**作成**] をクリックして保存します。</span><span class="sxs-lookup"><span data-stu-id="c489f-183">After reviewing the rule, click **Create** to save it.</span></span> <span data-ttu-id="c489f-184">カスタム検出ルールが直ちに実行されます。</span><span class="sxs-lookup"><span data-stu-id="c489f-184">The custom detection rule immediately runs.</span></span> <span data-ttu-id="c489f-185">この動作は、構成された頻度に基づいて、一致をチェックし、通知を生成し、応答アクションを実行することによって再度実行します。</span><span class="sxs-lookup"><span data-stu-id="c489f-185">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="c489f-186">既存のカスタム検出ルールを管理する</span><span class="sxs-lookup"><span data-stu-id="c489f-186">Manage existing custom detection rules</span></span>
<span data-ttu-id="c489f-187">既存のカスタム検出ルールの一覧を表示し、以前の実行をチェックして、トリガーされた通知を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c489f-187">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="c489f-188">また、必要に応じてルールを実行して変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="c489f-188">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="c489f-189">既存のルールを表示する</span><span class="sxs-lookup"><span data-stu-id="c489f-189">View existing rules</span></span>

<span data-ttu-id="c489f-190">既存のカスタム検出ルールをすべて表示**するには** > 、[**カスタム**検出の検索] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c489f-190">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="c489f-191">ページには、次の実行情報を含むすべてのルールの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c489f-191">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="c489f-192">[**前回の実行**]-ルールが最後に実行されたときに、クエリの一致をチェックし、通知を生成する</span><span class="sxs-lookup"><span data-stu-id="c489f-192">**Last run** — when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="c489f-193">**最終実行状態**—ルールが正常に実行されたかどうか</span><span class="sxs-lookup"><span data-stu-id="c489f-193">**Last run status** — whether a rule ran successfully</span></span>
- <span data-ttu-id="c489f-194">**次回の実行**-次のスケジュールされた実行</span><span class="sxs-lookup"><span data-stu-id="c489f-194">**Next run** — the next scheduled run</span></span>
- <span data-ttu-id="c489f-195">**状態**: ルールが有効になっているかどうか</span><span class="sxs-lookup"><span data-stu-id="c489f-195">**Status** — whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="c489f-196">ルールの詳細、変更ルール、および実行ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="c489f-196">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="c489f-197">カスタム検出ルールについての包括的な情報を表示するには、[**カスタム**検出を**探す** > ] のルールの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="c489f-197">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="c489f-198">これにより、カスタム検出ルールに関するページが、アラート、実行状態、およびスコープの詳細を含む、ルールに関する一般的な情報を使用して開きます。</span><span class="sxs-lookup"><span data-stu-id="c489f-198">This opens a page about the custom detection rule with general information about the rule, including the details of the alert, run status, and scope.</span></span> <span data-ttu-id="c489f-199">また、トリガーされた通知とトリガーされたアクションのリストも表示します。</span><span class="sxs-lookup"><span data-stu-id="c489f-199">It also provides the list of triggered alerts and triggered actions.</span></span>

<span data-ttu-id="c489f-200">![カスタム検出ルールの詳細ページ](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="c489f-200">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="c489f-201">*カスタム検出ルールの詳細*</span><span class="sxs-lookup"><span data-stu-id="c489f-201">*Custom detection rule details*</span></span>

<span data-ttu-id="c489f-202">このページでは、ルールに対して次の操作を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="c489f-202">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="c489f-203">**Run** -ルールを直ちに実行します。</span><span class="sxs-lookup"><span data-stu-id="c489f-203">**Run** — run the rule immediately.</span></span> <span data-ttu-id="c489f-204">これにより、次の実行の間隔もリセットされます。</span><span class="sxs-lookup"><span data-stu-id="c489f-204">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="c489f-205">**編集**—クエリを変更せずにルールを変更する</span><span class="sxs-lookup"><span data-stu-id="c489f-205">**Edit** — modify the rule without changing the query</span></span>
- <span data-ttu-id="c489f-206">**クエリの変更**-高度な検索でクエリを編集する</span><span class="sxs-lookup"><span data-stu-id="c489f-206">**Modify query** — edit the query in advanced hunting</span></span>
- <span data-ttu-id="c489f-207">**[オフ] をオンに** / **Turn off**して、ルールを有効にするか、実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="c489f-207">**Turn on** / **Turn off** — enable the rule or stop it from running</span></span>
- <span data-ttu-id="c489f-208">**削除**—ルールをオフにして削除する</span><span class="sxs-lookup"><span data-stu-id="c489f-208">**Delete** — turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="c489f-209">トリガーされた通知の表示と管理</span><span class="sxs-lookup"><span data-stu-id="c489f-209">View and manage triggered alerts</span></span>

<span data-ttu-id="c489f-210">[仕分けルールの詳細] 画面 (**ユーザー設定の検出** > を**探し** > ている場合) で、[トリガーされた**通知\*\*\*\*]** に移動して、ルールに一致することによって生成された通知の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c489f-210">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered alerts** to view the list of alerts generated by matches to the rule.</span></span> <span data-ttu-id="c489f-211">そのアラートに関する詳細情報を表示するアラートを選択し、そのアラートに対して次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="c489f-211">Select an alert to view detailed information about that alert and take the following actions on that alert:</span></span>

- <span data-ttu-id="c489f-212">状態と分類 (true または false のアラート) を設定してアラートを管理する</span><span class="sxs-lookup"><span data-stu-id="c489f-212">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="c489f-213">警告をインシデントにリンクする</span><span class="sxs-lookup"><span data-stu-id="c489f-213">Link the alert to an incident</span></span>
- <span data-ttu-id="c489f-214">高度な検索で警告をトリガーしたクエリを実行する</span><span class="sxs-lookup"><span data-stu-id="c489f-214">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="c489f-215">アクションを確認する</span><span class="sxs-lookup"><span data-stu-id="c489f-215">Review actions</span></span>
<span data-ttu-id="c489f-216">[ルールの詳細] 画面 ([**ユーザー設定の検出** > を**探し** > ています **]**) で、[トリガーされた**アクション**] に移動して、ルールへの一致に基づいて実行されたアクションのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="c489f-216">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions** to view the list of actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="c489f-217">テーブル内のアイテムに関する情報をすばやく表示し、アクションを実行するには、表の左側にある選択列 [&#10003;] を使用します。</span><span class="sxs-lookup"><span data-stu-id="c489f-217">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="c489f-218">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c489f-218">Related topic</span></span>
- [<span data-ttu-id="c489f-219">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="c489f-219">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="c489f-220">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="c489f-220">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c489f-221">高度な捜索のクエリ言語について学習する</span><span class="sxs-lookup"><span data-stu-id="c489f-221">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
