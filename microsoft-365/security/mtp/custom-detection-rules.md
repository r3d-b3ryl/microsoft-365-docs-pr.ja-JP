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
# <a name="create-and-manage-custom-detections-rules"></a>カスタム検出ルールを作成および管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

カスタム検出ルールは、高度なハンティング クエリを使用して設計および [調整できるルール](advanced-hunting-overview.md) です。 これらのルールを使用すると、侵害の疑いのあるアクティビティやエンドポイントの構成ミスなど、さまざまなイベントやシステム状態を事前に監視できます。 一致する場合は常に、一定の間隔で実行し、アラートを生成し、対応アクションを実行する設定を行うことができます。

## <a name="required-permissions-for-managing-custom-detections"></a>カスタム検出を管理するために必要なアクセス許可

カスタム検出を管理するには、次の役割のいずれかを割り当てる必要があります。

- **セキュリティ管理者**— この [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) ロールを持つユーザーは、Microsoft 365 セキュリティ センターや他のポータルやサービスでセキュリティ設定を管理できます。

- **セキュリティ オペレーター**— この [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) ロールを持つユーザーは、アラートを管理し、Microsoft 365 セキュリティ センターのすべての情報を含む、セキュリティ関連の機能へのグローバルな読み取り専用アクセス権を持っています。 この役割は、Microsoft Defender for Endpoint で役割ベースのアクセス制御 (RBAC) がオフになっている場合にのみ、カスタム検出を管理するのに十分です。 RBAC を構成している場合は、エンドポイント用 Defender のセキュリティ設定 **の** 管理アクセス許可も必要です。

必要なアクセス許可を管理するには、グローバル **管理者は次の方法を実行** できます。

- ロール セキュリティ **管理者の下で**[、Microsoft 365](https://admin.microsoft.com/)管理センターでセキュリティ管理者またはセキュリティオペレーター **の役割**  >  **を割り当てます**。
- Microsoft Defender セキュリティ センターの [設定のアクセス許可の役割] で [、Microsoft Defender](https://securitycenter.windows.com/) for Endpoint の RBAC **設定**  >  **を確認**  >  **します**。 対応する役割を選択して、セキュリティ設定の **管理アクセス許可を割り当** てる。

> [!NOTE]
> カスタム検出を管理するには、RBAC が有効になっている場合、セキュリティオペレーターは Microsoft Defender for Endpoint のセキュリティ設定の管理アクセス許可を必要とします。 

## <a name="create-a-custom-detection-rule"></a>カスタム検出ルールを作成する
### <a name="1-prepare-the-query"></a>1. クエリを準備します。

Microsoft 365 セキュリティ センターで、[高度な検索] に移動 **し、既存** のクエリを選択するか、新しいクエリを作成します。 新しいクエリを使用する場合は、クエリを実行してエラーを特定し、考えられる結果を把握します。

>[!IMPORTANT]
>サービスが返すアラートの数が多すぎるのを防ぐため、各ルールは、実行されるたびに生成されるアラートを 100 件に制限しています。 ルールを作成する前に、通常の毎日のアクティビティに対する警告を回避するためにクエリを調整してください。


#### <a name="required-columns-in-the-query-results"></a>クエリ結果に必要な列
カスタム検出ルールを作成するには、クエリが次の列を返す必要があります。

- `Timestamp`— 生成されたアラートのタイムスタンプを設定するために使用されます。
- `ReportId`—元のレコードの参照を有効にする
- 特定のデバイス、ユーザー、またはメールボックスを識別する次のいずれかの列:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (エンベロープ送信者またはReturn-Pathアドレス)
    - `SenderMailFromAddress` (メール クライアントによって表示される送信者アドレス)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>新しいテーブルが高度な検索スキーマに追加された場合、追加のエンティティ [のサポートが追加されます](advanced-hunting-schema-tables.md)。

結果のカスタマイズや集計に演算子を使用しないクエリなどの単純なクエリは、通常、これらの一般的な列 `project` `summarize` を返します。

より複雑なクエリがこれらの列を返すのを確実にするためのさまざまな方法があります。 たとえば、次のような列の下のエンティティで集計してカウントする場合でも、一意の各イベントが関係する最新のイベントから取得して取得 `DeviceId` `Timestamp` `ReportId` できます `DeviceId` 。

次のサンプル クエリでは、ウイルス対策が検出された一意のデバイス ( ) の数をカウントし、このカウントを使用して、5 つを超える検出を持つデバイスのみを `DeviceId` 検索します。 最新の関数と `Timestamp` 対応する関数を返す場合は `ReportId` 、 `summarize` 演算子を使用 `arg_max` します。

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> クエリのパフォーマンスを向上するには、ルールの実行頻度に一致する時間フィルターを設定します。 実行頻度が最も少ないのは _24_ 時間ごとに行われるので、過去 1 日のフィルター処理ではすべての新しいデータが処理されます。

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. 新しいルールを作成し、アラートの詳細を提供します。

クエリ エディターでクエリを使用して、[検出ルールの作成] を選択 **し、次** のアラートの詳細を指定します。

- **検出名**— 検出ルールの名前
- **頻度**— クエリを実行してアクションを実行する間隔。 [以下の追加のガイダンスを参照してください。](#rule-frequency)
- **アラートタイトル**- ルールによってトリガーされたアラートと一緒に表示されるタイトル
- **重大度 —** ルールによって識別されるコンポーネントまたはアクティビティの潜在的なリスク
- **カテゴリ**— ルールによって識別される脅威コンポーネントまたはアクティビティ
- **MITRE ATT&CK** の手法 [—MITRE ATT](https://attack.mitre.org/)と CK フレームワークに記載されているルールによって識別される 1 つ以上の攻撃&手法です。 このセクションは、マルウェア、ランサムウェア、疑わしいアクティビティ、望ましくないソフトウェアなど、特定のアラート カテゴリでは表示されません。
- **説明**— ルールによって識別されるコンポーネントまたはアクティビティに関する詳細 
- **推奨されるアクション**— アラートに応答してレスポンダーが実行する可能性がある追加のアクション

#### <a name="rule-frequency"></a>ルールの頻度
新しいルールを保存または編集すると、そのルールが実行され、過去 30 日間のデータの一致が確認されます。 その後、ルールは一定の間隔で再び実行され、選択した頻度に基づいてルックバック期間が適用されます。

- **24 時間** ごとに -24 時間ごとに実行され、過去 30 日間のデータをチェックします
- **12 時間ごとに**-12 時間ごとに実行され、過去 24 時間のデータをチェックします
- **3 時間ごとに**-3 時間ごとに実行され、過去 6 時間のデータをチェックします
- **1 時間** ごとに実行され、過去 2 時間のデータをチェックします。

>[!TIP]
> クエリ内の時間フィルターを、ルックバック期間と一致します。 ルックバック期間外の結果は無視されます。  

検出を監視する頻度と一致する頻度を選択します。 アラートに対応する組織の能力を考慮します。

### <a name="3-choose-the-impacted-entities"></a>3. 影響を受け取るエンティティを選択します。
影響を受ける主なエンティティまたは影響を受けるエンティティを検索すると予想されるクエリ結果の列を特定します。 たとえば、クエリは送信者 (または) アドレスと受信者 ( ) アドレス `SenderFromAddress` `SenderMailFromAddress` `RecipientEmailAddress` を返します。 影響を受ける主なエンティティを表す列を特定すると、サービスが関連するアラートの集計、インシデントの関連付け、および対象の対応アクションを行うのに役立ちます。

エンティティの種類 (メールボックス、ユーザー、またはデバイス) ごとに 1 つの列のみを選択できます。 クエリによって返されない列は選択できません。

### <a name="4-specify-actions"></a>4. アクションを指定します。
カスタム検出ルールは、クエリによって返されるデバイス、ファイル、またはユーザーに対して自動的にアクションを実行できます。

#### <a name="actions-on-devices"></a>デバイスでのアクション
これらのアクションは、クエリ結果の列にある `DeviceId` デバイスに適用されます。
- **デバイスの分離**— Microsoft Defender for Endpoint を使用して完全なネットワーク分離を適用し、デバイスがアプリケーションまたはサービスに接続しなくします。 [Microsoft Defender for Endpoint コンピューターの分離の詳細](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **調査パッケージの収集**- ZIP ファイル内のデバイス情報を収集します。 [Microsoft Defender for Endpoint 調査パッケージの詳細](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **ウイルス対策スキャンの** 実行 - デバイスでフル Windows Defenderウイルス対策スキャンを実行します
- **調査の開始**- デバイスで [自動調査](mtp-autoir.md) を開始する
- **アプリの実行を** 制限する - Microsoft が発行する証明書で署名されたファイルのみを実行できるデバイスの制限を設定します。 [Microsoft Defender for Endpoint でのアプリの制限について詳しくは、次をご覧ください。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>ファイルに対するアクション
選択すると、クエリ結果の [,  , ] () 列にあるファイルに検疫ファイルアクション `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` を適用できます。 この操作により、ファイルが現在の場所から削除され、コピーが検疫されます。

#### <a name="actions-on-users"></a>ユーザーに対するアクション
このオプションを選択すると、クエリ **結果** の [, ] 列にあるユーザーに対して [侵害されたユーザーとしてマークする `AccountObjectId` ] `InitiatingProcessAccountObjectId` `RecipientObjectId` アクションが実行されます。 このアクションは、Azure Active Directory でユーザーのリスク レベルを "高" に設定し、対応する ID 保護ポリシー [をトリガーします](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。

> [!NOTE]
> カスタム検出ルールの許可またはブロックのアクションは、Microsoft 365 Defender では現在サポートされていません。

### <a name="5-set-the-rule-scope"></a>5. ルールの範囲を設定します。
ルールの対象となるデバイスを指定するスコープを設定します。 このスコープは、デバイスをチェックするルールに影響し、メールボックスとユーザー アカウントまたは ID のみをチェックするルールには影響を与えます。

スコープを設定する場合は、次の項目を選択できます。

- すべてのデバイス
- 特定のデバイス グループ

範囲内のデバイスからのデータのみを照会します。 また、これらのデバイスでのみアクションが実行されます。

### <a name="6-review-and-turn-on-the-rule"></a>6. ルールを確認して有効にする。
ルールを確認した後、[作成] を **選択して** 保存します。 カスタム検出ルールが直ちに実行されます。 一致を確認し、アラートを生成し、対応アクションを実行するように構成された頻度に基づいて、再び実行されます。

## <a name="manage-existing-custom-detection-rules"></a>既存のカスタム検出ルールを管理する
既存のカスタム検出ルールの一覧の表示、以前の実行の確認、トリガーされたアラートの確認を行えます。 必要に応じてルールを実行して変更できます。

### <a name="view-existing-rules"></a>既存のルールを表示する

既存のすべてのカスタム検出ルールを表示するには、[**ハン** ティング カスタム検出  >  **] に移動します**。 このページには、次の実行情報を含むすべてのルールが一覧表示されます。

- **最後の実行**- クエリの一致をチェックしてアラートを生成するルールが最後に実行された場合
- **最終実行状態**— ルールが正常に実行されたかどうか
- **次の実行**— 次にスケジュールされた実行
- **状態**- ルールが有効または無効になっているかどうか

### <a name="view-rule-details-modify-rule-and-run-rule"></a>ルールの詳細の表示、ルールの変更、およびルールの実行

カスタム検出ルールに関する包括的な情報を表示するには、[**検索** カスタム検出] に移動し、ルール  >  の名前を選択します。 その後、ルールに関する一般的な情報 (実行状態や範囲に関する情報など) を表示できます。 このページには、トリガーされたアラートとアクションの一覧も表示されます。

![カスタム検出ルールの詳細ページ](../../media/custom-detection-details.png)<br>
*カスタム検出ルールの詳細*

このページからルールに対して次のアクションを実行することもできます。

- **Run**-run the rule immediately. これにより、次の実行の間隔もリセットされます。
- **Edit**- クエリを変更せずにルールを変更する
- **クエリの変更**- 高度な検索でクエリを編集する
- **オンにする**  / **無効にする**- ルールを有効にするか、ルールの実行を停止する
- **削除**- ルールをオフにし、削除する

### <a name="view-and-manage-triggered-alerts"></a>トリガーされたアラートの表示と管理

In the rule details screen (**Hunting**  >  **Custom detections**  >  **[Rule name]**), go to **Triggered alerts,** which lists the alerts generated by matches to the rule. アラートを選択してアラートに関する詳細情報を表示し、次のアクションを実行します。

- アラートの状態と分類を設定してアラートを管理する (true または false のアラート)
- アラートをインシデントにリンクする
- 高度な検索でアラートをトリガーしたクエリを実行する

### <a name="review-actions"></a>アクションを確認する
In the rule details screen (**Hunting**  >  **Custom detections**  >  **[Rule name]**), go to **Triggered actions,** which lists the actions taken based on matches to the rule.

>[!TIP]
>テーブル内のアイテムに関する情報をすばやく表示してアクションを実行するには、表の左側にある選択列 [&#10003;] を使用します。

## <a name="see-also"></a>関連項目
- [カスタム検出の概要](custom-detections-overview.md)
- [高度な検出の概要](advanced-hunting-overview.md)
- [高度な捜索のクエリ言語について学習する](advanced-hunting-query-language.md)
- [Microsoft Defender for Endpoint から高度な検索クエリを移行する](advanced-hunting-migrate-from-mdatp.md)
