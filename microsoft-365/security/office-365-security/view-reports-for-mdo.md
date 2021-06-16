---
title: '[レポート] ダッシュボードでOffice 365レポートの Defender を表示する'
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
description: Microsoft Defender のレポートを検索して、Office 365 Defender ポータルMicrosoft 365使用します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5c45f58ee83de11712b198c85a8e423314289bf
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930234"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-microsoft-365-defender-portal"></a>Defender ポータルの [Office 365] ダッシュボードで[Defender for Microsoft 365レポートを表示する]

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Office 365 組織向け Microsoft Defender (Microsoft 365 E5 サブスクリプション、Office 365 プラン 1 の Microsoft Defender、Office 365 プラン 2 アドオンの Microsoft Defender など) には、さまざまなセキュリティ関連レポートが含まれる。 必要な [アクセス許可がある](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)場合は、[電子メールの共同作業レポート] にアクセスして、Microsoft 365 Defender ポータルでこれらのレポート \>  \> **を表示できます**。 レポート ダッシュボードに直接移動するには、を開きます <https://security.microsoft.com/emailandcollabreport> 。

![Defender ポータルの [レポート] Microsoft 365ダッシュボード](../../media/user-reported-messages.png)

## <a name="defender-for-office-365-file-types-report"></a>Defender for Office 365 のファイル型レポート

[**ファイルの種類Office 365の** Defender レポートには、添付ファイルによって悪意のあるファイルとして検出されたファイルセーフ [表示されます](safe-attachments.md)。

 レポートの集計ビューでは 90 日間のフィルター処理が可能ですが、詳細ビューでは 10 日間のフィルター処理のみ可能です。

レポートを表示するには、Defender ポータルの Microsoft 365 [開き、[](https://security.microsoft.com)レポートダッシュボード] に移動し、[Defender] を選択してファイルの種類 \> **Office 365します**。 レポートに直接移動するには、を開きます <https://protection.office.com/reportv2?id=ATPFileReport> 。

![レポート ダッシュボードOffice 365ファイルの種類ウィジェットの Defender](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> このレポートの情報は、メッセージ廃棄レポートの[Defender でもOffice 365使用できます](#defender-for-office-365-message-disposition-report)。

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a>[ファイルの種類] レポートの Defender Office 365ビュー

次のビューを利用できます。

- **データの表示方法: ファイル**: グラフには、次の情報が含まれます。

  - **悪意のあるExcel添付ファイル**
  - **悪意のあるフラッシュの添付ファイル**
  - **悪意のある PDF 添付ファイル**
  - **悪意のあるPowerPoint添付ファイル**
  - **悪意のある URL**
  - **悪意のある Word の添付ファイル**
  - **悪意のある実行可能ファイルの添付ファイル**
  - **Others**

  特定の日 (データ ポイント) にカーソルを合わせると[、EOP](safe-attachments.md)の セーフ 添付ファイルとマルウェア対策保護によって検出された悪意のあるファイルの種類の内訳を[確認できます](anti-malware-protection.md)。

  ![[ファイルの種類] レポートの [Defender Office 365ビュー]](../../media/atp-file-types-report-file-view.png)

  [フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - グラフに表示されるのと同じファイルの種類の値。

- **データの表示: メッセージ**: グラフには、次の情報が含まれます。

  - **アクセスをブロックする**
  - **置き換えられたメッセージ**
  - **監視対象のメッセージ**
  - **動的メール配信に置き換えられる**: 詳細については、「添付ファイル ポリシーの [動的配信セーフを参照してください](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)。

  ![[ファイルの種類] レポートの Defender Office 365表示](../../media/atp-file-types-report-message-view.png)

  [フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - グラフで使用できるのと同じメッセージ廃棄値と、その他の **メッセージ渡し値** 。

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a>[ファイルの種類] レポートの Defender Office 365ビュー

[詳細テーブル **の表示]** をクリックすると、過去 10 日間組織内で発生したすべてのクリックのほぼリアルタイム ビューがレポートに表示されます。 表示される情報は、表示されているグラフによって異なります。

- **データの表示方法: ファイル**:

  - **Date**
  - **受信者のアドレス**
  - **[送信者のアドレス]**
  - **メッセージ ID**: メッセージ ヘッダーの **[Message-ID** ヘッダー] フィールドで使用できます。一意である必要があります。 値の例は `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 次のようになります (角かっこに注意してください)。
  - **ファイル**

  [フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - グラフに表示されるのと同じファイルの種類の値。

- **データの表示方法: メッセージ**:

  - **Date**
  - **受信者のアドレス**
  - **[送信者のアドレス]**
  - **[メッセージ ID]**
  - **ファイル**
  - **[件名]**

  [フィルター] **をクリック** すると、次のフィルターを使用して結果を変更できます。

  - **開始日と****終了日**
  - グラフで使用できるのと同じメッセージ廃棄値と、その他の **メッセージ渡し値** 。

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="defender-for-office-365-message-disposition-report"></a>Defender for Office 365 のメッセージ処理レポート

**ATP メッセージ廃棄レポート** には、悪意のあるコンテンツが検出された電子メール メッセージに対して実行されたアクションが表示されます。

レポートを表示するには [、Microsoft 365 Defender ポータルを開](https://security.microsoft.com)き、[レポート電子メール & コラボレーション の電子メール & コラボレーション レポート] に移動し、[Defender] を選択してメッセージの廃棄Office 365 \>  \> **します**。 レポートに直接移動するには、を開きます <https://protection.office.com/reportv2?id=ATPMessageReport> 。

![レポート ダッシュボードOffice 365メッセージ廃棄ウィジェットの Defender](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> このレポートの情報は、ファイルの種類レポートの[Defender でもOffice 365参照できます](#defender-for-office-365-file-types-report)。

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a>メッセージ廃棄レポートの Defender Office 365ビュー

次のビューを利用できます。

- **データの表示: メッセージ**: グラフには、次の情報が含まれます。

  - **アクセスをブロックする**
  - **置き換えられたメッセージ**
  - **監視対象のメッセージ**
  - **動的メール配信に置き換えられる**: 詳細については、「添付ファイル ポリシーの [動的配信セーフを参照してください](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)。

  ![[ファイルの種類] レポートの Defender Office 365表示](../../media/atp-file-types-report-message-view.png)

  [フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - グラフで使用できるのと同じメッセージ廃棄値と、その他の **メッセージ渡し値** 。

- **データの表示方法: ファイル**: グラフには、次の情報が含まれます。

  - **悪意のあるExcel添付ファイル**
  - **悪意のあるフラッシュの添付ファイル**
  - **悪意のある PDF 添付ファイル**
  - **悪意のあるPowerPoint添付ファイル**
  - **悪意のある URL**
  - **悪意のある Word の添付ファイル**
  - **悪意のある実行可能ファイルの添付ファイル**
  - **Others**

  特定の日 (データ ポイント) にカーソルを合わせると[、EOP](safe-attachments.md)の セーフ 添付ファイルとマルウェア対策保護によって検出された悪意のあるファイルの種類の内訳を[確認できます](anti-malware-protection.md)。

  ![[ファイルの種類] レポートの [Defender Office 365ビュー]](../../media/atp-file-types-report-file-view.png)

  [フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - グラフに表示されるのと同じファイルの種類の値。

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a>メッセージ廃棄レポートの Defender の詳細Office 365ビュー

[詳細テーブル **の表示]** をクリックすると、過去 10 日間組織内で発生したすべてのクリックのほぼリアルタイム ビューがレポートに表示されます。 表示される情報は、表示されているグラフによって異なります。

- **データの表示方法: メッセージ**:

  - **Date**
  - **受信者のアドレス**
  - **[送信者のアドレス]**
  - **[メッセージ ID]**
  - **ファイル**
  - **[件名]**

  [フィルター] **をクリック** すると、次のフィルターを使用して結果を変更できます。

  - **開始日と****終了日**
  - グラフで使用できるのと同じメッセージ廃棄値と、その他の **メッセージ渡し値** 。

- **データの表示方法: ファイル**:

  - **Date**
  - **受信者のアドレス**
  - **[送信者のアドレス]**
  - **[メッセージ ID]**
  - **ファイル**

  [フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - グラフに表示されるのと同じファイルの種類の値。

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="mail-latency-report"></a>メール遅延レポート

[ **メール待機時間] レポートには** 、組織内で発生したメール配信とデトレーションの待機時間の集計ビューが表示されます。 サービス内のメール配信時間は、多くの要因によって影響を受け、絶対配信時間 (秒) は成功または問題を示す良い指標ではない場合が多いです。 ある日の配信時間が遅い場合は、別の日の平均配信時間、またはその逆と見なされる場合があります。 メール **遅延レポートは、** 他のメッセージの観測された配信時間に関する統計データに基づいて、メッセージ配信を修飾します。

- **50 パーセント :** これは、メッセージの配信時間の中央です。 この値は、平均配信時間と見なされます。
- **90 パーセント :** これは、メッセージ配信の待機時間が長いを示します。 配信にこの値を超える時間がかかったメッセージはわずか 10% です。
- **99 パーセント :** メッセージ配信の最大待機時間を示します。

クライアント側とネットワークの待機時間は含まれません。

レポートを表示するには [、Microsoft 365 Defender](https://security.microsoft.com)ポータルを開き、[メール& コラボレーション レポート] & [メールの遅延レポート] の下にある [詳細の表示] \>  \> **を** クリック **します**。  レポートに直接移動するには、を開きます <https://security.microsoft.com/mailLatencyReport> 。

![レポート ダッシュボードのメール待機時間レポート ウィジェット](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a>メール待機時間レポートのレポート ビュー

レポートを開いた場合、既定では **[50 番目** のパーセント] タブが選択されます。

既定では、このビューには、次のフィルターで構成されたグラフが含まれます。

- **日付**: 過去 7 日間
- **メッセージ ビュー**:
  - 削除されたメッセージ

このグラフには、次のカテゴリに分類されたメッセージが表示されます。

- **メール配信の待機時間**
- **デトナレーションの待機時間**

グラフのカテゴリにカーソルを合わせると、各カテゴリの待機時間の内訳を確認できます。

![メール遅延レポート](../../media/mail-latency-report.png)

レポート ビューで **[フィルター]** をクリックすると、次のフィルターを使用して結果を変更できます。

- すべてのメッセージ
- 添付ファイルまたは URL を含むメッセージ

**[90** 番目のパーセント] タブまたは **[99** 番目のパーセント] タブをクリックすると **、50** 番目のパーセントビューの既定のフィルターと同じフィルターが使用されます。

### <a name="details-table-view-for-the-mail-latency-report"></a>メール待機時間レポートの詳細テーブル ビュー

詳細テーブル ビューには、次の情報が表示されます。

- **Date**
- **パーセント**
- **メッセージ数**
- **全体的な待機時間**

![メール遅延レポートの詳細](../../media/mail-latency-report-details.png)

上記の結果、11 月 14 日に配信および削除されたメッセージの平均待機時間は **108.033** 秒でした。

詳細テーブルには、各タブに同じ情報が含まれている。

## <a name="threat-protection-status-report"></a>脅威保護の状態レポート

脅威 **保護の状態** レポートは [、Exchange Online Protection](exchange-online-protection-overview.md) (EOP) と Microsoft Defender for Office 365 によって検出およびブロックされた悪意のあるコンテンツと悪意のある電子メールに関する情報をまとめる単一のビューです。 詳細については、「脅威保護の [状態レポート」を参照してください](view-email-security-reports.md#threat-protection-status-report)。

## <a name="url-threat-protection-report"></a>URL 脅威保護レポート

**URL 脅威保護レポートには、** 検出された脅威の概要と傾向ビュー、および URL クリックに対するアクションが[リンク] リンクの一部としてセーフ [されます](safe-links.md)。 このレポートには、[リンク] ポリシーが適用されているユーザーセーフクリックデータが含まれる場合は、[ユーザーのクリックを追跡しない]**オプションが** 選択されています。

レポートを表示するには [、Microsoft 365 Defender ポータルを開](https://security.microsoft.com)き、[レポートの電子メール & コラボレーション レポート \>  \> **&]** に移動し **、[URL** 保護レポートの詳細を表示する] をクリックします。 レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/URLProtectionActionReport> 。

![レポート ダッシュボードの URL 保護レポート ウィジェット](../../media/url-protection-report-widget.png)

> [!NOTE]
> これは保護傾向 *レポートで、* データは大きなデータセットの傾向を表します。 その結果、集計ビューのデータはここではリアルタイムで使用できませんが、詳細テーブル ビューのデータは使用できないので、2 つのビューの間に若干の不一致が発生する可能性があります。

### <a name="report-view-for-the-url-threat-protection-report"></a>URL 脅威保護レポートのレポート ビュー

**URL 脅威保護レポートには**、過去 90 日間のデータを示す 4 時間に 1 回更新される 2 つの集計ビューがあります。

- **URL クリック保護アクション**: 組織内のユーザーによる URL クリックの数と、クリックの結果を示します。

  - **ブロック (** ユーザーが URL への移動をブロックされました)
  - **ブロックおよびクリックスルー (** ユーザーが URL への引き続き移動を選択しました)
  - **スキャン中にクリックスルー** (ユーザーがスキャンが完了する前にリンクをクリックしました)

  クリックすると、ユーザーがブロック ページをクリックして悪意のある Web サイトに移動した (管理者は、[リンク] ポリシーでクリックセーフ無効にできます)。

  [フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。

  - **開始日と****終了日**
  - 使用可能なクリック保護アクションと、値 **Allowed** (ユーザーが URL への移動を許可された) を追加します。

  ![URL 脅威保護レポートの URL クリック保護アクション ビュー](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **アプリケーション別 URL クリック**: リンクをサポートするアプリケーション別の URL クリック数セーフします。

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

[詳細テーブル **の表示]** をクリックすると、過去 7 日間組織内で発生したすべてのクリックのほぼリアルタイム ビューがレポートに表示されます。詳細は次のとおりです。

- **クリック時間**
- **ユーザー**
- **URL**
- **Action**
- **アプリ**

詳細テーブル ビュー **で [フィルター** ] をクリックすると、レポート ビューと同じ条件でフィルター処理したり、ドメインまたは受信者をコンマで区切ってフィルター処理できます。

> [!NOTE]
> [ **ドメイン] フィルター** は、レポートの結果に一覧表示されている URL ドメインを参照します。 

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="additional-reports-to-view"></a>表示するその他のレポート

この記事で説明するレポートに加えて、次の表で説明するように、いくつかの他のレポートを使用できます。

****

|レポート|トピック|
|---|---|
|**エクスプローラー** (Microsoft Defender for Office 365 プラン 2) またはリアルタイム検出 **(Microsoft** Defender for Office 365 プラン 1)|[脅威エクスプローラー (およびリアルタイムの検出)](threat-explorer.md)|
|**[上位の送信者** と受信者] レポート、スプーフィング メール レポート、スパム検出レポートなどの電子メール セキュリティ レポート。|[Defender ポータルで電子メール セキュリティ レポートMicrosoft 365表示する](view-email-security-reports.md)|
|**転送レポート、** メールフロー状態レポート、上位送信者と受信者レポートなどのメール フロー レポート。|[Defender ポータルでメール フロー レポートをMicrosoft 365する](view-mail-flow-reports.md)|
|**[リンク] リンクセーフ URL トレース**(PowerShell のみ)。 このコマンドレットの出力には、過去 7 日間セーフリンク アクションの結果が表示されます。|[Get-UrlTrace](/powershell/module/exchange/get-urltrace)|
|**EOP および Microsoft Defender for Office 365** トラフィックの結果 (PowerShell のみ)。 このコマンドレットの出力には、ドメイン、日付、イベントの種類、方向、アクション、およびメッセージ数に関する情報が含まれる。|[Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport)|
|**EOP と Defender のメール詳細レポート (powerShell Office 365)** このコマンドレットの出力には、悪意のあるファイルまたは URL、フィッシングの試み、偽装、電子メールまたはファイル内のその他の潜在的な脅威に関する詳細が含まれる。|[Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>レポートの Defender を表示するために必要なアクセス許可Office 365ですか?

この記事で説明するレポートを表示して使用するには、Defender ポータルの次のいずれかの役割グループのMicrosoft 365必要があります。

- **組織の管理**
- **セキュリティ管理者**
- **セキュリティ リーダー**
- **グローバル リーダー**

詳細については、「Defender ポータル[のアクセス許可」をMicrosoft 365してください](permissions-in-the-security-and-compliance-center.md)。

**注**: Microsoft 365 管理センターの対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365の他の機能に対するアクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="what-if-the-reports-arent-showing-data"></a>レポートにデータが表示されない場合は、

レポートのデータが Defender に表示されない場合Office 365ポリシーが正しく設定されていることを確認してください。 Defender for セーフ[保護](set-up-safe-links-policies.md)を有効セーフするために、[](set-up-safe-attachments-policies.md)組織にリンク ポリシーと添付ファイル Office 365が定義されている必要があります。 「スパム [対策とマルウェア対策の保護」も参照してください](anti-spam-and-anti-malware-protection.md)。

## <a name="related-topics"></a>関連項目

[Defender ポータルのスマート レポートMicrosoft 365分析情報](reports-and-insights-in-security-and-compliance.md)

[役割のアクセス許可 (Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
