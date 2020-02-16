---
title: Microsoft コンプライアンススコア FAQ
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
ms.openlocfilehash: 9a71abba7b38bcf1e39073133f82abaedfc0d270
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078644"
---
# <a name="microsoft-compliance-score-preview-frequently-asked-questions"></a>Microsoft コンプライアンススコア (プレビュー) についてよく寄せられる質問

## <a name="what-is-compliance-score"></a>コンプライアンススコアとは

Microsoft コンプライアンススコアは、組織の法令遵守状況を理解するのに役立つ[microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md)のプレビュー機能です。 データ保護および規制標準に関するリスクを軽減するために、進行状況を測定するリスクベースのスコアを計算します。 また、組み込みのコントロールマッピングを使用して、主要な規制や規格に共通のコントロールを接続することができます。そのため、1つのアクションを実行して、複数の要件を同時に満たすことができ、コンプライアンスプログラムをより適切に拡張することができます。

## <a name="how-do-i-access-compliance-score"></a>コンプライアンススコアにアクセスするにはどうすればよいですか?

[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com/)に移動し、microsoft 365 グローバル管理者、コンプライアンス管理者、またはコンプライアンスデータ管理者ロールを使用して**サインイン**します。 左側のナビゲーションウィンドウで [**コンプライアンススコア**] を選択します。 その後、[コンプライアンススコアダッシュボードにスコアを](compliance-score-setup.md#understand-the-compliance-score-dashboard)表示する必要があります。 適切な役割アクセス権を持っていない場合は、組織のグローバル管理者がアクセス許可を付与できます。

## <a name="what-roles-or-permissions-are-needed-to-use-compliance-score"></a>コンプライアンススコアを使用するには、どのような役割またはアクセス許可が必要ですか。

コンプライアンススコアは、役割ベースのアクセス制御 (RBAC) アクセス許可モデルを使用し、実行できるアクションは、割り当てられている役割の種類によって異なります。 組織の Microsoft 365 グローバル管理者は、セットアップ機能を実行し、コンプライアンススコアで役割を管理できるユーザーです。 少なくとも、ユーザーは、コンプライアンススコアでデータを読み取るために**AZURE AD グローバルリーダー**の役割を必要とします。 アクセス許可、役割、およびセットアップ手順の詳細については、「[コンプライアンススコアの設定](compliance-score-setup.md)」を参照してください。

## <a name="what-is-the-difference-between-compliance-score-and-compliance-manager"></a>コンプライアンススコアとコンプライアンスマネージャーの違いは何ですか。

コンプライアンススコアとコンプライアンスマネージャーは同じバックエンドを共有していますが、2つの異なる場所 (コンプライアンススコアは Microsoft 365 コンプライアンスセンターで、コンプライアンスマネージャーは Microsoft Service Trust Portal にあります)。 コンプライアンスのスコアは、コンプライアンスマネージャーの簡易版と考えてください。これにより、組織の現在の法令遵守状況と、それを改善するための手順がより完全に表示されます。 コンプライアンススコアの範囲内で多くのアクションを直接実行できますが、一部の機能は現在、コンプライアンスマネージャーに存在します。 [コンプライアンススコアとコンプライアンスマネージャーの関係](compliance-score.md#relationship-to-compliance-manager)の詳細を参照してください。

## <a name="who-should-use-compliance-score-and-who-should-use-compliance-manager"></a>どのユーザーがコンプライアンススコアを使用し、コンプライアンスマネージャーを使用する必要があるか。

コンプライアンススコアは、コンプライアンス監視の役割を果たし、規制基準に準拠するためのアクティビティを実行する組織内のすべてのユーザーに役立ちます。 コンプライアンススコアでは、組織のデータ保護を向上させるために、規制や基準を熟知している必要はありません。 コンプライアンススコアは、すべてのユーザーにとって最適な開始位置です。 ここから、コンプライアンススコアを確認し、推奨されるアクションを使用してリスクを最小限に抑えることができます。多くの場合、これらのアクションを実行するためにソリューションを適切に起動します。

コンプライアンスマネージャーとは、評価を構築するために、ユーザーが評価を管理し、カスタムテンプレートを作成できるようにするための場所です。 パブリックプレビュー中に[コンプライアンスマネージャーのみがサポートするアクション](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager)について説明します。

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>スコアが高い場合は、完全に準拠していることを意味します。

いいえ。 コンプライアンススコアは、データ保護と規制基準に関するリスクを軽減するために、推奨されるアクションを完了するための進捗状況を測定します。 特定の標準または規制に対する組織のコンプライアンスの絶対的な測定基準を表すものではありません。 コンプライアンススコアは、何らかの保証として解釈されることはありません。

## <a name="what-regulations-and-standards-does-compliance-score-monitor"></a>コンプライアンススコアモニターではどのような規則と規格がありますか?

コンプライアンススコアでは、Microsoft 365 データ保護基準に基づく初期スコアが得られます。これは、一般的な業界の規制と標準を含む一連のコントロールです。 この基準は、主に NIST CSF (米国規格およびテクノロジ Cybersecurity フレームワーク) および ISO (国際標準化機構)、および FedRAMP (連邦リスクおよび承認管理) からの要素を描画します。プログラム) と GDPR (欧州連合の一般的なデータ保護規則)。

組織は、組織にとってより関連性の高いカスタム評価を作成し、追加することができます。 コンプライアンススコアの標準テンプレートの1つを使用して[、](compliance-score.md#templates)特定の標準の評価を作成したり、[独自のテンプレートを作成](working-with-compliance-manager.md#create-a-template-1)したりすることができます。

詳細については[、「コンプライアンススコアがスコアを計算する方法](compliance-score-methodology.md)」を参照してください。

## <a name="what-is-the-difference-between-compliance-score-and-secure-score"></a>コンプライアンススコアとセキュリティスコアの違いは何ですか。

コンプライアンススコアは、組織のデータ保護とコンプライアンスの状況を幅広く表示します。 コンプライアンススコアには、組み込みのワークフローツールも用意されています。これにより、組織は仕事をユーザーに割り当て、コントロールの実装とテストの状態を追跡したり、証拠をアップロードしたり、監査レポートを作成したりできます。

Microsoft Secure Score は、セキュリティに関する姿勢を理解するためのセキュリティ分析ツールです。 [セキュリティで保護されたスコアとそのしくみについて説明](../security/mtp/microsoft-secure-score.md)します。

## <a name="which-cloud-services-are-covered-by-compliance-score"></a>コンプライアンススコアの対象となるクラウドサービス

現在、コンプライアンススコアは Office 365 および Intune の評価を提供しています。 拡張されたカバレッジは将来のリリースで予想されるものであり、[コンプライアンススコアのリリースノート](compliance-score-release-notes.md)に記載されています。

## <a name="can-i-use-compliance-score-for-non-microsoft-products"></a>Microsoft 以外の製品でコンプライアンススコアを使用できますか。

コンプライアンススコアは継続的な監視と推奨されるアクションを Microsoft クラウドサービスに対してのみ提供しますが、社内のサードパーティサービスのコンプライアンスマネージャーでカスタム評価を追加することができます。 このようにして、Microsoft のコンプライアンススコアを SaaS コンプライアンス管理ツールとして使用し、デジタル資産全体のすべてのコントロールを管理することができます。

コンプライアンススコアの標準テンプレートの1つを使用して[、](compliance-score.md#templates)特定の標準の評価を作成したり、[独自のテンプレートを作成](working-with-compliance-manager.md#create-a-template-1)したりすることができます。

## <a name="how-do-i-delete-a-template-or-assessment-i-no-longer-need"></a>不要になったテンプレートまたは評価を削除するにはどうすればよいですか?

評価またはテンプレートを削除することはできませんが、ビューから非表示にすることはできます。 [評価を非表示にするための手順を](working-with-compliance-manager.md#hide-a-template-or-an-assessment)確認します。
