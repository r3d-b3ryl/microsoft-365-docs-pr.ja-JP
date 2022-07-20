---
title: Microsoft Purview コンプライアンス マネージャーの新機能
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: コンプライアンス マネージャーの新機能と、次の内容を確認します。 更新された評価、新しい評価テンプレート、新しいアクションなどについて説明します。
ms.openlocfilehash: be6527822798a518753897b5d104899077264ee3
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2022
ms.locfileid: "66894341"
---
# <a name="whats-new-in-microsoft-purview-compliance-manager"></a>Microsoft Purview コンプライアンス マネージャーの新機能

**この記事では、次の操作を行います。** コンプライアンス マネージャーの最近の更新プログラムについて説明します。

## <a name="july-2022"></a>2022 年 7 月

コンプライアンス マネージャーは、次の新しい評価テンプレートを公開しました。

- 香港 - 銀行業務コードと支払いカード

[評価テンプレートの完全な一覧を表示します](compliance-manager-templates-list.md)。


## <a name="may-2022"></a>2022 年 5 月

コンプライアンス マネージャーは、次の新しい評価テンプレートを公開しました。

ヨーロッパ、中東、アフリカ (EMEA)
- カタール国民情報保証 (NIA)
- アラブ首長国連邦データプライバシー法

米国政府機関コミュニティ (GCC) 中規模、GCC High、および国防総省 (DoD) のお客様は、これらのテンプレートが今後数週間で利用可能になるはずです。

[評価テンプレートの完全な一覧を表示します](compliance-manager-templates-list.md)。

## <a name="march-2022"></a>2022 年 3 月

### <a name="new-templates-available"></a>使用可能な新しいテンプレート

コンプライアンス マネージャーは、次の新しい評価テンプレートを公開しました。

**Global**
- ISO 37301
- NIST 800-207 - ゼロ トラスト アーキテクチャ
- SIG 2022

**米国政府機関**
- CMMC v2 レベル 1
- CMMC v2 レベル 2

**北アメリカ**
- 情報セキュリティ管理法 - カリフォルニア州の英国コロンビア州

[評価テンプレートの完全な一覧を表示します](compliance-manager-templates-list.md)。

### <a name="continuous-compliance-assessment-of-improvement-actions"></a>改善アクションの継続的なコンプライアンス評価

以前はセキュリティスコアでカバーされていなかったコンプライアンス マネージャーで、35 を超える改善アクションに対する自動テストと証拠生成を追加しています。 継続的なコンプライアンス評価を使用すると、コンプライアンス評価に関連していて、関連するソリューションにアクセスするライセンスがある場合に、完了したこれらの改善アクションの更新を受け取ることができます。 継続的なコンプライアンス評価では、改善アクションのスコアリング ロジックをユーザーに可視化し、特定のスコアを受け取った理由に関する分析情報と証拠も提供します。 この機能は、Microsoft 365 Secure Score との既存の統合と共に機能し、以前に構成した自動アクションは引き続きそのまま機能します。 [自動テスト設定](compliance-manager-setup.md#set-up-automated-testing)の詳細については、こちらを参照してください。

## <a name="february-2022"></a>2022 年 2 月

### <a name="alerts-and-alert-policies"></a>アラートとアラート ポリシー

ユーザーは、組織が追跡するコンプライアンス マネージャーの変更に対するアラートを設定できるようになりました。簡単なセットアップ ウィザードを使用すると、改善アクション スコアの変更、改善アクションの割り当ての変更、改善アクションのテストまたは実装状態の変更、改善アクションの [ドキュメント] タブでのファイルのアップロードまたは削除など、次の種類のイベントが発生したときに通知を作成するアラート ポリシーを作成できます。詳細については、 [コンプライアンス マネージャーのアラートとアラート ポリシー](compliance-manager-alert-policies.md)に関するページを参照してください。

### <a name="try-recommended-assessment-templates-for-your-organization"></a>組織に推奨される評価テンプレートを試す

組織は、コンプライアンス マネージャーから、どの評価が最も関連性が高い可能性があるかに関する推奨事項を取得できるようになりました。クイック セットアップ プロセスを使用して、立ち上がって実行できます。 ライセンスを購入する前に、推奨事項と Premium 評価テンプレートを試す方法の詳細については、「 [Premium 評価試用版を開始する](compliance-manager-setup.md#start-a-premium-assessments-trial)」を参照してください。

## <a name="november-2021"></a>2021 年 11 月

### <a name="zero-trust-integration-for-the-data-protection-baseline-template"></a>データ保護ベースライン テンプレートのゼロ トラスト統合

ゼロ トラストとは、すべてのトランザクションを明示的かつ継続的に検証し、最小限の特権を行使し、インテリジェンス、高度な検出、脅威に対するリアルタイムの対応に依存する、あらゆるデジタル資産の層にわたるセキュリティに対するプロアクティブで統合されたアプローチのことです。 すべてのユーザーに含まれる Compliance Manager のデータ保護ベースライン テンプレートは、次のコントロール ファミリ全体に配置された 57 個の新しいコントロールと 36 個の新しいアクションゼロ トラスト統合されました。

- ゼロ トラスト アプリケーション
- ゼロ トラスト アプリ開発ガイダンス
- ゼロ トラスト エンドポイント
- ゼロ トラスト データ
- ゼロ トラスト ID
- ゼロ トラスト インフラストラクチャ
- ゼロ トラスト ネットワーク
- ゼロ トラスト可視性、自動化、オーケストレーション

### <a name="new-preview-templates"></a>新しいプレビュー テンプレート

プレビューでは、次の評価テンプレートを使用できるようになりました。

- ISO 27001:2013 for Azure (プレビュー)
- ISO 27001:2013 for Dynamics 365 (プレビュー)
- FedRAMP Moderate for Dynamics 365 (プレビュー)
- FedRAMP Moderate for Azure (プレビュー)
- Azure 用 FedRAMP High (プレビュー)
- FedRAMP High for Dynamics 365 (プレビュー)
- AZURE 用 SOC 2 (プレビュー)
- SOC 2 for Dynamics 365 (プレビュー)
- AZURE の ISO 27018:2019 (プレビュー)
- ISO 27018:2019 for Dynamics 365 (プレビュー)

## <a name="october-2021"></a>2021 年 10 月

### <a name="new-assessment-templates"></a>新しい評価テンプレート

次のような新しい評価テンプレートを公開しました。

- (2010 年 3 月 10 日)
- バージニア消費者データプライバシー法 (CDPA)
- エジプト - データ保護法
- オーストラリア - ASD Essential 8 成熟度レベル 1
- オーストラリア - ASD Essential 8 成熟度レベル 2
- オーストラリア - ASD Essential 8 成熟度レベル 3

### <a name="integration-with-microsoft-priva"></a>Microsoft Privaとの統合

コンプライアンス マネージャーは、組織が Microsoft 365 に保存する個人データを保護するのに役立つソリューションであるMicrosoft Privaと連携できるようになりました。 Priva には、データの視覚化と理解、主要なリスク シナリオを管理するポリシーの実装、サブジェクト権利要求の処理に役立つツールが用意されています。 保存した個人データを保護するために Priva で手順を実行すると、コンプライアンス マネージャーでのプライバシー評価に貢献し、コンプライアンス スコアの向上に役立ちます。 Priva やその他のソリューションがスコアにどのように貢献しているかを確認し、さらに改善する可能性のある機会については、コンプライアンス マネージャーの [ **ソリューション** ] タブを参照してください。 Priva の詳細については、「[Microsoft Privaについて学習する](/privacy/priva)」を参照してください。

## <a name="july-2021"></a>2021 年 7 月

新しいユニバーサル バージョンのテンプレートに基づいて、Microsoft 365 以外の製品の評価を作成する機能を追加しました。 詳細については、 [まず評価テンプレートの操作に関](compliance-manager-templates.md)するページを参照してください。

## <a name="may-2021"></a>2021 年 5 月

### <a name="new-assessment-templates"></a>新しい評価テンプレート

次を含む 75 個の新しい評価テンプレートを公開しました。
- オーストラリアのプライバシー保護法
- CIS Microsoft 365 Foundation レベル 1 と 2
- ドイツ - 金融機関における IT の監督要件 (BAIT)
- Sarbanes-Oxley法
- 南アフリカ - 情報へのアクセスの促進法

[評価テンプレート](compliance-manager-templates-list.md)の完全な一覧を確認してください。

## <a name="april-2021"></a>2021 年 4 月

### <a name="support-for-us-government-dod-customers"></a>米国政府機関 DoD のお客様のサポート

コンプライアンス マネージャーは、米国政府機関コミュニティ (GCC) の中等および GCC High のお客様に加えて、米国政府機関 DoD のお客様が利用できるようになりました。

## <a name="march-2021"></a>2021 年 3 月

### <a name="active-and-inactive-templates"></a>アクティブなテンプレートと非アクティブなテンプレート

各評価ページと評価テンプレート ページには、アクティブ化されたテンプレート カウンターがあります。 このカウンターには、ライセンス契約に従って使用している対象となるテンプレートの数が表示されます。 詳細については、 [テンプレートの可用性とライセンスに関する](compliance-manager-templates.md#template-availability-and-licensing) ページを参照してください。
