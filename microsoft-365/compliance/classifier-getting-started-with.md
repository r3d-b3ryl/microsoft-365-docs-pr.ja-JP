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
description: Microsoft 365 trainable クラシファイアは、コンテンツのさまざまな種類を認識するために学習することができます。 分類子がトレーニングされると、結果が正確であることを確認できます。 次に、これを使用して組織のコンテンツを検索し、それを分類して、保持または機密ラベルを適用したり、データ損失防止 (DLP) またはアイテム保持ポリシーに含めたりします。
ms.openlocfilehash: 6706fe25194191d57ffd91f07f13d22fe5ec6cfd
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826258"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a>トレーニング可能な分類子の使用を開始する (プレビュー)

コンテンツを保護し、適切に処理するために、コンテンツの分類とラベル付けを行うことは、情報保護の統制の出発点となります。 Microsoft 365 には、コンテンツを分類するための3つの方法があります。

## <a name="manually"></a>手動

このメソッドには、人間の判断とアクションが必要です。 管理者は、既存のラベルと機密情報の種類を使用するか、独自に作成して発行することができます。 ユーザーおよび管理者は、発生時にコンテンツに適用されます。 その後、コンテンツを保護し、廃棄を管理できます。

## <a name="automated-pattern-matching"></a>自動パターンマッチング

この分類機構のカテゴリには、コンテンツの検索が含まれます。

- キーワードまたはメタデータ値 (キーワードクエリ言語)
- ソーシャルセキュリティ、クレジットカード、または銀行口座番号[(機密情報の種類)](what-the-sensitive-information-types-look-for.md)など、以前に識別された機密情報のパターンを使用する
- テンプレートのバリエーションであるためにアイテムを認識する[(ドキュメントのフィンガープリント)](document-fingerprinting.md)
- 正確な文字列の存在[(正確なデータ一致)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)の使用

機密情報と保持ラベルを自動的に適用して、[データ損失防止 (DLP)](data-loss-prevention-policies.md)と[アイテム保持ポリシー](retention-policies.md)でコンテンツを使用できるようにすることができます。

## <a name="trainable-classifiers"></a>Trainable 分類子

この分類方法は、手動または自動のパターン一致方式のどちらかによって簡単に識別できないコンテンツに特に適しています。 この分類の方法は、アイテムに基づいてアイテムを識別する分類子をトレーニングすることになります (アイテムに含まれる要素ではありません) (パターンマッチング)。 分類子は、分類するコンテンツの数百の例を参照して、コンテンツの種類を識別する方法を学習します。 最初に、カテゴリに含まれている例を示します。 それらを処理したら、一致する比較例と一致しない例の両方を組み合わせてテストします。 その後、分類子は、指定されたアイテムが作成中のカテゴリに属するかどうかについての予測を行います。 その後、その結果を確認し、陽性、ネガ、偽陽性、誤検知を並べ替えて、予測の精度を高めることができます。 トレーニング対象の分類子を発行すると、SharePoint Online、Exchange、および OneDrive などの場所にあるアイテムが並べ替えられ、コンテンツが分類されます。

> [!IMPORTANT]
> 組み込み分類子と trainable の両方の分類子は、条件と[通信のコンプライアンス](communication-compliance.md)[に基づいて、自動適用の保持ラベルポリシー](labels.md#applying-a-retention-label-automatically-based-on-conditions)の条件として使用できます。 機密ラベルは、組み込みの分類子を条件としてのみ使用できます。詳細については、「[コンテンツに機密ラベルを自動的に適用](apply-sensitivity-label-automatically.md)する」を参照してください。

> [!IMPORTANT]
> Trainable 分類子は、暗号化されておらず英語になっているアイテムに対してのみ機能します。

### <a name="licensing-requirements"></a>ライセンス要件

Trainable 分類子は、Microsoft 365 E5 または E5 準拠の機能です。 それらを利用するには、これらのサブスクリプションのいずれかが必要です。

## <a name="types-of-classifiers"></a>分類子の種類

組み込みの分類子と trainable 分類子があります。 Trainable クラシファイアを公開された状態にするには、トレーニングに必要な時間がかかります。 分類子の使用を開始するために、Microsoft 365 にはいくつかの組み込み分類子が付属しています。

> [!NOTE]
> 分類とラベル付けワークフローに組み込みの分類子を使用する前に、分類の予測が期待どおりになっていることを確認するために、カテゴリに適合していると思われる組織のコンテンツのサンプルに照らしてテストする必要があります。

### <a name="understanding-built-in-classifiers"></a>組み込み分類子について

Microsoft 365 には、次の6つの組み込み分類子が付属しています。

- **不快な言葉**: profanities、slurs、taunts、および偽装式を含むテキストアイテムを検出します (これは、より不快な用語と同じ意味を持つ式です)。
- **履歴書**: 申請者の個人、教育、専門資格、作業経験、その他の個人を特定できる情報のテキストアカウントであるアイテムを検出します。
- **ソースコード**: GitHub で使用されている上位25台のコンピュータプログラミング言語で記述された命令およびステートメントのセットを含むアイテムを検出します。

|言語名|||||
|---------|---------|---------|---------|---------|
|『|C        |C#       |+     |Clojure  |
|CoffeeScript|CSS     |移動       |Haskell |HTML     |
|Java     |JavaScript|Lua      |MATLAB   |Objective-C|
|Perl     |PHP      |Python   |R        |Ruby     |
|スケール a    |Shell    |実現    |テックス      |Vim スクリプト|


- **嫌がらせ**: 次の特徴に基づいて、1人または複数の個人を対象とした不快感のある言語のテキストアイテムの特定のカテゴリを検出します。競合、ethnicity、宗教、国内原産者、性別、性的なオリエンテーション、年齢、障碍。
- **不適切な用語**: 多くの人々を embarrass する式を含む、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。
- **脅威**: 暴力をコミットする脅威に関連する、不快感を与える、個人またはプロパティに対する物理的な損傷または損害をもたらす、不快な言語のテキストアイテムの特定のカテゴリを検出します。

これらは、 **Microsoft 365 コンプライアンスセンター** > **データ分類 (プレビュー)** > **Trainable 分類子**ビューに、の`Ready to use`状態と共に表示されます。

![分類子-すぐに使用できる分類子](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 不快な言葉、嫌がらせ、冒涜、および脅威の分類子は、検索可能なテキストのみで機能することに注意してください。  さらに、言語と文化的な標準が絶えず変化し、これらの現実からは、これらの分類子を裁量で更新する権利を Microsoft が留保します。 分類子は、お客様の組織が不快な言葉や使用されている他の言語を監視するのに役立ちますが、分類子は、そのような言語の結果に対応していません。そのような言語。 お客様の組織は、Microsoft またはその子会社ではなく、事前に訓練された分類子によって識別されるコンテンツの監視、実施、ブロック、削除、保持に関連するすべての意思決定に対して責任を負うことになります。

#### <a name="process-flow-for-using-built-in-classifiers"></a>組み込み分類子を使用するためのプロセスフロー

組み込みの分類子をトレーニングする必要はありませんが、コンプライアンスソリューションで使用する前に、必要なコンテンツの種類を特定することを確認する必要があります。 事前に学習した分類子のテストは、このフローに従います。

![事前に学習した分類子をテストするプロセスフロー](../media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a>Trainable 分類子について

組み込みの分類子がニーズに合わない場合は、独自の分類子を作成してトレーニングできます。 独自の作成に関しては、非常に多くの作業が必要になりますが、組織のニーズに応じてより適切にカスタマイズできます。 事前に学習した分類子の使用方法の詳細については、「[組み込みの分類子を使用](classifier-using-a-ready-to-use-classifier.md)する」を参照してください。

> [!IMPORTANT]
> Trainable 分類子を作成したユーザーのみが、その分類子によって行われた予測をトレーニングし、確認することができます。

#### <a name="process-flow-for-creating-trainable-classifiers"></a>Trainable 分類子を作成するためのプロセスフロー

Trainable 分類子を作成して、アイテム保持ポリシー、通信監督などのコンプライアンスソリューションで使用するために、このフローに従います。 Trainable 分類子を作成する方法の詳細については、「 [trainable クラシファイアを作成](classifier-creating-a-trainable-classifier.md)する」を参照してください。

![プロセスフロー trainable クラシファイア](../media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a>関連項目

- [保持ラベル](labels.md)
- [アイテム保持ポリシー](retention-policies.md)
- [データ損失防止 (DLP)](data-loss-prevention-policies.md)
- [機密ラベル](sensitivity-labels.md)
- [機密情報の種類](what-the-sensitive-information-types-look-for.md)
- [ドキュメントのフィンガープリント](document-fingerprinting.md)
- [正確なデータ一致](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
