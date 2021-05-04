---
title: トレーニング可能な分類子の詳細
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
ms.openlocfilehash: 1881e4de87fd41f21bb1f2236d46391b3a1ed785
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114053"
---
# <a name="learn-about-trainable-classifiers"></a>トレーニング可能な分類子の詳細

コンテンツを適切に保護および処理できるようにコンテンツを分類およびラベル付けすることは、情報保護に対するトレーニングの出発点です。 Microsoft 365 には、コンテンツを分類する 3 つの方法があります。

## <a name="manually"></a>手動

この方法では、人間の判断と行動が必要です。 管理者は、既存のラベルと機密情報の種類を使用するか、独自のラベルを作成して公開することができます。 ユーザーと管理者は、遭遇したコンテンツをそれらに適用します。 その後、コンテンツを保護し、その処分を管理できます。

## <a name="automated-pattern-matching"></a>自動パターン マッチング

分類メカニズムのこのカテゴリには、次の方法でコンテンツを検索する方法が含まれます。

- キーワードまたはメタデータ値 (キーワード クエリ言語)。
- 社会保障、クレジット カード、銀行口座番号 (機密情報の種類エンティティ定義) などの機密情報の以前に識別されたパターン [を使用する](sensitive-information-type-entity-definitions.md)。
- アイテムがテンプレートのバリエーション (ドキュメントフィンガー印刷) なので、アイテム [を認識します](document-fingerprinting.md)。
- 正確な文字列 (完全なデータ一 [致) の存在を使用します](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。

その後、感度ラベルと保持ラベルを自動的に適用して、「データ損失防止について[](dlp-learn-about-dlp.md)学習する」でコンテンツを使用し、保持ラベルのポリシーを[自動的に適用できます](apply-retention-labels-automatically.md)。

## <a name="classifiers"></a>分類子

この分類方法は、手動または自動のパターン マッチング方法では簡単に識別できないコンテンツに特に適しています。 この分類方法は、アイテムに含まれる要素ではなく、アイテムが何であるかに基づいてアイテムを識別するように分類子をトレーニングすることです (パターン マッチング)。 分類子は、分類したいコンテンツの数百の例を見て、コンテンツのタイプを識別する方法を学びます。 それを間違いなくカテゴリーにある例に与えることから始めます。 それらを処理したら、一致する例と一致しない例の両方を組み合わせてテストします。 次に、分類子は、特定のアイテムが作成中のカテゴリに該当するかどうかを予測します。 次に、その結果を確認し、予測の精度を高めるのに役立つ、真の陽性、真の負、誤検知、および偽陰性を並べ替えて確認します。 

分類子を発行すると、SharePoint Online、Exchange、OneDrive のような場所のアイテムを並べ替え、コンテンツを分類します。 分類子を発行した後、最初のトレーニング プロセスと同様のフィードバック プロセスを使用して、分類子をトレーニングし続けできます。

### <a name="where-you-can-use-trainable-classifiers"></a>トレーニング可能な分類子を使用できる場所
組み込みの分類子とトレーニング可能な分類子の両方が[、Office](apply-sensitivity-label-automatically.md)の感度ラベル付き自動ラベル付け、条件に基づく保持[](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)ラベル ポリシーの自動適用、および通信コンプライアンスの条件[](communication-compliance.md)として使用できます。 

感度ラベルは、条件として分類子を使用できます。「コンテンツに自動的に感度ラベルを適用 [する」を参照してください](apply-sensitivity-label-automatically.md)。

> [!IMPORTANT]
> 分類子は、暗号化されていないアイテムと英語のアイテムでのみ動作します。

## <a name="types-of-classifiers"></a>分類子のタイプ

- **事前トレーニング済みの分類子** - Microsoft は、トレーニングなしで使用を開始できる多数の分類子を作成および事前トレーニングしました。 これらの分類子は、 の状態で表示されます `Ready to use` 。
- **カスタム分類子** - 事前トレーニング済みの分類子がカバーする範囲を超える分類ニーズがある場合は、独自の分類子を作成してトレーニングできます。

### <a name="pre-trained-classifiers"></a>事前トレーニング済みの分類子

Microsoft 365には、5 つの事前トレーニング済み分類子が付属しています。

> [!CAUTION]
> 多くの誤 **検知が生成** されたため、攻撃言語の事前トレーニング済み分類子は廃止されています。 使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。 代わりに **、Threat** **、Profanity、** および **Harassment** の事前トレーニング済みの分類子を使用することをお勧めします。

- **履歴書**: 申請者の個人、教育、専門的な資格、職歴、その他の個人を特定する情報のテキスト アカウントであるアイテムを検出します。
- **ソース コード**: コンピューターで使用されている上位 25 のコンピューター プログラミング言語で記述された一連の命令とステートメントを含むアイテムをGitHub
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
> ソース コードは、テキストの大部分がソース コードである場合に検出するトレーニングを受けています。 プレーン テキストと相互に存在するソース コード テキストは検出されません。

- **嫌** がらせ : 人種、民族、宗教、出身国、性別、性的指向、年齢、障がい者の特性に基づいて、1 人または複数の個人を対象とする攻撃行為に関連する攻撃的な言語テキスト 項目の特定のカテゴリを検出します。
- **冒とく**: ほとんどの人を困らせる表現を含む不快な言語テキスト アイテムの特定のカテゴリを検出します。
- **脅威**: 暴力を行う、または人や財産に物理的な危害や損害を与える脅威に関連する攻撃的な言語テキスト アイテムの特定のカテゴリを検出します。

これらは、コンプライアンス センター **のデータMicrosoft 365** の状態を持つトレーニング可能な分類子  >    >  ビューに表示されます `Ready to use` 。

![分類子-事前トレーニング済み分類子](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 不快な言葉、ハラスメント、冒涜的表現、および脅威の分類は、検索可能なテキストでのみ機能し、網羅的または完全ではないことに注意してください。  さらに、言語と文化の基準は絶えず変化し、これらの現実に照らして、Microsoft は独自の裁量でこれらの分類子を更新する権利を留保します。 分類子は、不快な言語やその他の使用言語を監視するのに役立ちますが、分類子は、そのような言語の結果に対処するものではなく、そのような言語の使用を監視または応答する唯一の手段を組織に提供するものではありません。 事前にトレーニングされた分類子によって識別されたコンテンツの監視、施行、ブロック、削除、および保持に関するすべての決定は、Microsoft またはその子会社ではなく、お客様の組織の責任となります。

### <a name="custom-classifiers"></a>カスタム分類子

事前トレーニング済みの分類子がニーズを満たしない場合は、独自の分類子を作成してトレーニングできます。 独自に作成するには、はるかに多くの作業が必要になりますが、組織のニーズに合わせてカスタマイズできます。 

たとえば、次のトレーニング可能な分類子を作成できます。
 
- 法的文書 - 弁護士クライアント特権、終了セット、作業明細書など
- 戦略的ビジネス ドキュメント - プレスリリース、合併および買収、取引、ビジネスまたはマーケティング計画、知的財産、特許、デザイン ドキュメントなど
- 価格情報 - 請求書、価格見積もり、作業オーダー、入札ドキュメントなど 
- 財務情報 - 組織の投資、四半期または年次の結果など    

#### <a name="process-flow-for-creating-custom-classifiers"></a>カスタム分類子を作成するためのプロセス フロー

保持ポリシーや通信監督など、コンプライアンス ソリューションで使用する分類子の作成と発行は、このフローに従います。 カスタムトレーニング可能な分類子の作成の詳細については、「カスタム分類子の作成 [」を参照してください](classifier-get-started-with.md)。

![プロセス フローのカスタム分類子](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>分類子の再トレーニング

すべてのカスタム分類子と一部の事前トレーニング済み分類子の精度を向上させるために、ユーザーが実行する分類の精度に関するフィードバックを提供できます。 これを再トレーニングと呼び、このワークフローに従います。

![分類子の再トレーニング ワークフロー](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>関連項目

- [保持ラベル](retention.md)
- [データ損失防止について](dlp-learn-about-dlp.md)
- [秘密度ラベル](sensitivity-labels.md)
- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
- [ドキュメントの指の印刷](document-fingerprinting.md)
- [完全なデータ一致](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
