---
title: 完全なデータ一致に基づく機密情報の種類のソース データをエクスポートする
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 完全なデータ一致に基づく機密情報の種類のソース データをエクスポートする方法について学習します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9a1ee56708018ddfddf141499bf4cf5f9ee02449
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526264"
---
# <a name="export-source-data-for-exact-data-match-based-sensitive-information-type"></a>完全なデータ一致に基づく機密情報の種類のソース データをエクスポートする


機密データ テーブルは、ドキュメント内のコンテンツを比較して機密データを識別する値の行を含むテキスト ファイルです。 これらの値は、個人を特定できる情報、製品レコード、またはコンテンツで検出し、保護アクションを実行するテキスト形式のその他の機密データである可能性があります。

サポートされている形式でデータをエクスポートしたら、EDM スキーマの作成を続行できます。

## <a name="defining-your-edm-sensitive-type"></a>EDM の機密性の高い型の定義

EDM の機密性の高い型を定義する場合、最も重要な決定の 1 つは、プライマリ フィールドになるフィールドです。 プライマリ フィールドは、検出可能なパターンに従い、EDM スキーマで検索可能なフィールド (列) として定義する必要があります。 セカンダリ フィールドは、プライマリ フィールドに一致するすべてのテキストと比較されますので、パターンに従う必要があります。

プライマリ フィールドとして使用する列を決定するには、次のルールを使用します。

- 機密データ テーブル内のフィールドに一致する 1 つの値に基づいて機密データを検出する必要がある場合は、そのデータを取り巻く他の機密データが存在する場合に関係なく、その列を EDM 型のプライマリ要素として定義する必要があります。 
- 機密データ テーブル内の異なるフィールドの複数の組み合わせをコンテンツで検出する必要がある場合は、そのようなほとんどの組み合わせに共通する列を特定し、他のフィールドの主要な要素と組み合わせをセカンダリ要素として指定します。
- プライマリ フィールドとして使用する列が、テキスト文字列などの検出可能なパターンに従えない場合や、ドキュメントや電子メールの大部分のどこかに存在する検出可能なパターンに従う場合は、他のより良い構造化された列をプライマリ要素として選択してみてください。

`full name``Social Security Number``account number``date of birth`たとえば、列 、を持っている場合、最初と最後の名前は、検出するデータの異なる組み合わせに共通する列である場合でも、このような文字列は簡単に識別できるパターンに従うので、機密情報の種類として定義するのが難しい場合があります。 これは、一部の名前が大文字で始まる可能性もないので、2 つ、3 つ以上の単語で形成され、数字や他のアルファベット以外の文字を含む場合があります。 生年月日を簡単に識別できますが、すべての電子メールとほとんどのドキュメントに少なくとも 1 つの日付が含まれるので、それも良い候補ではありません。 社会保障番号とアカウント番号は、プライマリ フィールドとして使用する優れた候補です。

## <a name="save-sensitive-data-in-csv-tsv-or-pipe-separated-format"></a>機密データを .csv.tsv、またはパイプ区切り形式で保存する

1. 使用する機密情報を特定します。 データをアプリにエクスポートし、Microsoft Excelファイルに保存します。 ファイルは、.csv (コンマ区切り値)、.tsv (タブ区切り値)、またはパイプ区切り (|) 形式で保存できます。 データ値に住所などのコンマが含まれている場合は、.tsv 形式をお勧めします。
データ ファイルには、次のデータを含めることができます。
   - 最大 1 億行の機密データ
   - データ ソースごとに最大 32 列 (フィールド)
   - 検索可能としてマークされた列 (フィールド) を最大 5 列

2. EDM ベースの分類に使用されるフィールドの名前が最初の行に含まれる.csvまたは .tsv ファイル内の機密データを構造化します。 ファイルには、"ssn"、"birthdate"、"firstname"、"lastname" などのフィールド名が含まれ得ます。 列見出しの名前にスペースやアンダースコアを含めることはできません。 たとえば、この記事で使用するサンプルの .csv ファイルは *PatientRecords.csv* と呼ばれており、その列には *PatientID*、*MRN*、*LastName*、*FirstName*、*SSN* などが含まれています。

3. 機密データ フィールドの形式に注意してください。 特に、コンテンツにコンマを含む可能性があるフィールド (たとえば、値 "Seattle,WA" を含む住所) は、.csv 形式が選択されている場合に解析すると、2 つの別個のフィールドとして解析されます。 この問題を回避するには、.tsv 形式を使用するか、機密データ テーブルの値を二重引用符で囲むコンマを囲む必要があります。 コンマを含む値にスペースも含まれている場合は、対応する形式に一致するカスタム SIT を作成する必要があります。 たとえば、コンマとスペースを含む複数単語文字列を検出する SIT。

## <a name="next-step"></a>次のステップ

- [完全なデータ一致に基づく機密情報の種類のスキーマを作成する](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)

## <a name="see-also"></a>関連項目

- [完全なデータ一致に基づく機密情報の種類の使用を開始する](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)
- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
