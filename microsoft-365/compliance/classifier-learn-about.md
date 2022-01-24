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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: admindeeplinkMAC
search.appverid:
- MOE150
- MET150
description: トレーニング可能な分類子は、ラベル付けまたはポリシー アプリケーション用にさまざまな種類のコンテンツを認識するために、正のサンプルと負のサンプルを表示できます。
ms.openlocfilehash: 9301379e55865fc0524dbf814365239d700aa962
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2022
ms.locfileid: "62172153"
---
# <a name="learn-about-trainable-classifiers"></a>トレーニング可能な分類子の詳細

コンテンツを適切に保護および処理できるようにコンテンツを分類およびラベル付けすることは、情報保護に対するトレーニングの出発点です。 Microsoft 365 には、コンテンツを分類する 3 つの方法があります。

## <a name="manually"></a>手動

手動による分類には、人間の判断と行動が必要です。 ユーザーと管理者は、遭遇したコンテンツをそれらに適用します。 既存のラベルと機密情報の種類を使用するか、カスタム作成されたラベルを使用できます。  その後、コンテンツを保護し、その処分を管理できます。

## <a name="automated-pattern-matching"></a>自動パターンマッチング

この分類メカニズムのカテゴリには、次によるコンテンツの検索が含まれます。

- キーワードまたはメタデータ値 (キーワード クエリ言語)。
- 社会保障、クレジット カード、銀行口座番号 (機密情報の種類エンティティ定義) などの機密情報の以前に識別されたパターンを [使用する](sensitive-information-type-entity-definitions.md)。
- アイテムがテンプレートのバリエーション (ドキュメントフィンガー印刷) なので、アイテム [を認識します](document-fingerprinting.md)。
- 正確な文字列の存在を使用して、 [完全に一致するデータを使用します](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)。

その後、感度ラベルと保持ラベルを自動的に適用して、「データ損失防止の[](dlp-learn-about-dlp.md)詳細」および「保持ラベルのポリシーを自動適用する」でコンテンツを[使用できます](apply-retention-labels-automatically.md)。

## <a name="classifiers"></a>分類子

この分類方法は、手動または自動のパターンマッチング方法では容易に識別できないコンテンツに適しています。 この分類方法は、分類子を使用して、アイテム内の要素 (パターンマッチング) ではなく、アイテムの種類に基づいてアイテムを識別する方法です。 分類子は、分類したいコンテンツの数百の例を見て、コンテンツのタイプを識別する方法を学びます。

> [!NOTE]
> コンテンツ エクスプローラーでトレーニング可能な分類子を表示するには、フィルター パネルで **[トレーニング可能な** 分類子] を展開します。 トレーニング可能な分類子は、ラベル付けなしで、SharePoint、Teams、OneDrive で検出されたインシデントの数を自動的に表示します。
> この機能を使用しない場合は、Microsoft サポートに要求を送信して、箱から出た分類を無効にする必要があります。 これにより、ラベル付けポリシーを作成する前に、機密性の高いラベル付きコンテンツのスキャンが無効にされます。

### <a name="where-you-can-use-classifiers"></a>分類子を使用できる場所

分類子は、Office の自動ラベル付け、条件[に](apply-sensitivity-label-automatically.md)基づく保持ラベル ポリシーの自動適用[](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)、および通信コンプライアンスの条件として[使用できます](communication-compliance.md)。 

感度ラベルは、条件として分類子を使用できます。「コンテンツに自動的に感度ラベルを適用 [する」を参照してください](apply-sensitivity-label-automatically.md)。

> [!IMPORTANT]
> 分類子は、暗号化されていないアイテムでのみ動作します。

## <a name="types-of-classifiers"></a>分類子のタイプ

- **事前トレーニング済みの分類子** - Microsoft は、トレーニングなしで使用を開始できる複数の分類子を作成および事前トレーニングしました。 これらの分類子は、 の状態で表示されます `Ready to use` 。
- **カスタムトレーニング可能な** 分類子 - 事前トレーニング済みの分類子がカバーする範囲を超える分類ニーズがある場合は、独自の分類子を作成してトレーニングできます。

### <a name="pre-trained-classifiers"></a>事前トレーニング済みの分類子

Microsoft 365には、複数の事前トレーニング済み分類子が付属しています。

> [!CAUTION]
> 事前にトレーニングされた [**不快な言葉**] 分類子は、誤検知の数が多いため、廃止予定です。 使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。 代わりに **、Threat** **、Profanity、** および **Harassment** の事前トレーニング済みの分類子を使用することをお勧めします。

- **履歴書**: 申請者の個人、教育、専門的な資格、職歴、その他の個人識別情報のテキスト アカウントである docx、.pdf、.rtf、.txt アイテムを検出します。
- ソース コード: GitHub で使用される上位 25 のコンピューター プログラミング言語で記述された一連の命令とステートメントを含むアイテムを検出します。ActionScript、C、C#、C++、Clojure、CoffeeScript、Go、Haskell、Java、JavaScript、Lua、MATLAB、Objective-C、Perl、PHP、Python、R、Ruby、Scala、Shell、Swift、TeX、Vim スクリプト。

> [!NOTE]
> ソース コードは、テキストの大部分がソース コードである場合に検出するトレーニングを受けています。 プレーン テキストと相互に存在するソース コード テキストは検出されません。

- **契約:** 非開示契約、作業明細書、ローンおよびリース契約、雇用契約、非競争契約などの法的契約に関連するコンテンツを検出します。 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt、.one、.msg、.eml ファイルのコンテンツを検出します。
- **判別**: 明示的な判別言語を検出し、他のコミュニティと比較すると、アフリカ系アメリカ人/黒人コミュニティに対する差別的な言語に敏感です。
- **Finance**: 企業の財務、会計、経済、銀行、投資カテゴリのコンテンツを検出します。 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf のコンテンツを検出します。 .rtf、.txt、.one、.msg、.eml、.pptx、.pptm、.ppt、.potm、.potm、.ppsx、.ppsm、.ppsm、.pps、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam ファイル
- **嫌** がらせ : 人種、民族、宗教、出身国、性別、性的指向、年齢、障がいなどの特性に基づいて、1 人または複数の個人を対象とする攻撃的行為に関連する攻撃的な言語テキスト 項目の特定のカテゴリを検出します。
- **医療 :** 医療サービス、診断、治療、クレームなどの医療および医療管理の側面のコンテンツを検出します。.docx、.docm、.doc、.dotx、.dotm、.dot、.pdf のコンテンツを検出します。 .rtf、.txt、.one、.msg、.eml、.pptx、.pptm、.ppt、.potm、.potm、.ppsx、.ppsm、.ppsm、.pps、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam ファイル
- **人事**: 採用、面接、採用、トレーニング、評価、警告、終了の人事関連カテゴリのコンテンツを検出します。 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf のコンテンツを検出します。 .rtf、.txt、.one、.msg、.eml、.pptx、.pptm、.ppt、.potm、.potm、.ppsx、.ppsm、.ppsm、.pps、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam ファイル
- **IP**: 営業秘密や類似の機密情報などの知的財産関連カテゴリのコンテンツを検出します。 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf のコンテンツを検出します。 .rtf、.txt、.one、.msg、.eml、.pptx、.pptm、.ppt、.potm、.potm、.ppsx、.ppsm、.ppsm、.pps、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam ファイル
- **IT**: ネットワーク設定、情報セキュリティ、ハードウェア、ソフトウェアなどの情報テクノロジおよびサイバーセキュリティ カテゴリのコンテンツを検出します。 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf のコンテンツを検出します。 .rtf、.txt、.one、.msg、.eml、.pptx、.pptm、.ppt、.potm、.potm、.ppsx、.ppsm、.ppsm、.pps、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam ファイル
- **法務 :** 訴訟、法的プロセス、法的義務、法律用語、法律、法律などの法務関連カテゴリのコンテンツを検出します。 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt、.one、.msg、.eml ファイルのコンテンツを検出します。
- **調達**: 入札、引用、購入、および商品やサービスの供給に対する支払いカテゴリのコンテンツを検出します。 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt、.one、.msg、.eml、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam、.xla ファイルのコンテンツを検出します。
- **冒とく**: ほとんどの人を困らせる表現を含む不快な言語テキスト アイテムの特定のカテゴリを検出します。
- **Tax**: 税務計画、税務フォーム、税務申告、税規制などの税務関係のコンテンツを検出します。 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、のコンテンツを検出します。 .txt、.one、.msg、.eml、.pptx、.pptm、.ppt、.potm、.potm、.ppsx、.ppsm、.ppsm、.pps、.ppam、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam xlam ファイル。
- **脅威**: 暴力を犯したり、人や財産に物理的な危害や損害を与える脅威に関連する、攻撃的な言語テキスト アイテムの特定のカテゴリを検出します。

これらは、[データ分類] **Microsoft 365 コンプライアンス センター** の状態の [トレーニング可能な分類子]  >    >  ビューに表示されます `Ready to use` 。

![分類子-事前トレーニング済み分類子。](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 不快な言語、嫌がらせ、冒とく、差別、脅威分類子は検索可能なテキストでのみ機能し、これらの分野の用語や言語の完全なリストではありません。 さらに、言語と文化の基準は絶えず変化し、これらの現実に照らして、Microsoft は独自の裁量でこれらの分類子を更新する権利を留保します。 分類子は組織がこれらの領域を検出する場合に役立ちますが、分類子は、そのような言語の使用を検出または対処する組織の唯一の手段を提供することを目的としていない。 Microsoft または子会社ではなく、組織は、事前トレーニング済みの分類者によって識別されたコンテンツの監視、スキャン、ブロック、削除、保持に関連するすべての決定 (地域のプライバシーや他の適用される法律の遵守を含む) に対して引き続き責任を負います。 Microsoft では、展開と使用の前に法律顧問とのコンサルティングを推奨しています。

事前トレーニング済みの分類子は、次の言語でコンテンツをスキャンできます。

• 中国語 (簡体字) • 英語 • フランス語 • ドイツ語 • イタリア語 • 日本語 • ポルトガル語 • スペイン語

### <a name="custom-classifiers"></a>カスタム分類子

事前トレーニング済みの分類子がニーズを満たしない場合は、独自の分類子を作成してトレーニングできます。 独自に作成するには、はるかに多くの作業が必要になりますが、組織のニーズに合わせてカスタマイズできます。

カスタムトレーニング可能な分類子の作成を開始するには、カテゴリに確実に含める例を指定します。 これらの例を処理したら、一致する例と一致しない例の両方を組み合わせ、テストします。 次に、分類子は、特定のアイテムが作成中のカテゴリに該当するかどうかを予測します。 次に、その結果を確認し、予測の精度を高めるのに役立つ、真の陽性、真の負、誤検知、および偽陰性を並べ替えて確認します。 

分類子を発行すると、SharePoint Online、Exchange、OneDrive のような場所のアイテムを並べ替え、コンテンツを分類します。 分類子を発行した後、最初のトレーニング プロセスと同様のフィードバック プロセスを使用して、分類子をトレーニングし続けできます。

たとえば、次のトレーニング可能な分類子を作成できます。

- 法的文書 - 弁護士クライアント特権、終了セット、作業明細書など
- 戦略的ビジネス ドキュメント - プレスリリース、合併および買収、取引、ビジネスまたはマーケティング計画、知的財産、特許、デザイン ドキュメントなど
- 価格情報 - 請求書、価格見積もり、作業オーダー、入札ドキュメントなど
- 財務情報 - 組織の投資、四半期または年次の結果など

#### <a name="process-flow-for-creating-custom-classifiers"></a>カスタム分類子を作成するためのプロセス フロー

保持ポリシーや通信監督など、コンプライアンス ソリューションで使用する分類子の作成と発行は、このフローに従います。 カスタムトレーニング可能な分類子の作成の詳細については、「カスタム分類子の作成 [」を参照してください](classifier-get-started-with.md)。

![プロセス フローのカスタム分類子。](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>分類子の再トレーニング

すべてのカスタムトレーニング可能な分類子の精度を向上し、それらを実行する分類の精度に関するフィードバックを提供することで役立ちます。 これを再トレーニングと呼び、このワークフローに従います。

> [!NOTE]
> 事前トレーニング済みの分類子は再トレーニングできません。

![分類子の再トレーニング ワークフロー。](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>関連項目

- [保持ラベル](retention.md)
- [データ損失防止について](dlp-learn-about-dlp.md)
- [機密ラベル](sensitivity-labels.md)
- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
- [ドキュメントの指の印刷](document-fingerprinting.md)
- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
