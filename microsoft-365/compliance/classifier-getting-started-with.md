---
title: トレーニング可能な分類子の使用を開始する (プレビュー)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 トレーニング可能な分類子は、陽性と陰性のサンプルを提供することによって、さまざまなタイプのコンテンツを認識するトレーニング ツールです。 分類子がトレーニングされると、その結果が正しいことを確認します。 次に、それを使用して組織のコンテンツを検索し、分類して保持または秘密度ラベルを適用するか、データ損失防止 (DLP) または保持ポリシーに含めます。
ms.openlocfilehash: ba24bbe76bce5e3a41345c80616a57d3fb67a5fc
ms.sourcegitcommit: 2fbcecaa60e9f551738b9235bd380af807a6681a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "44339915"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a>トレーニング可能な分類子の使用を開始する (プレビュー)

コンテンツを適切に保護および処理できるようにコンテンツを分類およびラベル付けすることは、情報保護に対するトレーニングの出発点です。 Microsoft 365 には、コンテンツを分類する 3 つの方法があります。

## <a name="manually"></a>手動

この方法では、人間の判断と行動が必要です。 管理者は、既存のラベルと機密情報の種類を使用するか、独自のラベルを作成して公開することができます。 ユーザーと管理者は、遭遇したコンテンツをそれらに適用します。 その後、コンテンツを保護し、その処分を管理できます。

## <a name="automated-pattern-matching"></a>自動パターン マッチング

この分類メカニズムのカテゴリには、次によるコンテンツの検索が含まれます。

- キーワードまたはメタデータ値 (キーワードクエリ言語)。
- ソーシャルセキュリティ、クレジットカード、または銀行口座番号[(機密情報の種類のエンティティ定義)](sensitive-information-type-entity-definitions.md)など、以前に識別された機密情報のパターンを使用します。
- テンプレートのバリエーションであるためにアイテムを認識する[(ドキュメントのフィンガープリント)](document-fingerprinting.md)。
- 正確な文字列の存在[(正確なデータ一致)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)を使用します。

次に、秘密度ラベルと保持ラベルを自動的に適用して、コンテンツを[データ損失防止 (DLP)](data-loss-prevention-policies.md) および[保持ポリシー](retention-policies.md)で使用できるようにします。

## <a name="trainable-classifiers"></a>トレーニング可能な分類子

この分類方法は、手動または自動のパターン マッチング方法では簡単に識別できないコンテンツに特に適しています。 この分類方法は、アイテムに含まれる要素ではなく、アイテムが何であるかに基づいてアイテムを識別するように分類子をトレーニングすることです (パターン マッチング)。 分類子は、分類したいコンテンツの数百の例を見て、コンテンツのタイプを識別する方法を学びます。 それを間違いなくカテゴリーにある例に与えることから始めます。 それらを処理したら、一致する例と一致しない例の両方を組み合わせてテストします。 次に、分類子は、特定のアイテムが作成中のカテゴリに該当するかどうかを予測します。 その後、その結果を確認し、陽性、陰性、偽陽性、偽陰性に仕分けし、その予測の正確性を高めます。 トレーニング済みの分類子を公開すると、SharePoint Online、Exchange、OneDrive などの場所にあるアイテムが並べ替えられ、コンテンツが分類されます。

### <a name="where-you-can-use-trainable-classifiers"></a>Trainable 分類子を使用できる場所
組み込みの分類子とトレーニング可能な分類子の両方が、[条件に基づく保持ラベル ポリシーの自動適用](labels.md#applying-a-retention-label-automatically-based-on-conditions)と[通信コンプライアンス](communication-compliance-configure.md)の条件として使用できます。 

機密ラベルは、組み込みの分類子を使用して、独自の分類子を条件として使用できます。「[機密ラベルをコンテンツに自動的に適用](apply-sensitivity-label-automatically.md)する」および「 [Office アプリの自動ラベル付け](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)」を参照してください。

> [!IMPORTANT]
> トレーニング可能な分類子は、暗号化されていない英語のアイテムでのみ機能します。

### <a name="licensing-requirements"></a>ライセンスの要件

トレーニング可能な分類子は、Microsoft 365 E5 または E5 コンプライアンス機能です。 それらを使用するには、これらのサブスクリプションのいずれかが必要です。

### <a name="pre-requisites"></a>前提条件

UI の trainable 分類子にアクセスするには、次のようにします。 
- グローバル管理者がテナントに対してオプトインを選択する必要がある
- 分類子を教育するには、コンプライアンス管理者ロールまたはコンプライアンスデータ管理者が必要

次のシナリオでは、trainable 分類子を使用するために、これらのアクセス許可を持つアカウントが必要になります。

- 保持ラベルポリシーシナリオ: RecordManagement および Retention Management の役割 
- 機密ラベルポリシーのシナリオ: セキュリティ管理者、コンプライアンス管理者、コンプライアンスデータ管理者
- コミュニケーションコンプライアンスポリシーのシナリオ: Insider リスク管理管理者、監督レビュー管理者 

## <a name="types-of-classifiers"></a>分類子のタイプ

組み込みの分類子とトレーニング可能な分類子があります。 トレーニング可能な分類子を公開可能な状態にするには、それをトレーニングするために時間を投資する必要があります。 分類子の使用を開始するために、Microsoft 365 にはいくつかの組み込みの分類子が付属しています。

> [!NOTE]
> 分類とラベル付けのワークフローで組み込みの分類子を使用する前に、カテゴリに適合すると思われる組織コンテンツのサンプルに対してテストし、分類予測が期待を満たしていることを確認する必要があります。

### <a name="understanding-built-in-classifiers"></a>組み込み分類子について

Microsoft 365 には、推奨される 5 つの組み込み分類子が付属しています。

> [!CAUTION]
> 組み込みの [**不快な言葉**] は、誤検知の数が多いため、廃止予定です。 使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。 代わりに、[**脅威**]、[**冒涜的表現**]、および [**ハラスメント**] の組み込み分類子を使用することをお勧めします。

- **履歴書**: 申請者の個人、教育、専門資格、作業経験、その他個人を識別する情報のテキストアカウントであるアイテムを検出します。
- **ソースコード**: GitHub で使用されている上位25台のコンピュータプログラミング言語で記述された命令およびステートメントのセットを含むアイテムを検出します。

|言語名|||||
|---------|---------|---------|---------|---------|
|ActionScript|C        |C#       |C++     |Clojure  |
|CoffeeScript|CSS     |Go       |Haskell |HTML     |
|Java     |JavaScript|Lua      |MATLAB   |Objective-C|
|Perl     |PHP      |Python   |R        |Ruby     |
|Scala    |Shell    |Swift    |Tex      |Vim Script|

> [!NOTE]
> ソースコードは、テキストの大部分がソースコードであるときに検出するためにトレーニングされています。 プレーンテキストが混在しているソースコードテキストは検出されません。

- **嫌がらせ**: 次の特徴に基づいて、1人または複数の個人を対象とした不快感を持つ、不快感を持つテキストアイテムの特定のカテゴリを検出します。競合、ethnicity、宗教、国内原産者、性別、性的なオリエンテーション、年齢、障碍
- **不適切な用語**: 多くのユーザーを embarrass する式を含む、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。
- **脅威**: 暴力を確定する脅威、または人またはプロパティに物理的な悪影響や損害を与えることに関連する脅威に関連する、不快な言語のテキストアイテムの特定のカテゴリを検出します。

これらは、[**Microsoft 365 コンプライアンス センター**]  >  [**データ分類 (プレビュー)**]  >  [**トレーニング可能な分類子**] ビューに表示され、ステータスは `Ready to use` です。

![分類子はすぐに使用できる分類子](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 不快な言葉、ハラスメント、冒涜的表現、および脅威の分類は、検索可能なテキストでのみ機能し、網羅的または完全ではないことに注意してください。  さらに、言語と文化の基準は絶えず変化し、これらの現実に照らして、Microsoft は独自の裁量でこれらの分類子を更新する権利を留保します。 分類子は、不快な言語やその他の使用言語を監視するのに役立ちますが、分類子は、そのような言語の結果に対処するものではなく、そのような言語の使用を監視または応答する唯一の手段を組織に提供するものではありません。 事前にトレーニングされた分類子によって識別されたコンテンツの監視、施行、ブロック、削除、および保持に関するすべての決定は、Microsoft またはその子会社ではなく、お客様の組織の責任となります。

#### <a name="process-flow-for-using-built-in-classifiers"></a>組み込み分類子を使用するためのプロセス フロー

組み込み分類子をトレーニングする必要はありませんが、コンプライアンス ソリューションで使用する前に、それらが必要とするコンテンツのタイプを識別できることを確認する必要があります。 このフローに従って、事前トレーニング済みの分類子のテストを行います。

![事前トレーニング済みの分類子をテストするプロセス フロー](../media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a>トレーニング可能な分類子について

組み込み分類子がニーズを満たさない場合は、独自の分類子を作成してトレーニングできます。 独自に作成するには、はるかに多くの作業が必要になりますが、組織のニーズに合わせてカスタマイズできます。 事前トレーニング済みの分類子の使用方法の詳細については、「[組み込み分類子の使用](classifier-using-a-ready-to-use-classifier.md)」をご覧ください。

> [!IMPORTANT]
> トレーニング可能な分類子を作成するユーザーのみが、その分類子によって行われた予測をトレーニングおよび確認できます。

#### <a name="process-flow-for-creating-trainable-classifiers"></a>トレーニング可能な分類子を作成するためのプロセス フロー

保持ポリシーや通信監督など、コンプライアンス ソリューションで使用するトレーニング可能な分類子の作成と公開はこのフローに従います。 トレーニング可能な分類子の作成の詳細については、「[トレーニング可能な分類子の作成](classifier-creating-a-trainable-classifier.md)」をご覧ください。

![プロセス フローのトレーニング可能な分類子](../media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a>関連項目


- [保持ラベル](labels.md)
- [保持ポリシー](retention-policies.md)
- [データ損失防止 (DLP)](data-loss-prevention-policies.md)
- [機密ラベル](sensitivity-labels.md)
- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
- [ドキュメントのフィンガープリント](document-fingerprinting.md)
- [正確なデータ一致](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
