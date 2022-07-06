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
ms.openlocfilehash: d5c2038dd7f3b4a6a96ad5e320e73254b21519f8
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66622021"
---
# <a name="create-the-schema-for-exact-data-match-based-sensitive-information-types"></a>完全なデータ一致に基づく機密情報の種類のスキーマを作成する

スキーマと EDM SIT は、 [厳密なデータ一致スキーマと機密情報の種類パターンを使用するウィザードを使用](#use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard) するか [、手動で](#create-exact-data-match-schema-manually-and-upload)作成できます。 1 つのメソッドを使用して両方を組み合わせてスキーマを作成し、後でもう一方のメソッドを使用して編集することもできます。

EDM ベースの SITS またはその実装に慣れていない場合は、次の点に慣れる必要があります。

- [機密情報の種類に関する詳細情報](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [完全なデータ一致に基づく機密情報の種類の使用を開始する](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)

1 つの EDM スキーマは、同じ機密データ テーブルを使用する複数の機密情報の種類で使用できます。 Microsoft 365 テナントでは、最大 10 個の異なる EDM スキーマを作成できます。



## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>完全一致スキーマと機密情報の種類ウィザードを使用する

このウィザードを使用すると、スキーマ ファイルの作成プロセスを簡略化できます。

## <a name="pre-requisites"></a>前提条件

- [完全一致ベースの機密情報の種類に対してソース データをエクスポートする](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)の手順を実行します。

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>完全一致スキーマと機密情報の種類パターンウィザードを使用する

1. テナントのMicrosoft Purview コンプライアンス ポータルで、[**データ分類** > ] の [**正確なデータと一致する** > **EDM スキーマ] に移動します**。

2. **EDM スキーマを作成** を選択して、スキーマ ウィザードの構成 ポップアップを開きます。

   ![EDM スキーマ作成ウィザードの構成ポップアップ。](../media/edm-schema-wizard-1.png)

3. 適切な **名前** と **説明** を入力します。

4. スキーマ全体に対してその動作が必要な場合は、 **すべてのスキーマ フィールドの区切り記号と句読点を無視** するを選択します。 大文字と小文字または区切り記号を無視するように EDM を構成する方法の詳細については、この機能の詳細については、「 [caseInsensitive フィールドと ignoreDelimiters フィールドの使用](#using-the-caseinsensitive-and-ignoreddelimiters-fields) 」を参照してください。

5. **スキーマ フィールド#1** 必要な値を入力し、必要に応じてフィールドを追加します。 各スキーマ フィールドは、機密情報ソース ファイル内の列ヘッダーと同じである必要があります。

6. 必要に応じて、フィールドごとの値を次のように設定します。
    1. **フィールドは検索可能です**
    1. **フィールドで大文字と小文字が区別されない**
    1. **区切り記号と句読点を選択して、このフィールドを無視する**
    1. **このフィールドのカスタム区切り記号と句読点を入力します**

   > [!IMPORTANT]
   > 1 つ以上 5 つ以下のスキーマ フィールド を検索可能として指定する必要があります。

7. **[保存]** を選択します。 これでスキーマが一覧表示され、使用できるようになります。

   > [!IMPORTANT]
   > スキーマを削除し、それが既に EDM の機密情報の種類に関連付けられている場合は、まずEDM の機密情報の種類を削除し、その後、スキーマを削除できます。 データ ストアが関連付けられているスキーマを削除すると、24 時間以内にデータ ストアも削除されます。

## <a name="export-of-the-edm-schema-file-in-xml-format"></a>EDM スキーマ ファイルを XML 形式でエクスポートする

EDM スキーマ ウィザードで EDM スキーマを作成した場合は、EDM スキーマ ファイルを XML 形式でエクスポートする必要があります。 これをハッシュに含め、 [厳密なデータ一致の機密情報の種類フェーズの機密情報ソース テーブルをアップロード](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types) する必要があります。

1. [セキュリティ/コンプライアンス PowerShell に接続します](/powershell/exchange/connect-to-scc-powershell)。

2. EDM スキーマ ファイルをエクスポートするには、次の構文を使用します。

   ```powershell
   $Schema = Get-DlpEdmSchema -Identity "[your EDM Schema name]"
   Set-Content -Path ".\Schemafile.xml" -Value $Schema.EdmSchemaXML
   ```

3. 後で使用するために、このファイルを保存します。

## <a name="create-exact-data-match-schema-manually-and-upload"></a>完全なデータ一致スキーマを手動で作成し、アップロードする

スキーマ ファイルで、次の構文を使用して、機密情報ソース テーブル内の各列のエントリを構成します。

```xml
<Field name="FieldName" searchable="true/false" caseInsensitive="true/false" ignoredDelimiters="delimiter characters" />
```

### <a name="using-the-caseinsensitive-and-ignoreddelimiters-fields"></a>caseInsensitive フィールドと ignoredDelimiters フィールドの使用

次のスキーマ XML サンプルでは、 *caseInsensitive* フィールドと *ignoredDelimiters* フィールドを使用します。

スキーマ定義の値に設定された *caseInsensitive* フィールドを含めると、EDM はケースの `true` 違いに基づいてアイテムを除外しません。 たとえば、EDM には **、フィールドの値 FOO-1234** と **fOo-1234** が `PatientID` 同一であると表示されます。

サポートされている文字を *含む ignoreDelimiters* フィールドを含めると、EDM はそれらの文字を無視します。 そのため、EDM では、フィールドに対`PatienID`して **FOO-1234** と **FOO#1234** の値が同一であると表示されます。

この例では、両方 `caseInsensitive` を使用する `ignoredDelimiters` 場合、EDM は **FOO-1234** と **fOo#1234** を同一と見なし、アイテムを患者レコードの機密情報の種類として分類します。

これらのパラメーターはどちらもフィールドごとに使用されます。

> [!IMPORTANT]
> *スペース* を無視するように構成した場合、これはプライマリ フィールド列に対してのみ有効であり、複数単語の文字列を検出できる機密情報の種類が定義されます。 それ以外の場合は、分析対象のコンテンツ内の個々の単語に対して比較が行われます。

*ignoredDelimiters* フラグは、英数字以外の文字をサポートします。次に例を示します。

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
> EDM の機密情報の種類を定義する場合、 *ignoreDelimiters* は、EDM パターンのプライマリ要素に関連付けられた分類機密情報の種類がアイテム内のコンテンツを識別する方法に影響しません。 したがって、検索可能なフィールドに *ignoreDelimiters* を構成する場合は、そのフィールドに基づいて主要素に使用される機密情報の種類が、それらの文字が存在する場合と存在しない文字列の両方を選択するようにする必要があります。
>
> 機密情報ソース テーブル内の列の数とスキーマ内のフィールドの数が一致する必要があります。順序は関係ありません。

1. スキーマを XML 形式で定義します (次の例と同様)。 このスキーマ ファイル **edm.xml** に名前を付け、機密情報ソース テーブルの列ごとに構文を使用する行が存在するように構成します。

      `\<Field name="" searchable=""/\>`.

      - *Field name* の値に列名を使用します。
      - 検索可能なフィールドと最大 5 つのフィールドのプライマリ フィールドに *searchable="true" を* 使用します。 少なくとも 1 つのフィールドは検索可能である必要があります。

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

   XML 形式で EDM スキーマ ファイルを作成したら、それをクラウド サービスにアップロードする必要があります。

2. [セキュリティ/コンプライアンス PowerShell に接続します](/powershell/exchange/connect-to-scc-powershell)。

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
   > 変更を確認せずに行う場合は、手順 3 で使用 `-Confirm:$true` しないでください。

> [!NOTE]
> 追加機能を使用して EDMSchema を更新するには、10 から 60 分かかることがあります。 追加機能を使用する手順を実行する前に、更新プログラムを完了する必要があります。

## <a name="next-step"></a>次のステップ

- [機密情報の種類と完全に一致する機密情報のソース テーブルをハッシュしてアップロードする](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)
