---
title: Microsoft コンプライアンススコア
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
description: Microsoft コンプライアンススコアを使用すると、組織はリスク評価を簡略化および自動化し、リスクに対処するための推奨される処置を提案します。
ms.openlocfilehash: 5fced1a9452f2345a678bfef670e1a19b9811e81
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140852"
---
# <a name="microsoft-compliance-score-preview"></a>Microsoft コンプライアンススコア (プレビュー)

[Microsoft コンプライアンススコア](https://compliance.microsoft.com/compliancescore)は、コンプライアンスの管理方法を簡素化し、ユーザーフレンドリな環境でコンプライアンスリスクを軽減するのに役立ちます。 コンプライアンススコアは、 [Microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md)のパブリックプレビューで利用できます。

**この記事の内容**この記事を読むと、コンプライアンススコアの概要と、組織に合わせて設定する方法を理解できます。

**更新プログラムについて説明します。** 2020年4月リリースには、いくつかの更新プログラムが公開されています。 コンプライアンススコアの[リリースノート](compliance-score-release-notes.md)を参照して、コンプライアンススコアのプレビューバージョンに関する新着情報と既知の問題を確認してください。

## <a name="what-is-compliance-score"></a>コンプライアンススコアとは

Microsoft コンプライアンススコアは、Microsoft 365 コンプライアンスセンターのプレビュー機能で、組織の法令遵守状況を理解するのに役立ちます。 データ保護および規制標準に関するリスクを軽減するために、進行状況を測定するリスクベースのスコアを計算します。

コンプライアンススコアをツールとして使用して、すべてのリスク評価を追跡できます。 これにより、一般的なツールを使用してリスク評価を効率的に完了できるようにするためのワークフロー機能が提供されます。

現在[コンプライアンスマネージャー](compliance-manager-overview.md)を使用している場合は、コンプライアンスをより簡単に管理できるようにするための、よりシンプルでわかりやすい設計のスタンドアロンの機能としてコンプライアンススコアが表示されることがわかります。 

メインのコンプライアンススコアページはカスタムダッシュボードです。 現在のスコアが表示され、注意が必要な点を確認したり、スコアを向上させるためのアクションを案内したりできます。 コンプライアンススコアのダッシュボードは次のようになります。

![コンプライアンススコア-ダッシュボード](../media/compliance-score-dashboard.png "コンプライアンススコアダッシュボード")

### <a name="simplified-compliance-management"></a>容易なコンプライアンス管理

コンプライアンススコアは、以下を提供することによりコンプライアンス管理を簡素化します。

- **継続的な評価**: Microsoft 365 環境を自動的にスキャンして、システム内のデータ保護コントロールの有効性を検出および監視します。
- **推奨されるアクション**: コントロールを実装してスコアを最大化する方法について、推奨事項と詳しいガイダンスを示します。
-  **組み込みのコントロールマッピング**: 組み込みのコモンコントロールフレームワークを提供することにより、進化し続けるコンプライアンスの状況を最新の状態に保つことができます。

> [!IMPORTANT]
> コンプライアンス スコアおよびコンプライアンス マネージャーからの推奨事項は、コンプライアンスの保証として解釈してはいけません。 お客様は、お客様の規制環境に応じて、カスタマーコントロールの有効性を評価および検証することができます。 これらのサービスは現在プレビュー段階であり、[オンラインサービス](https://go.microsoft.com/fwlink/?linkid=2108910)の使用条件に従っています。 [セキュリティとコンプライアンスのための Microsoft 365 ライセンスガイダンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)も参照してください。

## <a name="relationship-to-compliance-manager"></a>コンプライアンスマネージャーとの関係

コンプライアンスマネージャーの簡易版として、コンプライアンススコアと考えてください。 2つの機能は、個別の統合されたツールとして存在しますが、コンプライアンススコアを使用すると、全体的なコンプライアンスの状況を簡単に監視し、改善するための手順を講じることができます。

コンプライアンススコアは、コンプライアンスマネージャーと同じバックエンドを共有するので、コンプライアンスマネージャーに既に所有しているデータがコンプライアンススコアに表示されます。

一部の機能は、評価の管理やテンプレートの作成など、パブリックプレビュー中のコンプライアンスマネージャーにのみ保持されます。 コンプライアンススコアでコンプライアンス管理アクティビティをすべて開始することをお勧めします。 コンプライアンスマネージャーによって処理された機能に到着すると、そのツールにガイドされます。 そのため、このドキュメントの一部では、コンプライアンスマネージャーのトピックについて説明しています。

コンプライアンススコアとコンプライアンスマネージャーの関係の詳細については、「[コンプライアンススコアのリリースノート](compliance-score-release-notes.md)」を参照してください。

## <a name="understanding-your-score"></a>スコアを理解する

コンプライアンススコアには、Microsoft 365 データ保護基準に基づく初期スコアが与えられます。 このベースラインは、一般的な業界の規制と基準を含む一連のコントロールです。 このスコアは、コンプライアンスの状況を評価するための開始点として最適ですが、組織にとってより関連性の高い評価を追加すると、コンプライアンススコアがより強力になります。

たとえば、組織が金融サービス業界に属している場合は、FFIEC 評価を追加することができます。 組織が医療機関に属している場合は、HIPAA/ヒット査定を追加することができます。 [コンプライアンスマネージャーで評価を追加](working-with-compliance-manager.md#assessments)する方法について説明します。

[コンプライアンススコアが計算され継続的に監視される方法](compliance-score-methodology.md)について説明します。


## <a name="key-components-controls-assessments-templates-groups"></a>主要なコンポーネント: コントロール、評価、テンプレート、グループ

コンプライアンススコアは、コンプライアンスアクティビティの管理に役立ついくつかのコンポーネントを使用します。 コンプライアンススコアを使用してコンプライアンスアクティビティの割り当て、テスト、および監視を行う際には、主要なコンポーネントであるコントロール、評価、テンプレート、およびグループについて、基本的な理解を深めることができます。

### <a name="controls"></a>Controls

コントロールは、システム構成、組織プロセス、および規制、標準、または内部ポリシーの特定の要件を満たす責任者を、どのように評価および管理するかを定義します。

コンプライアンススコアは、次の2種類のコントロールを追跡します。

1. **Microsoft managed controls**: microsoft クラウドサービスのコントロール (microsoft が実装する責任者)
2. **顧客管理コントロール**: 組織で管理されているコントロール。
 
### <a name="assessments"></a>講習

評価は、組織のスコアリングプロセスを開始するテンプレートの評価です。 評価標準、規制、または法律の要件を満たすために必要な処置をグループ化します。 たとえば、すべてのアクションを完了したときに、ISO 27001 要件に合わせて Office 365 の設定をオンラインにするという評価がある場合があります。

コンプライアンススコアは、組織に Microsoft 365 データ保護基準に基づく初期評価を提供します。 この評価は、データ保護とコンプライアンスのリスクを軽減するための推奨事項です (詳細については、こちらを[参照](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)してください)。

評価にはいくつかのコンポーネントがあります。

- **スコープ内サービス**: 評価に適用可能な Microsoft サービスの特定のセット
- **Microsoft managed controls**: microsoft が実装およびテストした制御
- **顧客管理コントロール**: 管理するコントロール
- **評価スコア**: その評価内でアクションを完了して得られたポイントのパーセンテージ

> [!NOTE]
> コンプライアンススコアには、評価と、全体的なスコアにどのような影響があるかが表示されます。 ただし、パブリックプレビュー中には、評価を管理するためにコンプライアンスマネージャーに転送されます。

[コンプライアンスマネージャーで評価を管理](working-with-compliance-manager.md#assessments)するための詳細な手順を表示します。

### <a name="templates"></a>テンプレート

コンプライアンススコア評価用に事前に構成されたテンプレートを提供します。 事前に構成されたテンプレートに独自のコントロールおよびアクションを追加して、カスタム評価を作成することもできます。 たとえば、事前に構成されたテンプレートの1つでは網羅されていない地域データ保護またはコンプライアンス標準のテンプレートとして、ビジネスプロセスコントロール用のテンプレートを作成できます。 独自のテンプレートをコンプライアンススコアにすることで、Microsoft クラウドの評価だけでなく、組織のスコープでのその他のリスク評価も追跡できます。

コンプライアンススコア用に事前に構成されたテンプレートは次のとおりです。

1. [ブラジルの一般データ保護法 (LGPD)](https://go.microsoft.com/fwlink/?linkid=2115387)
2. [カリフォルニアコンシューマ Privacy Act (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) (プレビュー)
3. [Cloud Security アライアンス (CSA) Cloud Controls Matrix (CCM) 3.0.1](https://go.microsoft.com/fwlink/?linkid=2109076)
4. [欧州連合 GDPR](https://go.microsoft.com/fwlink/?linkid=2108870)
5. [連邦金融機関調査協議会 (FFIEC) Information Security ブックレット](https://go.microsoft.com/fwlink/?linkid=2109077)
6. [FedRAMP モデレート](https://go.microsoft.com/fwlink/?linkid=2108869)
7. [HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / の[ヒット](https://go.microsoft.com/fwlink/?linkid=2109079)
8. [Irap](https://go.microsoft.com/fwlink/?linkid=2113709) / [オーストラリア自治体 ISM](https://go.microsoft.com/fwlink/?linkid=2113024) (プレビュー)
9. [ISO 27001:2013](https://go.microsoft.com/fwlink/?linkid=2109073)
10. [ISO 27018:2014](https://go.microsoft.com/fwlink/?linkid=2109074)
11. [ISO 27701:2019](https://go.microsoft.com/fwlink/?linkid=2113025)
12. [Microsoft 365 データ保護のベースライン](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)
13. [NIST 800-53 リビジョン4](https://go.microsoft.com/fwlink/?linkid=2109075)
14. [NIST 800-171](https://go.microsoft.com/fwlink/?linkid=2108867)
15. [NIST Cybersecurity Framework (CSF)](https://go.microsoft.com/fwlink/?linkid=2108868)
16. [SOC 1](https://go.microsoft.com/fwlink/?linkid=2115184)
17. [SOC 2](https://go.microsoft.com/fwlink/?linkid=2115184)

コンプライアンスマネージャーで実行される[テンプレートを作成するための詳細な手順](working-with-compliance-manager.md#templates)が表示されます。

### <a name="groups"></a>グループ

グループを使用すると、評価を論理的な方法で整理できます。 たとえば、年、コンプライアンス標準、サービス、組織内のチーム、またはその他の方法で評価をグループ化することを選択できます。

同じグループで2つの異なる評価を使用して顧客管理アクションを共有する場合、1つの評価でそのアクションの実装詳細、テスト、および状態に加えられた更新が、グループ内の他の評価でも同じアクションに自動的に同期されます。 この方法でアクションを同期すると、割り当てられた改善アクションがグループ全体にわたって統一され、作業の重複が減少します。

[コンプライアンスマネージャーでグループを作成](working-with-compliance-manager.md#groups)する方法について説明します。 グループを作成すると、[コンプライアンススコアダッシュボードをフィルター処理](compliance-score-setup.md#filtering-your-dashboard-view)して、1つ以上のグループでスコアを表示することができます。

## <a name="next-step-begin-setup"></a>次の手順: セットアップを開始する

[コンプライアンススコア](compliance-score-setup.md)の設定で、サインイン、アクセス許可の設定、および更新とダッシュボードの表示を構成する方法について説明します。
