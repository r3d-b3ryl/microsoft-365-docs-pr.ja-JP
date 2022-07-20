---
title: Microsoft 365 Business Premium のセキュリティ操作ガイド
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.date: 07/19/2022
ms.collection:
- m365solution-smb
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
description: '毎日、毎週、または毎月の操作に関して、Defender ポータルで取り組む内容に関する一連の提案事項。 '
ms.openlocfilehash: ab444aad5980af224b2005209dc5596fcb10f899
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2022
ms.locfileid: "66894079"
---
# <a name="microsoft-365-business-premium-security-operations-guide"></a>Microsoft 365 Business Premium セキュリティ操作ガイド

Microsoft 365 Business Premium を初めて使用する場合、またはセキュリティ操作ガイドがまだ用意されていない場合は、この記事を開始点にすることができます。 セキュリティ操作ガイドを既にお持ちの場合は、この記事の推奨される形式に照らして確認してください。

このガイダンスを使用して、セキュリティ インシデントの優先順位と、セキュリティ チームが Microsoft Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で実行するタスクに関する意思決定を行うことができます。

| おすすめの頻度 | タスク  |
|---------|---------|
| Daily (日単位)  | [脅威の脆弱性を確認します](#check-your-threat-vulnerability)。<br/>[保留中のアクションをアクション センターで確認します](#review-pending-actions-in-the-action-center)。<br/>[脅威の検出を含むデバイスを確認します](#review-devices-with-threat-detections)。<br/>[新しいインシデントまたはアラートについて説明します](#learn-about-new-incidents-or-alerts)。 |
| Weekly (週単位) | [Microsoft セキュア スコアを監視して改善します](#monitor-and-improve-your-microsoft-secure-score)。<br/>[デバイスのセキュア スコアを確認します](#review-the-secure-score-for-devices)。<br/>[デバイスのセキュリティ スコアを向上させます](#improve-your-secure-score-for-devices)。 |
| 毎月 | [レポートを実行します](#run-reports)。<br/>[シミュレーション チュートリアルを実行します](#run-a-simulation-tutorial)。<br/>[ラーニング ハブを探索します](#explore-the-learning-hub)。 |
| 必要に応じて | [[脅威の分析] ダッシュボードを使用します](#use-the-threat-analytics-dashboard)。<br/>[スキャンまたは調査を実行します](#run-a-scan-or-automated-investigation)。<br/>[アイテムを修復します](#remediate-an-item)。 | 

以降のセクションでは、各タスクの詳細について説明します。
  
## <a name="suggested-daily-tasks"></a>推奨される毎日のタスク

セキュリティ タスクを毎日実行するための推奨事項をいくつか以下に示します。

- [脅威の脆弱性を確認します](#check-your-threat-vulnerability)。
- [保留中のアクションをアクション センターで確認します](#review-pending-actions-in-the-action-center)。
- [脅威の検出を含むデバイスを確認します](#review-devices-with-threat-detections)。
- [新しいインシデントまたはアラートについて説明します](#learn-about-new-incidents-or-alerts)。

### <a name="check-your-threat-vulnerability"></a>脅威の脆弱性を確認する

簡単に言うと、脆弱性管理ダッシュボードを見て、脅威の脆弱性のスナップショットを取得できます。 これは、組織がサイバー セキュリティの脅威に対してどれほど脆弱であるかを反映しています。 暴露スコアが低いということは、デバイスが悪用されやすいことを意味します。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のナビゲーション ウィンドウで、**[脆弱性の管理] > [ダッシュボード]** の順に選択します。

2. 組織の暴露スコアを見てみましょう。 許容範囲または "高" の範囲にある場合は、次に進むことができます。 そうでない場合は、**[スコアの向上]** を選択して、このスコアを向上させるための詳細情報とセキュリティに関する推奨事項を表示します。

暴露スコアの認識は、次の点に役立ちます。

- 組織内のセキュリティの状態に関する高レベルな取り組みをすばやく理解して特定する
- 調査またはアクションが必要な領域を検出して対応し、現在の状態を改善する
- セキュリティに関する取り組みの影響について、同僚や経営陣と連携する

### <a name="review-pending-actions-in-the-action-center"></a>保留中のアクションをアクション センターで確認する

脅威が検出されると、修復アクションが実行されます。 特定の脅威とセキュリティ設定の構成方法によっては、修復アクションが自動的に実行されるか、承認時にのみ実行される可能性があるため、定期的に監視する必要があります。 修復アクションの例としては、検疫へのファイルの送信、プロセスの実行の停止、スケジュールされたタスクの削除などがあります。 すべての修復アクションは、アクション センターで追跡されます。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のナビゲーション ウィンドウで、**[アクション センター]** を選択します。

2. 保留中のアクションを表示して承認 (または拒否) するには、**[保留中]** タブを選択します。 このようなアクションは、ウイルス対策/マルウェア対策保護、自動調査、手動応答アクティビティ、またはライブ応答セッションから発生する可能性があります。

3. **[履歴]** タブを選択して、完了したアクションのリストを表示します。

### <a name="review-devices-with-threat-detections"></a>脅威の検出を含むデバイスの確認

脅威が発生したデバイスがあるかどうかを確認するには、次の手順を実行します。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のナビゲーション ウィンドウで、**[レポート] > [全般] > [セキュリティ レポート]** の順に選択します。

2. [脆弱なデバイス] 行まで下にスクロールします。 デバイスで脅威が検出された場合は、この行にその情報が表示されます。

### <a name="learn-about-new-incidents-or-alerts"></a>新しいインシデントまたはアラートについて学習する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のナビゲーション メニューで、**[インシデント]** を選択します。 インシデントは、関連するアラートを含むページに表示されます。

2. アラートを選択してポップアップ ウィンドウを開き、アラートの詳細を確認できます。

3. ポップアップでは、影響を受けるアラートの一覧 (エンドポイントやユーザー アカウントなど) を表示したり、使用可能なアクションを実行したり、リンクを使用して詳細情報を表示したり、選択したアラートの詳細ページを開いたりすることもできます。

### <a name="run-a-scan-or-automated-investigation"></a>スキャンまたは自動調査を実行する

1. Microsoft 365 Defender ポータル (https://security.microsoft.com)) のナビゲーション ウィンドウで、[デバイス インベントリ] を選択します。

2. デバイスを選択してポップアップ パネルを開き、表示される情報を確認します。

3. 省略記号 (...) を選択して、アクション メニューを開きます。

4. 「**ウイルス対策スキャンを実行する**」や「**自動調査を開始する**」などのアクションを選択します。

## <a name="suggested-weekly-tasks"></a>推奨される毎週のタスク

少なくとも週単位で行うべき重要なセキュリティ タスクの推奨事項を次に示します。

- [Microsoft セキュア スコアを監視して改善します](#monitor-and-improve-your-microsoft-secure-score)。
- [デバイスのセキュア スコアを確認します](#review-the-secure-score-for-devices)。
- [デバイスのセキュリティ スコアを向上させます](#improve-your-secure-score-for-devices)。

### <a name="monitor-and-improve-your-microsoft-secure-score"></a>Microsoft セキュア スコアを監視して改善する

Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほど改善のための処置の実行数が減少したことを示しています。

セキュア スコアは、次のような方法で組織に役立ちます。

- 組織のセキュリティ体制の現在の状態について報告します。
- 検出可能性、可視性、ガイダンス、制御機能を提供して、セキュリティ体制を改善します。
- ベンチマークと比較し、主要業績評価指標 (KPI) を確立します。

1. セキュリティ スコアを確認するには、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のナビゲーション ウィンドウで、**[セキュア スコア]** を選択します。 

2. Microsoft のセキュア スコア全体を向上させるために、修復と改善のための措置に関する確認と決定を行います。

### <a name="review-the-secure-score-for-devices"></a>デバイスのセキュア スコアを確認する

脆弱性管理ダッシュボードにも、デバイス カードの Microsoft セキュア スコアがあります。 このカードには現在のスコアが表示され、スコアが高いほど、エンドポイントのサイバー攻撃への耐障害性が高いことを示します。 これは、すべてのデバイスのセキュリティ状態をまとめて反映します。

このカードのデータは、几帳面で継続的な脆弱性検出プロセスの結果です。 これは、継続的に次の構成検出評価で集計されます。

- 収集された構成を収集されたベンチマークと比較して、正しく構成されていない資産を検出する
- 修復可能、または部分的に修復できる脆弱性に構成をマップする (リスク削減)
- ベスト プラクティスの構成ベンチマーク (ベンダー、セキュリティ フィード、内部調査チーム) を収集して管理する
- すべての資産からセキュリティ制御構成状態の変更点を収集して監視する

### <a name="improve-your-secure-score-for-devices"></a>デバイスのセキュリティ スコアを向上させる

セキュリティに関する推奨事項の一覧を使用して問題を修復することで、セキュリティ構成を改善します。 そうすることで、デバイスの Microsoft セキュア スコアが向上し、組織は今後のサイバーセキュリティの脅威や脆弱性への耐障害性を高めます。 スコアを確認して向上させるのに必要な時間は常に価値があります。

1. セキュリティ スコアを確認するには、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のナビゲーション ウィンドウで、**[セキュア スコア]** を選択します。

2. Defender 脆弱性管理ダッシュボードのデバイス カード向け **Microsoft セキュア スコア** で、カテゴリーの 1 つを選択します。 そのカテゴリに関連する推奨事項の一覧が、推奨事項と合わせて表示されます。

3. 一覧で項目を選択すると、推奨事項に関連する詳細が表示されます。

4. **[修復オプション]** を選択します。

5. 説明を読んで、問題のコンテキストと次に実行する操作を理解します。 期限を選択し、メモを追加し、[すべての修復アクティビティ データを CSV にエクスポートする] を選択して、フォローアップのためにメールに添付できるようにします。 修復タスクが作成されたことを示す確認メッセージが表示されます。

6. IT 管理者にフォローアップ メールを送信し、修復を割り当てた時間がシステムに反映されるようにします。

7. ダッシュボードで [デバイスの Microsoft セキュア スコア] カードに戻ります。 アクションの結果として、セキュリティ制御に関する推奨事項の数が減少しました。

8. **[セキュリティ制御]** を選択して、[セキュリティの推奨事項] ページに戻ります。 アドレス指定した項目が表示されなくなったため、Microsoft のセキュア スコアが向上します。

## <a name="suggested-monthly-tasks"></a>推奨される毎月のタスク

これらのタスクは、少なくとも月単位で実行する必要があります (頻度が低い場合)。 

- [レポートを実行します](#run-reports)。
- [シミュレーション チュートリアルを実行します](#run-a-simulation-tutorial)。
- [ラーニング ハブを探索します](#explore-the-learning-hub)。

### <a name="run-reports"></a>レポートを実行する

複数のレポートが、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で利用できます。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) の左側のナビゲーション ウィンドウで、**[レポート]** を選択します。

2. レポートを選択して確認します。 各レポートには、そのレポートに関連するカテゴリが多数表示されます。

3. **[詳細の表示]** を選択すると、各カテゴリの詳細情報が表示されます。

4. 特定の脅威のタイトルを選択して、その脅威特有の詳細を表示します。

### <a name="run-a-simulation-tutorial"></a>シミュレーション チュートリアルの実行

トレーニングを通じて、お客様とチームのセキュリティ準備を強化することをお勧めします。 Microsoft 365 Defender ポータルでシミュレーション チュートリアルにアクセスできます。 このチュートリアルでは、いくつかの種類のサイバー脅威について説明します。 

次の手順をお試しください。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のナビゲーション ウィンドウで、**[チュートリアル]** を選択します。

2. 実行したいチュートリアルのチュートリアルを読み、ファイルをダウンロードするか、指示に従ってシミュレーションを実行するために必要なスクリプトをコピーします。

### <a name="explore-the-learning-hub"></a>ラーニング ハブを調べる

ラーニング ハブには、そこに存在する脅威の多くとその対処方法に関する知識を高めることができるさまざまな領域があります。 お客様とチームは、特に Microsoft 365 Defender とエンドポイント セクションで提供されるリソースを時間をかけて調べることをお勧めします。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のナビゲーション ウィンドウで、**[ラーニング ハブ]** を選択します。

2. **Microsoft 365 Defender** や **エンドポイント** などの領域を選択します。

3. アイテムを選択して、各概念の詳細を確認します。 

> [!NOTE]
> ラーニング ハブの一部のリソースでは、実際には Microsoft 365 Business Premium に含まれていない機能がある場合があります。 たとえば、高度な追求機能は、Defender for Endpoint Plan 2 や Microsoft 365 Defender などのエンタープライズ サブスクリプションに含まれますが、Microsoft 365 Business Premium には含まれません。 [中小企業向けの Microsoft 365 プランのセキュリティ機能を比較します](../security/defender-business/compare-mdb-m365-plans.md)。

## <a name="as-needed"></a>必要に応じて

必要に応じて、次のタスクを実行します。

- [[脅威の分析] ダッシュボードを使用します](#use-the-threat-analytics-dashboard)。
- [スキャンまたは調査を実行します](#run-a-scan-or-automated-investigation)。
- [アイテムを修復します](#remediate-an-item)。

### <a name="use-the-threat-analytics-dashboard"></a>[脅威の分析] ダッシュボードの使用

[脅威の分析] ダッシュボードを使用して、組織に最も関連性の高いレポートを強調表示することで、現在の脅威の全体的な概要を確認します。 

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のナビゲーション ウィンドウで **[脅威分析]** を選択し、脅威分析ダッシュボードを表示します。 

   ダッシュボードは、脅威を次のセクションにまとめます。

   - 最新の脅威 - 最近発行されたか、更新された脅威レポートに合わせて、アクティブなアラートと解決済みアラートの数を一覧表示します。
   - インパクトのある脅威 - 組織に最も影響を与える脅威を一覧表示します。 このセクションでは、最初にアクティブなアラートと解決済みアラートの数が最も多い脅威の一覧を示します。
   - 最も露出度が高い - 最初に最も露出レベルが高い脅威を一覧表示します。 脅威の露出レベルは、脅威に関連する脆弱性の深刻さと、組織内のこれらの脆弱性によって悪用される可能性があるデバイスの数という 2 つの情報を使用して計算されます。

2. 調査対象のタイトルを選択し、関連するレポートを読みます。 

3. 詳細については、アナリスト レポート全体を確認するか、他の見出しを選択して、関連するインシデント、影響を受けた資産、露出と軽減策を表示することもできます。

### <a name="remediate-an-item"></a>アイテムを修復する

Microsoft 365 Business Premium には、いくつかの修復アクションがあります。 これらのアクションには、手動応答アクション、自動調査後のアクション、ライブ応答アクションが含まれます。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のナビゲーション ウィンドウで、**[デバイス インベントリ]** を選択します。

   :::image type="content" source="./../media/defender-business/mdb-deviceinventory.png" alt-text="デバイス インベントリのスクリーンショット":::

2. リスク レベルが高いデバイスや露出レベルの高いデバイスを選択します。 ポップアップ ウィンドウが開き、次の画像に示すように、そのアイテムに対して生成されたアラートとインシデントに関する詳細情報が表示されます。  

   :::image type="content" source="./../media/defender-business/mdb-deviceinventory-selecteddeviceflyout.png" alt-text="選択したデバイスのポップアップ ウィンドウのスクリーンショット":::

3. ポップアップで、表示される情報を確認します。 次の画像に示すように、省略記号 (...) を選択して、使用可能なアクションを一覧表示するメニューを開きます。 

   :::image type="content" source="./../media/defender-business/mdb-deviceinventory-selecteddeviceflyout-menu.png" alt-text="選択したデバイスで使用可能なアクションのスクリーンショット":::

4. 使用可能なアクションを選択します。 たとえば、**[ウイルス対策スキャンを実行する]** を選択すると、Microsoft Defender ウイルス対策によってデバイスでクイック スキャンが開始されます。 または、**[自動調査の開始]** を選択して、デバイスの自動調査をトリガーすることもできます。

#### <a name="remediation-actions-in-microsoft-365-business-premium"></a>Microsoft 365 Business Premium の修復アクション

次の表は、Microsoft 365 Business Premium で使用可能な修復のための措置をまとめたものです。

| ソース  | Actions  |
|---------|---------|
| 自動化された調査      | - ファイルの検疫 <br/>- レジストリ キーの削除 <br/>- プロセスの強制終了 <br/>- サービスの停止 <br/>- ドライバーの無効化 <br/>- スケジュールされたタスクの実行        |
| 手動応答アクション   | - ウイルス対策スキャンの実行 <br/>- デバイスの分離 <br/>- 停止と検疫 <br/>- ファイルをブロックまたは許可するインジケーターの追加       |
| ライブ応答  | - フォレンジック データの収集 <br/>- ファイルの分析 <br/>- スクリプトの実行 <br/>- 不審なエンティティを分析のために Microsoft に送信 <br/>- ファイルの修復 <br/>- 脅威の積極的な追求  |




## <a name="see-also"></a>関連項目

[ビジネス プランの Microsoft 365 をセキュリティで保護するためのベスト プラクティス](../admin/security-and-compliance/secure-your-business-data.md)