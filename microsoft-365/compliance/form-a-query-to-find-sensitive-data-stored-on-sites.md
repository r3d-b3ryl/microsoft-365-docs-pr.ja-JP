---
title: サイトに保存された機密データを検索するクエリの形成
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
description: SharePoint Online でデータ損失防止 (DLP) を使用して、テナント全体で機密データを含むドキュメントを検出します。
ms.openlocfilehash: 1bb3ed0286f719f9ea9210b4952044081213914f
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66638325"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>サイトに保存された機密データを検索するクエリの形成

ユーザーのサイトには、クレジット カード番号、社会保障番号、個人の機密データが保存されることが多く、これが長期にわたると、組織が重大なデータ損失リスクにさらされる可能性があります。 サイト (OneDrive for Business サイトを含む) に保存されているドキュメントは、情報にアクセスできない組織外のユーザーと共有できます。 SharePoint Online のMicrosoft Purview データ損失防止 (DLP) を使用すると、テナント全体で機密データを含むドキュメントを検出できます。 そのドキュメントが見つかったら、ドキュメントの所有者と連携してデータを保護できます。 このトピックは、機密データを検索するクエリを形成するために役立ちます。

> [!NOTE]
> 電子検出、電子情報開示、DLP は、 [SharePoint Online プラン 2](https://go.microsoft.com/fwlink/?LinkId=510080) を必要とするプレミアム機能です。

## <a name="forming-a-basic-dlp-query"></a>基本的な DLP クエリの形成

基本的な DLP クエリは、SensitiveType、count range、および confidence range の 3 つの部分で構成されています。 次の図に示すように、 **SensitiveType:"\<type\>"** は必須であり、両方 **|\<count range\>** とも **|\<confidence range\>** 省略可能です。

![クエリの例を必須と省略可能に分割します。](../media/DLP-query-example-text.png)

### <a name="sensitive-type---required"></a>機密情報の種類: 必須

では、各部分はどのようなものですか。 SharePoint DLP クエリは通常、プロパティ  `SensitiveType:"` と機密情報の種類 [のインベントリからの情報の種類](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)名で始まります。最後  `"`に 、 . 組織用に作成した [カスタムの機密情報の種類](create-a-custom-sensitive-information-type.md) の名前を使用することもできます。 たとえば、クレジット カード番号が含まれているドキュメントを検索するとします。 このようなインスタンスでは、次の形式を使用します  `SensitiveType:"Credit Card Number"`。 カウント範囲または信頼範囲を含めなかったため、クレジット カード番号が検出されたすべてのドキュメントがクエリによって返されます。 これは実行できる最も簡単なクエリであり、最も多くの結果を返します。 機密情報の種類のスペルと文字間隔は正確に入力する必要があります。

### <a name="ranges---optional"></a>範囲: 省略可能

次の 2 つの部分はどちらも範囲であるため、範囲の外観をすばやく調べてみましょう。 SharePoint DLP クエリでは、基本的な範囲は 2 つのピリオドで区切られた 2 つの数値で表されます。次のようになります  `[number]..[number]`。 たとえば、使用されている場合  `10..20` 、その範囲は 10 から 20 までの数値をキャプチャします。 さまざまな範囲の組み合わせがあり、このトピックで取り上げるものがいくつかあります。

クエリにカウント範囲を追加しましょう。 カウント範囲を使用すると、クエリ結果に含める前にドキュメントに含める必要がある機密情報の出現回数を定義できます。 たとえば、5 つのクレジット カード番号を含むドキュメントのみをクエリで返す場合は、次を使用します  `SensitiveType:"Credit Card Number|5"`。 カウント範囲は、リスクの高いドキュメントを特定するのにも役立ちます。 たとえば、組織では、5 つ以上のクレジット カード番号を持つドキュメントが高リスクであると考える場合があります。 この条件に適合するドキュメントを見つけるには、次のクエリを使用します  `SensitiveType:"Credit Card Number|5.."`。 または、次のクエリ  `SensitiveType:"Credit Card Number|..5"`を使用して、クレジット カード番号が 5 つ以下のドキュメントを見つけることができます。

#### <a name="confidence-range"></a>信頼範囲

最後に、信頼範囲は、検出された機密型が実際に一致するという信頼度のレベルです。 信頼範囲の値は、カウント範囲と同様に機能します。 カウント範囲を含めずにクエリを作成できます。 たとえば、信頼範囲が 85% 以上であれば、任意の数のクレジット カード番号を持つドキュメントを検索するには、次のクエリを使用します  `SensitiveType:"Credit Card Number|*|85.."`。

> [!IMPORTANT]
> アスタリスク ( `*` ) は、任意の値が機能することを意味するワイルドカード文字です。 ワイルドカード文字 ( `*` ) は、カウント範囲または信頼範囲で使用できますが、機密型では使用できません。

### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>電子情報開示センターで使用できるその他のクエリ プロパティと検索演算子

SharePoint の DLP では、LastSensitiveContentScan プロパティも導入されています。これは、特定の期間内にスキャンされたファイルを検索するのに役立ちます。 プロパティを  `LastSensitiveContentScan` 含むクエリの例については、次 [のセクションの複雑なクエリの例](#examples-of-complex-queries) を参照してください。

DLP 固有のプロパティを使用してクエリを作成するだけでなく、標準の SharePoint 電子情報開示検索プロパティ (例:  `Author`  `FileExtension`. 演算子を使用して、複雑なクエリを作成できます。 使用可能なプロパティと演算子の一覧については、 [電子情報開示での検索プロパティと演算子の使用](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery) に関するブログ記事を参照してください。

## <a name="examples-of-complex-queries"></a>例

次の例では、さまざまな機密性の高い型、プロパティ、演算子を使用して、クエリを絞り込んで探しているものを正確に見つける方法を示します。

<br>

****

|Query|説明|
|---|---|
|`SensitiveType:"International Banking Account Number (IBAN)"`|名前は非常に長いため、奇妙に見えるかもしれませんが、その機密性の高い型の正しい名前です。 [機密情報の種類のインベントリ](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)の正確な名前を使用してください。 組織用に作成した [カスタムの機密情報の種類](create-a-custom-sensitive-information-type.md) の名前を使用することもできます。|
|`SensitiveType:"Credit Card Number|1..4294967295|1..100"`|これにより、機密性の高い種類の "クレジット カード番号" に少なくとも 1 つの一致するドキュメントが返されます。 各範囲の値は、それぞれの最小値と最大値です。 このクエリを簡単に記述する方法は  `SensitiveType:"Credit Card Number"`、|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"`|これにより、2018 年 8 月 11 日から 2018 年 8 月 13 日までスキャンされた 5 ~ 25 個のクレジット カード番号を持つドキュメントが返されます。|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX`|これにより、2018 年 8 月 11 日から 2018 年 8 月 13 日までスキャンされた 5 ~ 25 個のクレジット カード番号を持つドキュメントが返されます。 XLSX 拡張子を持つファイルは、クエリ結果に含まれません。  `FileExtension` は、クエリに含めることができる多くのプロパティの 1 つです。 詳細については、「 [電子情報開示での検索プロパティと演算子の使用](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery)」を参照してください。|
|`SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"`|クレジット カード番号または社会保障番号が含まれているドキュメントを返します。|
|

## <a name="examples-of-queries-to-avoid"></a>例

すべてのクエリが平等に作成されているわけではありません。 次の表に、SharePoint で DLP を使用しないクエリの例と、その理由を説明します。

<br>

****

|サポートされていないクエリ|理由|
|---|---|
|`SensitiveType:"Credit Card Number|.."`|少なくとも 1 つの値を追加する必要があります。|
|`SensitiveType:"NotARule"`|"NotARule" は、有効な機密型名ではありません。 DLP クエリでは、 [機密情報の種類のインベントリ](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) 内の名前のみが機能します。|
|`SensitiveType:"Credit Card Number|0"`|0 は、最小値または範囲内の最大値として有効ではありません。|
|`SensitiveType:"Credit Card Number"`|見にくいかもしれませんが、"クレジット" と "Card" の間に余分な空白があり、クエリが無効になります。 機密情報の種類 [のインベントリ](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)から厳密に機密性の高い型名を使用します。|
|`SensitiveType:"Credit Card Number|1. .3"`|2 期間の部分をスペースで区切る必要はありません。|
|`SensitiveType:"Credit Card Number| |1..|80.."`|パイプ区切り記号が多すぎます (\|)。 代わりに、次の形式に従います。 `SensitiveType: "Credit Card Number|1..|80.."`|
|`SensitiveType:"Credit Card Number|1..|80..101"`|信頼度の値はパーセンテージを表すため、100 を超えることはできません。 1 ～ 100 の数値を選択してください。|
|

## <a name="for-more-information"></a>詳細情報

- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
- [コンテンツ検索を実行する](content-search.md)
- [コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)
