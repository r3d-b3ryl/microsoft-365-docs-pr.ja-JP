---
title: Microsoft 365 セキュリティ ポータルのデバイス プロファイル
description: 組織内のデバイスのリスクレベルと露出レベルを表示します。 過去と現在の脅威を分析し、最新の更新プログラムでデバイスを保護します。
keywords: セキュリティ, マルウェア, Microsoft 365, M365, Microsoft 365 Defender, セキュリティ センター, Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity、デバイス ページ、デバイス プロファイル、コンピューター ページ、コンピューター プロファイル
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: dansimp
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: d474b38e65c77fb75dd1472cfa6f316c9200b086
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67386610"
---
# <a name="device-profile-page"></a>[デバイス プロファイル] ページ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 セキュリティ ポータルにはデバイス プロファイル ページが用意されているため、ネットワーク上のデバイスの正常性と状態をすばやく評価できます。

> [!IMPORTANT]
> デバイス プロファイル ページは、デバイスがMicrosoft Defender for Endpoint、Microsoft Defender for Identity、またはその両方に登録されているかどうかによって、若干異なる場合があります。

デバイスがMicrosoft Defender for Endpointに登録されている場合は、デバイス プロファイル ページを使用して、一般的なセキュリティ タスクを実行することもできます。

## <a name="navigating-the-device-profile-page"></a>デバイス プロファイル ページ内を移動する

プロファイル ページは、いくつかの広範なセクションに分かれています。

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-overall.png" alt-text="Microsoft 365 Defender ポータルの [デバイス プロファイル] ページ" lightbox="../../media/mtp-device-profile/hybrid-device-overall.png":::

サイドバー (1) には、デバイスに関する基本的な詳細が一覧表示されます。

メイン コンテンツ領域 (2) には、切り替えてデバイスに関するさまざまな種類の情報を表示できるタブが含まれています。

デバイスがMicrosoft Defender for Endpointに登録されている場合は、応答アクションの一覧も表示されます (3)。 応答アクションを使用すると、一般的なセキュリティ関連タスクを実行できます。

## <a name="sidebar"></a>サイドバー

デバイス プロファイル ページのメイン コンテンツ領域の横にサイドバーがあります。

:::image type="content" source="../../media/mtp-device-profile/azure-atp-only-device-sidebar.png" alt-text="Microsoft 365 Defender ポータルのデバイス プロファイルの [サイドバー] タブ" lightbox="../../media/mtp-device-profile/azure-atp-only-device-sidebar.png":::

サイドバーには、デバイスの完全な名前と露出レベルが一覧表示されます。 また、小さなサブセクションでは、次のような重要な基本情報も提供されます。これには、開くか閉じるかを切り替えることができます。

* **タグ** - デバイスに関連付けられている任意のMicrosoft Defender for Endpoint、Microsoft Defender for Identity、またはカスタム タグ。 Microsoft Defender for Identityのタグは編集できません。
* **セキュリティ情報** - インシデントとアクティブなアラートを開きます。 Microsoft Defender for Endpointに登録されたデバイスには、露出レベルとリスク レベルも表示されます。

> [!TIP]
> 露出レベルは、デバイスがセキュリティの推奨事項に準拠している量に関連しますが、リスク レベルはアクティブなアラートの種類や重大度など、さまざまな要因に基づいて計算されます。

* **デバイスの詳細** - ドメイン、OS、デバイスが最初に表示されたときのタイムスタンプ、IP アドレス、リソース。 Microsoft Defender for Endpointに登録されているデバイスには、正常性状態も表示されます。 Microsoft Defender for Identityに登録されているデバイスには、デバイスが最初に作成されたときの SAM 名とタイムスタンプが表示されます。
* **ネットワーク アクティビティ** - デバイスがネットワーク上で初めて、最後に表示されたときのタイムスタンプ。
* **ディレクトリ データ** (*Microsoft Defender for Identityに登録されているデバイスの場合のみ*) - [UAC](/windows/security/identity-protection/user-account-control/user-account-control-overview) フラグ、[SPN](/windows/win32/ad/service-principal-names)、およびグループ メンバーシップ。

## <a name="response-actions"></a>応答アクション

応答アクションは、脅威から防御し、分析するための簡単な方法を提供します。

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-long-action-bar.png" alt-text="Microsoft 365 Defender ポータルのデバイス プロファイルのアクション バー" lightbox="../../media/mtp-device-profile/hybrid-device-long-action-bar.png":::

> [!IMPORTANT]
> * [応答アクション](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)は、デバイスがMicrosoft Defender for Endpointに登録されている場合にのみ使用できます。
> * Microsoft Defender for Endpointに登録されているデバイスでは、デバイスの OS とバージョン番号に基づいて、応答アクションの数が異なる場合があります。

デバイス プロファイル ページで使用できるアクションは次のとおりです。

* **タグを管理** する - このデバイスに適用したカスタム タグを更新します。
* **デバイスを分離** する - デバイスを組織のネットワークから分離し、Microsoft Defender for Endpointに接続したままにします。 Outlook、Teams、およびSkype for Businessがデバイスが分離されている間に、通信のために実行を許可することを選択できます。
* **アクション センター** - 送信されたアクションの状態を表示します。 別のアクションが既に選択されている場合にのみ使用できます。
* **アプリの実行を制限** する - Microsoft によって署名されていないアプリケーションの実行を禁止します。
* **ウイルス対策スキャンを実行** する - Microsoft Defender ウイルス対策定義を更新し、すぐにウイルス対策スキャンを実行します。 クイック スキャンまたはフル スキャンのどちらかを選択します。
* **調査パッケージを収集** する - デバイスに関する情報を収集します。 調査が完了したら、ダウンロードできます。
* **ライブ応答セッションを開始** する - デバイスにリモート シェルを読み込み、 [詳細なセキュリティ調査を行います](/microsoft-365/security/defender-endpoint/live-response)。
* **自動調査を開始する** - [脅威を自動的に調査して修復](../office-365-security/office-365-air.md)します。 このページから実行する自動調査を手動でトリガーできますが、 [特定のアラート ポリシー](../../compliance/alert-policies.md#default-alert-policies) では、独自に自動調査がトリガーされます。
* **アクション センター** - 現在実行中の応答アクションに関する情報を表示します。

## <a name="tabs-section"></a>[タブ] セクション

[デバイス プロファイル] タブでは、デバイスに関するセキュリティの詳細の概要と、アラートの一覧を含むテーブルを切り替えることができます。

Microsoft Defender for Endpointに登録されているデバイスには、タイムライン、セキュリティに関する推奨事項の一覧、ソフトウェア インベントリ、検出された脆弱性の一覧、不足している KB (セキュリティ更新プログラム) を含むタブも表示されます。

### <a name="overview-tab"></a>[概要] タブ

既定のタブは [ **概要] です**。 デバイスに関する最も重要なセキュリティファクトを簡単に確認できます。

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-overview.png" alt-text="Microsoft 365 Defender ポータルのデバイス プロファイルの [概要] タブ" lightbox="../../media/mtp-device-profile/hybrid-device-tab-overview.png":::

ここでは、デバイスのアクティブなアラートと、現在ログオンしているすべてのユーザーを簡単に確認できます。

デバイスがMicrosoft Defender for Endpointに登録されている場合は、デバイスのリスク レベルと、セキュリティ評価に関する使用可能なデータも表示されます。 セキュリティ評価では、デバイスの公開レベルを記述し、セキュリティに関する推奨事項を提供し、影響を受けるソフトウェアと検出された脆弱性を一覧表示します。

### <a name="alerts-tab"></a>[通知] タブ

[**アラート]** タブには、Microsoft Defender for IdentityとMicrosoft Defender for Endpointの両方からデバイスで発生したアラートの一覧が表示されます。

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-alerts.png" alt-text="Microsoft 365 Defender ポータルのデバイス プロファイルの [アラート] タブ" lightbox="../../media/mtp-device-profile/hybrid-device-tab-alerts.png":::

表示される項目の数と、項目ごとに表示される列をカスタマイズできます。 既定の動作では、ページごとに 30 個のアイテムを一覧表示します。

このタブの列には、アラートをトリガーした脅威の重大度に関する情報のほか、状態、調査の状態、アラートが割り当てられているユーザーが含まれます。

*影響を受けるエンティティ* 列は、現在表示しているプロファイルと、影響を受けるネットワーク内の他のデバイスを参照します。

この一覧から項目を選択すると、選択したアラートに関する詳細情報を含むポップアップが開きます。

この一覧は、重大度、状態、またはアラートが割り当てられているユーザーによってフィルター処理できます。

### <a name="timeline-tab"></a>[タイムライン] タブ

**[タイムライン**] タブには、デバイスで発生したすべてのイベントの対話型の時系列グラフが含まれています。 グラフの強調表示された領域を左右に移動すると、さまざまな期間にわたってイベントを表示できます。 また、対話型グラフとイベントの一覧の間のドロップダウン メニューから、カスタム範囲の日付を選択することもできます。

グラフの下には、選択した日付範囲のイベントの一覧があります。

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-timeline.png" alt-text="Microsoft 365 Defender ポータルのデバイス プロファイルの [タイムライン] タブ" lightbox="../../media/mtp-device-profile/hybrid-device-tab-timeline.png":::

表示される項目の数と一覧の列の両方をカスタマイズできます。 既定の列には、イベントの時刻、アクティブなユーザー、アクションの種類、エンティティ (プロセス)、イベントに関する追加情報が一覧表示されます。

このリストから項目を選択すると、イベント エンティティ グラフを表示するポップアップが開き、イベントに関連する親子プロセスが表示されます。

リストは、特定の種類のイベントでフィルター処理できます。たとえば、レジストリ イベントやスマート スクリーン イベントなどです。

この一覧は、ダウンロード用に CSV ファイルにエクスポートすることもできます。 ファイルはイベントの数によって制限されませんが、エクスポートを選択できる最大時間範囲は 7 日間です。

### <a name="security-recommendations-tab"></a>[セキュリティに関する推奨事項] タブ

[ **セキュリティの推奨事項** ] タブには、デバイスを保護するために実行できるアクションが一覧表示されます。 この一覧で項目を選択するとポップアップが開き、推奨事項を適用する方法の手順を確認できます。

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-security-recs.png" alt-text="Microsoft 365 Defender ポータルのデバイス プロファイルの [セキュリティに関する推奨事項] タブ" lightbox="../../media/mtp-device-profile/hybrid-device-tab-security-recs.png":::

前のタブと同様に、ページごとに表示される項目の数と表示される列をカスタマイズできます。

既定のビューには、対処されたセキュリティの弱点、関連する脅威、脅威の影響を受ける関連コンポーネントまたはソフトウェアなどを詳しく説明する列が含まれています。 アイテムは、推奨事項の状態でフィルター処理できます。

### <a name="software-inventory"></a>ソフトウェア インベントリ

[ **ソフトウェア インベントリ** ] タブには、デバイスにインストールされているソフトウェアが一覧表示されます。

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png" alt-text="Microsoft 365 Defender ポータルのデバイス プロファイルの [ソフトウェア インベントリ] タブ" lightbox="../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png":::

既定のビューには、ソフトウェア ベンダー、インストールされているバージョン番号、既知のソフトウェアの弱点の数、脅威分析情報、製品コード、タグが表示されます。 表示される項目の数と表示される列は、どちらもカスタマイズできます。

この一覧から項目を選択すると、選択したソフトウェアの詳細と、ソフトウェアが最後に見つかった時点のパスとタイムスタンプを含むポップアップが開きます。

この一覧は、製品コードでフィルター処理できます。

### <a name="discovered-vulnerabilities-tab"></a>[検出された脆弱性] タブ

[ **検出された脆弱性** ] タブには、デバイスに影響を与える可能性がある一般的な脆弱性と悪用 (CVE) が一覧表示されます。

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png" alt-text="Microsoft 365 Defender ポータルのデバイス プロファイルの [検出された脆弱性] タブ" lightbox="../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png":::

既定のビューには、CVE の重大度、共通脆弱性スコア (CVS)、CVE に関連するソフトウェア、CVE が発行されたとき、CVE が最後に更新されたとき、CVE に関連付けられている脅威が一覧表示されます。

前のタブと同様に、表示される項目の数と表示される列をカスタマイズできます。

このリストから項目を選択すると、CVE を説明するポップアップが開きます。

### <a name="missing-kbs"></a>不足している KB

[**不足している KB**] タブには、デバイスにまだ適用されていない Microsoft 更新が一覧表示されます。 問題の "KB" は、これらの更新プログラムについて説明する [ナレッジ ベースの記事](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) です。たとえば、 [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762) などです。

:::image type="content" source="../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG" alt-text="Microsoft 365 Defender ポータルのデバイス プロファイルの [不足している KB] タブ" lightbox="../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG":::

既定のビューには、更新プログラム、OS バージョン、影響を受ける製品、対応する CVE、KB 番号、タグが含まれるセキュリティ情報が一覧表示されます。

ページごとに表示される項目の数と、表示される列をカスタマイズできます。

アイテムを選択すると、更新プログラムにリンクするポップアップが開きます。

## <a name="related-topics"></a>関連項目

* [Microsoft 365 Defenderの概要](microsoft-365-defender.md)
* [Microsoft 365 Defender を有効にする](m365d-enable.md)
* [ライブ応答を使用してデバイス上のエンティティを調査する](../defender-endpoint/live-response.md)
* [Office 365 での自動調査および対応 (AIR)](../office-365-security/office-365-air.md)
