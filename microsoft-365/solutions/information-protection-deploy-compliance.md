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
description: コンプライアンス スコアとコンプライアンス マネージャーを使用して、個人データの保護レベルを向上させる方法について学習します。
ms.openlocfilehash: 5a655d504551e42398cdabbcf7a3f651d788c0ad
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60786016"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>コンプライアンス マネージャーを使用して改善アクションを管理する

Microsoft コンプライアンス マネージャーは、EU 一般データ保護規則 [(GDPR)](/compliance/regulatory/gdpr)、カリフォルニア州消費者保護法 CCPA、HIPAA-HITECH (米国の医療プライバシー法)、ブラジルデータ保護法 [(LGPD)](/compliance/regulatory/ccpa-faq)などのデータプライバシー規制に関連する改善を管理するのに役立ちます。

この記事では、データのプライバシーを目的としてこのツールを使用する方法について説明します。

> [!NOTE]
> コンプライアンス マネージャーの推奨事項は、コンプライアンスの保証と捉えることはできません。 お客様の規制環境ごとにお客様独自のコントロールの有効性を評価および検証するかどうかは、お客様の判断に委ねられています。 これらのサービスには、[オンライン サービスの条件](https://go.microsoft.com/fwlink/?linkid=2108910)の利用規約が適用されます。 「セキュリティ[とコンプライアンスMicrosoft 365ライセンス ガイダンス」も参照してください。](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

## <a name="getting-started-with-compliance-manager"></a>コンプライアンス マネージャーの使用を開始する

#### <a name="what-is-compliance-manager"></a>コンプライアンス マネージャーとは

[コンプライアンス マネージャー](../compliance/compliance-manager.md)は、Microsoft クラウド サービスに関連する規制コンプライアンス 活動Microsoft 365 コンプライアンス センター管理するためのワークフロー ベースのリスク評価ツールです。 コンプライアンス マネージャーは、Microsoft 365 または Azure Active Directory (Azure AD) サブスクリプションの一環として、Microsoft クラウド サービスの共有責任モデル内で規制コンプライアンスを管理するのに役立ちます。

**評価を使用する準備ができました**

コンプライアンス マネージャーは、GDPR や[](../compliance/compliance-manager-assessments.md)HIPAA/HITECH などのデータ プライバシー関連の規制に沿った評価を構築するために事前に構築されたテンプレートを提供します。 テンプレートには、規制の要件を満たす改善アクションを実行するのに役立つコントロール マッピングが組み込みされています。 各評価では、対象サービスに固有の各規制が呼び出すコントロールに関する情報を提供します。Microsoft が管理および制御するコントロールによって異なっています。

事前構築されたテンプレートを使用すると、リスク評価をすばやく開始できます。 コンプライアンス マネージャーの使用に詳しくなると、独自のコントロールと改善アクションを追加して、事前に構築されたテンプレートをカスタマイズしたり、組織のニーズに合わせて独自のカスタム評価を作成することができます。

コンプライアンス マネージャー [によって提供される評価テンプレートの完全](../compliance/compliance-manager-templates-list.md) な一覧を表示します。

**リアルタイムのコンプライアンス スコア**

コンプライアンス マネージャーは、コントロール内で推奨される改善アクションを完了する進捗状況を測定するコンプライアンス スコアも提供します。 このスコアを使用すると、進捗状況を監視し、リスクを軽減する可能性に基づいてアクションの優先順位を設定できます。

#### <a name="use-the-compliance-manager-quickstart-guide"></a>コンプライアンス マネージャーのクイック スタート ガイドを使用する

コンプライアンス [マネージャーのクイック スタート ガイド](../compliance/compliance-manager-quickstart.md) には、コンプライアンス マネージャーの作業に役立つ主要なリソースへの手順とリンクが示されています。

- [最初の訪問: コンプライアンス マネージャーについて理解する](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - コンプライアンス マネージャー ダッシュボードの操作
    - コンプライアンス スコアについて
    - ラーニングアクションの詳細
    - 評価とテンプレートについて
- [ランプアップ: コンプライアンス アクティビティを管理するコンプライアンス マネージャーを構成する](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - 最初の評価の作成と管理
    - 改善アクションの実装とテスト作業を実行して、評価のコントロールを完了する
    - さまざまなアクションがコンプライアンス スコアに与える影響を理解する
- [スケール アップ: 高度な機能を使用してカスタム ニーズを満たす](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - カスタム評価を作成して、製品以外の製品Microsoft 365する
    - 既存のテンプレートを変更してコントロールを追加または削除する
    - 改善アクションの自動テストのセットアップ

## <a name="how-your-compliance-score-is-calculated"></a>コンプライアンススコアの計算方法

コンプライアンス スコアは、Microsoft と顧客が管理するコントロールの実装の組み合わせに基づいて計算されます。 詳細 [については、「コンプライアンス スコアの](../compliance/compliance-score-calculation.md) 計算」を参照してください。

コントロールには、必須か任意か、予防的か探偵か修正かに基づいてスコア値が割り当てられます。 これらはまとめて、他のコントロールに対して実装しないリスクを表します。

コンプライアンス スコアの計算に関する記事で説明されている通り、予防コントロールは探偵や修正コントロールよりも高いスコアを取得し、必須のコントロールは任意のコントロールよりも高いスコアを取得します。

コンプライアンス スコア管理 UI では、これらのパラメーターは一覧表示されません。また、これらのパラメーターによってフィルター処理を行う機能も提供しません。 ただし、コンプライアンス マネージャーから関連付けられたテンプレートをダウンロードした場合、結果のデータ セットには、ほとんどの規制に対してこれらのパラメーターが一覧表示されます。

技術コントロールの場合、コンプライアンス マネージャーは、アクションが正常に実装およびテストされると、改善アクション スコアを自動的に更新します。 その他、操作上の操作やドキュメントに関連する操作などの技術的でない制御アクションは、ポイントがスコアにカウントされる前に手動で記録する &mdash; &mdash; 必要があります。

また、データ プライバシー規制のコンプライアンス以外の理由で保持ラベルを使用するなどの目的で、他の目的で特定の改善アクションを実装している場合も多く、意図的なコンプライアンスアクションの一部ではなく、他の目的で使用されている場合でも、そのような機能を使用する際の信用を得る可能性があります。 &mdash; &mdash;

コンプライアンス スコアは、広範な規模で改善を追跡する相対的な手段と見なされる必要があります。 完璧なスコアを追求する必要があります。

## <a name="additional-guidance"></a>追加のガイダンス

コンプライアンス マネージャーを使用してデータプライバシー規制のコンプライアンスを達成するための重要なヒントを次に示します。

- 各データプライバシー規制には、技術的な制御、ドキュメント仕様、運用、プロセス、およびレポートの要件が組み合わせて含まれています。 これらのすべてが改善アクションに表示されます。

- 改善アクションのビューを関心のある領域に絞り込むには、コンプライアンス マネージャー管理者の[ソリューション] タブでアクションの種類別にフィルター処理できます。コンプライアンス マネージャー ダッシュボード[ビューのフィルター処理について詳しくは、次のページをご覧ください](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)。

- コンプライアンス マネージャーで特定された改善アクションの相対的な重要性と優先度は、組織が管理する必要があるデータ プライバシー リスクと共に、より広範なリスク レビューの一環として考慮する必要があります。

- 複数の規制要件で改善アクションが集約されている場合でも、GDPR、LGPD、CCPA、HIPAA-HITECH の規制評価テンプレートが選択されている場合は、コンプライアンス マネージャーに約 400 件の改善アクションが表示されます。 この長いリストに対処するには、改善アクション フィルターを使用して、結果セットをより管理可能なリストに減らします。

- カテゴリ フィルターは、このソリューション全体の記事を追跡、防止、保護、保持、および調査する論理グループ化によって改善アクションをフィルター処理する手段を提供します。

- 改善アクションに記載されている一部のコントロールは、特定の規制記事に直接関連付けられていると見なされる場合があります。他のコントロールは、規制の精神に間接的に関連付けられる可能性があります。多くの場合は、単に推奨されるアクティビティまたはベスト プラクティスです。