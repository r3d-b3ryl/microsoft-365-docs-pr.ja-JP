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
description: 正確なデータ一致ベースの機密情報の種類に対してソース データをエクスポートする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 913870afeef443c5b346172099b0cd47db13e52e
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760693"
---
# <a name="export-source-data-for-exact-data-match-based-sensitive-information-type"></a>完全なデータ一致に基づく機密情報の種類のソース データをエクスポートする


機密データ テーブルは、機密データを識別するためにドキュメント内のコンテンツを比較する値の行を含むテキスト ファイルです。 これらの値は、コンテンツで検出して保護アクションを実行するテキスト形式の個人識別可能な情報、製品レコード、またはその他の機密データである可能性があります。

サポートされている形式のいずれかでデータがエクスポートされたら、EDM スキーマの作成を続行できます。

## <a name="defining-your-edm-sensitive-type"></a>EDM 機密型の定義

EDM 機密型を定義する場合、最も重要な決定事項の 1 つは、どのフィールドがプライマリ フィールドになるかです。 プライマリ フィールドは、検出可能なパターンに従い、EDM スキーマで検索可能なフィールド (列) として定義する必要があります。 セカンダリ フィールドは、一致を囲むすべてのテキストとプライマリ フィールドと比較されるため、パターンに従う必要はありません。

次のルールを使用して、プライマリ フィールドとして使用する列を決定するのに役立ちます。

- 機密データ テーブル内のフィールドに一致する 1 つの値の存在に基づいて機密データを検出する必要がある場合は、それを囲む他の機密データの存在に関係なく、その列を EDM 型のプライマリ要素として定義する必要があります。 
- 機密データ テーブル内の異なるフィールドの複数の組み合わせをコンテンツで検出する必要がある場合は、そのようなほとんどの組み合わせに共通する列を特定し、それらをプライマリ要素として指定し、他のフィールドの組み合わせをセカンダリ要素として指定します。
- プライマリ フィールドとして使用する列が、テキスト文字列などの検出可能なパターンに従わない場合や、ドキュメントや電子メールの大部分に存在する検出可能なパターンに従う場合は、その他の構造化列を主な要素として選択してみてください。

たとえば、最初`full name``date of birth``account number`と`Social Security Number`最後の名前が検出したいさまざまなデータの組み合わせに共通する列であっても、列 、を持っている場合、そのような文字列は簡単に識別可能なパターンに従わないので、機密情報の種類として定義するのが困難な場合があります。 これは、一部の名前は大文字で始まることさえなく、2 つ、3 つ以上の単語で形成される可能性があり、数字やその他のアルファベット以外の文字を含む場合があるためです。 生年月日をより簡単に識別できますが、すべての電子メールとほとんどのドキュメントには少なくとも 1 つの日付が含まれるため、適切な候補でもあります。 社会保障番号とアカウント番号は、プライマリ フィールドとして使用するための適切な候補です。

## <a name="save-sensitive-data-in-csv-tsv-or-pipe-separated-format"></a>機密データを.csv、.tsv、またはパイプ区切り形式で保存する

1. 使用する機密情報を特定します。 Microsoft Excelなどのアプリにデータをエクスポートし、ファイルをテキスト ファイルに保存します。 ファイルは、.csv (コンマ区切り値)、.tsv (タブ区切り値)、またはパイプ区切り (|) 形式で保存できます。 .tsv 形式は、データ値に住所などのコンマが含まれる場合に推奨されます。
データ ファイルには、次のデータを含めることができます。
   - 最大 1 億行の機密データ
   - データ ソースごとに最大 32 列 (フィールド)
   - 検索可能としてマークされた列 (フィールド) を最大 5 列

2. 最初の行に EDM ベースの分類に使用されるフィールドの名前を含め、.csv ファイルまたは .tsv ファイル内の機密データを構造化します。 ファイルには、"ssn"、"birthdate"、"firstname"、"lastname" などのフィールド名が含まれる場合があります。 列見出しの名前にスペースやアンダースコアを含めることはできません。 たとえば、この記事で使用するサンプルの .csv ファイルは *PatientRecords.csv* と呼ばれており、その列には *PatientID*、*MRN*、*LastName*、*FirstName*、*SSN* などが含まれています。

3. 機密データ フィールドの形式に注意してください。 特に、コンテンツにコンマを含むフィールド (たとえば、値 "Seattle,WA" を含む住所) は、.csv形式が選択されている場合、解析時に 2 つの別々のフィールドとして解析されます。 これを回避するには、.tsv 形式を使用するか、機密データ テーブルで値を含むコンマを二重引用符で囲みます。 値を含むコンマにスペースも含まれている場合は、対応する形式に一致するカスタム SIT を作成する必要があります。 たとえば、コンマとスペースを含む複数語の文字列を検出する SIT などです。

## <a name="next-step"></a>次のステップ

- [完全なデータ一致に基づく機密情報の種類のスキーマを作成する](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)

## <a name="see-also"></a>関連項目

- [完全なデータ一致に基づく機密情報の種類の使用を開始する](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)
- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
