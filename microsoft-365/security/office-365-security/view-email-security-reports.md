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
description: 組織の電子メール セキュリティ レポートを検索して使用する方法について学習します。 電子メール セキュリティ レポートは、セキュリティ/コンプライアンス センター&利用できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 568144c449d2f1a70082130cc847d48c3486d9da
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865106"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターで電子メールのセキュリティ レポートを表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


セキュリティ & コンプライアンス センターでは、Microsoft 365 のスパム対策、マルウェア対策、暗号化機能などの電子メール セキュリティ機能が組織を保護する方法を確認するのに役立つさまざまなレポートが用意されています。 [](https://protection.office.com) 必要な [アクセス許可がある](#what-permissions-are-needed-to-view-these-reports)場合は、レポート ダッシュボードに移動して、セキュリティ/コンプライアンス センター&レポート **を表示** \> **できます**。 レポート ダッシュボードに直接移動するには、開きます <https://protection.office.com/insightdashboard> 。

![セキュリティ/コンプライアンス センター&ダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>侵害されたユーザー レポート

> [!NOTE]
> このレポートは、Exchange Online メールボックスを使用している Microsoft 365 組織で利用できます。 スタンドアロンの Exchange Online Protection (EOP) 組織では使用できません。

[**侵害されたユーザー]** レポートには、過去 7 日以内に[不審] または [制限付き] とマークされたユーザー アカウントの数が表示されます。 これらのいずれかの状態のアカウントは、問題がある場合や、侵害されている場合もあります。 頻繁に使用すると、レポートを使用して、疑わしいアカウントや制限されたアカウントのスパイクや傾向を特定できます。 侵害されたユーザーの詳細については、「侵害されたメール アカウントへの対応 [」を参照してください](responding-to-a-compromised-email-account.md)。

![レポート ダッシュボードの侵害されたユーザー ウィジェット](../../media/compromised-users-report-widget.png)

集計ビューには過去 90 日間のデータが表示され、詳細ビューには過去 30 日間のデータが表示されます。

レポートを表示するには、セキュリティ/コンプライアンス センターを [開](https://protection.office.com)&**ダッシュボード** に移動し、[侵害されたユーザー \>  **] を選択します**。 レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=CompromisedUsers> 。

[フィルター] をクリックし、次の値の1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。

- **開始日と****終了日**

- **不審**: ユーザー アカウントが不審なメールを送信し、電子メールの送信が制限される危険性があります。

- **制限**: 不審なパターンが原因で、ユーザー アカウントによるメールの送信が制限されています。

![侵害されたユーザー レポートのレポート ビュー](../../media/compromised-users-report-activity-view.png)

[詳細テーブルの **表示] をクリックすると**、次の詳細が表示されます。

- **作成時刻**
- **[ユーザー ID]**
- **操作**

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="encryption-report"></a>暗号化レポート

暗号化 **レポートは** 、EOP (Exchange Online のメールボックスを持つサブスクリプション、または Exchange Online メールボックスを使用しないスタンドアロン EOP) で使用できます。 組織のセキュリティ チームは、このレポートの情報を使用してパターンを特定し、機密性の高い電子メール メッセージのポリシーを事前に適用または調整できます。 例:

- ユーザーによって暗号化された電子メール メッセージの数が多い場合は、暗号化ポリシーを追加して、特定の使用例の暗号化を自動化できます。 詳細については [、「Microsoft 365 でメール メッセージを暗号化するメール](../../compliance/define-mail-flow-rules-to-encrypt-email.md)フロー ルールを定義する」を参照してください。

- 利用可能な暗号化テンプレートが多数あるが、誰も使用できない場合は、ユーザーが機能トレーニングを必要とするかどうかを確認できます。

集計ビューでは過去 90 日間のフィルター処理が可能で、詳細ビューでは 10 日間のフィルター処理が可能です。

レポートを表示するには、セキュリティ/コンプライアンス センターを [開](https://protection.office.com)&レポート ダッシュボード **に移動し**、[暗号化] \> レポート **を選択します**。 レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=EncryptionReport> 。

暗号化の詳細については [、「Microsoft 365 での電子メールの暗号化」を参照してください](../../compliance/email-encryption.md)。

### <a name="report-view-for-the-encryption-report"></a>暗号化レポートのレポート ビュー

グラフでは、次のフィルターを使用できます。

- **データの表示方法: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:

  - **ユーザーによる暗号化**
  - **ポリシーによる暗号化**

  [フィルター] **をクリック** すると、次のフィルターを使用してグラフを変更できます。

  - **開始日と****終了日**
  - 暗号化方法。
  - 暗号化テンプレート。

- **データの表示方法: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:

  - **転送しない**
  - **暗号化のみ**
  - **前の OME**
  - **Custom**

  [フィルター] **をクリック** すると、次のフィルターを使用してグラフを変更できます。

  - **開始日と****終了日**
  - 暗号化方法
  - 暗号化テンプレート

- **View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.

  [フィルター]**をクリック** すると、開始日と **終了日を****選択できます**。

### <a name="details-table-view-for-the-encryption-report"></a>暗号化レポートの詳細テーブル ビュー

[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。

- **[Break down by: Encryption method] (暗号化方法** ) または **[Break down by]**(暗号化テンプレート): 次の情報を示します。

  - **日付**
  - **[送信者のアドレス]**
  - **暗号化テンプレート**
  - **暗号化方法**
  - **受信者のアドレス**
  - **[件名]**

- **データの表示方法: 上位 5 つの受信者ドメイン**:

  - **日付**
  - **受信者ドメイン**
  - **メッセージ数**

詳細テーブル ビューで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。

- **開始日と****終了日**
- 暗号化方法
- 暗号化テンプレート

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="mailflow-status-report"></a>メールフロー状態レポート

Mailflow **ステータス レポートには、** マルウェア、スパム、フィッシング、およびエッジでブロックされたメッセージに関する情報が含まれます。 詳細については、「メールフローの [状態レポート」を参照してください](view-mail-flow-reports.md#mailflow-status-report)。

## <a name="malware-detections-in-email-report"></a>メール レポートでのマルウェアの検出

電子 **メール レポートのマルウェア検出** では、受信および送信電子メール メッセージ (Exchange Online Protection または EOP によって検出されたマルウェア) のマルウェア検出に関する情報が表示されます。 EOP でのマルウェア保護の詳細については、「EOP での [マルウェア対策保護」を参照してください](anti-malware-protection.md)。

 集計ビュー フィルターでは 90 日間、詳細テーブルフィルターは 10 日間のみ使用できます。

レポートを表示するには、[セキュリティ](https://protection.office.com)/コンプライアンス センターを&レポート ダッシュボードに移動し、メールで \> **[マルウェアの検出] を選択します**。 レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=MalwareDetections> 。

![レポート ダッシュボードのメール ウィジェットでのマルウェア検出](../../media/malware-detections-widget.png)

[フィルター] をクリックして次の項目を選択すると、グラフと詳細テーブル **の両方** をフィルター処理できます。

- **開始日と****終了日**
- **受信**
- **送信**

![電子メール レポートのマルウェア検出のレポート ビュー](../../media/malware-detections-report-view.png)

[詳細テーブルの **表示] をクリックすると**、次の詳細が表示されます。

- **日付**
- **[送信者のアドレス]**
- **受信者のアドレス**
- **メッセージ ID**: メッセージ ヘッダーの **Message-ID** ヘッダー フィールドで使用できます。一意である必要があります。 値の例を `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 次に示します (角かっこに注意してください)。
- **[件名]**
- **Filename**
- **マルウェア名**

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="mail-latency-report"></a>メール待機時間レポート

メール **の待機時間レポートには** 、組織内で発生したメール配信と分析の待機時間に関する情報が含まれている。 詳細については、「メールの待機時間 [レポート」を参照してください](view-reports-for-atp.md#mail-latency-report)。

## <a name="sent-and-received-email-report"></a>送信および受信メール レポート

送信 **および受信メール** レポートには、マルウェア、スパム、メール フロー ルール (トランスポート ルールとも呼ばれる)、およびメールがサービスに入った後の高度なマルウェア検出に関する情報が含まれています。 詳細については、「送信および受信 [メール レポート」を参照してください](view-mail-flow-reports.md#sent-and-received-email-report)。

## <a name="spam-detections-report"></a>スパム検出レポート

スパム **検出レポートには** 、EOP によってブロックされたスパム 電子メール メッセージが表示されます。 メッセージは個別にカウントされ、受信者ごとにカウントされません。 たとえば、同じスパム メッセージが組織内の 100 人の受信者に送信された場合、1 つのメッセージとしてカウントされます。

集計ビューでは 90 日間のフィルター処理が可能で、詳細テーブルでは 10 日間のフィルター処理が可能です。

レポートを表示するには、セキュリティ/コンプライアンス センターを [開](https://protection.office.com)&ダッシュボード **に移動し**、[スパム検出] \> **を選択します**。 レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=SpamDetections> 。

![レポート ダッシュボードのスパム検出ウィジェット](../../media/spam-detections-report-widget.png)

スパム対策保護の詳細については [、「EOP でのスパム対策保護」を参照してください](anti-spam-protection.md)。

### <a name="report-view-for-the-spam-detections-report"></a>スパム検出レポートのレポート ビュー

レポート ビューでは、次のグラフを使用できます。

- **[Break down by: Action]:** 次のイベントの種類が表示されます。

  - **フィルター処理されたスパム コンテンツ**
  - **スパム IP ブロック**
  - **スパム エンベロープ ブロック**
  - **Spam DBEB filter**: Directory based edge blocking (DBEB)

  グラフ内の 1 日 (データ ポイント) の上にマウス ポインターを移動すると、その日にブロックされたアイテムの数と、それらのアイテムの分類方法を確認できます。

  ![スパム検出レポートのアクション ビュー](../../media/spam-detections-report-action-view.png)

- **[Break down by: Direction]**(方向): 次の方向を示します。

  - **受信**
  - **送信**

  ![スパム検出レポートの方向ビュー](../../media/spam-detections-report-direction-view.png)

レポート ビューで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。

- **開始日と****終了日**
- 方向の値
- イベントの種類の値

### <a name="details-table-view-for-the-spam-detections-report"></a>スパム検出レポートの詳細テーブル ビュー

レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。

- **日付**
- **[送信者のアドレス]**
- **受信者のアドレス**
- **イベントの種類**
- **操作**
- **[件名]**

詳細テーブルで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。

- **開始日と****終了日**
- 方向の値
- イベントの種類の値

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="spoof-detections-report"></a>スプーフィング検出レポート

ス **プーフィン** グ検出レポートには、検出されたスプーフィング メール メッセージの数と、それらのスプーフィング メール メッセージの数が示されます。それらのメッセージは "良好" と見なされました (正当なビジネス上の理由で行われたスプーフィング メール)。 スプーフィングの詳細については、「EOP でのスプーフィング対策 [保護」を参照してください](anti-spoofing-protection.md)。

レポートの集計ビューでは 90 日間のフィルター処理が可能で、詳細ビューでは 10 日間のフィルター処理のみ可能です。

レポートを表示するには、Security [& Compliance Center](https://protection.office.com)を開き、[**レポート** ダッシュボード] に移動し、[スプーフィング \> **の検出] を選択します**。 レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=SpoofMailReport> 。

![レポート ダッシュボードのスプーフィング検出ウィジェット](../../media/spoof-detections-widget.png)

グラフの 1 日 (データ ポイント) をポイントすると、スプーフィング メール メッセージの受信数を確認できます。

[フィルター] をクリックし、次の値の1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。

- **開始日と****終了日**

- **良いメール**

- **スパムとして検出された**

![スプーフィング検出レポートのレポート ビュー](../../media/spoof-detections-report-view.png)

[詳細テーブルの **表示] をクリックすると**、次の詳細が表示されます。

- **日付**
- **スプーフィングされた送信者**
- **真の送信者**
- [**Sender IP (送信者の IP)**]
- **操作**
- **メッセージ数**

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="threat-protection-status-report"></a>脅威保護の状態レポート

脅威 **保護状態レポート** は、EOP と Microsoft Defender の両方で、Office 365 で利用できます。ただし、レポートには異なるデータが含まれる。 たとえば、EOP のお客様は電子メールで検出されたマルウェアに関する情報を表示できますが [、ATP for SharePoint、OneDrive、または Microsoft Teams](atp-for-spo-odb-and-teams.md)で検出された悪意のあるファイルに関する情報は表示されません。

このレポートは、マルウェア対策エンジン、ゼロアワー自動消去[(ZAP)、Defender](zero-hour-auto-purge.md)for Office 365 の機能 (安全なリンク、安全な添付ファイル、フィッシング対策など) によってブロックされたファイルや Web サイト アドレス[](atp-safe-attachments.md)(URL)[](set-up-anti-phishing-policies.md)など、悪意のあるコンテンツを含む電子メール メッセージの数を提供します。 [](atp-safe-links.md) この情報を使用して、傾向を特定したり、組織のポリシーに調整が必要かどうかを判断できます。

**注**: メッセージが 5 人の受信者に送信される場合、1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされる点を理解することが重要です。

レポートを表示するには、Security [& Compliance Center](https://protection.office.com)を開き、[**レポート** ダッシュボード] に移動し、[脅威保護の状態 \> **] を選択します**。 レポートに直接移動するには、次のいずれかの URL を開きます。

- Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP>
- EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport>

![レポート ダッシュボードの脅威保護状態ウィジェット](../../media/threat-protection-status-report-widget.png)

既定では、グラフには過去 7 日間のデータが表示されます。 [フィルター] **をクリック** すると、90 日間の日付範囲を選択できます (試用版サブスクリプションの期間は 30 日間に制限されます)。 詳細テーブル ビューでは、30 日間のフィルター処理が可能です。

### <a name="report-view-for-the-threat-protection-status-report"></a>脅威保護状態レポートのレポート ビュー

次のビューを利用できます。

- **データの表示方法: 概要**: 次の検出情報が表示されます。

  - **マルウェアへのメール送信**
  - **メールフィッシング**
  - **コンテンツ マルウェア**

  ![脅威保護状態レポートの概要ビュー](../../media/threat-protection-status-report-overview-view.png)

- **データの表示方法: コンテンツ \> マルウェア**<sup>1:</sup>次の情報は、365 組織の Microsoft Defender Office示されています。

  - **マルウェア対策エンジン**: [Microsoft 365](virus-detection-in-spo.md)の組み込みウイルス検出により、Sharepoint、OneDrive、および Microsoft Teams で悪意のあるファイルが検出されました。
  - **ファイル分析**: [Sharepoint、OneDrive、および Microsoft Teams](atp-for-spo-odb-and-teams.md)の ATP によって検出された悪意のあるファイル。

  ![脅威保護状態レポートのコンテンツ マルウェア ビュー](../../media/threat-protection-status-report-content-malware-view.png)

- **データの表示:メッセージの上書き**: 次の上書き理由情報が表示されます。

  - **オンプレミス のスキップ**
  - **IP 許可**
  - **メール フロー ルール**
  - **送信者の許可**
  - **ドメインの許可**
  - **ZAP が有効になっていません**
  - **迷惑メール フォルダーが有効になっていません**
  - **ユーザーの差出人セーフ リスト**
  - **ユーザー セーフ ドメイン**

  ![脅威保護状態レポートのメッセージ上書きビュー](../../media/threat-protection-status-report-message-override-view.png)

- **詳しくは、「検出テクノロジ」と「****データの表示方法 \> :メール** フィッシング」をご覧ください。次の情報が表示されます。

  - **ATP 生成 URL 評価**<sup>1</sup>: 他の Microsoft 365 ユーザーの Office 365 分析に対して Defender から生成された悪意のある URL 評価。
  - **高度なフィッシング フィルター**: 機械学習に基づくフィッシングシグナル。
  - **スプーフィング対策 - DMARC エラー**: メッセージに対する DMARC 認証エラー。
  - **スプーフィング対策 - 組織内**: 送信者が受信者ドメインをスプーフィングしようとしている。
  - **スプーフィング対策 - 外部ドメイン**: 送信者が他のドメインをスプーフィングしようとしている。
  - **ブランド偽装**: 送信者に基づく既知のブランドの偽装。
  - **ドメイン偽装**<sup>1</sup>: 顧客が所有または定義するドメインの偽装。
  - **EOP URL 評価**: 悪意のある URL 評価。
  - **一般的なフィッシング フィルター**: アナリストのルールに基づくフィッシングシグナル。
  - **Others**
  - **フィッシング ZAP**<sup>2</sup>: フィッシング メッセージのゼロアワー自動消去。
  - **URL デトレーション**<sup>1</sup>
  - **ユーザー偽装**<sup>1</sup>: 管理者によって定義された、またはメールボックス インテリジェンスを通じて学習されたユーザーの偽装。

  ![脅威保護状態レポートでのフィッシングメールの検出テクノロジ ビュー](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **ブレークダウン: 検出テクノロジと****データの表示方法: 電子メール \> マルウェア**: 次の情報が表示されます。

  - **ATP 生成ファイル評価**<sup>1</sup>: Defender によって 365 回の分析のために生成Office悪意のあるファイル評価。
  - **マルウェア対策エンジン**<sup>1</sup>: マルウェア対策エンジンからの検出。
  - **マルウェア対策ポリシーのファイルの種類** ブロック : これらは、メッセージで識別された悪意のあるファイルの種類のためにフィルター処理された電子メール メッセージです。
  - **ファイル分析**<sup>1</sup>: 安全な添付ファイルによる検出。
  - **悪意のあるファイル評価**
  - **マルウェア ZAP**<sup>2</sup>
  - **Others**

  ![脅威保護状態レポートでのマルウェアの検出テクノロジ ビュー](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **ブレークダウン:ポリシーの種類** とデータ **の表示方法: メール \> フィッシング** またはデータの **表示方法: 電子メール \> マルウェア**: 次の情報が表示されます。

  - **マルウェア対策**
  - **安全な添付ファイル**<sup>1</sup>
  - **フィッシング対策**
  - **スパム対策**
  - **メール フロー ルール** (トランスポート ルールとも呼ばれる)
  - **Others**

  ![脅威保護状態レポートのフィッシング メールのポリシーの種類ビュー](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **配信の状態と** データの表示 **\>** 方法:メール フィッシングまたはデータの表示方法:メール **\> マルウェア**: 次の情報が表示されます。

  - **配信に失敗しました**
  - **破棄**
  - **Forwarded**
  - **ホストされたメールボックス: カスタム フォルダー**
  - **ホストされたメールボックス: 削除済みアイテム**
  - **ホストされたメールボックス: 受信トレイ**
  - **ホストされたメールボックス: 迷惑メール**
  - **オンプレミス サーバー: 配信**
  - **検疫**

  ![脅威保護状態レポートのフィッシング メールの配信状態ビュー](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>365</sup> の場合のみ 1 Office Defender

<sup>2</sup> ゼロアワー自動消去 (ZAP) はスタンドアロン EOP では使用できません (Exchange Online メールボックスでのみ機能します)。

[フィルター] **をクリック** すると、使用できるフィルターは、表示していたグラフによって異なります。

- [**データの表示方法]: コンテンツ \> マルウェア** の場合は、開始日と終了日、および検出値でレポートを **変更** できます。

- [ **データの表示方法]: [メッセージの上書** き] では、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - **上書き理由**
  - **タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) で結果をフィルター処理します。 ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。
  - **ドメイン**

- その他のすべてのビューでは、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - **検出**
  - **Protected by**: **ATP** or **EOP**
  - **タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) で結果をフィルター処理します。 ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。
  - **ドメイン**

### <a name="details-table-view-for-the-threat-protection-status-report"></a>脅威保護状態レポートの詳細テーブル ビュー

[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。

- **View data by: Overview**: No **View details table** button is available.

- **データの表示方法: コンテンツ \> マルウェア**:

  - **日付**
  - **Location**
  - **提供者**
  - **マルウェア名**

  このビューで **[フィルター** ] をクリックすると、レポートを開始日と終了日、および検出値で **変更** できます。

- **View data by: Message Override**:

  - **日付**
  - **[件名]**
  - **送信者**
  - **受信者**
  - **検出者**
  - **上書き理由**
  - **侵害のソース**
  - **Tags**

  このビューで **[フィルター]** をクリックすると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - **上書き理由**
  - **タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) で結果をフィルター処理します。 ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。
  - **ドメイン**
  - **受信者** (このフィルター可能なプロパティは詳細テーブル ビューでのみ使用できます)

- その他すべてのグラフ:

  - **日付**
  - **[件名]**
  - **送信者**
  - **受信者**
  - **検出者**
  - **配信状態**
  - **侵害のソース**
  - **Tags**

  [フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - **検出**
  - **Protected by**: **Defender for Office 365** or **EOP**
  - **タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) で結果をフィルター処理します。 ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。
  - **ドメイン**
  - **受信者** (このフィルター可能なプロパティは詳細テーブル ビューでのみ使用できます)

## <a name="top-malware-report"></a>トップ マルウェア レポート

Top **malware report** shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).

レポートを表示するには、セキュリティ/コンプライアンス センターを [&](https://protection.office.com)レポート **ダッシュボード** に移動し、[上位マルウェア] \> を **選択します**。 レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=TopMalware> 。

![レポート ダッシュボードの上位マルウェア ウィジェット](../../media/top-malware-report-widget.png)

円グラフでくさびの上にマウス ポインターを移動すると、マルウェアの種類の名前と、そのマルウェアが検出されたメッセージの数が表示されます。

![トップ マルウェア レポート ビュー](../../media/top-malware-report-view.png)

[詳細テーブルの **表示] をクリックすると**、次の詳細が表示されます。

- **トップ マルウェア**
- **Count**

レポート ビュー **または詳細** テーブル ビューで [フィルター] をクリックすると、開始日と終了日で日付範囲 **を****指定できます**。

## <a name="url-threat-protection-report"></a>URL 脅威保護レポート

URL **脅威保護レポートは、Microsoft** Defender で Office 365 で利用できます。 詳細については、「URL 脅威保護 [レポート」を参照してください](view-reports-for-atp.md#url-threat-protection-report)。

## <a name="user-reported-messages-report"></a>ユーザーから報告されたメッセージ レポート

ユーザー **報告メッセージ** レポートには、迷惑メール報告アドインまたはフィッシング報告アドインを使用して、ユーザーが迷惑メール、フィッシング詐欺、または良 [](enable-the-report-message-add-in.md)いメールとして報告した電子メール メッセージに関する情報が表示 [されます。](enable-the-report-phish-add-in.md)

配信理由 (組織に構成されているスパム ポリシーの例外やメール フロー ルールなど) など、メッセージごとに詳細を確認できます。 詳細を表示するには、ユーザー レポート リストでアイテムを選択し、[概要] タブと [詳細] タブ **に** 情報を **表示** します。

![[User-Reported メッセージ] レポートには、迷惑メール、迷惑メール、フィッシングの試行としてラベルが付いたメッセージが表示されます。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

このレポートを表示するには、セキュリティ & [コンプライアンス センターで、](https://protection.office.com)次のいずれかの操作を行います。

- 脅威管理 **ダッシュボードのユーザー** \> **から** \> **報告されたメッセージに移動します**。

- [脅威の管理 **] ユーザーから** \> **報告** \> **されたメッセージを確認するに移動します**。

![セキュリティ/コンプライアンス センターで、[脅威&レビュー ユーザーが \> 報告 \> したメッセージ] を選択します。](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> ユーザーから報告されたメッセージ レポートが正しく機能するには、365 環境で監査ログを有効Office必要があります。  これは通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。 詳細については [、「Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)監査ログ検索を有効またはオフにする」を参照してください。

## <a name="what-permissions-are-needed-to-view-these-reports"></a>これらのレポートを表示するために必要なアクセス許可

この記事で説明されているレポートを表示して使用するには、セキュリティ/コンプライアンス センターの次のいずれかの役割グループのメンバー&必要があります。

- **組織の管理**
- **セキュリティ管理者**
- **セキュリティ閲覧者**
- **グローバル リーダー**

詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

**注**: Microsoft 365 管理センターで対応する Azure Active Directory ロールにユーザーを追加すると、セキュリティ & コンプライアンスセンターで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。

## <a name="what-if-the-reports-arent-showing-data"></a>レポートにデータが表示されない場合

レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを確認してください。 詳細については、「脅威からの保護 [」を参照してください](protect-against-threats.md)。

## <a name="related-topics"></a>関連項目

[EOP でのスパム対策およびマルウェア対策保護](anti-spam-and-anti-malware-protection.md)

[セキュリティ/コンプライアンス センターのスマート レポートと分析情報](reports-and-insights-in-security-and-compliance.md)

[セキュリティ/コンプライアンス センターでメール フロー レポート&表示する](view-mail-flow-reports.md)

[Defender for Office 365 のレポートを表示する](view-reports-for-atp.md)
