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
description: 組織の電子メール セキュリティ レポートを検索して使用する方法について説明します。 セキュリティ グループ コンプライアンス センターでは、電子メールの&レポートを利用できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b714d9dc4e3ca143d2cb2d7164f8c3c737d1928
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826507"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターで電子メールのセキュリティ レポートを表示する

セキュリティ & コンプライアンス センターでは、 [さまざまなレポートを使用して、Microsoft](https://protection.office.com) 365 のスパム対策、マルウェア対策、暗号化機能などの電子メールのセキュリティ機能が組織をどのように保護しているかを確認することができます。 必要なアクセス許可 [があは、](#what-permissions-are-needed-to-view-these-reports)セキュリティ コンプライアンス センターでこれらのレポートを表示するには、[レポート & ダッシュボード] に **移動** \> **します**。 レポート ダッシュボードに直接移動するには、開きます <https://protection.office.com/insightdashboard> 。

![セキュリティ センター センターのレポート ダッシュボード& レポート](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>侵害されたユーザー レポート

> [!NOTE]
> このレポートは Exchange Online メールボックスが有効な Microsoft 365 組織で使用できます。 スタンドアロン Exchange Online Protection (EOP) 組織では使用できません。

侵 **害されたユーザー レポートには** 、過去 7 日間以内に **不** 審なか制限 **付き** のマークが付いたユーザー アカウントの数が表示されます。 これらの状態のどちらかのアカウントは問題や、もしくは侵害を受けました。 With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts. 侵害されたユーザーの詳細については、「侵害 [されたメール アカウントへの対応」を参照してください](responding-to-a-compromised-email-account.md)。

![レポート ダッシュボードで侵害されたユーザー ウィジェット](../../media/compromised-users-report-widget.png)

集計ビューには過去 90 日間のデータが表示され、詳細ビューには過去 30 日間のデータが表示されます。

レポートを表示するには、コンプライアンス センター[でセキュリティ&開き、[](https://protection.office.com)**レポート** \> **ダッシュボード] に移動****して、侵害されたユーザーを選択します**。 レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=CompromisedUsers> 。

グラフと詳細テーブルの両方にフィルターを適用するには、[ **フィルター] をクリックし** 、次の 1 つ以上の値を選択します。

- **開始日** と **終了日**

- **不審な情報**: ユーザー アカウントから不審なメールが送信され、電子メールの送信が制限されるリスクがあります。

- **制限 :** ユーザー アカウントは、不審なパターンが原因でメールの送信が制限されています。

![侵害されたユーザー レポートのレポート ビュー](../../media/compromised-users-report-activity-view.png)

[詳細の表示 **] テーブルをクリック**すると、次の詳細情報が表示されます。

- **作成日時**
- **[ユーザー ID]**
- **操作**

レポート ビューに戻るには、[レポートの表示] **をクリックします**。

## <a name="encryption-report"></a>[暗号化] レポート

暗号化 **レポートは** EOP で使用可能です (Exchange Online のメールボックスでのサブスクリプション、または Exchange Online メールボックスのないスタンドアロン EOP)。 組織のセキュリティ チームは、このレポートの情報を使用してパターンを特定し、機密性の高い電子メール メッセージのポリシーをプロアクティブに適用または調整できます。 たとえば、次のようにします。

- ユーザーが暗号化する電子メール メッセージが多す多い場合は、暗号化ポリシーを追加して、特定の用例で暗号化を自動化することもできます。 詳細については [、「Microsoft 365 でメール メッセージを暗号化するメール フロー ルールの定義」を参照してください](../../compliance/define-mail-flow-rules-to-encrypt-email.md)。

- 利用可能な暗号化テンプレートが数回あっても、これらのテンプレートを使用しない場合は、ユーザーに機能のトレーニングが必要かどうかを確認できます。

集計ビューでは過去 90 日間のフィルター処理を行い、詳細ビューでは 10 日間のフィルター処理を使用できます。

レポートを表示するには、セキュリティ コンプライアンス センター [を開&、[レポート](https://protection.office.com)ダッシュボード] **に移動し** \> **、[** 暗号化レポート **] を選択します**。 レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=EncryptionReport> 。

暗号化の詳細については [、「Microsoft 365 での電子メールの暗号化」を参照してください](../../compliance/email-encryption.md)。

### <a name="report-view-for-the-encryption-report"></a>暗号化レポートのレポート ビュー

グラフには次のフィルターを使用できます。

- **データの表示方法: 暗号化方法****: 暗号化方法: 暗号化方法**を次に示します。

  - **ユーザー別の暗号化**
  - **ポリシーによる暗号化**

  [フィルター] を **クリック**した場合は、次のフィルターを使用してグラフを変更できます。

  - **開始日** と **終了日**
  - 暗号化方法。
  - 暗号化テンプレート。

- **データの表示方法: 暗号化の** 種類: **暗号化テンプレート: 次**の暗号化方法を使用できます。

  - **転送不可**
  - **暗号化のみ**
  - **以前の OME**
  - **Custom**

  [フィルター] を **クリック**した場合は、次のフィルターを使用してグラフを変更できます。

  - **開始日** と **終了日**
  - 暗号化方法
  - 暗号化テンプレート

- **データの表示元: 上位 5 の受信者ドメイン**: 上位 5 つの受信者ドメインのメッセージ数が、このビューには送信済みメッセージ数が表示されます。

  [フィルター] を**クリック**した場合は、開始日**と終了日****を選択できます**。

### <a name="details-table-view-for-the-encryption-report"></a>暗号化レポートの詳細テーブル ビュー

[詳細の **表示] テーブルを**クリックした場合に表示される情報は、表示しているグラフによって異なるためです。

- **方法の詳細: 暗号化または暗号化** テンプレート **での切り分け:** 次の情報が示されます。

  - **Date**
  - **[送信者のアドレス]**
  - **暗号化テンプレート**
  - **暗号化方法**
  - **受信者のアドレス**
  - **[件名]**

- **データの表示元: 上位 5 つの受信者のドメイン**:

  - **Date**
  - **受信者ドメイン**
  - **メッセージ数**
  
詳細テーブル ビュー **で [** フィルター] をクリックした場合、結果は次のフィルターを使用して変更できます。

- **開始日** と **終了日**
- 暗号化方法
- 暗号化テンプレート

レポート ビューに戻るには、[レポートの表示] **をクリックします**。

## <a name="mailflow-status-report"></a>メール フロー状態レポート

メール **フロー状態レポートには、マルウェア** 、スパム、フィッシング、およびエッジでブロックされたメッセージに関する情報が含まれています。 詳細については、「メール フロー ステータス [レポート」を参照してください](view-mail-flow-reports.md#mailflow-status-report)。

## <a name="malware-detections-in-email-report"></a>メール レポートでのマルウェア検出

メール **レポートでのマルウェア検出は、** 受信および送信電子メール メッセージ内のマルウェア検出に関する情報を示します (マルウェアは Exchange Online Protection または EOP で検出されます)。 EOP のマルウェア保護の詳細については、EOP の [マルウェア対策保護を参照してください](anti-malware-protection.md)。

 集計ビュー フィルターでは 90 日間が可能で、詳細テーブル フィルターでは 10 日間のみ指定できます。

レポートを表示するには、セキュリティ コンプライアンス [センター&開き、[レポート](https://protection.office.com)ダッシュボード **]** に \> **移動して** メールでの **マルウェア検出を選択します**。 レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=MalwareDetections> 。

![レポート ダッシュボードのメール ウィジェットでのマルウェア検出](../../media/malware-detections-widget.png)

次の項目を選択して、グラフと詳細テーブルの **両方を** フィルター処理できます。

- **開始日** と **終了日**
- **受信**
- **送信**

![メール レポートのマルウェア検出のレポート ビュー](../../media/malware-detections-report-view.png)

[詳細の表示 **] テーブルをクリック**すると、次の詳細情報が表示されます。

- **Date**
- **[送信者のアドレス]**
- **受信者のアドレス**
- **メッセージ ID**: メッセージ ヘッダー内 **の Message-ID** ヘッダー フィールドに使用できます。一意である必要があります。 角かっ `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` こなどに注:
- **[件名]**
- **Filename**
- **マルウェア名**

レポート ビューに戻るには、[レポートの表示] **をクリックします**。

## <a name="sent-and-received-email-report"></a>送受信メール レポート

送信 **および受信メール レポート** には、マルウェア、スパム、メール フロー ルール (別名トランスポート ルール)、メールがサービスに移行された後の高度なマルウェア検出に関する情報が含まれます。 詳細については、「送信および受信 [メール」を参照してください](view-mail-flow-reports.md#sent-and-received-email-report)。

## <a name="spam-detections-report"></a>スパム検出レポート

スパム **検出レポートには、EOP** によってブロックされたスパム メール メッセージが表示されます。 メッセージは受信者ごとにカウントされます。 たとえば、同じスパム メッセージが組織内の 100 人の受信者に送信された場合、そのメッセージは 1 メッセージとしてカウントされます。

集計ビューでは 90 日間のフィルター処理を実行できますが、詳細テーブルでは 10 日間のフィルター処理を実行できます。

レポートを表示するには、コンプライアンス センターで [セキュリティ &に移動](https://protection.office.com)し、[ **スパム** \> **検出** ] **を選択します**。 レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=SpamDetections> 。

![レポート ダッシュボードのスパム検出ウィジェット](../../media/spam-detections-report-widget.png)

スパム対策保護の詳細については、「EOP の [スパム対策保護」を参照してください](anti-spam-protection.md)。

### <a name="report-view-for-the-spam-detections-report"></a>スパム検出レポートのレポート ビュー

レポート ビューでは、次のグラフを使用できます。

- **操作の別の方法: 操作**の種類は次のとおりです。

  - **フィルター処理スパム コンテンツ**
  - **スパム IP ブロック**
  - **スパム エンベロープのブロック**
  - **スパム DBEB フィルター**: ディレクトリ ベースのエッジ ブロック (DBEB)

  グラフで 1 日 (データ ポイント) にポインターを移動すると、その日がブロックされた項目の数と、それらのアイテムの分類方法を確認できます。

  ![スパム検出レポートのアクション ビュー](../../media/spam-detections-report-action-view.png)

- **次の手順で区切**りを下します。次の手順について説明します。

  - **受信**
  - **送信**

  ![スパム検出レポートの方向ビュー](../../media/spam-detections-report-direction-view.png)

レポート ビューで **[フィルター** ] をクリックした場合は、次のフィルターを使用して結果を変更できます。

- **開始日** と **終了日**
- Direction の値
- イベントの種類の値

### <a name="details-table-view-for-the-spam-detections-report"></a>スパム検出レポートの詳細テーブル ビュー

レポート ビューで **[詳細の表示]** テーブルをクリックすると、次の情報が表示されます。

- **Date**
- **[送信者のアドレス]**
- **受信者のアドレス**
- **イベントの種類**
- **操作**
- **[件名]**

詳細テーブルの **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。

- **開始日** と **終了日**
- Direction の値
- イベントの種類の値

レポート ビューに戻るには、[レポートの表示] **をクリックします**。

## <a name="spoof-detections-report"></a>なりすみ検出レポート

**スプーフィング検出レポート**には、検出されたスプーフィング メール メッセージの数と、どのメッセージが「良好」な (正当な業務上の理由で実行された) と見なされたメッセージが表示されます。 スプーフィングの詳細については [、EOP のスプーフィング対策保護を参照してください](anti-spoofing-protection.md)。

レポートの集計ビューには 90 日間のフィルター処理を行えますが、詳細ビューには 10 日間のフィルターしか使用できません。

レポートを表示するには、セキュリティ/コンプライアンス [センター&開き、[](https://protection.office.com)レポート **ダッシュボード]** \> **に移動して** [ **スプーフィングの検出] を選択します**。 レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=SpoofMailReport> 。

![レポート ダッシュボードのスプーフィング検出ウィジェット](../../media/spoof-detections-widget.png)

グラフ内の 1 日 (データ ポイント) にポインターを移動すると、通過したスプーフィング メール メッセージの数を確認できます。

グラフと詳細テーブルの両方にフィルターを適用するには、[ **フィルター] をクリックし** 、次の 1 つ以上の値を選択します。

- **開始日** と **終了日**

- **良いメール**

- **スパムとしてキャッチ**

![なりすみ検出レポートのレポート ビュー](../../media/spoof-detections-report-view.png)

[詳細の表示 **] テーブルをクリック**すると、次の詳細情報が表示されます。

- **Date**
- **偽の送信者**
- **真の送信者**
- [**Sender IP (送信者の IP)**]
- **操作**
- **メッセージ数**

レポート ビューに戻るには、[レポートの表示] **をクリックします**。

## <a name="threat-protection-status-report"></a>脅威保護の状態レポート

脅 **威保護の状態** レポートは、EOP と Office 365 ATP の両方で利用できます。ただし、レポートにはデータが異なります。 たとえば、EOP のお客様は電子メールで検出されたマルウェアに関する情報を [表示できますが、SharePoint Online、OneDrive、または Microsoft Teams](atp-for-spo-odb-and-teams.md)で検出された悪意のあるファイルについての情報は表示できません。

レポートは、マルウェア対策エンジンによってブロックされたファイルや Web サイト アドレス (URL) など、悪意のあるコンテンツを含む一意のメール メッセージの集計された数を提供します。たとえば、マルウェア対策エンジン、 [ゼロア自動消去 (ZAP) によってブロック](zero-hour-auto-purge.md)された [ATP 機能、ATP](atp-safe-links.md)の安全な添付ファイル [、ATP](atp-safe-attachments.md)の安全な添付ファイル [、ATP](set-up-anti-phishing-policies.md)のフィッシング対策などの ATP 機能です。 この情報を使用して傾向を特定したり、組織のポリシーに調整が必要かどうかを判断したりできます。

レポートを表示するには、セキュリティ/ [コンプライアンス センター&、[レポート ダッシュボード]](https://protection.office.com)に移動 **して** \> **脅** 威保護の **状態を選択します**。 レポートに直接移動するには、次の URL のいずれかを開きます。

- Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport> .
- EOP: <https://protection.office.com/reportv2?id=ATPAggregateLightReport>

![レポート ダッシュボードの脅威保護状態ウィジェット](../../media/threat-protection-status-report-widget.png)

既定では、グラフには過去 7 日間のデータが表示されます。 [フィルター] を **クリック**した場合は、90 日間の日付範囲を選択できます (試用版サブスクリプションは 30 日間に制限されます)。 詳細テーブル ビューでは、30 日間のフィルター処理が可能です。

### <a name="report-view-for-the-threat-protection-status-report"></a>脅威保護状態レポートのレポート ビュー

次のビューを利用できます。

- **データの表示方法: 概要**: 次の検出情報が表示されます。

  - **マルウェア マルウェア**
  - **メールのフィッシング**
  - **コンテンツ マルウェア**

  ![脅威保護状態レポートの概要ビュー](../../media/threat-protection-status-report-overview-view.png)

- **データの表示方法: コンテンツ \> マルウェア**<sup>1:</sup>365 ATP 組織Office次の情報を示します。

  - **マルウェア対策エンジン**
  - **ファイルの追加**

  ![脅威保護状態レポートのコンテンツ マルウェアビュー](../../media/threat-protection-status-report-content-malware-view.png)

- **次の手順で詳細に説明します。検出テクノロジ****ーおよびデータ表示の方法:電子 \> メール フィッシング**: 次の情報が表示されます。

  - **ATP によって生成される URL の評価**<sup>1</sup>
  - **高度なフィッシング フィルター**
  - **スプーフィング対策: DMARC エラー**
  - **スプーフィング対策: Intra-org**
  - **スプーフィング対策: 外部ドメイン**
  - **ブランド偽装**
  - **ドメイン偽装**<sup>1</sup>
  - **EOP URL の評価**
  - **一般的なフィッシング フィルター**
  - **Others**
  - **フィッシング ZAP**<sup>2</sup>
  - **URL の特定**<sup>1</sup>
  - **ユーザー偽装**<sup>1</sup>

  ![脅威保護状態レポートのフィッシング電子メールの検出テクノロジ ビュー](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **次の手順で詳細に説明します。検出テクノロジ****ーおよびデータの表示方法:電子 \> メール マルウェア**: 次の情報が表示されます。

  - **ATP によって生成されたファイルの評価**<sup>1</sup>
  - **マルウェア対策エンジン**<sup>1</sup>
  - **マルウェア対策ポリシー ファイルの種類のブロック**
  - **ファイルの追加**<sup>1</sup>
  - **悪意のあるファイルの評価**
  - **マルウェア ZAP**<sup>2</sup>
  - **Others**

  ![脅威保護状態レポートでのマルウェアの検出テクノロジ ビュー](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **ポリシーの種類とデータ表示の****方法:電子メールの \> フィッ**シングまたは**データの表示方法:電子メール \> のマルウェア**: 次の情報が表示されます。

  - **マルウェア対策**
  - **安全な添付ファイル**<sup>1</sup>
  - **フィッシング対策**
  - **スパム対策**
  - **メール フロー ルール** (トランスポート ルールとも呼ばれる)
  - **Others**

  ![脅威保護状態レポートでのフィッシング メールのポリシーの種類のビュー](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **以下の方法でインスペレーターを分け** 、データ **の表示方法:電子メール \> のフィッシング** または **データの表示方法:電子メール \> のマルウェア**: 次の情報が表示されます。

  - **配信失敗**
  - **Dropped**
  - **Forwarded**
  - **ホストされたメールボックス: カスタム フォルダー**
  - **ホストされたメールボックス: 削除済みアイテム**
  - **ホストされたメールボックス: 受信トレイ**
  - **ホストされたメールボックス: 迷惑メール**
  - **社内サーバー: 配信済み**
  - **検疫**

  ![脅威保護状態レポートのフィッシング電子メールの配信状態ビュー](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>1</sup> Office 365 ATP のみ

<sup>2</sup> 時間の自動消去 (ZAP) はスタンドアロン EOP では使用できません (Exchange Online メールボックスでのみ動作します)。

[フィルター] を **クリック**すると、次のフィルターを使用してレポートを変更できます。

- **開始日** と **終了日**
- 検出値
- Office**保護****ATP****EOP** このフィルター処理可能なプロパティは、コンテンツ マルウェアという**表示データでは使用 \> できません。**

### <a name="details-table-view-for-the-threat-protection-status-report"></a>脅威保護状態レポートの詳細テーブル ビュー

[詳細の **表示] テーブルを**クリックした場合に表示される情報は、表示しているグラフによって異なるためです。

- **データの表示方法: コンテンツ \> Malware**(マルウェア):

  - **Date**
  - **Location**
  - **ディレクティブ**
  - **マルウェア名**

- **[概要] : [概要:** 詳細の **表示] ボタンが** ありません。

- その他のグラフ:

  - **Date**
  - **[件名]**
  - **送信者**
  - **受信者**
  - **検出元のデータ**
  - **配信状態**
  - **侵害のソース**

[フィルター] を **クリック**すると、次のフィルターを使用してレポートを変更できます。

- **開始日** と **終了日**
- 検出値
- Office**保護****ATP****EOP** このフィルター処理可能なプロパティは、コンテンツ マルウェアという**表示データでは使用 \> できません。**

## <a name="top-malware-report"></a>最上位マルウェア レポート

上 **位マルウェア レポート** では、EOP でマルウェア対策保護によって検出されたさまざまな [種類のマルウェアが表示されます](anti-malware-protection.md)。

レポートを表示するには、セキュリティ センターのコンプライアンス [センター&、[レポート](https://protection.office.com)ダッシュボード] に移動 **して**[上 \> **位** マルウェア] を **選択します**。 レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=TopMalware> 。

![レポート ダッシュボードの上部のマルウェア ウィジェット](../../media/top-malware-report-widget.png)

円グラフのウェイバーにポイントすると、マルウェアの種類と、そのマルウェアが含めたときに検出されたメッセージの数を確認できます。

![最上位マルウェア レポート ビュー](../../media/top-malware-report-view.png)

[詳細の表示 **] テーブルをクリック**すると、次の詳細情報が表示されます。

- **[最も一マルウェア]**
- **Count**

レポート ビューまたは**詳細**テーブルのビューで [フィルター] をクリックした場合、開始日と終了日で**日付範囲****を指定できます**。

## <a name="url-threat-protection-report"></a>URL 脅威保護レポート

**URL 脅威保護レポートは**、Office 365 Advanced Threat Protection (ATP) で利用できます。 詳細については、URL の脅威 [保護レポートを参照してください](view-reports-for-atp.md#url-threat-protection-report)。

## <a name="user-reported-messages-report"></a>ユーザーから報告されたメッセージ レポート

ユーザー **から報告されたメッセージ レポートは** 、ユーザーが迷惑メール、フィッシングの試行、または適切なメールとして報告した電子メール メッセージに関 [する情報を、メッセージ報告アドインを使用して表示されます](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)。

組織に構成されたスパム ポリシー例外またはメール フロー ルールなど、配信理由などの各メッセージの詳細を利用できます。 詳細を表示するには、ユーザー レポートのリストでアイテムを選択し、[概要と詳細] **タブの** 情報 **を** 表示します。

![「ユーザー報告メッセージ」レポートには、迷惑メール、迷惑メール、フィッシングの試行などのラベルが付けされたメッセージが表示されます。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

このレポートを表示するには、セキュリティ [/コンプライアンス センターで&](https://protection.office.com)のいずれかの手順を実行します。

- 脅威**管理ダッシュボードの** \> **Dashboard** \> **ユーザーが報告したメッセージに移動します**。

- 脅威管理 **に移動** \> **して** \> **、ユーザーが報告したメッセージを確認します**。

![セキュリティ/コンプライアンス センター&威管理レビュー ユーザー \> の \> メッセージを選択する](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> ユーザーから報告されたメッセージ レポートが正しく動作するには、Office 365 環境 **で** 監査ログを有効にする必要があります。 これは、通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって実行されます。 詳細については [、「Microsoft 365 監査ログの検索を有効または無効にする」をご覧ください](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)。

## <a name="what-permissions-are-needed-to-view-these-reports"></a>これらのレポートを表示するにはどのようなアクセス許可が必要ですか?

レポートを表示して使用するには、セキュリティ保護センターおよび Exchange Online で指定された &役割グループの **メンバーである** 必要があります。

- コンプライアンス センターで&役割グループのいずれかのメンバーである必要があります。

  -組織の管理 - セキュリティ管理者 [(Azure Active Directory](https://aad.portal.azure.com) 管理センター -Security Reader でも実行できます)

  詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)」を参照してください。

- Exchange Online で、次の役割グループのいずれかのメンバーである必要があります。

  -Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management

詳細については、「Exchange [Online のアクセス許可」と「Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) [の役割グループの管理」を参照してください](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。

## <a name="what-if-the-reports-arent-showing-data"></a>レポートにデータが表示されない場合はどうでしょうか。

レポートにデータが表示されない場合は、ポリシーが正しく設定されていることをダブルクリックします。 詳細については、「脅威からの [保護」を参照してください](protect-against-threats.md)。

## <a name="related-topics"></a>関連トピック

[EOP のスパム対策とマルウェア対策の保護](anti-spam-and-anti-malware-protection.md)

[セキュリティ/コンプライアンス センターのスマート レポートと分析情報](reports-and-insights-in-security-and-compliance.md)

[セキュリティ グループおよびコンプライアンス センターでメール フロー レポート&表示する](view-mail-flow-reports.md)

[Office 365 Advanced Threat Protection のレポートを表示する](view-reports-for-atp.md)
