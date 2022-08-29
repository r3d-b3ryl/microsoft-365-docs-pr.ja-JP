---
title: Microsoft 365 Defenderでカスタム検出ルールを作成および管理する
description: 高度なハンティング クエリに基づいてカスタム検出ルールを作成および管理する方法について説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, カスタム検出, ルール, スキーマ, kusto, RBAC, アクセス許可, Microsoft Defender for Endpoint
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0bc0ff6c0ccd9013685ff59e2ce3f12745a7e82e
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387025"
---
# <a name="create-and-manage-custom-detections-rules"></a>カスタム検出ルールを作成および管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

カスタム検出ルールは、 [高度なハンティング](advanced-hunting-overview.md) クエリを使用して設計および調整できるルールです。 これらのルールを使用すると、侵害の疑いのあるアクティビティや誤った構成されたエンドポイントなど、さまざまなイベントやシステム状態を事前に監視できます。 一定の間隔で実行し、アラートを生成しながら一致するたびに応答アクションを実行するように設定できます。

## <a name="required-permissions-for-managing-custom-detections"></a>カスタム検出を管理するのに必要なアクセス許可

カスタム検出を管理するには、次の役割の割り当てのうちどれかが必要になります。

- **セキュリティ管理者** - この [Azure Active Directory ロール](/azure/active-directory/roles/permissions-reference#security-administrator)を持つユーザーは、Microsoft 365 Defender ポータルや他のポータルやサービスでセキュリティ設定を管理できます。

- **セキュリティ オペレーター** - この [Azure Active Directory ロール](/azure/active-directory/roles/permissions-reference#security-operator)を持つユーザーは、アラートを管理し、Microsoft 365 Defender ポータル内のすべての情報を含む、セキュリティ関連の機能へのグローバルな読み取り専用アクセス権を持つことができます。 このロールは、ロールベースのアクセス制御 (RBAC) がMicrosoft Defender for Endpointでオフになっている場合にのみ、カスタム検出を管理するのに十分です。 RBAC を構成している場合は、Defender for Endpoint の **セキュリティ設定の管理** アクセス許可も必要です。

また、アクセス許可がある場合は、特定のMicrosoft 365 Defender ソリューションのデータに適用されるカスタム検出を管理することもできます。 たとえば、Office のMicrosoft 365 Defenderに対する管理アクセス許可のみを持っている場合は、テーブルではなくテーブル`Identity`を使用してカスタム検出を`Email`作成できます。  

必要なアクセス許可を管理するために、 **グローバル管理者** は次のことができます。

- [**ロールのセキュリティ管理者]** の下にある [Microsoft 365 管理センター](https://admin.microsoft.com/)で **、セキュリティ管理者またはセキュリティ** **オペレーター****ロールを** > 割り当てます。
- Microsoft 365 Defenderの [設定 **のアクセス許可** ロール] で [、Microsoft Defender for Endpoint](https://security.microsoft.com/)の RBAC **設定を** >  > 確認 **します**。 対応するロールを選択して、 **セキュリティ設定の管理** アクセス許可を割り当てます。

> [!NOTE]
> カスタム検出を管理するには、RBAC が有効になっている場合、**セキュリティオペレーター** はMicrosoft Defender for Endpointの **セキュリティ設定の管理** アクセス許可を必要とします。

## <a name="create-a-custom-detection-rule"></a>カスタム検出ルールを作成する
### <a name="1-prepare-the-query"></a>1. クエリを準備します。

Microsoft 365 Defender ポータルで、**高度な検索** に移動し、既存のクエリを選択するか、新しいクエリを作成します。 新しいクエリを使用する場合は、クエリを実行してエラーを特定し、あり得る結果を想定します。

>[!IMPORTANT]
>サービスでアラートの数が多くなりすぎないように、各ルールの実行時に生成されるアラートは 100 個に制限されています。 ルールを作成する前に、クエリを調整して、通常の毎日のアクティビティに対してアラートが生成されないようにします。


#### <a name="required-columns-in-the-query-results"></a>クエリ結果に必要な列
カスタム検出ルールを作成するには、クエリで次の列を返す 必要があります。

- `Timestamp`—生成されたアラートのタイムスタンプを設定するために使用されます
- `ReportId`—元のレコードの参照を有効にします
- 特定のデバイス、ユーザー、またはメールボックスを識別する次のいずれかの列。
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (封筒送信者または Return-Path アドレス)
    - `SenderMailFromAddress` (メール クライアントによって表示される送信者アドレス)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>新しいテーブルが [高度なハンティング スキーマ](advanced-hunting-schema-tables.md)に追加されると、追加のエンティティのサポートが追加されます。

結果をカスタマイズまたは集計するために演算子を`summarize`使用`project`しないクエリなど、単純なクエリは、通常、これらの一般的な列を返します。

より複雑なクエリがこれらの列を返すようにするには、さまざまな方法があります。 たとえば、列の下にエンティティを集計してカウントする場合など`DeviceId`、各一意`DeviceId`のイベントを含む最新のイベントから取得して返`Timestamp``ReportId`すことができます。


> [!IMPORTANT]
> 列を使用して `Timestamp` カスタム検出をフィルター処理しないでください。 カスタム検出に使用されるデータは、検出頻度に基づいて事前にフィルター処理されます。


次のサンプル クエリでは、ウイルス対策検出を含む一意のデバイス (`DeviceId`) の数をカウントし、この数を使用して、5 つを超える検出を持つデバイスのみを検索します。 最新 `Timestamp` の関数と対応する `ReportId`演算子を返すには、関数と共に `summarize` 演算子を `arg_max` 使用します。

```kusto
DeviceEvents
| where ingestion_time() > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> クエリのパフォーマンスを向上させるには、ルールの目的の実行頻度に一致する時間フィルターを設定します。 最も頻度の低い実行は _24 時間ごとに_ 行われるので、過去 1 日のフィルター処理ではすべての新しいデータが対象になります。

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. 新しいルールを作成し、アラートの詳細を指定します。

クエリ エディターでクエリを使用して、[ **検出ルールの作成** ] を選択し、次のアラートの詳細を指定します。

- **検出名** - 検出ルールの名前。は一意である必要があります
- **頻度** - クエリを実行してアクションを実行するための間隔。 [以下の追加のガイダンスを参照してください](#rule-frequency)
- **アラート タイトル** - ルールによってトリガーされたアラートで表示されるタイトル。は一意である必要があります
- **重大度** - ルールによって識別されたコンポーネントまたはアクティビティの潜在的なリスク
- **カテゴリ** - ルールによって識別される脅威コンポーネントまたはアクティビティ
- **MITRE ATT&CK 手法**。 [MITRE ATT&CK フレームワーク](https://attack.mitre.org/)に記載されているように、ルールによって識別される 1 つ以上の攻撃手法。 このセクションは、マルウェア、ランサムウェア、不審なアクティビティ、不要なソフトウェアなど、特定のアラート カテゴリでは非表示です
- **説明** - ルールによって識別されるコンポーネントまたはアクティビティに関する詳細情報 
- **推奨されるアクション** - レスポンダーがアラートに応答して実行する可能性がある追加のアクション

#### <a name="rule-frequency"></a>ルールの頻度
新しいルールを保存すると、過去 30 日間のデータの一致が実行され、チェックされます。 その後、ルールは一定間隔で再度実行され、選択した頻度に基づいてルックバック期間が適用されます。

- **24 時間ごと** —24 時間ごとに実行され、過去 30 日間のデータを確認します
- **12 時間ごと** —12 時間ごとに実行され、過去 24 時間のデータを確認します
- **3 時間ごと** —3 時間ごとに実行され、過去 6 時間のデータを確認します
- **1 時間ごとに** 実行され、過去 2 時間のデータを確認します

ルールを編集すると、設定した頻度に従ってスケジュールされた次の実行時に、適用する変更と一緒に実行されます。 ルールの頻度は、インジェスト時間ではなく、イベント タイムスタンプに基づいています。



>[!TIP]
> クエリ内の時間フィルターをルックバック期間と一致させます。 ルックバック期間の範囲外の結果は無視されます。  

検出を監視する頻度に一致する頻度を選択します。 アラートに応答する組織の能力を検討してください。

### <a name="3-choose-the-impacted-entities"></a>3. 影響を受けたエンティティを選択します。
主な影響、影響を受けたエンティティを見つけるクエリ結果の列を特定します。 たとえば、クエリは送信者 (`SenderFromAddress` または `SenderMailFromAddress`) アドレスと受信者 (`RecipientEmailAddress`) アドレスを返す場合があります。 これらの列の中で影響を受ける主なエンティティがある列を特定すると、サービスで関連するアラートの集計、インシデントの関連付け、応答アクションのターゲットができるようになります。

エンティティの種類 (メールボックス、ユーザー、またはデバイス) ごとに 1 つの列のみを選択できます。 クエリによって返すことができない列は選択できません。

### <a name="4-specify-actions"></a>4. アクションを指定します。
カスタム検出ルールで、クエリによって返されるデバイス、ファイル、またはユーザーに対して自動的にアクションを実行できます。

#### <a name="actions-on-devices"></a>デバイスでのアクション
これらのアクションは、クエリ結果の列 `DeviceId` にあるデバイスに適用されます。
- **デバイスを分離**—Microsoft Defender for Endpointを使用して完全なネットワーク分離を適用し、デバイスがアプリケーションまたはサービスに接続できないようにします。 [コンピューターの分離Microsoft Defender for Endpoint詳細を確認する](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **調査パッケージを収集** する - ZIP ファイル内のデバイス情報を収集します。 [Microsoft Defender for Endpoint調査パッケージの詳細を確認する](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **ウイルス対策スキャンを実行** する — デバイスで Microsoft Defender ウイルス対策の完全なスキャンを実行します
- **調査を開始**—デバイスで [自動調査](m365d-autoir.md) を開始します。
- **アプリの実行を制限** する - Microsoft 発行の証明書で署名されたファイルのみを実行できるように、デバイスに対する制限を設定します。 [Microsoft Defender for Endpointを使用したアプリの制限の詳細](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>ファイルへのアクション
選択すると、クエリ結果の 、または`InitiatingProcessSHA256`列内の **ファイル** に`SHA1``InitiatingProcessSHA1``SHA256`検疫ファイル アクションを適用することを選択できます。 このアクションでは、ファイルが現在ある場所から削除され、コピーが検疫に入ります。

#### <a name="actions-on-users"></a>ユーザーへのアクション
選択されると、**ユーザーを侵害済みにする** アクションをクエリ結果の `AccountObjectId`、`InitiatingProcessAccountObjectId`、または `RecipientObjectId` 列にあるユーザーに適用することができます。 このアクションにより、Azure Active Directory でユーザーのリスク レベルが "高" に設定され、対応する [ID 保護ポリシー](/azure/active-directory/identity-protection/overview-identity-protection)がトリガーされます。

> [!NOTE]
> 現在、カスタム検出ルールの許可またはブロックアクションは、Microsoft 365 Defenderではサポートされていません。

### <a name="5-set-the-rule-scope"></a>5. ルールスコープを設定します。
範囲を設定してルールの対象となるデバイスを指定します。 この範囲で、デバイスをチェックするルールが影響されますが、メールボックスのみをチェックするルールやユーザー アカウントまたは ID のみをチェックするルールには影響はありません。

範囲を設定する場合は、次の項目を選択できます。

- すべてのデバイス
- 特定のデバイス グループ

範囲内のデバイスからのデータだけがクエリされます。 また、これらのデバイスでのみアクションが実行されます。

### <a name="6-review-and-turn-on-the-rule"></a>6. ルールを確認して有効にします。
ルールを確認した後、**[作成]** を選択して保存します。 カスタム検出ルールが直ちに実行されます。 構成された頻度に基づいて再度実行され、一致の確認後アラートが生成されると応答アクションが実行されます。


>[!Important] 
>効率性と有効性については、カスタム検出を定期的に確認する必要があります。 真のアラートをトリガーする検出を作成していることを確認するには、「既存のカスタム検出ルールを管理する」の手順に従って [、時間をかけて既存のカスタム検出](#manage-existing-custom-detection-rules)を確認します。 <br>  
カスタム検出によって生成された誤ったアラートがルールの特定のパラメーターを変更する必要があることを示すように、カスタム検出の広さまたは固有性を制御します。


## <a name="manage-existing-custom-detection-rules"></a>既存のカスタム検出ルールを管理する
既存のカスタム検出ルールの一覧を表示し、以前の実行を確認し、トリガーしたアラートを確認できます。 また、ルールをオンデマンドで実行して変更することもできます。

>[!TIP]
> カスタム検出によって発生したアラートは、アラートとインシデント API を介して使用できます。 詳細については、「[サポートされているMicrosoft 365 Defender API」を参照してください](api-supported.md)。

### <a name="view-existing-rules"></a>既存のルールを表示する

既存のすべてのカスタム検出ルールを表示するには、 **ハンティング** > **カスタム検出ルール** に移動します。 ページには、次の実行情報を含むすべてのルールが一覧表示されます。

- **最終実行** - ルールが最後に実行され、クエリの一致を確認し、アラートを生成した場合
- **最終実行状態** -ルールが正常に実行されたかどうか
- **次の実行** -次にスケジュールされた実行
- **状態** - ルールがオンまたはオフになっているかどうか

### <a name="view-rule-details-modify-rule-and-run-rule"></a>ルールの詳細の表示、ルールの変更、およびルールの実行

カスタム検出ルールに関する包括的な情報を表示するには、カスタム **検出ルール** の **検索** > に移動し、ルールの名前を選択します。 その後、ルールの実行状態と範囲に関する情報など、ルールに関する一般的な情報を確認することができます。 このページには、トリガーされたアラートとアクションの一覧も表示されます。

:::image type="content" source="../../media/custom-detect-rules-view.png" alt-text="Microsoft 365 Defender ポータルの [カスタム検出ルールの詳細] ページ" lightbox="../../media/custom-detect-rules-view.png":::<br>
*カスタム検出ルールの詳細*

また、このページからルールに対して次のアクションを実行することもできます。

- **[実行**] - すぐにルールを実行します。 これにより、次の実行の間隔もリセットされます。
- **編集** - クエリを変更せずにルールを変更する
- **クエリを変更** する - 高度なハンティングでクエリを編集する
- **オンにする** / **[オフ]** - ルールを有効にするか、実行を停止します
- **削除** - ルールをオフにして削除する

### <a name="view-and-manage-triggered-alerts"></a>トリガーされたアラートを表示して管理する

[ルールの詳細] 画面 ([**カスタム検出** > の **検索** > **][ルール名]) で**、[**トリガーされたアラート**] に移動します。このアラートには、ルールに一致して生成されたアラートが一覧表示されます。 アラートを選択して、アラートに関する詳細情報を表示し、次のアクションを実行します。

- 状態と分類 (true または false アラート) を設定してアラートを管理する
- アラートをインシデントにリンクする
- 高度な捜索でアラートをトリガーしたクエリを実行する

### <a name="review-actions"></a>アクションを確認する
[ルールの詳細] 画面 ([**カスタム検出** > の **検索** > **][ルール名]) で**、[**トリガーされたアクション**] に移動します。このアクションには、ルールに対する一致に基づいて実行されたアクションが一覧表示されます。

>[!TIP]
>テーブル内の項目に対して情報をすばやく表示し、アクションを実行するには、テーブルの左側にある選択列 [&#10003;] を使用します。

>[!NOTE]
>この記事の一部の列は、Microsoft Defender for Endpointでは使用できない場合があります。 [Microsoft 365 Defenderを有効にして](m365d-enable.md)、より多くのデータ ソースを使用して脅威を検出します。 高度なハンティング クエリをMicrosoft Defender for Endpointから移行するの手順に従って、[高度なハンティング ワークフローをMicrosoft Defender for EndpointからMicrosoft 365 Defender](advanced-hunting-migrate-from-mde.md)に移動できます。

## <a name="see-also"></a>関連項目
- [カスタム検出の概要](custom-detections-overview.md)
- [高度な追求の概要](advanced-hunting-overview.md)
- [高度な捜索のクエリ言語について学習する](advanced-hunting-query-language.md)
- [高度なハンティング クエリをMicrosoft Defender for Endpointから移行する](advanced-hunting-migrate-from-mde.md)
