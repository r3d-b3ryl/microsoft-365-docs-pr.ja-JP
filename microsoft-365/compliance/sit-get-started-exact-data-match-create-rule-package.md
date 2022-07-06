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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 機密情報の種類/ルール パッケージと完全に一致するデータを作成する
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16da97f249eff856fd1b0e671d71d813b3cbac73
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66628509"
---
# <a name="create-exact-data-match-sensitive-information-typerule-package"></a>機密情報の種類/ルール パッケージと完全に一致するデータを作成する

コンプライアンス センターの [EDM スキーマと SIT ウィザード](#use-the-edm-schema-and-sit-wizard) を使用して、厳密なデータ一致 (EDM) 機密情報の種類 (SIT) を作成するか、ルール パッケージ XML ファイルを [手動で](#create-a-rule-package-manually)作成できます。 1 つのメソッドを使用して両方を組み合わせてスキーマを作成し、後でもう一方のメソッドを使用して編集することもできます。

EDM ベースの SITS またはその実装に慣れていない場合は、次の点に慣れる必要があります。

- [機密情報の種類に関する詳細情報](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [完全なデータ一致に基づく機密情報の種類の使用を開始する](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)

## <a name="use-the-edm-schema-and-sit-wizard"></a>EDM スキーマと SIT ウィザードを使用する

このウィザードを使用すると、プロセスを簡略化するために機密情報の種類 (SIT) ファイルを作成できます。

EDM 機密情報の種類は、1 つ以上のパターンで構成されます。 各パターンは、ドキュメントまたは電子メール内の機密コンテンツを識別するために使用される証拠 (スキーマのフィールド) の組み合わせを記述します。

## <a name="pre-requisites"></a>前提条件

次の記事の手順を実行します。

1. [完全なデータ一致に基づく機密情報の種類のソース データをエクスポートする](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
2. [完全なデータ一致に基づく機密情報の種類のスキーマを作成する](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)
3. [機密情報の種類と完全に一致する機密情報のソース テーブルをハッシュしてアップロードする](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)

- ウィザードを使用して EDM 機密情報の種類を作成する場合でも、PowerShell を使用してルール パッケージ XML ファイルを作成する場合でも、UI を使用してカスタムの機密情報の種類を作成、テスト、デプロイするには、グローバル管理者またはコンプライアンス管理者のアクセス許可が必要です。 [Office 365の管理者ロールについて](/office365/admin/add-users/about-admin-roles)を参照してください。
- 主要素の機密情報の種類として使用する組み込みの SIT の 1 つを特定します。
  - 組み込みの機密情報の種類が選択した列のデータと一致しない場合は、カスタムの機密情報の種類を作成する必要があります。
  - スキーマのプライマリ要素列で [無視区切り記号] オプションを選択した場合は、作成するカスタム SIT が、選択した区切り記号の有無にかかわらずデータと一致することを確認します。
  - 組み込みの SIT を使用する場合は、選択する文字列を正確に検出し、周囲の文字を含めたり、機密情報テーブルに格納されている文字列の有効な部分を除外したりしないようにしてください。

[「機密情報の種類のエンティティ定義」](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions)および[「コンプライアンス センターでのカスタムの機密情報の種類の作成」を参照してください](create-a-custom-sensitive-information-type.md)。

### <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>完全一致スキーマと機密情報の種類パターンウィザードを使用する

1. テナントのMicrosoft Purview コンプライアンス ポータルで、[**データ分類** > **の完全一致]** に移動します。

2. **EDM の機密情報の種類** を選択し、 **EDM の機密情報の種類を作成** して、機密情報の種類の構成ウィザードを開きます。

3. [ **既存の EDM スキーマの選択]** を選択し、 [完全一致ベースの機密情報の種類のスキーマを作成する](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)で作成したスキーマを選択します。

4. **次へ** を選択し、**パターンの作成** を選択します。

5. **信頼度** および **主要要素** を選択します。 信頼レベルの詳細については、「 [機密情報の種類の詳細](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)」を参照してください。

6. **プライマリ要素の機密情報の種類** を選択して関連付け、ドキュメント内のテキストを主要素フィールドのすべての値と比較する内容を定義します。 利用可能な機密情報の種類の詳細については、「[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」を参照してください。

   > [!IMPORTANT]
   > 検索するコンテンツの形式と密接に一致する機密情報の種類を選択します。 不要なコンテンツに一致する機密情報の種類 (すべてのテキスト文字列に一致するものやすべての数値など) を選択すると、システムに過度の読み込みが発生し、機密情報が失われる可能性があります。

7. **サポート要素** と一致オプションを選択します。

8. [ **完了] と** **[次へ**] を選択します。

9. 目的の **信頼度と文字の間隔** を選択します。 これは、EDM の機密情報の種類全体の既定値です。

10. EDM の機密情報の種類に追加のパターンを作成する場合は、[パターンの **作成** ] を選択します。

11. [**次へ**] を選択し、**名前** および **管理者向けの説明** を入力します。

12. レビューし、[**送信**] を選択します。

### <a name="edit-or-delete-the-sensitive-information-type-pattern"></a>機密情報の種類パターンを編集または削除する

1. **コンプライアンス センター** > **のデータ分類** > **の完全一致を開きます**。

2. **EDM の機密情報の種類を選択します**。

3. 編集する EDM SIT を選択します。

4. ポップアップから **[EDM の機密情報の種類の編集]** または **[EDM の機密情報の種類の削除** ] を選択します。

## <a name="working-with-specific-types-of-data"></a>特定の種類のデータの操作

パフォーマンス上の理由から、不要な一致の数を最小限に抑えるパターンを使用することが重要です。 たとえば、正規表現に基づいて機密情報の種類を使用できます。

`\b\w*\b`

これは、ドキュメントまたは電子メール内のすべての個々の単語または番号と一致します。 これにより、サービスが一致してオーバーロードされ、真の一致が検出されません。 より正確なパターンを使用すると、この状況を回避できます。 一般的な種類のデータに対して適切な構成を識別するための推奨事項を次に示します。

**電子メール アドレス**: 電子メール アドレスは簡単に識別できますが、コンテンツでは非常に一般的であるため、プライマリ フィールドとして使用すると、システムに大きな負荷がかかる可能性があります。 セカンダリ 証拠としてのみ使用します。 主要な証拠として使用する必要がある場合は、ロジックを使用して電子メールの使用 `From` を除外する `To` カスタムの機密情報の種類を定義し、一致する必要がある不要な文字列の数を減らすために、会社の電子メール アドレスを持つユーザーを除外します。

**電話番号**: 電話番号は、国のプレフィックス、市外局番、区切り記号など、さまざまな形式で使用できます。 負荷を最小限に抑えながら誤った負の値を減らすには、セカンダリ要素としてのみ使用し、かっこやダッシュなどの可能性のある区切り記号をすべて除外し、常に電話番号に存在する部分のみを機密データ テーブルに含めます。

**人物の名前**: この EDM 型の分類要素として正規表現に基づく機密情報の種類を使用する場合は、一般的な単語と区別するのが難しいため、主な要素として人の名前を使用しないでください。

処理する多くの一致を生成する可能性があるプロジェクト コード名など、特定のパターンで識別するのが難しい主な要素を使用する必要がある場合は、EDM 型の分類要素として使用する機密情報の種類にキーワードを含める必要があります。 たとえば、通常の単語である可能性があるプロジェクト コード名を使用する場合、EDM 型の分類要素として使用される機密型のプロジェクト名正規表現ベースのパターンに近い、必要な追加の証拠として単語 `project` を使用できます。 または、EDM SIT の分類要素として、通常のディクショナリに基づく機密型の使用を検討することもできます。

数値文字列を一致させる場合は、数字の数や開始桁 (既知の場合) など、許容される数値範囲を指定します。 比較的柔軟な範囲の数値と一致する必要がある場合は、基本 SIT でキーワードを使用して一致する数を減らすことができます。 たとえば、7 から 11 桁の数字で構成されるアカウント番号を一致させようとする場合は、必要な追加の証拠として SIT に単語 `account`() `customer``acct.` を追加します。 これにより、EDM によって処理される一致の制限を超える可能性がある不要な一致の可能性が低くなります。

主要素として使用する必要があるフィールドが、多数の一致を引き起こす可能性がある単純なパターンに従い、機密情報の種類で追加の証拠としてキーワードの存在を追加できない場合は、そのパターンの出現回数を最小限に抑える必要があります。 たとえば、次の方法で定義されたカスタムの機密情報の種類を使用して、EDM と一致する可能性のある 5 桁の数字を囲む他の 5 桁の数字を少なくとも 29 個検出できます。

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

場合によっては、履歴上の理由で標準化されたパターンに従っていない特定のアカウントまたはレコードの識別番号を識別する必要があります。 たとえば、 `Medical Record Numbers` 同じ組織内の文字と数字の多くの異なる順列で構成できます。 パターンを特定するのは最初は難しいかもしれませんが、多くの場合、より詳細な検査を行うと、無効な一致が過剰に発生することなく、すべての有効な値を記述するパターンを絞り込むことが可能になります。 たとえば、"すべての MRN は少なくとも 7 文字の長さであり、少なくとも 2 つの数字が含まれ、文字が含まれている場合は 1 から始まる" ことが検出される場合があります。 このような条件に基づいて正規表現を作成すると、必要なすべての値をキャプチャしながら不要な一致を最小限に抑えることができます。さらに分析すると、異なる形式を記述する個別のパターンを定義することで、精度が向上する可能性があります。

## <a name="create-a-rule-package-manually"></a>ルール パッケージを手動で作成する

この手順では、ルール パッケージと呼ばれる XML 形式のファイルを (Unicode エンコードを使用して) 作成し、Security & Compliance PowerShell コマンドレットを使用して Microsoft Purview にアップロードする方法を示します。

> [!NOTE]
> マップする SIT で複数単語の裏付けとなる証拠を検出できる場合は、手動で作成されたルール パッケージで定義するセカンダリ要素を SIT にマップできます。 たとえば、その裏付けとなる証拠フィールドがそのパターンを検出できる SIT にマップされていない場合は、コンテンツ内でフィールドの 1 つにアップロードされた用語`John Smith`と個別に比較`John`して`Smith`見つけたため、名前`John Smith`はセカンダリ要素として一致しません。
>
> Microsoft 365 テナントには、10 個のルール パッケージの制限があります。 ルール パッケージには任意の数の機密情報の種類を含めることができるため、このメソッドを使用して新しい機密情報の種類を定義するたびに新しいルール パッケージを作成することは避けることができます。代わりに、既存のルール パッケージをエクスポートし、再アップロードする前に機密情報の種類を XML に追加します。

1. 次の例のように、XML 形式 (Unicode エンコード) でルール パッケージを作成します。 (この例は、コピー、変更、使用することができます。)

   ルール パッケージを設定するときは、.csv、.tsv、またはパイプ (|) で区切られた機密情報ソース テーブル ファイルとedm.xmlスキーマ ファイル **を** 正しく参照してください。 この例は、コピー、変更、使用が可能です。 このサンプル xml では、EDM 機密型を作成するために、次のフィールドをカスタマイズする必要があります。

   - **RulePack id & ExactMatch id**: [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid) を使用して GUID を作成します。

   - **Datastore**: このフィールドは、使用する EDM ルックアップデータストアを指定します。 構成済みの EDM スキーマのデータ ソース名を指定します。

   - **idMatch**: このフィールドは、EDM の主要素を示します。
   - **一致**: 完全参照で使用するフィールドを指定します。 データストアの EDM スキーマで検索可能なフィールド名を指定します。
   - **分類**: このフィールドは、EDM ルックアップをトリガーする機密情報の種類の一致を指定します。 既存の組み込みまたはカスタムの機密情報の種類の名前または GUID を使用できます。

   > [!NOTE]
   > 指定された SIT に一致する文字列はすべてハッシュされ、機密情報ソース テーブル内のすべてのエントリと比較されることに注意してください。 分類要素にカスタム SIT を選択した場合にパフォーマンスの問題を回避するには、コンテンツの大きな割合に一致するものを使用しないでください。 たとえば、"任意の数値" または "任意の 5 文字の単語" に一致する単語などです。 サポート キーワードを追加するか、カスタム分類 SIT の定義に書式設定を含めることで、区別できます。

   - **一致**: このフィールドは、idMatch の近くで見つかった追加の証拠を指します。
   - **一致**: DataStore の EDM スキーマに任意のフィールド名を指定します。
   - **Resource idRef:** このセクションでは、複数のロケールで機密性の高い型の名前と説明を指定します
     - ExactMatch ID の GUID を指定します。
     - **名前** & **説明**: 必要に応じてカスタマイズします。

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

2. 次の PowerShell コマンドを実行して、ルール パッケージをアップロードします。

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData ([System.IO.File]::ReadAllBytes('.\\rulepack.xml'))
   ```

> [!NOTE]
> ルール パッケージ ファイルの構文は、他の機密情報の種類と同じです。 ルール パッケージ ファイルの構文と追加の構成オプションの詳細、および PowerShell を使用した機密情報の種類の変更と削除の手順については、 [PowerShell を使用してカスタムの機密情報の種類を作成します](create-a-custom-sensitive-information-type-in-scc-powershell.md#create-a-custom-sensitive-information-type-using-powershell)。

## <a name="next-step"></a>次のステップ

- [機密情報の種類と完全に一致するデータをテストする](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)
