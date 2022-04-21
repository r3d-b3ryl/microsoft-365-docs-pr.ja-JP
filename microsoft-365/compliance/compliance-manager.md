---
title: Microsoft Purview コンプライアンス マネージャー
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
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: Microsoft Purview コンプライアンス マネージャーは、組織がリスク評価を簡素化および自動化するのに役立ち、リスクに対処するために推奨されるアクションを提案します。
ms.openlocfilehash: 1d5f036b8bc97da431ed6e41017d59e01db749a4
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64997100"
---
# <a name="microsoft-purview-compliance-manager"></a>Microsoft Purview コンプライアンス マネージャー

> [!TIP]
> *9 つの Microsoft Purview ソリューションの Premium バージョンを無料で試すことができることをご存じですか?* 90 日間の Purview ソリューション試用版を使用して、堅牢な Purview 機能が組織のコンプライアンス ニーズを満たすのにどのように役立つかを調べます。 Microsoft 365 E3およびOffice 365 E3のお客様は、[Microsoft Purview コンプライアンス ポータルの試用版ハブ](https://compliance.microsoft.com/trialHorizontalHub?sku=ComplianceE5&ref=DocsRef)から開始できます。 [サインアップできるユーザーと試用版の使用条件](compliance-easy-trials.md)の詳細について説明します。

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

**この記事では、次の操作を行います。** コンプライアンス マネージャーとは何か、コンプライアンスを簡素化してリスクを軽減する方法、およびその主要なコンポーネントについて説明します。

## <a name="what-is-compliance-manager"></a>コンプライアンス マネージャーとは?

[Microsoft Purview コンプライアンス マネージャー](https://compliance.microsoft.com/compliancemanager) は、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a> の機能であり、組織のコンプライアンス要件をより簡単かつ便利に管理するのに役立ちます。 コンプライアンス マネージャーは、データ保護リスクのインベントリの作成から、複雑な制御の実装の管理、規制や認証の最新情報の入手、監査人への報告まで、コンプライアンスの過程全体を支援します。

コンプライアンス マネージャーが組織でコンプライアンスを管理する方法を簡略化する方法については、次のビデオをご覧ください。
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

コンプライアンス マネージャーは、次の情報を提供することで、コンプライアンスを簡素化し、リスクを軽減するのに役立ちます。

- 一般的な業界および地域の標準と規制に対する事前に構築された評価、または独自のコンプライアンス ニーズを満たすカスタム評価 (利用可能な評価は、ライセンス契約によって異なります)。 [詳細については、こちらを参照してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance))。

- 単一のツールを使用してリスク評価を効率的に完了させるためのワークフロー。

- 組織に最も関連する標準と規制に準拠するのに役立つ、改善の推奨アクションに関する詳細なステップ バイ ステップ ガイダンス。 Microsoft によって管理されるアクションの場合は、実装の詳細と監査結果が表示されます。

- 改善アクションの完了の進行状況を測定することで、コンプライアンス体制を理解するのに役立つリスクベースのコンプライアンス スコア。

コンプライアンス マネージャー ダッシュボードには、現在のコンプライアンス スコアが表示され、注意が必要なものを確認し、主要な改善アクションを案内します。 コンプライアンス マネージャー ダッシュボードの例を次に示します。

![コンプライアンス マネージャーのダッシュ ボード。](../media/compliance-manager-dashboard.png "コンプライアンス マネージャーのダッシュ ボード")

## <a name="understanding-your-compliance-score"></a>コンプライアンス スコアについて

コンプライアンス マネージャーは、規制、標準、またはポリシーに準拠するために実行された改善アクションを完了するためのポイントを付与し、それらのポイントを全体的なコンプライアンス スコアに結合します。 各アクションは、関連する潜在的なリスクに応じてスコアに異なる影響を与えます。 コンプライアンス スコアは、全体的なコンプライアンス体制を改善するためにどのアクションに重点を置くかを優先順位付けするのに役立ちます。

コンプライアンス マネージャーは、Microsoft 365 データ保護ベースラインに基づいて、初期スコアを提供します。 このベースラインは、データ保護と一般的なデータ ガバナンスに関する主要な規制と基準を含む一連のコントロールです。

##### <a name="learn-more"></a>詳細情報

[コンプライアンス スコアの計算方法を理解します](compliance-score-calculation.md)。

[改善アクションを操作する方法について説明します](compliance-manager-improvement-actions.md)。

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a>重要な要素: コントロール、評価、テンプレート、改善アクション

コンプライアンス マネージャーでは、コンプライアンス アクティビティの管理に役立つ複数のデータ要素を使用します。 コンプライアンス マネージャーを使用してコンプライアンス アクティビティの割り当て、テスト、監視を行う場合は、コントロール、評価、テンプレート、改善アクションなどの重要な要素を基本的に理解しておくと便利です。

### <a name="controls"></a>コントロール

コントロールは、規制、標準、またはポリシーの要件のことです。 コントロールは、システム構成、組織のプロセス、および規制、標準、ポリシーの特定の要件への準拠に関する責任者を評価し、管理する方法を定義します。

コンプライアンス マネージャーは、次の種類のコントロールを追跡します。

1. **Microsoft マネージド コントロール**: Microsoft クラウド サービスのコントロール。
2. **コントロール**: カスタマー マネージド コントロールとも呼ばれることもあります。これらは組織によって実装および管理されるコントロールです。
3. **共有コントロール**: これらは、組織と Microsoft の両方が実装する責任を共有するコントロールです。

##### <a name="learn-more"></a>詳細情報

[コントロールの進行状況を監視します](compliance-manager-assessments.md#monitor-assessment-progress-and-controls)。

[コンプライアンス マネージャーがコントロールを継続的に評価する方法について説明します](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)。

### <a name="assessments"></a>評価

評価とは、特定の規制、標準、またはポリシーからの制御のグループ化です。 評価は、標準、規則、または法律の要件を満たすのに役立つ評価内で処置を完了します。 たとえば、その中のすべてのアクションを完了すると、ISO 27001 の要件に沿ったMicrosoft 365設定に役立つ評価が得られます。

評価には、次のいくつかのコンポーネントがあります。

- **範囲内のサービス**: 評価に適用される Microsoft サービスの特定のセット
- **Microsoft マネージド コントロール**: Microsoft クラウド サービスのコントロール。Microsoft がユーザーに代わって実装します
- **コントロール**: カスタマー マネージド コントロールとも呼ばれることもあります。これらは組織によって実装および管理されるコントロールです。
- **共有コントロール**: これらは、組織と Microsoft の両方が実装する責任を共有するコントロールです。
- **評価スコア**: 組織と Microsoft によって管理される評価内のアクションから可能な合計ポイントを達成した進捗状況を示します

評価を作成するときは、それらをグループに割り当てます。 組織にとって最も論理的な方法でグループを構成できます。 たとえば、監査年、リージョン、ソリューション、組織内のチーム、またはその他の方法で評価をグループ化できます。 グループを作成したら、 [コンプライアンス マネージャー ダッシュボードをフィルター処理](compliance-manager-setup.md#filtering-your-dashboard-view) して、1 つ以上のグループでスコアを表示できます。

##### <a name="learn-more"></a>詳細情報

[コンプライアンス マネージャーで評価を構築および管理します](compliance-manager-assessments.md)。

### <a name="templates"></a>テンプレート

コンプライアンス マネージャーには、評価をすばやく作成するのに役立つテンプレートが用意されています。 これらのテンプレートを変更して、ニーズに合わせて最適化された評価を作成できます。 独自のコントロールとアクションを使用してテンプレートを作成することで、カスタム評価を構築することもできます。 たとえば、テンプレートで内部ビジネス プロセス制御をカバーする場合や、325 以上の事前構築済みの評価テンプレートの 1 つではカバーされていない地域データ保護標準を使用できます。

##### <a name="learn-more"></a>詳細情報

[コンプライアンス マネージャーによって提供される評価テンプレートの一覧を表示します](compliance-manager-templates-list.md)。

[評価用のテンプレートの作成と変更に関する詳細な手順を確認します](compliance-manager-templates.md)。

### <a name="improvement-actions"></a>改善のための処置

改善アクションは、コンプライアンス アクティビティを一元化するのに役立ちます。 各改善アクションには、データ保護の規制や標準に合わせて役立つ推奨されるガイダンスが用意されています。 改善のための処置は、実装やテスト作業を行う組織内のユーザーに割り当てることができます。 また、改善のための処置の中にドキュメント、メモ、記録状態の更新を保存することができます。

##### <a name="learn-more"></a>詳細情報

[改善アクションを使用して、コンプライアンス ワークフローを管理します](compliance-manager-improvement-actions.md)。

[アクションがコンプライアンス スコアに与える影響について説明します](compliance-score-calculation.md#action-types-and-points)。

## <a name="supported-languages"></a>サポートされている言語

コンプライアンス マネージャーは、次の言語で使用できます。

- 英語
- Bahasa インドネシア語
- Bahasa Malay
- 簡体字中国語
- 繁体字中国語
- チェコ語
- デンマーク語
- オランダ語
- フィンランド語
- フランス語
- ドイツ語
- ヘブライ語
- ハンガリー語
- イタリア語
- 日本語
- 韓国語
- ノルウェー語
- ポーランド語
- ポルトガル語 (ブラジル)
- ロシア語
- スペイン語
- スウェーデン語
- タイ語
- トルコ語

## <a name="next-steps-set-up-and-customize"></a>次の手順: セットアップとカスタマイズ

[コンプライアンス マネージャー](compliance-manager-setup.md)を使用して概要で、サインイン、アクセス許可とロールの割り当て、設定の構成、ダッシュボード ビューのカスタマイズを行う方法について説明します。

次に、コンプライアンス マネージャーのカスタマイズを開始し、 [評価を設定](compliance-manager-assessments.md)することで、組織にとって最も重要な業界標準に準拠できるようにします。

データ プライバシー規制に準拠できるように、コンプライアンス マネージャーの使用を含め、Microsoft 365全体で機能を計画および実装するためのエンド ツー エンド プロセスをガイドするワークフローを設計しました。 詳細については、「[Microsoft 365を使用したデータプライバシー規制の情報保護の展開 (aka.ms/m365dataprivacy)](../solutions/information-protection-deploy.md)」を参照してください。 
