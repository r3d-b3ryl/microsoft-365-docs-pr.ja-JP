---
title: 機密情報の種類/ルール パッケージと完全に一致するデータを作成する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 機密情報の種類/ルール パッケージと完全に一致するデータを作成する
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eb15f54a8a944e1c764a2540f36926dd433fb2d3
ms.sourcegitcommit: bb493f12701f6d6ee7d5e64b541adb87470bc7bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2022
ms.locfileid: "62900748"
---
# <a name="create-exact-data-match-sensitive-information-typerule-package"></a>機密情報の種類/ルール パッケージと完全に一致するデータを作成する

コンプライアンス センターの EDM スキーマと SIT ウィザードを使用して、正確なデータ一致 ( [EDM](#use-the-edm-schema-and-sit-wizard) ) 機密情報の種類 (SIT) を作成するか、ルール パッケージ XML ファイルを手動で作成 [できます](#create-a-rule-package-manually)。 1 つのメソッドを使用してスキーマを作成し、後でもう一方のメソッドを使用して編集することで、両方を組み合わせすることもできます。

EDM ベースの SITS またはそれらの実装に精通していない場合は、次の情報を理解する必要があります。

- [機密情報の種類に関する詳細情報](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [完全なデータ一致に基づく機密情報の種類の使用を開始する](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)

## <a name="use-the-edm-schema-and-sit-wizard"></a>EDM スキーマと SIT ウィザードの使用

このウィザードを使用すると、プロセスを簡略化するために機密情報の種類 (SIT) ファイルを作成できます。

EDM 機密情報の種類は、1 つ以上のパターンで構成されます。 各パターンは、ドキュメントまたは電子メール内の機密性の高いコンテンツを識別するために使用される証拠 (スキーマのフィールド) の組み合わせを表します。

## <a name="pre-requisites"></a>前提条件

以下の記事の手順を実行します。

1. [完全なデータ一致に基づく機密情報の種類のソース データをエクスポートする](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
2. [完全なデータ一致に基づく機密情報の種類のスキーマを作成する](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)
3. [機密情報の種類と完全に一致する機密情報のソース テーブルをハッシュしてアップロードする](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)

- ウィザードを使用して EDM 機密情報の種類を作成するか、PowerShell 経由でルール パッケージ XML ファイルを作成する場合でも、UI を使用してカスタム機密情報の種類を作成、テスト、展開するには、グローバル管理者またはコンプライアンス管理者のアクセス許可が必要です。 「[管理者の役割について」を参照Office 365](/office365/admin/add-users/about-admin-roles)。
- プライマリ要素の機密情報の種類として使用する組み込みの 1 つを識別します。
  - 組み込みの機密情報の種類が、選択した列のデータと一致しない場合は、行うカスタム機密情報の種類を作成する必要があります。
  - スキーマのプライマリ要素列に対して [区切り文字を無視する] オプションを選択した場合は、作成するカスタム SIT が、選択した区切り記号を使用せずにデータと一致します。
  - 組み込みの SIT を使用する場合は、選択する文字列を正確に検出し、周囲の文字を含めず、機密情報テーブルに格納されている文字列の有効な部分を除外します。

「[機密情報の種類エンティティ定義」および「](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions)[コンプライアンス センターでカスタム機密情報の種類を作成する」を参照してください](create-a-custom-sensitive-information-type.md)。

### <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>完全一致スキーマと機密情報の種類パターンウィザードを使用する

1. テナントの Microsoft 365 コンプライアンス センターでは、**データの分類** > **完全一致** に移動します。 

2. **EDM の機密情報の種類** を選択し、 **EDM の機密情報の種類を作成** して、機密情報の種類の構成ウィザードを開きます。

3. [ **既存の EDM スキーマの選択] を** 選択し、[完全なデータ一致ベースの機密情報の種類のスキーマの作成] で作成したスキーマ [を選択します](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)。

4. **次へ** を選択し、**パターンの作成** を選択します。

5. **信頼度** および **主要要素** を選択します。 信頼度の詳細については、「機密情報の [種類について」を参照してください](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)。

6. [Primary] **要素の** 機密情報の種類を選択して関連付け、ドキュメント内のテキストをプライマリ要素フィールドのすべての値と比較するテキストを定義します。 利用可能な機密情報の種類の詳細については、「[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」を参照してください。

   > [!IMPORTANT]
   > 検索するコンテンツの形式と密接に一致する機密情報の種類を選択します。 不要なコンテンツに一致する機密情報の種類 (すべてのテキスト文字列に一致する情報など) を選択すると、システムに過剰な負荷が発生し、機密情報が欠落する可能性があります。 ここで使用する機密情報の種類を選択する場合の推奨事項については、このドキュメントの「完全なデータ照合の概要」の「ベスト プラクティス」セクションを参照してください。

7. [サポート] 要素 **と一致オプション** を選択します。

8. [完了 **] と [** 次へ] を **選択します**。

9. 目的の **信頼度と文字の間隔** を選択します。 これは、EDM 機密情報の種類全体の既定値になります。

10. EDM **機密情報** の種類に追加のパターンを作成する場合は、[パターンの作成] を選択します。

11. [**次へ**] を選択し、**名前** および **管理者向けの説明** を入力します。

12. レビューし、[**送信**] を選択します。

### <a name="edit-or-delete-the-sensitive-information-type-pattern"></a>機密情報の種類パターンを編集または削除する

1. コンプライアンス **センターを開** > **くData 分類** > **Exact データが一致します**。

2. **[EDM 機密情報の種類] を選択します**。

3. 編集する EDM SIT を選択します。

4. [ **EDM 機密情報の種類の編集] または** [ **EDM 機密情報** の種類をフライアウトから削除する] を選択します。

## <a name="create-a-rule-package-manually"></a>ルール パッケージを手動で作成する

この手順では、ルール パッケージと呼ばれる XML 形式 (Unicode エンコード) でファイルを作成し、コンプライアンス センター PowerShell コマンドレットを使用して Microsoft 365 にアップロードする方法を示します。

> [!NOTE]
> マップする SIT が複数語の検索証拠を検出できる場合は、手動で作成されたルール パッケージで定義するセカンダリ要素を SIT にマップできます。 `John Smith` `John Smith` `Smith` `John`たとえば、その詳細証拠フィールドが、そのパターンを検出できる SIT にマップされていない場合、コンテンツ内で 1 つのフィールドにアップロードされた用語と個別に比較して見つかったため、名前はセカンダリ要素として一致しません。
>
> 1 つのテナントに 10 のルール パッケージMicrosoft 365があります。 ルール パッケージには任意の数の機密情報の種類を含め、このメソッドを使用して新しい機密情報の種類を定義する度に新しいルール パッケージを作成しないようにすることができます。代わりに、既存のルール パッケージをエクスポートし、機密情報の種類を XML に追加してから再アップロードします。

1. 次の例のように、XML 形式 (Unicode エンコード) でルール パッケージを作成します。 (この例は、コピー、変更、使用することができます。)

   ルール パッケージを設定する場合は、.csv、.tsv、またはパイプ (|) で区切られた機密情報ソース テーブル ファイルとedm.xmlスキーマ ファイル **を正しく参照してください** 。 この例は、コピー、変更、使用が可能です。 このサンプル xml では、EDM の機密性の高い型を作成するために、次のフィールドをカスタマイズする必要があります。

   - **RulePack id & ExactMatch id**: [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid) を使用して GUID を作成します。

   - **Datastore**: このフィールドは、使用する EDM ルックアップデータストアを指定します。 構成済みの EDM スキーマのデータ ソース名を指定します。

   - **idMatch**: このフィールドは、EDM の主要素を示します。
   - **一致**: 正確な参照で使用するフィールドを指定します。 データストアの EDM スキーマで検索可能なフィールド名を指定します。
   - **分類**: このフィールドは、EDM 参照をトリガーする機密情報の種類の一致を指定します。 既存の組み込みまたはカスタムの機密情報の種類の名前または GUID を使用できます。

   > [!NOTE]
   > 指定された SIT に一致する文字列はハッシュされ、機密情報ソース テーブル内のすべてのエントリと比較されます。 分類要素のカスタム SIT を選択した場合にパフォーマンスの問題を回避するには、コンテンツの大きな割合に一致する SIT を使用しません。 たとえば、"任意の数値" または "任意の 5 文字の単語" に一致する単語などです。 サポート キーワードを追加するか、カスタム分類 SIT の定義に書式を含めて区別できます。

   - **一** 致: このフィールドは、idMatch の近接で見つかった追加の証拠を示します。
   - **一致**: データストアの EDM スキーマに任意のフィールド名を指定します。
   - **Resource idRef:** このセクションでは、複数の地域で機密性の高い型の名前と説明を指定します。
     - ExactMatch ID の GUID を指定します。
     - **名前** & **description**: 必要に応じてカスタマイズします。

      ```xml
      <RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
        <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
          <Version build="0" major="2" minor="0" revision="0" />
          <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
          <Details defaultLangCode="en-us">
            <LocalizedDetails langcode="en-us">
              <PublisherName>IP DLP</PublisherName>
              <Name>Health Care EDM Rulepack</Name>
              <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
            </LocalizedDetails>
          </Details>
        </RulePack>
        <Rules>
          <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
            <Pattern confidenceLevel="65">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
            </Pattern>
            <Pattern confidenceLevel="75">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
              <Any minMatches ="3" maxMatches ="6">
                <match matches="PatientID" />
                <match matches="MRN"/>
                <match matches="FirstName"/>
                <match matches="LastName"/>
                <match matches="Phone"/>
                <match matches="DOB"/>
              </Any>
            </Pattern>
          </ExactMatch>
          <LocalizedStrings>
            <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
              <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
              <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
            </Resource>
          </LocalizedStrings>
        </Rules>
      </RulePackage>
      ```

2. アップロード PowerShell コマンドを実行して、ルール パッケージを作成します。

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData ([System.IO.File]::ReadAllBytes('.\\rulepack.xml'))
   ```

> [!NOTE]
> ルール パッケージ ファイルの構文は、他の機密情報の種類と同じです。 ルール パッケージ ファイルの構文と追加の構成オプションの詳細、および PowerShell を使用して機密情報の種類を変更および削除する手順については、「 [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md#create-a-custom-sensitive-information-type-using-powershell) を使用してカスタム機密情報の種類を作成する」を参照してください。

## <a name="next-step"></a>次の手順

- [機密情報の種類と完全に一致するデータをテストする](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)
