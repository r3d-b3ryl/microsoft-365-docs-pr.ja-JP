---
title: Microsoft Defender for Endpoint のデバイスの正常性とコンプライアンス レポート
description: デバイスの正常性とコンプライアンス レポートを使用して、デバイスの正常性、ウイルス対策の状態とバージョン、OS プラットフォーム、Windows 10バージョンを追跡します。
keywords: 正常性状態, ウイルス対策, OS プラットフォーム, Windows 10 バージョン, バージョン, 正常性, コンプライアンス, 状態
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
ms.date: 08/08/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 00a43da0c6b817c6e53ef93ae27fa8e59d7c5341
ms.sourcegitcommit: 6bff75867764335685f972943170c7db46e33a6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2022
ms.locfileid: "67300457"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint のデバイスの正常性とコンプライアンス レポート

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。
> _商用リリース_ される機能に関する情報は、「[パブリックリリース:Microsoft Defender for Endpointのデバイスの正常性とコンプライアンスレポート](#publicly-released-device-health-and-compliance-report-in-microsoft-defender-for-endpoint)」セクションのプレリリース情報に従います。

## <a name="public-preview---device-health-and-antivirus-compliance-report-in-microsoft-defender-for-endpoint"></a>パブリック プレビュー - Microsoft Defender for Endpointのデバイスの正常性とウイルス対策のコンプライアンス レポート

デバイスの状態レポートには、組織内のデバイスに関する高度な情報が表示されます。 このレポートには、センサーの正常性状態、ウイルス対策状態、OS プラットフォーム、およびWindows 10バージョンを示す傾向のある情報が含まれています。

> [!IMPORTANT]
> Windows&nbsp;Server&nbsp;2012&nbsp;R2 と Windows&nbsp;Server 2016 を&nbsp;デバイス正常性レポートに表示するには、これらのデバイスを最新の統合ソリューション パッケージを使用してオンボードする必要があります。 詳細については、「[Windows Server 2012 R2 と 2016 の最新の統合ソリューションの新機能」を参照してください](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)。

Microsoft 365 セキュリティ ダッシュボードのナビゲーション パネルで [ **レポート**] を選択し、 **デバイスの正常性とコンプライアンスを開きます**。
デバイスの正常性とコンプライアンスのダッシュボードは、次の 2 つのタブで構成されています。

- [ [**センサーの正常性& OS** ] タブ](#sensor-health--os-tab) には、一般的なオペレーティング システム情報が表示され、次のデバイス属性を表示する 3 つのカードに分割されます。
  - [センサーの正常性カード](#sensor-health-card)
  - [オペレーティング システムとプラットフォーム カード](#operating-systems-and-platforms-card)
  - [Windows 10 バージョン カード](#windows-10-versions-card)

- [**Microsoft Defender ウイルス対策の正常性** タブ](#microsoft-defender-antivirus-health-tab)には、Microsoft Defender ウイルス対策の側面を報告する 8 つのカードがあります。
  - [ウイルス対策モード カード](#antivirus-mode-card)
  - [ウイルス対策エンジンのバージョン カード](#antivirus-engine-version-card)
  - [ウイルス対策セキュリティ インテリジェンス バージョン カード](#antivirus-security-intelligence-version-card)
  - [ウイルス対策プラットフォームのバージョン カード](#antivirus-platform-version-card)
  - [最近のウイルス対策スキャン結果カード](#recent-antivirus-scan-results-card)
  - [ウイルス対策エンジンの更新カード](#antivirus-engine-updates-card)
  - [セキュリティ インテリジェンス更新プログラム カード](#security-intelligence-updates-card)
  - [ウイルス対策プラットフォームの更新カード](#antivirus-platform-updates-card)

### <a name="sensor-health--os-tab"></a>[センサーの正常性& OS] タブ

センサーの正常性と OS カードは、検出センサーの正常性、最新のオペレーティング システムと古いオペレーティング システム、Windows 10 バージョンを含む一般的なオペレーティング システムの正常性を報告します。

> [!div class="mx-imgBorder"]
> ![センサーの正常性とオペレーティング システムの情報を表示します。 ウイルス対策エンジン、ウイルス対策セキュリティ インテリジェンス、ウイルス対策プラットフォームの詳細を含む Microsoft Defender ウイルス対策の正常性タブ。 ](images/device-health-sensor-health-os-tab.png)

**[センサーの正常性**] タブの 3 つのカードにはそれぞれ、現在の _状態_ と _デバイスの傾向_ という 2 つのレポート セクションがあり、グラフとして表示されます。

#### <a name="current-state-graph"></a>現在の状態グラフ

各カードでは、現在の状態 ( _デバイスの概要_ として一部のドキュメントで参照) が上の横棒グラフです。 現在の状態は、組織内のデバイスに関して収集された情報を現在の日付の範囲で示すスナップショットです。 このグラフは、状態を報告する、または特定の状態であることが検出された組織全体のデバイスの分布を表します。

> [!div class="mx-imgBorder"]
> ![デバイス正常性内の現在の状態グラフを表示します](images/device-health-sensor-health-os-current-state-graph.png)

#### <a name="device-trends-graph"></a>デバイスの傾向グラフ

3 つのカードの下のグラフには名前が付けられていませんが、一般的に _デバイスの傾向_ と呼ばれます。 デバイスの傾向グラフは、グラフのすぐ上に示されている期間を通じて、組織全体のデバイスのコレクションを示します。
既定では、デバイスの傾向グラフには、30 日間のデバイス情報が表示され、最新の 1 日で終了します。 組織内で発生する傾向についてより適切な視点を得るために、表示される期間を調整してレポート期間を微調整できます。 期間を調整するには、フィルターを開き、開始日と終了日を選択します。

> [!div class="mx-imgBorder"]
> ![デバイス正常性バージョンの傾向を表示する](images/device-health-sensor-health-os-device-trends-graph.png)

#### <a name="filtering-data"></a>データのフィルター処理

特定の属性を持つデバイスを含めたり除外したりするには、指定されたフィルターを使用します。 デバイス属性から適用するフィルターを複数選択できます。 適用すると、レポート内の 3 つのカードすべてにフィルターが適用されます。

たとえば、アクティブなセンサーの正常性状態を持つデバイスWindows 10に関するデータを表示するには、次のようにします。

1. [ **フィルター** > **センサーの正常性状態** > **] で [アクティブ] を選択します**。
2. 次に **、OS プラットフォームを** > 選択 **しますWindows 10**。
3. **[適用]** を選択します。

#### <a name="sensor-health-card"></a>センサーの正常性カード

センサーの正常性カードには、デバイス上のセンサーの状態に関する情報が表示されます。 センサーの正常性は、次のデバイスの集計ビューを提供します。

- アクティブ
- 非アクティブ
- 通信障害が発生している
- またはセンサー データが報告されない場所

通信障害が発生しているデバイス、またはセンサー データが検出されないデバイスは、組織をリスクにさらし、調査を保証する可能性があります。 同様に、長期間非アクティブなデバイスでは、古いソフトウェアが原因で組織が脅威にさらされる可能性があります。 長期間非アクティブなデバイスでも、調査が必要です。

#### <a name="operating-systems-and-platforms-card"></a>オペレーティング システムとプラットフォーム カード

このカードには、組織内に存在するオペレーティング システムとプラットフォームの分布が表示されます。
_OS システムとプラットフォームは、_ 組織内のデバイスが現在のオペレーティング システムと古いオペレーティング システムのどちらを実行しているかに関する有用な分析情報を提供できます。 新しいオペレーティング システムが導入されると、セキュリティの脅威に対する組織の体制を改善するセキュリティ強化が頻繁に含まれます。

たとえば、Windows 8で導入されたセキュア ブートは、最も有害な種類のマルウェアの脅威を実質的に排除しました。 Windows 10の機能強化により、PC メーカーは、ユーザーがセキュア ブート機能を無効にできないようにすることができます。 ユーザーがセキュア ブート機能を無効にできないようにすると、悪意のあるルートキットやその他の低レベルのマルウェアがブート プロセスに感染する可能性がほとんどなくなります。
理想的には、"現在の状態" グラフは、オペレーティング システムの数が、古いバージョンよりも多くの現在の OS を優先して重み付けされていることを示しています。  それ以外の場合、傾向グラフは、新しいシステムが採用されているか、以前のシステムが更新または置き換えられていることを示します。

#### <a name="windows-10-versions-card"></a>Windows 10 バージョン カード

カードには、組織内の Windows デバイスとそのバージョンの配布が表示されます。
Windows 8からWindows 10へのアップグレードによって組織内のセキュリティが向上するのと同じように、Windows の初期リリースから最新バージョンに変更することで、考えられる脅威に対する姿勢が向上します。

Windows バージョンの傾向グラフは、最新のセキュリティで保護されたバージョンのWindows 10に更新することで、組織が最新の状態を維持しているかどうかを迅速に判断するのに役立ちます。

### <a name="microsoft-defender-antivirus-health-tab"></a>Microsoft Defender ウイルス対策の正常性タブ  

Microsoft Defender ウイルス対策の正常性タブには、組織内の Microsoft Defender ウイルス対策のいくつかの側面を報告する 8 つのカードが含まれています。

[ウイルス対策モード カード](#antivirus-mode-card)と[最近のウイルス対策スキャン結果カード](#recent-antivirus-scan-results-card)の 2 つのカードで、Microsoft Defender ウイルス対策機能について報告します。

残りの 6 枚のカードは、組織内のデバイスの Microsoft Defender ウイルス対策の状態について報告します。

| _バージョン_ カード: | _カードの更新_ {<a id="fn1">1</a>} |
|:---|:---|
| [ウイルス対策エンジンのバージョン カード](#antivirus-engine-version-card) <br> [ウイルス対策セキュリティ インテリジェンス バージョン カード](#antivirus-security-intelligence-version-card) <br> [ウイルス対策プラットフォームのバージョン カード](#antivirus-platform-version-card) | [ウイルス対策エンジンの更新カード](#antivirus-engine-updates-card) <br> [セキュリティ インテリジェンス更新プログラム カード](#security-intelligence-updates-card) <br> [ウイルス対策プラットフォームの更新カード](#antivirus-platform-updates-card) |
| 3 つの更新カードには、詳細を確認するためのその他のリソースへのリンクが用意されています。 | 3 つのバージョン カードは、追加情報を提供するポップアップ レポートを提供し、詳細な調査を可能にします。 |

<sup>{[1](#fn1)}</sup> 3 つの _更新_ カードの場合、"**No data available**" は、更新プログラムの状態を報告していないデバイスを示します。 更新プログラムの状態を報告していないデバイスは、次のようなさまざまな理由が原因である可能性があります。

- コンピューターがネットワークから切断されている
- コンピューターの電源が切っているか、休止状態になっている
- Microsoft Defender ウイルス対策が無効になっている
- デバイスが Windows (Mac または Linux) 以外のデバイスである
- クラウド保護が有効になっていない

> [!NOTE]
> 現在、"最新" レポートは Windows デバイスでのみ使用できます。  最新のレポートでは、クラウド保護が有効で、エンジン バージョンが 1.1.19300.2 以降の Windows デバイスに関する情報が生成されます。 Mac や Linux などのクロスプラットフォーム デバイスは、"利用できるデータがありません" の下に一覧表示されます。

> [!div class="mx-imgBorder"]
> ![Microsoft Defender ウイルス対策の正常性タブを表示します](images/device-health-defender-antivirus-health-tab.png)

#### <a name="card-functionality"></a>カード機能

この機能は、基本的にすべてのカードで同じです。 いずれかのカードの番号付きバーをクリックすると、 **Microsoft Defender ウイルス対策の詳細** ポップアップが開き、そのカードの側面のバージョン番号で構成されているすべてのデバイスに関する情報を確認できます。

> [!div class="mx-imgBorder"]
> ![Microsoft Defender ウイルス対策の正常性の詳細を表示する](images/device-health-defender-antivirus-health-antivirus-details.png)

クリックしたバージョン番号が次の場合:

- 現在のバージョンの **修復が必要** で **、セキュリティに関する推奨事項** が存在しない
- 古いバージョン、レポートの上部に通知が表示され、 **修復が必要** であることを示し、 **セキュリティに関する推奨事項** のリンクが表示されます。 セキュリティに関する推奨事項のリンクを選択して、脅威と脆弱性の管理 コンソールに移動します。適切なウイルス対策更新プログラムを推奨できます。

**Microsoft Defender ウイルス対策の詳細** ポップアップで特定の種類の情報を追加または削除するには、[**列のカスタマイズ**] をクリックします。 [ **列のカスタマイズ**] で、アイテムを選択またはクリアして、Microsoft Defender ウイルス対策の詳細レポートに含める項目を指定します。

> [!div class="mx-imgBorder"]
> ![Microsoft Defender ウイルス対策正常性レポートのカスタム列オプションを表示する](images/device-health-defender-antivirus-engine-version-details-custom-columns.png)

ポップアップ内で、デバイスの名前をクリックすると、そのデバイスの [デバイス] ページにリダイレクトされ、詳細なレポートにアクセスできます。

_Microsoft Defender ウイルス対策の詳細_ ポップアップ内の **[エクスポート**] ボタンを使用して、レポートを Excel スプレッドシートにエクスポートできます。 エクスポートされたレポートは、詳細レポートへのエントリ ポイントと、設定したフィルターまたはカスタマイズされた列に基づいて情報をキャプチャします。

API を使用したエクスポートの詳細については、次の記事を参照してください。

- [デバイスウイルス対策の正常性レポートをエクスポートする](device-health-export-antivirus-health-report-api.md)
- [デバイスウイルス対策の正常性の詳細 API のメソッドとプロパティをエクスポートする](device-health-api-methods-properties.md)

#### <a name="microsoft-defender-antivirus-version-and-update-cards-functionality"></a>Microsoft Defender ウイルス対策のバージョンと更新カードの機能

Microsoft Defender ウイルス対策エンジン、セキュリティ インテリジェンス、およびプラットフォーム コンポーネントの _バージョン_ と _更新_ 情報について報告する 6 つのカードの説明を次に示します。

##### <a name="full-report"></a>完全なレポート

3 つの _バージョン_ カードのいずれかで、[ **レポート全体の表示** ] をクリックして、Windows、Mac、Linux の 3 種類の各デバイスの最新の Microsoft Defender ウイルス対策 _バージョン_ レポートを 9 つ表示します。存在する数が 9 未満の場合は、すべて表示されます。 **その他の** カテゴリでは、検出された場合に、10 位以下の最新のウイルス対策エンジンバージョンをキャプチャします。

> [!div class="mx-imgBorder"]
> ![各種類の上位 9 つのオペレーティング システムの分布を示します](images/device-health-defender-antivirus-health-view-full-report.png)

3 つの _バージョン_ カードの主な利点は、最新バージョンのウイルス対策エンジン、プラットフォーム、およびセキュリティ インテリジェンスが利用されているかどうかに関するクイック インジケーターを提供することです。 カードにリンクされている詳細情報と組み合わせて、バージョン カードは、バージョンが最新かどうかを確認し、個々のコンピューターまたはコンピューターのグループに関する情報を収集するための強力なツールになります。
これらのレポートを実行すると、古いバージョンではなく、最新のウイルス対策バージョンがインストールされていることを示すのが理想的です。
これらのレポートを使用して、組織が最新バージョンを最大限に活用しているかどうかを判断します。

> [!div class="mx-imgBorder"]
> ![Microsoft Defender ウイルス対策のバージョンの詳細を表示する](images/device-health-defender-antivirus-health-antivirus-details-up-to-date.png)

マルウェア対策ソリューションで最新の脅威が検出されるようにするには、Windows Updateの一部として更新プログラムを自動的に取得します。

現在のバージョンと、さまざまな Microsoft Defender ウイルス対策コンポーネントを更新する方法の詳細については、 [Microsoft Defender ウイルス対策プラットフォームのサポート](manage-updates-baselines-microsoft-defender-antivirus.md)に関するページを参照してください。

#### <a name="card-descriptions"></a>カードの説明

_各ウイルス対策バージョン_ カードで報告される収集された情報の簡単な概要を次に示します。

##### <a name="antivirus-mode-card"></a>ウイルス対策モード カード

組織内のデバイスの数 (カードに記載されている日付) に関するレポートは、次のいずれかの Microsoft Defender ウイルス対策モードにあります。

| 値 | mode |
|---|---|
| 0 | Active |
| 1 | パッシブ |
| 2 | 無効 (アンインストール、無効、または SideBySidePassive {低周期スキャンとも呼ばれます}) |
| 3 | その他 (実行されていない、不明) |
| 4 | EDRBlocked |

> [!div class="mx-imgBorder"]
> ![Microsoft Defender ウイルス対策モードのフィルター処理を表示する](images/device-health-defender-antivirus-health-antivirus-mode.png)

各モードの説明を次に示します。

- **アクティブ** モード - アクティブ モードでは、デバイス上のプライマリウイルス対策アプリとして Microsoft Defender ウイルス対策が使用されます。 ファイルがスキャンされ、脅威が修正され、検出された脅威が組織のセキュリティ レポートと Windows セキュリティ アプリに一覧表示されます。
- **パッシブ** モード - パッシブ モードでは、デバイス上のプライマリウイルス対策アプリとして Microsoft Defender ウイルス対策は使用されません。 ファイルはスキャンされ、検出された脅威は報告されますが、脅威は Microsoft Defender ウイルス対策によって修復されません。 重要: Microsoft Defender ウイルス対策は、Microsoft Defender for Endpoint にオンボードされているエンドポイントでのみパッシブ モードで実行できます。 「[Microsoft Defender ウイルス対策をパッシブ モードで実行するための要件](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode)」を参照してください。
- **無効** モード - アンインストール済み、無効、sideBySidePassive、および低周期スキャンと同義です。 無効にすると、Microsoft Defender ウイルス対策は使用されません。 ファイルはスキャンされず、脅威は修復されません。 一般に、Microsoft Defender ウイルス対策を無効またはアンインストールすることはお勧めしません。
- **[その他]** モード - [実行されていません]、[不明]
- **ブロック モードの EDR** - エンドポイントの検出と応答 (EDR) ブロック モード。 [ブロック モードでのエンドポイントの検出と応答を](edr-in-block-mode.md)参照してください

パッシブデバイス、LPS デバイス、またはオフデバイスは、潜在的なセキュリティ リスクを提示し、調査する必要があります。

LPS の詳細については、「 [Microsoft Defender ウイルス対策で制限付き定期的なスキャンを使用する」を](limited-periodic-scanning-microsoft-defender-antivirus.md)参照してください。

##### <a name="recent-antivirus-scan-results-card"></a>最近のウイルス対策スキャン結果カード

このカードには、クイック スキャンとフル スキャンのオールアップ結果を示す 2 つの棒グラフがあります。 どちらのグラフでも、最初のバーはスキャンの完了率を示し、 **完了**、 **キャンセル**、または **失敗** を示します。 各セクションの 2 番目のバーには、失敗したスキャンのエラー コードが表示されます。
**[モード**] 列と **[最近のスキャン結果**] 列をスキャンすることで、アクティブなウイルス対策スキャン モードではないデバイスや、最近のウイルス対策スキャンに失敗またはキャンセルしたデバイスをすばやく特定できます。 この情報を使用してレポートに戻り、詳細とセキュリティに関する推奨事項を収集できます。 このカードでエラー コードが報告された場合は、エラー コードの詳細を確認するためのリンクが表示されます。

現在の Microsoft Defender ウイルス対策のバージョンと、さまざまな Microsoft Defender ウイルス対策コンポーネントを更新する方法の詳細については、 [Microsoft Defender ウイルス対策の更新プログラムの管理とベースラインの適用](manage-updates-baselines-microsoft-defender-antivirus.md)に関するページを参照してください。

##### <a name="antivirus-engine-version-card"></a>ウイルス対策エンジンのバージョン カード

組織内の Windows デバイス、Mac デバイス、Linux デバイスにインストールされている最新の Microsoft Defender ウイルス対策エンジンバージョンのリアルタイムの結果を表示します。 Microsoft Defender ウイルス対策エンジンは毎月更新されます。
現在のバージョンと、さまざまな Microsoft Defender ウイルス対策コンポーネントを更新する方法の詳細については、 [Microsoft Defender ウイルス対策プラットフォームのサポート](manage-updates-baselines-microsoft-defender-antivirus.md)に関するページを参照してください。

##### <a name="antivirus-security-intelligence-version-card"></a>ウイルス対策セキュリティ インテリジェンス バージョン カード

ネットワーク上のデバイスにインストールされている _Microsoft Defender ウイルス対策セキュリティ インテリジェンス_ の最も一般的なバージョンを一覧表示します。
Microsoft は、最新の脅威に対処し、検出ロジックを絞り込むために、Microsoft Defender セキュリティ インテリジェンスを継続的に更新します。 これらのセキュリティ インテリジェンスの改良により、潜在的な脅威を正確に特定する Microsoft Defender ウイルス対策 (およびその他の Microsoft マルウェア対策ソリューション) の機能が強化されます。 このセキュリティ インテリジェンスは、クラウド ベースの保護と直接連携して、高速で強力な AI 強化された次世代の保護を提供します。

##### <a name="antivirus-platform-version-card"></a>ウイルス対策プラットフォームのバージョン カード

組織内の Windows、Mac、Linux デバイスの各バージョンにインストールされている最新の Microsoft Defender ウイルス対策プラットフォーム のバージョンのリアルタイムの結果を表示します。 Microsoft Defender ウイルス対策プラットフォームは毎月更新されます。
現在のバージョンと、さまざまな Microsoft Defender ウイルス対策コンポーネントを更新する方法の詳細については、[Microsoft Defender ウイルス対策プラットフォームのサポート](manage-updates-baselines-microsoft-defender-antivirus.md)に関するページを参照してください。

##### <a name="antivirus-engine-updates-card"></a>ウイルス対策エンジンの更新カード

このカードは、最新のバージョンと最新ではないウイルス対策エンジンのバージョンを持つデバイスを識別します。
"_最新_" の一般的な定義 - デバイスのエンジン バージョンは最新のエンジン リリースです 。エンジンは通常、Windows Update (WU)} を介して毎月リリースされます。  WU がリリースされた日から 3 日間の猶予期間があります。

| Microsoft では、次のような **ウイルス対策エンジンの更新プログラムが適用された** デバイスを検討しています。  |  次のようになります。  |
|:----|:----|
| 過去 7 日以内に署名発行時間を使用して Defender に通信 _し、__過去_ 60 日以内にエンジンまたはプラットフォームバージョンのビルド時間を設定しました   | 最新  |
| 過去 7 日以内に署名発行時間を使用して Defender に通信したが、エンジンまたはプラットフォームバージョンのビルド時間が 60 日 _を超える_ | 古い  |
| 過去 7 日間に Defender に通知され、署名発行時間 _が日数を超えた_  場合  | 使用可能なデータがありません  |
| 過去 7 日間に Defender に通知されず、最後の状態が "最新" であった  | 使用可能なデータがありません  |
| 過去 7 日間に Defender に通知されず、最後の状態が "古い"  | 使用可能なデータがありません |

##### <a name="security-intelligence-updates-card"></a>セキュリティ インテリジェンス更新プログラム カード

このカードは、最新のセキュリティ インテリジェンス バージョンと古いバージョンのデバイスを識別します。
"**最新**" の一般的な定義 - デバイスのセキュリティ インテリジェンス バージョンは、過去 7 日間に記述されました。

| Microsoft では、次のような **セキュリティ インテリジェンス更新プログラムが適用された** デバイスを検討しています。  | 次のようになります。  |
|:----|:----|
|  過去 7 日間に記述されたセキュリティ インテリジェンス バージョン | 最新  |
| 過去 7 日以内に Defender に通知され、署名発行時刻が過去 7 日以内に表示されました | 最新  |
| 過去 7 日間に Defender に通知され、署名発行時間が過去 7 日間を超えた場合 | 古い |
| 過去 7 日間に Defender に通知されず、最後の状態が "最新" であった  |  使用可能なデータがありません  |
| 過去 7 日間に Defender に通知されず、最後の状態が最新でない  | 古い |

##### <a name="antivirus-platform-updates-card"></a>ウイルス対策プラットフォームの更新カード

このカードは、ウイルス対策プラットフォームのバージョンが最新のデバイスと古いデバイスを識別します。
"_最新_" の一般的な定義 - デバイスのプラットフォーム バージョンは最新のプラットフォーム リリースです (プラットフォームは通常、Windows Updateを介して毎月リリースされます)。  WU がリリースされた日から 3 日間の猶予期間があります。

| Microsoft では、次のような **ウイルス対策プラットフォームの更新プログラムが適用された** デバイスを検討しています。  |  次のようになります。  |
|:----|:----|
| 過去 7 日以内に署名発行時間を使用して Defender に通信 _し、__過去_ 60 日以内にエンジンまたはプラットフォームバージョンのビルド時間を設定しました   | 最新  |
| 過去 7 日以内に署名発行時間を使用して Defender に通信したが、エンジンまたはプラットフォームバージョンのビルド時間が 60 日 _を超える_ | 古い  |
| 過去 7 日間に Defender に通知され、署名発行時間 _が日数を超えた_  場合  | 使用可能なデータがありません  |
| 過去 7 日間に Defender に通知されず、最後の状態が "最新" であった  | 使用可能なデータがありません  |
| 過去 7 日間に Defender に通知されず、最後の状態が "古い"  | 使用可能なデータがありません |

Microsoft Defender ウイルス対策更新プログラムのバージョンの管理の詳細については、「[月次プラットフォームとエンジンのバージョン](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)」を参照してください。

### <a name="see-also"></a>関連項目

- [デバイスウイルス対策の正常性の詳細 API のメソッドとプロパティをエクスポートする](device-health-api-methods-properties.md)
- [Device-health-export-antivirus-health-report-api.md](device-health-api-methods-properties.md)
- [脅威に対する保護のレポート](threat-protection-reports.md)

## <a name="publicly-released-device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>一般公開: Microsoft Defender for Endpointのデバイスの正常性とコンプライアンスレポート

デバイスの状態レポートには、組織内のデバイスに関する高度な情報が表示されます。 このレポートには、センサーの正常性状態、ウイルス対策状態、OS プラットフォーム、およびWindows 10バージョンを示す傾向のある情報が含まれています。

ダッシュボードは、次の 2 つのセクションに構成されています。

![デバイス レポートの画像。](images/device-reports.png)

|Section|説明|
|---|---|
|1|デバイスの傾向|
|2|デバイスの概要 (現在の日)|

### <a name="device-trends"></a>デバイスの傾向

既定では、デバイスの傾向グラフには、最新の 1 日で終わる 30 日間のデバイス情報が表示されます。 組織で発生している傾向をより適切に把握するために、表示される期間を調整してレポート期間を微調整できます。 期間を調整するには、ドロップダウン オプションから時間範囲を選択します。

- 30 日間
- 3か月
- 6 か月
- Custom

> [!NOTE]
> これらのフィルターは、デバイスの傾向セクションにのみ適用されます。 デバイスの概要セクションには影響しません。

### <a name="device-summary"></a>デバイスの概要

デバイスの傾向グラフとは異なり、デバイスの概要グラフには、現在の日付の範囲のデバイス情報が表示されます。

> [!NOTE]
> 概要セクションに反映されるデータの範囲は、現在の日付の 180 日前です。 たとえば、今日の日付が 2019 年 3 月 27 日の場合、概要セクションのデータには、2018 年 9 月 28 日から 2019 年 3 月 27 日までの数値が反映されます。
> [傾向] セクションに適用されたフィルターは、[概要] セクションには適用されません。

[デバイスの傾向] セクションでは、対応するフィルターを適用してデバイスの一覧にドリルダウンできます。 たとえば、センサー正常性状態カードの [非アクティブ] バーをクリックすると、センサーの状態が非アクティブなデバイスのみが表示される結果が表示されるデバイスの一覧が表示されます。

### <a name="device-attributes"></a>デバイス属性

レポートは、次のデバイス属性を表示するカードで構成されます。

- **正常性状態**: デバイス上のセンサーの状態に関する情報を表示します。 このグラフは、アクティブなデバイス、通信の障害が発生しているデバイス、非アクティブなデバイス、またはセンサー データが表示されないデバイスの概要を示します。
- **アクティブなWindows 10 デバイスのウイルス対策の状態**: デバイスの数と Microsoft Defender ウイルス対策の状態が表示されます。
- **OS プラットフォーム**: 組織内に存在する OS プラットフォームの分布を示します。
- **Windows 10 バージョン**: 組織内のWindows 10 デバイスとそのバージョンの分布を示します。

### <a name="filter-data"></a>データをフィルター処理する

特定の属性を持つデバイスを含めたり除外したりするには、指定されたフィルターを使用します。

デバイス属性から適用するフィルターを複数選択できます。

> [!NOTE]
> これらのフィルターは、レポート **内のすべての** カードに適用されます。

たとえば、アクティブなセンサーの正常性状態を持つデバイスWindows 10に関するデータを表示するには、次のようにします。

1. [ **フィルター] > [センサーの正常性状態] > [アクティブ] です**。
2. 次に、**OS プラットフォーム > Windows 10** を選択します。
3. **[適用]** を選択します。

### <a name="related-articles"></a>関連記事

- [脅威に対する保護のレポート](threat-protection-reports.md)

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)
