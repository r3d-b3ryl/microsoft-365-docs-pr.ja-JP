---
title: レポート ダッシュボードで Office 365 レポートの Defender を表示する
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: セキュリティ/コンプライアンス センターで microsoft Defender for Office 365 のレポート&使用します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3e5d48f6ac8f6246b65761f5728405c37333d71
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286599"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センター Officeレポート ダッシュボードで 365 レポートの Defender &表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Office 365 組織向け Microsoft Defender (たとえば、Microsoft 365 E5 サブスクリプション、Office 365 プラン 1 の Microsoft Defender、または Office 365 プラン 2 アドオン用の Microsoft Defender など) には、さまざまなセキュリティ関連レポートが含まれている。 必要なアクセス許可 [がある](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)場合は、レポート ダッシュボードに移動して、セキュリティ/コンプライアンス センター&レポート **を表示** \> **できます**。 レポート ダッシュボードに直接移動するには、開きます <https://protection.office.com/insightdashboard> 。

![セキュリティ/コンプライアンス センター& ダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a>Defender for Office 365 のファイル型レポート

Defender **for Office 365 ファイル** の種類レポートレポートには、安全な添付ファイルによって悪意のあるファイルとして検出されたファイルの種類 [が表示されます](atp-safe-attachments.md)。

 レポートの集計ビューでは 90 日間のフィルター処理が可能で、詳細ビューでは 10 日間のフィルター処理のみ可能です。

レポートを表示するには、[セキュリティ](https://protection.office.com)/コンプライアンス センターを開き&**ダッシュボード** に移動し、365 のファイルの種類に対して \> Defender **Officeを選択します**。 レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=ATPFileReport> 。

![レポート ダッシュボードOffice 365 ファイルの種類のウィジェット用 Defender](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> このレポートの情報は、Defender で Office [365 メッセージ廃棄レポートでも確認できます](#defender-for-office-365-message-disposition-report)。

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a>Defender for Office 365 ファイルの種類レポートのレポート ビュー

次のビューを利用できます。

- **View data by: File**: the chart contains the following information:

  - **悪意のある Excel 添付ファイル**
  - **悪意のある Flash 添付ファイル**
  - **悪意のある PDF 添付ファイル**
  - **悪意のある PowerPoint 添付ファイル**
  - **悪意のある URL**
  - **悪意のある Word の添付ファイル**
  - **悪意のある実行可能ファイル**
  - **Others**

  特定の日 (データ ポイント) をポイントすると[、EOP](anti-malware-protection.md)の安全な添付ファイルとマルウェア対策保護[](atp-safe-attachments.md)によって検出された悪意のあるファイルの種類の内訳を確認できます。

  ![Defender for Office 365 ファイル の種類レポートのファイル ビュー](../../media/atp-file-types-report-file-view.png)

  [フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - グラフに表示されているのと同じファイルの種類の値。

- **View data by: Message**: the chart contains the following information:

  - **アクセスをブロックする**
  - **置き換えられたメッセージ**
  - **監視対象のメッセージ**
  - **動的電子メール配信に置き換** えられた : 詳細については、「安全な添付ファイル ポリシー [での動的配信」を参照してください](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)。

  ![365 のファイルの種類レポートOffice Defender のメッセージ ビュー](../../media/atp-file-types-report-message-view.png)

  [フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - グラフで使用可能な同じメッセージ廃棄値と、追加のメッセージ渡 **し** 値。

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a>Defender for Office 365 ファイルの種類レポートの詳細テーブル ビュー

[詳細の **表示]** テーブルをクリックすると、過去 10 日間に組織内で発生したクリックのほぼリアルタイムのビューがレポートに表示されます。 表示される情報は、表示されているグラフによって異なります。

- **データの表示方法: ファイル**:

  - **日付**
  - **受信者のアドレス**
  - **[送信者のアドレス]**
  - **メッセージ ID**: メッセージ ヘッダーの **Message-ID** ヘッダー フィールドで使用できます。一意である必要があります。 値の例を `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 次に示します (角かっこに注意してください)。
  - **File**

  [フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - グラフに表示されているのと同じファイルの種類の値。

- **View data by: Message**:

  - **日付**
  - **受信者のアドレス**
  - **[送信者のアドレス]**
  - **[メッセージ ID]**
  - **File**
  - **[件名]**

  [フィルター] **をクリック** すると、次のフィルターを使用して結果を変更できます。

  - **開始日と****終了日**
  - グラフで使用可能な同じメッセージ廃棄値と、追加のメッセージ渡 **し** 値。

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="defender-for-office-365-message-disposition-report"></a>Defender for Office 365 のメッセージ処理レポート

**ATP Message Disposition レポートには**、悪意のあるコンテンツが含みと検出された電子メール メッセージに対して実行されたアクションが表示されます。

レポートを表示するには、[セキュリティ](https://protection.office.com)/コンプライアンス センターを開き&**ダッシュボード** に移動し \> **、365** メッセージの廃棄に対して Defender Officeを選択します。 レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=ATPMessageReport> 。

![レポート ダッシュボードOffice 365 メッセージ廃棄ウィジェットの Defender](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> このレポートの情報は、365 種類のファイルの種類 [に関するレポートOffice Defender でも確認できます](#defender-for-office-365-file-types-report)。

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a>Defender for Office 365 メッセージ廃棄レポートのレポート ビュー

次のビューを利用できます。

- **View data by: Message**: the chart contains the following information:

  - **アクセスをブロックする**
  - **置き換えられたメッセージ**
  - **監視対象のメッセージ**
  - **動的電子メール配信に置き換** えられた : 詳細については、「安全な添付ファイル ポリシー [での動的配信」を参照してください](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)。

  ![365 のファイルの種類レポートOffice Defender のメッセージ ビュー](../../media/atp-file-types-report-message-view.png)

  [フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - グラフで使用可能な同じメッセージ廃棄値と、追加のメッセージ渡 **し** 値。

- **View data by: File**: the chart contains the following information:

  - **悪意のある Excel 添付ファイル**
  - **悪意のある Flash 添付ファイル**
  - **悪意のある PDF 添付ファイル**
  - **悪意のある PowerPoint 添付ファイル**
  - **悪意のある URL**
  - **悪意のある Word の添付ファイル**
  - **悪意のある実行可能ファイル**
  - **Others**

  特定の日 (データ ポイント) をポイントすると[、EOP](anti-malware-protection.md)の安全な添付ファイルとマルウェア対策保護[](atp-safe-attachments.md)によって検出された悪意のあるファイルの種類の内訳を確認できます。

  ![Defender for Office 365 ファイル の種類レポートのファイル ビュー](../../media/atp-file-types-report-file-view.png)

  [フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - グラフに表示されているのと同じファイルの種類の値。

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a>Defender for Office 365 メッセージ廃棄レポートの詳細テーブル ビュー

[詳細の **表示]** テーブルをクリックすると、過去 10 日間に組織内で発生したクリックのほぼリアルタイムのビューがレポートに表示されます。 表示される情報は、表示されているグラフによって異なります。

- **View data by: Message**:

  - **日付**
  - **受信者のアドレス**
  - **[送信者のアドレス]**
  - **[メッセージ ID]**
  - **File**
  - **[件名]**

  [フィルター] **をクリック** すると、次のフィルターを使用して結果を変更できます。

  - **開始日と****終了日**
  - グラフで使用可能な同じメッセージ廃棄値と、追加のメッセージ渡 **し** 値。

- **データの表示方法: ファイル**:

  - **日付**
  - **受信者のアドレス**
  - **[送信者のアドレス]**
  - **[メッセージ ID]**
  - **File**

  [フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - グラフに表示されているのと同じファイルの種類の値。

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="mail-latency-report"></a>メール待機時間レポート

[ **メールの待機時間]** レポートには、組織内で発生したメール配信と分析の待機時間の集計ビューが表示されます。 サービス内のメール配信時間は、多くの要因によって影響を受け、絶対配信時間 (秒) は成功や問題を示す良い指標ではない場合があります。 ある日の遅い配信時間は、別の日の平均配信時間、またはその逆と見なされる場合があります。 メール **待機時間レポートは、他** のメッセージの観察された配信時間に関する統計データに基づいて、メッセージ配信の条件を設定しようと試みられます。

- **50 パーセント**: これは、メッセージの配信時間の中間です。 この値は、平均配信時間と見なされます。
- **90 パーセント**: これは、メッセージ配信の待機時間が長い状態を示します。 配信にこの値を超える時間がかかったのはメッセージの 10% のみです。
- **99 パーセント**: これは、メッセージ配信の待機時間が最も長いかどうかを示します。

クライアント側とネットワークの待機時間は含まれません。

レポートを表示するには、セキュリティ/[](https://protection.office.com)コンプライアンス センターを&レポート ダッシュボードに移動し、[メールの待機時間] \> **レポートを選択します**。 レポートに直接移動するには、開きます <https://protection.office.com/mailLatencyReport?viewid=P50> 。

![レポート ダッシュボードのメール待機時間レポート ウィジェット](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a>メール待機時間レポートのレポート ビュー

レポートを開く場合、既定では **[50** 番目の割合] タブが選択されます。

既定では、このビューには次のフィルターで構成されたグラフが含まれます。

- **日付**: 過去 7 日間
- **メッセージ ビュー**:
  - デトニートされたメッセージ

このグラフには、次のカテゴリに分類されたメッセージが表示されます。

- **メール配信の待機時間**
- **デトレーションの待機時間**

グラフのカテゴリにマウス ポインターを合わせると、各カテゴリの待機時間の内訳が表示されます。

![メール待機時間レポート](../../media/mail-latency-report.png)

レポート ビューで **[フィルター]** をクリックすると、次のフィルターを使用して結果を変更できます。

- すべてのメッセージ
- 添付ファイルまたは URL を含むメッセージ

**[90** 番目のパーセント] タブまたは **[99** 番目のパーセント] タブをクリックすると **、50** 番目のパーセント ビューの同じ既定のフィルターが使用されます。

### <a name="details-table-view-for-the-mail-latency-report"></a>メール待機時間レポートの詳細テーブル ビュー

詳細テーブル ビューには、次の情報が表示されます。

- **日付**
- **Percentiles**
- **メッセージ数**
- **全体的な待機時間**

![メール待機時間レポートの詳細](../../media/mail-latency-report-details.png)

上の例では、11 月 14 日に配信され、デトトされたメッセージの平均待機時間は **108.033** 秒でした。

詳細テーブルには、各タブに同じ情報が含まれる。

## <a name="threat-protection-status-report"></a>脅威保護の状態レポート

脅威 **保護** 状態レポートは [、Exchange Online Protection](exchange-online-protection-overview.md) (EOP) と microsoft Defender for Office 365 によって検出およびブロックされた悪意のあるコンテンツと悪意のある電子メールに関する情報をまとめる単一ビューです。 詳細については、「脅威保護の [状態レポート」を参照してください](view-email-security-reports.md#threat-protection-status-report)。

## <a name="url-threat-protection-report"></a>URL 脅威保護レポート

**URL 脅威保護レポートは、** 検出された脅威と、安全なリンクの一部として URL クリックに対して実行されたアクションの概要と傾向ビュー [を提供します](atp-safe-links.md)。 このレポートには、安全なリンク ポリシーが適用されているユーザーからのクリック データが表示されません。[ユーザーのクリックを追跡しない] オプション **が** 選択されています。

レポートを表示するには、セキュリティ/コンプライアンス センター&[開](https://protection.office.com)き、[レポート **ダッシュボード]** に移動し、[URL 保護 \> ]**レポートを選択します**。 レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=URLProtectionActionReport> 。

![レポート ダッシュボードの URL 保護レポート ウィジェット](../../media/url-protection-report-widget.png)

> [!NOTE]
> これは保護傾向 *レポートで、* データは大規模データセットの傾向を表します。 その結果、集計ビューのデータは、ここではリアルタイムでは使用できませんが、詳細テーブル ビューのデータなので、2 つのビューの間にわずかな不一致が表示される場合があります。

### <a name="report-view-for-the-url-threat-protection-report"></a>URL 脅威保護レポートのレポート ビュー

**URL 脅威保護レポートには**、過去 90 日間のデータを表示する 4 時間ごとに 1 回更新される 2 つの集計ビューがあります。

- **URL クリック保護アクション**: 組織内のユーザーによる URL クリックの数とクリックの結果を示します。

  - **ブロック (** ユーザーが URL への移動をブロックされました)
  - **ブロックしてクリックスルーする**
  - **スキャン中のクリックスルー**

  クリックは、ユーザーがブロック ページをクリックして悪意のある Web サイトに移動したかどうかを示します (管理者は、安全なリンク ポリシーでクリックスルーを無効にできます)。

  [フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - 使用可能なクリック保護アクションに、許可 **された** 値 (ユーザーは URL への移動を許可された)。

  ![URL の脅威保護レポートの URL クリック保護アクション ビュー](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **アプリケーション別 URL** クリック : 安全なリンクをサポートするアプリケーション別の URL クリック数を示します。

  - **電子メール クライアント**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **その他**

  [フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - 使用可能なアプリケーション。

### <a name="details-table-view-for-the-url-threat-protection-report"></a>URL 脅威保護レポートの詳細テーブル ビュー

[詳細の **表示]** テーブルをクリックすると、組織内で過去 7 日間に発生したクリックのほぼリアルタイムビューがレポートに表示されます。詳細は次のとおりです。

- **クリック時間**
- **ユーザー**
- **URL**
- **操作**
- **App**

詳細テーブル ビューで **[** フィルター] をクリックすると、レポート ビューと同じ条件でフィルター処理したり、ドメインまたは受信者をコンマで区切ってフィルター処理することができます。

> [!NOTE]
> Domains **フィルターは** 、レポートの結果に記載されている URL ドメインを参照します。 

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="additional-reports-to-view"></a>表示するその他のレポート

この記事で説明するレポートに加えて、次の表で説明するように、他のいくつかのレポートを使用できます。

****

|レポート|トピック|
|---|---|
|**エクスプローラー** (Microsoft Defender for Office 365 プラン 2) またはリアルタイムの検出 **(Microsoft** Defender for Office 365 プラン 1)|[脅威エクスプローラー (およびリアルタイムの検出)](threat-explorer.md)|
|**上位の送信者** と受信者のレポート、スプーフィング メール レポート、スパム検出レポートなどの電子メール セキュリティ レポート。|[セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する](view-email-security-reports.md)|
|**転送レポート、** メールフローステータス レポート、上位送信者と受信者レポートなどのメール フロー レポート。|[セキュリティ/コンプライアンス センターでメール フロー レポート&表示する](view-mail-flow-reports.md)|
|**安全なリンクの URL トレース** (PowerShell のみ)。 このコマンドレットの出力には、過去 7 日間の安全なリンクアクションの結果が表示されます。|[Get-UrlTrace](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**EOP と Microsoft Defender のメール トラフィックの結果は、Office 365** 用です (PowerShell のみ)。 このコマンドレットの出力には、Domain、Date、Event Type、Direction、Action、および Message Count に関する情報が含まれる。|[Get-MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|**365 の検出に関する EOP** および Defender Office詳細レポート (PowerShell のみ)。 このコマンドレットの出力には、悪意のあるファイルまたは URL、フィッシング詐欺の試み、偽装、および電子メールまたはファイル内のその他の潜在的な脅威に関する詳細が含されます。|[Get-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>365 レポートの Defender を表示するために必要Officeアクセス許可

この記事で説明されているレポートを表示して使用するには、セキュリティ/コンプライアンス センターの次のいずれかの役割グループのメンバー&があります。

- **組織の管理**
- **セキュリティ管理者**
- **セキュリティ閲覧者**
- **グローバル閲覧者**

詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

**注**: Microsoft 365 管理センターで対応する Azure Active Directory ロールにユーザーを追加すると、セキュリティ & コンプライアンスセンターで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="what-if-the-reports-arent-showing-data"></a>レポートにデータが表示されない場合

365 レポートのデータが Defender にOffice場合は、ポリシーが正しく設定されていることを確認してください。 Defender for [](set-up-atp-safe-links-policies.md) Office 365 保護を適用するには、組織に安全なリンク ポリシーと安全な添付ファイル ポリシーが定義されている必要があります。 [](set-up-atp-safe-attachments-policies.md) スパム対策 [とマルウェア対策保護も参照してください](anti-spam-and-anti-malware-protection.md)。

## <a name="related-topics"></a>関連項目

[セキュリティ/コンプライアンス センターのスマート レポートと分析情報](reports-and-insights-in-security-and-compliance.md)

[ロールのアクセス許可 (Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
