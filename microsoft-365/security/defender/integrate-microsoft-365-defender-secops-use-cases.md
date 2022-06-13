---
title: 手順 5.  ユース ケースの開発とテスト
description: Microsoft 365 Defenderをセキュリティ操作に統合する場合のユース ケースの開発とテストの基本。
keywords: インシデント, アラート, 調査, 相関関係, 攻撃, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, Microsoft, m365, インシデント対応, サイバー攻撃, secops, セキュリティ操作, soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-m365dsecops
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: a039239545a5442592fe1a07f840cf75bebb0eca
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66012948"
---
# <a name="step-5-develop-and-test-use-cases"></a>手順 5.  ユース ケースの開発とテスト

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Security Operations Center (SOC) にMicrosoft 365 Defenderをデプロイするために推奨される方法は、SOC チームの現在のツール、プロセス、スキルセットのセットによって異なります。 何百ものセキュリティ ソースではないにしても、数十個から大量のデータが送信されるため、プラットフォーム間でサイバー検疫を維持することは困難な場合があります。

セキュリティ ツールは相互に関連しています。 セキュリティ テクノロジで 1 つの機能を有効にするか、プロセスを変更すると、別の機能が中断される可能性があります。 このため、MICROSOFT では、SOC チームがユース ケースを定義して優先順位を付ける方法を形式化することをお勧めします。 ユース ケースは、さまざまなチーム間で SOC 操作の要件とテスト プロセスを定義するのに役立ちます。 メトリックをキャプチャするための手法を作成し、適切なロールとタスクの組み合わせが適切なチームと適切なスキルセットに合っているかどうかを判断します。

## <a name="develop-and-formalize-use-case-process"></a>ユース ケース プロセスの開発と形式化

SOC は、SOC 監視チームによって規制されるユース ケースを開発するための高レベルの標準とプロセスを定義する必要があります。 SOC 監視チームは、最終的に SOC チームの Runbook とプレイブックに入る SOC のユース ケースに優先順位を付けるために、ビジネス、IT、法的、人事、その他のグループと協力する必要があります。 ユース ケースの優先順位は、コンプライアンスやプライバシーなどの目的に基づいています。

ユース ケースの開発に関連する SOC 監視アクティビティは次のとおりです。

- 要件
- スタッフまたはトレーニングのニーズ
- ソフトウェア ライセンス
- ベンダーの契約
- プランの管理
- ユース ケース レジストリの保守
- テンプレートの保守/更新

Runbook とプレイブックの作成プロセスを容易にするには、ユース ケースデシジョン ツリーを作成します。 この図は例を示しています。

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/use-case-decision-process.png" alt-text="ユース ケースの決定プロセス" lightbox="../../media/integrate-microsoft-365-defender-secops/use-case-decision-process.png":::

高レベルのユース ケース標準が定義され、承認されたら、次の手順では実際のユース ケースを作成してテストします。 次のセクションでは、フィッシング対策と脅威と脆弱性スキャンのシナリオを例として使用します。

## <a name="use-case-example-1-new-phishing-variant"></a>ユース ケースの例 1: 新しいフィッシングバリアント

ユース ケースを作成する最初の手順は、ストーリー ボードを使用してワークフローの概要を説明することです。 脅威インテリジェンス チームに対する新しいフィッシング悪用通知の概要を示すストーリー ボードの例を次に示します。

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-phishing.png" alt-text="フィッシング詐欺対策キャンペーンのユース ケースのワークフロー" lightbox="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-phishing.png":::

### <a name="invoke-the-use-case-workflow-for-example-1"></a>ユース ケース ワークフローの呼び出し (例 1)

ストーリー ボードが承認されたら、次の手順ではユース ケース ワークフローを呼び出します。 フィッシング対策キャンペーンのプロセスの例を次に示します。

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-phishing.png" alt-text="フィッシング詐欺対策キャンペーンの詳細なユース ケース ワークフロー" lightbox="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-phishing.png":::

## <a name="use-case-example-2-threat-and-vulnerability-scanning"></a>ユース ケースの例 2: 脅威と脆弱性のスキャン

ユース ケースを使用できるもう 1 つのシナリオは、脅威と脆弱性のスキャンです。 この例では、SOC では、資産のスキャンを含む承認されたプロセスを使用して、資産に対する脅威と脆弱性を修復する必要があります。

アセットの脅威と脆弱性の管理の高レベルストーリーボードの例を次に示します。

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-tvm.png" alt-text="脅威と脆弱性の管理のユース ケース ワークフロー" lightbox="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-tvm.png":::

### <a name="invoke-the-use-case-workflow-for-example-2"></a>ユース ケース ワークフローの呼び出し (例 2)

脅威と脆弱性のスキャンのプロセスの例を次に示します。

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-tvm.png" alt-text="脅威と脆弱性の管理の詳細なユース ケース ワークフロー" lightbox="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-tvm.png":::

### <a name="analyze-the-use-case-output-and-lessons-learned"></a>ユース ケースの出力と学習した教訓を分析する

ユース ケースが承認され、テストされた後、セキュリティ チーム間のギャップと、関連する人、プロセス、およびMicrosoft 365 Defenderテクノロジを特定する必要があります。 Microsoft 365 Defenderテクノロジを分析して、目的の成果を達成できるかどうかを判断する必要があります。 これらは、チェックリストまたはマトリックスを使用して追跡できます。

たとえば、フィッシング対策シナリオの例では、SOC チームがこの表で検出した可能性があります。

|SOC チーム|要件|要件を満たすユーザー|要件を満たすプロセス|関連するテクノロジ|識別されたギャップ|ユース ケース変更ログ|除外 (Y/N)|
|---|---|---|---|---|---|---|---|
|脅威インテリジェンスと分析チーム|データ ソースは、脅威インテリジェンス エンジンに適切に供給されています。|脅威インテリジェンス アナリスト/エンジニア|データ フィードの要件が確立され、承認されたソースから脅威インテリジェンスがトリガーされる|Microsoft Defender for Identity、Microsoft Defender for Endpoint|脅威インテリジェンス チームは、自動化スクリプトを使用してMicrosoft 365 Defender API と脅威 Intel エンジンをリンクしませんでした|脅威エンジンにデータ ソースとしてMicrosoft 365 Defenderを追加する <p> ユース ケース実行ブックを更新する|N|
|監視チーム|データ ソースが監視ダッシュボードに適切にフィードされている|階層 1,2 SOC アナリスト – & アラートの監視|セキュリティ & コンプライアンス センターのセキュリティ スコアを報告するためのワークフロー|[セキュリティ & コンプライアンス センターのアラート](/microsoft-365/security/office-365-security/alerts) <p> セキュア スコアの監視|SOC アナリストが、セキュリティスコアを向上させるための新しいフィッシングバリアント検出の成功を報告するメカニズムがない <p> [Microsoft 365 Defender ポータルで電子メール セキュリティ レポートを表示する](/microsoft-365/security/office-365-security/view-email-security-reports)|Reporting ワークフローにセキュリティスコアの改善を追跡するプロセスを追加する|N|
|エンジニアリングチームと SecOps チーム|変更制御の更新は、SOC チーム Runbook で行われます|Tier 2 SOC エンジニア|SOC チーム Runbook の変更制御通知手順|セキュリティ デバイスに対する承認済みの変更|SOC セキュリティ テクノロジへのMicrosoft 365 Defender接続を変更するには、承認が必要です|MICROSOFT DEFENDER FOR CLOUD APPS、Defender for Identity、Defender for Endpoint、Security & Compliance Center を SOC Runbook に追加する|Y|

さらに、SOC チームは、上で説明した脅威と脆弱性の管理シナリオに関して、次の表に示す発見を行った可能性があります。

|SOC チーム|要件|要件を満たすユーザー|要件を満たすプロセス|関連するテクノロジ|識別されたギャップ|ユース ケース変更ログ|除外 (Y/N)|
|---|---|---|---|---|---|---|---|
|SOC 監視|承認済みネットワークに接続されているすべての資産が識別され、分類されます|SOC 監視、BU 所有者、アプリケーション所有者、IT 資産所有者など。|リスクに基づいて資産のカテゴリと属性を検出して一覧表示する一元化された資産管理システム。|ServiceNow またはその他の資産。 <br><br>[デバイス インベントリのMicrosoft 365](/microsoft-365/security/defender-endpoint/device-discovery)|検出された資産の割合は 70% のみです。 既知の資産に対してのみ有効な修復追跡Microsoft 365 Defender|Microsoft 365 Defenderに 100% のカバレッジを確保するための成熟した資産ライフサイクル管理サービス|N|
|エンジニアリング & SecOps Teams|資産の高い影響と重大な脆弱性は、ポリシーに従って修復されます|SecOps エンジニア、SOC アナリスト: 脆弱性&コンプライアンス、セキュリティ エンジニアリング|高リスクおよび重大な脆弱性を分類するための定義済みプロセス|[脅威と脆弱性の管理ダッシュボード](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)|Defender for Endpoint は、Microsoft 推奨アクティビティの修復計画または実装なしで、影響が大きく、アラートが高いデバイスを特定しました|ポリシーごとに 30 日以内に修復アクティビティが必要な場合に、資産所有者に通知するワークフローを追加します。チケット発行システムを実装して、修復手順を資産所有者に通知します。|N|
|監視Teams|脅威と脆弱性の状態は、会社のイントラネット ポータルを介して報告されます|階層 2 SOC アナリスト|資産の修復の進行状況を示すMicrosoft 365 Defenderから自動生成されたレポート|[セキュリティ & コンプライアンス センターのアラート](/microsoft-365/security/office-365-security/alerts) <p> セキュア スコアの監視|資産の脅威と脆弱性の状態に関して、ビューまたはダッシュボード レポートが資産所有者に伝達されません。|組織に対するリスクの高い重大な資産の脆弱性修復の状態を設定する自動化スクリプトを作成します。|N|

これらのユース ケースの例では、テストでは、SOC チームの要件に、各チームの責任のベースラインとして確立されたいくつかのギャップが明らかにされました。 ユース ケースチェックリストは、SOC チームが新しいまたは既存の SOC 要件とのMicrosoft 365 Defender統合に備えるために、必要に応じて包括的にすることができます。 これは反復的なプロセスであるため、ユース ケース開発プロセスとユース ケース出力コンテンツは、学習した教訓を得て SOC の Runbook を自然に更新し、成熟させるのに役立ちます。

## <a name="update-production-runbooks-and-playbooks"></a>運用 Runbook とプレイブックを更新する

すべてのギャップに対してユース ケース テストが修復されると、その中で収集された教訓とメトリックを、SOC チームの運用 Runbook (運用プロセス) とプレイブック (インシデント対応とエスカレーション手順) に組み込むことができます。

SOC チーム Runbook とプレイブックのメンテナンスは、さまざまな方法で整理できます。 各 SOC チームが独自の責任を負う場合や、すべてのチームが中央リポジトリで共有するための単一の一元化されたバージョンがある場合があります。 個々の組織の Runbook とプレイブックの管理は、サイズ、スキルセット、役割、職務の分離に基づいています。 Runbook が更新されたら、プレイブックの更新プロセスに従う必要があります。

## <a name="use-a-standard-framework-for-escalation"></a>エスカレーションに標準フレームワークを使用する

Playbooks は、ユース ケースの正常な統合とテストに基づいて、SOC チームが実際のイベントが発生したときに従う必要がある手順です。 そのため、SOC は、インシデント対応の主要な業界標準の 1 つである [NIST インシデント対応標準](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf) など、インシデント対応に対する正式なアプローチに従う必要があります。

NIST の 4 段階のインシデント対応プロセスには、次の 4 つのフェーズがあります。

1. 準備
2. 検出と分析
3. コンテインメント、根絶、および回復
4. インシデント後のアクティビティ

### <a name="example-tracking-preparation-phase-activity"></a>例: 準備フェーズアクティビティの追跡

エスカレーション プレイブックの中核となる基盤の 1 つは、各 SOC チームがイベントやインシデントの前、中、後に行うべきことについてあいまいさを少なくすることです。 そのため、ステップ バイ ステップの手順を一覧表示することをお勧めします。

たとえば、準備フェーズには、タスクの if/then または XoR マトリックスを含める場合があります。 新しいフィッシングバリアントのユース ケースの例では、このようなマトリックスは次のようになります。

|エスカレーションが保証される理由|次のステップ|
|---|---|
|**500/時間**>**重大な** トリガーとして評価された SOC 監視のアラート|Playbook A、セクション 2、アクティビティ 5 に移動します (プレイブック セクションへのリンクあり)|
|eCommerce で DDoS 攻撃の可能性が報告されました|Playbook B セクション C、アクティビティ 19 を呼び出す (プレイブック セクションへのリンクあり)|
|エグゼクティブが不審なメールをスピア フィッシングの試みとして報告しました|Playbook 5、セクション 2、アクティビティ 5 に移動します (プレイブック セクションへのリンクあり)|

準備フェーズを実行した後、組織は NIST で概説されているように残りのフェーズを呼び出す必要があります。

- 検出と分析
- コンテインメント、根絶、および回復
- インシデント後のアクティビティ

## <a name="next-step"></a>次のステップ

[手順 6.SOC メンテナンス タスクを特定する](integrate-microsoft-365-defender-secops-tasks.md)
