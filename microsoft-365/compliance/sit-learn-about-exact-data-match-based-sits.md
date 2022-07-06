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
description: 正確なデータ一致ベースの機密情報の種類について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5d4a45e7ecdb143187b9d90fdedbaf1f235c7d52
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66621999"
---
# <a name="learn-about-exact-data-match-based-sensitive-information-types"></a>完全なデータ一致に基づく機密情報の種類の詳細

[機密情報の種類](sensitive-information-type-learn-about.md) は、機密情報の種類を使用して、機密情報が誤ってまたは不適切に共有されないようにしたり、電子情報開示で関連するデータを特定したり、特定の種類の情報にガバナンス アクションを適用したりするのに役立ちます。 次に基づいて、カスタムの機密情報の種類 (SIT) を定義します。

- パターン
- *従業員*、*社会保障番号*、*ID* などのキーワード証拠
- 特定のパターンの証拠に対する文字の近接性
- 信頼度レベル

ただし、汎用パターンに基づいて一致するものではなく、正確またはほぼ正確なデータ値を使用するカスタムの機密情報型 (SIT) が必要な場合はどうでしょうか。 完全一致 (EDM) ベースの分類を使用すると、次のように設計されたカスタムの機密情報の種類を作成できます。

- 動的に、簡単に更新する
- 拡張性の高いものにする
- 結果的に誤検知の数を減らす
- 構造化された機密データを操作する
- Microsoft を含む他のユーザーと共有せず、機密情報をより安全に処理する
- さまざまな Microsoft クラウド サービスで使用する

![EDM ベースの分類。](../media/EDMClassification.png)

EDM ベースの分類を使用すると、機密情報のデータベース内の正確な値を参照する、カスタムの機密情報の種類を作成できます。 データベースは毎日更新できます。また、最大 1 億行のデータを格納できます。 そのため、従業員、患者、または顧客の出入りに合わせて記録が変更されても、カスタムの機密情報の種類は最新の状態が維持されます。 また、[Microsoft Purview データ損失防止](dlp-learn-about-dlp.md)ポリシーや[Microsoft Cloud App Security ファイル](/cloud-app-security/data-protection-policies) ポリシーなどのポリシーで EDM ベースの分類を使用できます。

> [!NOTE]
> Microsoft Purview 情報保護では、次の 2 バイト文字セット言語がサポートされています。
>
> - 中国語 (簡体字)
> - 中国語 (繁体字)
> - 韓国語
> - 日本語
>
> このサポートは、機密情報の種類で使用できます。 詳細については、「[2バイト文字セットのリリースノート (preview) についての情報保護サポー](mip-dbcs-relnotes.md)」を参照してください。

## <a name="whats-different-in-an-edm-sit"></a>EDM SIT の違い

EDM SIT を使用する場合は、それらに固有のいくつかの概念を理解しておくと便利です。  

### <a name="schema"></a>Schema

スキーマは、次を定義する xml ファイルです。

- 後で *DataStore* と呼ばれるスキーマの名前。 
- 機密情報ソース テーブルに含まれるフィールド名。 スキーマ フィールド名と機密情報ソース テーブル列名の 1 対 1 のマッピングがあります。
- 検索可能なフィールド。
- 構成 *可能な一致* と呼ばれる検索変更パラメーター 。たとえば、区切り記号の無視や、検索された値の大文字と小文字の区別などです。

### <a name="sensitive-information-source-table"></a>機密情報ソース テーブル

機密ソース テーブルには、EDM SIT が検索する機密情報の値が含まれています。 これは、列と行で構成されます。 列ヘッダーはフィールド名で、行はデータのインスタンスであり、各セルにはそのフィールドのインスタンスの値が含まれます。

機密情報ソース テーブルの簡単な例を次に示します。

|名|姓|Date of Birth|
|---|---|---|
|イザヤ|ランガー| 05-05-1960|
|Ana|ボウマン|11-24-1971|
|オスカー|区|02-12-1998|

### <a name="rule-package"></a>ルール パッケージ

すべての SIT にはルール パッケージがあります。 EDM SIT でルール パッケージを使用して、次を定義します。

- 一致します。これは、完全な参照で使用される主な要素となるフィールドを指定します。 これは、チェックサム検証、キーワード リスト、キーワード ディクショナリ、または関数の有無にかかわらず正規表現を使用できます。
- 分類。これは、EDM ルックアップをトリガーする機密型の一致を指定します。
- 検出された要素であるサポート要素は、一致の信頼度を高めるのに役立つサポート証拠を提供します。 たとえば、SSN 番号の近くにあるキーワード "SSN" などです。 チェックサム検証、キーワード リスト、キーワード ディクショナリの有無にかかわらず、正規表現を使用できます。
- 信頼度レベル (高、中、低) は、主要な要素と共に検出されたサポート証拠の量を反映します。 アイテムに含まれるサポート証拠が多いほど、一致するアイテムに探している機密情報が含まれるという信頼度が高くなります。 信頼度レベルの詳細については、 [機密情報の種類の基本部分](sensitive-information-type-learn-about.md#fundamental-parts-of-a-sensitive-information-type) を参照してください。
近接 - プライマリ要素とサポート要素の間の文字数

### <a name="you-supply-your-own-schema-and-data"></a>独自のスキーマとデータを指定します

Microsoft Purview には、定義済みのスキーマ、正規表現パターン、キーワード、信頼レベルを備えた [200 を超える SITS](sensitive-information-type-entity-definitions.md) が付属しています。 EDM SIT を使用すると、機密項目を識別するプライマリ フィールドとセカンダリ フィールドだけでなく、スキーマを定義する必要があります。 スキーマとプライマリとセカンダリのデータ値は非常に機密性が高いため、ランダムに生成されたまたは自己提供の [salt](https://en.wikipedia.org/wiki/Salt_(cryptography)#:~:text=The%20salt%20value%20is%20generated%20at%20random%20and,the%20salt%20value%20and%20hashed%20value%20are%20stored.) 値を含む[ハッシュ](/dotnet/standard/security/ensuring-data-integrity-with-hash-codes)関数を使用して暗号化します。 その後、これらのハッシュされた値がサービスにアップロードされるため、機密データが開かれることはありません。

### <a name="primary-and-secondary-support-elements"></a>プライマリとセカンダリのサポート要素

EDM SIT を作成するときは、ルール パッケージに *プライマリ要素* フィールドを定義します。 プライマリ フィールドは、すべてのコンテンツを検索する要素であり、識別するために定義されたパターンに従う必要があります。 スキャンされた項目でプライマリ要素が見つかると、EDM は、パターンに従う必要のない *セカンダリ* 要素またはサポート要素、およびプライマリ要素への近接性を探します。 EDM では、プライマリ要素が既存の SIT を介して最初に検出可能であることが必要です。 使用可能な SIT の完全な一覧については、 [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md) を参照してください。 EDM SIT で検出するクラスを検出するもののいずれかを見つける必要があります。 たとえば、EDM SIT スキーマに主な要素として米国の社会保障番号がある場合、EDM スキーマを作成するときに、それを [米国社会保障番号 (SSN)](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn) SIT に関連付けたとします。

## <a name="how-matching-works"></a>照合のしくみ

EDM は、定義した機密データのテーブルと見なされるコンテンツを比較することで、一致を検索します。 一致テストは、従来のルールとパターンの組み合わせを使用して行われ、一致するデータが検索および保護するデータの実際のインスタンスであることを確認します。 その中核となる EDM は、ドキュメント内の文字列と電子メールを機密データのテーブル内の値と比較することで機能し、コンテンツ内の値が一方向の暗号化ハッシュを比較してテーブルに存在するかどうかを調べます。

> [!TIP]
> 一般的な方法は、EDM 機密情報の種類の使用と、DLP ルールに基づく通常の機密情報の種類と、異なるしきい値を組み合わせることです。 たとえば、社会保障番号やその他のデータを検索する EDM 機密情報の種類を使用できます。厳しい要件と、1 つ以上の一致によって DLP アラートが発生する許容度が低く、米国社会保障番号の組み込みのように通常の機密情報の種類を使用して、より多くのカウントを実現できます。  

## <a name="services-that-edm-supports"></a>EDM がサポートするサービス


|サービス  |場所  |
|---------|---------|
| Microsoft Purview データ損失防止    | - SharePoint Online </br>- OneDrive for Business </br>- Teams チャット </br>- Exchange Online </br>- デバイス       |
|Microsoft Defender for Cloud Apps     | - SharePoint Online </br>- OneDrive for Business        |
|自動ラベル付け (サービス側)     |- SharePoint Online </br>- OneDrive for Business </br>- Exchange Online         |
|自動ラベル付け (クライアント側)     |- Word </br>- Excel </br>- PowerPoint </br>- Exchange デスクトップ クライアント         |
|カスタマー マネージド キー     |- SharePoint Online </br>- OneDrive for Business </br>- Teams チャット </br>- Exchange Online </br>- Word </br>- Excel </br>- PowerPoint </br>- Exchange デスクトップ クライアント </br>- デバイス         |
|電子情報開示     |- SharePoint Online </br>- OneDrive for Business </br>- Teams チャット </br>- Exchange Online </br>- Word </br>- Excel </br>- PowerPoint </br>- Exchange デスクトップ クライアント  |
|インサイダー リスクの管理     |- SharePoint Online </br>- OneDrive for Business </br>- Teams チャット </br>- Exchange Online </br>- Word </br>- Excel </br>- PowerPoint </br>- Exchange デスクトップ クライアント      |

## <a name="see-also"></a>関連項目

- [完全なデータ一致に基づく機密情報の種類の使用を開始する](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)
