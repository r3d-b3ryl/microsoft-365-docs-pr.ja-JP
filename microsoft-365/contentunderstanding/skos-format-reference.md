---
title: SharePoint 分類の SKOS 形式リファレンス
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
description: SharePoint 分類の SKOS 形式リファレンス
ms.openlocfilehash: eb228394b06b6e6027937ab105df7c0079875226
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296081"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>SharePoint 分類の SKOS 形式リファレンス

この記事には、 [SharePoint の分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) を表すために使用される RDF ボキャブラリが含まれており、 [skos](https://www.w3.org/TR/skos-primer/)に基づいています。 この RDF 構文のシリアル化では、RDF [タートル](https://www.w3.org/TR/turtle/)を使用します。

次の表は、 [SharePoint の分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy)の語彙に相当する[skos](https://www.w3.org/TR/skos-primer/)を示しています。 SharePoint では、SharePoint 分類が対応していない [Skos](https://www.w3.org/TR/skos-primer/) 値はサポートされていません。

|SharePoint 分類|SKOS の同等物|
|:-----------------|:--------------|
|sharepoint-分類: 用語|skos: 概念|
|sharepoint-分類: 用語セット|skos: ConceptScheme|
|sharepoint-分類: inTermSet|skos: inScheme|
|sharepoint-分類: hasTopLevelTerm|skos: hasTopConcept|
|sharepoint-分類: topLevelTermOf|skos: topConceptOf|
|sharepoint-分類: defaultLabel|skos: prefLabel|
|sharepoint-分類: termSetName|skos: prefLabel|
|sharepoint-分類: propertyName|skos: prefLabel|
|sharepoint-分類: otherLabel|skos: altLabel|
|sharepoint-分類: 説明|skos: definition|
|sharepoint-分類: 親|skos: より幅広い|
|sharepoint-分類: 子|skos: 狭い|

次の表に、 [OWL](https://www.w3.org/TR/owl2-primer/)から派生した SharePoint 分類ボキャブラリのエンティティを示します。

|SharePoint 分類ボキャブラリ|OWL から派生したもの|
|:-----------------------------|:----------------------|
|sharepoint-分類: Is持ち Forタグ|owl:datatypeproperty|
|sharepoint-分類: SharedCustomPropertyForTerm|owl: ObjectProperty|
|sharepoint-分類: LocalCustomPropertyForTerm|owl: ObjectProperty|
|sharepoint-分類: CustomPropertyForTermSet|owl: ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>SharePoint 分類ボキャブラリ

分類は、正式な分類システムです。 分類は、何かを説明する単語、ラベル、用語をグループ化し、そのグループを階層に配置します。

**sharepoint-分類: 用語**

管理メタデータ階層内の Term またはキーワードを表します。

[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)は、SharePoint[用語ストア](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)の原子単位です。 各[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)は、 [Termgroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)に属する[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)に属します。 

[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を定義する構文は次のとおりです。

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)内に Compulsorily と[いう用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)が存在する。 DefaultLabel は、視覚的表現に表示される [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) の名前です。 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を定義するために必要なフィールドは次のとおりです。

- sharepoint-分類: defaultLabel
- sharepoint-分類: inTermSet

[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)は次のようになります。

- 同じ[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)に属する[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)が存在する別の[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)に階層的に関連付けられます。
- 複数の子 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)がありますが、1つの親 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)のみが含まれます。
- 親 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) が定義されていない (TopLevelTermOf a [用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)の場合)。
- [用語ストア](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)作業言語ごとに1つの defaultlabel を用意します。
- 親 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)が含まれていない場合、または TopLevelTermOf a [用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)でない場合は、存在しません。 
- 同じ階層レベルに一意の defaultLabel のみを設定します。

**sharepoint-分類: 用語セット**

"用語セット" と呼ばれる用語オブジェクトの階層構造またはフラットセットを表します。

名前からわかるように、用語セットは一連の [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)です。 [用語ストア](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)内の[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)は、[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)に属している必要があります。 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)は単独では存在できません。 

[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)を定義する構文は次のとおりです。

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[Termsets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) は、 [termsets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)に論理的にまとめられています。 [用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)を定義するために必要なフィールドは次のとおりです。

- sharepoint-分類: termSetName

指定された termSetName が [Termgroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)内で一意ではない場合、sharepoint は、termSetName の一意性を維持するために、名前の末尾に数字を追加します。

**sharepoint-分類: hasTopLevelTerm**

SharePoint では、このプロパティを使用して[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)の最上位[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)をマップします。これは、[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)内の[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)の階層へのエントリポイントです。 これは、sharepoint 分類: topLevelTermOf への逆の関係です。 

これを定義する構文は次のとおりです。

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> 親[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)のトップレベル[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を定義することはできません。

**sharepoint-分類: topLevelTermOf**

Sharepoint-分類: topLevelTermOf は、hasTopLevelTerm の逆の方法です。

これを定義する構文は次のとおりです。

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-分類: inTermSet**

[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)にマップするのに使用します。 1つの[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)内にのみ存在する[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)があります。 SharePoint [では、用語を定義](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)するときにこのプロパティが必要です。

## <a name="required-labels"></a>必要なラベル

管理されたメタデータの使用を開始する前に、組織で慎重に計画する必要がある場合があります。 必要な計画の量は、分類の正式な方法によって異なります。 また、メタデータをどの程度制御するかによっても異なります。 階層の各レベルで、用語または用語セットに対して必要な lables を構成する必要があります。

用語には、既定の言語で1つ以上のラベルを含めることができます。また、既定以外の言語では、0個以上のラベルを使用できます。 用語に言語のラベルが含まれている場合、ラベルの1つは既定のラベルである必要があります。

**sharepoint-分類: defaultLabel**

[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)の必須パラメーターである[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)には、この既定の字句ラベルを使用します。 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を視覚的に表すために使用します。

DefaultLabel を定義する構文は次のとおりです。

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

DefaultLabel には、文字列と言語タグの2つの部分が含まれています。 言語は、 [用語ストア](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 作業言語のいずれかである必要があります。 DefaultLabel は、同じ階層レベルで、同じ[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)内のすべての[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)に対して一意である必要があります。

**sharepoint-分類: termSetName**

現在の用語セットオブジェクトの名前を取得または設定します。

これは、 [用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)の字句ラベルで、 [用語ストア](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) の作業言語になります。 これは、 [用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)の必須パラメーターです。 [用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)を視覚的に表すために使用します。

TermSetName を定義する構文は次のとおりです。

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-分類: propertyName**

現在の用語セットオブジェクトのプロパティ名を取得または設定します。

これは、 [用語ストア](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 作業言語では、sharepoint 分類: sharedcustompropertyforterm、Sharepoint-CustomPropertyForTermSet: localcustompropertyforterm、および sharepoint-分類: の字句ラベルです。

Sharepoint 分類: propertyName は、CustomProperty のキーとして扱われます。

PropetyName を定義する構文は次のとおりです。

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>オプションのラベル

また、分類にオプションのラベルを追加することもできます。

**sharepoint-分類: otherLabel**

[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)の代替の字句ラベルです。 

OtherLabel を定義する構文は次のとおりです。

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>セマンティック関係

分類には階層型と単純な "関連用語" という関連性のある関係がありますが、"セマンティックリレーションシップ" またはカスタム作成されたリレーションシップを持つものがあります。 

**sharepoint-分類: 親**

これは、ある [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) を別の [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)に階層的に関連付けます。 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)には、[用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)の最上位の[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を指定することもできますが、その場合には、親の[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)を含める必要はありません。 

親を定義する構文は次のとおりです。

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

これは、TermA1 に親 TermA があることを意味します。 TermA1 は、TermA の子でもあることを意味します。 親子関係は inversible の関係です。

**sharepoint-分類: 子**

オブジェクトには、1つ以上の子用語セットインスタンスが含まれています。これらには、TermSets プロパティを使用してアクセスできます。 このクラスには、新しい子用語セットオブジェクトを作成するためのメソッドも用意されています。 子用語および用語セットインスタンスを編集するためのアクセス許可は、グループで指定されています。 

これは、ある [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) を別の [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)に階層的に関連付けます。

子を定義する構文は次のとおりです。

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

これは、TermA に子 TermA1 があることを意味します。 また、TermA が TermA1 の親子関係の親であることも意味しています。 inversible の関係です。

## <a name="documentation-notes"></a>ドキュメントのメモ

このセクションでは、Microsoft SharePoint の分類の名前空間に詳細が記載されている分類について説明します。

**sharepoint-分類: 説明**

これは、 [SharePoint 分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) ボキャブラリエンティティの詳細な説明です。 

説明を追加するための構文は次のとおりです。

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>カスタム プロパティ

読み取り専用の辞書から、現在の用語オブジェクトのカスタムプロパティオブジェクトのコレクションを取得します。

カスタムプロパティは、 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) または [用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)に対して定義できるキーと値の組み合わせであり、 [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) または [用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)の説明にも使用できます。 SharePoint は、propertyName のヘルプを使用して、カスタムプロパティのキーを指定します。

**sharepoint-分類: CustomPropertyForTermSet**

これを定義する構文は次のとおりです。

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-分類: SharedCustomPropertyForTerm**

用語のカスタムプロパティを[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)と一緒に再利用[する必要が](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)ある場合は、[その用語を別の場所に](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)再利用するときに、sharedcustompropertyforterm の下で定義する必要があります。

これを定義する構文は次のとおりです。

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-分類: LocalCustomPropertyForTerm**

[用語の](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)カスタムプロパティを[用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)と一緒に再利用する必要がない場合は、その用語を別[の場所に](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)再利用するときに、localcustompropertyforterm の下に用語を定義する必要があります。

これを定義する構文は次のとおりです。

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>データプロパティ

階層の各レベルで、用語または用語セットに特定のデータプロパティを構成できます。

**sharepoint-分類: Is持ち Forタグ**

これを使用して、SharePoint リストとライブラリで使用可能な [用語](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) または [用語セット](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) を指定します。  

この場合の構文は次のとおりです。

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>ドメインと範囲

次の表は、SharePoint 分類の語彙のドメインと範囲を示しています。

|述語/動詞|意味|ドメイン|範囲|
|:--------------|:------|:-----|:----|
inTermSet|用語セット内|Term|用語セット|
inTermGroup|用語グループ|TermSet|TermGroup|
topLevelTermOf|トップレベルの用語|Term|TermSet|
hasTopLevelTerm|最上位レベルの用語|用語セット|Term|
termSetName|用語セットの名前|Term|プレーンなリテラル|
defaultLabel|用語に既定のラベルがあります|Term|プレーンなリテラル|
otherLabel|その他のラベルがある用語|Term|プレーンなリテラル|
propertyName|プロパティラベルあり|SharedCustomPropertyForTerm、LocalCustomPropertyForTerm、CustomPropertyForTermSet |Boolean、String、Integer、Decimal、Double|
|説明|説明あり|すべて|プレーンなリテラル|
|親|親がある|Term|Term|
|子供|子がある|Term|Term|
|Is持ち Forタグ|タグ付けに使用可能|用語、用語セット|Boolean|
|SharedCustomPropertyForTerm|共有されたカスタムプロパティがある|Term|Boolean、string、Integer、Decimal、Double|
|LocalCustomPropertyForTerm|ローカルカスタムプロパティがある|Term|Boolean、String、Integer、Decimal、Double|
|CustomPropertyForTermSet|カスタムプロパティあり|TermSet|Boolean、String、Integer、Decimal、Double|

[SharePoint 分類](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy)で許可されていない、 [skos](https://www.w3.org/TR/skos-primer/)の有効なシナリオは次のとおりです。

- 階層的な冗長性- [Skos](https://www.w3.org/TR/skos-primer/) の概念は、複数のより広範な概念に同時にアタッチできますが、sharepoint の分類に含めることができるのは1つの sharepoint 分類だけであり、そのため、用語の循環依存関係も許可されません。
- 孤立した用語は SharePoint 分類では許可されていません。 すべての sharepoint 分類: 用語には、sharepoint の分類を設定する必要があります: 親であるか、sharepoint の分類である必要があります: topLevelTermOf a 用語セット。
- SharePoint 分類は関連関係をサポートしていません。
- SharePoint の分類では、2種類の階層関係のみが許可されます。 sharepoint 分類: 親と sharepoint の分類: 子。 
- [Skos](https://www.w3.org/TR/skos-primer/)とは異なり、SharePoint 分類語彙の階層関係は、同じ用語セット内の用語でのみ確立できます。

## <a name="see-also"></a>関連項目

[SKOS ベースの形式を使用して用語セットをインポートする](import-term-set-skos.md)

