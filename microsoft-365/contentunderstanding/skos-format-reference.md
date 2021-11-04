---
title: 「SharePoint 分類計画」のためのSKOSフォーマットの詳細
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ms.localizationpriority: high
description: 「SharePoint 分類計画」のためのSKOSフォーマットの詳細
ms.openlocfilehash: 95183b64d76a70f69d08cd5a3c9dcf76f4e83bce
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747658"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>「SharePoint 分類計画」のためのSKOSフォーマットの詳細

この記事では、[SharePoint の分類](/dotnet/api/microsoft.sharepoint.taxonomy) に使用される RDF ボキャブラリについて説明します。これは [SKOS](https://www.w3.org/TR/skos-primer/)に基づいています。 この RDF 構文のシリアル化には、RDF [タートル](https://www.w3.org/TR/turtle/)を使用します。

次の表は、[SharePoint の分類](/dotnet/api/microsoft.sharepoint.taxonomy) ボキャブラリに相当する [SKOS](https://www.w3.org/TR/skos-primer/) の説明です。 SharePoint は、SharePoint の分類に対応していない [SKOS](https://www.w3.org/TR/skos-primer/) 値をサポートしていません。

|SharePoint 分類計画|SKOS同等物|
|:-----------------|:--------------|
|sharepoint-taxonomy:用語|skos: 概念|
|sharepoint-taxonomy:TermSet|skos: ConceptScheme|
|sharepoint-taxonomy:inTermSet|skos: inScheme|
|sharepoint-taxonomy:hasTopLevelTerm|skos:hasTopConcept|
|sharepoint-taxonomy:topLevelTermOf|skos: topConceptOf|
|sharepoint-taxonomy:defaultLabel|skos:prefLabel|
|sharepoint-taxonomy:termSetName|skos:prefLabel|
|sharepoint-taxonomy:propertyName|skos:prefLabel|
|sharepoint-taxonomy:otherLabel|skos:altLabel|
|sharepoint-taxonomy:説明|skos: 定義|
|sharepoint-taxonomy:parent|skos: より幅広い|
|sharepoint-taxonomy:子供|skos: 狭い|

次の表に、 [OWL](https://www.w3.org/TR/owl2-primer/)から派生した、SharePoint 分類ボキャブラリのエンティティを示します。

|SharePoint の分類ボキャブラリ|OWLから派生。|
|:-----------------------------|:----------------------|
|sharepoint-taxonomy:isAvailableForTagging|owl:datatypeproperty|
|sharepoint-taxonomy:SharedCustomPropertyForTerm|owl: ObjectProperty|
|sharepoint-taxonomy:LocalCustomPropertyForTerm|owl: ObjectProperty|
|sharepoint-taxonomy:CustomPropertyForTermSet|owl: ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>SharePoint の分類ボキャブラリ

分類は、正式なクラス分けシステムです。分類により、何かを記述する単語、ラベル、および用語はグループ化され、それらのグループは 1 つの階層に配置されます。

**sharepoint-taxonomy:用語**

管理されたメタデータ階層内に用語またはキーワードを表します。

[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) は、SharePoint [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)の最小単位です。 各[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) は[TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group)に属する [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) に属します。

[項](/dotnet/api/microsoft.sharepoint.taxonomy.term) を定義する構文は次のとおりです。

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)内に[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) が絶対に存在しなければなりません。 DefaultLabel は、視覚的表現に表示された[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)の名前です。 [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)の定義には、次のようなフィールドが必要です。

- sharepoint-taxonomy:defaultLabel
- sharepoint-taxonomy:inTermSet

[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)は次のことができます；

- 同じ [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)に属している [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) 両方が提供されている[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)に階層を関連付けることができます。
- 複数の子[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)を持っていますが、親 [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)は1つだけです。
- もしそれが[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)のtopLevelTermOfの場合、親 [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)が定義されていません。 
- [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)作業言語毎に1つの defaultLabel が用意されています。
- 親 [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)が含まれていないか、[TermSet ](/dotnet/api/microsoft.sharepoint.taxonomy.termset)のtopLevelTermOf でもない場合は、存在しません。
- 同じ階層レベルで一意の defaultLabel のみを持ちます。

**sharepoint-taxonomy:TermSet**

"TermSet" と呼ばれる、階層構造またはフラットな用語オブジェクトのセットを表します。

名前が示しているように、TermSet は、[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)のセットです。 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) の [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) は [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)に属している必要があります。 [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) は独自に存在できません。

[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) を定義する構文は次のとおりです。

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[Termsets](/dotnet/api/microsoft.sharepoint.taxonomy.termset)は、[TermGroups](/dotnet/api/microsoft.sharepoint.taxonomy.group)内に論理的にグループ化されます。 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) を定義するために必要なフィールドは次のとおりです。

- sharepoint-taxonomy:termSetName

与えられたtermSetName が[TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group)内でユニークではない場合、SharePointは名前の末尾に数字を追加して、termSetNameの独自性を維持します。

**sharepoint-taxonomy:hasTopLevelTerm**

SharePoint では、このプロパティを使用して、[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) の最上位の [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) をマップします。これは、[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) の [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) の階層へのエントリ ポイントです。これは、sharepoint-taxonomy:topLevelTermOf と逆の関係です。

これを定義する構文は次のとおりです。

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

> [!NOTE]
> 親 [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)の最上位の[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) を定義することはできません。

**sharepoint-taxonomy:topLevelTermOf**

Sharepoint-taxonomy:topLevelTermOfは、sharepoint-taxonomy:hasTopLevelTermの逆です。

これを定義する構文は次のとおりです。

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-taxonomy:inTermSet**

これを使用して、 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)を[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)にマッピングします。 [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) は、1つの[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)にのみ存在します。 SharePointがこのプロパティを必要なのは、[用語](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)を定義する場合です。

## <a name="required-labels"></a>必要なラベル

管理されたメタデータの使用を開始する前に、組織で慎重な計画が必要になる場合があります。 必要な計画のボリュームは、分類をどの程度フォーマルにするかによって異なります。 これは、メタデータに適用するコントロールのサイズによっても異なります。 階層の各レベルで、用語または TermSet の必須ラベルを構成する必要があります。

用語には、既定の言語では 1 つ以上のラベル、既定以外の言語では 0 個以上のラベルを含めることができます。用語に言語のラベルがある場合、ラベルの 1 つが既定のラベルである必要があります。

**sharepoint-taxonomy:defaultLabel**

[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) の既定の語彙ラベルを使用します。これは、[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) に必要なパラメーターです。[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) を視覚的に表すために使用します。

DefaultLabel を定義する構文は次のとおりです。

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

DefaultLabel には、文字列と 言語タグという2つの部分があります。 言語は、 [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) の作業言語のいずれかである必要があります。 DefaultLabel は、同じ階層レベルにある同じ [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)内のすべての[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) に関して固有である必要があります。

**sharepoint-taxonomy:termSetName**

現在の TermSet オブジェクトの名前を取得または設定します。

これが、[TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)の作業言語内の[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)の字句ラベルです。 これは、[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)に必須のパラメーターです。 [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)を視覚的に表現するために使用します。

TermSetName を定義する構文は次のとおりです。

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-taxonomy:propertyName**

現在の TermSet オブジェクトのプロパティ名を取得または設定します。

これは、sharepoint-taxonomy:SharedCustomPropertyForTerm、sharepoint-taxonomy:LocalCustomPropertyForTerm および[TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)作業言語内の working language.sharepoint-taxonomy:CustomPropertyForTermSet のTermSetの字句ラベルです。

The sharepoint-taxonomy:propertyNameは、CustomProperty のキーとして扱われます。

PropetyName を定義する構文は次のとおりです。

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>省略可能なラベル。

また、任意のラベルを分類に追加できます。

**sharepoint-taxonomy:otherLabel**

これは、[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)の別の字句ラベルです。

ほかのラベルを定義する構文は次のとおりです。

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>セマンティックの関係

分類は階層的で、場合によっては単純な "関連用語" に関連するリレーションシップですが、"意味的な関係" やユーザー設定のリレーションシップがあるものもあります。

**sharepoint-taxonomy:parent**

これは、[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) を別の[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)に階層的に関連付けます。[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) は、[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) の最上位レベルの [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) である可能性があります。ただし、関連付けしない場合は、親 [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) が必要です。

親を定義する構文は次のとおりです。

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

これは、TermA が親で、TermA が子であることを意味します。

**sharepoint-taxonomy:child**

このオブジェクトには、1つ以上の子 TermSet インスタンスが含まれています。これらは、TermSets プロパティからアクセスできます。 このクラスには、新しい子 TermSet オブジェクトを作成するためのメソッドもあります。 子用語と TermSet インスタンスを編集するためのアクセス許可がグループに指定されています。

これにより、[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) が別の[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)に階層的に関連付けられます。

子を定義する構文は次のとおりです。

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

これは、TermA が親で、TermA が子であることを意味します。

## <a name="documentation-notes"></a>ドキュメントメモ

ここでは、Microsoft.SharePoint.Taxonomy Namespaceに記載されている分類について詳細に説明します。

**sharepoint-taxonomy:description**

ここでは、 [SharePoint の分類](/dotnet/api/microsoft.sharepoint.taxonomy) の語彙のエンティティについて詳しく説明します。

説明を追加する構文は次のとおりです。

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>カスタム プロパティ

読み取り専用ディクショナリから、現在の用語オブジェクトのカスタムプロパティオブジェクトのコレクションを取得します。

カスタムプロパティは、[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) または[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)に対して定義できるキー値のペアです。また、 [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) または [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)の詳細についても説明します。 SharePoint では、propertyName を使用してカスタムプロパティのキーを指定します。

**sharepoint-taxonomy:CustomPropertyForTermSet**

これを定義する構文は次のとおりです。

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-taxonomy:SharedCustomPropertyForTerm**

[Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) のカスタムプロパティを[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)と共に使用する必要があり、[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) を再使用している場合はSharedCustomPropertyForTerm を定義する必要があります。

これを定義する構文は次のとおりです。

```SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-taxonomy:LocalCustomPropertyForTerm**

[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) のカスタムプロパティを [用語](/dotnet/api/microsoft.sharepoint.taxonomy.term)と共に使用する必要がなく、[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) を再利用する場合は、LocalCustomPropertyForTermの下で定義する必要があります。

これを定義する構文は次のとおりです。

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>データ プロパティ

階層の各レベルで、用語や TermSet に特定のデータプロパティを構成できます。

**sharepoint-taxonomy:isAvailableForTagging**

この機能を使用して、SharePoint のリストとライブラリで使用できる[用語](/dotnet/api/microsoft.sharepoint.taxonomy.term) または [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) を指定します。

この構文は次のとおりです。

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>ドメインと範囲

下の表は、SharePoint の分類ボキャブラリのドメインと範囲を示しています。

|述語/動詞|意味|ドメイン|範囲|
|:--------------|:------|:-----|:----|
inTermSet|用語セットで|用語|用語セット|
inTermGroup|用語グループ|TermSet|TermGroup|
topLevelTermOf|は最上位の用語|用語|TermSet|
hasTopLevelTerm|最上位の用語|用語セット|用語|
termSetName|用語セットに名前がある|用語|プレーンリテラル|
defaultLabel|Term に既定のラベルがある|用語|プレーンリテラル|
otherLabel|"その他" というラベル|用語|プレーンリテラル|
PropertyName|プロパティラベルあり|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Boolean、String、Integer、Decimal、Double|
|説明|説明がある|すべて|プレーンリテラル|
|親|親がある|用語|用語|
|子|子がある|用語|用語|
|isAvailableForTagging|タグ付けで使用可能|用語、用語セット|ブール値|
|SharedCustomPropertyForTerm|共有カスタムプロパティがあります|用語|Boolean、string、Integer、Decimal、Double|
|LocalCustomPropertyForTerm|ローカルのカスタムプロパティがあります|用語|Boolean、String、Integer、Decimal、Double|
|CustomPropertyForTermSet|Custom プロパティがある|TermSet|Boolean、String、Integer、Decimal、Double|

[SKOS](https://www.w3.org/TR/skos-primer/)これは[SharePoint の分類](/dotnet/api/microsoft.sharepoint.taxonomy) が許可されていない有効なシナリオ:

- 階層冗長化-[SKOS](https://www.w3.org/TR/skos-primer/) 概念が複数の階層の概念に同時に関連付けられている います。ただし、sharepoint の分類項目：用語は、1つの sharepoint 分類：親しか持てませんので、用語の循環的な依存関係になり、それは許可されません。
- 孤立した用語は、SharePoint 分類では許可されていません。すべての sharepoint-taxonomy:Term には sharepoint-taxonomy:parent が必要です。または、TermSet の sharepoint-taxonomy:topLevelTermOf である必要があります。
- SharePoint の分類は、関連する関係をサポートしていません。
- SharePoint の分類では、2種類の階層関係 (sharepoint-taxonomy:親およびsharepoint-Taxonomy:子) のみが許可されます。
- [SKOS](https://www.w3.org/TR/skos-primer/)とは異なり、SharePoint 分類のボキャブラリの階層関係は、同じTermSet内の用語を使用して作成する必要があります。 

## <a name="see-also"></a>関連項目

[SKOS ベースの形式を使用して用語セットをインポートする](import-term-set-skos.md)