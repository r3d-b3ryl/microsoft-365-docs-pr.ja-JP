---
title: カスタム検出ルールを作成および管理Microsoft 365 Defender
description: 高度な検索クエリに基づいてカスタム検出ルールを作成および管理する方法について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、カスタム検出、ルール、スキーマ、kusto、RBAC、permissions、Microsoft Defender for Endpoint
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
ms.openlocfilehash: c1d0095860242492dc8dd5e370f8583aaed7cff4
ms.sourcegitcommit: 132b8dc316bcd4b456de33d6a30e90ca69b0f956
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594222"
---
# <a name="create-and-manage-custom-detections-rules"></a>カスタム検出ルールを作成および管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

カスタム検出ルールは、高度な検索クエリを使用して設計および [調整できるルール](advanced-hunting-overview.md) です。 これらのルールを使用すると、侵害の疑いのあるアクティビティや誤った構成されたエンドポイントなど、さまざまなイベントやシステム状態を積極的に監視できます。 一定の間隔で実行し、アラートを生成し、一致するたびに応答アクションを実行する設定できます。

## <a name="required-permissions-for-managing-custom-detections"></a>カスタム検出を管理するために必要なアクセス許可

カスタム検出を管理するには、次のいずれかの役割を割り当てる必要があります。

- **セキュリティ管理者**:この役割を持 [Azure Active Directoryユーザーは](/azure/active-directory/roles/permissions-reference#security-administrator)、ポータルや他のポータルやサービスMicrosoft 365 Defender設定を管理できます。

- **セキュリティ オペレーター**-この [](/azure/active-directory/roles/permissions-reference#security-operator)Azure Active Directory ロールを持つユーザーは、アラートを管理し、セキュリティ関連の機能 (Microsoft 365 Defender ポータルのすべての情報を含む) へのグローバルな読み取り専用アクセス権を持つ。 この役割は、Microsoft Defender for Endpoint で役割ベースのアクセス制御 (RBAC) がオフになっている場合にのみ、カスタム検出を管理するのに十分です。 RBAC が構成されている場合は、Defender **for** Endpoint のセキュリティ設定の管理アクセス許可も必要です。

また、特定のソリューションのデータに適用されるカスタム検出Microsoft 365 Defenderアクセス許可がある場合は管理できます。 たとえば、Microsoft 365 DefenderのOfficeを管理する場合は、テーブルを使用してカスタム検出を作成できますが、テーブルは `Email` 作成 `Identity` できません。  

必要なアクセス許可を管理するには、グローバル **管理者は次の機能を使用** できます。

- [役割の **セキュリティ管理者] の** 下の [セキュリティ管理者 **] の** 下Microsoft 365 管理センター管理者または [セキュリティ](https://admin.microsoft.com/)オペレーター **の役割**  >  **を割り当てます**。
- [アクセス許可の役割] の下にある [Microsoft Defender for Endpoint [Microsoft Defender セキュリティ センター](https://securitycenter.windows.com/) RBAC 設定  >  **を**  >  **確認します**。 対応する役割を選択して、セキュリティ設定の **管理権限を割り当** てる。

> [!NOTE]
> カスタム検出を管理 **するには、RBAC** が有効になっている場合、セキュリティオペレーターは Microsoft Defender for Endpoint のセキュリティ設定の管理権限を必要とします。

## <a name="create-a-custom-detection-rule"></a>カスタム検出ルールの作成
### <a name="1-prepare-the-query"></a>1. クエリを準備します。

このポータルMicrosoft 365 Defender[高度な検索] に **移動し、** 既存のクエリを選択するか、新しいクエリを作成します。 新しいクエリを使用する場合は、クエリを実行してエラーを特定し、考えられる結果を理解します。

>[!IMPORTANT]
>サービスがあまりにも多くのアラートを返さなすぎ防止するために、各ルールは、実行されるたびに 100 件のアラートのみを生成するに制限されます。 ルールを作成する前に、クエリを調整して、通常の毎日のアクティビティに対する警告を回避してください。


#### <a name="required-columns-in-the-query-results"></a>クエリ結果に必要な列
カスタム検出ルールを作成するには、次の列を返す必要があります。

- `Timestamp`生成されたアラートのタイムスタンプを設定するために使用される
- `ReportId`—元のレコードの参照を有効にする
- 特定のデバイス、ユーザー、またはメールボックスを識別する次のいずれかの列。
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (封筒の送信者またはReturn-Pathアドレス)
    - `SenderMailFromAddress` (電子メール クライアントによって表示される送信者アドレス)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>新しいテーブルが高度な狩猟スキーマに追加されるに応じて、追加のエンティティ [のサポートが追加されます](advanced-hunting-schema-tables.md)。

単純なクエリ (結果をカスタマイズまたは集計するために or 演算子を使用しないクエリなど) は、通常、これらの一般的な `project` `summarize` 列を返します。

より複雑なクエリがこれらの列を返すには、さまざまな方法があります。 たとえば、次のような列の下のエンティティ別に集計してカウントする場合でも、各一意のイベントを含む最新のイベントから取得 `DeviceId` `Timestamp` `ReportId` できます `DeviceId` 。


> [!IMPORTANT]
> 列を使用してカスタム検出をフィルター処理 `Timestamp` しないようにします。 カスタム検出に使用されるデータは、検出頻度に基づいて事前にフィルター処理されます。


以下のサンプル クエリは、ウイルス対策の検出を含む一意のデバイス ( ) の数をカウントし、この数を使用して 5 つを超える検出を持つデバイス `DeviceId` のみを検索します。 最新の値と `Timestamp` 対応する値を取得 `ReportId` するには、関数と `summarize` 一緒に演算子を使用 `arg_max` します。

```kusto
DeviceEvents
| where ingestion_time() > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> クエリのパフォーマンスを向上するには、ルールの目的の実行頻度に一致する時間フィルターを設定します。 実行頻度が最も少ないのは _24_ 時間ごとに行われるので、過去 1 日のフィルター処理では、すべての新しいデータがカバーされます。

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. 新しいルールを作成し、アラートの詳細を提供します。

クエリ エディターでクエリを使用して、[検出ルールの作成] **を選択し** 、次のアラートの詳細を指定します。

- **検出名**—検出ルールの名前
- **頻度**—クエリを実行してアクションを実行する間隔。 [以下のその他のガイダンスを参照してください。](#rule-frequency)
- **アラート タイトル**- ルールによってトリガーされたアラートで表示されるタイトル
- **重大度**—ルールによって識別されるコンポーネントまたはアクティビティの潜在的なリスク
- **Category**—ルールによって識別される脅威コンポーネントまたはアクティビティ
- **MITRE ATT&CK** の手法 (CK フレームワークの [MITRE ATT](https://attack.mitre.org/)に記載されているルールによって識別される 1 つ以上の攻撃&です。 このセクションは、マルウェア、ランサムウェア、疑わしいアクティビティ、望ましくないソフトウェアなど、特定のアラート カテゴリでは非表示になっています。
- **Description**—ルールによって識別されるコンポーネントまたはアクティビティの詳細 
- **推奨されるアクション**—応答者がアラートに応答して実行する可能性がある追加のアクション

#### <a name="rule-frequency"></a>ルールの頻度
新しいルールを保存すると、過去 30 日間のデータの一致が実行され、チェックされます。 その後、ルールは一定の間隔で再び実行され、選択した頻度に基づいてルックバック期間が適用されます。

- **24 時間ごとに** 実行され、過去 30 日間のデータを確認します。
- **12 時間ごとに** 実行され、過去 24 時間のデータを確認します。
- **3 時間ごとに** 実行され、過去 6 時間のデータを確認します。
- **1 時間** ごとに 1 時間ごとに実行され、過去 2 時間のデータを確認します。

ルールを編集すると、設定した頻度に従ってスケジュールされた次の実行時に適用された変更と一緒に実行されます。



>[!TIP]
> クエリのタイム フィルターとルックバック期間を一致します。 ルックバック期間外の結果は無視されます。  

検出を監視する頻度に一致する頻度を選択します。 通知に応答する組織の容量を検討します。

### <a name="3-choose-the-impacted-entities"></a>3. 影響を受け取ったエンティティを選択します。
影響を受ける主なエンティティまたは影響を受けるエンティティを検索するクエリ結果の列を特定します。 たとえば、クエリが送信者 (または) アドレスと受信者 `SenderFromAddress` `SenderMailFromAddress` ( ) アドレスを `RecipientEmailAddress` 返す場合があります。 これらの列の中で、影響を受ける主なエンティティを表す列を特定すると、サービスは関連するアラートの集計、インシデントの関連付け、およびターゲット応答アクションの集計に役立ちます。

エンティティの種類 (メールボックス、ユーザー、またはデバイス) ごとに 1 つの列のみを選択できます。 クエリによって返されない列は選択できません。

### <a name="4-specify-actions"></a>4. アクションを指定します。
カスタム検出ルールは、クエリによって返されるデバイス、ファイル、またはユーザーに対して自動的にアクションを実行できます。

#### <a name="actions-on-devices"></a>デバイスでのアクション
これらのアクションは、クエリ結果の列 `DeviceId` のデバイスに適用されます。
- **デバイスの分離**—Microsoft Defender for Endpoint を使用して完全なネットワーク分離を適用し、デバイスが任意のアプリケーションまたはサービスに接続できません。 [Microsoft Defender for Endpoint マシンの分離の詳細](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **調査パッケージの収集**— ZIP ファイル内のデバイス情報を収集します。 [Microsoft Defender for Endpoint 調査パッケージの詳細](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **ウイルス対策スキャンの実行**- デバイスでWindows Defender ウイルス対策スキャンを実行します。
- **調査を開始** する -デバイス [で自動調査](m365d-autoir.md) を開始する
- **アプリの実行を制限** する :Microsoft 発行の証明書で署名されたファイルのみを実行できるデバイスの制限を設定します。 [Microsoft Defender for Endpoint でのアプリ制限の詳細](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>ファイルに対するアクション
選択すると、クエリ結果の 、または列のファイルに対して [ファイルの検疫] `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` アクションを適用できます。 このアクションでは、ファイルを現在の場所から削除し、コピーを検疫に入れる。

#### <a name="actions-on-users"></a>ユーザーに対するアクション
選択すると、クエリ結果の **、、** または列のユーザーに対してユーザーに対して [侵害されたユーザーとしてマーク] `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` アクションが実行されます。 このアクションは、ユーザーのリスク レベルをユーザーのリスク レベルを Azure Active Directoryに設定し、対応する ID 保護[ポリシーをトリガーします](/azure/active-directory/identity-protection/overview-identity-protection)。

> [!NOTE]
> カスタム検出ルールの許可またはブロックアクションは、現在、ユーザー設定でMicrosoft 365 Defender。

### <a name="5-set-the-rule-scope"></a>5. ルールスコープを設定します。
スコープを設定して、ルールの対象となるデバイスを指定します。 このスコープは、デバイスをチェックするルールに影響を与え、メールボックスとユーザー アカウントまたは ID のみをチェックするルールには影響を与えます。

スコープを設定する場合は、次の項目を選択できます。

- すべてのデバイス
- 特定のデバイス グループ

スコープ内のデバイスからのデータだけがクエリされます。 また、これらのデバイスでのみアクションが実行されます。

### <a name="6-review-and-turn-on-the-rule"></a>6. ルールを確認して有効にする。
ルールを確認した後、[作成] **を選択して** 保存します。 カスタム検出ルールが直ちに実行されます。 構成された頻度に基づいて再び実行され、一致を確認し、アラートを生成し、応答アクションを実行します。


>[!Important] 
>カスタム検出は、効率と有効性を定期的に確認する必要があります。 真のアラートをトリガーする検出を作成するには、「既存のカスタム検出ルールの管理」の手順に従って、既存のカスタム検出を確認する時間 [を取ってください](#manage-existing-custom-detection-rules)。 <br>  
カスタム検出の広さまたは特定性を制御し、カスタム検出によって生成された誤った通知がルールの特定のパラメーターを変更する必要を示す場合があります。


## <a name="manage-existing-custom-detection-rules"></a>既存のカスタム検出ルールの管理
既存のカスタム検出ルールの一覧を表示し、以前の実行を確認し、トリガーしたアラートを確認できます。 必要に応じてルールを実行して変更できます。

>[!TIP]
> カスタム検出によって発生したアラートは、アラートとインシデント API で利用できます。 詳細については[、「Supported Microsoft 365 Defender API」を参照してください](api-supported.md)。

### <a name="view-existing-rules"></a>既存のルールの表示

既存のすべてのカスタム検出ルールを表示するには、[ハンティングカスタム検出  >  **] に移動します**。 ページには、次の実行情報を含むすべてのルールが一覧表示されます。

- **Last run**—クエリの一致を確認し、アラートを生成するルールが最後に実行された場合
- **最終実行の状態**:ルールが正常に実行されたかどうか
- **次の実行**— 次のスケジュールされた実行
- **Status**—ルールが有効または無効になっているかどうか

### <a name="view-rule-details-modify-rule-and-run-rule"></a>ルールの詳細の表示、ルールの変更、およびルールの実行

カスタム検出ルールに関する包括的な情報を表示するには、[ハンティング カスタム検出] に移動し、ルールの  >  名前を選択します。 その後、ルールの実行状態とスコープに関する情報を含む、ルールに関する一般的な情報を表示できます。 このページには、トリガーされたアラートとアクションの一覧も表示されます。

![カスタム検出ルールの詳細ページ。](../../media/custom-detection-details.png)<br>
*カスタム検出ルールの詳細*

また、このページからルールに対して次のアクションを実行することもできます。

- **Run**—ルールを直ちに実行します。 これにより、次の実行の間隔もリセットされます。
- **Edit**—クエリを変更せずにルールを変更する
- **クエリの変更**—高度な検索でクエリを編集する
- **有効にする**  / **無効にする**-ルールを有効にするか、ルールの実行を停止する
- **Delete**—ルールをオフにし、削除する

### <a name="view-and-manage-triggered-alerts"></a>トリガーされたアラートの表示と管理

ルールの詳細画面 (**ハンティング** カスタム検出 [ルール名]) で、[トリガーされたアラート] に移動し、ルールに一致して生成されたアラート  >    >  を一覧表示します。  アラートを選択して、アラートに関する詳細情報を表示し、次のアクションを実行します。

- 状態と分類を設定してアラートを管理する (true または false アラート)
- アラートをインシデントにリンクする
- 高度な検索でアラートをトリガーしたクエリを実行する

### <a name="review-actions"></a>アクションを確認する
ルールの詳細画面 (**ハンティング** カスタム検出 [ルール名]) で、[トリガーされたアクション] に移動し、ルールとの一致に基づいて実行されるアクションを  >    >  一覧表示します。 

>[!TIP]
>テーブル内のアイテムに関する情報をすばやく表示し、アクションを実行するには、表の左側にある [&#10003;] の選択列を使用します。

>[!NOTE]
>この記事の一部の列は、Microsoft Defender for Endpoint では使用できない場合があります。 [複数のデータ Microsoft 365 Defender](m365d-enable.md)を使用して脅威を検出するには、このオプションをオンにしてください。 高度なハンティング ワークフローを Microsoft Defender for Endpoint から Microsoft 365 Defenderに移動するには、「Advanced Hunting [queries](advanced-hunting-migrate-from-mde.md)を Microsoft Defender for Endpoint から移行する」の手順に従います。

## <a name="see-also"></a>関連項目
- [カスタム検出の概要](custom-detections-overview.md)
- [高度な追求の概要](advanced-hunting-overview.md)
- [高度な捜索のクエリ言語について学習する](advanced-hunting-query-language.md)
- [Microsoft Defender for Endpoint から高度なハンティング クエリを移行する](advanced-hunting-migrate-from-mde.md)
