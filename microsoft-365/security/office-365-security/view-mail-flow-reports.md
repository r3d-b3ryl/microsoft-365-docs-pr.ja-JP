---
title: セキュリティ/コンプライアンス センターのメールフローレポートを表示
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 組織のメールフローセキュリティレポートを検索して使用する方法について説明します。 メールフローレポートは、セキュリティ & コンプライアンスセンターで利用できます。
ms.custom: ''
ms.openlocfilehash: e891d9373b169dc01cfd89f114e31b23e1bd8480
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434181"
---
# <a name="view-mail-flow-reports-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターのメールフローレポートを表示

セキュリティ & コンプライアンスセンターで利用できる[メールフローの洞察](mail-flow-insights-v2.md)に加えて、さまざまなメールフローレポートを使用して、Microsoft 365 組織の監視に役立てることもできます。 [必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合は、 <https://office.protection.com> **レポート**ダッシュボードにアクセスすることで、これらのレポートをセキュリティ & コンプライアンスセンターで表示でき \> **Dashboard**ます。 レポートダッシュボードに直接移動するには、を開き <https://office.protection.office.com/insightdashboard> ます。

![セキュリティ & コンプライアンスセンターのレポートダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>コネクタレポート

**コネクタレポート**には、組織に対して構成されている[受信コネクタと送信コネクタ](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)のメールフローアクティビティが表示されます。

レポートを表示するには、[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] を開き、[**レポート** \> **ダッシュボード**] に移動して、[**コネクタレポート**] を選択します。 レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=ConnectorReport> ます。

![レポートダッシュボードのコネクタレポートウィジェット](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a>コネクタレポートのレポートビュー

次のグラフはレポートビューで利用できます。

- **データの表示: メールフロー**: このグラフは、次の方法で開催される受信メッセージと送信メッセージの数を示します。

  - **合計**
  - **コネクタのないインターネットから**
  - **コネクタを使用せずにインターネットに接続する**
  - 構成済みの特定のコネクタ。
  
  グラフのデータを分離するには、[**データの表示**] コントロールを使用して、これらのオプションのいずれかまたは**すべてのメールフロー**を選択します。

  ![コネクタレポートでメールフロー別にデータを表示する](../../media/connector-report-view-data-by-mail-flow.png)

- **データの表示方法: tls 使用法**: このグラフは、メールフローのトランスポート層セキュリティ (TLS) バージョンの使用率を示しています。

  グラフのデータを分離するには、[**データの表示**] コントロールを使用して、次のいずれかのオプションを選択します。

  - **すべてのメールフロー**
  - **コネクタのないインターネットから**
  - **コネクタを使用せずにインターネットに接続する**
  - 構成済みの特定のコネクタ。

  ![コネクタレポートでの TLS 使用法によるデータの表示](../../media/connector-report-view-data-by-tls-usage.png)

レポートビューで [**フィルター** ] をクリックすると、**開始日**と**終了日**を含む日付範囲を指定できます。

### <a name="details-table-view-for-the-connector-report"></a>コネクタレポートの詳細表ビュー

レポートビューで [**詳細テーブルの表示**] をクリックすると、次の情報が表示されます。

- **Date**
- **コネクタの方向と名前**
- **コネクタの種類**
- **FORCED TLS?**: 値**True**または**False**。
- **TLS なし**(パーセント)
- **TLS 1.0** (パーセント)
- **TLS 1.1** (パーセント)
- **TLS 1.2** (パーセント)
- **Volume**: メッセージ数。

詳細テーブルビューで [**フィルター** ] をクリックすると、**開始日**と**終了日**を含む日付範囲を指定できます。

レポートビューに戻るには、[**レポートの表示**] をクリックします。

## <a name="exchange-transport-rule-report"></a>Exchange トランスポートルールレポート

**Exchange トランスポートルールレポート**は、組織内の受信メッセージと送信メッセージに対するメールフロールール (トランスポートルールとも呼ばれます) の影響を示します。

レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート** \> **ダッシュボード**] に移動して、[ **Exchange トランスポートルール**] を選択します。 レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=ETRRuleReport> ます。

![レポートダッシュボードの Exchange トランスポートルールウィジェット](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a>Exchange トランスポートルールレポートのレポートビュー

次のグラフはレポートビューで利用できます。

- **データの表示方法: Exchange トランスポートルール** \>**分割ダウン: 方向**: このグラフは、トランスポートルールによって影響を受けた**受信**メッセージと**送信**メッセージの数を示します。

- **データの表示方法: Exchange トランスポートルール** \>**下に移動: 重要**度: このグラフは、重要**High severity**度が高い**ものと重要度が**低いもの、**重大度が低い**メッセージの数を示しています。 重要度レベルをルールのアクションとして設定します (**このルールを重要度レベル**または_Setauditseverity_で監査します)。 詳細については、「 [Exchange Online のメールフロールールのアクション](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)」を参照してください。

- **データの表示方法: DLP Exchange トランスポートルール** \>**分解ダウン: Direction**: このグラフは、データ損失防止 (DLP) トランスポートルールによって影響を受けた**受信**メッセージと**送信**メッセージの数を示します。 次のオプションのいずれかを選択して、グラフをさらに細かく調整できます。

  - **データの表示: すべての DLP トランスポートルール**
  - **データの表示: 侵害されたユーザー**
  - **データを表示する対象: 低容量のコンテンツを検出したこと。米国 Patriot Act**

- **データの表示方法: DLP Exchange トランスポートルール** \>**下に移動: 方向**: このビューには、重要度が**高**で、**中程度**、および DLP トランスポートルールの影響を受けた**重要度の低い**メッセージが表示されます。 次のオプションのいずれかを選択して、グラフをさらに細かく調整できます。

  - **データの表示: すべての DLP トランスポートルール**
  - **データの表示: 侵害されたユーザー**
  - **データを表示する対象: 低容量のコンテンツを検出したこと。米国 Patriot Act**

レポートビューで [**フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。

- **開始日**と**終了日**
- Direction 値
- 重要度の値

![Exchange トランスポートルールレポートのレポートビュー](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a>Exchange トランスポートルールレポートの詳細表ビュー

[**詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。

- **データの表示方法: Exchange トランスポートルール**:

  - **Date**
  - **トランスポートルール**
  - **[件名]**
  - **[送信者のアドレス]**
  - **受信者のアドレス**
  - **重大度**
  - **[方向]**

- **データの表示方法: DLP Exchange トランスポートルール**:

  - **Date**
  - **DLP ポリシー**
  - **トランスポートルール**
  - **[件名]**
  - **[送信者のアドレス]**
  - **受信者のアドレス**
  - **重大度**
  - **[方向]**

詳細テーブルビューで [**フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。

- **開始日**と**終了日**
- Direction 値
- 重要度の値

レポートビューに戻るには、[**レポートの表示**] をクリックします。

## <a name="forwarding-report"></a>転送レポート

**転送レポート**には、組織が Exchange Online メールボックスから外部ドメインにメッセージを自動的に転送したことが表示されます。 転送されたメッセージは、セキュリティまたはコンプライアンスリスクを引き起こす可能性があり、侵害されたアカウントを示す場合があります。

レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動して、 \> **Dashboard** [レポートの**転送**] を選択します。 レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=MailFlowForwarding> ます。

![レポートダッシュボードでレポートウィジェットを転送する](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a>転送レポートのレポートビュー

次のグラフがレポートビューで利用できます。

- **データの表示: 転送方法**: 次のメソッドを示します。

  - **トランスポートルール**:[メールフロールール](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)とも呼ばれます。
  - **メールボックスルール**:[受信トレイルール](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)とも呼ばれます。

  ![転送レポートでの転送方法の表示](../../media/forwarding-report-forwarding-methods.png)

- **データの表示: 転送ドメイン**: このビューには、転送先の受信者ドメインが表示されます。

  ![転送レポートでのドメインの転送ビュー](../../media/forwarding-report-forwarding-domains.png)

- **データの表示: フォワーダー**: 次のフォワーダーが表示されます。

  - **トランスポートルール**
  - 転送の受信トレイルールを含むメールボックス。

  ![転送レポートのフォワーダービュー](../../media/forwarding-report-forwarders.png)

レポートビューで [**フィルター** ] をクリックすると、**開始日**と**終了日**を含む日付範囲を指定できます。

### <a name="details-table-view-for-the-forwarding-report"></a>転送レポートの詳細表ビュー

レポートビューで [**詳細テーブルの表示**] をクリックすると、次の情報が表示されます。

- **フォワーダー**: 転送の受信トレイルールを含む値**トランスポートルール**またはメールボックス。
- **転送の種類**: 値**メールボックスルール**または**トランスポートルール**。
- **受信者名**
- **受信者ドメイン**
- **詳細**: これは、メールフロールールの GUID 値、または受信トレイルールの RuleIdentity 値です。
- **Count**
- **最初の繰越日付**

詳細テーブルビューで [**フィルター** ] をクリックすると、**開始日**と**終了日**を含む日付範囲を指定できます。

レポートビューに戻るには、[**レポートの表示**] をクリックします。

## <a name="mailflow-status-report"></a>メールフロー状態レポート

**メールフローの状態レポート**は、[送信および受信](#sent-and-received-email-report)した電子メールレポートに似ていますが、エッジで許可またはブロックされる電子メールに関する追加情報が含まれています。 これは、エッジ保護情報が含まれている唯一のレポートで、Exchange Online Protection (EOP) による評価のためにサービスに許可されるまでにブロックされる電子メールの量のみを示しています。

レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard**て、**メールフローの状態レポート**を選択します。 **メールフロー状態レポート**に直接移動するには、を開き <https://protection.office.com/mailflowStatusReport> ます。

![レポートダッシュボードのメールフロー status レポートウィジェット](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>メールフロー状態レポートの種類ビュー

レポートを開くと、既定で [**種類**] タブが選択されます。 既定では、このビューには、次のフィルターを使用して構成されたグラフとデータテーブルが含まれています。

- **日付**: 過去7日間。
- **方向**:

  - **受信**
  - **向き**
  - **組織内**(**受信**および**送信**とは別にカウントされます)

- **型**:

  - **正常なメール**
  - **マルウェア**
  - **スパム**
  - **エッジ保護**
  - **ルールメッセージ**
  - **フィッシング詐欺メール**

グラフは、 **Type**の値で構成されています。

これらのフィルターを変更するには、[**フィルター** ] をクリックするか、グラフの凡例で値をクリックします。

データテーブルには、次の情報が含まれています。

- **[方向]**
- **型**
- **24 時間**
- **3 日間**
- **7日**
- **15 日**
- **30 日間**

[カテゴリの選択] をクリックし**て詳細**を確認する場合は、次の値から選択できます。

- **フィッシング電子メール**: この選択によって、[脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)が表示されます。
- **メール内のマルウェア**: この選択によって、[脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)が表示されます。
- **スパム検出**: この選択を行うと、[スパム検出レポート](view-email-security-reports.md#spam-detections-report)が表示されます。
- **エッジブロック**されたスパム: これを選択すると、[スパム検出レポート](view-email-security-reports.md#spam-detections-report)に移動します。

**エクスポート**:

詳細ビューでは、1日分のデータしかエクスポートできません。 そのため、7日間データをエクスポートする場合は、7つの異なるエクスポート操作を行う必要があります。

エクスポートされた各 .csv ファイルは、15万行に制限されます。 その日のデータに15万行を超える行が含まれている場合は、複数の .csv ファイルが作成されます。

![メールフロー状態レポートの種類ビュー ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>メールフロー状態レポートの方向ビュー

[**方向**] タブをクリックすると、[**種類**] ビューの同じ既定のフィルターが使用されます。

グラフは**方向**の値によって構成されます。

これらのフィルターを変更するには、[**フィルター** ] をクリックするか、グラフの凡例で値をクリックします。 [**種類**の表示と同じフィルターを使用します。

データテーブルには、**種類**ビューと同じ情報が含まれています。

[詳細を表示する**カテゴリを選択**してください] の選択肢と動作は、[**種類**] ビューと同じです。

**エクスポート**:

詳細ビューでは、1日分のデータしかエクスポートできません。 そのため、7日間データをエクスポートする場合は、7つの異なるエクスポート操作を行う必要があります。

エクスポートされた各 .csv ファイルは、15万行に制限されます。 その日のデータに15万行を超える行が含まれている場合は、複数の .csv ファイルが作成されます。

![メールフロー状態レポートの方向ビュー ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a>送信および受信した電子メールレポート

**送信および受信**した電子メールレポートは、スパム検出、マルウェア、および "good" と識別された電子メールを含む、受信および送信電子メールに関する情報を示すスマートレポートです。 このレポートと[メールフロー状態レポート](#mailflow-status-report)の違いは次のとおりです。このレポートには、エッジ保護によってブロックされたメッセージに関するデータは含まれません。

レポートの集計ビューと詳細ビューでは、90日間のフィルター処理を実行できます。

レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動して、 \> **Dashboard** [**送信済みおよび受信した電子メール**] を選択します。 レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> ます。

![レポートダッシュボードで送信および受信した電子メールウィジェット](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a>送信および受信した電子メールレポートのレポートビュー

次のグラフがレポートビューで利用できます。

- **分割ダウン: 種類**: 使用可能なすべてのカテゴリをグラフに表示します。

  - **合計**
  - **正常なメール**
  - **マルウェア (マルウェア対策)** (EOP)
  - **スパム検出**
  - **ルールメッセージ**
  - **高度なマルウェア**(OFFICE 365 ATP)

  グラフの1日 (データポイント) にカーソルを置くと、その日の詳細が表示されます。

  ![送信済みおよび受信した電子メールレポートの種類ビュー](../../media/sent-and-received-email-report-type-view.png)

- **分割ダウン: 方向**: グラフには、**合計**、**受信**、および**送信**データが表示されます。 グラフの1日 (データポイント) にカーソルを置くと、その日の詳細が表示されます。

  ![送信および受信した電子メールレポートの方向ビュー](../../media/sent-and-received-email-report-direction-view.png)

- **ドリルダウン** \> する方法**マルウェア (マルウェア対策)**: この選択を行うと、[電子メールレポートにあるマルウェアの検出](view-email-security-reports.md#malware-detections-in-email-report)が行われます。

- **ドリルダウン** \> する方法**スパム検出)**: この選択によって、[スパム検出レポート](view-email-security-reports.md#spam-detections-report)が表示されます。

レポートビューで [**フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。

- **開始日**と**終了日**
- Direction 値
- 型の値

レポートビューに戻るには、[**レポートの表示**] をクリックします。

### <a name="details-table-view-for-the-sent-and-received-email-report"></a>送信および受信した電子メールレポートの詳細表ビュー

[次の方法で**詳細テーブルを表示**] をクリックすると、 **[方向] または**[**下に移動: 方向**] が表示され、次の情報が表示されます。

- **日付 (UTC)**
- **型**
- **[方向]**
- **メッセージ数**

詳細テーブルビューで [**フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。

- **開始日**と**終了日**
- Direction 値
- 型の値

レポートビューに戻るには、[**レポートの表示**] をクリックします。

## <a name="top-senders-and-recipients-report"></a>[上位送信者および受信者] レポート

[**上位の送信者と受信者**] レポートは、上位の電子メール送信者と受信者を示す円グラフです。

レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート** \> **ダッシュボード**] に移動して [**上位の送信者と受信者**] を選択します。 レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> ます。

![レポートダッシュボードの [上位送信者および受信者] ウィジェット](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a>上位送信者および受信者レポートのレポートビュー

次のグラフがレポートビューで利用できます。

- **上位メール送信者のデータを表示する \>**
- **\>最上位のメール受信者のデータを表示する**
- **上位スパム受信者のデータを表示する \>**
- **データの \> 表示上位マルウェア受信者**(EOP)
- **データの \> 表示上位マルウェア受信者 (ATP)** (Office 365 atp)

これらの選択に基づいて、円グラフの構成が変更されます。

円グラフのくさび形の上にポインターを移動すると、送信または受信したメッセージの数が表示されます。

レポートビューで [**フィルター** ] をクリックすると、**開始日**と**終了日**を含む日付範囲を指定できます。

![上位の送信者と受信者レポートのレポートビューに表示された円グラフ](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a>上位送信者および受信者レポートの詳細テーブルビュー

[**詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。

- **上位メール送信者のデータを表示する \>**

  - **上位メール送信者**
  - **Count**

- **\>最上位のメール受信者のデータを表示する**

  - **上位メール受信者**
  - **Count**

- **上位スパム受信者のデータを表示する \>**

  - **上位スパム受信者**
  - **Count**

- **データの \> 表示上位マルウェア受信者**(EOP)

  - **上位マルウェア受信者**
  - **Count**

- **データの \> 表示上位マルウェア受信者 (ATP)** (Office 365 atp)

  - **上位マルウェア受信者 (ATP)**
  - **Count**

詳細テーブルビューで [**フィルター** ] をクリックすると、**開始日**と**終了日**を含む日付範囲を指定できます。

レポートビューに戻るには、[**レポートの表示**] をクリックします。

## <a name="what-permissions-are-needed-to-view-these-reports"></a>これらのレポートを表示するには、どのようなアクセス許可が必要ですか。

レポートを表示して使用するには、セキュリティ & コンプライアンスセンター**および**Exchange Online で、指定された役割グループのメンバーである必要があります。

- セキュリティ & コンプライアンスセンターでは、次のいずれかの役割グループのメンバーである必要があります。

  -組織の管理

  -セキュリティ管理者 ( [Azure Active Directory 管理センター](https://aad.portal.azure.com) -セキュリティリーダでこれを実行することもできます)

  詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)」を参照してください。

- Exchange Online では、次のいずれかの役割グループのメンバーである必要があります。

  -組織の管理

  -表示のみの組織管理

  -表示のみの受信者

  -コンプライアンス管理

詳細については、「exchange online の[アクセス許可](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo)」および「 [Manage Role Groups in exchange online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。

## <a name="related-topics"></a>関連項目

[セキュリティとコンプライアンス センターのスマート レポートと分析情報](reports-and-insights-in-security-and-compliance.md)

[セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する](view-email-security-reports.md)
