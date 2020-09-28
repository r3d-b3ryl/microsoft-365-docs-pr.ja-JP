---
title: セキュリティ/コンプライアンス センターで電子メールのセキュリティ レポートを表示する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 組織の電子メールセキュリティレポートを検索して使用する方法について説明します。 電子メールセキュリティレポートは、セキュリティ & コンプライアンスセンターで利用できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b26dd18754a96d1879a2f57ae9742ae1d1a36ce4
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295540"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターで電子メールのセキュリティ レポートを表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[セキュリティ & コンプライアンスセンター](https://protection.office.com)では、Microsoft 365 のスパム対策、マルウェア対策、暗号化機能などの電子メールセキュリティ機能が組織を保護していることを確認するのに役立つさまざまなレポートが提供されています。 [必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合は、**レポート**ダッシュボードにアクセスすることによって、セキュリティ & コンプライアンスセンターでこれらのレポートを表示でき \> **Dashboard**ます。 レポートダッシュボードに直接移動するには、を開き <https://protection.office.com/insightdashboard> ます。

![セキュリティ & コンプライアンスセンターのレポートダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>侵害されたユーザーレポート

> [!NOTE]
> このレポートは、Microsoft 365 組織の Exchange Online メールボックスを使用して利用できます。 これは、スタンドアロンの Exchange Online Protection (EOP) 組織では使用できません。

侵害された **ユーザー** のレポートには、過去7日間以内に **疑わしい** または **制限** されたユーザーアカウントの数が表示されます。 これらの状態のいずれかのアカウントは、問題が発生しているか、侵害されています。 よく使用されるので、レポートを使用して、不審なアカウントや制限付きのアカウントでスパイクや傾向を見つけることができます。 侵害されたユーザーの詳細については、「 [危害を受けた電子メールアカウントへの対応](responding-to-a-compromised-email-account.md)」を参照してください。

![レポートダッシュボードの侵害されたユーザーウィジェット](../../media/compromised-users-report-widget.png)

集計ビューには過去90日間のデータが表示され、詳細ビューには過去30日間のデータが表示されます。

レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート**] \> **ダッシュボード** に移動して、[侵害された **ユーザー**] を選択します。 レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=CompromisedUsers> ます。

[ **フィルター** ] をクリックして、次のいずれかまたは複数の値を選択することによって、グラフと詳細テーブルの両方をフィルターできます。

- **開始日** と **終了日**

- **疑わしい**: ユーザーアカウントは、不審な電子メールを送信しているため、電子メールの送信が制限される危険性があります。

- **制限**: 非常に疑わしいパターンがあるため、ユーザーアカウントが電子メールの送信を制限されています。

![侵害されたユーザーレポートのレポートビュー](../../media/compromised-users-report-activity-view.png)

[ **詳細テーブルの表示**] をクリックすると、次の詳細情報が表示されます。

- **作成時刻**
- **[ユーザー ID]**
- **Action**

レポートビューに戻るには、[ **レポートの表示**] をクリックします。

## <a name="encryption-report"></a>暗号化レポート

**暗号化レポート**は、EOP (exchange online またはスタンドアロン EOP の exchange online メールボックスなしのメールボックスを使用したサブスクリプション) で利用できます。 組織のセキュリティチームは、このレポートの情報を使用して、パターンを識別し、機密性の高い電子メールメッセージのポリシーを事前に適用または調整することができます。 例:

- ユーザーによって大量の電子メールメッセージが暗号化されている場合、暗号化ポリシーを追加して、特定のユースケースの暗号化を自動化することができます。 詳細については、「 [Microsoft 365 で電子メールメッセージを暗号化するためのメールフロールールを定義する](../../compliance/define-mail-flow-rules-to-encrypt-email.md)」を参照してください。

- 使用可能な暗号化テンプレートが多数あり、それを使用しているものがない場合は、ユーザーが機能のトレーニングを必要としているかどうかを調べることができます。

集計ビューでは、過去90日間のフィルターを使用でき、詳細ビューでは10日間のフィルター処理を実行できます。

レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> **ダッシュボード** ] に移動して、[ **暗号化レポート**] を選択します。 レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=EncryptionReport> ます。

暗号化の詳細については、「 [Microsoft 365 の電子メールの暗号化](../../compliance/email-encryption.md)」を参照してください。

### <a name="report-view-for-the-encryption-report"></a>暗号化レポートのレポートビュー

グラフでは、次のフィルターを使用できます。

- **データの表示: メッセージの暗号化レポート** と次の **方法で分割**します。暗号化方法: 次の暗号化方法を使用できます。

  - **ユーザーによる暗号化**
  - **ポリシーによる暗号化**

  [ **フィルター**] をクリックすると、次のフィルターを使用してグラフを変更できます。

  - **開始日** と **終了日**
  - 暗号化方法。
  - 暗号化テンプレート。

- **データの表示形式: メッセージの暗号化レポート** と **分解: 暗号化テンプレート**: 次の暗号化方法を使用できます。

  - **転送不可**
  - **暗号化のみ**
  - **OME previous**
  - **Custom**

  [ **フィルター**] をクリックすると、次のフィルターを使用してグラフを変更できます。

  - **開始日** と **終了日**
  - 暗号化方法
  - 暗号化テンプレート

- **データの表示形式: 上位5受信者ドメイン**: このビューには、上位5受信者ドメインの送信されたメッセージ数が円グラフで表示されます。

  [ **フィルター**] をクリックすると、 **開始日** と **終了日**を選択できます。

### <a name="details-table-view-for-the-encryption-report"></a>暗号化レポートの詳細表ビュー

[ **詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。

- **下に移動: 暗号化方法** または次のよう **に分割します。暗号化テンプレート**: 次の情報が表示されます。

  - **Date**
  - **[送信者のアドレス]**
  - **暗号化テンプレート**
  - **暗号化方法**
  - **受信者のアドレス**
  - **Subject**

- **データの表示方法: 上位5受信者ドメイン**:

  - **Date**
  - **受信者ドメイン**
  - **メッセージ数**
  
詳細テーブルビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。

- **開始日** と **終了日**
- 暗号化方法
- 暗号化テンプレート

レポートビューに戻るには、[ **レポートの表示**] をクリックします。

## <a name="mailflow-status-report"></a>メールフロー状態レポート

**メールフロー status レポート**には、マルウェア、スパム、フィッシングおよびエッジブロックされたメッセージに関する情報が含まれています。 詳細については、「 [メールフロー status report](view-mail-flow-reports.md#mailflow-status-report)」を参照してください。

## <a name="malware-detections-in-email-report"></a>電子メールレポートでのマルウェアの検出

**電子メールのマルウェア検出**レポートには、受信および送信電子メールメッセージ (Exchange Online Protection または EOP によって検出されたマルウェア) でのマルウェアの検出に関する情報が表示されます。 EOP でのマルウェア保護の詳細については、「 [EOP のマルウェア対策保護](anti-malware-protection.md)」を参照してください。

 集計ビューのフィルターでは90日間が許可されますが、詳細テーブルのフィルターでは10日間しか許可されません。

レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> ] **ダッシュボード** に移動して、[ **電子メールでマルウェアの検出**] を選択します。 レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=MalwareDetections> ます。

![レポートダッシュボードの電子メールウィジェットでのマルウェアの検出](../../media/malware-detections-widget.png)

[ **フィルター** ] をクリックして、次のものを選択することによって、グラフと詳細テーブルの両方をフィルターできます。

- **開始日** と **終了日**
- **受信**
- **向き**

![電子メールレポートでのマルウェア検出のレポートビュー](../../media/malware-detections-report-view.png)

[ **詳細テーブルの表示**] をクリックすると、次の詳細情報が表示されます。

- **Date**
- **[送信者のアドレス]**
- **受信者のアドレス**
- メッセージ**id**: メッセージヘッダーの**メッセージ id**ヘッダーフィールドで利用可能で、一意である必要があります。 値の例を次に示し `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` ます (角かっこに注意してください)。
- **Subject**
- **Filename**
- **マルウェアの名前**

レポートビューに戻るには、[ **レポートの表示**] をクリックします。

## <a name="sent-and-received-email-report"></a>送信および受信した電子メールレポート

**送信および受信した電子メール**レポートには、マルウェア、スパム、メールフロールール (トランスポートルールとも呼ばれる) に関する情報と、電子メールがサービスに入った後の高度なマルウェアの検出に関する情報が含まれています。 詳細については、「 [送信および受信した電子メールレポート](view-mail-flow-reports.md#sent-and-received-email-report)」を参照してください。

## <a name="spam-detections-report"></a>スパム検出レポート

**スパム検出**レポートには、EOP によってブロックされたスパム電子メールメッセージが表示されます。 メッセージは、受信者ごとではなく個別にカウントされます。 たとえば、同じスパムメッセージが組織内の100の受信者に送信された場合は、1つのメッセージとして数えられます。

集計ビューでは90日間のフィルター処理が可能で、詳細テーブルでは10日のフィルター処理が許可されています。

レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard**て、[**スパム検出**] を選択します。 レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=SpamDetections> ます。

![レポートダッシュボードのスパム検出ウィジェット](../../media/spam-detections-report-widget.png)

スパム対策保護の詳細については、「 [EOP のスパム対策保護](anti-spam-protection.md)」を参照してください。

### <a name="report-view-for-the-spam-detections-report"></a>スパム検出レポートのレポートビュー

次のグラフがレポートビューで利用できます。

- **分割ダウン: アクション**: 次のイベントの種類が表示されます。

  - **スパムコンテンツのフィルター処理**
  - **スパム IP 禁止**
  - **スパムの封筒ブロック**
  - **スパム dbeb フィルター**: ディレクトリベースのエッジブロック (dbeb)

  グラフの1日 (データポイント) にカーソルを置くと、その日にブロックされたアイテムの数と、それらのアイテムがどのように分類されているかを確認できます。

  ![スパム検出レポートのアクションビュー](../../media/spam-detections-report-action-view.png)

- 次のよう**に分割します。方向**: 次の方向が表示されます。

  - **受信**
  - **向き**

  ![スパム検出レポートでの方向ビュー](../../media/spam-detections-report-direction-view.png)

レポートビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。

- **開始日** と **終了日**
- Direction 値
- イベントの種類の値

### <a name="details-table-view-for-the-spam-detections-report"></a>スパム検出レポートの詳細表ビュー

いずれかのレポートビューで [ **詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。

- **Date**
- **[送信者のアドレス]**
- **受信者のアドレス**
- **イベントの種類**
- **Action**
- **Subject**

詳細テーブルで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。

- **開始日** と **終了日**
- Direction 値
- イベントの種類の値

レポートビューに戻るには、[ **レポートの表示**] をクリックします。

## <a name="spoof-detections-report"></a>スプーフィング検出レポート

**スプーフィング検出**レポートには、検出されたスプーフィングメールメッセージの数と、それらのメッセージのうちどれが "good" (正当なビジネス上の理由で、メールのスプーフィングが行われたもの) であることが示されています。 スプーフィングの詳細については、「 [EOP でのスプーフィング対策保護](anti-spoofing-protection.md)」を参照してください。

レポートの集計ビューでは90日間のフィルター処理が可能になりますが、詳細ビューでは10日間のフィルター処理しか許可されません。

レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard**て、[**スプーフィング検出**] を選択します。 レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=SpoofMailReport> ます。

![レポートダッシュボードのスプーフィング検出ウィジェット](../../media/spoof-detections-widget.png)

グラフの1日 (データポイント) にカーソルを置くと、受信したスプーフィングメールメッセージの数を確認できます。

[ **フィルター** ] をクリックして、次のいずれかまたは複数の値を選択することによって、グラフと詳細テーブルの両方をフィルターできます。

- **開始日** と **終了日**

- **正常なメール**

- **スパムとして検出された**

![スプーフィング検出レポートのレポートビュー](../../media/spoof-detections-report-view.png)

[ **詳細テーブルの表示**] をクリックすると、次の詳細情報が表示されます。

- **Date**
- **スプーフィングされた送信者**
- **True 送信者**
- [**Sender IP (送信者の IP)**]
- **Action**
- **メッセージ数**

レポートビューに戻るには、[ **レポートの表示**] をクリックします。

## <a name="threat-protection-status-report"></a>脅威保護の状態レポート

**脅威保護の状態**レポートは、EOP と OFFICE 365 ATP の両方で使用できます。ただし、レポートには異なるデータが含まれています。 たとえば、EOP のお客様は、電子メールで検出されたマルウェアに関する情報を表示できますが、 [SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイル](atp-for-spo-odb-and-teams.md)に関する情報は表示できません。

このレポートでは、マルウェア対策エンジンによってブロックされたファイルや web サイトアドレス (Url)、 [ゼロ時間自動削除 (ZAP)](zero-hour-auto-purge.md)、Atp の [安全なリンク](atp-safe-links.md)、Atp の [安全な添付ファイル](atp-safe-attachments.md)、 [atp のフィッシング対策](set-up-anti-phishing-policies.md)など、さまざまなコンテンツを含む電子メールメッセージの数が提供されます。 この情報を使用して、傾向を特定したり、組織のポリシーを調整する必要があるかどうかを判断したりできます。 メッセージが5人の受信者に送信される場合は、メッセージを5つの異なるメッセージとしてカウントし、1つのメッセージではないことを理解しておくことが重要です。

レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard**て、[**脅威保護の状態**] を選択します。 レポートに直接移動するには、次のいずれかの Url を開きます。

- Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport> 。
- EOP <https://protection.office.com/reportv2?id=ATPAggregateLightReport>

![レポートダッシュボードの脅威保護状態ウィジェット](../../media/threat-protection-status-report-widget.png)

既定では、グラフに過去7日間のデータが表示されます。 [ **フィルター**] をクリックした場合は、90日の日付の範囲を選択できます (試用版のサブスクリプションは30日間に制限される場合があります)。 詳細テーブルビューでは、30日間のフィルター処理を実行できます。

### <a name="report-view-for-the-threat-protection-status-report"></a>脅威保護状態レポートのレポートビュー

次のビューを利用できます。

- **データの表示: 概要**: 次の検出情報が表示されます。

  - **メールマルウェア**
  - **電子メールフィッシング**
  - **コンテンツマルウェア**

  ![脅威保護状態レポートの概要ビュー](../../media/threat-protection-status-report-overview-view.png)

- **データの表示方法: コンテンツ \> マルウェア**<sup>1</sup>: 次の情報は、Office 365 ATP 組織で表示されます。

  - **マルウェア対策エンジン**
  - **ファイル分析**

  ![脅威保護状態レポートのコンテンツマルウェアビュー](../../media/threat-protection-status-report-content-malware-view.png)

- **下に移動: 検出テクノロジ** と **View data: Email \> フィッシング**: 次の情報が表示されます。

  - **ATP で生成された URL 評価**<sup>1</sup>
  - **高度なフィッシングフィルター**
  - **スプーフィング防止: DMARC エラー**
  - **スプーフィング対策: 組織内**
  - **スプーフィング防止: 外部ドメイン**
  - **ブランド偽装**
  - **ドメイン偽装**<sup>1</sup>
  - **EOP URL 評価**
  - **一般的なフィッシングフィルター**
  - **Others**
  - **フィッシング ZAP**<sup>2</sup>
  - **URL 分析**<sup>1</sup>
  - **ユーザー偽装**<sup>1</sup>

  ![脅威保護状態レポートのフィッシング電子メールの検出テクノロジビュー](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **分割ダウン: 検出テクノロジ** と **データの表示者: 電子メール \> マルウェア**: 次の情報が表示されます。

  - **ATP で生成されたファイル評価**<sup>1</sup>
  - **マルウェア対策エンジン**<sup>1</sup>
  - **マルウェア対策ポリシーファイルの種類ブロック**
  - **ファイル分析**<sup>1</sup>
  - **悪意のあるファイルの評価**
  - **マルウェアの ZAP**<sup>2</sup>
  - **Others**

  ![脅威保護状態レポートでのマルウェアの検出テクノロジビュー](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **分割ダウン: Policy type** and **view Data by: Email \> フィッシング** Or **view data by: email \> マル**: 次の情報が表示されます。

  - **マルウェア対策**
  - **安全な添付ファイル**<sup>1</sup>
  - **フィッシング**
  - **スパム対策**
  - **メールフロールール** (トランスポートルールとも呼ばれる)
  - **Others**

  ![脅威保護の状態レポートに表示されるフィッシング電子メールのポリシーの種類](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **分割ダウン: 配信状態** および **表示データ: 電子メールの \> フィッシング** または **view by: email \> マルウェア**: 次の情報が表示されます。

  - **配信失敗**
  - **落下**
  - **転送**
  - **ホストされているメールボックス: カスタムフォルダー**
  - **ホストされているメールボックス: 削除済みアイテム**
  - **ホストされているメールボックス: 受信トレイ**
  - **ホストされているメールボックス: 迷惑**
  - **オンプレミスサーバー: 配信済み**
  - **検疫**

  ![脅威保護状態レポートのフィッシング電子メールの配信状態ビュー](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>1</sup> OFFICE 365 ATP のみ

<sup>2</sup> ゼロ時間自動削除 (ZAP) は、スタンドアロン EOP では使用できません (Exchange Online メールボックスでのみ動作します)。

[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。

- **開始日** と **終了日**
- **検出**
- **保護対象**: **ATP** または **EOP**
- **タグ**: タグでフィルター処理して、特定のタグが適用されたユーザーまたはグループを返します。 ユーザータグの詳細については、「 [user tags](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide)」を参照してください。
- **ドメイン**

> [!NOTE]
> **保護者**、 **タグ** 、および **ドメイン** は Office 365 ATP のみです。 これらのフィルター可能なプロパティは、 **「データの表示方法: コンテンツ \> マルウェア**」では使用できません。

### <a name="details-table-view-for-the-threat-protection-status-report"></a>脅威保護状態レポートの詳細表ビュー

[ **詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。

- **データの表示方法: コンテンツ \> マルウェア**:

  - **Date**
  - **場所**
  - **転送者**
  - **マルウェアの名前**

このビューで [ **フィルター** ] をクリックすると、次のフィルターを使用してレポートを変更できます。

- **開始日** と **終了日**
- **検出**

**データの表示: 概要**: [ **表示の詳細] テーブル** ボタンは使用できません。

- その他のすべてのグラフ:

  - **Date**
  - **Subject**
  - **送信者**
  - **受信者**
  - **検出者**
  - **配信状態**
  - **侵害のソース**
  - **Tags**

[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。

- **開始日** と **終了日**
- **検出**
- **保護者** (OFFICE 365 ATP のみ): **ATP** または **EOP**
- **タグ**: タグでフィルター処理して、特定のタグが適用されたユーザーまたはグループを返します。 ユーザータグの詳細については、「 [user tags](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide)」を参照してください。
- **ドメイン**
- **受信者** (このフィルター処理可能なプロパティは、詳細テーブルビューでのみ使用可能であることに注意してください)

## <a name="top-malware-report"></a>上位マルウェアレポート

**上位マルウェア**レポートには、 [EOP でマルウェア対策保護](anti-malware-protection.md)によって検出されたさまざまな種類のマルウェアが表示されます。

レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート**] \> **ダッシュボード** に移動して [ **上位マルウェア**] を選択します。 レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=TopMalware> ます。

![レポートダッシュボードのトップマルウェアウィジェット](../../media/top-malware-report-widget.png)

円グラフのくさび形の上にポインターを移動すると、マルウェアの種類の名前と、マルウェアを持っていることが検出されたメッセージの数を確認できます。

![トップマルウェアレポートビュー](../../media/top-malware-report-view.png)

[ **詳細テーブルの表示**] をクリックすると、次の詳細情報が表示されます。

- **上位マルウェア**
- **Count**

レポートビューまたは詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始** 日と **終了日**を含む日付範囲を指定できます。

## <a name="url-threat-protection-report"></a>URL の脅威保護レポート

**URL 脅威保護レポート**は、Office 365 Advanced threat PROTECTION (ATP) で利用できます。 詳細については、「 [URL の脅威保護レポート](view-reports-for-atp.md#url-threat-protection-report)」を参照してください。

## <a name="user-reported-messages-report"></a>ユーザーによって報告されたメッセージレポート

ユーザーによって報告された **メッセージ** レポートには、ユーザーが [レポートメッセージアドイン](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)を使用して、迷惑メール、フィッシングの試行、または正常なメールとして報告した電子メールメッセージに関する情報が表示されます。

組織に対して構成されたスパムポリシーの例外やメールフロールールなどの配信理由を含む、各メッセージの詳細を表示できます。 詳細を表示するには、[ユーザーレポート] リスト内のアイテムを選択し、[ **概要** ] タブと [ **詳細** ] タブで情報を表示します。

![ユーザーによって報告されたメッセージのレポートには、ユーザーが迷惑メールではないというラベルが付けられます。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

このレポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)で、次のいずれかの手順を実行します。

- [**脅威管理**] ダッシュボードのユーザーによって報告されたメッセージに移動 \> **Dashboard** \> **User-reported messages**します。

- [**脅威の管理**] に移動して \> **Review** \> **、ユーザーから報告**されたメッセージを確認します。

![セキュリティ & コンプライアンスセンターで、[脅威管理] [ \> ユーザーが報告するメッセージを確認する] を選択します。 \>](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> ユーザーによって報告されたメッセージレポートが正常に機能するためには、Office 365 環境の **監査ログを有効にする必要があり** ます。 これは、通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。 詳細については、「 [Microsoft 365 監査ログ検索を有効または無効にする](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)」を参照してください。

## <a name="what-permissions-are-needed-to-view-these-reports"></a>これらのレポートを表示するには、どのようなアクセス許可が必要ですか。

レポートを表示して使用するには、セキュリティ & コンプライアンスセンター **および** Exchange Online で、指定された役割グループのメンバーである必要があります。

- セキュリティ & コンプライアンスセンターでは、次のいずれかの役割グループのメンバーである必要があります。

  -組織の管理-セキュリティ管理者 ( [Azure Active Directory 管理センター](https://aad.portal.azure.com) -セキュリティリーダでこれを実行することもできます)

  詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)」を参照してください。

- Exchange Online では、次のいずれかの役割グループのメンバーである必要があります。

  -組織の管理-表示のみの組織の管理-表示のみの受信者-コンプライアンス管理

詳細については、「exchange online の [アクセス許可](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) 」および「 [Manage Role Groups in exchange online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。

## <a name="what-if-the-reports-arent-showing-data"></a>レポートでデータが表示されない場合はどうなりますか。

レポートにデータが表示されない場合は、ポリシーが正しく設定されているかどうかを再確認してください。 詳細については、「 [脅威からの保護](protect-against-threats.md)」を参照してください。

## <a name="related-topics"></a>関連トピック

[EOP でのスパム対策とマルウェア対策の保護](anti-spam-and-anti-malware-protection.md)

[セキュリティ/コンプライアンス センターのスマート レポートと分析情報](reports-and-insights-in-security-and-compliance.md)

[セキュリティ & コンプライアンスセンターでメールフローレポートを表示する](view-mail-flow-reports.md)

[Office 365 Advanced Threat Protection のレポートを表示する](view-reports-for-atp.md)
