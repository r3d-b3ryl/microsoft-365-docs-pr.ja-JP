---
title: 手順 5.  使用例の開発とテスト
description: セキュリティ操作に統合する際の使用例の開発とテストMicrosoft 365 Defender基本。
keywords: インシデント、アラート、調査、相関関係、攻撃、デバイス、ユーザー、ID、ID、メールボックス、メール、365、microsoft、m365、インシデント対応、サイバー攻撃、secops、セキュリティ操作、soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 79a5b1ea36e6a18d880d7fec7681f826cacac48f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60158984"
---
# <a name="step-5-develop-and-test-use-cases"></a>手順 5.  使用例の開発とテスト

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

セキュリティ 運用センター (SOC) に Microsoft 365 Defenderを展開する推奨される方法は、SOC チームの現在のツール、プロセス、およびスキルセットによって異なっています。 何百ものセキュリティ ソースではないにしろ、数十から大量のデータが収集されるので、プラットフォーム全体でサイバー衛生を維持するには困難な場合があります。 

セキュリティ ツールは相互に関連しています。 セキュリティ テクノロジで 1 つの機能を有効にしたり、プロセスを変更したりすると、別の機能が壊れる可能性があります。 このため、SOC チームは、使用例を定義および優先順位付けするためのメソッドを形式化する必要があります。 使用例は、さまざまなチームで SOC 操作の要件とテスト プロセスを定義するのに役立ちます。 適切な役割とタスクの組み合わせが適切なスキルセットを持つ適切なチームに揃っているかどうかを判断するために、メトリックをキャプチャするための方法論を作成します。 

## <a name="develop-and-formalize-use-case-process"></a>使用例プロセスの開発と形式化

SOC は、SOC Oversight チームによって規制される、使用例を開発するための高レベルの標準とプロセスを定義する必要があります。 SOC Oversight チームは、ビジネス、IT、法務、人事などのグループと一緒に作業し、最終的に SOC チームの Runbook やプレイブックに入る SOC の使用例に優先順位を付ける必要があります。 使用例の優先順位は、コンプライアンスやプライバシーなどの目的に基づいて行います。

使用例の開発に関連する SOC 監視アクティビティには、次のものが含まれます。 

- 要件
- スタッフまたはトレーニングのニーズ
- ソフトウェア ライセンス
- ベンダー契約
- 計画の管理
- 使用例レジストリの維持
- テンプレートの保守および更新

Runbook とプレイブックの作成プロセスを容易にするために、使用例の決定ツリーを作成します。 次の図は、例を示しています。

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/use-case-decision-process.png" alt-text="使用例の決定プロセス。":::

高レベルの使用例の標準が定義され、承認されると、次に実際の使用例を作成してテストします。 次のセクションでは、フィッシング対策と脅威と脆弱性スキャンのシナリオを例として使用します。

## <a name="use-case-example-1-new-phishing-variant"></a>使用例 1: 新しいフィッシングバリアント

使用例を作成する最初の手順は、ストーリー ボードを使用してワークフローの概要を説明します。 脅威インテリジェンス チームへの新しいフィッシング攻撃通知のハイレベル ストーリー ボードの例を次に示します。
 
:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-phishing.png" alt-text="フィッシング対策キャンペーンの使用例ワークフロー。":::

### <a name="invoke-the-use-case-workflow-for-example-1"></a>使用例のワークフロー (例 1) を呼び出す

ストーリー ボードが承認されると、次に、使用例ワークフローを呼び出します。 フィッシング対策キャンペーンのプロセス例を次に示します。 
 
:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-phishing.png" alt-text="フィッシング対策キャンペーンの詳細な使用例のワークフローの例。":::

## <a name="use-case-example-2-threat-and-vulnerability-scanning"></a>使用例 2: 脅威と脆弱性のスキャン

使用例を使用できるもう 1 つのシナリオは、脅威と脆弱性のスキャンです。 この例では、SOC では、資産のスキャンを含む承認されたプロセスを介して、資産に対する脅威と脆弱性を修復する必要があります。 

アセットの種類に関する概要ストーリーボード脅威と脆弱性の管理次に示します。
 
:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-tvm.png" alt-text="ユーザーの使用例のワークフロー脅威と脆弱性の管理。":::

### <a name="invoke-the-use-case-workflow-for-example-2"></a>使用例のワークフロー (例 2) を呼び出す

脅威と脆弱性のスキャンのプロセスの例を次に示します。
 
:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-tvm.png" alt-text="ユーザーの詳細な使用例のワークフローの脅威と脆弱性の管理。":::
 
### <a name="analyze-the-use-case-output-and-lessons-learned"></a>使用例の出力と学習した教訓を分析する

使用例が承認およびテストされた後、セキュリティ チーム間のギャップを、人、プロセス、および関連するMicrosoft 365 Defenderする必要があります。 Microsoft 365 Defenderテクノロジを分析して、望ましい結果を達成できるかを判断する必要があります。 チェックリストまたはマトリックスを使用して追跡できます。 

たとえば、フィッシング対策のシナリオの例では、SOC チームが次の表で検出を行った可能性があります。


| SOC チーム | 要件 | 要件を満たすユーザー | 要件を満たすプロセス | 関連するテクノロジ | 識別されるギャップ | 使用例の変更ログ | 除外 (Y/N) |
|:-------|:-----|:-------|:-------|:-------|:-----|:-------|:-------|
| 脅威インテリジェンスと分析チーム | データ ソースが脅威インテリジェンス エンジンに適切に供給されています。 | 脅威インテリジェンス アナリスト/エンジニア | データ フィードの要件が確立され、承認済みソースからの脅威インテリジェンス トリガー | Microsoft Defender for Identity, Microsoft Defender for Endpoint | 脅威インテリジェンス チームは、オートメーション スクリプトを使用して API Microsoft 365 Defenderインテル エンジンにリンクしなかった | 脅威Microsoft 365 Defenderにデータ ソースとして追加する <BR> <BR> 使用例の実行ブックを更新する | × |
| 監視チーム | データ ソースが監視ダッシュボードに適切にフィードされている | Tier 1,2 SOC Analyst-Monitoring &アラート | コンプライアンス センターのセキュリティ スコア&レポートのワークフロー | [セキュリティ コンプライアンス センター&アラート](/microsoft-365/security/office-365-security/alerts)  <br><br> セキュリティで保護されたスコアの監視  | SOC アナリストが新しいフィッシング バリアント検出の成功を報告してセキュリティで保護されたスコアを向上させるメカニズムはありません <br><br> [セキュリティ コンプライアンス センター&レポート](/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance)| レポート ワークフローにセキュリティスコアの改善を追跡するためのプロセスを追加する | × | 
| エンジニアリングチームと SecOps チーム | 変更コントロールの更新は、SOC チームの runbook で行います。 | Tier 2 SOC エンジニア | SOC チームの Runbook のコントロール通知手順を変更する | セキュリティ デバイスに対する承認済みの変更 | SOC セキュリティ テクノロジMicrosoft 365 Defenderの変更には承認が必要です | SOC runbook にMicrosoft Cloud App Security、Defender for Identity、Defender for Endpoint、Security & コンプライアンス センターを追加する | Y |
|||||||||

さらに、SOC チームは、上記のシナリオに関して、以下の表に示す脅威と脆弱性の管理を行う可能性があります。

| SOC チーム | 要件 | 要件を満たすユーザー | 要件を満たすプロセス | 関連するテクノロジ | 識別されるギャップ | 使用例の変更ログ | 除外 (Y/N) |
|:-------|:-----|:-------|:-------|:-------|:-----|:-------|:-------|
| SOC の監視 | 承認済みネットワークに接続されているすべてのアセットが識別され、分類されます。 | SOC 監視、BU 所有者、アプリケーション所有者、IT 資産所有者など | リスクに基づいて資産カテゴリと属性を検出および一覧表示する一元的な資産管理システム。 | ServiceNow または他のアセット。 <br><br>[Microsoft 365デバイス インベントリ](/security/defender-endpoint/device-discovery) | 資産の 70% だけが検出されました。 Microsoft 365 Defender既知の資産にのみ有効な修復追跡 | 資産ライフサイクル管理サービスを成熟し、Microsoft 365 Defender 100% のカバレッジを確保する | × |
| エンジニアリング & SecOps Teams | アセットの影響が大きく、重大な脆弱性はポリシーに従って修復されます | SecOps のエンジニア、SOC アナリスト: コンプライアンス&セキュリティ エンジニアリングの脆弱性 | 高リスクと重大な脆弱性を分類する定義されたプロセス | [脅威と脆弱性の管理ダッシュボード](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | Defender for Endpoint は、Microsoft 推奨アクティビティの修復計画や実装を行う必要がない、影響が大きく、アラートの高いデバイスを特定しました | ポリシーごとに 30 日以内に修復アクティビティが必要な場合にアセット所有者に通知するためのワークフローを追加します。資産所有者に修復手順を通知するチケット システムを実装します。 | × |
| 監視Teams | 脅威と脆弱性の状態は、会社のイントラネット ポータルを介して報告されます | Tier 2 SOC アナリスト | アセットの修復の進行状況をMicrosoft 365 Defenderから自動生成されたレポート | [セキュリティ コンプライアンス センター&アラート](/microsoft-365/security/office-365-security/alerts) <br><br> セキュリティで保護されたスコアの監視 | アセットの脅威と脆弱性の状態に関するビューまたはダッシュボード レポートがアセット所有者に伝達されません。 | 自動化スクリプトを作成して、リスクの高い重要な資産脆弱性の修復の状態を組織に設定します。 | × |
|||||||||

次の使用例では、テストでは、各チームの責任の基準として確立された SOC チームの要件にいくつかのギャップが見えました。 使用例のチェックリストは、SOC チームが新しい SOC 要件または既存の SOC 要件との統合Microsoft 365 Defenderに備えた包括的なチェックリストです。 これは反復的なプロセスなので、使用例の開発プロセスと使用例の出力コンテンツは、学習したレッスンで SOC の runbook を更新および成熟する際に自然に役立つでしょう。

## <a name="update-production-runbooks-and-playbooks"></a>実稼働の Runbook とプレイブックを更新する

すべてのギャップに対する使用例のテストが修復された後、学習した教訓と、その中で収集された指標を、SOC チームの運用運用手順 (運用プロセス) およびプレイブック (インシデント対応とエスカレーション手順) に組み込む必要があります。 

SOC チームの Runbook とプレイブックのメンテナンスは、さまざまな方法で整理できます。 各 SOC チームが独自の責任を負う場合や、すべてのチームが中央リポジトリで共有する 1 つの一元化されたバージョンがある場合があります。 個々の組織の Runbook とプレイブックの管理は、サイズ、スキルセット、役割、および職務の分離に基づいて行います。 Runbook が更新された後は、プレイブックの更新プロセスに従う必要があります。 

## <a name="use-a-standard-framework-for-escalation"></a>エスカレーションに標準フレームワークを使用する

プレイブックは、実際のイベントが発生した場合に SOC チームが実行する必要がある手順です。この手順は、成功した統合と使用例のテストに基づいて行われます。 したがって、SOC はインシデント対応の主要な業界標準の 1 つになった [NIST](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf) インシデント対応標準など、インシデント対応に対する正式なアプローチに従う必要があります。

NIST の 4 つの手順インシデント対応プロセスには、次の 4 つのフェーズが含まれます。

1.  準備
2.  検出と分析
3.  コンテインメント、根絶、および回復
4.  インシデント後のアクティビティ

### <a name="example-tracking-preparation-phase-activity"></a>例: 準備フェーズのアクティビティの追跡

エスカレーション プレイブックの主要な基盤の 1 つは、各 SOC チームがイベントまたはインシデントの前、中、および後に行う必要があるものに関するあいまいさはほとんどない点です。 したがって、手順を示す手順を示すのが良い方法です。 

たとえば、準備フェーズには、if/then または XoR マトリックスのタスクが含まれる場合があります。 新しいフィッシングバリアントの使用例の場合、このようなマトリックスは次のようになります。

| エスカレーションが保証される理由 | 次のステップ |
|:-------|:-----|
| **500** 時間にクリティカルトリガーされたと評価された SOC 監視>アラート | [Playbook A, Section 2, Activity 5] ([プレイブック] セクションへのリンク付き) に移動します。 |
| eCommerce が潜在的な DDoS 攻撃を報告しました | Playbook B-Section C, Activity 19 を呼び出す (playbook セクションへのリンク付き) |
| エグゼクティブが不審なメールをスピアフィッシングの試みとして報告しました | [Playbook 5, Section 2, Activity 5] (Playbook セクションへのリンク付き) に移動します。 |
|||

準備フェーズを実行した後、組織は NIST で概説されている残りのフェーズを呼び出す必要があります。

- 検出と分析
- コンテインメント、根絶、および回復
- インシデント後のアクティビティ 

## <a name="next-step"></a>次の手順

[手順 6.SOC のメンテナンス タスクを特定する](integrate-microsoft-365-defender-secops-tasks.md)

