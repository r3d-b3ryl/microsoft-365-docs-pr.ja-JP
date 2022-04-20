---
title: コンプライアンス マネージャーを使用して改善アクションを管理する
ms.author: chvukosw
author: chvukosw
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: admindeeplinkCOMPLIANCE
description: コンプライアンス スコアとコンプライアンス マネージャーを使用して、個人データの保護レベルを向上させる方法について説明します。
ms.openlocfilehash: 469584abbf784fe6c556aab14a49a5ed44280a69
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64947453"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>コンプライアンス マネージャーを使用して改善アクションを管理する

Microsoft Purview コンプライアンス マネージャーは、欧州連合 [一般データ保護規則 (GDPR)](/compliance/regulatory/gdpr)、 [カリフォルニア消費者保護法 CCPA)](/compliance/regulatory/ccpa-faq)、HIPAA-HITECH (米国医療プライバシー法)、ブラジルデータ保護法 (LGPD) などのデータ プライバシー規制に関連する改善を管理するのに役立ちます。

この記事では、データプライバシーの目的でこのツールを使用する方法に関するガイダンスを提供します。

> [!NOTE]
> コンプライアンス マネージャーの推奨事項は、コンプライアンスの保証と捉えることはできません。 お客様の規制環境ごとにお客様独自のコントロールの有効性を評価および検証するかどうかは、お客様の判断に委ねられています。 これらのサービスには、[オンライン サービスの条件](https://go.microsoft.com/fwlink/?linkid=2108910)の利用規約が適用されます。 [セキュリティとコンプライアンスに関するMicrosoft 365ライセンスガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)も参照してください

## <a name="getting-started-with-compliance-manager"></a>コンプライアンス マネージャーの概要

#### <a name="what-is-compliance-manager"></a>コンプライアンス マネージャーとは

[コンプライアンス マネージャー](../compliance/compliance-manager.md) は、Microsoft Purview コンプライアンス ポータルのワークフロー ベースのリスク評価ツールで、Microsoft クラウド サービスに関連する規制コンプライアンス アクティビティを管理します。 コンプライアンス マネージャーは、Microsoft 365またはAzure Active Directory (Azure AD) サブスクリプションの一部として、Microsoft クラウド サービスの共有責任モデル内で規制コンプライアンスを管理するのに役立ちます。

**評価を使用する準備ができました**

コンプライアンス マネージャーは、GDPR や HIPAA/HITECH などのデータ プライバシー関連の規制に合わせた [評価を構築](../compliance/compliance-manager-assessments.md) するための事前構築済みテンプレートを提供します。 このテンプレートには、規制の要件を満たすための改善アクションを実行するのに役立つコントロール マッピングが組み込まれています。 各評価では、各規制がターゲット サービスに固有に呼び出すコントロールに関する情報を提供します。これは、Microsoft が管理するコントロールと管理するコントロールによって分けられます。

事前構築済みのテンプレートを使用すると、リスク評価をすばやく開始できます。 コンプライアンス マネージャーの使用に慣れるにつれて、独自のコントロールと改善アクションを追加して事前に構築されたテンプレートをカスタマイズしたり、組織のニーズに合わせて独自のカスタム評価を作成したりできます。

コンプライアンス マネージャーによって提供される [評価テンプレートの完全な一覧](../compliance/compliance-manager-templates-list.md) を表示します。

**リアルタイムのコンプライアンス スコア**

コンプライアンス マネージャーには、コントロール内で推奨される改善アクションを完了する進行状況を測定するコンプライアンス スコアも用意されています。 このスコアを使用すると、進行状況を監視し、リスクを軽減する可能性に基づいてアクションに優先順位を付けることができます。

#### <a name="use-the-compliance-manager-quickstart-guide"></a>コンプライアンス マネージャーのクイック スタート ガイドを使用する

[コンプライアンス マネージャーのクイック スタート](../compliance/compliance-manager-quickstart.md) ガイドには、コンプライアンス マネージャーの操作に役立つ主要なリソースへの段階的な手順とリンクが用意されています。

- [最初の訪問: コンプライアンス マネージャーについて理解する](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - コンプライアンス マネージャー ダッシュボードの操作
    - コンプライアンス スコアについて
    - 改善アクションに関するラーニング
    - 評価とテンプレートについて
- [急増: コンプライアンス アクティビティを管理するようにコンプライアンス マネージャーを構成する](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - 最初の評価の構築と管理
    - 改善アクションの実装とテスト作業を実行して、評価の制御を完了する
    - さまざまなアクションがコンプライアンス スコアに与える影響を理解する
- [スケールアップ: 高度な機能を使用してカスタム ニーズを満たす](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Microsoft 365以外の製品を追跡するためのカスタム評価の作成
    - コントロールを追加または削除するための既存のテンプレートの変更
    - 改善アクションの自動テストを設定する

## <a name="how-your-compliance-score-is-calculated"></a>コンプライアンススコアの計算方法

コンプライアンス スコアは、Microsoft とカスタマー マネージド コントロールの実装の組み合わせに基づいて計算されます。 詳細な説明については、 [コンプライアンス スコアの計算](../compliance/compliance-score-calculation.md) を参照してください。

コントロールには、必須であるか裁量的であるか、およびそれらが予防的であるか、探偵であるか、修正であるかに基づいてスコア値が割り当てられます。 これらは、他のコントロールに対して実装しないリスクをまとめて表します。

コンプライアンス スコアの計算に関する記事で説明されているように、予防コントロールは探偵や修正用のコントロールよりも高いスコアを取得し、必須コントロールは随意のスコアよりも高いスコアを取得します。

コンプライアンス スコア管理 UI では、これらのパラメーターは一覧表示されず、それらのパラメーターでフィルター処理する機能も提供されません。 ただし、コンプライアンス マネージャーから関連するテンプレートをダウンロードした場合、結果のデータ セットには、ほとんどの規制に対してこれらのパラメーターが一覧表示されます。

技術的な制御の場合、コンプライアンス マネージャーは、アクションが正常に実装およびテストされると、改善アクション スコアを自動的に更新します。 その他の非技術的な制御アクション&mdash;(操作上またはドキュメント&mdash;に関連するものなど)は、ポイントがスコアにカウントされる前に実装されているように手動で記録する必要があります。

また、データプライバシー規制コンプライアンス以外の理由で保持ラベルを使用するなど、他の目的&mdash;に対して特定の改善アクションを実装する場合も多く、意図的なコンプライアンス&mdash; アクションの一部ではなく、他の目的で使用されている場合でも、このような機能を使用したクレジットを得られます。

コンプライアンス スコアは、広範囲にわたる改善を追跡するための相対的なメジャーと見なす必要があります。 完璧なスコアを追い求めてはなりません。

## <a name="additional-guidance"></a>追加のガイダンス

コンプライアンス マネージャーを使用して、データ プライバシー規制コンプライアンスを達成するために役立つ重要なヒントをいくつか次に示します。

- 各データ プライバシー規制には、技術的な制御、ドキュメント仕様、運用、プロセス、およびレポートの要件の組み合わせが含まれています。 これらすべてが改善アクションに表示されます。

- 改善アクションのビューを目的の領域に絞り込むには、コンプライアンス マネージャー管理者の [ **ソリューション** ] タブでアクションの種類でフィルター処理できます。 [コンプライアンス マネージャー ダッシュボード ビューのフィルター処理](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)の詳細について説明します。

- コンプライアンス マネージャーで特定された改善アクションの相対的な重要性と優先順位は、組織が管理する必要があると判断したデータ プライバシー リスクと共に、より広範なリスク レビューの一部と見なす必要があります。

- 複数の規制要件にわたる改善アクション集計でも、GDPR、LGPD、CCPA、HIPAA-HITECH の規制評価テンプレートが選択されている場合は、コンプライアンス マネージャーに約 400 件の改善アクションが表示されます。 この長いリストに対処するには、改善アクション フィルターを使用して、結果セットをより管理しやすいリストに減らします。

- カテゴリ フィルターは、このソリューション全体の記事を追跡、防止、保護、保持、および調査する論理的なグループ化によって改善アクションをフィルター処理する手段を提供します。

- 改善アクションに記載されている一部のコントロールは、特定の規制記事に直接関連付けられていると見なされることがありますが、他のコントロールは規制の精神に間接的に関連付けられている場合があり、多くの場合、単に推奨されるアクティビティまたはベスト プラクティスです。