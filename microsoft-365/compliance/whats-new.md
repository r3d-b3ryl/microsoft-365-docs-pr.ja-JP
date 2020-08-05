---
title: コンプライアンス センターの新機能
f1.keywords:
- NOCSH
ms.author: brendonb
author: brendonb
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Microsoft 365 コンプライアンスセンターに継続的に新機能を追加しています。 今月の内容を確認してください。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77ba6f0926a1826fe6c946ff4f8c05cf913c57ed
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560264"
---
# <a name="whats-new-in-the-microsoft-365-compliance-center"></a>Microsoft 365 コンプライアンスセンターの新機能

[Microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md)に新機能を継続的に追加し、学習した問題を修正し、フィードバックに基づいて変更を加えています。 お客様が現在利用できるものを確認するには、次のようにしてください。 一部の機能は、お客様のさまざまなスピードでロールアウトされます。 機能がまだ表示されていない場合は、[対象のリリース](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)に追加してみてください。

> [!TIP]
> 他の管理センターでは何が起こっているのでしょうか。 次の記事をご覧ください。<br>[Microsoft 365 管理センターの新機能](https://docs.microsoft.com/office365/admin/whats-new-in-preview?view=o365-worldwide)<br>[SharePoint 管理センターの新機能](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br><br>
また、 [microsoft 365 ロードマップ](https://www.microsoft.com/en-us/microsoft-365/roadmap)を参照して、起動された、展開中の、開発中である、キャンセルされた、または既にリリースされた microsoft 365 の機能について説明します。

## <a name="june-2020"></a>2020 年 6 月

### <a name="spotlight-new-data-connectors-hit-preview"></a>スポットライト: 新しいデータコネクタのヒットプレビュー

その他のサードパーティのソースから Microsoft 365 にデータをインポートするための約束を基にして、次の2つのデータコネクタのプレビューリリースを発表することを嬉しくしています。

- [Bloomberg メッセージ](archive-bloomberg-message-data.md)。 Bloomberg メッセージコラボレーションツールから金融サービスの電子メールデータをインポートおよびアーカイブします。 メールボックスに格納されたデータは、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、通信コンプライアンス、および保持ポリシーなどのコンプライアンス機能においてデータにアクセスして使用することができます。
- [氷チャット](archive-icechat-data.md)。 ICE チャットコラボレーションツールから金融サービスチャットデータをインポートおよびアーカイブします。 メールボックスに格納されたデータは、訴訟ホールド、電子情報開示、アーカイブ、監査、通信コンプライアンス、およびアイテム保持ポリシーなどのコンプライアンス機能のデータにアクセスして使用することができます。

### <a name="compliance-score--compliance-manager-the-hits-keep-coming"></a>コンプライアンススコア & コンプライアンスマネージャー: ヒットしたままにする

6月の更新プログラムには、[コンプライアンススコア](compliance-score.md)における新しい評価のドリルダウンビューが含まれています。 進捗管理の監視、コンプライアンススコアから直接評価を追加、削除します。

コンプライアンススコアとコンプライアンスマネージャーの更新プログラムを常に最新の状態に保つ必要がありますか。 [コンプライアンススコアのリリースノート](compliance-score-release-notes.md)にブックマークを入れ、頻繁に確認します。

## <a name="may-2020"></a>2020 年 5 月

### <a name="spotlight-data-classification-is-officially-released"></a>スポットライト: データ分類は正式にリリースされています

データ分類、別名「[データを認識する](data-classification-overview.md)」、機能 (分析、コンテンツエクスプローラー、およびアクティビティエクスプローラー) はプレビューフェーズからの段階的なものであり、すべての組織が使用できます。 強力な洞察とツールを使用すると、組織全体のコンテンツに機密情報とラベル (保持と機密情報) がどのように使用されているかを検出し、評価するのに役立ちます。 機密情報が含まれている、またはラベルが適用されているコンテンツを確認し、Microsoft 365 の場所にまたがるラベルアクティビティを調査し、カスタムの機密情報の種類を作成するなどを行います。

ビデオツアーを実行する...

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

### <a name="trainable-classifiers-a-fix-and-a-feature"></a>Trainable 分類子: 修正と機能

Trainable 分類子の拡張機能が向上する可能性があります。

- フィードバックに基づく修正: カスタム分類子をシード処理してトレーニングする場合は、SharePoint サイトの Url とフォルダーのパスを手動で入力する必要がなくなります。 サイトとフォルダーの事前設定リストから選択できるようになりました。
- 新機能: 機密ラベルを作成し、Office アプリの自動ラベル設定を構成するときに、trainable 分類子に一致するコンテンツに対してラベルを自動的に適用 (または推奨) することができます。 [詳細情報](apply-sensitivity-label-automatically.md#configuring-trainable-classifiers-for-a-label)

### <a name="communication-compliance-yammer-support-is-here"></a>通信のコンプライアンス: Yammer のサポートはこちらから

Yammer のプライベートメッセージとパブリックコミュニティの会話は、通信コンプライアンスポリシーでサポートされています。 Yammer はオプションのチャネルであり、メッセージと添付ファイルのスキャンをサポートするためには、[ネイティブ モード](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)に設定されている必要があります。

### <a name="data-loss-prevention-new-sharing-restriction"></a>データ損失防止: 新しい共有の制限

SharePoint または OneDrive のコンテンツを保護するように DLP ポリシーを設定する場合は、[コンテンツへのアクセスを制限する] アクションを構成して、[[リンクを持つすべて](https://support.microsoft.com/office/share-files-outside-your-organization-with-anyone-links-53e91027-fb8e-4a6e-a3e4-5df4be32e38a)のユーザー] オプションを使用してコンテンツへのアクセスを許可されたユーザーをブロックすることができるようになりました。

### <a name="insider-risk-management-tailor-your-alert-volume"></a>Insider リスク管理: 通知ボリュームを調整する

Insider リスクポリシーによって検出されたユーザーアクティビティには特定のリスクスコアが割り当てられ、それによってアラートの重要度 (低、中、高) が決定されます。 既定では、Microsoft 365 は、特定の量の低、中、高重要度の警告を生成しますが、新しい[通知ボリューム設定](insider-risk-management-settings.md#alert-volume)を使用すると、必要に応じて音量を増減することができます。

### <a name="pst-import-new-region-supported"></a>PST インポート: サポートされている新しい地域

ネットワークアップロードは、アラブ首長国連邦で利用可能になりました。

### <a name="sensitivity-labels-new-privacy-option"></a>機密ラベル: 新しいプライバシーオプション

ラベルの[サイトとグループの設定](sensitivity-labels-teams-groups-sites.md#how-to-configure-site-and-group-settings)を構成するときに、プライバシーオプションを [なし] に設定し、**ユーザーがサイトにアクセスできるユーザーを選択**できるようにすることができます。 これは、機密ラベルを使用してコンテナー内のコンテンツを保護するが、ユーザーが自分でプライバシー設定を構成できるようにする場合に便利です。

## <a name="april-2020"></a>2020 年 4 月

### <a name="records-management-overhauland-a-new-addition"></a>レコード管理: 見直し...新しい追加

April には、レコード管理ソリューションへのいくつかの重要な更新が含まれています。

- 「Records management」セクションは、コンプライアンスセンターで完全に使用できるようになりました。 更新されたユーザーインターフェイスと機能を利用して、ファイル計画、保持ラベル、ラベルポリシー、イベント、および処分を行います。
- 廃棄に関しては、SharePoint および OneDrive のレコードの[廃棄の証明](disposition.md#disposition-of-records)も展開しました。 これで、自動または廃棄レビューの後に、それらの場所にあるアイテムのリストが表示されるようになりました。

:::image type="content" source="../media/mcc-records-management-page.png" alt-text="Microsoft 365 コンプライアンスセンターのレコード管理セクション":::

### <a name="sensitivity-labels-preview-auto-labeling-policies"></a>機密ラベル: 自動ラベル付けポリシーのプレビュー

自動ラベル付けポリシーを使用すると、既に保存されている SharePoint および OneDrive ドキュメントに機密ラベルを自動的に適用することができます。また、既に保存されている電子メール (「送信中」という別名) と電子メールを送信または受信します。 このラベル付けは、アプリではなくサービスによって適用されるため、アプリユーザーの用途とバージョンについて心配する必要はありません。

この機能は、機密ラベルを作成するときに、[Office アプリの自動ラベル付け] 設定に既に含まれている既存のクライアント側のラベルを拡張します。 自動ラベル付けのオプションの違いと利点については、 [「更新さ](apply-sensitivity-label-automatically.md)れた記事」を参照してください。

## <a name="march-2020"></a>2020 年 3 月

### <a name="introducing-advanced-audit"></a>高度な監査の概要

[Microsoft 365 の高度な監査](advanced-audit.md)には、組織にフォレンジックおよびコンプライアンスの調査を支援する新しい監査機能が導入されています。 重要な点としては、監査ログの長期保存、カスタム監査ログの保持ポリシー、新しい*Mailitemsaccessed*されたメールボックス監査アクション、および新しいテナントレベルの調整制限の導入によって、組織は監査データにアクセスするための完全に割り当てられた帯域幅クォータを使用できます。

### <a name="compliance-score--compliance-manager-preview-the-latest-enhancements"></a>コンプライアンススコア & コンプライアンスマネージャー: 最新の機能強化のプレビュー

このプレビューリリースの主要な更新プログラムは次のとおりです。

- テンプレートを作成および変更するための簡略化されたプロセス
- テンプレートとアクションのバージョン管理通知とコントロール
- グループ間で共通のアクションを同期する
- 言語サポートは、簡体字中国語 (簡体字)、中国語 (繁体字)、フランス語、ドイツ語、イタリア語、日本語、韓国語、ポルトガル語 (ブラジル)、ロシア語、スペイン語に拡張されました。

[コンプライアンススコア](compliance-score.md)と[コンプライアンスマネージャー](compliance-manager-overview.md)の詳細情報

### <a name="sensitivity-labels-support-for-labeling-office-files-in-sharepoint-and-onedrive-preview"></a>機密ラベル: SharePoint および OneDrive での Office ファイルへのラベル付けのサポート (プレビュー)

プレビューを有効にすると、ユーザーは web 上の Office に機密ラベルを適用することができます。 これにより、リボン上の [**秘密度**] ボタンと、適用されたラベル名がステータスバーに表示されるようになります。 また、デスクトップアプリを使用して、SharePoint または OneDrive にファイルをラベル付けして保存すると、Microsoft 365 は、そのラベルに暗号化設定が適用されている場合にこれらのファイルのコンテンツを処理できるようになります。 このような状況では、共同編集、電子情報開示、データ損失防止、検索、およびその他のコラボレーション機能もサポートされます。

[プレビューを有効にする方法について説明します。](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="february-2020"></a>2020 年 2 月

### <a name="insider-risk-management-is-officially-released"></a>Insider リスク管理が正式にリリースされている

ドラムロール (ご記入ください)<br>Insider リスク管理は、次のサブスクリプションを使用する組織で使用できるようになりました。

- [Microsoft 365 E5](https://go.microsoft.com/fwlink/?linkid=2120431) (有料または試用版)
- Microsoft 365 Enterprise E3 サブスクリプションと[Microsoft E5 コンプライアンスアドオン](https://go.microsoft.com/fwlink/?linkid=2120432)

プレビューリリース後に、[新しい役割グループ](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)と[ソリューションレベルの設定](insider-risk-management-configure.md#step-4-configure-insider-risk-settings)を含むいくつかの改善を行いました。

そのため、ソリューションを使用するときにはフィードバックを残して、改善を続けられるようにしてください。

### <a name="records-management"></a>レコード管理

この新しいソリューションにより、すべてのレコード管理機能が1つの包括的な下に表示されます。 重要な点としては、SharePoint と OneDrive のレコードバージョン管理の導入やレコードの廃棄証明が挙げられます。

![Microsoft 365 コンプライアンスセンターのレコード管理ページ](../media/mcc-records-management-page.png)

[レコード管理についての詳細情報](records-management.md)

### <a name="solution-spotlight-data-connectors-for-facebook-and-twitter"></a>ソリューションスポットライト: Facebook および Twitter のデータコネクタ

先月[リリース](#just-launched)されたデータコネクタは、次のコネクタをテストするためのヘルプを探しています。

- [Facebook ビジネスページ](archive-facebook-data-with-sample-connector.md) Facebook のビジネスページのデータをインポートし、Microsoft 365 にアーカイブします。 レコード管理や電子情報開示などのコンプライアンスソリューションに役立ちます。
- [Twitter](archive-twitter-data-with-sample-connector.md)。 Twitter から Microsoft 365 にデータをインポートしてアーカイブします。 レコード管理や電子情報開示などのコンプライアンスソリューションに役立ちます。

これらのコネクタを設定して検証するときには、何がうまくいったのか、何ができなかったのか、また、操作を改善するためにできることについてのフィードバックをお寄せください。

## <a name="january-2020"></a>2020 年 1 月

待機が終了しています。 Microsoft 365 コンプライアンスセンターは、Microsoft 365、Office 365、Enterprise Mobility + Security (EMS)、および Windows 10 Enterprise プランを使用しているすべてのお客様が利用できることを嬉しくお勧めいたします。 セキュリティ & コンプライアンスセンターで管理していたすべてのデータやポリシーは、コンプライアンスセンターで利用できます。そのため、前後に移動する必要はありません。

> [!TIP]
> 最近プレビューした[新しいソリューション](#new-compliance-solutions)の一部、およびセキュリティ & コンプライアンスセンターからのコンプライアンス機能が Microsoft 365 で有効になっていることを示す[ロードマップ](#updated-compliance-solutions)については、先月の「更新」を参照してください。

[https://compliance.microsoft.com](https://compliance.microsoft.com)組織全体にわたるコンプライアンスを管理するためのワンストップショップのツアーを開始するには、今すぐにブックマークを作成してください。詳細については、[この記事を参照](microsoft-365-compliance-center.md)してください。

![Microsoft 365 コンプライアンスセンターのホームページ](../media/mcc-home-ga.png)

また、今月の新規および更新されたソリューションもリリースしました。 強調表示の概要は次のとおりです。

### <a name="now-in-preview"></a>現在はプレビュー

**Insider リスク管理 (プレビュー)**

これで、insider のリスク管理ソリューションが公開プレビューであることがわかります。 簡単に言うと、insider リスク管理は、次のような情報を提供することで、組織がインテリジェントに内部のリスクを特定し、アクションを実行できるようにします。

- ユーザーのプライバシーを確保するための匿名性制御。
- 内部の脅威 (データリークなど) を識別するネイティブおよびサードパーティの指標を使用したインテリジェントポリシーテンプレート。
- IT、人事、および法務チーム全体にわたる、統合されたエンドツーエンドの調査ワークフロー。

ご感想をお聞かせください。 ソリューションを使用している間に、フィードバックをお寄せください。これにより、一般的な可用性に至るまでのニーズを満たすことができるようになります。

[Insider リスク管理の詳細情報](insider-risk-management.md)

### <a name="just-launched"></a>開始したばかり

**通信コンプライアンス**

Graduating は、プレビュー段階から完全な可用性まで、コミュニケーションコンプライアンスは新しい insider リスクソリューションセットの主要なコンポーネントです。 この堅牢なソリューションにより、組織の標準に準拠していないメッセージの検出、調査、修復処理を行うためのワークフローを使用して、コミュニケーションリスクを最小限に抑えることができます。

プレビュー中のお客様からのフィードバックはすばらしいものでした。 開始、調査、修復処理の改善など、いくつかの機能強化が行われています。

[通信のコンプライアンスに関する詳細情報](communication-compliance.md)

![Microsoft 365 コンプライアンスセンターの [通信コンプライアンス] ページで、最初のカードの案内画面が表示されている](../media/mcc-communication-compliance-page-with-fre.png)

**データコネクタ**

以前は、Office 365 セキュリティ & コンプライアンスセンターの他の「インポート」機能とのスペースを共有しています。データコネクタは、Microsoft 365 コンプライアンスセンターで独自のホームになっています。 新しい [データコネクタ] ページを使用して、組織の人事 (HR) ファイルと、さまざまなサードパーティ製プラットフォーム (Facebook、LinkedIn、Twitter、インスタント Bloomberg など) のデータを Microsoft 365 組織のメールボックスにインポートおよびアーカイブします。 インポートされると、このデータは、電子情報開示、insider リスク管理、コミュニケーションコンプライアンス、監査、アイテム保持ポリシーなどを含む、いくつかのコンプライアンスソリューションで管理できます。

[データコネクタの詳細情報](archiving-third-party-data.md)

![Microsoft 365 コンプライアンスセンターのデータコネクタページ](../media/mcc-data-connectors-page.png)

### <a name="noteworthy-updates"></a>注目すべき更新プログラム

**コンプライアンススコアの新しい評価テンプレート (プレビュー)**

常に努力していくことにより、絶えず進化するコンプライアンスに役立てられるようになり、コンプライアンススコアチームは新しい一連のテンプレートを提供し、最近の規制に対する組織のコンプライアンスを評価し、より効果的な制御を実装する方法に関するガイダンスを得ることができます。 次の新しいテンプレートが表示られるようになります。

- ISO/IEC 27701:2019
- カリフォルニア州消費者プライバシー法 (CCPA)
- ブラジルの一般データ保護法 (Lei Geral de Proteção de Dados-LGPD)
- SOC 1 タイプ2および SOC 2 タイプ2

[コンプライアンススコアテンプレートの詳細情報](compliance-score.md#templates)

## <a name="november--december-2019"></a>2019年12月 &

休日に加えて、Ignite でデモされていたすべての高度なコンプライアンスソリューションのロールアウトを開始しました。 ほとんどはプレビュー状態であるため、それをテストして、コンプライアンスセンターの右下でフィードバックカードを開いて、ご意見をお聞かせください。

![feedback](../media/Feedback_card_MCC.JPG)

### <a name="get-to-know-the-new-neighborhood"></a>新しい近隣を理解する

新しい Microsoft 365 コンプライアンスセンターには、新しいソリューションに加えて、Office 365 セキュリティ & コンプライアンスセンターで熟知しているコンプライアンス機能が含まれています。 詳細については、さらに詳しく説明します。

#### <a name="new-compliance-solutions"></a>新しいコンプライアンスソリューション

*ソリューション*について疑問があるかもしれません。 クラウドがビジネスを遂行する方法によって革命になるにつれて、データの盗用や不正行為の新たな方法や、必要とされる新しい規制についても、このドアを開くことができます。 コンプライアンスソリューションは、これらの進化したコンプライアンス要件を管理するのに役立つ統合された機能の集合です。 ソリューションの機能には、ポリシー、警告、レポートなどの組み合わせが含まれることがあります。

ここでは、次のような新しいソリューションについて概要を説明します。 近日中に他のユーザーが閲覧できるようにしておきます。

> [!NOTE]
> これらのソリューションは、Microsoft 365 コンプライアンスセンターのみにあります。 Office 365 セキュリティ & コンプライアンスセンターで管理することはできません。
<br/>

|**新しいソリューション**|**説明**|**詳細情報**|
|:-----|:-----|:-----|
|Microsoft コンプライアンススコア (プレビュー) <br/>|コンプライアンス[マネージャー](compliance-manager-overview.md)を基にしたコンプライアンススコアは、よりシンプルでわかりやすい設計を備えたスタンドアロンの機能です。これにより、組織の法令遵守状況を理解し、改善することができます。 データ保護および規制標準に関するリスクを軽減するために、進行状況を測定するリスクベースのスコアを計算します。 <br/>|[Microsoft コンプライアンススコアの概要 (プレビュー)](compliance-score.md)|
|ソリューションカタログ (プレビュー) <br/>|ソリューションカタログは、コンプライアンスおよびリスク管理ソリューションの発見、学習、迅速な開始を行うためのワンストップショップです。 カタログは3つのコンプライアンスカテゴリに編成されており、それぞれにカテゴリを構成するソリューションに関する詳細が含まれています。 カテゴリには、情報保護 & ガバナンス、Insider リスク管理、検出 & 応答が含まれます。 <br/>|[ソリューションカタログの概要 (プレビュー)](microsoft-365-solution-catalog.md)|
|通信のコンプライアンス (プレビュー) <br/>|コミュニケーションへのコンプライアンスは、組織内の不適切なメッセージに対する修復アクションを検出、取得、および実行できるようにすることで、コミュニケーションリスクを最小限にするために役立つ、新しい insider リスク管理カテゴリに含まれています。 このソリューションでは、インテリジェントテンプレート、柔軟な修復ワークフロー、実践的な洞察など、いくつかの新しい拡張機能を導入することで、Office 365 の監督ポリシーの機能が拡張されています。 <br/>|[Microsoft 365 の通信コンプライアンス (プレビュー)](communication-compliance.md)|
|データ分類 (プレビュー) <br/>|新しいデータ分類ページには、組織全体のコンテンツに機密情報とラベル (保持と機密情報) がどのように使用されているかを検出して評価するのに役立つ、強力な洞察とツールが含まれています。 機密情報が含まれている、またはラベルが適用されているコンテンツを確認し、Microsoft 365 の場所にまたがるラベルアクティビティを調査し、カスタムの機密情報の種類を作成するなど、さまざまな内容を確認します。<br/>|[データ分類の概要 (プレビュー)](data-classification-overview.md)|
|Trainable 分類子 (プレビュー) <br/>|この強力な新しいツールは、機械学習エンジンを使用して、規制文書や従業員契約書など、組織内のコンテンツのカテゴリを特定するのに役立ちます。 作成した分類子は、いくつかのコンプライアンスソリューションで使用して、関連するコンテンツを検出し、それを分類し、保護し、その他の情報を保持することができます。<br/>|[トレーニング可能な分類子の使用を開始する (プレビュー)](classifier-getting-started-with.md)|

#### <a name="updated-compliance-solutions"></a>コンプライアンスソリューションの更新

コンプライアンスのニーズに応じて Office 365 セキュリティ & コンプライアンスセンターを使用している場合は、一部の機能が新しい Microsoft 365 コンプライアンスセンターで有効になっていることを不思議に思うかもしれません。 新しい自宅を見つけるのに役立つクイックロードマップを次に示します。

> [!NOTE]
> 一部の機能は依然として Office 365 セキュリティ & コンプライアンスセンターでのみ利用できます。 しかし、Microsoft 365 コンプライアンスセンターでは、これらをプレビューするのは困難なので、更新プログラムを常にチューニングするように努力しています。 
<br/>

|**機能**|**Office 365 セキュリティ/コンプライアンス センター**|**Microsoft 365 コンプライアンス センター**|**詳細情報**|
|:-----|:-----|:-----|:-----|
|高度な電子情報開示|電子情報開示 > の高度な電子情報開示 <br/> https://protection.office.com/advancedediscoverycases |電子情報開示 > の詳細 <br/> https://compliance.microsoft.com/advancedediscovery | [Microsoft 365 の高度な電子情報開示ソリューションの概要](overview-ediscovery-20.md) |
|ポリシーを通知する|通知 > 警告ポリシー <br/> https://protection.office.com/alertpolicies |現時点では、アラートポリシーは Office 365 セキュリティ & コンプライアンスセンターでのみ管理されます。 |[セキュリティ/コンプライアンス センターのアラート ポリシー](alert-policies.md) |
|アラート|通知 > 表示する通知 <br/> https://protection.office.com/viewalerts |アラート <br/> https://compliance.microsoft.com/compliancealerts |[通知の表示](alert-policies.md#viewing-alerts)|
|アーカイブ|情報ガバナンス > アーカイブ <br/> https://protection.office.com/archiving |情報ガバナンス > [アーカイブ] タブ <br/> https://compliance.microsoft.com/informationgovernance?viewid=archive |[アーカイブ メールボックスの有効化](enable-archive-mailboxes.md)|
|監査ログ検索|検索 > 監査ログの検索 <br/> https://protection.office.com/unifiedauditlog |監査 <br/> https://compliance.microsoft.com/auditlogsearch | [セキュリティ/コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)|
|コンテンツ検索|検索 > コンテンツ検索 <br/> https://protection.office.com/contentsearchbeta?ContentOnly=1 | コンテンツ検索 <br/> https://compliance.microsoft.com/contentsearch |[Office 365 のコンテンツを検索する](search-for-content.md) |
|データコネクタ|情報ガバナンス > サードパーティのデータをアーカイブする <br/> https://protection.office.com/nativeconnector | データコネクタ <br/> https://compliance.microsoft.com/connectorlanding |[サード パーティのデータをアーカイブする](archiving-third-party-data.md)|
|データ損失防止|データ損失防止 <br/> https://protection.office.com/datalossprevention |データ損失防止 <br/> https://compliance.microsoft.com/datalossprevention |[データ損失防止の概要](data-loss-prevention-policies.md)|
|データ主体要求 |データのプライバシー > データ主体要求 <br/> https://protection.office.com/dsrcases |データ主体要求 <br/> https://compliance.microsoft.com/datasubjectrequest |[DSR ケースツールを使用して GDPR データ主体要求を管理する](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md)|
|電子情報開示|電子情報開示 > 電子情報開示 <br/> https://protection.office.com/ediscoveryv1 |電子情報開示 > コア <br/> https://compliance.microsoft.com/classicediscovery |[eDiscovery ケースを管理する](ediscovery-cases.md) |
|Events|レコード管理 > イベント <br/> https://protection.office.com/events |レコード管理 > [イベント] タブ <br/> https://compliance.microsoft.com/recordsmanagement?viewid=events |[イベントの発生時に保持を開始する](event-driven-retention.md)|
|ファイル計画|レコード管理 > ファイル計画 <br/> https://protection.office.com/fileplan |レコード管理 > ファイル計画] タブ <br/> https://compliance.microsoft.com/recordsmanagement?viewid=fileplan |[ファイルプランを使用して保持ラベルを管理する](file-plan-manager.md)|
|PST ファイルのインポート|情報ガバナンス > PST ファイルのインポート <br/> https://protection.office.com/importV2 |情報ガバナンス > インポート] タブ <br/> https://compliance.microsoft.com/informationgovernance?viewid=import |[組織の PST ファイルのインポートの概要](importing-pst-files-to-office-365.md)|
|ラベルアクティビティエクスプローラー|情報ガバナンス > ラベルアクティビティエクスプローラー <br/> https://protection.office.com/labelexplorer |データ分類 > アクティビティエクスプローラータブ <br/> https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer |[ラベル付きコンテンツのアクティビティを表示する (プレビュー)](data-classification-activity-explorer.md)|
|保持ラベルとラベルポリシー |[ラベル] タブと [ラベルポリシー] タブ > の > 保持ラベルの分類 <br/> https://protection.office.com/retentionlabels |情報ガバナンス > ラベルとラベルポリシー] タブ <br/> https://compliance.microsoft.com/informationgovernance?viewid=labels <br/> https://compliance.microsoft.com/informationgovernance?viewid=labelpolicies | 「[保持ラベルの概要](retention.md)」を参照してください。|
|アイテム保持ポリシー|情報ガバナンス > の保持 <br/> https://protection.office.com/retention |情報ガバナンス > [保持] タブ <br/> https://compliance.microsoft.com/informationgovernance?viewid=retention |[アイテム保持ポリシーと保持ラベルの詳細](retention.md)|
|機密情報の種類|機密情報の種類 > 分類 <br/> https://protection.office.com/sensitivetypes |データ分類 > 機密情報の種類] タブ <br/> https://compliance.microsoft.com/dataclassification?viewid=sensitiveinfotypes |[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)|
|機密ラベルとラベルポリシー|[ラベル] タブと [ラベルポリシー] タブ > 機密ラベルの分類 > <br/> https://protection.office.com/sensitivity |情報保護 > ラベルとラベルポリシー] タブ <br/> https://compliance.microsoft.com/informationprotection?viewid=sensitivitylabels <br/> https://compliance.microsoft.com/informationprotection?viewid=sensitivitylabelpolicies |[秘密度ラベルの詳細](sensitivity-labels.md) |
|サービス アシュアランス|サービス アシュアランス <br/> https://protection.office.com/serviceassurance/dashboard |現時点では、サービス保証のリソースには、Office 365 セキュリティ & コンプライアンスセンターのみがアクセスできます。 |[セキュリティ/コンプライアンス センターのサービス アシュアランス](service-assurance.md)|
|監督|監督 <br/> https://protection.office.com/supervisoryreviewv2 |通信コンプライアンス <br/> https://compliance.microsoft.com/supervisoryreview |[Microsoft 365 の通信コンプライアンス (プレビュー)](communication-compliance.md) |

## <a name="september-2019"></a>2019 年 9 月

今月リリースのリリース前に静かになる理由をご確認ください。 マイクロソフトは、11月に[Microsoft Ignite](https://www.microsoft.com/ignite)で最近される新しい革新的なコンプライアンスソリューションの構築に取り組んでいます。 引き続きご調整ください。

### <a name="new-encryption-options-for-sensitivity-labels"></a>機密ラベルの新しい暗号化オプション 

機密ラベルの暗号化を構成する場合、次の2つのオプションがあるので、ユーザーはラベルを電子メールやドキュメントに手動で適用するときにアクセス許可を割り当てることができます。<br>
- **Outlook 電子メール**にラベルを適用する場合、ユーザーは [転送不可] オプションに相当する制限を適用できます。 受信者は、メッセージを読み取ることはできますが、コンテンツを転送、印刷、またはコピーすることはできません。
- **Word、PowerPoint、Excel**の各ファイルにラベルを適用すると、ユーザーは特定のユーザーやグループにアクセス許可を割り当てるように求められます。

詳細については、「[機密ラベルを使用してコンテンツへのアクセスを制限](encryption-sensitivity-labels.md#let-users-assign-permissions)する」を参照し、暗号化を適用してください。

## <a name="august-2019"></a>2019 年 8 月

### <a name="update-to-data-investigations"></a>データ調査への更新

データの調査を実行すると、元の場所からアイテムを削除できるようになります。 これは、組織全体の Exchange メールボックス、SharePoint サイト、および OneDrive アカウントからアイテムを削除できることを意味します。 アイテムを証拠として収集したため、証拠セットに保存されたアイテムのコピーが、さらに参考になるか、参照として保持することができます。 詳細について[は、「Microsoft 365 のデータ流出インシデントの管理」](manage-data-spillage-incidents.md#step-4-delete-the-spilled-data)を参照してください。 

## <a name="july-2019"></a>2019 年 7 月

### <a name="new-admin-roles"></a>新しい管理者の役割

組織のセキュリティとコンプライアンスを管理するために、2つの新しい管理者の役割をリリースしました。すべての友人に連絡します。

- **コンプライアンスデータ管理者**。この役割を持つユーザーは、Microsoft 365 コンプライアンスセンター、Microsoft 365 管理センター、および Azure のデータを保護および追跡するためのアクセス許可を持っています。 また、Exchange 管理センター、コンプライアンスマネージャー、Teams & Skype for Business 管理センターを管理したり、Azure および Microsoft 365 のサポートチケットを作成したりすることもできます。
- **セキュリティオペレーター**。 この役割を持つユーザーは、通知を管理し、Microsoft 365 セキュリティセンター、Azure Active Directory、Id 保護、特権 Id 管理、および Office 365 Security & コンプライアンスセンターのすべてを含む、セキュリティ関連機能へのグローバルな読み取り専用アクセスを持つことができます。

[これらの役割の詳細情報](https://docs.microsoft.com/microsoft-365/security//office-365-security/permissions-microsoft-365-compliance-security)

### <a name="search-and-filtering-for-reports"></a>レポートの検索とフィルター処理

必要なレポートを見つけるために、大量のレポートをスクロールする必要はありません。 これで、(タイトルに基づいて) レポートを検索し、「ラベル」や「コンプライアンス」、「Office 365」や「Microsoft Cloud App Security」などのソースのカテゴリにフィルターを適用することができます。

![適用されたフィルターを使用したレポートの検索とフィルターのボタンの画面キャプチャ](../media/mcc_report_filtering.png)
