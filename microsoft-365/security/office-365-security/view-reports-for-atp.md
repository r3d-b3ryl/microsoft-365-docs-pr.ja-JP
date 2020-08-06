---
title: 高度な脅威保護のレポートを表示する
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: セキュリティ/コンプライアンスセンターで Office 365 Advanced Threat Protection のレポートを検索して使用し &amp; ます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 194ce245e02490a313effdeaad0715fdd8035a19
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577986"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection のレポートを表示する

Office 365 Advanced Threat Protection (ATP) 組織 (たとえば、Microsoft 365 E5 サブスクリプションまたは atp プラン1または ATP プラン2アドオン) には、さまざまなセキュリティ関連のレポートが含まれています。 [必要なアクセス許可](#what-permissions-are-needed-to-view-the-atp-reports)がある場合は、**レポート**ダッシュボードにアクセスすることによって、セキュリティ & コンプライアンスセンターでこれらのレポートを表示でき \> **Dashboard**ます。 レポートダッシュボードに直接移動するには、を開き <https://protection.office.com/insightdashboard> ます。

![セキュリティ & コンプライアンスセンターのレポートダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a>Advanced Threat Protection ファイルの種類レポート

**Advanced Threat Protection のファイルの種類レポート**レポートには、 [ATP の安全な添付](atp-safe-attachments.md)ファイルによって検出されたファイルの種類が表示されます。

 レポートの集計ビューでは90日間のフィルター処理が可能になりますが、詳細ビューでは10日間のフィルター処理のみが可能です。

レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート** \> **ダッシュボード**] に移動して、[ **Office ATP ファイルの種類**] を選択します。 レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=ATPFileReport> ます。

![レポートダッシュボードの Office ATP ファイルの種類ウィジェット](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> このレポートの情報は、 [Advanced Threat Protection メッセージの廃棄レポート](#advanced-threat-protection-message-disposition-report)でも利用できます。

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a>高度な脅威保護のファイルの種類レポートのレポートビュー

次のビューを利用できます。

- **データの表示方法: ファイル**: グラフには、次の情報が含まれています。

  - **悪意のある Excel 添付ファイル**
  - **悪意のあるフラッシュ添付ファイル**
  - **悪意のある PDF 添付ファイル**
  - **悪意のある PowerPoint 添付ファイル**
  - **悪意のある Url**
  - **悪意のある Word 添付ファイル**
  - **悪意のある実行可能ファイルの添付ファイル**
  - **Others**

  特定の日 (データポイント) にカーソルを移動すると、EOP での[ATP の安全な添付](atp-safe-attachments.md)ファイルと[マルウェア対策保護](anti-malware-protection.md)によって検出された悪意のあるファイルの種類の内訳を確認できます。

  ![ATP ファイルの種類レポートのファイルビュー](../../media/atp-file-types-report-file-view.png)

  [**フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。

  - **開始日**と**終了日**
  - グラフに表示されているものと同じファイルの種類の値。

- **データの表示: メッセージ**: グラフには次の情報が含まれています。

  - **アクセスをブロックする**
  - **置き換えられるメッセージ**
  - **監視されたメッセージ**
  - **動的な電子メール配信に置き換え**ます。詳細については、「[動的配信と、ATP の安全な添付ファイルを使用したプレビュー](dynamic-delivery-and-previewing.md)」を参照してください。

  ![ATP ファイルの種類レポートのメッセージビュー](../../media/atp-file-types-report-message-view.png)

  [**フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。

  - **開始日**と**終了日**
  - グラフで使用できるものと同じメッセージの廃棄値、および値が**渡さ**れる追加メッセージ。

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a>高度な脅威保護のファイルの種類レポートの詳細表ビュー

[**詳細テーブルの表示**] をクリックすると、過去10日間に組織内で発生したすべてのクリックが、ほぼリアルタイムで表示されます。 表示される情報は、表示されていたグラフによって異なります。

- **データの表示方法: ファイル**:

  - **Date**
  - **受信者のアドレス**
  - **[送信者のアドレス]**
  - メッセージ**id**: メッセージヘッダーの**メッセージ id**ヘッダーフィールドで利用可能で、一意である必要があります。 値の例を次に示し `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` ます (角かっこに注意してください)。
  - **File**

  [**フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。

  - **開始日**と**終了日**
  - グラフに表示されているものと同じファイルの種類の値。

- **データの表示: メッセージ**:

  - **Date**
  - **受信者のアドレス**
  - **[送信者のアドレス]**
  - **[メッセージ ID]**
  - **File**
  - **[件名]**

  [**フィルター**] をクリックすると、次のフィルターを使用して結果を変更できます。

  - **開始日**と**終了日**
  - グラフで使用できるものと同じメッセージの廃棄値、および値が**渡さ**れる追加メッセージ。

レポートビューに戻るには、[**レポートの表示**] をクリックします。

## <a name="advanced-threat-protection-message-disposition-report"></a>Advanced Threat Protection メッセージの廃棄レポート

**ATP メッセージディスポジション**レポートには、悪意のあるコンテンツが含まれていることが検出された電子メールメッセージに対して実行されたアクションが表示されます。

レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard**て、[ **Office ATP メッセージ廃棄**] を選択します。 レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=ATPMessageReport> ます。

![レポートダッシュボードの Office 365 ATP メッセージ廃棄ウィジェット](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> このレポートの情報は、 [Advanced Threat Protection のファイルの種類レポート](#advanced-threat-protection-file-types-report)でも利用できます。

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a>Advanced Threat Protection メッセージ廃棄レポートのレポートビュー

次のビューを利用できます。

- **データの表示: メッセージ**: グラフには次の情報が含まれています。

  - **アクセスをブロックする**
  - **置き換えられるメッセージ**
  - **監視されたメッセージ**
  - **動的な電子メール配信に置き換え**ます。詳細については、「[動的配信と、ATP の安全な添付ファイルを使用したプレビュー](dynamic-delivery-and-previewing.md)」を参照してください。

  ![ATP ファイルの種類レポートのメッセージビュー](../../media/atp-file-types-report-message-view.png)

  [**フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。

  - **開始日**と**終了日**
  - グラフで使用できるものと同じメッセージの廃棄値、および値が**渡さ**れる追加メッセージ。

- **データの表示方法: ファイル**: グラフには、次の情報が含まれています。

  - **悪意のある Excel 添付ファイル**
  - **悪意のあるフラッシュ添付ファイル**
  - **悪意のある PDF 添付ファイル**
  - **悪意のある PowerPoint 添付ファイル**
  - **悪意のある Url**
  - **悪意のある Word 添付ファイル**
  - **悪意のある実行可能ファイルの添付ファイル**
  - **Others**

  特定の日 (データポイント) にカーソルを移動すると、EOP での[ATP の安全な添付](atp-safe-attachments.md)ファイルと[マルウェア対策保護](anti-malware-protection.md)によって検出された悪意のあるファイルの種類の内訳を確認できます。

  ![ATP ファイルの種類レポートのファイルビュー](../../media/atp-file-types-report-file-view.png)

  [**フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。

  - **開始日**と**終了日**
  - グラフに表示されているものと同じファイルの種類の値。

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a>Advanced Threat Protection メッセージ廃棄レポートの詳細表ビュー

[**詳細テーブルの表示**] をクリックすると、過去10日間に組織内で発生したすべてのクリックが、ほぼリアルタイムで表示されます。 表示される情報は、表示されていたグラフによって異なります。

- **データの表示: メッセージ**:

  - **Date**
  - **受信者のアドレス**
  - **[送信者のアドレス]**
  - **[メッセージ ID]**
  - **File**
  - **[件名]**

  [**フィルター**] をクリックすると、次のフィルターを使用して結果を変更できます。

  - **開始日**と**終了日**
  - グラフで使用できるものと同じメッセージの廃棄値、および値が**渡さ**れる追加メッセージ。

- **データの表示方法: ファイル**:

  - **Date**
  - **受信者のアドレス**
  - **[送信者のアドレス]**
  - **[メッセージ ID]**
  - **File**

  [**フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。

  - **開始日**と**終了日**
  - グラフに表示されているものと同じファイルの種類の値。

レポートビューに戻るには、[**レポートの表示**] をクリックします。

## <a name="threat-protection-status-report"></a>脅威保護の状態レポート

**脅威保護の状態**レポートは、悪意のあるコンテンツや悪意のある電子メールに関する情報をまとめた1つのビューで、 [Exchange Online protection](exchange-online-protection-overview.md) (EOP) および Office 365 ATP によって検出されブロックされます。 詳細については、「[脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)」を参照してください。

## <a name="url-threat-protection-report"></a>URL の脅威保護レポート

**Url 脅威保護レポート**には、検出された脅威と、 [ATP の安全なリンク](atp-safe-links.md)の一部として、URL クリックに対して行われた操作の概要と傾向のビューが表示されます。 このレポートには、安全なリンクポリシーが適用されているユーザーのクリックデータがありません。 [ユーザーのクリックを**追跡**しない] オプションが選択されています。

レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート** \> **ダッシュボード**] に移動して、[ **URL 保護レポート**] を選択します。 レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=URLProtectionActionReport> ます。

![レポートダッシュボードの URL 保護レポートウィジェット](../../media/url-protection-report-widget.png)

> [!NOTE]
> これは、*保護傾向レポート*で、データが大きなデータセット内の傾向を表すことを意味します。 その結果、集計ビュー内のデータはリアルタイムでは使用できませんが、[詳細] テーブルビューのデータは、2つのビューの間に若干の違いがあることがわかります。

### <a name="report-view-for-the-url-threat-protection-report"></a>URL 脅威保護レポートのレポートビュー

**URL 脅威保護**レポートには、過去90日間のデータを表示する4時間ごとに更新される2つの集計ビューがあります。

- **[URL] [保護アクション] をクリック**します。組織内のユーザーによる URL クリック数、およびクリックの結果が表示されます。

  - **ブロック**(ユーザーが URL への移動をブロックされた)
  - **ブロックとクリックスルー**
  - **スキャン中にクリックでクリック**

  クリックすると、ユーザーが悪意のある web サイトをクリックしたことを示します (管理者は、安全なリンクポリシーでクリックを無効にすることができます)。

  [**フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。

  - **開始日**と**終了日**
  - 利用可能なクリック保護アクションと**許容さ**れる値 (ユーザーが URL への移動を許可されたもの)。

  ![URL URL の脅威保護レポートにある [保護アクション表示] をクリックします。](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **Url [アプリケーションごと]**: OFFICE 365 ATP の安全なリンクをサポートしているアプリケーションによる url クリックの数を表示します。

  - **電子メール クライアント**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **その他**

  [**フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。

  - **開始日**と**終了日**
  - 利用可能なアプリケーション。

### <a name="details-table-view-for-the-url-threat-protection-report"></a>URL 脅威保護レポートの詳細表ビュー

[**詳細テーブルの表示**] をクリックすると、このレポートでは、過去7日間の組織内で発生したすべてのクリックが、次のようなほぼリアルタイムで表示されます。

- **[時刻] をクリック**
- **ユーザー**
- **URL**
- **操作**
- **App**

詳細テーブルビューで [**フィルター** ] をクリックすると、レポートビューと同じ条件で、およびコンマで区切られた**ドメイン**または**受信者**によってフィルター処理を行うことができます。

レポートビューに戻るには、[**レポートの表示**] をクリックします。

## <a name="additional-reports-to-view"></a>表示する追加レポート

このトピックで説明する ATP レポートに加えて、次の表に示すように、他のいくつかのレポートも利用できます。

|レポート|トピック|
|---|---|
|**エクスプローラー** (atp plan 2) または**リアルタイム検出**(atp プラン 1)|[脅威エクスプローラー (およびリアルタイムの検出)](threat-explorer.md)|
|上位の送信者と受信者レポート、スプーフィングメールレポート、スパム検出レポートなどの**電子メールセキュリティレポート**。|[セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する](view-email-security-reports.md)|
|転送レポート、メールフロー状態レポート、上位の送信者と受信者レポートなどの**メールフローレポート**。|[セキュリティ & コンプライアンスセンターでメールフローレポートを表示する](view-mail-flow-reports.md)|
|**ATP の安全なリンクの URL トレース**(PowerShell のみ)。 このコマンドレットの出力では、過去7日間の ATP の安全なリンクアクションの結果が表示されます。|[取得-UrlTrace](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**EOP および ATP のメールトラフィック結果**(PowerShell のみ)。 このコマンドレットの出力には、ドメイン、日付、イベントの種類、方向、アクション、およびメッセージ数に関する情報が含まれています。|[Get-mailtrafficatpreport](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport) <br/><br/> |
|**EOP および ATP の検出に関するメール詳細レポート**(PowerShell のみ)。 このコマンドレットの出力には、悪意のあるファイルまたは Url、フィッシングの試行、偽装、その他の電子メールやファイルの潜在的な脅威に関する詳細が記載されています。|[Get-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>ATP レポートを表示するには、どのようなアクセス許可が必要ですか。

このトピックで説明されているレポートを表示して使用するには、**セキュリティ &amp; コンプライアンスセンターと Exchange 管理センターの両方に対して適切な役割が割り当てられている必要があり**ます。

- セキュリティ & コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。

  - 組織管理
  - セキュリティ管理者 (Azure Active Directory 管理センターで割り当て [https://aad.portal.azure.com](https://aad.portal.azure.com) 可能)
  - Security Operator (Azure Active Directory 管理センター () で割り当てることができます [https://aad.portal.azure.com](https://aad.portal.azure.com) )
  - セキュリティ閲覧者

- Exchange Online の場合は、Exchange 管理センター ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) または PowerShell コマンドレット (「 [Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。

  - 組織の管理
  - 表示限定の組織管理
  - "View-Only Recipients/表示専用受信者" 役割
  - コンプライアンス管理

詳細については、次のリソースを参照してください。

- [セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online の機能アクセス許可](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a>レポートでデータが表示されない場合はどうなりますか。

ATP レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを再確認してください。 組織で atp の[安全なリンクポリシー](set-up-atp-safe-links-policies.md)と[atp の安全な添付ファイルのポリシー](set-up-atp-safe-attachments-policies.md)が定義されている必要があります。これは、atp 保護を適切に実行するためです。 また、「[スパム対策およびマルウェア対策保護 (Office 365](anti-spam-and-anti-malware-protection.md))」を参照してください。

## <a name="related-topics"></a>関連項目

[セキュリティ/コンプライアンス センターのスマート レポートと分析情報](reports-and-insights-in-security-and-compliance.md)
  
[役割のアクセス許可 (Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
