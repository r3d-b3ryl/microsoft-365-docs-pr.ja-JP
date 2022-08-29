---
title: Defender for Endpoint Devices の一覧のデバイスを調査する
description: 影響を受けるデバイスを調査するには、アラート、ネットワーク接続情報の確認、デバイス タグとグループの追加、サービスの正常性の確認を行います。
keywords: デバイス, タグ, グループ, エンドポイント, アラート キュー, アラート, デバイス名, ドメイン, 最後に見た, 内部 IP, アクティブなアラート, 脅威カテゴリ, フィルター, 並べ替え, アラートの確認, ネットワーク, 接続, 種類, パスワード盗難, ランサムウェア, エクスプロイト, 脅威, 重要度の低い, サービスの正常性
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f80f33b76ad5061372351ef0c399adabcc8a8c26
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67384448"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a>Microsoft Defender for Endpoint デバイスの一覧のデバイスを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatemachines-abovefoldlink)

特定のデバイスで発生したアラートの詳細を調査して、アラートまたは侵害の潜在的な範囲に関連する可能性がある他の動作やイベントを特定します。

> [!NOTE]
> 調査または対応プロセスの一環として、デバイスから調査パッケージを収集できます。 次の方法を使用します。 [デバイスから調査パッケージを収集します](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices)。

影響を受けるデバイスをポータルに表示するたびにクリックして、そのデバイスに関する詳細なレポートを開くことができます。 影響を受けるデバイスは、次の領域で識別されます。

- [デバイスの一覧](investigate-machines.md)
- [アラート キュー](alerts-queue.md)
- [セキュリティ運用ダッシュボード](security-operations-dashboard.md)
- 個々のアラート
- 個々のファイルの詳細ビュー
- 任意の IP アドレスまたはドメインの詳細ビュー

特定のデバイスを調査すると、次の情報が表示されます。

- デバイスの詳細
- 応答アクション
- タブ (概要、アラート、タイムライン、セキュリティに関する推奨事項、ソフトウェア インベントリ、検出された脆弱性、欠落している KB)
- カード (アクティブなアラート、ログオンしているユーザー、セキュリティ評価、デバイスの正常性状態) 
 

:::image type="content" source="images/specific-device.png" alt-text="デバイス ビュー" lightbox="images/specific-device.png":::

> [!NOTE]
> 製品の制約により、デバイス プロファイルでは、(デバイス ページにも表示される) "最後に見た" 時間枠を決定するときに、すべてのサイバー証拠が考慮されるわけではありません。
> たとえば、[デバイス] ページの [最後に表示] の値は、コンピューターのタイムラインで最新のアラートまたはデータを使用できる場合でも、古い時間枠を示す場合があります。

## <a name="device-details"></a>デバイスの詳細

デバイスの詳細セクションでは、デバイスのドメイン、OS、正常性状態などの情報を提供します。 デバイスで使用可能な調査パッケージがある場合は、パッケージをダウンロードできるリンクが表示されます。

## <a name="response-actions"></a>応答アクション

応答アクションは、特定のデバイス ページの上部に沿って実行され、次のものが含まれます。

- タグの管理
- デバイスの分離
- アプリの実行を制限する
- ウイルス対策スキャンの実行
- 調査パッケージの収集
- ライブ応答セッションを開始する
- 自動調査を開始する
- 脅威のエキスパートに相談する
- アクション センター

アクション センター、特定のデバイス ページ、または特定のファイル ページで、応答アクションを実行できます。

デバイスでアクションを実行する方法の詳細については、「デバイスで [応答アクションを実行する](respond-machine-alerts.md)」を参照してください。

詳細については、「 [ユーザー エンティティの調査](investigate-user.md)」を参照してください。

## <a name="tabs"></a>タブ

タブには、デバイスに関連するセキュリティと脅威の防止に関する情報が表示されます。 各タブで、列ヘッダーの上にあるバーから [列の **カスタマイズ** ] を選択して、表示される列をカスタマイズできます。

### <a name="overview"></a>概要

[ **概要** ] タブには、アクティブなアラート、ログオンしているユーザー、およびセキュリティ評価の [カード](#cards) が表示されます。

:::image type="content" source="images/overview-device.png" alt-text="デバイス ページの [概要] タブ" lightbox="images/overview-device.png":::

### <a name="alerts"></a>アラート

[ **アラート]** タブには、デバイスに関連付けられているアラートの一覧が表示されます。 この一覧は、 [アラート キュー](alerts-queue.md)のフィルター処理されたバージョンであり、アラート、重大度 (高、中、低、情報)、キュー内の状態 (新規、進行中、解決済み)、分類 (未設定、偽アラート、真のアラート)、調査状態、アラートのカテゴリ、アラートに対処しているユーザー、および最後のアクティビティの簡単な説明を示します。 アラートをフィルター処理することもできます。

:::image type="content" source="images/alerts-device.png" alt-text="デバイスに関連するアラートのタブ" lightbox="images/alerts-device.png":::

アラートの左側にある円アイコンが選択されると、ポップアップが表示されます。 このパネルでは、アラートを管理し、インシデント番号や関連デバイスなどの詳細を表示できます。 一度に複数のアラートを選択できます。

インシデント グラフとプロセス ツリーを含むアラートのフル ページ ビューを表示するには、アラートのタイトルを選択します。

### <a name="timeline"></a>タイムライン

**[タイムライン**] タブには、デバイスで観察されたイベントと関連するアラートの時系列ビューが表示されます。 これにより、デバイスに関連するすべてのイベント、ファイル、および IP アドレスを関連付けることができます。

タイムラインを使用すると、特定の期間内に発生したイベントを選択的にドリルダウンすることもできます。 選択した期間にデバイスで発生したイベントの一時的なシーケンスを表示できます。 ビューをさらに制御するには、イベント グループでフィルター処理するか、列をカスタマイズします。

> [!NOTE]
> ファイアウォール イベントを表示するには、監査ポリシーを有効にする必要があります。「 [監査フィルター プラットフォーム接続](/windows/security/threat-protection/auditing/audit-filtering-platform-connection)」を参照してください。
>
> ファイアウォールには、次のイベントが含まれます。
>
> - [5025](/windows/security/threat-protection/auditing/event-5025) - ファイアウォール サービスが停止しました
> - [5031](/windows/security/threat-protection/auditing/event-5031) - アプリケーションがネットワーク上の受信接続を受け入れるのをブロックする
> - [5157](/windows/security/threat-protection/auditing/event-5157) - ブロックされた接続

:::image type="content" source="images/timeline-device.png" alt-text="イベントを含むデバイス タイムライン" lightbox="images/timeline-device.png":::

一部の機能には、次のものが含まれます。

- 特定のイベントを検索する
  - 検索バーを使用して、特定のタイムライン イベントを検索します。
- 特定の日付からイベントをフィルター処理する
  - テーブルの左上にある予定表アイコンを選択して、過去の日、週、30 日間、またはカスタム範囲のイベントを表示します。 既定では、デバイスタイムラインは過去 30 日間のイベントを表示するように設定されています。
  - タイムラインを使用して、セクションを強調表示して特定の時点にジャンプします。 タイムライン上の矢印は、自動調査を正確に示します
- 詳細なデバイス タイムライン イベントをエクスポートする
  - 現在の日付または指定した日付範囲のデバイス タイムラインを最大 7 日間エクスポートします。

特定のイベントの詳細については、「 **追加情報」** セクションを参照してください。 これらの詳細は、次のようなイベントの種類によって異なります。

- Application Guard に含まれる - Web ブラウザー イベントが分離されたコンテナーによって制限された
- アクティブな脅威が検出されました - 脅威の検出は、脅威の実行中に発生しました
- 修復に失敗しました - 検出された脅威を修復しようとしましたが、失敗しました
- 修復に成功しました - 検出された脅威が停止され、クリーニングされました
- ユーザーによってバイパスされた警告 - Windows Defender SmartScreen 警告が無視され、ユーザーによってオーバーライドされました
- 疑わしいスクリプトが検出されました - 悪意のある可能性のあるスクリプトが実行されているのが見つかりました
- アラート カテゴリ - イベントがアラートの生成につながった場合は、アラート カテゴリ ("横移動" など) が提供されます。

#### <a name="event-details"></a>イベントの詳細

イベントを選択すると、そのイベントに関する関連する詳細が表示されます。 パネルが表示され、一般的なイベント情報が表示されます。 適用可能でデータが使用可能な場合は、関連エンティティとそのリレーションシップを示すグラフも表示されます。

イベントと関連イベントをさらに調べるには、関連イベントの **ハント** を選択して [高度なハンティング](advanced-hunting-overview.md) クエリをすばやく実行できます。 クエリは、選択したイベントと、同じエンドポイントで同じ時刻に発生した他のイベントの一覧を返します。

:::image type="content" source="images/event-details.png" alt-text="イベントの詳細パネル" lightbox="images/event-details.png":::

### <a name="security-recommendations"></a>セキュリティに関する推奨事項

**セキュリティに関する推奨事項** は、Microsoft Defender for Endpointの [脆弱性管理機能](tvm-dashboard-insights.md)から生成されます。 推奨事項を選択するとパネルが表示され、推奨事項の説明や、それを適用しないことに関連する潜在的なリスクなどの関連する詳細を表示できます。 詳細については、「 [セキュリティに関する推奨事項](tvm-security-recommendation.md) 」を参照してください。

:::image type="content" source="images/security-recommendations-device.png" alt-text="[セキュリティに関する推奨事項] タブ" lightbox="images/security-recommendations-device.png":::

### <a name="software-inventory"></a>ソフトウェア インベントリ

[ **ソフトウェア インベントリ** ] タブでは、弱点や脅威と共に、デバイス上のソフトウェアを表示できます。 ソフトウェアの名前を選択すると、ソフトウェアの詳細ページに移動し、セキュリティに関する推奨事項、検出された脆弱性、インストールされたデバイス、およびバージョンの配布を表示できます。 詳細については、「 [ソフトウェア インベントリ](tvm-software-inventory.md) 」を参照してください。

:::image type="content" source="images/software-inventory-device.png" alt-text="[ソフトウェア インベントリ] タブ" lightbox="images/software-inventory-device.png":::

### <a name="discovered-vulnerabilities"></a>検出された脆弱性

[ **検出された脆弱性** ] タブには、デバイスで検出された脆弱性の名前、重大度、脅威の分析情報が表示されます。 特定の脆弱性を選択すると、説明と詳細が表示されます。

:::image type="content" source="images/discovered-vulnerabilities-device.png" alt-text="[検出された脆弱性] タブ" lightbox="images/discovered-vulnerabilities-device.png":::

### <a name="missing-kbs"></a>不足している KB
[ **不足している KB** ] タブには、デバイスの不足しているセキュリティ更新プログラムが一覧表示されます。

:::image type="content" source="images/missing-kbs-device.png" alt-text="[不足している KB] タブ" lightbox="images/missing-kbs-device.png":::

## <a name="cards"></a>カード

### <a name="active-alerts"></a>アクティブなアラート

**Azure Advanced Threat Protection** カードには、デバイスとそのリスク レベルに関連するアラートの概要が表示されます(Microsoft Defender for Identity機能を有効にしていて、アクティブなアラートがある場合)。 詳細については、「アラート」のドリルダウンを参照してください。

:::image type="content" source="images/risk-level-small.png" alt-text="アクティブなアラート カード" lightbox="images/risk-level-small.png":::

> [!NOTE]
> この機能を使用するには、Microsoft Defender for Identityと Defender for Endpoint の両方で統合を有効にする必要があります。 Defender for Endpoint では、高度な機能でこの機能を有効にすることができます。 高度な機能を有効にする方法の詳細については、「高度な機能 [を有効にする」](advanced-features.md)を参照してください。

### <a name="logged-on-users"></a>ログオンしているユーザー

**[ログオンユーザー]** カードには、過去 30 日間にログオンしたユーザーの数と、最も頻度の低いユーザーが表示されます。 [すべてのユーザーを表示] リンクを選択すると、詳細ウィンドウが開き、ユーザーの種類、ログオンの種類、ユーザーが最初に表示されたときや最後に表示された日時などの情報が表示されます。 詳細については、「 [ユーザー エンティティの調査](investigate-user.md)」を参照してください。

:::image type="content" source="images/logged-on-users.png" alt-text="[ユーザーの詳細] ウィンドウ" lightbox="images/logged-on-users.png":::

> [!NOTE]
> "最も頻度の高い" ユーザー値は、対話形式で正常にログオンしたユーザーの証拠に基づいてのみ計算されます。
> ただし、"すべてのユーザー" サイド ペインでは、あらゆる種類のユーザー ログオンが計算されるため、ユーザーが対話型でない可能性があるため、サイド ウィンドウにユーザーが頻繁に表示されることが予想されます。

### <a name="security-assessments"></a>セキュリティ評価

**セキュリティ評価** カードには、全体的な露出レベル、セキュリティに関する推奨事項、インストールされているソフトウェア、検出された脆弱性が表示されます。 デバイスの露出レベルは、保留中のセキュリティ推奨事項の累積的な影響によって決まります。

:::image type="content" source="images/security-assessments.png" alt-text="セキュリティ評価カード" lightbox="images/security-assessments.png":::


### <a name="device-health-status"></a>デバイスの正常性の状態

**デバイスの正常性状態** カードには、特定のデバイスの正常性レポートの概要が表示されます。 次のいずれかの状態がカードの上部に表示され、デバイスの全体的な状態が示されます。

- デバイスが最新の状態
- プラットフォームが最新ではありません
- フル スキャンに失敗しました
- クイック スキャンに失敗しました
- エンジンが最新ではない
- セキュリティ インテリジェンスが最新ではない
- Defender ウイルス対策がアクティブでない
- macOS & Linux では使用できない状態

カード内のその他の情報には、最後のフル スキャン、最後のクイック スキャン、セキュリティ インテリジェンス更新プログラムのバージョン、エンジン更新プログラムのバージョン、プラットフォーム更新プログラムのバージョン、Defender ウイルス対策モードなどがあります。 

>[!NOTE]
>macOS デバイスと Linux デバイスの全体的な状態メッセージは、現在、"MacOS & Linux では使用できない状態" として表示されています。 現時点では、状態の概要は Windows デバイスでのみ使用できます。 テーブル内の他のすべての情報は、サポートされているすべてのプラットフォームの各デバイス正常性信号の個々の状態を示す最新の情報です。 

デバイス正常性レポートの詳細なビューを取得するには、[ **レポート] > [デバイスの正常性]** に移動します。 詳細については、「[Microsoft Defender for Endpointのデバイスの正常性とコンプライアンスレポート](/microsoft-365/security/defender-endpoint/machine-reports)」を参照してください。 

:::image type="content" source="images/device-health-status.png"  alt-text="デバイスの正常性状態カード" lightbox="images/device-health-status.png":::



## <a name="related-topics"></a>関連項目

- [Microsoft Defender for Endpoint アラート キューを表示して整理する](alerts-queue.md)
- [Microsoft Defender for Endpoint アラートを管理する](manage-alerts.md)
- [Microsoft Defender for Endpointアラートを調査する](investigate-alerts.md)
- [Defender for Endpoint アラートに関連付けられているファイルを調査する](investigate-files.md)
- [Defender for Endpoint アラートに関連付けられている IP アドレスを調査する](investigate-ip.md)
- [Defender for Endpoint アラートに関連付けられているドメインを調査する](investigate-domain.md)
- [Defender for Endpoint のユーザー アカウントを調査する](investigate-user.md)
- [セキュリティに関する推奨事項](tvm-security-recommendation.md)
- [ソフトウェア インベントリ](tvm-software-inventory.md)
