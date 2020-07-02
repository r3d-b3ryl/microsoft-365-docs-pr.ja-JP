---
title: Microsoft コンプライアンススコア (プレビュー) の FAQ
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft のコンプライアンススコアに関してよく寄せられる質問への回答を検索します。これにより、組織はリスク評価を簡素化および自動化できます。
ms.openlocfilehash: 6ba71620d689e6d028b61ff24f7c837337ef60c6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016202"
---
# <a name="compliance-score-preview-frequently-asked-questions"></a>コンプライアンススコア (プレビュー) についてよく寄せられる質問

## <a name="what-is-compliance-score"></a>コンプライアンススコアとは

Microsoft コンプライアンススコアは、組織の法令遵守状況を理解するのに役立つ[microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md)のプレビュー機能です。 データ保護および規制標準に関するリスクを軽減するために、進行状況を測定するリスクベースのスコアを計算します。 コンプライアンススコアには、主要な規制や基準間で共通のコントロールを接続するために役立つ組み込みのコントロールマッピングが用意されています。 このマッピングにより、複数の要件を満たすために1つのアクションを同時に実行して、コンプライアンスプログラムを拡張することができます。

## <a name="whats-new-in-the-preview-version-of-compliance-score"></a>コンプライアンススコアのプレビューバージョンの新機能

機能の更新および既知の問題については、[コンプライアンススコアのリリースノート](compliance-score-release-notes.md)を参照してください。

## <a name="how-do-i-access-compliance-score"></a>コンプライアンススコアにアクセスするにはどうすればよいですか?

[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com/)に移動し、microsoft 365 グローバル管理者、コンプライアンス管理者、またはコンプライアンスデータ管理者ロールを使用して**サインイン**します。 左側のナビゲーション ウィンドウで、[**コンプライアンス スコア**] を選択します。 その後、[自分のスコアとともにコンプライアンス スコアのダッシュボード](compliance-score-setup.md#understand-the-compliance-score-dashboard)が表示されます。 適切な役割アクセス権を持っていない場合は、組織のグローバル管理者がアクセス許可を付与できます。

## <a name="what-roles-or-permissions-are-needed-to-use-compliance-score"></a>コンプライアンススコアを使用するには、どのような役割またはアクセス許可が必要ですか。

コンプライアンススコアは、役割ベースのアクセス制御 (RBAC) アクセス許可モデルを使用します。 実行できるアクションは、割り当てられている役割の種類によって異なります。 組織の Microsoft 365 グローバル管理者は、セットアップ機能を実行し、コンプライアンススコアで役割を管理できるユーザーです。 少なくとも、ユーザーは、コンプライアンススコアでデータを読み取るために**AZURE AD グローバルリーダー**の役割を必要とします。 アクセス許可、役割、およびセットアップ手順の詳細については、「[コンプライアンススコアの設定](compliance-score-setup.md)」を参照してください。

## <a name="what-is-the-difference-between-compliance-score-and-compliance-manager"></a>コンプライアンススコアとコンプライアンスマネージャーの違いは何ですか。

コンプライアンススコアとコンプライアンスマネージャーは同じバックエンドを共有します。 1つのツールで行う操作は、他のツールにも表示されます。 これらは、2つの異なる場所に存在します。コンプライアンススコアは Microsoft 365 コンプライアンスセンターで、コンプライアンスマネージャーは Microsoft Service Trust Portal にあります。 コンプライアンスのスコアは、コンプライアンスマネージャーの簡易版と考えてください。これにより、組織の現在の法令遵守状況と、それを改善するための手順がより完全に表示されます。

コンプライアンススコアの範囲内で多くのアクションを直接実行できますが、パブリックプレビュー中には、一部の機能がコンプライアンスマネージャーに存在します。 [コンプライアンススコアとコンプライアンスマネージャーの関係](compliance-score.md#relationship-to-compliance-manager)の詳細を参照してください。

[Microsoft Service Trust Portal でコンプライアンスマネージャーに](https://servicetrust.microsoft.com/ComplianceManager/V3)アクセスします。 トップナビゲーションドロップダウンメニューから **[コンプライアンスマネージャー** ] を選択してください。これには、最新の機能があり、事前にリリースされた機能を含む*コンプライアンスマネージャー (クラシック) ではありません*。

## <a name="should-i-use-compliance-score-or-compliance-manager"></a>コンプライアンススコアまたはコンプライアンスマネージャーを使用する必要がありますか?

コンプライアンススコアは、組織内のすべてのユーザーが、法令遵守で役割を演じる際に役立ちます。 コンプライアンススコアでは、組織のデータ保護を向上させるために、規制や基準を熟知している必要はありません。 コンプライアンススコアは、すべてのユーザーにとって最適な開始位置です。 ここから、コンプライアンススコアを確認して、リスクを最小限に抑えるために推奨されるアクションと、評価を管理する方法を理解できます。

ここで、コンプライアンスマネージャーは、評価を構築するためのカスタムテンプレートを作成できる場所です。 パブリックプレビュー中に[コンプライアンスマネージャーのみがサポートするアクション](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager)について説明します。

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>スコアが高い場合は、完全に準拠していることを意味します。

いいえ。 コンプライアンススコアは、データ保護と規制基準に関するリスクを軽減するために、推奨されるアクションを完了するための進捗状況を測定します。 特定の標準または規制に対する組織のコンプライアンスの絶対的な測定基準を表すものではありません。 コンプライアンススコアは、何らかの保証として解釈されることはありません。

## <a name="what-regulations-and-standards-does-compliance-score-monitor"></a>コンプライアンススコアモニターではどのような規則と規格がありますか?

コンプライアンススコアでは、Microsoft 365 データ保護基準に基づく初期スコアが得られます。これは、一般的な業界の規制と標準を含む一連のコントロールです。 この基準は、主に NIST CSF (米国国立標準およびテクノロジ Cybersecurity フレームワーク) および ISO (国際標準化機構)、および、FedRAMP (連邦リスクおよび承認管理プログラム) および GDPR (欧州連合の一般的なデータ保護規則) からの要素を描画します。

組織は、組織にとってより関連性の高いカスタム評価を作成し、追加することができます。 コンプライアンススコアのいずれかを使用して、[テンプレート](compliance-score-templates.md)を使用したり、独自のコントロールやアクションを使用して Microsoft テンプレートをカスタマイズしたり、独自のテンプレートを作成したりすることができます。 [評価とテンプレートの](compliance-score-assessments.md)使用に関する詳細をお読みください。

## <a name="how-does-compliance-score-continuously-assess-my-environment"></a>コンプライアンススコアはどのようにして環境を継続的に評価しますか?

コンプライアンススコアは、環境を自動的にスキャンし、セキュリティで保護されたスコアを使用してシステム設定を検出します。 [継続的な評価](compliance-score-methodology.md#how-compliance-score-continuously-assesses-controls)の詳細について説明します。

## <a name="what-is-the-difference-between-compliance-score-and-secure-score"></a>コンプライアンススコアとセキュリティスコアの違いは何ですか。

コンプライアンススコアは、組織のデータ保護とコンプライアンスの状況を幅広く表示します。 コンプライアンススコアには、組み込みのワークフローツールも用意されています。これにより、組織は仕事をユーザーに割り当て、コントロールの実装とテストの状態を追跡したり、証拠をアップロードしたり、監査レポートを作成したりできます。

Microsoft Secure Score は、セキュリティに関する姿勢を理解するためのセキュリティ分析ツールです。 [セキュリティで保護されたスコアとそのしくみについて説明](../security/mtp/microsoft-secure-score-new.md)します。

## <a name="which-cloud-services-are-covered-by-compliance-score"></a>コンプライアンススコアの対象となるクラウドサービス

現在、コンプライアンススコアは Office 365 および Intune の評価を提供しています。 拡張されたカバレッジは将来のリリースで予想されるものであり、[コンプライアンススコアのリリースノート](compliance-score-release-notes.md)に記載されています。

## <a name="can-i-use-compliance-score-for-non-microsoft-products"></a>Microsoft 以外の製品でコンプライアンススコアを使用できますか。

コンプライアンススコアは継続的な監視と推奨されるアクションを Microsoft クラウドサービスに対してのみ提供しますが、社内のサードパーティサービスのコンプライアンスマネージャーでカスタム評価を追加することができます。 このようにして、Microsoft のコンプライアンススコアを SaaS コンプライアンス管理ツールとして使用し、デジタル資産全体のすべてのコントロールを管理することができます。

コンプライアンススコアのいずれかを使用して、特定の標準の[評価を作成](compliance-score-templates.md)したり、[独自のテンプレートを作成](working-with-compliance-manager.md#create-a-template)したりすることができます。これは、コンプライアンスマネージャーで行う必要があります。

## <a name="how-do-i-delete-a-template-or-assessment-i-no-longer-need"></a>不要になったテンプレートまたは評価を削除するにはどうすればよいですか?

評価を削除するには、削除する評価を開いて、[**評価の削除**] を選択します。 評価の削除は永続的なものであることに注意してください。 [評価の削除](compliance-score-assessments.md#delete-an-assessment)に関するその他の詳細を表示します。 評価を削除しても、そのテンプレートは削除されません。 テンプレートを削除することはできませんが、ビューでは非表示にすることができます。 [テンプレートを非表示にする手順を](working-with-compliance-manager.md#hide-a-template-or-an-assessment)確認します。

## <a name="what-test-procedures-does-microsoft-follow-for-controls"></a>コントロールに対して Microsoft が実行するテスト手順

Microsoft は、コントロールの年間監査に参加しています。 監査者からの監査レポートを確認できます。これは、 [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3)からダウンロードできます。

## <a name="why-are-some-controls-tested-annually-and-others-tested-every-three-years"></a>毎年、3年ごとにテストされているコントロールがあるのはなぜですか?

FedRAMP 評価は、このようなケースに該当する場合の例です。 これは毎年行われ、主要な統制ファミリの間で統制のクロスセクションをテストします。 FedRAMP は、年間テストを必要とするほど重要な場合に、**中核**としてコントロールを分類します。 非コアとして指定されたコントロールは、3年ごとにテストされます。 すべての主要なコントロールファミリにまたがるコントロールのサブセットは、毎年テストされます。 このようにして、毎年の各監査は、ソリューションが堅牢であることを確認するために、ボード全体のシナリオを調べます。 [Fedramp の年間評価プロセス](https://www.fedramp.gov/annual-assessment-guidance/)の詳細を参照してください。
