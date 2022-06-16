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
description: トレーニング可能な分類子は、ラベル付けまたはポリシー アプリケーション用のさまざまな種類のコンテンツを認識できます。
ms.openlocfilehash: ed2b744c1c136afde38151dc424eef547607ef27
ms.sourcegitcommit: 18bc521a88b7b521bccb0e69d02deac764218087
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2022
ms.locfileid: "66115853"
---
# <a name="learn-about-trainable-classifiers"></a>トレーニング可能な分類子の詳細

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

コンテンツを適切に保護および処理できるようにコンテンツを分類およびラベル付けすることは、情報保護に対するトレーニングの出発点です。 Microsoft 365 には、コンテンツを分類する 3 つの方法があります。

## <a name="manually"></a>手動

手動による分類には、人間の判断とアクションが必要です。 ユーザーと管理者は、遭遇したコンテンツをそれらに適用します。 既存のラベルと機密情報の種類を使用するか、カスタムで作成されたものを使用できます。  その後、コンテンツを保護し、その処分を管理できます。

## <a name="automated-pattern-matching"></a>自動パターン マッチング

この分類メカニズムのカテゴリには、次によるコンテンツの検索が含まれます。

- キーワードまたはメタデータ値 (キーワード クエリ言語)。
- 社会保障、クレジット カード、銀行口座番号 [(機密情報の種類エンティティ定義)](sensitive-information-type-entity-definitions.md) などの機密情報の以前に識別されたパターンを使用する。
- テンプレート [(ドキュメントフィンガー印刷)](document-fingerprinting.md) のバリエーションであるため、アイテムを認識します。
- 正確な文字列の存在を使用して [、正確なデータ一致を行います](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)。

その後、秘密度ラベルと保持ラベルを自動的に適用して、保持ラベルのポリシーのMicrosoft Purview データ損失防止と[自動適用](apply-retention-labels-automatically.md)[に関するページ](dlp-learn-about-dlp.md)でコンテンツを使用できるようにします。

## <a name="classifiers"></a>クラシファイア

この分類方法は、手動または自動のパターンマッチング方法で簡単に識別できないコンテンツに適しています。 この分類方法は、分類子を使用して、アイテム内の要素 (パターン マッチング) ではなく、アイテムの内容に基づいてアイテムを識別する方法について詳しく説明します。 分類子は、分類したいコンテンツの数百の例を見て、コンテンツのタイプを識別する方法を学びます。

> [!NOTE]
> プレビュー - フィルター パネルで [トレーニング可能な分類子] を展開することで、コンテンツ エクスプローラーで **トレーニング可能な分類子** を表示できます。 トレーニング可能な分類子は、ラベル付けを必要とせずに、SharePoint、Teams、OneDriveで検出されたインシデントの数を自動的に表示します。
> この機能を使用しない場合は、既定の分類を無効にするには、Microsoft サポートで要求を提出する必要があります。 これにより、ラベル付けポリシーを作成する前に、機密コンテンツとラベル付きコンテンツのスキャンが無効になります。

### <a name="where-you-can-use-classifiers"></a>分類子を使用できる場所

分類子は、秘密度ラベルを使用した[自動ラベル付けをOffice](apply-sensitivity-label-automatically.md)するための条件として使用でき、条件と[通信コンプライアンス](communication-compliance.md)[に基づいてアイテム保持ラベル ポリシーを自動適用](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)できます。

機密ラベルは条件として分類子を使用できます。「 [コンテンツに秘密度ラベルを自動的に適用する」を](apply-sensitivity-label-automatically.md)参照してください。

> [!IMPORTANT]
> 分類子は、暗号化されていない項目でのみ機能します。

## <a name="types-of-classifiers"></a>分類子のタイプ

- **事前トレーニング済みの分類子** - Microsoft では、トレーニングなしで使用を開始できる複数の分類子を作成し、事前にトレーニングしました。 これらの分類子は、状態 `Ready to use`が .
- **カスタムトレーニング可能な分類子** - 事前トレーニング済みの分類子がカバーする範囲を超える分類ニーズがある場合は、独自の分類子を作成してトレーニングできます。

### <a name="pre-trained-classifiers"></a>事前トレーニング済みの分類子

Microsoft 365には、事前にトレーニングされた複数の分類子が付属しています。

- **成人向け、racy、および gory**: これらの種類の画像を検出します。 画像のサイズは 50 KB から 4 メガバイト (MB) で、高さ x 幅の寸法は 50 x 50 ピクセルを超える必要があります。 スキャンと検出は、Exchange Online電子メール メッセージ、およびMicrosoft Teams チャネルとチャットでサポートされています。 .jpeg、.png、.gif、.bmp ファイル内のコンテンツを検出します。

- **契約**: 秘密保持契約、作業明細書、ローンおよびリース契約、雇用契約、非競争契約など、法的契約に関連するコンテンツを検出します。 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt、.one、.msg、.eml ファイルのコンテンツを検出します。

- **顧客からの苦情**: 顧客の苦情分類子は、組織の製品またはサービスに関するフィードバックと苦情を検出します。 この分類子は、消費者金融保護局や食品医薬品局の要件など、苦情の検出とトリアージに関する規制要件を満たすのに役立ちます。 通信コンプライアンスでは、.msg ファイルと .eml ファイル内のコンテンツが検出されます。 残りのMicrosoft Purview 情報保護 サービスでは、.docx、.pdf、.txt、.rtf、.jpg、.jpeg、.png、.gif、.bmp、.svg ファイル内のコンテンツが検出されます。

- **差別**: 明示的な差別言語を検出し、他のコミュニティと比較して、アフリカ系アメリカ人/ブラックコミュニティに対する差別的言語に依存します。

- **Finance**: 企業財務、会計、経済、銀行、投資のカテゴリのコンテンツを検出します。 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、 .txt、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.ppsm、.ppss、.pps、.xlsm、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam、.xla ファイル。

- **嫌がらせ**: 人種、民族、宗教、国籍、性別、性的指向、年齢、障疳という特徴に基づいて、1 人または複数の個人を対象とする攻撃的行為に関連する不快な言語テキスト項目の特定のカテゴリを検出します。 .msg、.docx、.pdf、.txt、.rtf、.jpeg、.jpg、.png、.gif、.bmp、.svg ファイル内のコンテンツを検出します。

- **医療**: 医療サービス、診断、治療、クレームなどの医療および医療管理の側面でコンテンツを検出します。.docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、 .txt、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.ppsm、.ppss、.pps、.xlsm、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam、.xla ファイル。

- **人事**: 採用、面接、採用、トレーニング、評価、警告、終了の人事関連カテゴリのコンテンツを検出します。 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、 .txt、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.ppsm、.ppss、.pps、.xlsm、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam、.xla ファイル。

- **IP**: 企業秘密や同様の機密情報など、知的財産関連のカテゴリ内のコンテンツを検出します。 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、 .txt、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.ppsm、.ppss、.pps、.xlsm、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam、.xla ファイル。

- **IT**: ネットワーク設定、情報セキュリティ、ハードウェア、ソフトウェアなどの情報技術とサイバーセキュリティのカテゴリのコンテンツを検出します。 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、 .txt、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.pot、.ppsx、.ppsm、.ppsm、.ppss、.pps、.xlsm、.ppa、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam、.xla ファイル。

- **法務**: 訴訟、法的手続き、法的義務、法律用語、法律、法律など、法務関連のカテゴリのコンテンツを検出します。 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt、.one、.msg、.eml ファイルのコンテンツを検出します。

- **調達**: 商品やサービスの供給に対して、入札、見積もり、購入、支払いなどのカテゴリのコンテンツを検出します。 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、.rtf、.txt、.one、.msg、.eml、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xltm、.xlt、.xlam、.xla ファイルでコンテンツを検出します。

- **不適切な表現**: ほとんどの人を困らせる表現を含む、不快な言語テキスト項目の特定のカテゴリを検出します。 .msg、.docx、.pdf、.txt、.rtf、.jpeg、.jpg、.png、.gif、.bmp、.svg ファイル内のコンテンツを検出します。

- **履歴書**: 申請者の個人、教育、職業資格、職務経験、その他の個人識別情報のテキスト アカウントである docx、.pdf、.rtf、.txt項目を検出します。

- **ソース コード**: ActionScript、C、C#、C++、Clojure、CoffeeScript、Go、Haskell、Java、JavaScript、Lua、MATLAB、Objective-C、Perl、PHP、Python、R、Ruby、Scala、Shell、Swift、TeX、Vim スクリプトの一連の命令とステートメントが記述されたコンピューター プログラミング GitHub言語を含む項目を検出します。 .msg、.as、.h、.c、.cs、.cc、.cpp、.hpp、 .cxx、.hh、.c++、.clj、.edn、.cljc、.cljs、.coffee、.litcoffee、.go、.hs、.lhs、.java、.jar、.js、.mjs、.lua、.m、.mm、.pl、.pm、.t、.xs、.pod、.php、.phar、.php4、.pyc、 .R、.r、.rda、.RData、.rds、.rb、.scala、.sc、.sh、.swift ファイル。

  > [!NOTE]
  > ソース コードは、テキストの大部分がソース コードである場合を検出するようにトレーニングされます。 プレーンテキストが混在するソース コード テキストは検出されません。

- **税**: 税計画、税務フォーム、税務書類、税規制などの税関係の内容を検出します。 .docx、.docm、.doc、.dotx、.dotm、.dot、.pdf、 .rtf、.txt、.one、.msg、.eml、.pptx、.pptm、.ppt、.potx、.potm、.ppsx、.ppsm、.ppsm、.ppss、.ppsm、.xlsx、.xlsm、.xlsb、.xls、.csv、.xltx、.xltm、.xlt、.xlam、xla ファイル。

- **脅威**: 人や財産に対する暴行や身体的危害または損害を与える脅威に関連する、攻撃的な言語テキスト項目の特定のカテゴリを検出します。

- **脅威**: 人や財産に対する暴行や身体的危害または損害を与える脅威に関連する、攻撃的な言語テキスト項目の特定のカテゴリを検出します。 .msg、.docx、.pdf、.txt、.rtf、.jpeg、.jpg、.png、.gif、.bmp、.svg ファイル内のコンテンツを検出します。

これらの分類子は、Microsoft Purview コンプライアンス ポータル **データ分類** \> **トレーニング可能な分類子** ビューに表示され\>、状態`Ready to use`は .

![分類子-事前トレーニング済み分類子。](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 組み込みのトレーニング可能な分類子とグローバル分類子では、これらの領域全体の用語または言語の完全な一覧は提供されないことに注意してください。 さらに、言語と文化の基準は絶えず変化し、これらの現実に照らして、Microsoft は独自の裁量でこれらの分類子を更新する権利を留保します。 分類子は組織がこれらの領域を検出するのに役立つ場合がありますが、分類子は、そのような言語の使用を検出または対処する組織の唯一の手段を提供することを意図していません。 Microsoft またはその子会社ではなく、組織は、事前トレーニング済みの分類子によって識別されたコンテンツの監視、スキャン、ブロック、削除、および保持に関連するすべての決定について責任を負います。これには、地域のプライバシーやその他の適用法への準拠が含まれます。 Microsoft では、展開と使用の前に法律相談者に相談することをお勧めします。

脅威、冒涜、嫌がらせ、差別の分類子は、次の言語でコンテンツをスキャンできます。

- アラビア語
- 簡体字中国語
- 繁体字中国語
- オランダ語
- 英語
- フランス語
- ドイツ語
- イタリア語
- 韓国語
- 日本語
- ポルトガル語
- スペイン語

その他はすべて、現時点では英語のみです。

### <a name="custom-classifiers"></a>カスタム分類子

事前トレーニング済みの分類子がニーズを満たしていない場合は、独自の分類子を作成してトレーニングできます。 独自の作成にはより多くの作業が伴いますが、組織のニーズに合わせて調整する方がはるかに優れています。

カスタムトレーニング可能な分類子の作成を開始するには、間違いなくカテゴリに含まれる例を入力します。 これらの例を処理したら、一致する例と一致しない例の両方を組み合わせてテストします。 次に、分類子は、特定のアイテムが作成中のカテゴリに該当するかどうかを予測します。 その結果を確認し、真陽性、真陰性、偽陽性、および偽陰性を並べ替えて、予測の精度を高めます。

分類子を発行すると、SharePoint Online、Exchange、OneDriveなどの場所のアイテムを並べ替え、コンテンツを分類します。 分類子を発行した後は、最初のトレーニング プロセスに似たフィードバック プロセスを使用して、それをトレーニングし続けることができます。

たとえば、次のトレーニング可能な分類子を作成できます。

- 法的ドキュメント - 弁護士クライアント特権、クロージング セット、作業明細書など
- 戦略的ビジネス ドキュメント - プレス リリース、合併と買収、取引、ビジネスまたはマーケティング計画、知的財産、パテント、設計ドキュメントなど
- 価格情報 - 請求書、価格見積もり、作業指示書、入札ドキュメントなど
- 財務情報 ( 組織の投資、四半期または年間の結果など)

#### <a name="process-flow-for-creating-custom-classifiers"></a>カスタム分類子を作成するためのプロセス フロー

保持ポリシーや通信監督など、コンプライアンス ソリューションで使用する分類子を作成して公開すると、このフローに従います。 カスタムトレーニング可能な分類子の作成の詳細については、「 [カスタム分類子の作成」を](classifier-get-started-with.md)参照してください。

![プロセス フローのカスタム分類子。](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>分類子の再トレーニング

トレーニング可能なすべての分類子の精度を向上させ、実行する分類の精度に関するフィードバックを提供することができます。 これは再トレーニングと呼ばれ、このワークフローに従います。

> [!NOTE]
> 事前トレーニング済みの分類子を再トレーニングすることはできません。

![分類子の再トレーニングワークフロー。](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>関連項目

- [保持ラベル](retention.md)
- [データ損失防止について](dlp-learn-about-dlp.md)
- [機密ラベル](sensitivity-labels.md)
- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
- [ドキュメントの指の印刷](document-fingerprinting.md)
- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
