---
title: PowerShell を使用してカスタムの機密情報の種類を作成する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.article: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: コンプライアンス センターでポリシーのカスタムの機密情報の種類を作成してインポートする方法について説明します。
ms.openlocfilehash: 4e9a6eb7c4766fa598b0a28f7632c7c3ed530f9e
ms.sourcegitcommit: 99067d5eb1fa7b094e7cdb1f7be65acaaa235a54
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2022
ms.locfileid: "62272068"
---
# <a name="create-a-custom-sensitive-information-type-using-powershell"></a>PowerShell を使用してカスタムの機密情報の種類を作成する

この記事では、カスタムの機密情報の種類を定義 *する XML ルール* パッケージ ファイルを作成 [する方法について説明します](sensitive-information-type-entity-definitions.md)。 この記事では、従業員 ID を識別するカスタム機密情報の種類について説明します。 この記事のサンプル XML は、独自の XML ファイルの開始点として使用できます。

機密情報の種類の詳細については、「機密情報の [種類について」を参照してください](sensitive-information-type-learn-about.md)。

整形式の XML ファイルを作成したら、PowerShell を使用してそのファイルをMicrosoft 365できます。 次に、ポリシーでカスタムの機密情報の種類を使用する準備ができました。 意図した機密情報を検出する際に、その有効性をテストできます。

> [!NOTE]
> PowerShell が提供する詳細なコントロールが必要ない場合は、カスタムの機密情報の種類をユーザー設定で作成Microsoft 365 コンプライアンス センター。 詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」をご覧ください。

## <a name="important-disclaimer"></a>重要な免責事項

Microsoft サポートは、コンテンツ一致の定義を作成するのに役立ち得ない。

カスタム コンテンツマッチングの開発、テスト、デバッグを行う場合は、独自の内部 IT リソースを使用するか、Microsoft Consulting Services (MCS) などのコンサルティング サービスを使用する必要があります。 Microsoft サポート エンジニアは、この機能に対して限定的なサポートを提供できますが、カスタム コンテンツ一致の提案がニーズを完全に満たすという保証はありません。

MCS は、テストの目的で正規表現を提供できます。 また、1 つの特定のコンテンツ例で期待通り動作しない既存の RegEx パターンのトラブルシューティングにも役立つ情報を提供できます。

この [記事で注意する必要がある検証の潜在的な問題](#potential-validation-issues-to-be-aware-of) を参照してください。

テキストを処理するために使用されている Boost.RegEx (以前の RegEx++) エンジンの詳細については、「[Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/)」を参照してください。

> [!NOTE]
> カスタム機密情報の種類でキーワードの一部としてアンパサンド文字 (&) を使用する場合は、文字の周囲にスペースを含む用語を追加する必要があります。 たとえば、not を使用`L & P`_します_`L&P`。

## <a name="sample-xml-of-a-rule-package"></a>ルール パッケージのサンプル XML

ここでは、この記事で作成するルール パッケージのサンプル XML を示します。 要素と属性については、以下のセクションで説明します。

```xml
<?xml version="1.0" encoding="UTF-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
<RulePack id="DAD86A92-AB18-43BB-AB35-96F7C594ADAA">
  <Version build="0" major="1" minor="0" revision="0"/>
  <Publisher id="619DD8C3-7B80-4998-A312-4DF0402BAC04"/>
  <Details defaultLangCode="en-us">
    <LocalizedDetails langcode="en-us">
      <PublisherName>Contoso</PublisherName>
      <Name>Employee ID Custom Rule Pack</Name>
      <Description>
      This rule package contains the custom Employee ID entity.
      </Description>
    </LocalizedDetails>
  </Details>
</RulePack>
<Rules>
<!-- Employee ID -->
  <Entity id="E1CC861E-3FE9-4A58-82DF-4BD259EAB378" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="65">
      <IdMatch idRef="Regex_employee_id"/>
    </Pattern>
    <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_employee_id"/>
      <Match idRef="Func_us_date"/>
    </Pattern>
    <Pattern confidenceLevel="85">
      <IdMatch idRef="Regex_employee_id"/>
      <Match idRef="Func_us_date"/>
      <Any minMatches="1">
        <Match idRef="Keyword_badge" minCount="2"/>
        <Match idRef="Keyword_employee"/>
      </Any>
      <Any minMatches="0" maxMatches="0">
        <Match idRef="Keyword_false_positives_local"/>
        <Match idRef="Keyword_false_positives_intl"/>
      </Any>
    </Pattern>
  </Entity>
  <Regex id="Regex_employee_id">(\s)(\d{9})(\s)</Regex>
  <Keyword id="Keyword_employee">
    <Group matchStyle="word">
      <Term>Identification</Term>
      <Term>Contoso Employee</Term>
    </Group>
  </Keyword>
  <Keyword id="Keyword_badge">
    <Group matchStyle="string">
      <Term>card</Term>
      <Term>badge</Term>
      <Term caseSensitive="true">ID</Term>
    </Group>
  </Keyword>
  <Keyword id="Keyword_false_positives_local">
    <Group matchStyle="word">
      <Term>credit card</Term>
      <Term>national ID</Term>
    </Group>
  </Keyword>
  <Keyword id="Keyword_false_positives_intl">
    <Group matchStyle="word">
      <Term>identity card</Term>
      <Term>national ID</Term>
      <Term>EU debit card</Term>
    </Group>
  </Keyword>
  <LocalizedStrings>
    <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB378">
      <Name default="true" langcode="en-us">Employee ID</Name>
      <Description default="true" langcode="en-us">
      A custom classification for detecting Employee IDs.
      </Description>
      <Description default="false" langcode="de-de">
      Description for German locale.
      </Description>
    </Resource>
  </LocalizedStrings>
</Rules>
</RulePackage>
```

## <a name="what-are-your-key-requirements-rule-entity-pattern-elements"></a>主な要件 [Rule、Entity、Pattern 要素]

ルールの XML スキーマの基本的な構造を理解することが重要です。 構造を理解すると、カスタムの機密情報の種類が適切なコンテンツを識別するのに役立ちます。

ルールは、1 つ以上のエンティティ (機密情報の種類とも呼ばれる) を定義します。 各エンティティは、1 つ以上のパターンを定義します。 パターンとは、ポリシーがコンテンツ (電子メールやドキュメントなど) を評価するときにポリシーが検索するパターンです。

XML マークアップでは、"rules" は機密情報の種類を定義するパターンを意味します。 この記事のルールへの参照を、他の Microsoft の機能で一般的な "条件" や "アクション" に関連付けない。

### <a name="simplest-scenario-entity-with-one-pattern"></a>最もシンプルなシナリオ: パターンが 1 つのエンティティ

簡単なシナリオを次に示します。組織で使用されている 9 桁の従業員の ID を含むコンテンツをポリシーで識別します。 パターンは、9 桁の数字を識別するルール内の正規表現を参照します。 9 桁の数字を含むコンテンツは、パターンを満たします。

![1 つのパターンを持つエンティティの図。](../media/4cc82dcf-068f-43ff-99b2-bac3892e9819.png)

ただし、このパターンでは **、9 桁** の数字 (長い数字や、従業員の ID ではない 9 桁の数字の他の種類を含む) を識別する場合があります。 この種類の望ましくない一致は、誤検知と *呼ばれる。*

### <a name="more-common-scenario-entity-with-multiple-patterns"></a>より一般的なシナリオ: パターンが複数あるエンティティ

誤検知が発生する可能性がある場合、通常は複数のパターンを使用してエンティティを定義します。 複数のパターンは、ターゲット エンティティの証拠をサポートします。 たとえば、追加のキーワード、日付、または他のテキストは、元のエンティティ (たとえば、9 桁の従業員番号) を識別するのに役立ちます。

たとえば、従業員 ID を含むコンテンツを識別する可能性を高めるには、次のパターンを定義できます。

- 採用日を識別するパターン。
- 採用日と "従業員 ID" キーワードの両方を識別するパターン。

![複数のパターンを持つエンティティの図。](../media/c8dc2c9d-00c6-4ebc-889a-53b41a90024a.png)

複数のパターンの一致に関して考慮すべき重要な点は次のとおりです。

- より多くの証拠が必要なパターンの方が信頼度が高くなります。 信頼度に基づいて、次のアクションを実行できます。
  - 信頼性の高い一致で、より制限の厳しいアクション (ブロック コンテンツなど) を使用します。
  - 信頼性の低い一致で制限の少ないアクション (送信通知など) を使用します。

- サポートと `IdMatch` 要素 `Match` は、実際には要素の子である RegExes `Rule` `Pattern`とキーワードを参照します。. これらのサポート要素は、 によって参照 `Pattern`されますが、 に含まれています `Rule`。 この動作は、正規表現やキーワード リストなど、サポート要素の 1 つの定義を複数のエンティティとパターンで参照できるという意味です。

## <a name="what-entity-do-you-need-to-identify-entity-element-id-attribute"></a>どのエンティティを識別する必要がありますか? [Entity 要素, ID 属性]

エンティティは、明確に定義されたパターンを持つ、クレジットカード番号などの機密情報の種類です。各エンティティは、ID として一意の GUID を持っています。

### <a name="name-the-entity-and-generate-its-guid"></a>エンティティに名前を付けて GUID を生成する

1. 選択した XML エディターで、要素と要素を `Rules` 追加 `Entity` します。
2. 従業員 ID など、ユーザー設定エンティティの名前を含むコメントを追加します。 後で、エンティティ名をローカライズされた文字列セクションに追加し、ポリシーを作成するときにその名前が管理センターに表示されます。
3. エンティティの一意の GUID を生成します。 たとえば、次のWindows PowerShellコマンドを実行できます`[guid]::NewGuid()`。 後で、エンティティのローカライズされた文字列セクションに GUID を追加します。

![ルールと Entity 要素を示す XML マークアップ。](../media/c46c0209-0947-44e0-ac3a-8fd5209a81aa.png)

## <a name="what-pattern-do-you-want-to-match-pattern-element-idmatch-element-regex-element"></a>マッチングするパターン [Pattern 要素、IdMatch 要素、Regex 要素]

パターンには、機密情報の種類の一覧が含まれている。 このパターンには、RegExes、キーワード、組み込み関数を含めできます。 関数は、RegExes を実行して日付や住所を検索するタスクを実行します。 機密情報の種類には、固有の信頼レベルを持つ複数のパターンを指定することができます。

次の図では、すべてのパターンが同じ正規表現を参照しています。 この RegEx は、空白で囲まれた 9 `(\d{9})` 桁の数字を検索します `(\s) ... (\s)`。 この正規表現は要素によって `IdMatch` 参照され、Employee ID エンティティを探すすべてのパターンに対する一般的な要件です。 `IdMatch` は、パターンが一致しようとしている識別子です。 要素には `Pattern` 、1 つの要素が必要 `IdMatch` です。

![単一の Regex 要素を参照する複数の Pattern 要素を示す XML マークアップ。](../media/8f3f497b-3b8b-4bad-9c6a-d9abf0520854.png)

満たされたパターンの一致は、ポリシーの条件で使用できるカウントと信頼度を返します。 機密情報の種類を検出する条件をポリシーに追加すると、次の図に示すように、カウントと信頼度を編集できます。 信頼度 (マッチ精度とも呼ばれる) については、この記事の後半で説明します。

![インスタンス数と一致精度のオプション。](../media/sit-confidence-level.png)

正規表現は強力なので、知る必要がある問題があります。 たとえば、コンテンツが多すぎると識別される RegEx がパフォーマンスに影響を与える可能性があります。 これらの問題の詳細については、この記事の後半[](#potential-validation-issues-to-be-aware-of)の「潜在的な検証の問題に注意する」を参照してください。

## <a name="do-you-want-to-require-additional-evidence-match-element-mincount-attribute"></a>追加の証拠が必要な場合 [Match 要素、minCount 属性]

さらに、パターン `IdMatch`は要素 `Match` を使用して、キーワード、RegEx、日付、アドレスなどの追加の証拠を要求できます。

A には `Pattern` 、複数の要素が含 `Match` まれる場合があります。

- 要素内で直接 `Pattern` 指定します。
- 要素を使用して結合 `Any` します。

`Match` 要素は暗黙的 AND 演算子によって結合されます。 つまり、パターンが一 `Match` 致するには、すべての要素を満たす必要があります。

要素を使用して AND `Any` 演算子または OR 演算子を導入できます。 要素 `Any` については、この記事で後述します。

省略可能な属性を使用 `minCount` して、各要素に対して一致する必要があるインスタンスの数を指定 `Match` できます。 たとえば、キーワード リストから少なくとも 2 つのキーワードが見つかった場合にのみ、パターンを満たします。

![minOccurs 属性を持つ Match 要素を示す XML マークアップ。](../media/607f6b5e-2c7d-43a5-a131-a649f122e15a.png)

### <a name="keywords-keyword-group-and-term-elements-matchstyle-and-casesensitive-attributes"></a>キーワード [Keyword 要素、Group 要素、Term 要素、matchStyle 属性、caseSensitive 属性]

前述したように、機密情報を特定するには、多くの場合、追加のキーワードを証拠として必要とします。 たとえば、9 桁の数字に一致する以外に、Keyword 要素を使用して"card"、"badge"、"ID" のような単語を検索できます。 要素 `Keyword` には、複数の `ID` パターンまたはエンティティ内 `Match` の複数の要素で参照できる属性があります。

キーワードは、要素内の要素のリスト `Term` として含 `Group` まれます。 要素には `Group` 、次の 2 つの `matchStyle` 値を持つ属性があります。

- **matchStyle="word"**: 単語の一致は、空白または他の区切り記号で囲まれた単語全体を識別します。 アジア言語の単語または **単語** の一部を一致する必要がない限り、常に単語を使用する必要があります。

- **matchStyle="string"**: 文字列の一致は、囲まれている文字列に関係なく文字列を識別します。 たとえば、"ID" は "bid" と "idea" と一致します。 アジア `string` 語の単語と一致する必要がある場合、またはキーワードが他の文字列に含まれている可能性がある場合にのみ使用します。

最後に、要素`caseSensitive``Term`の属性を使用して、小文字と大文字を含む、コンテンツがキーワードと完全に一致する必要がある場合に指定できます。

![キーワードを参照する Match 要素を示す XML マークアップ。](../media/e729ba27-dec6-46f4-9242-584c6c12fd85.png)

### <a name="regular-expressions-regex-element"></a>正規表現 [Regex 要素]

この例では、`ID``IdMatch`従業員エンティティは既に要素を使用してパターンの正規表現 (空白で囲まれた 9 桁の数字) を参照しています。 さらに、パターン`Match``Regex`は要素を使用して、追加の要素を参照して、米国の郵便番号の形式で 5 桁または 9 桁の番号など、詳細な証拠を識別できます。

### <a name="additional-patterns-such-as-dates-or-addresses-built-in-functions"></a>日付や住所などのその他のパターン [組み込み関数]

機密情報の種類は、組み込みの関数を使用して、証拠の裏付けを特定することもできます。 たとえば、米国の日付、EU の日付、有効期限、米国の住所などです。 Microsoft 365独自のカスタム関数のアップロードはサポートされていません。 ただし、カスタムの機密情報の種類を作成すると、エンティティは組み込み関数を参照できます。

たとえば、従業員 ID `Func_us_date` バッジには採用日が含まれるので、このカスタム エンティティは組み込み関数を使用して、米国で一般的に使用される形式で日付を識別できます。

詳細は、「[DLP 関数で探索する内容](what-the-dlp-functions-look-for.md)」を参照してください。

![組み込み関数を参照する Match 要素を示す XML マークアップ。](../media/dac6eae3-9c52-4537-b984-f9f127cc9c33.png)

## <a name="different-combinations-of-evidence-any-element-minmatches-and-maxmatches-attributes"></a>証拠のさまざまな組み合わせ [Any 要素、minMatches 属性、maxMatches 属性]

要素では `Pattern` 、すべての要素 `IdMatch` と `Match` 要素が暗黙的な AND 演算子によって結合されます。 つまり、パターンを満たす前に、すべての一致を満たす必要があります。

要素を使用して要素をグループ化することで、より柔軟な `Any` 照合ロジックを作成 `Match` できます。 たとえば、要素を使用して、 `Any` その子要素のすべて、なし、または完全なサブセットを一致 `Match` できます。

要素`Any`にはオプションと`minMatches``maxMatches`属性`Match`が含まれています。これは、パターンが一致する前に満たす必要がある子要素の数を定義するために使用できます。 これらの属性は、*一致する*`Match`証拠のインスタンス数ではなく、要素の数を定義します。 リストの 2 つの`minCount``Match`キーワードなど、特定の一致のインスタンスの最小数を定義するには、要素の属性を使用します (上記を参照)。

### <a name="match-at-least-one-child-match-element"></a>少なくとも 1 つの子 Match 要素に一致する

最小数の要素のみを必要と `Match` するには、属性を使用 `minMatches` できます。 実際には、これらの要素 `Match` は暗黙的 OR 演算子によって結合されます。 この `Any` 要素は、US 形式の日付またはいずれかのリストのキーワードが見つかった場合に満たされます。

```xml
<Any minMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```

### <a name="match-an-exact-subset-of-any-children-match-elements"></a>任意の子 Match 要素の完全サブセットと一致する

要素の正確な数を要求するには `Match` 、同じ `minMatches` 値 `maxMatches` に設定します。 この `Any` 要素は、正確に 1 つの日付またはキーワードが見つかった場合にのみ満たされます。 それ以上の一致がある場合、パターンは一致しません。

```xml
<Any minMatches="1" maxMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```

### <a name="match-none-of-children-match-elements"></a>子 Match 要素のいずれとも一致しない

パターンを満たすための特定の証拠がないことを必須にするには、minMatches と maxMatches の両方を 0 に設定できます。この方法は、誤検知を示す可能性が高いキーワード一覧やその他の証拠がある場合に便利です。

たとえば、従業員 ID エンティティは "ID カード" を指している可能性があるため、キーワード "カード" を探しているとします。ただし、カードという単語が "クレジット カード" という語句内にのみ出現する場合、このコンテンツの "カード" が "ID カード" を示す可能性はあまりありません。そのため、パターンを満たす単語から除外する単語の一覧にキーワードとして "クレジット カード" を追加できます。

```xml
<Any minMatches="0" maxMatches="0" >
    <Match idRef="Keyword_false_positives_local" />
    <Match idRef="Keyword_false_positives_intl" />
</Any>
```

### <a name="match-a-number-of-unique-terms"></a>一意の条件の数を照合する

一意の条件の数を照合する場合、以下の例に示されているように、*uniqueResults* パラメーターを *true* に設定して使用します。

```xml
<Pattern confidenceLevel="75">
    <IdMatch idRef="Salary_Revision_terms" />
    <Match idRef=" Salary_Revision_ID " minCount="3" uniqueResults="true" />
</Pattern>
```

この例では、3 つ以上の一意の一致を使用して、給与改定パターンを定義しています。

## <a name="how-close-to-the-entity-must-the-other-evidence-be-patternsproximity-attribute"></a>エンティティと他の証拠との近接度 [patternsProximity 属性]

機密情報の種類で従業員 ID を表すパターンを検索していて、そのパターンの一部として、"ID" などのキーワードのような補強証拠も検索する場合があります。この証拠が互いに近くにあるほど、パターンが実際の従業員 ID になる可能性が高くなります。パターン内の他の証拠とエンティティの近接度を判断するには、Entity 要素の必須の patternsProximity 属性を使用します。

![patternsProximity 属性を示す XML マークアップ。](../media/e97eb7dc-b897-4e11-9325-91c742d9839b.png)

エンティティ内の各パターンに対し、そのパターンに対して指定されたすべての他の一致について、patternsProximity 属性値で IdMatch の場所からの距離 (Unicode 文字) を定義します。近接ウィンドウは、IdMatch の場所によってアンカーされ、IdMatch の左側と右側にウィンドウが展開されます。

![近接ウィンドウの図。](../media/b593dfd1-5eef-4d79-8726-a28923f7c31e.png)

以下の例は、従業員 ID のカスタム エンティティの IdMatch 要素で、キーワードまたは日付の少なくとも 1 つの補完的な一致を必要とするパターン マッチングに対して、近接ウィンドウがどのように影響するかを示しています。ID2 と ID3 の場合、近接ウィンドウ内に補強証拠がまったくないか、部分的にしかないため、ID1 のみが一致します。

![腐食証拠と近接ウィンドウの図。](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

電子メールの場合、メッセージ本文と各添付ファイルは個別のアイテムとして扱われる点に注意してください。 つまり、近接ウィンドウは、これらの各項目の末尾を超えて拡張されません。 アイテム (添付ファイルまたは本文) ごとに、idMatch と詳細証拠の両方をそのアイテムに存在する必要があります。

## <a name="what-are-the-right-confidence-levels-for-different-patterns-confidencelevel-attribute-recommendedconfidence-attribute"></a>パターンごとの適切な信頼度 [confidenceLevel 属性、recommendedConfidence 属性]

パターンに必要な証拠が多くなるほど、パターンが一致したときに実際のエンティティ (従業員 ID など) が特定される信頼度が高くなります。たとえば、9 桁の ID 番号、雇用日、近接度の高いキーワードが必要なパターンの場合、9 桁の ID 番号のみが必要なパターンよりも信頼度が高くなります。

Pattern 要素には必須の confidenceLevel 属性があります。confidenceLevel の値 (1 から 100 の整数) は、エンティティに含まれる各パターンの一意の ID と考えることができます。エンティティのパターンには、異なる信頼度を割り当てる必要があります。この整数を細かく指定することにあまり大きな意味はありません。社内のコンプライアンス チームにとって意味のある数値を選択してください。カスタムの機密情報の種類をアップロードし、ポリシーを作成したら、作成するルールの条件でその信頼度を参照できます。

![confidenceLevel 属性の異なる値を持つ Pattern 要素を示す XML マークアップ。](../media/sit-xml-markedup-2.png)

Entity には各パターン の confidenceLevel に加え、 recommendedConfidence 属性があります。 recommendedConfidence 属性は、ルールの既定の信頼度と考えることができます。 ポリシーでルールを作成するときに、使用するルールの信頼度を指定しない場合、そのエンティティの推奨される信頼度に基づいてルールのマッチングが行われます。 ルールパッケージ内で各エンティティ ID に recommendedConfidence 属性が必須であることに注意してください。存在しない場合、機密情報の種類を使用するポリシーを保存できません。

## <a name="do-you-want-to-support-other-languages-in-the-ui-of-the-compliance-center-localizedstrings-element"></a>コンプライアンス センターの UI で他の言語をサポートする場合 [LocalizedStrings 要素]

コンプライアンス チームが Microsoft 365 コンプライアンス センターを使用して異なるロケールと異なる言語でポリシーを作成する場合、カスタムの機密情報の種類の名前と説明について、ローカライズされたバージョンを提供することができます。コンプライアンス チームがサポートしている言語で Microsoft 365 を使用すると、ローカライズされた名前が UI に表示されます。

![インスタンス数と一致精度の構成。](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

Rules 要素には、LocalizedStrings 要素を含める必要があります。LocalizedStrings 要素には、カスタム エンティティの GUID を参照する Resource 要素が含まれています。また、各 Resource 要素には、1 つまたは複数の Name 要素と Description 要素が含まれており、それぞれが langcode 属性を使用して特定の言語のローカライズされた文字列を提供します。

![LocalizedStrings 要素の内容を示す XML マークアップ。](../media/a96fc34a-b93d-498f-8b92-285b16a7bbe6.png)

ローカライズされた文字列は、カスタムの機密情報の種類がコンプライアンス センターの UI でどのように表示されるかを指定するためにのみ使用できることに注意してください。ローカライズされた文字列を使用して、キーワード リストまたは正規表現の異なるローカライズ バージョンを提供することはできません。

## <a name="other-rule-package-markup-rulepack-guid"></a>その他のルール パッケージ マークアップ [RulePack GUID]

最後に、各 RulePackage の先頭には、入力する必要のある一般的な情報が含まれています。次のマークアップをテンプレートとして使用し、「. . .」プレースホルダーを自分の情報に置き換えることができます。

最も重要な点は、RulePack の GUID を生成する必要があることです。これまでにエンティティの GUID を生成しましたが、これは RulePack の 2 つ目の GUID です。GUID を生成するにはいくつかの方法がありますが、PowerShell では [guid]::NewGuid() と入力することで簡単に行うことができます。

Version 要素も重要です。ルール パッケージを初めてアップロードすると、Microsoft 365 はバージョン番号を記録します。後でルール パッケージを更新して新しいバージョンをアップロードする場合は、バージョン番号を必ず更新してください。そうしないと、Microsoft 365 で新しいルール パッケージは展開されません。

```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." />
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>

 <Rules>
  . . .
 </Rules>
</RulePackage>
```

完了すると、RulePack 要素は次のようになります。

![RulePack 要素を示す XML マークアップ。](../media/fd0f31a7-c3ee-43cd-a71b-6a3813b21155.png)

## <a name="validators"></a>検証ツール

Microsoft 365一般的に使用される SIT の関数プロセッサを検証ツールとして公開します。 その一覧を次に示します。

### <a name="list-of-currently-available-validators"></a>現在使用可能な検証ツールの一覧

- `Func_credit_card`
- `Func_ssn`
- `Func_unformatted_ssn`
- `Func_randomized_formatted_ssn`
- `Func_randomized_unformatted_ssn`
- `Func_aba_routing`
- `Func_south_africa_identification_number`
- `Func_brazil_cpf`
- `Func_iban`
- `Func_brazil_cnpj`
- `Func_swedish_national_identifier`
- `Func_india_aadhaar`
- `Func_uk_nhs_number`
- `Func_Turkish_National_Id`
- `Func_australian_tax_file_number`
- `Func_usa_uk_passport`
- `Func_canadian_sin`
- `Func_formatted_itin`
- `Func_unformatted_itin`
- `Func_dea_number_v2`
- `Func_dea_number`
- `Func_japanese_my_number_personal`
- `Func_japanese_my_number_corporate`

これにより、独自の RegEx を定義して検証できます。 バリデーターを使用するには、独自の RegEx を定義し `Validator` 、プロパティを使用して、選択した関数プロセッサを追加します。 定義が完了したら、SIT でこの RegEx を使用できます。

次の例では、正規表現 - Regex_credit_card_AdditionalDelimiters がクレジット カードに対して定義され、その後、Func_credit_card を検証ツールとして使用してクレジット カードのチェックサム関数を使用して検証されます。

```xml
<Regex id="Regex_credit_card_AdditionalDelimiters" validators="Func_credit_card"> (?:^|[\s,;\:\(\)\[\]"'])([0-9]{4}[ -_][0-9]{4}[ -_][0-9]{4}[ -_][0-9]{4})(?:$|[\s,;\:\(\)\[\]"'])</Regex>
<Entity id="675634eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
<Pattern confidenceLevel="85">
<IdMatch idRef="Regex_credit_card_AdditionalDelimiters" />
<Any minMatches="1">
<Match idRef="Keyword_cc_verification" />
<Match idRef="Keyword_cc_name" />
<Match idRef="Func_expiration_date" />
</Any>
</Pattern>
</Entity>
```

Microsoft 365 2 つの汎用バリデーターを提供する

### <a name="checksum-validator"></a>チェックサム検証ツール

この例では、従業員 ID のチェックサム検証ツールを定義して、RegEx for EmployeeID を検証します。

```xml
<Validators id="EmployeeIDChecksumValidator">
<Validator type="Checksum">
<Param name="Weights">2, 2, 2, 2, 2, 1</Param>
<Param name="Mod">28</Param>
<Param name="CheckDigit">2</Param> <!-- Check 2nd digit -->
<Param name="AllowAlphabets">1</Param> <!— 0 if no Alphabets -->
</Validator>
</Validators>
<Regex id="Regex_EmployeeID" validators="ChecksumValidator">(\d{5}[A-Z])</Regex>
<Entity id="675634eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
<Pattern confidenceLevel="85">
<IdMatch idRef="Regex_EmployeeID"/>
</Pattern>
</Entity>
```

### <a name="date-validator"></a>Date Validator

この例では、RegEx パーツに対して日付検証機能が定義され、その部分は date です。

```xml
<Validators id="date_validator_1"> <Validator type="DateSimple"> <Param name="Pattern">DDMMYYYY</Param> <!—supported patterns DDMMYYYY, MMDDYYYY, YYYYDDMM, YYYYMMDD, DDMMYYYY, DDMMYY, MMDDYY, YYDDMM, YYMMDD --> </Validator> </Validators>
<Regex id="date_regex_1" validators="date_validator_1">\d{8}</Regex>
```

## <a name="changes-for-exchange-online"></a>Exchange Online の変更

以前は、DLP 用にカスタムの機密情報の種類をインポートするために Exchange Online PowerShell を使用することがありました。 カスタムの機密情報の種類は、管理センターとコンプライアンス センター <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange両方</a>で使用できます。 この改善の一環で、カスタムの機密情報の種類をインポートする場合、コンプライアンス センター PowerShell の使用が必須になりました。Exchange PowerShell からはインポートできません。 カスタムの機密情報の種類は以前と同様に使用できますが、コンプライアンス センターでカスタムの機密情報の種類を変更した場合、Exchange 管理センターに表示されるまでに最大 1 時間かかる可能性があります。

コンプライアンス センターでは、**[New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)** コマンドレットを入力して、ルール パッケージをアップロードします。 (以前は、Exchange 管理センターで **ClassificationRuleCollection** コマンドレットを使用していました。)

## <a name="upload-your-rule-package"></a>ルール パッケージをアップロードする

ルール パッケージをアップロードするには、次の手順を実行します。

1. ルールを Unicode エンコードで .xml ファイルとして保存します。

2. [コンプライアンス センター PowerShell に接続する](/powershell/exchange/exchange-online-powershell)

3. 次の構文を使用してください。

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData ([System.IO.File]::ReadAllBytes('PathToUnicodeXMLFile'))
   ```

   この例では、MyNewRulePack.xml という名前の Unicode XML ファイルを C:\My Documents からアップロードします。

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData ([System.IO.File]::ReadAllBytes('C:\My Documents\MyNewRulePack.xml'))
   ```

   構文とパラメーターの詳細情報については、[New-dlpsensitiveinformationtyperulepackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage) をご覧ください。

   > [!NOTE]
   > サポートされるルール パッケージの最大数は 10 ですが、各パッケージには複数の機密情報の種類の定義を含めることができます。

4. 新しい機密情報の種類が正常に作成されたことを確認するには、次に示す手順のいずれかを実行します。

   - [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) コマンドレットを実行して、新しいルール パッケージが一覧表示されることを確認します。

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) コマンドレットを使用して、機密情報の種類が一覧表示されることを確認します。

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     カスタムの機密情報の種類の場合、Publisher プロパティ値を Microsoft Corporation 以外に設定します。

   - \<Name\>Name を機密情報の種類の名前値 (たとえば、従業員 ID) に置き換えて、[Get-DlpSensitiveInformationType ](/powershell/module/exchange/get-dlpsensitiveinformationtype)コマンドレットを実行します。

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="potential-validation-issues-to-be-aware-of"></a>注意する必要がある潜在的な検証の問題

ルール パッケージの XML ファイルをアップロードすると、システムで XML が検証され、既知の不適切なパターンや明らかなパフォーマンスの問題が確認されます。検証で確認される既知の正規表現に関する問題について一部を紹介します。

- 正規表現の Lookbehind アサーションは、固定の長さである必要があります。 可変長アサーションでは、エラーが発生します。

  たとえば、検証 `"(?<=^|\s|_)"` に合格しません。 最初のパターン (`^`) は長さが 0 で、次の 2 つのパターン ( と`\s` `_`) の長さは 1 です。 この正規表現を書く別の方法は、 です `"(?:^|(?<=\s|_))"`。

- 空の一致と見なされるので、すべてと一致する alternator `|`で開始または終了することはできません。

  たとえば、検証に `|a` `b|` 合格しない場合などです。

- 機能上の目的を持ち `.{0,m}` 、パフォーマンスを低下させるだけのパターンで開始または終了することはできません。

  たとえば、検証に `.{0,50}ASDF` `ASDF.{0,50}` 合格しない場合などです。

- グループを持 `.{0,m}` つ、 `.{1,m}` またはグループに含め、グループを持 `.\*` つ、またはグループに `.+` することはできません。

  たとえば、検証 `(.{0,50000})` に合格しません。

- グループ内にリピーターまたはリ `{0,m}` ピーター `{1,m}` を含む文字を含めすることはできません。

  たとえば、検証 `(a\*)` に合格しません。

- 開始または終了できません。 `.{1,m}`代わりに、 を使用します `.`。

  たとえば、検証 `.{1,m}asdf` に合格しません。 代わりに、 を使用します `.asdf`。

- グループに非バウンドリピータ (`*``+`または) を設定することはできません。

  たとえば、検証 `(xx)\*` に `(xx)+` 合格しません。

- キーワードの長さは最大 50 文字です。  グループ内にこれを超えるキーワードがある場合、推奨される解決策は、用語のグループを[キーワード ディクショナリ](./create-a-keyword-dictionary.md)として作成し、ファイル内の Match または idMatch のエンティティの一部として XML 構造内のキーワード ディクショナリの GUID を参照することです。

- 各カスタム機密情報タイプには、合計で最大 2048 個のキーワードを含めることができます。

- 1 つのテナントのキーワード ディクショナリの最大サイズは、スキーマの制限に準拠AD 480 KB です。 カスタムの機密情報の種類を作成する場合、同じ辞書を必要な回数だけ参照します。 キーワード リストに 2048 個を超えるキーワードがある場合、またはキーワードの長さが 50 文字を超える場合は、まず機密情報の種類のカスタム キーワード リストを作成し、キーワード辞書を使用します。

- テナントでは、最大 50 のキーワード辞書ベースの機密情報の種類が許可されます。

- 各 Entity 要素に recommendedConfidence 属性が含まれていることを確認します。

- PowerShell コマンドレットを使用する場合、逆シリアル化されたデータの最大戻りサイズは約 1 メガバイトです。   これは、ルール パックの XML ファイルのサイズに影響します。 処理時にエラーが発生しない一貫した結果を得るための推奨制限として、アップロードされたファイルを最大 770 メガバイトに制限してください。

- XML 構造では、スペース、タブ、キャリッジ リターン/ラインフィード エントリなどの書式設定文字は必要としません。  アップロードのスペースを最適化するときは、このことに注意してください。 Microsoft Visual Code などのツールは、XML ファイルを圧縮するための結合線機能を提供します。

パフォーマンスに影響する可能性のある問題がカスタムの機密情報の種類に含まれている場合は、アップロードされず、次のいずれかのエラー メッセージが表示されることがあります。

- `Generic quantifiers which match more content than expected (e.g., '+', '*')`

- `Lookaround assertions`

- `Complex grouping in conjunction with general quantifiers`

## <a name="recrawl-your-content-to-identify-the-sensitive-information"></a>コンテンツを再クロールして機密情報を特定する

Microsoft 365 は、検索クローラーを使用して、サイト コンテンツ内の機密情報を特定し、分類しています。SharePoint Online サイトと OneDrive for Business サイトのコンテンツが更新されると、自動的に再クロールされます。ただし、既存のすべてのコンテンツで新しいカスタムの機密情報の種類を特定するには、そのコンテンツを再クロールする必要があります。

このMicrosoft 365組織全体の再収集を手動で要求することはできませんが、サイト コレクション、リスト、またはライブラリの再収集を手動で要求できます。 詳細については、「サイト、ライブラリ、またはリストのクロールとインデックスの再作成を手動で要求 [する」を参照してください](/sharepoint/crawl-site-content)。

## <a name="reference-rule-package-xml-schema-definition"></a>リファレンス: ルール パッケージ XML スキーマの定義

このマークアップをコピーし、XSD ファイルとして保存して、ルール パッケージの XML ファイルの検証に使用できます。

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:mce="http://schemas.microsoft.com/office/2011/mce"
           targetNamespace="http://schemas.microsoft.com/office/2011/mce"
           xmlns:xs="https://www.w3.org/2001/XMLSchema"
           elementFormDefault="qualified"
           attributeFormDefault="unqualified"
           id="RulePackageSchema">
  <!-- Use include if this schema has the same target namespace as the schema being referenced, otherwise use import -->
  <xs:element name="RulePackage" type="mce:RulePackageType"/>
  <xs:simpleType name="LangType">
    <xs:union memberTypes="xs:language">
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value=""/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="GuidType" final="#all">
    <xs:restriction base="xs:token">
      <xs:pattern value="[0-9a-fA-F]{8}\-([0-9a-fA-F]{4}\-){3}[0-9a-fA-F]{12}"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulePackageType">
    <xs:sequence>
      <xs:element name="RulePack" type="mce:RulePackType"/>
      <xs:element name="Rules" type="mce:RulesType">
        <xs:key name="UniqueRuleId">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueProcessorId">
          <xs:selector xpath="mce:Regex|mce:Keyword|mce:Fingerprint"></xs:selector>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueResourceIdRef">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:key>
        <xs:keyref name="ReferencedRuleMustExist" refer="mce:UniqueRuleId">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:keyref>
        <xs:keyref name="RuleMustHaveResource" refer="mce:UniqueResourceIdRef">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:keyref>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="RulePackType">
    <xs:sequence>
      <xs:element name="Version" type="mce:VersionType"/>
      <xs:element name="Publisher" type="mce:PublisherType"/>
      <xs:element name="Details" type="mce:DetailsType">
        <xs:key name="UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="mce:LocalizedDetails"/>
          <xs:field xpath="@langcode"/>
        </xs:key>
        <xs:keyref name="DefaultLangCodeMustExist" refer="mce:UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="."/>
          <xs:field xpath="@defaultLangCode"/>
        </xs:keyref>
      </xs:element>
      <xs:element name="Encryption" type="mce:EncryptionType" minOccurs="0" maxOccurs="1"/>
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="VersionType">
    <xs:attribute name="major" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="minor" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="build" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="revision" type="xs:unsignedShort" use="required"/>
  </xs:complexType>
  <xs:complexType name="PublisherType">
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="LocalizedDetailsType">
    <xs:sequence>
      <xs:element name="PublisherName" type="mce:NameType"/>
      <xs:element name="Name" type="mce:RulePackNameType"/>
      <xs:element name="Description" type="mce:OptionalNameType"/>
    </xs:sequence>
    <xs:attribute name="langcode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="DetailsType">
    <xs:sequence>
      <xs:element name="LocalizedDetails" type="mce:LocalizedDetailsType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="defaultLangCode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="EncryptionType">
    <xs:sequence>
      <xs:element name="Key" type="xs:normalizedString"/>
      <xs:element name="IV" type="xs:normalizedString"/>
    </xs:sequence>
  </xs:complexType>
  <xs:simpleType name="RulePackNameType">
    <xs:restriction base="xs:token">
      <xs:minLength value="1"/>
      <xs:maxLength value="64"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="NameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="1"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="OptionalNameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="0"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="RestrictedTermType">
    <xs:restriction base="xs:string">
      <xs:minLength value="1"/>
      <xs:maxLength value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulesType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Entity" type="mce:EntityType"/>
        <xs:element name="Affinity" type="mce:AffinityType"/>
        <xs:element name="Version" type="mce:VersionedRuleType"/>
      </xs:choice>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Regex" type="mce:RegexType"/>
        <xs:element name="Keyword" type="mce:KeywordType"/>
        <xs:element name="Fingerprint" type="mce:FingerprintType"/>
        <xs:element name="ExtendedKeyword" type="mce:ExtendedKeywordType"/>
      </xs:choice>
      <xs:element name="LocalizedStrings" type="mce:LocalizedStringsType"/>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="EntityType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedPatternType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="patternsProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="recommendedConfidence" type="mce:ProbabilityType"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="PatternType">
    <xs:sequence>
      <xs:element name="IdMatch" type="mce:IdMatchType"/>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="AffinityType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedEvidenceType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="evidencesProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="thresholdConfidenceLevel" type="mce:ProbabilityType" use="required"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="EvidenceType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="IdMatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
  </xs:complexType>
  <xs:complexType name="MatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
    <xs:attribute name="minCount" type="xs:positiveInteger" use="optional"/>
    <xs:attribute name="uniqueResults" type="xs:boolean" use="optional"/>
  </xs:complexType>
  <xs:complexType name="AnyType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="minMatches" type="xs:nonNegativeInteger" default="1"/>
    <xs:attribute name="maxMatches" type="xs:nonNegativeInteger" use="optional"/>
  </xs:complexType>
  <xs:simpleType name="ProximityType">
    <xs:union>
      <xs:simpleType>
        <xs:restriction base='xs:string'>
          <xs:enumeration value="unlimited"/>
        </xs:restriction>
      </xs:simpleType>
      <xs:simpleType>
        <xs:restriction base="xs:positiveInteger">
          <xs:minInclusive value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="ProbabilityType">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="1"/>
      <xs:maxInclusive value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="WorkloadType">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Exchange"/>
      <xs:enumeration value="Outlook"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="EngineVersionType">
    <xs:restriction base="xs:token">
      <xs:pattern value="^\d{2}\.01?\.\d{3,4}\.\d{1,3}$"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="VersionedRuleType">
    <xs:choice maxOccurs="unbounded">
      <xs:element name="Entity" type="mce:EntityType"/>
      <xs:element name="Affinity" type="mce:AffinityType"/>
    </xs:choice>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedPatternType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedEvidenceType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:simpleType name="FingerprintValueType">
    <xs:restriction base="xs:string">
      <xs:minLength value="2732"/>
      <xs:maxLength value="2732"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="FingerprintType">
    <xs:simpleContent>
      <xs:extension base="mce:FingerprintValueType">
        <xs:attribute name="id" type="xs:token" use="required"/>
        <xs:attribute name="threshold" type="mce:ProbabilityType" use="required"/>
        <xs:attribute name="shingleCount" type="xs:positiveInteger" use="required"/>
        <xs:attribute name="description" type="xs:string" use="optional"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="RegexType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="KeywordType">
    <xs:sequence>
      <xs:element name="Group" type="mce:GroupType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="id" type="xs:token" use="required"/>
  </xs:complexType>
  <xs:complexType name="GroupType">
    <xs:sequence>
      <xs:choice>
        <xs:element name="Term" type="mce:TermType" maxOccurs="unbounded"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="matchStyle" default="word">
      <xs:simpleType>
        <xs:restriction base="xs:NMTOKEN">
          <xs:enumeration value="word"/>
          <xs:enumeration value="string"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  </xs:complexType>
  <xs:complexType name="TermType">
    <xs:simpleContent>
      <xs:extension base="mce:RestrictedTermType">
        <xs:attribute name="caseSensitive" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="ExtendedKeywordType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="LocalizedStringsType">
    <xs:sequence>
      <xs:element name="Resource" type="mce:ResourceType" maxOccurs="unbounded">
      <xs:key name="UniqueLangCodeUsedInNamePerResource">
        <xs:selector xpath="mce:Name"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
      <xs:key name="UniqueLangCodeUsedInDescriptionPerResource">
        <xs:selector xpath="mce:Description"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
    </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="ResourceType">
    <xs:sequence>
      <xs:element name="Name" type="mce:ResourceNameType" maxOccurs="unbounded"/>
      <xs:element name="Description" type="mce:DescriptionType" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="idRef" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="ResourceNameType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="DescriptionType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
</xs:schema>
```

## <a name="more-information"></a>詳細情報

- [データ損失防止について](dlp-learn-about-dlp.md)
- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
- [DLP 関数の検索対象](what-the-dlp-functions-look-for.md)
