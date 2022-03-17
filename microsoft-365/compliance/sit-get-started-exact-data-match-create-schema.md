---
title: 完全なデータ一致に基づく機密情報の種類のスキーマを作成する
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
description: 完全なデータ一致に基づく機密情報の種類のスキーマを作成する
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6bd411411c3075259bd3b9fc74ec3f558171fce7
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526292"
---
# <a name="create-the-schema-for-exact-data-match-based-sensitive-information-types"></a>完全なデータ一致に基づく機密情報の種類のスキーマを作成する

スキーマと EDM SIT を作成するには、[完全なデータ一致スキーマと機密情報の種類パターンを使用する] ウィザードを使用するか、手動で[実行](#use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard)[します](#create-exact-data-match-schema-manually-and-upload)。 1 つのメソッドを使用してスキーマを作成し、後でもう一方のメソッドを使用して編集することで、両方を組み合わせすることもできます。

EDM ベースの SITS またはそれらの実装に精通していない場合は、次の情報を理解する必要があります。

- [機密情報の種類に関する詳細情報](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [完全なデータ一致に基づく機密情報の種類の使用を開始する](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)

1 つの EDM スキーマは、同じ機密データ テーブルを使用する複数の機密情報の種類で使用できます。 1 つのテナントに最大 10 の異なる EDM スキーマMicrosoft 365できます。

## <a name="working-with-specific-types-of-data"></a>特定の種類のデータを操作する

パフォーマンス上の理由から、不要な一致の数を最小限に抑えるパターンを使用する必要があります。 たとえば、正規表現に基づいて機密情報の種類を使用できます。

`\b\w*\b`

これは、ドキュメントまたは電子メール内のすべての個々の単語または番号と一致します。 これにより、サービスに一致がオーバーロードされ、true の一致が検出されない場合があります。 より正確なパターンを使用すると、この状況を回避できます。 一般的な種類のデータに対して適切な構成を特定するための推奨事項を次に示します。

**電子メール アドレス**: 電子メール アドレスは簡単に識別できますが、コンテンツで非常に一般的なので、プライマリ フィールドとして使用すると、システムに大きな負荷が発生する可能性があります。 二次証拠としてのみ使用してください。 `From` `To`主な証拠として使用する必要がある場合は、ロジックを使用して電子メールの使用またはフィールドを除外するカスタム機密情報の種類を定義し、一致する必要がある不要な文字列の数を減らすために、会社の電子メール アドレスを持つユーザーを除外します。

**電話** 番号: 電話は、国のプレフィックス、エリア コード、および区切り記号を含む、または除外するさまざまな形式で使用できます。 負荷を最小限に抑えながら偽の負を減らすには、セカンダリ要素としてのみ使用し、かっこやダッシュなどの可能性があるすべての区切り記号を除外し、常に電話番号に存在する部分のみを機密データ テーブルに含める必要があります。

**人物** の名前: 正規表現に基づく機密情報の種類をこの EDM 型の分類要素として使用する場合は、一般的な単語と区別するのが難しいため、ユーザーの名前を主な要素として使用しません。

処理する一致の多くを生成する可能性があるプロジェクト コード名など、特定のパターンで識別が難しいプライマリ要素を使用する必要がある場合は、EDM 型の分類要素として使用する機密情報の種類にキーワードを含める必要があります。 `project`たとえば、通常の単語である可能性があるプロジェクト コード名を使用する場合は、EDM 型の分類要素として使用される機密型のプロジェクト名正規表現ベースのパターンに近接して、必要な追加の証拠として単語を使用できます。 または、通常の辞書に基づく機密性の高い型を EDM SIT の分類要素として使用する場合があります。

数値の文字列を一致させようとする場合は、数字の数や開始数字など、許容される数値の範囲 (既知の場合) を指定します。 比較的柔軟な数値範囲に一致する必要がある場合は、基本の SIT でキーワードを使用して、一致する数を減らします。 たとえば、7 ~ 11 `account`桁の数字で構成されるアカウント番号を一致させようとする場合は、必要な追加の証拠として、SIT に 、`customer``acct.`という単語を追加します。 これにより、EDM によって処理される一致の制限を超える可能性がある不必要な一致の可能性が低下します。

プライマリ要素として使用する必要があるフィールドが、多数の一致を引き起こす可能性がある単純なパターンに従い、機密情報の種類に追加の証拠としてキーワードの存在を追加できない場合は、そのパターンの出現回数を最小限に抑える必要があります。 たとえば、次の方法で定義されたカスタムの機密情報の種類を使用して、EDM と一致する可能性のある 5 桁の番号を囲む少なくとも 29 の他の 5 桁の数字を検出できます。

```xml
 <Entity id="98703510-18b3-43d4-961f-15317594beb7"
                  patternsProximity="300"
                  recommendedConfidence="85"
                  relaxProximity="false">
                  <Pattern confidenceLevel="85"
                              proximity="300">
                              <IdMatch idRef="MRN"/>
                              <Match idRef="30 AccountNrs"
                                    minCount="30"
                                    proximity="3000"
                                    uniqueResults="true"/>
                  </Pattern>
      </Entity>
      <Regex id="30 AccountNrs">\d{5}</Regex>
```

場合によっては、一定のアカウントを特定したり、履歴上の理由で標準化されたパターンに従ってない識別番号を記録する必要がある場合があります。 たとえば、同 `Medical Record Numbers` じ組織内の文字と数字の多くの異なる変換で構成できます。 最初はパターンを特定するのは難しい場合でも、詳細な検査を行うと、無効な一致の数を多く発生させずに、すべての有効な値を記述するパターンを絞り込む場合があります。 たとえば、「すべての MRN は長さが 7 文字以上、数字が 2 桁以上で、文字が 1 文字で始まる」と検出される場合があります。 このような条件に基づいて正規表現を作成すると、必要なすべての値をキャプチャしながら不必要な一致を最小限に抑え、さらに分析を行って、異なる形式を記述する個別のパターンを定義することで精度を高める可能性があります。

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>完全一致スキーマと機密情報の種類ウィザードを使用する

このウィザードを使用すると、スキーマ ファイルの作成プロセスを簡略化できます。

## <a name="pre-requisites"></a>前提条件

- 「ソース データをエクスポート [する」の手順を実行して、厳密なデータ一致ベースの機密情報の種類を指定します](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)。

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>完全一致スキーマと機密情報の種類パターンウィザードを使用する

1. テナントのMicrosoft 365コンプライアンス センターで、**データ分類** > **Exact データと** > 一致 **するEDM スキーマに移動します**。

2. **EDM スキーマを作成** を選択して、スキーマ ウィザードの構成 ポップアップを開きます。

   ![EDM スキーマ作成ウィザード構成のフライアウト。](../media/edm-schema-wizard-1.png)

3. 適切な **名前** と **説明** を入力します。

4. スキーマ **全体に対してその動作を行** う場合は、[すべてのスキーマ フィールドの区切り記号と句読点を無視する] を選択します。 大文字と小文字または区切り記号を無視するように EDM を構成する方法の詳細については、「 [Using the caseInsensitive and ignoreDelimiters](#using-the-caseinsensitive-and-ignoreddelimiters-fields) fields」を参照してください。

5. **スキーマ フィールド#1** 必要な値を入力し、必要に応じてフィールドを追加します。 各スキーマ フィールドは、機密情報ソース ファイルの列ヘッダーと同一である必要があります。

6. 必要な場合は、次のフィールドごとの値を設定します。
    1. **フィールドが検索可能**
    1. **フィールドは大文字と小文字を区別しません**
    1. **このフィールドで無視する区切り記号と句読点を選択する**
    1. **このフィールドにカスタム区切り記号と句読点を入力する**

   > [!IMPORTANT]
   > 1 つ以上 5 つ以下のスキーマ フィールド を検索可能として指定する必要があります。

7. **[保存]** を選択します。 これでスキーマが一覧表示され、使用できます。

   > [!IMPORTANT]
   > スキーマを削除し、それが既に EDM の機密情報の種類に関連付けられている場合は、まずEDM の機密情報の種類を削除し、その後、スキーマを削除できます。 データ ストアが関連付けられているスキーマを削除すると、24 時間以内にデータ ストアも削除されます。

## <a name="export-of-the-edm-schema-file-in-xml-format"></a>XML 形式の EDM スキーマ ファイルのエクスポート

EDM スキーマ ウィザードで EDM スキーマを作成した場合は、EDM スキーマ ファイルを XML 形式でエクスポートする必要があります。 正確なデータ一致の機密情報の種類フェーズについては、ハッシュで機密情報ソース テーブルを [アップロードする必要](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types) があります。

1. [セキュリティ/コンプライアンス センターの PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)。

2. EDM スキーマ ファイルをエクスポートするには、次の構文を使用します。

   ```powershell
   $Schema = Get-DlpEdmSchema -Identity "[your EDM Schema name]"
   Set-Content -Path ".\Schemafile.xml" -Value $Schema.EdmSchemaXML
   ```

3. 後で使用するためにこのファイルを保存します。

## <a name="create-exact-data-match-schema-manually-and-upload"></a>完全なデータ一致スキーマを手動で作成し、アップロードする

スキーマ ファイルで、次の構文を使用して、機密情報ソース テーブルの各列のエントリを構成します。

```xml
<Field name="FieldName" searchable="true/false" caseInsensitive="true/false" ignoredDelimiters="delimiter characters" />
```

### <a name="using-the-caseinsensitive-and-ignoreddelimiters-fields"></a>caseInsensitive フィールドと ignoredDelimiters フィールドの使用

次のスキーマ XML サンプルでは、 *caseInsensitive フィールド* と *ignoredDelimiters フィールドを使用* します。

スキーマ定義の *値に設定された caseInsensitive* `true` フィールドを含める場合、EDM は大文字と小文字の違いに基づいてアイテムを除外しません。 たとえば、EDM では、 **フィールドの値 FOO-1234** と **fOo-1234** が同一と表示 `PatientID` されます。

*ignoreDelimiters フィールドに* サポートされている文字を含める場合、EDM はそれらの文字を無視します。 したがって、EDM は **FOO-1234** と **FOO#1234** の値がフィールドで同一と見な `PatienID` されます。

この例では、両方が使用されている場合、EDM は **FOO-1234** と **fOo#1234** を同一と見なし、アイテムを患者レコードの機密情報の種類として分類します。`caseInsensitive` `ignoredDelimiters`

これらの両方のパラメーターは、フィールド単位で使用されます。

> [!IMPORTANT]
> 空白を *無視する* 構成を行う場合、これはプライマリ フィールド列にのみ有効であり、複数単語の文字列を検出できる機密情報の種類が定義されます。 それ以外の場合は、分析対象のコンテンツ内の個々の単語に対して比較が行います。

*ignoredDelimiters フラグは*、英数字以外の文字をサポートします。次に例を示します。

- \.
- \-
- \/
- \_
- \*
- \^
- \#
- \!
- \?
- \[
- \]
- \{
- \}
- \\
- \~
- \;

`ignoredDelimiters`フラグは以下をサポートしていません:

- 0 から 9 の文字
- A から Z
- a から z
- \"
- \,

> [!IMPORTANT]
> EDM 機密情報の種類を定義する場合、 *ignoreDelimiters* は、EDM パターン内のプライマリ要素に関連付けられた分類機密情報の種類がアイテム内のコンテンツを識別する方法に影響しません。 したがって、検索可能なフィールドに *ignoreDelimiters* を構成する場合は、そのフィールドに基づいてプライマリ要素に使用される機密情報の種類が、それらの文字が存在する場合と存在しない文字列の両方を選択することを確認する必要があります。
>
> 機密情報ソース テーブル内の列数とスキーマ内のフィールドの数が一致する必要があります。順序は関係ありません。

1. スキーマを XML 形式で定義します (以下の例と同様)。 このスキーマ ファイル **に名前を** edm.xmlし、機密情報ソース テーブルの各列に、構文を使用する行が含まれる構成を行います。

      `\<Field name="" searchable=""/\>`.

      - *Field name* の値に列名を使用します。
      - 検索可能なフィールドと最大 5 つのフィールドまでのプライマリ フィールドには、 *searchable="true"* を使用します。 少なくとも 1 つのフィールドは検索可能である必要があります。

      たとえば、次の XML ファイルは患者レコードのデータベースのスキーマを定義します。検索可能として指定された 5 つのフィールドは、*PatientID*、*MRN*、*SSN*、*Phone*、*DOB* です。

      (この例は、コピー、変更、使用することができます。)

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
                  <Field name="MRN" searchable="true" />
                  <Field name="FirstName" />
                  <Field name="LastName" />
                  <Field name="SSN" searchable="true" />
                  <Field name="Phone" searchable="true" />
                  <Field name="DOB" searchable="true" />
                  <Field name="Gender" />
                  <Field name="Address" />
            </DataStore>
      </EdmSchema>
      ```

   EDM スキーマ ファイルを XML 形式で作成したら、クラウド サービスにアップロードする必要があります。

2. [セキュリティ/コンプライアンス センターの PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)。

3. データベース スキーマをアップロードするには、次のコマンドを実行します。

      ```powershell
      New-DlpEdmSchema -FileData ([System.IO.File]::ReadAllBytes('.\\edm.xml')) -Confirm:$true
      ```

      次のように、確認を求められます。

      > 確認
      >
      > この操作を実行しますか?
      >
      > データストア ' patientrecords ' の新しい EDM スキーマがインポートされます。
      >
      > \[Y\] Yes \[A\] すべて Yes \[N\] No \[L\] すべて No \[?\] ヘルプ (規定値は "Y"):

   > [!TIP]
   > 確認なしで変更を行う場合は `-Confirm:$true` 、手順 3 では使用しません。

> [!NOTE]
> 追加機能を使用して EDMSchema を更新するには、10 から 60 分かかることがあります。 追加機能を使用する手順を実行する前に、更新プログラムを完了する必要があります。

## <a name="next-step"></a>次のステップ

- [機密情報の種類と完全に一致する機密情報のソース テーブルをハッシュしてアップロードする](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)