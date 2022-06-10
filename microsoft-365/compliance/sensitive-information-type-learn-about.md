---
title: 機密情報の種類に関する詳細情報
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
description: この記事では、機密情報の種類の概要と、機密性の高いアイテムを識別するために社会保障、クレジット カード、銀行口座番号などの機密情報を検出する方法について説明します。
ms.openlocfilehash: d814bd413fc95a02bc35ab05a804c544d9b84b1e
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66014236"
---
# <a name="learn-about-sensitive-information-types"></a>機密情報の種類に関する詳細情報

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

組織の管理下にある機密アイテムを識別して分類することは、[Information Protection規範](./information-protection.md)の最初のステップです。  Microsoft Purview では、アイテムを分類できるように、次の 3 つの方法でアイテムを識別できます。

- ユーザーが手動で
- 機密情報の種類など、自動パターン認識
- [機械学習](classifier-learn-about.md)

機密情報の種類 (SIT) は、パターン ベースの分類子です。 ソーシャル セキュリティ、クレジット カード、銀行口座番号などの機密情報を検出して機密アイテムを識別します。すべての SIT の完全な一覧については、「 [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md) 」を参照してください。

Microsoft では、多数の事前構成済み SIT を提供するか、独自の SIT を作成できます。

## <a name="sensitive-information-types-are-used-in"></a>機密情報の種類は、

- [Microsoft Purview データ損失防止ポリシー](dlp-learn-about-dlp.md)
- [機密ラベル](sensitivity-labels.md)
- [保持ラベル](retention.md)
- [インサイダー リスク管理](insider-risk-management.md)
- [通信コンプライアンス](communication-compliance.md)
- [自動ラベル付けポリシー](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [Microsoft Priva](/privacy/priva)

## <a name="categories-of-sensitive-information-types"></a>機密情報の種類のカテゴリ

### <a name="built-in-sensitive-information-types"></a>組み込みの機密情報の種類

これらの SID は、Microsoft によって既定でコンプライアンス コンソールに表示されて作成されます。 これらの SIT は編集できませんが、テンプレートとして使用し、カスタムの機密情報の種類を作成するためにコピーできます。 すべての SIT の完全な一覧については、 [機密情報の種類エンティティ定義](sensitive-information-type-entity-definitions.md) を参照してください。

### <a name="named-entity-sensitive-information-types"></a>名前付きエンティティの機密情報の種類

既定では、名前付きエンティティの SID もコンプライアンス コンソールに表示されます。 ユーザー名、物理アドレス、医療条件を検出します。 編集またはコピーすることはできません。 詳細については、 [名前付きエンティティに関する ](named-entities-learn.md#learn-about-named-entities) ページを参照してください。 名前付きエンティティ SIT には、次の 2 種類があります。

**バンドルされていない**

これらの名前付きエンティティ SIT は、単一の国や単一の用語クラスなど、より狭いフォーカスを持っています。 検出範囲が狭い DLP ポリシーが必要な場合に使用します。 [名前付きエンティティ SIT の例](named-entities-learn.md#examples-of-named-entity-sits)を参照してください。

**バンドル**

バンドルされた名前付きエンティティ SIT は、すべての物理アドレスなど、クラス内で考えられるすべての一致を検出します。 機密アイテムを検出するための DLP ポリシーの広範な条件として使用します。 [名前付きエンティティ SIT の例](named-entities-learn.md#examples-of-named-entity-sits)を参照してください。

### <a name="custom-sensitive-information-types"></a>カスタムの機密情報の種類

事前に構成された機密情報の種類がニーズを満たしていない場合は、完全に定義した独自のカスタム機密情報の種類を作成するか、組み込みの機密情報の 1 つをコピーして変更することができます。 詳細については、「 [コンプライアンス センターでカスタムの機密情報の種類を作成](create-a-custom-sensitive-information-type.md) する」を参照してください。

### <a name="exact-data-match-sensitive-information-types"></a>厳密なデータ一致の機密情報の種類

すべての EDM ベースの SID は、最初から作成されます。 これらを使用して、機密情報のデータベースで定義した正確な値を持つ項目を検出します。 詳細 [については、「厳密なデータ一致に基づく機密情報の種類](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types) 」を参照してください。

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>機密情報の種類の基本的な部分

すべての機密情報の種類エンティティは、次のフィールドによって定義されます。

- name: 機密情報の種類を参照する方法
- description: 機密情報の種類が何を探しているかについて説明します
- pattern: パターンは、機密情報の種類が検出する内容を定義します。 次のコンポーネントで構成されます。
  - プライマリ要素 – 機密情報の種類が探しているメイン要素。 これは、チェックサム検証、**キーワード リスト**、**キーワード ディクショナリ**、**または関数** の有無にかかわらず正規表現を使用できます。
  - サポート要素 – マッチの信頼度を高めるのに役立つサポート証拠として機能する要素。 たとえば、SSN 番号に近いキーワード "SSN" です。 チェックサム検証、キーワード リスト、キーワード ディクショナリの有無にかかわらず、正規表現を使用できます。
  - 信頼レベル - 信頼レベル (高、中、低) は、主要要素と共に検出されたサポート証拠の量を反映します。 アイテムに含まれるサポート証拠が多いほど、一致するアイテムに探している機密情報が含まれるという信頼度が高くなります。
  - 近接 – プライマリ要素とサポート要素の間の文字数。

![補強証拠と近接ウィンドウの図。](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

この短いビデオでは、信頼度レベルの詳細について説明します。

 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]

### <a name="example-sensitive-information-type"></a>機密情報の種類の例

#### <a name="argentina-national-identity-dni-number"></a>アルゼンチンの国民 ID (DNI) 番号

### <a name="format"></a>フォーマット

ピリオドで区切られた 8 桁の数字

### <a name="pattern"></a>パターン

8 桁の数字:

- 2 桁の数字
- 期間
- 3 桁
- 期間
- 3 桁

### <a name="checksum"></a>チェックサム

不要

### <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという中程度の信頼を持っています。

- 正規表現Regex_argentina_national_idは、パターンに一致するコンテンツを検索します。
- Keyword_argentina_national_idのキーワードが見つかりました。

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity number
- ID
- ID ナショナル ID カード
- DNI
- NIC National Registry of Persons
- Documento Nacional de Identidad
- Registro Nacional de las Personas
- Identidad
- Identificación

### <a name="more-on-confidence-levels"></a>信頼レベルの詳細

機密情報の種類のエンティティ定義では、 **信頼レベル** は、主要な要素に加えて、どの程度のサポート証拠が検出されるかを反映します。 アイテムに含まれるサポート証拠が多いほど、一致するアイテムに探している機密情報が含まれるという信頼度が高くなります。 たとえば、信頼度が高い一致には、プライマリ要素に近いより多くのサポート証拠が含まれますが、信頼度レベルが低い一致には、近接するサポート証拠がほとんど含まれない場合があります。

高信頼度レベルでは、最も少ない偽陽性が返されますが、より多くの偽陰性が発生する可能性があります。 低信頼度または中信頼度レベルでは、より多くの誤検知が返されますが、偽陰性は少数からゼロになります。

- **低信頼度**: 一致する項目には、最も少ない偽陰性が含まれますが、最も偽陽性が多くなります。 低信頼度は、すべての低信頼、中、高信頼の一致を返します。 低信頼度レベルの値は 65 です。
- **中程度の信頼度**: 一致する項目には、偽陽性と偽陰性の平均量が含まれます。 中信頼度は、すべての中信頼度と高信頼度の一致を返します。 中信頼レベルの値は 75 です。
- **高信頼** 度: 一致する項目には、最も少ない偽陽性が含まれますが、最も偽陰性が多くなります。 高信頼度は、高信頼一致のみを返し、値は 85 です。

高信頼度パターンは、5 から 10 など、信頼度の高いパターンは 20 以上と呼ばれる高い数で使用する必要があります。

> [!NOTE]
> 数値ベースの信頼レベル (精度とも呼ばれます) を使用して定義された既存のポリシーまたはカスタムの機密情報の種類 (SIT) がある場合は、3 つの個別の信頼レベルに自動的にマップされます。セキュリティ @ コンプライアンス センター UI 全体で、低信頼度、中信頼度、高信頼度。
>
> - 最小精度または 76 ~ 100 の信頼レベルを持つカスタム SIT パターンを持つすべてのポリシーは、高信頼度にマップされます。
> - 最小精度または 66 ~ 75 の信頼レベルを持つカスタム SIT パターンを持つすべてのポリシーは、中程度の信頼度にマップされます。
> - 信頼度レベルが 65 以下の最小精度またはカスタム SIT パターンを持つすべてのポリシーは、低信頼度にマップされます。

## <a name="creating-custom-sensitive-information-types"></a>カスタムの機密情報の種類を作成する

コンプライアンス センターでカスタムの機密情報の種類を作成するには、いくつかのオプションから選択できます。

- **UI を使用する** - コンプライアンス センター UI を使用して、カスタムの機密情報の種類を設定できます。 この方法では、正規表現、キーワード、キーワード辞書を使用することができます。 詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」を参照してください。

- **EDM を使用する** - 完全一致 (EDM) ベースの分類を使用して、カスタムの機密情報の種類を設定できます。 この方法では、定期的に更新できる安全なデータベースを使用して、動的な機密情報の種類を作成することができます。 [厳密なデータ一致ベースの機密情報の種類については、「」を](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)参照してください。

- **PowerShell を使用する - PowerShell** を使用して、カスタムの機密情報の種類を設定できます。 この方法は、UI を使用する場合よりも複雑ですが、より多くの構成オプションがあります。 [セキュリティ & コンプライアンス PowerShell でのカスタム機密情報の種類の作成に関する](create-a-custom-sensitive-information-type-in-scc-powershell.md)説明を参照してください。

> [!NOTE]
> Microsoft Purview データ損失防止サービス、情報保護、通信コンプライアンス、データ ライフサイクル管理、およびレコード管理内ですぐに使用するために、信頼レベルの向上を利用できます。
> Information Protectionでは、次の 2 バイト文字セット言語がサポートされるようになりました。
> - 中国語 (簡体字)
> - 中国語 (繁体字)
> - 韓国語
> - 日本語
>
> このサポートは、機密情報の種類で使用できます。 詳細については、 [2 バイト文字セットの情報保護のサポートに関するリリース ノート](mip-dbcs-relnotes.md) を参照してください。

> [!TIP]
> 中国語/日本語の文字と 1 バイト文字を含むパターンを検出する、または中国語/日本語と英語を含むパターンを検出するには、キーワードまたは正規表現の 2 つのバリエーションを定義します。
>
> - たとえば、「机密的ドキュメント」のようなキーワードを検出するには、キーワードの 2 つのバリエーションを使用します。 1 つは日本語と英語のテキストの間にスペースがあり、もう 1 つは日本語と英語のテキストの間にスペースがありません。 したがって、SITに追加するキーワードは、"机密的 document" と "机密的document" である必要があります。 同様に、"東京オリンピック2020" というフレーズを検出するには、"東京オリンピック 2020" と "東京オリンピック2020" の 2 つのバリエーションを使用する必要があります。
>
> 中国語/日本語/2 バイト文字と共に、キーワード/フレーズの一覧に中国語/日本語以外の単語 (英語のみなど) も含まれている場合は、2 つの辞書/キーワード リストを作成する必要があります。 1 つは中国語/日本語/ 2 バイト文字を含むキーワード用で、もう1 つは英語のみ用です。
>
> - たとえば、"機密性が高い"、"機密性が高い"、"機密性の高い"、"機密性の高い"、"机密的文書" の 3 つの語句を含むキーワード ディクショナリ/リストを作成する場合は、2 つのキーワード リストを作成する必要があります。
>     1. Highly confidential
>     2. 機密性が高い、机密的document、机密的 document
>
> 2 バイトのハイフンまたは 2 バイトのピリオドを使用して正規表現を作成するときは、正規表現のハイフンまたはピリオドをエスケープするように、必ず両方の文字をエスケープしてください。参考までに、サンプルの正規表現を次に示します。
>
> `(?<!\d)([4][0-9]{3}[\-?\-\t]*[0-9]{4}`
>
> キーワード リストでは、単語一致ではなく文字列一致を使用することをお勧めします。

## <a name="for-further-information"></a>詳細については、次の情報を参照してください。

- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
- [カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)
- [PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)

機密情報の種類を使用してデータプライバシー規制に準拠する方法については、「Microsoft 365を使用した[データプライバシー規制の情報保護の展開](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy)」を参照してください。

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
