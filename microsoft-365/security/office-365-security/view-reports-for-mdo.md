---
title: Defender for Office 365 レポートを表示する
f1.keywords:
- CSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、Defender を検索して使用して、Office 365ポータルで使用できるレポートをMicrosoft 365 Defenderできます。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: de0dd5b7c0466a722a788ee3fe4e6c843d70f5eb
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63680976"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a>[Defender for Office 365] Microsoft 365 Defenderポータル

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Office 365 組織向け Microsoft Defender (Microsoft 365 E5 サブスクリプション、Office 365 プラン 1 の Microsoft Defender、Office 365 プラン 2 アドオンの Microsoft Defender など) には、さまざまなセキュリティ関連レポートが含まれる。 必要なアクセス許可[を持っている場合](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)は、これらのレポートを表示して、このポータルMicrosoft 365 Defenderできます。

## <a name="view-and-download-reports"></a>レポートを表示してダウンロードする

### <a name="view-reports"></a>レポートの表示

1. [電子メール Microsoft 365 Defender] の [<https://security.microsoft.com>\>レポートの電子メール] &**コラボレーション** \> レポート **&移動します**。 [コラボレーション レポートの電子メール] **ページ&移動するには** 、 を使用します <https://security.microsoft.com/emailandcollabreport>。

1. 表示するレポートを選択し、[詳細の表示] **を選択します**。  

### <a name="download-reports"></a>レポートのダウンロード

1. [レポート] Microsoft 365 Defenderの <https://security.microsoft.com>[**ReportsEmail** > ] に移動し、&**コラボレーション レポート** \> **をダウンロードします**。 [ダウンロード用のレポート] **ページに直接移動するには** 、 を使用します <https://security.microsoft.com/ReportsForDownload?viewid=custom>。

![[&] ポータルの [コラボレーション レポート] ページにMicrosoft 365 Defenderメールを送信します。](../../media/email-collaboration-download-reports.png)

> [!NOTE]
>
> Defender を必要としない電子メール セキュリティ レポートについては、「Office 365ポータルの電子メール セキュリティ レポートの表示」[でMicrosoft 365 Defenderされています](view-email-security-reports.md)。
>
> メール フローに関連するレポートは、現在、Exchangeセンター (EAC) に表示されます。 これらのレポートの詳細については、「新しい管理センターのメール フロー [レポートExchange参照してください](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。

## <a name="safe-attachments-file-types-report"></a>セーフ添付ファイルの種類レポート

> [!NOTE]
> このレポートは廃止されました。 脅威保護の状態レポートでも同 [じ情報を使用できます](#threat-protection-status-report)。

## <a name="safe-attachments-message-disposition-report"></a>セーフ添付ファイル メッセージ廃棄レポート

> [!NOTE]
> このレポートは廃止されました。 脅威保護の状態レポートでも同 [じ情報を使用できます](#threat-protection-status-report)。

## <a name="mail-latency-report"></a>メール遅延レポート

[ **メール待機時間] レポートには** 、組織内で発生したメール配信とデトレーションの待機時間の集計ビューが表示されます。 サービス内のメール配信時間は、多くの要因によって影響を受け、絶対配信時間 (秒) は成功または問題を示す良い指標ではない場合が多いです。 ある日の配信時間が遅い場合は、別の日の平均配信時間、またはその逆と見なされる場合があります。 これにより、他のメッセージの観測配信時間に関する統計データに基づいて、メッセージ配信を修飾します。

クライアント側とネットワークの待機時間は含まれません。

レポートを表示するには、ポータルの [Microsoft 365 Defender <https://security.microsoft.com> \>] を開き、[レポートメール] &**コラボレーション** \> レポート **&移動します**。 [コラボレーション レポートの電子メール] **ページ&移動するには** 、 を使用します <https://security.microsoft.com/emailandcollabreport>。

[電子メール **&] コラボレーション** レポート ページで、[ **メールの待機時間** ] レポートを検索し、[詳細の表示] **をクリックします**。 レポートに直接移動するには、 を使用します <https://security.microsoft.com/mailLatencyReport>。

![[メール の遅延レポート] ウィジェットが [メール &] ページに表示されます。](../../media/mail-latency-report-widget.png)

[メール **の待機時間レポート] ページで** 、[メールの待機時間] レポート ページで次 **のタブを使用** できます。

- **50 パーセント**: これはメッセージの配信時間の中央です。 この値は、平均配信時間と見なされます。 このタブは既定で選択されています。
- **90 パーセント**: これは、メッセージ配信の待機時間が長いを示します。 配信にこの値を超える時間がかかったメッセージはわずか 10% です。
- **99 パーセント**: メッセージ配信の最大待機時間を示します。

選択したタブに関係なく、グラフには次のカテゴリに分類されたメッセージが表示されます。

- **メール配信の待機時間**
- **Detonations**

グラフのカテゴリにカーソルを合わせると、各カテゴリの待機時間の内訳を確認できます。

![メール待機時間レポートの 50 パーセント表示。](../../media/mail-latency-report-50th-percentile-view.png)

[フィルター] **をクリック** すると、グラフと詳細テーブルの両方を次の値でフィルター処理できます。

- **日付 (UTC)**: **開始日と****終了日**
- **メッセージ ビュー**: 次のいずれかの値。
  - **すべてのメッセージ**
  - **添付ファイルまたは URL を含むメッセージ**
  - **削除されたメッセージ**

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

グラフの下の詳細テーブルでは、次の情報を使用できます。

- **日付 (UTC)**
- **パーセント:** **50**、 **90**、 **または 99**
- **メッセージ数**
- **全体的な待機時間**

メイン レポート ページの [エクスポート] ![アイコン。](../../media/m365-cc-sc-download-icon.png) **[[エクスポート](view-email-security-reports.md#export-report)** ] ボタンを使用できます。

## <a name="threat-protection-status-report"></a>脅威保護の状態レポート

脅威 **保護の** 状態レポートは、Exchange Online Protection (EOP) と Microsoft Defender for [Office 365](exchange-online-protection-overview.md) によって検出およびブロックされた悪意のあるコンテンツと悪意のある電子メールに関する情報をまとめる単一のビューです。 詳細については、「脅威保護の [状態レポート」を参照してください](view-email-security-reports.md#threat-protection-status-report)。

## <a name="top-senders-and-recipients-report"></a>上位の送信者と受信者レポート

[**上位の送信者と受信者] レポートには**、EOP と Defender の保護機能の上位受信者Office 365表示されます。 詳細については、「上位の送信者 [と受信者レポート」を参照してください](view-email-security-reports.md#top-senders-and-recipients-report)。

## <a name="url-protection-report"></a>URL 保護レポート

**URL 保護レポートには、** 検出された脅威の概要と傾向ビュー、およびリンクの一部として URL クリックで行セーフ [されます](safe-links.md)。 このレポートには、[リンク] ポリシーが適用されているユーザーセーフのクリック データは表示されません。[ユーザーのクリックを追跡しない **] オプションが** 選択されています。

レポートを表示するには、レポート ポータルを開きMicrosoft 365 Defender[レポートの電子 [メール]](https://security.microsoft.com) \> &**コラボレーション** \> レポート **&移動します**。 [メール **の作成&] ページで** 、[URL 保護] **ページを** 見つけて、[詳細の表示] **をクリックします**。 レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/URLProtectionActionReport>。

![[メール] ページの [コラボレーション レポート] ページ& URL 保護レポート ウィジェット。](../../media/url-protection-report-widget.png)

[URL 保護レポート **] ページで** 使用可能なビューについては、次のセクションで説明します。

> [!NOTE]
> これは保護傾向 *レポートで、* データは大きなデータセットの傾向を表します。 その結果、グラフ内のデータはリアルタイムでは使用できませんが、詳細テーブルのデータは次の値なので、2 つのデータの間に若干の不一致が見られます。 グラフは 4 時間に 1 回更新され、過去 90 日間のデータが含まれています。

### <a name="view-data-by-url-click-protection-action"></a>URL クリック保護アクションによるデータの表示

![URL 保護レポートの [URL] クリック保護アクション ビュー。](../../media/url-threat-protection-report-url-click-protection-action-view.png)

[ **URL によるデータの表示] クリック保護アクション** ビューには、組織内のユーザーによる URL クリックの数と、クリックの結果が表示されます。

- **許可:** クリックが許可されます。
- **テナント管理者が許可** する: [リンク] ポリシーで許可セーフクリックします。
- **ブロック: [** ブロック] をクリックします。
- **テナント管理者によってブロック**: [リンク] ポリシーでブロックセーフクリックします。
- **ブロックおよびクリックスルー**: ユーザーがクリックしてブロックされた URL をクリックします。
- **テナント管理者によってブロックされ、クリック** スルー: 管理者はリンクをブロックしましたが、ユーザーはクリックスルーしました。
- **スキャン中にクリックスルー**: ユーザーが保留中のスキャン ページをクリックして URL をクリックします。
- **保留中のスキャン**: スキャンの評決を保留している URL をクリックします。

クリックすると、ユーザーがブロック ページをクリックして悪意のある Web サイトに移動した (管理者は、[リンク] ポリシーでクリックセーフ無効にできます)。

[フィルター] **をクリック** すると、表示されるフライアウトで次の値の 1 つ以上を選択して、レポートと詳細テーブルを変更できます。

- **日付 (UTC)**: **開始日と****終了日**
- **アクション**:
  - **可**
  - **ブロック済み**
  - **テナント管理者が許可する**
  - **ブロックおよびクリックスルー**
  - **テナント管理者がブロックし、クリックスルー**
  - **スキャン中にクリックスルー**
  - **保留中のスキャン**
- **ドメイン**: レポートの結果に表示される URL ドメイン。
- **受信者**

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

グラフの下の詳細テーブルには、過去 7 日間に組織内で発生したすべてのクリックのほぼリアルタイム ビューが示されています。

- **クリック時間**
- **ユーザー**
- **URL**
- **操作**
- **アプリ**

メイン レポート ページの [スケジュールの作成 ![] アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](view-email-security-reports.md#schedule-report)**、レポート ![の要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[レポートを要求](view-email-security-reports.md#request-report)** し、[エクスポート ![] アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](view-email-security-reports.md#export-report)** ボタンを使用できます。

### <a name="view-data-by-url-click-by-application"></a>アプリケーション別の URL クリックによるデータの表示

![URL 保護レポートのアプリケーション ビューで URL をクリックします。](../../media/url-threat-protection-report-url-click-by-application-view.png)

[**URL によるデータの表示] アプリケーション** によるクリックビューには、リンクをサポートするアプリによる URL クリック数セーフ表示されます。

- **電子メール クライアント**
- **Officeドキュメント**
- **Teams**

[フィルター] **をクリック** すると、表示されるフライアウトで次の値の 1 つ以上を選択して、レポートと詳細テーブルを変更できます。

- **日付 (UTC)**: **開始日と****終了日**
- **検出**: グラフから使用可能なアプリ。
- **ドメイン**: レポートの結果に表示される URL ドメイン。
- **受信者**

フィルターの構成が完了したら、[適用]、[キャンセル]、または [フィルターのクリア] **をクリックします**。

グラフの下の詳細テーブルには、過去 7 日間に組織内で発生したすべてのクリックのほぼリアルタイム ビューが示されています。

- **クリック時間**
- **ユーザー**
- **URL**
- **操作**
- **アプリ**

メイン レポート ページの [スケジュールの作成 ![] アイコン。](../../media/m365-cc-sc-create-icon.png) **[スケジュールの作成](view-email-security-reports.md#schedule-report)**、レポート ![の要求アイコン。](../../media/m365-cc-sc-download-icon.png) **[レポートを要求](view-email-security-reports.md#request-report)** し、[エクスポート ![] アイコンをクリックします。](../../media/m365-cc-sc-download-icon.png) **[エクスポート](view-email-security-reports.md#export-report)** ボタンを使用できます。

## <a name="additional-reports-to-view"></a>表示するその他のレポート

この記事で説明するレポートに加えて、次の表で説明するように、いくつかの他のレポートを使用できます。

|レポート|トピック|
|---|---|
|**エクスプローラー** (Microsoft Defender for Office 365 プラン 2) またはリアルタイム **検出 (Microsoft** Defender for Office 365 プラン 1)|[脅威エクスプローラー (およびリアルタイムの検出)](threat-explorer.md)|
|Defender を必要としない電子メール セキュリティ Office 365|[ポータルで電子メール セキュリティ レポートをMicrosoft 365 Defenderする](view-email-security-reports.md)|
|管理センター (EAC) Exchangeフロー レポート|[新しい管理センターのメール フロー Exchangeレポート](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|

PowerShell レポートコマンドレット:

|レポート|トピック|
|---|---|
|上位送信者および受信者|[Get-MailTrafficTopReport](/powershell/module/exchange/get-mailtraffictopreport) <p> [Get-MailTrafficSummaryReport](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|トップ マルウェア|[Get-MailTrafficSummaryReport](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|メール トラフィック|[Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <p> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|
|安全なリンク|[Get-SafeLinksAggregateReport](/powershell/module/exchange/get-safelinksaggregatereport) <p> [Get-SafeLinksDetailReport](/powershell/module/exchange/get-safelinksdetailreport)|
|侵害されたユーザー|[Get-CompromisedUserAggregateReport](/powershell/module/exchange/get-compromiseduseraggregatereport) <p> [Get-CompromisedUserDetailReport](/powershell/module/exchange/get-compromiseduserdetailreport)|
|メール フローの状態|[Get-MailflowStatusReport](/powershell/module/exchange/get-mailflowstatusreport)|
|スプーフィングされたユーザー|[Get-スプーフィングMailReport](/powershell/module/exchange/get-spoofmailreport)|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>レポートの Defender を表示するために必要なアクセス許可Office 365ですか?

この記事で説明するレポートを表示して使用するには、ポータルで次のいずれかの役割グループのメンバーであるMicrosoft 365 Defenderがあります。

- **組織の管理**
- **セキュリティ管理者**
- **セキュリティ閲覧者**
- **グローバル リーダー**

詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。

**注**: Microsoft 365 管理センター の対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="what-if-the-reports-arent-showing-data"></a>レポートにデータが表示されない場合は、

レポートのデータが Defender にOffice 365場合は、ポリシーが正しく設定されていることを確認してください。 Defender が保護をセーフするために、セーフ Office 365[リンク](set-up-safe-links-policies.md) ポリシー[](set-up-safe-attachments-policies.md)と添付セーフ添付ファイル ポリシーが定義されている必要があります。 「スパム [対策とマルウェア対策の保護」も参照してください](anti-spam-and-anti-malware-protection.md)。

## <a name="related-topics"></a>関連項目

[スマート レポートと分析情報 (Microsoft 365 Defender ポータル)](reports-and-insights-in-security-and-compliance.md)

[Azure AD組み込みの役割](/azure/active-directory/roles/permissions-reference)
