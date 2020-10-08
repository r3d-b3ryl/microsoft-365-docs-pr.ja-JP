---
title: トレーニング可能な分類子の詳細 (プレビュー)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 トレーニング可能な分類子は、陽性と陰性のサンプルを提供することによって、さまざまなタイプのコンテンツを認識するトレーニング ツールです。 分類子がトレーニングされると、その結果が正しいことを確認します。 次に、それを使用して組織のコンテンツを検索し、分類して保持または秘密度ラベルを適用するか、データ損失防止 (DLP) または保持ポリシーに含めます。
ms.openlocfilehash: 7abfbe101508d24e58464ff38b14ab87447001f0
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379309"
---
# <a name="learn-about-classifiers-preview"></a>分類子 (プレビュー) について

コンテンツを適切に保護および処理できるようにコンテンツを分類およびラベル付けすることは、情報保護に対するトレーニングの出発点です。 Microsoft 365 には、コンテンツを分類する 3 つの方法があります。

## <a name="manually"></a>手動

この方法では、人間の判断と行動が必要です。 管理者は、既存のラベルと機密情報の種類を使用するか、独自のラベルを作成して公開することができます。 ユーザーと管理者は、遭遇したコンテンツをそれらに適用します。 その後、コンテンツを保護し、その処分を管理できます。

## <a name="automated-pattern-matching"></a>自動パターン マッチング

この分類メカニズムのカテゴリには、コンテンツの検索が含まれます。

- キーワードまたはメタデータ値 (キーワードクエリ言語)。
- ソーシャルセキュリティ、クレジットカード、または銀行口座番号 [(機密情報の種類のエンティティ定義)](sensitive-information-type-entity-definitions.md)など、以前に識別された機密情報のパターンを使用します。
- テンプレートのバリエーションであるためにアイテムを認識する [(ドキュメントのフィンガープリント)](document-fingerprinting.md)。
- 正確な文字列の存在 [(正確なデータ一致)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)を使用します。

機密情報と保持ラベルを自動的に適用して、 [データ損失防止 (DLP)](data-loss-prevention-policies.md) および [保持ラベルの自動適用ポリシー](apply-retention-labels-automatically.md)で使用できるようにすることができます。

## <a name="classifiers"></a>器

この分類方法は、手動または自動のパターン マッチング方法では簡単に識別できないコンテンツに特に適しています。 この分類方法は、アイテムに含まれる要素ではなく、アイテムが何であるかに基づいてアイテムを識別するように分類子をトレーニングすることです (パターン マッチング)。 分類子は、分類したいコンテンツの数百の例を見て、コンテンツのタイプを識別する方法を学びます。 それを間違いなくカテゴリーにある例に与えることから始めます。 それらを処理したら、一致する例と一致しない例の両方を組み合わせてテストします。 次に、分類子は、特定のアイテムが作成中のカテゴリに該当するかどうかを予測します。 その後、結果を確認し、真陽性、真陽性、誤検知、誤検知を並べ替えて、予測の精度を高めることができます。 

分類子を発行すると、SharePoint Online、Exchange、および OneDrive などの場所にあるアイテムが並べ替えられ、コンテンツが分類されます。 分類子を発行した後は、最初のトレーニングプロセスに似たフィードバックプロセスを使用して、それを引き続きトレーニングできます。

### <a name="where-you-can-use-trainable-classifiers"></a>Trainable 分類子を使用できる場所
組み込み分類子と trainable 分類子は、両方とも、[条件](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)および[通信コンプライアンス](communication-compliance.md)に基づいて、[機密ラベルを使用した Office autolabeling](apply-sensitivity-label-automatically.md)の条件として使用できます。 

機密ラベルでは分類子を条件として使用できます。「 [機密ラベルをコンテンツに自動的に適用](apply-sensitivity-label-automatically.md)する」を参照してください。

> [!IMPORTANT]
> 分類子は、暗号化されておらず英語になっているアイテムに対してのみ機能します。

## <a name="types-of-classifiers"></a>分類子のタイプ

- 事前にトレーニングされた**分類子**-Microsoft は、トレーニングを実施せずに使用を開始できる分類子を作成し、事前にトレーニングを受けています。 これらの分類子は、の状態と共に表示され `Ready to use` ます。
- **カスタム分類子** -事前に訓練された分類子の範囲を超えて分類する必要がある場合は、独自の分類子を作成してトレーニングできます。

### <a name="pre-trained-classifiers"></a>事前にトレーニングした分類子

Microsoft 365 には、事前にトレーニングされた分類子が5つあります。

> [!CAUTION]
> 不快なのは、誤検知の数が多いので、 **不快感** を持つ言語の事前トレーニングされた分類子を廃止しています。 使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。 代わりに、 **脅威**、 **プロファニティ**、および **嫌がらせ** の事前トレーニング分類子を使用することをお勧めします。

- **履歴書**: 申請者の個人、教育、専門資格、作業経験、その他個人を識別する情報のテキストアカウントであるアイテムを検出します。
- **ソースコード**: GitHub で使用されている上位25台のコンピュータプログラミング言語で記述された命令およびステートメントのセットを含むアイテムを検出します。
    - ActionScript
    - C
    - C#
    - C++
    - Clojure
    - CoffeeScript
    - Go
    - Haskell
    - Java
    - JavaScript
    - Lua
    - MATLAB
    - Objective-C
    - Perl
    - PHP
    - Python
    - R
    - Ruby
    - Scala
    - Shell
    - Swift
    - Tex
    - Vim Script

> [!NOTE]
> ソースコードは、テキストの大部分がソースコードであるときに検出するためにトレーニングされています。 プレーンテキストが混在しているソースコードテキストは検出されません。

- **嫌がらせ**: 次の特徴に基づいて、1人または複数の個人を対象とした不快感を持つ、不快感を持つテキストアイテムの特定のカテゴリを検出します。競合、ethnicity、宗教、国内原産者、性別、性的なオリエンテーション、年齢、障碍
- **不適切な用語**: 多くのユーザーを embarrass する式を含む、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。
- **脅威**: 暴力を確定する脅威、または人またはプロパティに物理的な悪影響や損害を与えることに関連する脅威に関連する、不快な言語のテキストアイテムの特定のカテゴリを検出します。

これらは、[**Microsoft 365 コンプライアンス センター**]  >  [**データ分類 (プレビュー)**]  >  [**トレーニング可能な分類子**] ビューに表示され、ステータスは `Ready to use` です。

![分類子-事前トレーニング-分類子](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 不快な言葉、ハラスメント、冒涜的表現、および脅威の分類は、検索可能なテキストでのみ機能し、網羅的または完全ではないことに注意してください。  さらに、言語と文化の基準は絶えず変化し、これらの現実に照らして、Microsoft は独自の裁量でこれらの分類子を更新する権利を留保します。 分類子は、不快な言語やその他の使用言語を監視するのに役立ちますが、分類子は、そのような言語の結果に対処するものではなく、そのような言語の使用を監視または応答する唯一の手段を組織に提供するものではありません。 事前にトレーニングされた分類子によって識別されたコンテンツの監視、施行、ブロック、削除、および保持に関するすべての決定は、Microsoft またはその子会社ではなく、お客様の組織の責任となります。

### <a name="custom-classifiers"></a>カスタム分類子

事前に訓練された分類子がニーズに合わない場合は、独自の分類子を作成してトレーニングできます。 独自に作成するには、はるかに多くの作業が必要になりますが、組織のニーズに合わせてカスタマイズできます。

> [!IMPORTANT]
> 既定では、カスタムの分類子を作成したユーザーのみが、その分類子によって行われた予測を教育およびレビューすることができます。 他のユーザーが分類子予測をトレーニングおよびレビューできるようにする場合は、「 [他のユーザーにトレーニングとレビューの権限を付与](classifier-get-started-with.md#give-others-train-and-review-rights)する」を参照してください。

#### <a name="process-flow-for-creating-custom-classifiers"></a>カスタム分類子を作成するためのプロセスフロー

保持ポリシー、コミュニケーション監督など、コンプライアンスソリューションで使用する分類子を作成して発行するには、このフローに従います。 カスタム trainable 分類子を作成する方法の詳細については、「 [カスタム分類子を作成](classifier-get-started-with.md)する」を参照してください。

![プロセスフローカスタム分類子](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>再トレーニング分類子

ユーザーが実行する分類の精度に関するフィードバックを提供することにより、すべてのカスタム分類子と事前トレーニングされた分類子の精度を向上させることができます。 これは再トレーニングと呼ばれ、このワークフローに従います。

![分類子の再トレーニングワークフロー](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>関連項目

- [保持ラベル](retention.md)
- [データ損失防止 (DLP)](data-loss-prevention-policies.md)
- [機密ラベル](sensitivity-labels.md)
- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
- [ドキュメントのフィンガープリント](document-fingerprinting.md)
- [正確なデータ一致](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
