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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: オンラインでデータ損失防止 (DLP) をSharePoint、テナント全体に機密データを含むドキュメントを検出します。
ms.openlocfilehash: e2ecaa6b4b230db09095a9f9e5008dfdf0698043
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191490"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>サイトに保存された機密データを検索するクエリの形成

ユーザーのサイトには、クレジット カード番号、社会保障番号、個人の機密データが保存されることが多く、これが長期にわたると、組織が重大なデータ損失リスクにさらされる可能性があります。 サイトに保存されているドキュメント (OneDrive for Business サイトを含む) は、情報にアクセスできない組織外のユーザーと共有できます。 SharePoint Online のデータ損失防止 (DLP) を使用すると、テナント全体で機密データを含むドキュメントを検出できます。 そのドキュメントが見つかったら、ドキュメントの所有者と連携してデータを保護できます。 このトピックは、機密データを検索するクエリを形成するために役立ちます。

> [!NOTE]
> 電子的検出、または電子情報開示、DLP は、オンライン プラン 2 をSharePoint[プレミアム機能です](https://go.microsoft.com/fwlink/?LinkId=510080)。

## <a name="forming-a-basic-dlp-query"></a>基本的な DLP クエリの形成

基本的な DLP クエリは、SensitiveType、count range、および confidence range の 3 つの部分で構成されています。 次の図に示す場合 **、SensitiveType:" \<type\> は** 必須であり、両方 **|\<count range\>** とも **|\<confidence range\>** 省略可能です。

![必須と省略可能に分割されたクエリの例。](../media/DLP-query-example-text.png)

### <a name="sensitive-type---required"></a>機密情報の種類: 必須

では、各部分はどのようなものですか。 SharePointDLP クエリは、通常、機密情報の種類インベントリのプロパティと情報の種類の名前で始まり、で `SensitiveType:"` 終わり[](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) `"` です。 また、組織用に [作成したカスタム](create-a-custom-sensitive-information-type.md) 機密情報の種類の名前を使用することもできます。 たとえば、クレジット カード番号が含まれているドキュメントを検索するとします。 このようなインスタンスでは、次の形式を使用します  `SensitiveType:"Credit Card Number"` 。 カウント範囲または信頼範囲を含めなかったため、クエリはクレジット カード番号が検出されたすべてのドキュメントを返します。 これは実行できる最も簡単なクエリであり、最も多くの結果を返します。 機密情報の種類のスペルと文字間隔は正確に入力する必要があります。

### <a name="ranges---optional"></a>範囲: 省略可能

次の 2 つの部分はどちらも範囲なので、範囲の外観をすばやく確認します。 DLP SharePointでは、基本的な範囲は 2 つのピリオドで区切られた 2 つの数値で表されます。これは次のように表示されます `[number]..[number]` 。 たとえば、使用する  `10..20` 場合、その範囲は 10 ~ 20 の数値を取得します。 このトピックでは、さまざまな範囲の組み合わせといくつかの組み合わせについて説明します。

クエリにカウント範囲を追加します。 カウント範囲を使用して、クエリ結果に含める前にドキュメントに含める必要がある機密情報の発生回数を定義できます。 たとえば、正確に 5 つのクレジット カード番号を含むドキュメントのみをクエリで返す場合は、次の値を使用します  `SensitiveType:"Credit Card Number|5"` 。 カウント範囲は、リスクが高いドキュメントを識別するのにも役立ちます。 たとえば、組織では、5 つ以上のクレジット カード番号を持つドキュメントがリスクが高いと考える場合があります。 この条件に適合するドキュメントを見つけるには、次のクエリを使用します  `SensitiveType:"Credit Card Number|5.."` 。 または、次のクエリを使用して、クレジット カード番号が 5 つ以下のドキュメントを検索することもできます  `SensitiveType:"Credit Card Number|..5"` 。

#### <a name="confidence-range"></a>信頼範囲

最後に、信頼範囲は、検出された機密性の高い型が実際には一致する信頼度です。 信頼範囲の値は、カウント範囲と同様に機能します。 カウント範囲を含めずにクエリを形成できます。 たとえば、任意の数のクレジット カード番号を持つドキュメントを検索するには、信頼範囲が 85% 以上である限り、次のクエリを使用します  `SensitiveType:"Credit Card Number|*|85.."` 。

> [!IMPORTANT]
> アスタリスク ( `*` ) は、任意の値が機能するワイルドカード文字です。 ワイルドカード文字 ( ) は、カウント範囲または信頼範囲内で使用できますが、機密性の高い `*` 型では使用できません。

### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>電子情報開示センターで使用できるその他のクエリ プロパティと検索演算子

また、SharePoint DLP では LastSensitiveContentScan プロパティも導入され、特定の時間枠内でスキャンされたファイルを検索するのに役立ちます。 プロパティのクエリ例については、次のセクションの「複雑なクエリの例 `LastSensitiveContentScan` 」を参照してください。 [](#examples-of-complex-queries)

DLP 固有のプロパティを使用してクエリを作成することもできますが、電子情報開示検索SharePointなどの標準のプロパティを作成 `Author` することもできます `FileExtension` 。 演算子を使用して、複雑なクエリを作成できます。 使用可能なプロパティと演算子の一覧については [、「Using Search Properties and Operators with eDiscovery blog post」を](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery) 参照してください。

## <a name="examples-of-complex-queries"></a>例

次の例では、さまざまな機密性の高い型、プロパティ、演算子を使用して、クエリを絞り込み、探している情報を正確に見つける方法を説明します。

<br>

****

|クエリ|説明|
|---|---|
|`SensitiveType:"International Banking Account Number (IBAN)"`|名前は長いので奇妙に見えるかもしれませんが、その機密性の高い型の正しい名前です。 機密情報の種類のインベントリから正確な名前 [を使用してください](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)。 また、組織用に [作成したカスタム](create-a-custom-sensitive-information-type.md) 機密情報の種類の名前を使用することもできます。|
|`SensitiveType:"Credit Card Number|1..4294967295|1..100"`|これにより、機密性の高い種類の "クレジット カード番号" に少なくとも 1 つ一致するドキュメントが返されます。 各範囲の値は、それぞれの最小値と最大値です。 このクエリを記述するより簡単な方法  `SensitiveType:"Credit Card Number"` は、ですが、その中で楽しいのはどこですか?|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"`|これにより、2018 年 8 月 11 日から 2018 年 8 月 13 日までスキャンされた 5 ~ 25 のクレジット カード番号を含むドキュメントが返されます。|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX`|これにより、2018 年 8 月 11 日から 2018 年 8 月 13 日までスキャンされた 5 ~ 25 のクレジット カード番号を含むドキュメントが返されます。 XLSX 拡張子を持つファイルは、クエリ結果には含まれません。  `FileExtension` は、クエリに含め得る多くのプロパティの 1 つです。 詳細については、「検索プロパティと [演算子を電子情報開示で使用する」を参照してください](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery)。|
|`SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"`|クレジット カード番号または社会保障番号が含まれているドキュメントを返します。|
|

## <a name="examples-of-queries-to-avoid"></a>例

すべてのクエリが平等に作成されているわけではありません。 次の表に、DLP で動作しないクエリの例を示し、そのSharePoint説明します。

<br>

****

|サポートされていないクエリ|理由|
|---|---|
|`SensitiveType:"Credit Card Number|.."`|少なくとも 1 つの値を追加する必要があります。|
|`SensitiveType:"NotARule"`|"NotARule" は、有効な機密性の高い型名ではありません。 機密情報の種類の [名前だけが DLP クエリ](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) で機能します。|
|`SensitiveType:"Credit Card Number|0"`|0 は、範囲内の最小値または最大値として無効です。|
|`SensitiveType:"Credit Card Number"`|見にくい場合がありますが、"Credit" と "Card" の間には余分な空白が含まれているので、クエリが無効になります。 機密情報の種類のインベントリから厳密に機密性 [の高い型名を使用します](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)。|
|`SensitiveType:"Credit Card Number|1. .3"`|2 つの期間の部分は、スペースで区切る必要があります。|
|`SensitiveType:"Credit Card Number| |1..|80.."`|パイプ区切り記号 () が多すぎます \| 。 代わりに、次の形式に従います。 `SensitiveType: "Credit Card Number|1..|80.."`|
|`SensitiveType:"Credit Card Number|1..|80..101"`|信頼度の値はパーセンテージを表すので、100 を超えかねない。 1 ～ 100 の数値を選択してください。|
|

## <a name="for-more-information"></a>詳細情報

- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
- [コンテンツ検索を実行する](content-search.md)
- [コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)
