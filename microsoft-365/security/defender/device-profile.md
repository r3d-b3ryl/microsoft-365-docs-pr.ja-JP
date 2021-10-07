---
title: セキュリティ ポータルのMicrosoft 365プロファイル
description: 組織内のデバイスのリスクと露出レベルを表示します。 過去および現在の脅威を分析し、最新の更新プログラムを使用してデバイスを保護します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、Microsoft 365 Defender、セキュリティ センター、Microsoft Defender for Endpoint、microsoft Defender for Office 365、Microsoft Defender for Identity、デバイス ページ、デバイス プロファイル、コンピューター ページ、コンピューター プロファイル
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 9838d7f3ffed46c62891822c6e3761e36d49baf5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60181213"
---
# <a name="device-profile-page"></a>[デバイス プロファイル] ページ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


セキュリティ Microsoft 365は、デバイス プロファイル ページを提供します。そのため、ネットワーク上のデバイスの正常性と状態をすばやく評価できます。

> [!IMPORTANT]
> デバイス プロファイル ページは、デバイスが Microsoft Defender for Endpoint、Microsoft Defender for Identity、または両方に登録されているかどうかによって、若干異なって表示される場合があります。

デバイスが Microsoft Defender for Endpoint に登録されている場合は、デバイス プロファイル ページを使用して一般的なセキュリティ タスクを実行することもできます。

## <a name="navigating-the-device-profile-page"></a>デバイス プロファイル ページの移動

プロファイル ページは、いくつかの広範なセクションに分割されます。

![(1) タブ領域 (2) サイドバーと (3) アクションが赤色で強調表示されたデバイス プロファイル ページのイメージ。](../../media/mtp-device-profile/hybrid-device-overall.png)

サイドバー (1) には、デバイスに関する基本的な詳細が一覧表示されます。

メイン コンテンツ領域 (2) には、デバイスに関するさまざまな種類の情報を表示するために切り替え可能なタブが含まれています。

デバイスが Microsoft Defender for Endpoint に登録されている場合は、応答アクションの一覧 (3) も表示されます。 応答アクションを使用すると、一般的なセキュリティ関連のタスクを実行できます。

## <a name="sidebar"></a>サイドバー

デバイス プロファイル ページのメイン コンテンツ領域の横にサイドバーがあります。

![デバイス プロファイルのサイドバー タブのイメージ。](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

サイドバーには、デバイスの完全な名前と露出レベルが一覧表示されます。 また、次のような、開くまたは閉じ切り替えできる小さなサブセクションの重要な基本情報も提供します。

* **タグ** - デバイスに関連付けられた Microsoft Defender for Endpoint、Microsoft Defender for Identity、またはカスタム タグ。 Microsoft Defender for Identity のタグは編集できません。
* **セキュリティ情報** - インシデントとアクティブなアラートを開きます。 Microsoft Defender for Endpoint に登録されているデバイスには、露出レベルとリスク レベルも表示されます。

> [!TIP]
> 露出レベルは、デバイスがセキュリティ推奨事項に準拠している量に関連しますが、リスク レベルはアクティブなアラートの種類や重大度など、さまざまな要因に基づいて計算されます。

* **デバイスの詳細** - ドメイン、OS、デバイスが最初に表示された時刻のタイムスタンプ、IP アドレス、リソース。 Microsoft Defender for Endpoint に登録されているデバイスにも正常性状態が表示されます。 Microsoft Defender for Identity に登録されているデバイスには、デバイスが最初に作成された時刻の SAM 名とタイムスタンプが表示されます。
* **ネットワーク アクティビティ** - デバイスがネットワーク上で初めて、最後に表示されたタイムスタンプ。
* **ディレクトリ データ***(Microsoft Defender for Identity* に登録されているデバイスの場合のみ) - UAC フラグ [、SPN、](/windows/win32/ad/service-principal-names)およびグループ メンバーシップ。 [](/windows/security/identity-protection/user-account-control/user-account-control-overview)

## <a name="response-actions"></a>応答アクション

応答アクションは、脅威に対する防御と分析を迅速に行う方法を提供します。

![デバイス プロファイルのアクション バーのイメージ。](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * [応答アクション](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) は、デバイスが Microsoft Defender for Endpoint に登録されている場合にのみ使用できます。
> * Microsoft Defender for Endpoint に登録されているデバイスでは、デバイスの OS とバージョン番号に基づいて、応答アクションの数が異なる場合があります。

デバイス プロファイル ページで使用できるアクションは次のとおりです。

* **タグの管理** - このデバイスに適用したカスタム タグを更新します。
* **デバイスの分離** - デバイスを Microsoft Defender for Endpoint に接続しながら、組織のネットワークからデバイスを分離します。 通信の目的で、Outlook、Teams、Skype for Businessの実行を許可できます。
* **アクション センター** - 送信されたアクションの状態を表示します。 別のアクションが既に選択されている場合にのみ使用できます。
* **アプリの実行を制限** する - Microsoft によって署名されていないアプリケーションが実行されるのを防ぐ。
* **ウイルス対策スキャンを実行** する - Windows Defender ウイルス対策定義を更新し、すぐにウイルス対策スキャンを実行します。 [クイック スキャン] または [フル スキャン] の間で選択します。
* **調査パッケージの収集** - デバイスに関する情報を収集します。 調査が完了したら、ダウンロードできます。
* **ライブ応答セッションの開始** - デバイスにリモート シェルを読み込んで、詳細なセキュリティ [調査を行います](/microsoft-365/security/defender-endpoint/live-response)。
* **自動調査の開始** - 脅威 [を自動的に調査および修復します](../office-365-security/office-365-air.md)。 このページから自動調査を手動で実行することもできますが、特定のアラート[](../../compliance/alert-policies.md#default-alert-policies)ポリシーによって独自に自動調査がトリガーされます。
* **アクション センター** - 現在実行中の応答アクションに関する情報を表示します。

## <a name="tabs-section"></a>[タブ] セクション

デバイス プロファイル タブを使用すると、デバイスに関するセキュリティの詳細と、アラートの一覧を含むテーブルの概要を切り替えられます。

Microsoft Defender for Endpoint に登録されているデバイスには、タイムライン、セキュリティ推奨事項の一覧、ソフトウェア インベントリ、検出された脆弱性の一覧、および不足している KB (セキュリティ更新プログラム) を備えたタブも表示されます。

### <a name="overview-tab"></a>[概要] タブ

既定のタブは [概要] **です**。 デバイスに関する最も重要なセキュリティの事実を簡単に確認できます。

![デバイス プロファイルの [概要] タブのイメージ。](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

ここでは、デバイスのアクティブなアラートと、現在ログオンしているユーザーを簡単に確認できます。

デバイスが Microsoft Defender for Endpoint に登録されている場合は、デバイスのリスク レベルと、セキュリティ評価に関して利用可能なデータも表示されます。 セキュリティ評価では、デバイスの露出レベルを説明し、セキュリティに関する推奨事項を提供し、影響を受けるソフトウェアと検出された脆弱性を一覧表示します。

### <a name="alerts-tab"></a>[通知] タブ

[ **アラート]** タブには、Microsoft Defender for Identity と Microsoft Defender for Endpoint の両方から、デバイスで発生したアラートの一覧が表示されます。

![デバイス プロファイルの [アラート] タブのイメージ。](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

表示されるアイテムの数と、各アイテムに対して表示される列をカスタマイズできます。 既定の動作では、ページごとに 30 アイテムを一覧表示します。

このタブの列には、アラートをトリガーした脅威の重大度、および状態、調査状態、アラートが割り当てられているユーザーに関する情報が含まれます。

[ *影響を受けるエンティティ* ] 列は、現在表示されているプロファイルと、影響を受けるネットワーク内の他のデバイスを含むデバイス (エンティティ) を参照します。

このリストからアイテムを選択すると、選択したアラートに関するさらに詳しい情報を含むフライアウトが開きます。

このリストは、重大度、状態、またはアラートが割り当てられているユーザーによってフィルター処理できます。

### <a name="timeline-tab"></a>[タイムライン] タブ

[ **タイムライン]** タブには、デバイスで発生したすべてのイベントの対話型の時系列グラフが表示されます。 グラフの強調表示された領域を左または右に移動すると、さまざまな期間のイベントを表示できます。 また、対話型グラフとイベントの一覧の間にあるドロップダウン メニューから、日付のカスタム範囲を選択することもできます。

グラフの下には、選択した日付範囲のイベントの一覧があります。

![デバイス プロファイルの [タイムライン] タブのイメージ。](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

表示されるアイテムの数とリストの列の両方をカスタマイズできます。 既定の列には、イベント時間、アクティブ ユーザー、アクションの種類、エンティティ (プロセス)、およびイベントに関する追加情報が一覧表示されます。

このリストからアイテムを選択すると、イベントに関係する親プロセスと子プロセスを示すイベント エンティティ グラフが表示されるフライアウトが開きます。

リストは、特定の種類のイベントでフィルター処理できます。たとえば、レジストリ イベントやスマート スクリーン イベントなどです。

リストは、ダウンロード用に CSV ファイルにエクスポートできます。 ファイルはイベントの数によって制限されるのではなく、エクスポートできる最大時間範囲は 7 日間です。

### <a name="security-recommendations-tab"></a>[セキュリティの推奨事項] タブ

[ **セキュリティの推奨事項] タブ** には、デバイスを保護するために実行できるアクションが一覧表示されます。 このリストでアイテムを選択すると、提案の適用方法に関する手順を取得できるフライアウトが開きます。

![デバイス プロファイルの [セキュリティの推奨事項] タブのイメージ。](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

前のタブと同様に、ページごとに表示されるアイテムの数と表示される列をカスタマイズできます。

既定のビューには、対応するセキュリティの弱点、関連する脅威、脅威の影響を受ける関連コンポーネントまたはソフトウェアなどについて詳しく説明する列が含まれます。 アイテムは、推奨事項の状態によってフィルター処理できます。

### <a name="software-inventory"></a>ソフトウェア インベントリ

[ **ソフトウェア インベントリ] タブ** には、デバイスにインストールされているソフトウェアが一覧表示されます。

![デバイス プロファイルの [ソフトウェア インベントリ] タブのイメージ。](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

既定のビューには、ソフトウェア ベンダー、インストールされているバージョン番号、既知のソフトウェアの弱点の数、脅威の分析情報、製品コード、およびタグが表示されます。 表示されるアイテムの数と表示される列の両方をカスタマイズできます。

このリストからアイテムを選択すると、選択したソフトウェアの詳細と、ソフトウェアが最後に見つかった時点のパスとタイムスタンプを含むフライアウトが開きます。

このリストは、製品コードでフィルター処理できます。

### <a name="discovered-vulnerabilities-tab"></a>[検出された脆弱性] タブ

[ **検出された脆弱性] タブ** には、デバイスに影響を与える可能性のある一般的な脆弱性と悪用 (CVEs) が一覧表示されます。

![デバイス プロファイルの [検出された脆弱性] タブのイメージ。](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

既定のビューには、CVE の重大度、共通の脆弱性スコア (CVS)、CVE に関連するソフトウェア、CVE が公開された場合、CVE が最後に更新された場合、および CVE に関連する脅威が一覧表示されます。

前のタブと同様に、表示されるアイテムの数と表示される列をカスタマイズできます。

このリストからアイテムを選択すると、CVE を説明するフライアウトが開きます。

### <a name="missing-kbs"></a>不足している KB

[ **不足している KB]** タブには、デバイスにまだ適用されていない Microsoft 更新プログラムが一覧表示されます。 問題の "KB" は、これらの [更新プログラムについて説明](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) するサポート技術情報の記事です。たとえば [、KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

![デバイス プロファイルの不足している kbs タブのイメージ。](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

既定のビューには、更新プログラム、OS バージョン、影響を受ける製品、アドレス指定された CVEs、KB 番号、およびタグが含まれるセキュリティ情報が一覧表示されます。

ページごとに表示されるアイテムの数と表示される列をカスタマイズできます。

アイテムを選択すると、更新プログラムにリンクするフライアウトが開きます。

## <a name="related-topics"></a>関連トピック

* [Microsoft 365 Defender概要](microsoft-365-defender.md)
* [Microsoft 365 Defender を有効にする](m365d-enable.md)
* [ライブ応答を使用して、デバイス上のエンティティを調査する](../defender-endpoint/live-response.md)
* [Office 365 での自動調査および対応 (AIR)](../office-365-security/office-365-air.md)
