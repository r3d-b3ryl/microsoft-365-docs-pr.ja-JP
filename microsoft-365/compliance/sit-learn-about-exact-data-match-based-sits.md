---
title: 完全なデータ一致に基づく機密情報の種類の詳細
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 正確なデータ一致に基づく機密情報の種類について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 21e6f3c12d7c401562a1ee1915e1e1c266724b1b
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526922"
---
# <a name="learn-about-exact-data-match-based-sensitive-information-types"></a>完全なデータ一致に基づく機密情報の種類の詳細

[機密情報](sensitive-information-type-learn-about.md) の種類は、機密性の高いアイテムが誤って共有または不適切に共有されるのを防ぐため、電子情報開示で関連するデータを検索したり、特定の種類の情報にガバナンス アクションを適用したりするために使用されます。 次に基づいて、カスタムの機密情報の種類 (SIT) を定義します。

- パターン
- 従業員、社会保障 *番号、* ID などのキーワード *証拠*
- 特定のパターンの証拠に対する文字の近接性
- 信頼度レベル

しかし、一般的なパターンに基づいて一致が見つかったデータ値ではなく、正確またはほぼ正確なデータ値を使用するカスタム機密情報の種類 (SIT) が必要な場合は、どうしますか? 完全データ一致 (EDM) ベースの分類を使用すると、次の目的で設計されたカスタム機密情報の種類を作成できます。

- 動的に、簡単に更新する
- 拡張性の高いものにする
- 結果的に誤検知の数を減らす
- 構造化された機密データを操作する
- Microsoft を含むすべてのユーザーと機密情報を共有しない、より安全に機密情報を処理する
- さまざまな Microsoft クラウド サービスで使用する

![EDM ベースの分類。](../media/EDMClassification.png)

EDM ベースの分類を使用すると、機密情報のデータベース内の正確な値を参照する、カスタムの機密情報の種類を作成できます。 データベースは毎日更新できます。また、最大 1 億行のデータを格納できます。 そのため、従業員、患者、または顧客の出入りに合わせて記録が変更されても、カスタムの機密情報の種類は最新の状態が維持されます。 また、EDM ベースの分類は、[データ損失防止ポリシー](dlp-learn-about-dlp.md)や [Microsoft Cloud App Security ファイル ポリシー](/cloud-app-security/data-protection-policies) などのポリシーと共に使用できます。

> [!NOTE]
> Microsoft 365 Information Protection は、次のような場合に 2 バイト文字セットの言語をサポートします。
>
> - 中国語 (簡体字)
> - 中国語 (繁体字)
> - 韓国語
> - 日本語
>
> このサポートは、機密情報の種類で使用できます。 詳細については、「[2バイト文字セットのリリースノート (preview) についての情報保護サポー](mip-dbcs-relnotes.md)」を参照してください。

## <a name="whats-different-in-an-edm-sit"></a>EDM SIT の違い

EDM SIT を使用する場合は、独自の概念を理解すると便利です。  

### <a name="schema"></a>Schema

スキーマは、次を定義する xml ファイルです。

- 後で *DataStore* と呼ばれるスキーマの名前。 
- 機密情報ソース テーブルに含まれるフィールド名。 スキーマ フィールド名と機密情報ソース テーブル列名のマッピングは 1:1 です。
- 検索可能なフィールド。
- 区切り記号や検索値の大文字と小文字を無視するなど、構成可能な一致と呼ばれる検索変更パラメーター。

### <a name="sensitive-information-source-table"></a>機密情報のソース テーブル

機密性の高いソース テーブルには、EDM SIT が探す機密情報の値が含まれます。 列と行ででなされます。 列ヘッダーはフィールド名、行はデータのインスタンスであり、各セルにはそのフィールドのそのインスタンスの値が含まれます。

機密情報ソース テーブルの簡単な例を次に示します。

|名  |姓  |Date of Birth  |
|---------|---------|---------|
|Isaiah   |Langer  | 05-05-1960 |
|Ana   |Bowman         |11-24-1971 |
|Oscar   |ワード         |02-12-1998 |


### <a name="rule-package"></a>ルール パッケージ

すべての SIT にはルール パッケージがあります。 EDM SIT のルール パッケージを使用して、次の定義を行います。

- 完全な参照で使用する主な要素になるフィールドを指定する一致。 チェックサムの検証、キーワード リスト、キーワード 辞書、または関数を含む正規表現を指定できます。
- 分類:EDM 参照をトリガーする機密の種類の一致を指定します。
- 検出された要素であるサポート要素は、一致の信頼性を高めるのに役立つ証拠を提供します。 たとえば、SSN 番号の近接にあるキーワード "SSN" です。 これは、チェックサム検証、キーワード リスト、キーワード 辞書の付いた正規表現と指定できます。
- 信頼度 (高、中、低) は、主要素と共に検出された証拠の量を反映します。 アイテムに含まれる証拠が多いほど、一致するアイテムに探している機密情報が含まれているという信頼性が高くなります。 信頼度 [の詳細については、「](sensitive-information-type-learn-about.md#fundamental-parts-of-a-sensitive-information-type) 機密情報の種類の基本的な部分」を参照してください。
近接 – プライマリ要素とサポート要素の間の文字数

### <a name="you-supply-your-own-schema-and-data"></a>独自のスキーマとデータを指定する

[Microsoft 365 200](sensitive-information-type-entity-definitions.md) を超える SITS と、定義済みのスキーマ、正規表現パターン、キーワード、信頼度が付属しています。 EDM の EDM の場合は、スキーマと、機密性の高いアイテムを識別するプライマリ フィールドとセカンダリ フィールドを定義します。 スキーマとプライマリ データ値とセカンダリ データ値は非常に機密性が高いので、ランダムに生成または自己提供された[](/dotnet/standard/security/ensuring-data-integrity-with-hash-codes)ソルト値を含むハッシュ関数を使用して[暗号化します。](https://en.wikipedia.org/wiki/Salt_(cryptography)#:~:text=The%20salt%20value%20is%20generated%20at%20random%20and,the%20salt%20value%20and%20hashed%20value%20are%20stored.) その後、これらのハッシュ値がサービスにアップロードされ、機密データが開かれません。

### <a name="primary-and-secondary-support-elements"></a>プライマリおよびセカンダリ のサポート要素

EDM SIT を作成する場合は、ルール パッケージ *でプライマリ要素* フィールドを定義します。 プライマリ フィールドは、すべてのコンテンツを検索する要素であり、特定するために定義されたパターンに従う必要があります。 スキャンされたアイテムでプライマリ要素が見つかった場合、EDM は、パターンに従う必要はないセカンダリ要素またはサポート要素、およびプライマリ要素への近接性を探します。 EDM では、プライマリ要素を最初に既存の SIT を介して検出可能である必要があります。 使用可能な [SIT の完全な一覧](sensitive-information-type-entity-definitions.md) については、「機密情報の種類エンティティ定義」を参照してください。 EDM SIT で検出するクラスを検出するクラスのいずれかを見つける必要があります。 たとえば、EDM SIT スキーマに主な要素として米国の社会保障番号がある場合、EDM スキーマを作成するときに、その番号を米国社会保障番号 [(SSN)](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn) SIT に関連付けることができます。


## <a name="how-matching-works"></a>マッチングのしくみ

EDM は、見つけたコンテンツを、定義した機密データのテーブルと比較して一致を検索します。 一致テストは、従来のルールとパターンの組み合わせを使用して行われ、一致するデータが検索および保護するデータの実際のインスタンスである必要があります。 EDM は、ドキュメント内の文字列と電子メールを、提供する機密データのテーブル内の値と比較して、一方通行の暗号化ハッシュを比較して、コンテンツ内の値がテーブルに存在するのを確認することで機能します。

> [!TIP]
> 一般的な方法は、EDM 機密情報の種類の使用と、DLP ルールに基づく通常の機密情報の種類を、異なるしきい値と組み合わせることです。 たとえば、社会保障番号や他のデータを検索する EDM 機密情報の種類を使用し、厳しい要件と許容度が低く、1 つ以上の一致で DLP アラートが発生する場合は、通常の機密情報の種類 (米国の社会保障番号組み込みなど) を使用すると、より高い数を得る必要があります。  

## <a name="see-also"></a>関連項目

- [完全なデータ一致に基づく機密情報の種類の使用を開始する](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)
   
