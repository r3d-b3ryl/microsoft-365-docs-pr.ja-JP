---
title: 個人情報の漏えいを監視する
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MET150
description: 個人データの漏えいの監視に使用できる 3 つのツールについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c40078626948e51c0e43f06dd567967f3cff516
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58565650"
---
# <a name="monitor-for-leaks-of-personal-data"></a>個人情報の漏えいを監視する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


個人データの使用と転送を監視するために使用できるツールは数多くあります。このトピックでは、効果的な 3 つのツールについて説明します。

![個人データの使用と転送を監視するためのツール。](../../media/Monitor-for-leaks-of-personal-data-image1.png)

この図について:

- まず、SharePoint Online、OneDrive for Business、転送中のメールの個人データを監視するための Microsoft 365 データ損失防止レポートから開始します。これらのレポートは、個人データを監視するための最も詳細なレベルの内容を提供します。ただし、このレポートには Office 365 のすべてのサービスが含まれているわけではありません。

- 次に、アラート ポリシーと監査ログを使用して、サービス全体のアクティビティを監視します。進行中の監視を設定するか、監査ログを検索してインシデントを調査します。監査ログは、Sway、Power BI、電子情報開示、Dynamics 365、Power Automate、Microsoft Teams、管理アクティビティ、OneDrive for Business、SharePoint Online、転送中のメール、保管中のメールボックスなどのサービス全体で機能します。Skype の会話は保管中のメールボックスに含まれます。

- 最後に、Microsoft Cloud App Security を使用して、他の SaaS プロバイダーの機密データを含むファイルを監視します。機密情報の種類と統合ラベルを Azure Information Protection と Cloud App Security が有効な Office で使用できる機能が近日公開予定です。すべての SaaS アプリまたは特定のアプリ (Box など) に適用するポリシーを設定できます。Cloud App Security では、メールに添付されたファイルを含め、Exchange Online のファイルは検出されません。

## <a name="data-loss-prevention-reports"></a>データ損失防止レポート

データ損失防止 (DLP) ポリシーを作成したら、意図したとおりに動作し、コンプライアンスの遵守に役立っているかどうかを確認します。Office 365 の DLP レポートを使用すると、DLP ポリシーの一致項目、上書き、誤検知の数をすぐに確認したり、時間の経過とともに増加または減少する傾向があるかどうかを見極めたりできます。また、さまざまな方法でレポートをフィルター処理したり、グラフ上の線の特定のポイントを選択して詳細情報を表示したりできます。

DLP レポートを使用すると、以下のことを行えます。

- 特定の期間に絞り込み、スパイクや傾向の理由を理解します。
- 組織の DLP ポリシーに違反するビジネス プロセスを検出します。
- DLP ポリシーのビジネスに及ぼす影響を理解します。
- ユーザーがポリシーを上書きしたり、誤検知を報告したりしてポリシーのヒントを解決するときに送信する正当な理由を表示します。
- 特定の DLP ポリシーに関する一致箇所を表示することによって、そのポリシーのコンプライアンス遵守を確認します。
- 詳細ウィンドウで、DLP ポリシーに一致する機密データを含むファイルの一覧を表示します。

さらに、テスト モードで実行するときに、DLP レポートを使用して DLP ポリシーを微調整することができます。

DLP レポートは、Microsoft 365 コンプライアンス センターにあります。**[レポート]** \> **[組織データ]** セクションに移動して、**DLP ポリシーの一致**、**DLP インシデント**、および **DLP の誤検知と上書き** のレポートを検索します。

詳細については、「[データ損失防止のレポートの表示](../../compliance/view-the-dlp-reports.md)」を参照してください。

![DLP ポリシーと一致することを示すレポート。](../../media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="audit-log-and-alert-policies"></a>監査ログおよびアラートのポリシー

監査ログには、Exchange Online、SharePoint Online、OneDrive for Business、Azure Active Directory、Microsoft Teams、Power BI、Sway などの サービスからのイベントが含まれます。

Microsoft 365 Defender ポータルと Microsoft 365 コンプライアンス センターでは、監査ログを監視およびレポートする 2 つの方法を提供しています。

- アラート ポリシーの設定、アラートの表示、トレンドの監視には、Microsoft 365 Defender ポータルまたは Microsoft 365 コンプライアンス センターのいずれかにあるアラート ポリシーやアラート ダッシュボード ツールを使用します。
- 監査ログを直接検索するには、指定した日付の範囲ですべてのイベントを検索します。また、操作を実行したユーザー、操作、または対象オブジェクトなど、特定の条件に基づいて結果をフィルター処理することもできます。

情報コンプライアンスおよびセキュリティ チームは、これらのツールを使用して、エンド ユーザーと管理者の両方がサービスで実行したアクティビティを予防的に確認することができます。特定のアクティビティが特定のサイト コレクションで発生した場合に (たとえば、GDPR 関連情報が含まれていることがわかっているサイトからコンテンツを共有する場合など)、メール通知を送信するように自動アラートを設定できます。これによってチームは、ユーザーをフォローアップして、企業のセキュリティ ポリシーの遵守の徹底、追加のトレーニング提供などを行うことができます。

情報セキュリティ チームは、監査ログを検索して疑いのあるデータ侵害を調査し、根本原因と違反の程度の両方を判断することもできます。この組み込みの機能は、GDPR の第 33 条および第 34 条の遵守を円滑にします。これらの条項では、データ違反について GDPR 監督当局およびデータ主体に、特定の期間内に通知することが求められています。監査ログ エントリは、サービス内で 90 日間のみ保持されます。多くの場合、これらのログをより長期間保持することが推奨され、多くの企業もそれを必要としています。

Microsoft 管理アクティビティ API を使用して統一監査ログを購読し、必要に応じてログ エントリを保存し、高度なダッシュボードとアラートを提供することができるソリューションを活用できます。たとえば、[Microsoft Operations Management Suite (OMS)](/azure/operations-management-suite/oms-solution-office-365) が例として挙げられます。

アラート ポリシーと監査ログの検索については、以下を参照してください。

- [Microsoft 365 のアラート ポリシー](../../compliance/alert-policies.md)
- [Office 365 で監査ログを検索してユーザーと管理者のアクティビティを確認する](../../compliance/search-the-audit-log-in-security-and-compliance.md) (概要)
- [監査ログ検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)
- [監査ログを検索する](../../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) (コマンドレット)
- [監査ログの詳細なプロパティ](../../compliance/detailed-properties-in-the-office-365-audit-log.md)

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

Microsoft Cloud App Security は、ネットワーク上で使用されている他の SaaS アプリや、これらのアプリとの間でやり取りされる機密データの検出に役立ちます。

Microsoft Cloud App Security は、クラウド アプリのための詳細な可視化、きめ細やかな制御、高度な脅威の防止を提供する包括的なサービスです。ネットワーク上のすべてのデバイスから 15,000 以上のクラウド アプリケーションを識別し、リスク スコアリングや継続的なリスク評価と分析を提供します。ファイアウォールやプロキシから情報を収集して、クラウドの使用状況やシャドウ IT に関する完全な可視性とコンテキストを提供するため、エージェントは必要ありません。

クラウド環境をよりよく理解するために、Cloud App Security の調査機能は、承認および管理されているアプリのすべてのアクティビティ、ファイル、アカウントの詳細内容を可視化します。ファイル レベルの詳細な情報を取得し、クラウド アプリでのデータの移動を把握できます。

たとえば、次の図は GDPR に役立つ 2 つのクラウド アプリケーション セキュリティ ポリシーを示しています。

![クラウド アプリケーション セキュリティ ポリシーの例。](../../media/Monitor-for-leaks-of-personal-data-image3.png)

1 番目のポリシーは、選択した事前定義の PII 属性またはカスタム式を持つファイルが、選択した SaaS アプリから組織外で共有されると警告します。

2 番目のポリシーは、管理対象外のデバイスへのファイル ダウンロードをブロックします。検索するファイル内の属性と、ポリシーを適用する SaaS アプリを選択します。

これらの属性タイプは、Cloud App Security に近日公開されます。

- 機密情報の種類
- Microsoft 365 および Azure Information Protection での統一ラベル

### <a name="cloud-app-security-dashboard"></a>Cloud App Security ダッシュボード

まだ Cloud App Security の使用を開始していない場合は、まず開始してください。Cloud App Security には <https://portal.cloudappsecurity.com> からアクセスできます。

> [!NOTE]
> Cloud App Security の使用を開始するときやラベルを割り当てる前に、[一般設定] の [Azure Information Protection 分類ラベルについてファイルを自動的にスキャンする] を有効にしてください。設定後は、Cloud App Security は、変更されるまで既存ファイルを再スキャンしません。

![アラートに関する情報を表示するダッシュボード。](../../media/Monitor-for-leaks-of-personal-data-image4.png)

詳しくは、以下の資料を参照してください。

- [Cloud App Security を展開する](/cloud-app-security/getting-started-with-cloud-app-security)
- [Microsoft Cloud App Security の詳細情報](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [Microsoft Cloud App Security プロキシを使用して機密情報のダウンロードをブロックする](/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a>個人データの共有を検出するためのファイル ポリシーとアクティビティ ポリシーの例

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a>PII (クレジット カード番号) を含むファイルの共有を検出する

承認されたクラウド アプリから、クレジット カード番号を含むファイルが共有されたときに警告します。

<br>

****

|コントロール|設定|
|---|---|
|ポリシーの種類|ファイル ポリシー|
|ポリシー テンプレート|テンプレートなし|
|ポリシーの重要度|高|
|カテゴリ|DLP|
|フィルター設定|Access level = Public (Internet), Public, External <p> App = \<select apps\> (特定の SaaS アプリに監視を制限する場合は、この設定を使用します)|
|適用先|すべてのファイル、すべての所有者|
|内容の検査|現在の式に一致するファイルを含む: All countries: Finance: Credit card number <p> 関連するコンテキストを必要としない: オフ (この設定は、キーワードと正規表現に一致します) <p> 1 つでも一致するファイルを含む <p> 違反の最後の 4 文字をマスク解除する: オン|
|アラート|一致するファイルごとにアラートを作成する: オン <p> 1 日のアラート制限: 1000 <p> 電子メールとしてアラートを選択する: オン <p> 宛先: infosec@contoso.com|
|ガバナンス|Microsoft OneDrive for Business <p> 非公開にする: 外部ユーザーの削除をオン <p> その他のすべての設定: オフ <p> Microsoft SharePoint Online <p> 非公開にする: 外部ユーザーの削除をオン <p> その他のすべての設定: オフ|
|

類似のポリシー:

- PII (メール アドレス) を含むファイルの共有を検出する
- PII (パスポート番号) を含むファイルの共有を検出する

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a>Box for Business または OneDrive for Business の顧客データや人事データを検出する

OneDrive for Business または Box for Business に Customer Data (顧客データ) または HR Data (人事データ) という名前のファイルがアップロードされたときに警告します。

注:

- Box の監視では、API Connector SDK を使用してコネクタを設定する必要があります。
- このポリシーには、現在プライベート プレビューになっている機能が必要です。

<br>

****

|コントロール|設定|
|---|---|
|ポリシーの種類|アクティビティ ポリシー|
|ポリシー テンプレート|テンプレートなし|
|ポリシーの重要度|高|
|カテゴリ|制御を共有|
|操作対象|1 つのアクティビティ|
|フィルター設定|アクティビティの種類 = ファイルのアップロード <p> アプリ = Microsoft OneDrive for Business および Box <p> 分類ラベル (現在はプライベート プレビュー): Azure Information Protection = 顧客データ、人事—給与データ、人事—従業員データ|
|アラート|アラートを作成する: オン <p> 1 日のアラート制限: 1000 <p> 電子メールとしてアラートを選択する: オン <p> 宛先: infosec@contoso.com|
|ガバナンス|すべてのアプリ <p> ユーザーを検疫に入れる: オン <p> その他のすべての設定: オフ <p> Office 365 <p> ユーザーを検疫に入れる: オン <p> その他のすべての設定: オフ|
|

類似のポリシー:

- 顧客データや人事データの大量ダウンロードを検出する—顧客データや人事データを含む多数のファイルが、単一ユーザーによって短時間にダウンロードされたことが検出されたときに警告します。
- 顧客および人事データの共有を検出する—顧客または人事データを含むファイルが共有されたときに警告します。
