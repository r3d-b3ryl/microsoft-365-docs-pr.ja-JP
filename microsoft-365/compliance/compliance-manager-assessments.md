---
title: Microsoft Purview コンプライアンス マネージャーで評価を構築および管理する
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
description: Microsoft Purview コンプライアンス マネージャーで評価を構築し、組織にとって重要な規制や認定の要件を満たすのに役立ちます。
ms.openlocfilehash: 187820e789f376b990414bb7208b1eaa004a4be2
ms.sourcegitcommit: 06b81b66f13774102bb34556479c1ff890011afb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67357336"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a>コンプライアンス マネージャーで評価を構築および管理する

**この記事では、次の操作を行います。** 評価を作成して管理することで、組織のコンプライアンス マネージャーをカスタマイズする方法について説明 **します**。 この記事では、評価を作成する方法、 **それらをグループ** に整理する方法、 **コントロール** を操作する方法、 **更新プログラム** を受け入れる方法、評価レポートをエクスポートする方法について説明 **します**。

## <a name="introduction-to-assessments"></a>評価の概要

コンプライアンス マネージャーは、組織に適用される業界および地域の規制に対するコンプライアンスを評価する評価を作成するのに役立ちます。 評価は、評価テンプレートのフレームワークに基づいて構築されています。このテンプレートには、必要なコントロール、改善アクション、および評価を完了するための Microsoft のアクションが含まれています。 組織に最も関連性の高い評価を設定すると、コンプライアンス リスクを制限するためのポリシーと運用手順を実装するのに役立ちます。

すべての評価は、コンプライアンス マネージャーの [評価] タブに一覧表示されます。 [評価のビューをフィルター処理し、状態の状態を解釈する方法](compliance-manager-setup.md#assessments-page)について説明します。

> [!IMPORTANT]
> 評価を構築するために組織で使用できるテンプレートは、ライセンス契約によって異なります。 [ライセンスの詳細を確認します](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-compliance-manager)。

## <a name="data-protection-baseline-default-assessment"></a>データ保護ベースラインの既定の評価

Microsoft では、作業を開始するために、**Microsoft 365 データ保護ベースライン** のコンプライアンス マネージャーで **既定** の評価を提供しています。 このベースライン評価には、データ保護と一般的なデータ ガバナンスに関する主要な規制と標準に対する一連の制御があります。 このベースラインは、主に NIST CSF (国立標準技術研究所のサイバー セキュリティ フレームワーク) および ISO (国際標準化機構) や、FedRAMP (米国連邦リスクおよび承認管理プログラム) および GDPR (一般データ保護規則) の要素を取り入れています。

この評価は、他の評価を構成する前に、コンプライアンス マネージャーに初めてアクセスするときに最初のコンプライアンス スコアを計算するために使用されます。 コンプライアンス マネージャーは、Microsoft 365 ソリューションから初期シグナルを収集します。 組織が主要なデータ保護の標準と規制に対してどのように実行されているかを一目で確認し、推奨される改善アクションを確認できます。

コンプライアンス マネージャーは、組織の特定のニーズを満たすために独自の評価を構築および管理すると、より役に立ちます。

## <a name="understand-groups-before-creating-assessments"></a>評価を作成する前にグループを理解する

評価を作成するときは、それをグループに割り当てる必要があります。 グループは、年や規制など、組織の部門や地域に基づいて、自分に合った方法で評価を整理できるコンテナーです。 そのため、評価を作成する前にグループ化戦略を計画することをお勧めします。

2 つのグループとその基になる評価の例を次に示します。

- **FFIEC IS 評価 2020**
  - FFIEC IS
- **データのセキュリティとプライバシーの評価**
  - ISO 27001:2013
  - ISO 27018:2014

グループまたはグループ内の異なる評価では、改善アクションが共有される場合があります。 改善アクションは、テナントにマップされた技術ソリューション内で行う変更 (2 要素認証を有効にする場合など) や、新しい職場ポリシーの作成など、システムの外部で実行する非技術的なアクションに加える場合があります。 技術的改善アクションに対して行った詳細または状態の更新は、すべてのグループの評価によって取得されます。 技術的な改善アクション以外の更新プログラムは、適用するグループ内の評価によって認識されます。 これにより、1 つの改善アクションを実装し、複数の要件を同時に満たすことができます。

### <a name="create-a-group"></a>グループを作成する

新しい評価の作成中にグループを作成できます。 グループをスタンドアロン エンティティとして作成することはできません。

### <a name="what-to-know-when-working-with-groups"></a>グループを操作するときに知っておくべきこと

- グループには、少なくとも 1 つの評価が含まれている必要があります。
- グループ名は組織内で一意である必要があります。
- グループにはセキュリティ プロパティがありません。 すべてのアクセス許可は評価に関連付けられます。
- グループに評価を追加すると、グループ化を変更することはできません。
- 既存のグループに新しい評価を追加すると、そのグループの評価の共通情報が新しい評価にコピーされます。
- 同じグループ内のさまざまな評価の関連評価コントロールは、完了すると自動的に更新されます。
- グループには同じ認定または規制の評価を含めることができますが、各グループに含めることができる評価は、特定の製品と認定のペアに対して 1 つだけです。 たとえば、グループにOffice 365と NIST CSF の 2 つの評価を含めることはできません。 1 つのグループに同じ製品に対して複数の評価を含めることができるのは、それぞれに対応する認定または規制が異なる場合のみです。
- 評価を削除すると、その評価とグループの間の関係が解除されます。
- グループを削除することはできません。

## <a name="understand-templates-before-creating-assessments"></a>評価を作成する前にテンプレートを理解する

評価テンプレートには、さまざまなプライバシー規制と標準の認定に基づいて、評価のコントロールとアクションの推奨事項が含まれています。 組織は、ライセンス契約に応じて、少なくとも 1 つ以上の **テンプレート** を使用できます。 組織では、追加 **の Premium** テンプレートを購入することもできます。

各テンプレートは、Microsoft 365 (または使用可能な他の Microsoft 製品) で使用するためのバージョンと、使用する他の製品を評価するように調整できるユニバーサル バージョンの 2 つのバージョンで存在します。 評価する製品に適したテンプレートの種類を選択できます。

テンプレートの詳細については、 [コンプライアンス マネージャーの評価テンプレートの詳細を参照してください](compliance-manager-templates.md)。

## <a name="create-assessments"></a>評価を作成する

> [!NOTE]
> グローバル管理者、コンプライアンス マネージャー管理、またはコンプライアンス マネージャーの評価者ロールを持つユーザーのみが、評価を作成および変更できます。 [ロールとアクセス許可](compliance-manager-setup.md#set-user-permissions-and-assign-roles)の詳細については、こちらを参照してください。

開始する前に、割り当てるグループがわかっているか、この評価用に新しいグループを作成する準備ができていることを確認してください。 [グループと評価](#understand-groups-before-creating-assessments)に関する詳細を読みます。

評価を作成するには、ガイド付きプロセスを使用してテンプレートを選択し、関連する製品を指定します。 [ **評価]** ページでは、 **推奨される評価の追加** から始めることをお勧めします。これにより、組織の最も関連性の高い評価を一度に特定して迅速に設定できます。 [評価の **追加]** を選択して、一度に 1 つずつ評価を設定することもできます。 次の手順に従って、評価の構築を開始します。

#### <a name="create-assessments-based-on-recommendations-for-your-org-type"></a>組織の種類の推奨事項に基づいて評価を作成する

コンプライアンス マネージャーは、組織に最も関連する可能性がある評価を示すことができます。 組織の業界と場所に関する基本情報を提供する場合は、300 を超えるテンプレートのライブラリから使用するテンプレートをお勧めします。 複数の評価を一度に簡単にセットアップするために推奨されるテンプレートの中から選択するだけです。

推奨事項に基づいて 1 つ以上の評価を作成するには、[評価] ページから [ **推奨される評価の追加** ] を選択し、次 **の** 手順に従います。

- 組織を識別する 1 つ以上の業界を選択し、[**次へ**] を選択します。
- 組織の場所の 1 つ以上のリージョンを選択し、[**次へ**] を選択します。
- [ **評価の選択** ] 画面で、[ **推奨されるテンプレート** ] の横にあるドロップダウン矢印を選択して、組織に適用すると思う評価の一覧を表示します。 評価の作成に使用するテンプレートの横にあるボックスをオンにし、[ **次へ**] を選択します。
- 最終的な選択内容を確認し、[ **推奨評価の追加]** を選択して新しい評価を作成します。

#### <a name="create-an-assessment-using-a-guided-process"></a>ガイド付きプロセスを使用して評価を作成する

1. [ **評価] ページで** 、[ **評価の追加**] を選択します。 これにより、評価作成ウィザードに移動します。

2. [ **基本テンプレート** ] 画面で、[ **テンプレートの選択** ] を選択して、評価用のテンプレートを選択します。

3. ポップアップ ウィンドウで、評価の基準となる規制または認定のテンプレートを選択します。 含まれるカテゴリと Premium カテゴリに分割されたテンプレートの一覧 ([詳細を取得](compliance-manager-templates.md#template-availability-and-licensing)します)。 ポップアップ ウィンドウの上部にある **[アクティブ化された/ライセンスされたテンプレート** ] カウンターには、使用可能な合計数のうち使用しているテンプレート、または組織が使用する方法が表示されます ([詳細については、こちらを参照](compliance-manager-templates.md#active-and-inactive-templates)してください)。選択したテンプレートの横にあるラジオ ボタンを選択し、[ **保存**] を選択します。 **[基本テンプレート**] 画面に戻り、テンプレートの詳細を確認し、[**次へ**] を選択して続行します。

4. **製品、名前、およびグループ:** これらのプロパティを設定して評価を識別し、評価する製品を選択し、グループに割り当てます。

    - **製品**: 評価を適用する製品を選択します。 Microsoft 365 用に設計されたテンプレートなど、Microsoft テンプレートを使用している場合は、適切な製品を示すためにこのフィールドが設定され、変更できません。 ユニバーサル テンプレートを使用している場合は、新しい製品に対してこの評価を作成するか、コンプライアンス マネージャーで既に定義したカスタム製品を作成するかを選択します。 新しい製品を選択する場合は、その名前を入力します。 ユニバーサル テンプレートを使用する場合は、定義済みの Microsoft 製品を選択できないことに注意してください。
    - **評価名: [** 評価名] フィールドに評価の **名前** を入力します。 評価名はグループ内で一意である必要があります。 評価の名前が特定のグループ内の別の評価の名前と一致する場合は、別の名前を作成するように求めるエラーが表示されます。
    - **グループ**: 評価をグループに割り当てます。 以下のどちらかの方法で実行できます。
        - [ **既存のグループを使用して** 、既に作成したグループに割り当てる] を選択します。または
        - [ **新しいグループの作成** ] を選択して新しいグループを作成し、この評価をそのグループに割り当てます。
            - グループの名前を決定し、ラジオ ボタンの下のフィールドに入力します。
            - 適切なボックスを選択すると、実装やテストの詳細やドキュメントなど、 **既存のグループからデータをコピー** できます。

    完了したら、[**次へ**] を選択します。

5. **確認と完了:** 選択内容を確認し、必要な編集を行います。 準備ができたら、[評価の作成] を選択 **します**。

次の画面では、評価が作成されたことを確認します。 **[完了]** を選択すると、新しい評価の詳細ページに移動します。

[評価の **作成**] を選択した後に [**評価の失敗] 画面が表示される** 場合は、[**再試行**] を選択して評価を再作成します。

評価の詳細ページの右上隅にある **[名前の編集]** ボタンを選択すると、作成後に [評価の](#monitor-assessment-progress-and-controls)名前を変更できます。

## <a name="monitor-assessment-progress-and-controls"></a>評価の進行状況と制御を監視する

各評価には、評価の完了の進行状況を一目で確認できる詳細ページがあります。 このページには、コントロールの完了の進行状況と、それらのコントロール内の主要な改善アクションのテスト状態が表示されます。

### <a name="overview-tab"></a>[概要] タブ

[概要] タブには、評価の完了に対する割合を示すグラフが含まれています。 このグラフには、自分が所有するアクションのポイントと、Microsoft が所有するアクションのポイントの内訳が含まれているため、評価を完了するために必要なポイントの数を確認できます。

評価のコントロールの主な改善アクションは、ポイントを獲得するための最大の潜在的な影響の順序で一覧表示されます。 関連するグラフでは、改善アクションの集計されたテスト状態が詳細に表示されるため、テストされた内容と実行する必要がある作業をすばやく測定できます。

個々の改善アクションにアクセスするには、[ **コントロール** ] タブまたは [ **改善アクション** ] タブにアクセスします。

### <a name="controls-tab"></a>コントロール タブ

[コントロール] タブには、評価にマップされた各コントロールの詳細情報が表示されます。 **コントロールの状態内訳** グラフには、ファミリ別のコントロールの状態が表示されるため、どのコントロールのグループに注意が必要かを一目で確認できます。

グラフの下にあるテーブルには、評価内の各コントロールに関する詳細情報が一覧表示されます。 コントロールは、コントロール ファミリによってグループ化されます。 各ファミリ名を展開して、含まれる個々のコントロールを表示します。 各コントロールの一覧には、次の情報が含まれます。

- **コントロールのタイトル**
- **状態**: コントロール内の改善アクションのテスト状態を反映します。
  - **成功** - すべての改善アクションのテスト状態が "合格" であるか、少なくとも 1 つが渡され、残りが "範囲外" である
  - **失敗 -** 少なくとも 1 つの改善アクションのテスト状態が "失敗しました"
  - **なし** - すべての改善アクションがテストされていません
  - **範囲外** - すべての改善アクションがこの評価の範囲外です
  - **進行中** - 改善アクションには、上記以外の状態があります。これには、"進行中"、"部分的なクレジット"、または "検出されない" が含まれる可能性があります。
- **コントロール ID**: 対応する規制、標準、またはポリシーによって割り当てられたコントロールの識別番号
- **達成されたポイント**: アクションを完了して獲得したポイントの数。達成可能なポイントの合計数のうち
- **アクション**: 実行するアクションの合計数のうち、完了したアクションの数
- **Microsoft アクション**: Microsoft によって完了されたアクションの数

コントロールの詳細を表示するには、そのコントロールをテーブル内の行から選択します。 コントロールの詳細ページには、そのコントロール内のアクションのテスト状態を示すグラフが表示されます。 グラフの下の表は、そのコントロールの主な改善アクションを示しています。

一覧から改善アクションを選択して、改善アクションの詳細ページにドリルダウンします。 詳細ページには、テストの状態と実装に関する注意事項が表示され、推奨されるソリューションを起動します。

### <a name="your-improvement-actions-tab"></a>[改善アクション] タブ

改善アクションのタブには、組織によって管理されている評価のすべてのコントロールが一覧表示されます。 ステータス バーには、評価の改善アクションの集計されたテスト状態が詳細に表示されるため、テストされた内容と実行する必要がある作業をすばやく測定できます。 バーの下には、改善アクションと主な詳細の完全な一覧が表示されます。たとえば、テストの状態、潜在的なポイントと獲得ポイントの数、関連する規制と標準、適用可能なソリューション、アクションの種類、コントロール ファミリなどです。 [アクションがコンプライアンス スコアに与える影響](compliance-score-calculation.md#action-types-and-points)について詳しくは、こちらをご覧ください。

改善アクションを選択して詳細ページを表示し、[ **今すぐ起動]** リンクを選択して、アクションを実行するソリューションを開きます。

### <a name="microsoft-actions-tab"></a>[Microsoft アクション] タブ

Microsoft 製品をサポートするテンプレートに基づく評価の [Microsoft アクション] タブが表示されます。 Microsoft によって管理されている評価内のすべてのアクションが一覧表示されます。 一覧には、テストの状態、全体的なコンプライアンス スコアに貢献するポイント、関連する規制と標準、適用可能なソリューション、アクションの種類、コントロール ファミリなど、主要なアクションの詳細が表示されます。 改善アクションを選択して詳細ページを表示します。

[コントロールと改善アクションの追跡とスコア付け方法](compliance-score-calculation.md)の詳細について説明します。

## <a name="accept-updates-to-assessments"></a>評価の更新を受け入れる

評価で更新プログラムを利用できる場合は、通知が表示され、更新を受け入れるか、後で延期するかを選択できます。

更新は、Microsoft 365 で使用するように設計されたテンプレートなど、Microsoft テンプレートに基づく評価に使用できます。 組織が他の製品を評価するためにユニバーサル テンプレートを使用している場合、継承はサポートされない可能性があります。 詳細については、「 [評価テンプレートの拡張](compliance-manager-templates-extend.md)」を参照してください。

### <a name="what-causes-an-update"></a>更新の原因

評価の更新は、スコアリングに影響を与える基になるテンプレートの変更がある場合に発生します。 変更には、規制の変更や製品の変更に基づく制御マッピングまたはその他のガイダンスの調整が含まれる場合があります。 評価の更新は、組織 ( [カスタム テンプレートの変更](compliance-manager-templates-modify.md)時など) と Microsoft から行うことができます。

延長したコンプライアンス マネージャー テンプレートを Microsoft が更新した場合、評価は更新プログラムを受け入れると継承されます。 評価を延長すると、評価に適用した追加の属性が保持されます。

作成したカスタム評価は、Microsoft からテンプレートの更新プログラムを受け取りません。 カスタム評価は改善アクションの更新プログラムを受け取ることができますが、評価と改善アクションの間のマッピングを制御するための Microsoft 更新プログラムは、カスタム テンプレートには適用されません。

> [!NOTE]
> 評価の更新は、グループ レベルでのみ適用されます。 2 つの異なるグループに存在する同じテンプレートから構築された 2 つの評価がある場合、各評価には保留中の更新通知が表示され、それぞれのグループ内の各評価の更新を個別に受け入れる必要があります。

#### <a name="where-youll-see-assessment-update-notifications"></a>評価の更新通知が表示される場所

評価の詳細ページには、更新プログラムを含む評価の横に **[保留中の更新** ] ラベルも表示されます。 その評価を選択して詳細ページに移動します。

評価の詳細ページの上部付近にあるメッセージは、その評価で更新プログラムを利用できることを示しています。 バナーの [ **更新の確認** ] ボタンを選択して、特定の変更を確認し、更新を承諾または延期します。

評価の詳細ページには、その横に **[保留中の更新]** ラベルを持つ改善アクションが一覧表示される場合もあります。 これらの更新プログラムは、改善アクション自体に対する特定の変更のためであり、個別に受け入れる必要があります。 詳細については、 [改善アクションに関する更新プログラムの同意](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions) に関するページを参照してください。

#### <a name="review-update-to-accept-or-defer"></a>更新プログラムを確認して承諾または延期する

評価の詳細ページから **[更新の確認** ] を選択すると、画面の右側にポップアップ ウィンドウが表示されます。 ポップアップ ウィンドウには、保留中の更新に関する以下の重要な詳細が表示されます。

- テンプレート タイトル
- 更新プログラムのソース (Microsoft、組織、または特定のユーザー)
- 更新プログラムが作成された日付
- 更新プログラムの概要
- コンプライアンス スコアへの影響、評価の完了に向けた進行状況の量、改善アクションとコントロールに対する変更の特定の数など、変更に関する具体的な詳細。

**[更新されたテンプレート**] コマンドを選択すると、保留中の更新プログラムを含むテンプレートのバージョンのコントロール データを含む Excel ファイルがダウンロードされます。 **[現在のテンプレート**] コマンドを選択すると、更新プログラムなしで既存のテンプレートのファイルがダウンロードされます。

更新プログラムを受け入れ、評価に変更を加えるには、[ **更新を受け入れる**] を選択します。 受け入れられた変更は永続的です。

**[キャンセル]** を選択した場合、更新プログラムは評価に適用されません。 ただし、 **更新を** 受け入れるまで、保留中の更新通知が引き続き表示されます。

**更新プログラムを受け入れることをお勧めする理由**

更新プログラムを受け入れることは、ソリューションの使用に関する最新のガイダンスを確実に提供し、適切な改善アクションを実行して、認定資格の要件を満たすのに役立ちます。

**更新プログラムを延期する理由**

評価を完了する途中の場合は、制御マッピングを中断する可能性がある評価の更新を受け入れる前に、その評価の作業が完了していることを確認することをお探しの場合があります。 後で更新プログラムを延期するには、レビュー更新ポップアップ ウィンドウで **[キャンセル]** を選択します。

## <a name="export-an-assessment-report"></a>評価レポートをエクスポートする

組織内のコンプライアンス関係者、または外部監査人および規制者向けの評価を Excel ファイルにエクスポートできます。 評価の詳細ページで、ページの上部付近にある [ **レポートの生成** ] ボタンを選択し、保存して共有できる Excel ファイルを作成します。

レポートは、エクスポートの日付と時刻に関する評価のスナップショットです。 これには、実装状態、テスト日、テスト結果など、お客様と Microsoft の両方によって管理されるコントロールの詳細が含まれています。

## <a name="delete-an-assessment"></a>評価を削除する

評価を削除すると、評価ページの一覧から削除されます。 評価の削除に関する重要な点に注意してください。

- **評価の削除は永続的です。元に戻すことはできません。** 同じ評価をもう一度使用する場合は、それを再作成する必要があります。
- 評価の改善アクションが他の評価に表示されない場合、評価が削除されると削除されます。
- 評価 [を完全に削除する](#export-an-assessment-report) 前に、評価のレポートをエクスポートすることをお勧めします。

評価を削除するには、次の手順に従います。

1. **評価** ページから、削除する評価を選択して、その評価の詳細ページを開きます。

2. 画面の右上隅にある [ **評価の削除** ] を選択します。

3. 評価を完全に削除することを確認するウィンドウが表示されます。 [ **評価の削除]** を選択してウィンドウを閉じます。 コンプライアンス マネージャーから評価が削除されたことを示す確認ウィンドウが表示されます。

> [!NOTE]
> すべての評価を削除することはできません。 コンプライアンス マネージャーが正常に機能するには、少なくとも 1 つの評価が必要です。 削除する評価が唯一の評価である場合は、他の評価を削除する前に別の評価を追加します。
