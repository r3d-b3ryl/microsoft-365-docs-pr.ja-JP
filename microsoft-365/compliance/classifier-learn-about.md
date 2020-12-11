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
ms.openlocfilehash: 77ebefe338f393a916f0a6844b42b16e3d011d49
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620163"
---
# <a name="learn-about-classifiers-preview"></a>分類子 (プレビュー) について

コンテンツを適切に保護および処理できるようにコンテンツを分類およびラベル付けすることは、情報保護に対するトレーニングの出発点です。 Microsoft 365 には、コンテンツを分類する 3 つの方法があります。

## <a name="manually"></a>手動

この方法では、人間の判断と行動が必要です。 管理者は、既存のラベルと機密情報の種類を使用するか、独自のラベルを作成して公開することができます。 ユーザーと管理者は、遭遇したコンテンツをそれらに適用します。 その後、コンテンツを保護し、その処分を管理できます。

## <a name="automated-pattern-matching"></a>自動パターン マッチング

このカテゴリの分類メカニズムには、次の方法でコンテンツを検索する方法が含まれます。

- キーワードまたはメタデータ値 (キーワード クエリ言語)。
- 社会保障、クレジット カード番号、銀行口座番号 (機密情報の種類のエンティティ定義) など、以前に識別された機密情報のパターン [を使用する](sensitive-information-type-entity-definitions.md)。
- テンプレート上のバリエーション (ドキュメントの指の印刷) のため、アイテム [を認識します](document-fingerprinting.md)。
- 正確な文字列 (完全なデータ一 [致) の存在を使用します](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。

その後、データ損失防止 [(DLP)](data-loss-prevention-policies.md) および保持ラベルの自動適用ポリシーでコンテンツを使用できるよう、そのラベルを自動的に適用 [できます](apply-retention-labels-automatically.md)。

## <a name="classifiers"></a>分類子

この分類方法は、手動または自動のパターン マッチング方法では簡単に識別できないコンテンツに特に適しています。 この分類方法は、アイテムに含まれる要素ではなく、アイテムが何であるかに基づいてアイテムを識別するように分類子をトレーニングすることです (パターン マッチング)。 分類子は、分類したいコンテンツの数百の例を見て、コンテンツのタイプを識別する方法を学びます。 それを間違いなくカテゴリーにある例に与えることから始めます。 それらを処理したら、一致する例と一致しない例の両方を組み合わせてテストします。 次に、分類子は、特定のアイテムが作成中のカテゴリに該当するかどうかを予測します。 その結果を確認し、真陽性、真陰性、誤検知、検出検出検出を並べ替えて、予測の精度を高めることができます。 

分類子を発行すると、SharePoint Online、Exchange、OneDrive のような場所にあるアイテムを並べ替え、コンテンツが分類されます。 分類子を発行した後は、最初のトレーニング プロセスと同様のフィードバック プロセスを使用して、分類子を引き続きトレーニングできます。

### <a name="where-you-can-use-trainable-classifiers"></a>トレーニング可能な分類子を使用できる場所
組み込みの分類子とトレーニング可能な分類子の両方が、Office 自動ラベル付[](apply-sensitivity-label-automatically.md)けの条件として、条件と通信コンプライアンスに基づいて[](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)保持ラベル ポリシーを自動適用[できます。](communication-compliance.md) 

機度ラベルでは、条件として分類子を使用できます。「コンテンツに機ティフィティ ラベルを自動的に適用 [する」を参照してください](apply-sensitivity-label-automatically.md)。

> [!IMPORTANT]
> 分類子は、暗号化されていない、英語のアイテムでのみ機能します。

## <a name="types-of-classifiers"></a>分類子のタイプ

- **事前トレーニング済みの** 分類子 - Microsoft は、トレーニングなしで使用を開始できる多くの分類子を作成および事前トレーニングしています。 これらの分類子は、状態と一緒に表示されます `Ready to use` 。
- **カスタム分類子** - 事前トレーニング済みの分類子の範囲を超える分類ニーズがある場合は、独自の分類子を作成してトレーニングできます。

### <a name="pre-trained-classifiers"></a>事前トレーニング済みの分類子

Microsoft 365 には、5 つの事前トレーニング済み分類子が付属しています。

> [!CAUTION]
> 不快言語の事前トレーニング済み分類子は、誤検知の数が多く生成され始めているため、廃止されます。 使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。 代わりに、脅威 **、不適切** 行為、**および** ハラスメントの事前トレーニング済みの分類子を使用することをお勧めします。

- **履歴** 書 : 個人、教育、専門的資格、作業経験、その他の個人を特定する情報のテキスト アカウントであるアイテムを検出します
- **ソース コード**: GitHub の上位 25 の使用コンピューター プログラミング言語で記述された一連の命令とステートメントを含むアイテムを検出します
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
> ソース コードは、テキストの大部分がソース コードである場合を検出するトレーニングを受けています。 プレーン テキストと一緒に挿入されているソース コード テキストは検出されません。

- **ハラ** スメント: 次の特徴に基づいて、1 人または複数の個人を対象とする攻撃的行為に関連する特定のカテゴリの不快言語テキスト アイテムを検出します。特徴は次のとおりです。レース、民族性、民族、国家の原点、性別、性的指向、年齢、障がい
- **不適切表現**: ほとんどのユーザーを困惑する表現を含む、不快言語のテキスト アイテムの特定のカテゴリを検出します
- **脅威**: 暴力を加え、人やプロパティに物理的な危害や損害を与える脅威に関連する、攻撃的な言語のテキスト アイテムの特定のカテゴリを検出します

これらは、[**Microsoft 365 コンプライアンス センター**]  >  [**データ分類 (プレビュー)**]  >  [**トレーニング可能な分類子**] ビューに表示され、ステータスは `Ready to use` です。

![分類子-pre-trained-classifiers](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 不快な言葉、ハラスメント、冒涜的表現、および脅威の分類は、検索可能なテキストでのみ機能し、網羅的または完全ではないことに注意してください。  さらに、言語と文化の基準は絶えず変化し、これらの現実に照らして、Microsoft は独自の裁量でこれらの分類子を更新する権利を留保します。 分類子は、不快な言語やその他の使用言語を監視するのに役立ちますが、分類子は、そのような言語の結果に対処するものではなく、そのような言語の使用を監視または応答する唯一の手段を組織に提供するものではありません。 事前にトレーニングされた分類子によって識別されたコンテンツの監視、施行、ブロック、削除、および保持に関するすべての決定は、Microsoft またはその子会社ではなく、お客様の組織の責任となります。

### <a name="custom-classifiers"></a>カスタム分類子

事前トレーニング済みの分類子がニーズを満たしない場合は、独自の分類子を作成してトレーニングできます。 独自に作成するには、はるかに多くの作業が必要になりますが、組織のニーズに合わせてカスタマイズできます。 

たとえば、次のトレーニング可能な分類子を作成できます。
 
- 法的文書 - 弁護士依頼人特権、終了セット、作業明細書など
- 戦略的ビジネス ドキュメント - プレス リリース、合併と買収、取引、ビジネスまたはマーケティング計画、知的財産、特許、デザイン ドキュメントなど
- 価格情報 - 請求書、価格見積もり、作業命令、文書の編集など 
- 財務情報 - 組織への投資、四半期または年間の結果など    

#### <a name="process-flow-for-creating-custom-classifiers"></a>カスタム分類子を作成するためのプロセス フロー

アイテム保持ポリシーや通信監督などのコンプライアンス ソリューションで使用する分類子の作成と発行は、このフローに従います。 カスタムトレーニング可能な分類子の作成の詳細については、「カスタム分類子の [作成」を参照してください](classifier-get-started-with.md)。

![プロセス フローカスタム分類子](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>分類子の再トレーニング

すべてのカスタム分類子と事前トレーニング済みの分類子の精度を向上させるために、実行する分類の精度に関するフィードバックを提供できます。 これを再トレーニングと呼び、このワークフローに従います。

![分類子再トレーニング ワークフロー](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>関連項目

- [保持ラベル](retention.md)
- [データ損失防止 (DLP)](data-loss-prevention-policies.md)
- [秘密度ラベル](sensitivity-labels.md)
- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
- [ドキュメントの指の印刷](document-fingerprinting.md)
- [完全なデータ一致](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
