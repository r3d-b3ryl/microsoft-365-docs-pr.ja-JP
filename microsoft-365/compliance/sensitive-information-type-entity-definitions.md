---
title: 機密情報の種類のエンティティ定義
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: DLP ポリシーで使用できる機密情報の種類は 200 種類です。 この記事では、これらすべての機密情報の種類を一覧表示し、DLP ポリシーが各種類を検出するときに検索する情報漏えい対策ポリシーを示します。
ms.openlocfilehash: 92b6d6720da67274e820a57fec8d2ade338574f2
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754167"
---
# <a name="sensitive-information-type-entity-definitions"></a>機密情報の種類のエンティティ定義

この記事では、すべての機密情報の種類エンティティ定義を一覧表示します。 各定義は、DLP ポリシーが各種類を検出するために検索する情報を示します。 機密情報の種類の詳細については、「機密情報の [種類」を参照してください。](sensitive-information-type-learn-about.md)

> [!NOTE]
> 精度番号 (数値 1 ~ 100) を使用した信頼度 (高/中/低) のマッピング
> - 低信頼度: 65 以下
> - 中程度の信頼度: 75
> - 高い信頼度: 85

## <a name="aba-routing-number"></a>ABA ルーティング番号

### <a name="format"></a>フォーマット

書式付きまたは書式設定されていないパターンに含め得る 9 桁の数字

### <a name="pattern"></a>パターン

- 00 ~ 12、21~32、61~72、または 80 の範囲の 2 桁
- 2 桁
- オプションのハイフン
- 4 桁
- オプションのハイフン
- 数字


### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_aba_routing がパターンに一致するコンテンツを検出した。
- Keyword_ABA_Routing のキーワードを検出した。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- 関数 Func_aba_routing がパターンに一致するコンテンツを検出した。

```xml
    <!-- ABA Routing Number -->
    <Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_aba_routing" />
      </Pattern>
    </Entity>
```


### <a name="keywords"></a>キーワード

#### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- aba number
- aba#
- aba
- abarouting#
- abaroutingnumber
- americanbankassociationrouting#
- americanbankassociationroutingnumber
- bankrouting#
- bankroutingnumber
- ルーティング#
- ルーティングなし
- ルーティング番号
- routing transit number
- ルーティング#
- RTN


## <a name="argentina-national-identity-dni-number"></a>アルゼンチンの国民 ID (DNI) 番号

### <a name="format"></a>フォーマット

ピリオドの付きまたは指定のない 8 桁の数字

### <a name="pattern"></a>パターン

8 桁の数字:
- 2 桁
- オプションの期間
- 3 桁の数字
- オプションの期間
- 3 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、Regex_argentina_national_id一致するコンテンツを検索します。
- このページのKeyword_argentina_national_idが見つかりました。

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity number
- cedula
- cédula
- dni
- documento nacional de identidad
- documento número
- documento numero
- registro nacional de las personas
- rnp

## <a name="argentina-unique-tax-identification-key-cuitcuil"></a>アルゼンチン固有の税識別キー (CUIT/CUIL)

### <a name="format"></a>フォーマット

ダッシュ付き 11 桁

### <a name="pattern"></a>パターン

ダッシュ付き 11 桁:
- 20、23、24、27、30、33、34 の 2 桁
- ハイフン (-)
- 8 桁
- ハイフン (-)
- 1 つのチェックディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数 `Func_Argentina_Unique_Tax_Key` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_Argentina_Unique_Tax_Key` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数 `Func_Argentina_Unique_Tax_Key` は、パターンに一致するコンテンツを検索します。

```xml
    <!-- Argentina Unique Tax Identification Key (CUIT/CUIL) -->
      <Entity id="98da3da1-9199-4571-b7c4-b6522980b507" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
          <Match idRef="Keyword_Argentina_Unique_Tax_Key" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_argentina_unique_tax_key"></a>Keyword_Argentina_Unique_Tax_Key

- Clave Unica de Identificacion Tributaria
- CUIT
- 一意の労働識別コード 
- Clave Única de Identificación Tributaria
- 一意の労働識別コード
- CUIL
- 一意の税の識別キー
- 一意の労働識別キー
- 労働識別の一意のキー
- 一意の作業識別コード
- 一意の作業コードの識別
- 一意の作業識別キー
- 作業識別の一意のキー
- 一意の税の識別コード
- 納税者識別の一意のキー
- 一意の労働識別コード
- 固有の労働識別コード
- 一意の作業識別キー
- 労働識別の一意のキー
- 税 ID
- taxID#
- taxId
- taxidnumber
- 税番号
- tax no
- tax#
- tax#
- 納税者 ID
- 納税者番号
- 納税者なし
- 納税者#
- 納税者#
- 税金の ID
- tax identification
- Número de Identificación Fiscal
- número de contribuyente


## <a name="australia-bank-account-number"></a>オーストラリアの銀行口座番号

### <a name="format"></a>フォーマット

銀行の状態分岐番号の付きまたは指定なしの 6 ~ 10 桁の数字

### <a name="pattern"></a>パターン

アカウント番号は 6 ~ 10 桁です。

オーストラリアの銀行の州支店番号:
- 3 桁の数字
- ハイフン
- 3 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、Regex_australia_bank_account_number一致するコンテンツを検索します。
- Keyword_australia_bank_account_number のキーワードを検出した。
- 正規表現 Regex_australia_bank_account_number_bsb がパターンに一致するコンテンツを検出した。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、Regex_australia_bank_account_number一致するコンテンツを検索します。

- Keyword_australia_bank_account_number のキーワードを検出した。

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_australia_bank_account_number"></a>Keyword_australia_bank_account_number

- swift bank code
- correspondent bank
- base currency
- usa account
- holder address
- bank address
- information account
- fund transfers
- bank charges
- bank details
- banking information
- full names
- iaea

## <a name="australia-business-number"></a>オーストラリアのビジネス番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ


### <a name="format"></a>フォーマット

11 桁の数字 (オプションの区切り記号付き)

### <a name="pattern"></a>パターン

11 桁の数字とオプションの区切り記号:

- 2 桁
- オプションのハイフンまたはスペース
- 3 桁の数字
- オプションのハイフンまたはスペース
- 3 桁の数字
- オプションのハイフンまたはスペース
- 3 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_australian_business_number一致するコンテンツを検索します。
- このページのKeywords_australian_business_numberが見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_australian_business_number一致するコンテンツを検索します。

```xml
      <!-- Australia Business Number -->
      <Entity id="76e83b3b-01ee-4530-aced-e667a6609f49" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_australian_business_number" />
          <Match idRef="Keywords_australian_business_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_australian_business_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- オーストラリア のビジネスなし
- ビジネス番号
- abn#
- businessid#
- ビジネス ID
- abn
- businessno#

## <a name="australia-company-number"></a>オーストラリアの会社番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

区切り記号付き 9 桁

### <a name="pattern"></a>パターン

区切り記号が付く 9 桁の数字:

- 3 桁の数字
- スペース
- 3 桁の数字
- スペース
- 3 桁の数字


### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_Australian_Company_Number一致するコンテンツを検索します。
- このページのKeyword_Australian_Company_Numberが見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数はFunc_Australian_Company_Number一致するコンテンツを検索します。

```xml
      <!-- Australia Company Number -->
      <Entity id="b1fba4f7-7b3e-4bb9-8f9a-9366df604dbb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Australian_Company_Number" />
          <Match idRef="Keyword_Australian_Company_Number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_Australian_Company_Number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keyword_australia_company_number"></a>Keyword_australia_company_number

- can
- オーストラリアの会社なし
- オーストラリアの会社なし#
- オーストラリアの会社番号
- オーストラリアの会社なし
- オーストラリアの会社なし#
- オーストラリアの会社番号

## <a name="australia-drivers-license-number"></a>オーストラリアの運転免許証番号

### <a name="format"></a>フォーマット

9 文字と数字

### <a name="pattern"></a>パターン

9 文字と数字:

- 2 桁の数字または文字 (大文字と小文字を区別しない)
- 2 桁
- 5 桁または 1 文字 (大文字と小文字は区別されません)

または

- 1 ~ 2 文字の省略可能な文字 (大文字と小文字を区別しない)
- 4 ~ 9 桁

または

- 9 桁の数字または文字 (大文字と小文字を区別しない)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現 Regex_australia_drivers_license_number がパターンに一致するコンテンツを検出した。
- Keyword_australia_drivers_license_number のキーワードを検出した。
- Keyword_australia_drivers_license_number_exclusions のキーワードを検出しなかった。

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_australia_drivers_license_number"></a>Keyword_australia_drivers_license_number

- international driving permits
- australian automobile association
- international driving permit
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Licence
- Driver Licences
- DriversLic
- DriversLicence
- DriversLicences
- Drivers Lic
- Drivers Lics
- Drivers Licence
- Drivers Licences
- Driver'Lic
- Driver'Lics
- 運転免許証
- 運転免許証
- Driver' Lic
- Driver' Lics
- Driver' Licence
- Driver' Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's Licence
- Driver's Licences
- DriverLic#
- DriverLics#
- DriverLicence#
- DriverLicences#
- Driver Lic#
- Driver Lics#
- Driver Licence#
- Driver Licences#
- DriversLic#
- DriversLics#
- DriversLicence#
- DriversLicences#
- Drivers Lic#
- Drivers Lics#
- Drivers Licence#
- Drivers Licences#
- Driver'Lic#
- Driver'Lics#
- 運転免許証#
- 運転免許証#
- Driver' Lic#
- Driver' Lics#
- Driver' Licence#
- Driver' Licences#
- Driver'sLic#
- Driver'sLics#
- Driver'sLicence#
- Driver'sLicences#
- Driver's Lic#
- Driver's Lics#
- Driver's Licence#
- Driver's Licences#

#### <a name="keyword_australia_drivers_license_number_exclusions"></a>Keyword_australia_drivers_license_number_exclusions

- aaa
- DriverLicense
- DriverLicenses
- Driver License
- Driver Licenses
- DriversLicense
- DriversLicenses
- Drivers License
- Drivers Licenses
- 運転免許証
- 運転免許証
- Driver' License
- Driver' Licenses
- Driver'sLicense
- Driver'sLicenses
- Driver's License
- Driver's Licenses
- DriverLicense#
- DriverLicenses#
- Driver License#
- Driver Licenses#
- DriversLicense#
- DriversLicenses#
- Drivers License#
- Drivers Licenses#
- 運転免許証#
- 運転免許証#
- Driver' License#
- Driver' Licenses#
- Driver'sLicense#
- Driver'sLicenses#
- Driver's License#
- Driver's Licenses#

## <a name="australia-medical-account-number"></a>オーストラリアの医療アカウント番号

### <a name="format"></a>フォーマット

10 ～ 11 桁の数字

### <a name="pattern"></a>パターン

10 ～ 11 桁の数字:
- 最初の桁は 2 ～ 6 のいずれか
- 9 桁目はチェック ディジット
- 10 桁目は発行桁
- 11 桁目 (省略可能) は個人番号

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。
- Keyword_Australia_Medical_Account_Number のキーワードを検出した。
- チェックサムが渡される。


```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_australia_medical_account_number"></a>Keyword_Australia_Medical_Account_Number

- bank account details
- medicare payments
- mortgage account
- bank payments
- information branch
- credit card loan
- department of human services
- local service
- medicare


## <a name="australia-passport-number"></a>オーストラリアのパスポート番号

### <a name="format"></a>フォーマット

8 文字または 9 文字の英数字

### <a name="pattern"></a>パターン

- 1 文字 (N、E、D、F、A、C、U、X) の後に 7 桁の数字または
- 2 文字 (PA、PB、PC、PD、PE、PF、PU、PW、PX、PZ) の後に 7 桁の数字が続きます。

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、 `Regex_australia_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_australia_passport_number` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- 正規表現は、 `Regex_australia_passport_number` パターンに一致するコンテンツを検索します。

```xml
    <!-- Australia Passport Number -->
    <Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Match idRef="Keyword_australia_passport_number" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_australia_passport_number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- national identity card
- travel document
- issuing authority


## <a name="australia-tax-file-number"></a>オーストラリアの税ファイル番号

### <a name="format"></a>フォーマット

8 桁から 9 桁

### <a name="pattern"></a>パターン

通常、8 ~ 9 桁の数字には、次のようにスペースが表示されます。
- 3 桁の数字
- オプションのスペース
- 3 桁の数字
- オプションのスペース
- 最後の数字がチェック桁である 2 ~ 3 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数 Func_australian_tax_file_number がパターンに一致するコンテンツを検出した。
- Keyword_Australia_Tax_File_Number または Keyword_number_exclusions のキーワードを検出しなかった。
- チェックサムが渡される。

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_australia_tax_file_number"></a>Keyword_australia_tax_file_number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number
- tfn

## <a name="austria-drivers-license-number"></a>オーストリアの運転免許証番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 8 桁の数字

### <a name="pattern"></a>パターン

8 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。

- 正規表現は、  `Regex_austria_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_austria_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Austria Driver's License Number -->
      <Entity id="682f18ce-44eb-482b-8198-2bcb96a0761e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_austria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver's_license_number

- fuhrerschein
- führerschein
- Führerscheine
- Führerscheinnummer
- Führerscheinnummern

## <a name="austria-identity-card"></a>オーストリアの ID カード
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

文字、数字、特殊文字の 24 文字の組み合わせ

### <a name="pattern"></a>パターン

24 文字:

-  22 文字 (大文字と小文字を区別しない)、数字、円記号、スラッシュ、またはプラス記号

- 2 文字 (大文字と小文字を区別しない)、数字、円記号、スラッシュ、プラス記号、または等号

### <a name="checksum"></a>チェックサム

該当なし

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。

- 正規表現は、  `Regex_austria_eu_national_id_card` パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_austria_eu_national_id_card` 見つかりました。

```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- ID 番号
- national id
- personalausweis republik österreich

## <a name="austria-passport-number"></a>オーストリアのパスポート番号

### <a name="format"></a>フォーマット

1 文字の後にオプションのスペースと 7 桁の数字が続きます。

### <a name="pattern"></a>パターン

1 文字、7 桁、および 1 つのスペースの組み合わせ。

- 1 文字 (大文字と小文字は区別されません)
- 1 つのスペース (オプション)
- 7 桁

### <a name="checksum"></a>チェックサム

該当なし

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_austria_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_austria_eu_passport_number` つかったか、検索されます。
- 正規表現が `Regex_eu_passport_date1` DD.MM.YYYYY 形式の日付を検索するか、キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_austria_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_austria_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Austria Passport Number -->
      <Entity id="1c96ae4e-303b-447d-86c7-77113ac266bf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- reisepassnummer
- reisepasse
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付

## <a name="austria-social-security-number"></a>オーストリアの社会保障番号

### <a name="format"></a>フォーマット

指定した形式の 10 桁

### <a name="pattern"></a>パターン

10 桁の数字:

- シリアル番号に対応する 3 桁の数字
- 1 つのチェックディジット
- 生年月日に対応する 6 桁の数字 (DDMMYY)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_austria_eu_ssn_or_equivalent` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_austria_eu_ssn_or_equivalent` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数  `Func_austria_eu_ssn_or_equivalent` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Austria Social Security Number -->
      <Entity id="6896a906-86c9-4d19-a2da-6e43ccd19b7b" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_austria_eu_telephone_number" />
            <Match idRef="Keywords_austria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- オーストリアの ssn
- ehic 番号
- ehic no
- 保険コード
- insurancecode#
- 保険番号
- 保険なし
- krankenkassennummer
- krankenversicherung
- socialsecurityno
- socialsecurityno#
- 社会保障なし
- social security number
- social security code
- sozialversicherungsnummer
- sozialversicherungsnummer#
- soziale sicherheit kein
- sozialesicherheitkein#
- ssn#
- ssn
- versicherungscode
- versicherungsnummer
- zdravstveno zavarovanje

## <a name="austria-tax-identification-number"></a>オーストリアの納税者番号

### <a name="format"></a>フォーマット

オプションのハイフンとスラッシュを含む 9 桁の数字

### <a name="pattern"></a>パターン

オプションのハイフンとスラッシュを含む 9 桁の数字:

- 2 桁
- ハイフン (オプション)
- 3 桁の数字
- スラッシュ (省略可能)
- 4 桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_austria_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_austria_eu_tax_file_number` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数  `Func_austria_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Austria Tax Identification Number -->
      <Entity id="4fd58d22-af28-4451-b18a-6f722430a56d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

- österreich
- st.nr。
- steuernummer
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#
- 税番号

## <a name="austria-value-added-tax"></a>オーストリアの付加価値税
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

11 文字の英数字パターン

### <a name="pattern"></a>パターン

11 文字の英数字パターン:

- A または a
- T または t
- オプションの領域
- U または u
- オプションのスペース
- 2 桁または 3 桁の数字
- オプションのスペース
- 4 桁
- オプションのスペース
- 1 桁または 2 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_Austria_Value_Added_Tax一致するコンテンツを検索します。
- ユーザーからのキーワードKeyword_Austria_Value_Added_Tax見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_Austria_Value_Added_Tax一致するコンテンツを検索します。

```xml
      <!-- Austria Value Added Tax -->
      <Entity id="b6a3eda2-c56c-4b69-a5f7-dca34db00f48" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
          <Match idRef="Keyword_Austria_Value_Added_Tax" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keyword_austria_value_added_tax"></a>Keyword_austria_value_added_tax

- vat 番号
- vat#
- オーストリアの vat 番号
- vat No.
- vatno#
- 付加価値税番号
- オーストリアの vat
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- vat ID 番号
- atu 番号
- uid 番号


## <a name="azure-documentdb-auth-key"></a>Azure DocumentDB 認証キー

### <a name="format"></a>フォーマット

文字列 "DocumentDb" の後に、次のパターンで概説されている文字と文字列が続きます。

### <a name="pattern"></a>パターン

- 文字列 "DocumentDb"
- 3 ~ 200 文字の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 大きい記号 (>)、等号 (=)、二重引用符 (")、またはアポストロフィ (')
- 86 文字の小文字または大文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ
- 2 つの等号 (=)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、CEP_Regex_AzureDocumentDBAuthKey一致するコンテンツを検索します。
- パターンに一CEP_CommonExampleKeywords一致するコンテンツが見当たらない正規表現。

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(技術的には、この機密情報の種類は、キーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- contoso
- fabrikam
- northwind
- サンドボックス
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->net

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure IAAS データベース接続文字列と Azure SQL接続文字列

### <a name="format"></a>フォーマット

文字列 "Server"、"server"、または "data source" の後に、以下のパターンで概説されている文字列 ("cloudapp.azure" という文字列を含む) が続きます。<!--no-hyperlink-->com" または "cloudapp.azure" を指定します。<!--no-hyperlink-->net" または "database.windows" を指定します。<!--no-hyperlink-->net"、および文字列 "Password" または "password" または "pwd"

### <a name="pattern"></a>パターン

- 文字列 "Server"、"server"、または "data source"
- 0 から 2 文字の空白文字
- 等号 (=)
- 0 から 2 文字の空白文字
- 1 ~ 200 文字の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- "cloudapp.azure" という文字列。<!--no-hyperlink-->com", "cloudapp.azure.<!--no-hyperlink-->net"、または "database.windows" を指定します。<!--no-hyperlink-->net"
- 1 ~ 300 の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 文字列 "Password"、"password"、または "pwd"
- 0 から 2 文字の空白文字
- 等号 (=)
- 0 から 2 文字の空白文字
- セミコロンでない 1 つ以上の文字 (;)、引用符 (")、またはアポストロフィ (')
- セミコロン (;)、引用符 (")、またはアポストロフィ (')

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、CEP_Regex_AzureConnectionString一致するコンテンツを検索します。
- パターンに一CEP_CommonExampleKeywords一致するコンテンツが見当たらない正規表現。

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(技術的には、この機密情報の種類は、キーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- contoso
- fabrikam
- northwind
- サンドボックス
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->net

## <a name="azure-iot-connection-string"></a>Azure IoT接続文字列

### <a name="format"></a>フォーマット

文字列 "HostName" の後に、以下のパターンで概説されている文字列 ("azure-devices" という文字列を含む) が続きます。<!--no-hyperlink-->net」と「SharedAccessKey」。

### <a name="pattern"></a>パターン

- 文字列 "HostName"
- 0 から 2 文字の空白文字
- 等号 (=)
- 0 から 2 文字の空白文字
- 1 ~ 200 文字の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 文字列 "azure-devices.<!--no-hyperlink-->net"
- 1 ~ 200 文字の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 文字列 "SharedAccessKey"
- 0 から 2 文字の空白文字
- 等号 (=)
- 0 から 2 文字の空白文字
- 43 文字の小文字または大文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ
- 等号 (=)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、CEP_Regex_AzureIoTConnectionString一致するコンテンツを検索します。
- パターンに一CEP_CommonExampleKeywords一致するコンテンツが見当たらない正規表現。

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(技術的には、この機密情報の種類は、キーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- contoso
- fabrikam
- northwind
- サンドボックス
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->net

## <a name="azure-publish-setting-password"></a>Azure 発行設定パスワード

### <a name="format"></a>フォーマット

文字列 "userpwd=" の後に英数字の文字列が続きます。

### <a name="pattern"></a>パターン

- 文字列 "userpwd="
- 60 文字の小文字または数字の任意の組み合わせ
- 引用符 (")

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、CEP_Regex_AzurePublishSettingPasswords一致するコンテンツを検索します。
- パターンに一CEP_CommonExampleKeywords一致するコンテンツが見当たらない正規表現。


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(技術的には、この機密情報の種類は、キーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- contoso
- fabrikam
- northwind
- サンドボックス
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->net

## <a name="azure-redis-cache-connection-string"></a>Azure Redis キャッシュ接続文字列

### <a name="format"></a>フォーマット

文字列 "redis.cache.windows。<!--no-hyperlink-->net" の後に、文字列 "password" または "pwd" を含む、以下のパターンで概説されている文字と文字列が続きます。

### <a name="pattern"></a>パターン

- 文字列 "redis.cache.windows" を指定します。<!--no-hyperlink-->net"
- 1 ~ 200 文字の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 文字列 "password" または "pwd"
- 0 から 2 文字の空白文字
- 等号 (=)
- 0 から 2 文字の空白文字
- 小文字または大文字、数字、スラッシュ (/)、またはプラス記号 (+) の 43 文字の任意の組み合わせ
- 等号 (=)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、CEP_Regex_AzureRedisCacheConnectionString一致するコンテンツを検索します。
- パターンに一CEP_CommonExampleKeywords一致するコンテンツが見当たらない正規表現。

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(技術的には、この機密情報の種類は、キーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- contoso
- fabrikam
- northwind
- サンドボックス
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->net

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>フォーマット

文字列 "sig" の後に、以下のパターンで概説されている文字と文字列が続きます。

### <a name="pattern"></a>パターン

- 文字列 "sig"
- 0 から 2 文字の空白文字
- 等号 (=)
- 0 から 2 文字の空白文字
- 小文字または大文字、数字、またはパーセント記号 (%) である 43 ~ 53 文字の任意の組み合わせ
- 文字列 "%3d"
- 小文字または大文字、数字、またはパーセント記号 (%) ではない文字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、CEP_Regex_AzureSAS一致するコンテンツを検索します。

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Azure Service バス接続文字列

### <a name="format"></a>フォーマット

文字列 "EndPoint" の後に、文字列 "servicebus.windows" を含む、以下のパターンで概説されている文字と文字列が続きます。<!--no-hyperlink-->net」および「SharedAccesKey」を参照してください。

### <a name="pattern"></a>パターン

- 文字列 "EndPoint"
- 0 から 2 文字の空白文字
- 等号 (=)
- 0 から 2 文字の空白文字
- 1 ~ 200 文字の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 文字列 "servicebus.windows" を指定します。<!--no-hyperlink-->net"
- 1 ~ 200 文字の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 文字列 "SharedAccessKey"
- 0 から 2 文字の空白文字
- 等号 (=)
- 0 から 2 文字の空白文字
- 小文字または大文字、数字、スラッシュ (/)、またはプラス記号 (+) の 43 文字の任意の組み合わせ
- 等号 (=)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、CEP_Regex_AzureServiceBusConnectionString一致するコンテンツを検索します。
- パターンに一CEP_CommonExampleKeywords一致するコンテンツが見当たらない正規表現。

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(技術的には、この機密情報の種類は、キーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- contoso
- fabrikam
- northwind
- サンドボックス
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->net

## <a name="azure-storage-account-key"></a>Azure ストレージ アカウント キー

### <a name="format"></a>フォーマット

"DefaultEndpointsProtocol" という文字列の後に、"AccountKey" という文字列を含む、以下のパターンで概説されている文字と文字列が続きます。

### <a name="pattern"></a>パターン

- 文字列 "DefaultEndpointsProtocol"
- 0 から 2 文字の空白文字
- 等号 (=)
- 0 から 2 文字の空白文字
- 1 ~ 200 文字の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 文字列 "AccountKey"
- 0 から 2 文字の空白文字
- 等号 (=)
- 0 から 2 文字の空白文字
- 小文字または大文字、数字、スラッシュ (/)、またはプラス記号 (+) である 86 文字の任意の組み合わせ
- 2 つの等号 (=)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、CEP_Regex_AzureStorageAccountKey一致するコンテンツを検索します。
- パターンに一CEP_AzureEmulatorStorageAccountFilter一致するコンテンツが見当たらない正規表現。
- パターンに一CEP_CommonExampleKeywords一致するコンテンツが見当たらない正規表現。

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cep_azure_emulator_storage_account_filter"></a>CEP_azure_emulator_storage_account_filter

(技術的には、この機密情報の種類は、キーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(技術的には、この機密情報の種類は、キーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- contoso
- fabrikam
- northwind
- サンドボックス
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->net

## <a name="azure-storage-account-key-generic"></a>Azure Storage アカウント キー (汎用)

### <a name="format"></a>フォーマット

86 文字の小文字または大文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせで、次のパターンで説明されている文字が先行または続きます。

### <a name="pattern"></a>パターン

- 0 から 1 の大きい記号 (>)、アポストロフィ (')、等号 (=)、二重引用符 (")、または番号記号 (#)
- 小文字または大文字、数字、スラッシュ (/)、またはプラス記号 (+) である 86 文字の任意の組み合わせ
- 2 つの等号 (=)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、CEP_Regex_AzureStorageAccountKeyGeneric一致するコンテンツを検索します。

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>ベルギーの運転免許証番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 10 桁の数字

### <a name="pattern"></a>パターン

10 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_belgium_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見 `Keywords_eu_driver's_license_number` `Keywords_belgium_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Belgium Driver's License Number -->
      <Entity id="d89fd329-9324-433c-b687-2c37bd5166f3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_belgium_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード


#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver's_license_number

- rijbewijs
- rijbewijsnummer
- führerschein
- führerscheinnummer
- füehrerscheinnummer
- fuhrerschein
- fuehrerschein
- fuhrerscheinnummer
- fuehrerscheinnummer
- permis de conduire
- numéro permis conduire


## <a name="belgium-national-number"></a>ベルギーの国番号

### <a name="format"></a>フォーマット

11 桁の数字とオプションの区切り記号

### <a name="pattern"></a>パターン

11 の数字と区切り文字:
- 6 桁の数字と 2 つのオプションのピリオドを YY 形式で指定します。MM.DD の生年月日
- ドット、ダッシュ、スペースからのオプションの区切り文字
- 3 桁の連続した数字 (男性の場合は奇数、女性の場合も)
- ドット、ダッシュ、スペースからのオプションの区切り文字
- 2 つのチェックの数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_belgium_national_number一致するコンテンツを検索します。
- このページのKeyword_belgium_national_number見つかりました。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数はFunc_belgium_national_number一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- Belgium National Number -->
       <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_national_number" />
          <Match idRef="Keyword_belgium_national_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_belgium_national_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- belasting aantal
- bnn#
- bnn
- carte d'identité
- 国の特定者
- identifiantnational#
- identificatie
- ID
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- ID
- inscription
- 国番号
- 国の登録
- nationalnumber#
- nationalnumber
- nif#
- nif
- numéro d'assuré
- numéro de registre national
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- numéro national
- numéronational#
- 個人用 ID 番号
- personalausweis
- personalidnumber#
- registratie
- 登録
- registrationsnumme
- registrierung
- social security number
- ssn#
- ssn
- steuernummer
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#

## <a name="belgium-passport-number"></a>ベルギーのパスポート番号

### <a name="format"></a>フォーマット

2 文字の後に 6 桁の数字が続き、スペースまたは区切り記号は使用されません。

### <a name="pattern"></a>パターン

2 文字、その後に 6 桁の数字

### <a name="checksum"></a>チェックサム

該当なし

### <a name="definition"></a>定義

 DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_belgium_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_belgium_eu_passport_number` つかったか、検索されます。
- 正規表現は、DD MM YY 形式の日付を検索するか、検索 `Regex_eu_passport_date2` されたキーワード `Keywords_eu_passport_date` を `Keywords_belgium_eu_passport_number` 検索します。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_belgium_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_belgium_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Belgium Passport Number -->
      <Entity id="d7b1315b-21ca-4774-a32a-596010ff78fd" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
            <Match idRef="Keywords_belgium_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro パスポート
- paspoort nr
- paspoort-nr
- paspoortnummer
- paspoortnummers
- パスポート のデカルト
- パスポート livre
- Pass-Nr
- Passnummer
- reisepass kein

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付

## <a name="belgium-value-added-tax-number"></a>ベルギーの付加価値税番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

12 文字の英数字パターン

### <a name="pattern"></a>パターン

12 文字の英数字パターン:

- 文字 B または b
- E または e の文字
- 数字 0
- 1 ~ 9 の数字
- オプションのドットまたはハイフンまたはスペース
- 4 桁
- オプションのドットまたはハイフンまたはスペース
- 4 桁


### <a name="checksum"></a>チェックサム

はい


### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_belgium_value_added_tax_number一致するコンテンツを検索します。
- ユーザーのキーワードKeywords_belgium_value_added_tax_number見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_belgium_value_added_tax_number一致するコンテンツを検索します。

```xml
      <!-- Belgium Value Added Tax Number -->
      <Entity id="85b5b3c3-f2de-4ae8-ac46-fd3cb38bf9ed" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
          <Match idRef="Keywords_belgium_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
        </Pattern>
      </Entity>
    </Version>
```
### <a name="keywords"></a>キーワード

#### <a name="keyword_belgium_value_added_tax_number"></a>Keyword_belgium_value_added_tax_number

- nº tva
- vat 番号
- vat いいえ
- numéro t.v.a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- btw
- btw#
- vat#


## <a name="brazil-cpf-number"></a>ブラジルの CPF 番号

### <a name="format"></a>フォーマット

書式設定ありまたは書式設定なしのチェック ディジットを含む 11 桁の数字

### <a name="pattern"></a>パターン

書式設定:
- 3 桁の数字
- ピリオド
- 3 桁の数字
- ピリオド
- 3 桁の数字
- ハイフン
- チェックの数字である 2 桁の数字

Unformatted:
- 11 桁の数字 (最後の 2 桁はチェック ディジット)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_brazil_cpf一致するコンテンツを検索します。
- ユーザーからのキーワードKeyword_brazil_cpf見つかりました。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_brazil_cpf一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- CPF
- ID
- 登録
- 収益
- Cadastro de Pessoas Físicas
- Imposto
- Identificação
- Inscrição
- Receita


## <a name="brazil-legal-entity-number-cnpj"></a>ブラジルの法人番号 (CNPJ)

### <a name="format"></a>フォーマット

登録番号、枝番号、チェック ディジット、および区切り文字を含む 14 桁の数字

### <a name="pattern"></a>パターン

14 桁の数字と区切り文字:

- 2 桁
- ピリオド
- 3 桁の数字
- ピリオド
- 3 桁 (最初の 8 桁は登録番号です)
- スラッシュ
- 4 桁の分岐番号
- ハイフン
- チェックの数字である 2 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_brazil_cnpj一致するコンテンツを検索します。
- ユーザーからのキーワードKeyword_brazil_cnpj見つかりました。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_brazil_cnpj一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_brazil_cnpj"></a>Keyword_brazil_cnpj

- CNPJ
- CNPJ/MF
- CNPJ-MF
- National Registry of Legal Entities
- Taxpayers Registry
- Legal entity
- Legal entities
- Registration Status
- Business
- Company
- CNPJ
- Cadastro Nacional da Pessoa Jurídica
- Cadastro Geral de Contribuintes
- CGC
- Pessoa jurídica
- Pessoas jurídicas
- Situação cadastral
- Inscrição
- Empresa


## <a name="brazil-national-identification-card-rg"></a>ブラジルの国民識別カード (RG)

### <a name="format"></a>フォーマット

Registro Geral (旧形式): 9 桁

Registro de Identidade (RIC) (新しい形式): 11 桁

### <a name="pattern"></a>パターン

Registro Geral (従来の形式):
- 2 桁
- ピリオド
- 3 桁の数字
- ピリオド
- 3 桁の数字
- ハイフン
- チェックディジットである 1 桁の数字

Registro de Identidade (RIC) (新しい形式):
- 10 桁の数字
- ハイフン
- チェックディジットである 1 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_brazil_rg一致するコンテンツを検索します。
- ユーザーからのキーワードKeyword_brazil_rg見つかりました。
- チェックサムが渡される。


```xml
      <!-- Brazil National ID Card (RG) -->
      <Entity id="486de900-db70-41b3-a886-abdf25af119c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_brazil_rg" />
          <Match idRef="Keyword_brazil_rg" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Cédula de identidade
- Identity card
- national id
- número de rregistro
- registro de Iidentidade
- registro geral
- RG (このキーワードでは大文字と小文字が区別されます)
- RIC (このキーワードでは大文字と小文字が区別されます)


## <a name="bulgaria-drivers-license-number"></a>ブルガリアの運転免許証番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 9 桁の数字

### <a name="pattern"></a>パターン

9 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_bulgaria_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_bulgaria_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Bulgaria Driver's License Number -->
      <Entity id="66d39258-94c2-43b2-804b-aa312258e54b" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver's_license_number

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка
- шофьорски книжки

## <a name="bulgaria-uniform-civil-number"></a>ブルガリアの一様な民事番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースと区切り記号のない 10 桁の数字

### <a name="pattern"></a>パターン

スペースと区切り記号のない 10 桁の数字

- 生年月日に対応する 6 桁の数字 (YYMMDD)
- 出生順序に対応する 2 桁の数字
- 性別に対応する 1 桁の数字: 男性の偶数桁、女性の奇数桁
- 1 つのチェックディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_bulgaria_eu_national_id_card` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_bulgaria_eu_national_id_card` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数  `Func_bulgaria_eu_national_id_card` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Bulgaria Uniform Civil Number -->
      <Entity id="100d58b1-0a35-4fb1-aa89-e4a86fb53fcc" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_bulgaria_eu_telephone_number" />
            <Match idRef="Keywords_bulgaria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_bulgaria_eu_national_id_card"></a>Keywords_bulgaria_eu_national_id_card

- bnn#
- bnn
- bucn#
- bucn
- edinen grazhdanski nomer
- egn#
- egn
- identification number
- national id
- 国番号
- nationalnumber#
- nationalnumber
- 個人用 ID
- 個人のいいえ
- 個人番号
- personalidnumber#
- social security number
- ssn#
- ssn
- uniform civil id
- uniform civil no
- 一様な民事番号
- uniformcivilno#
- uniformcivilno
- uniformcivilnumber#
- uniformcivilnumber
- 一意の市民権番号
- егн#
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ ID
- униформ граждански ID
- униформ граждански не
- униформ граждански номер
- униформгражданскиid#
- униформгражданскине.#


## <a name="bulgaria-passport-number"></a>ブルガリアのパスポート番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 9 桁の数字

### <a name="pattern"></a>パターン

9 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_bulgaria_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_bulgaria_eu_passport_number` つかったか、検索されます。
- 正規表現が `Regex_eu_passport_date1` DD.MM.YYYYY 形式の日付を検索するか、キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_bulgaria_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_bulgaria_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Bulgaria Passport Number -->
      <Entity id="f7172b82-c588-4216-845e-4e54e397f29a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- паспортいいえ

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付

## <a name="canada-bank-account-number"></a>カナダの銀行口座番号

### <a name="format"></a>フォーマット

7 桁または 12 桁

### <a name="pattern"></a>パターン

カナダの銀行口座番号は 7 桁または 12 桁です。

カナダの銀行口座転送番号は次のとおりです。
- 5 桁
- ハイフン
- 3 桁の OR
- ゼロ "0"
- 8 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。
- Keyword_canada_bank_account_number のキーワードを検出した。
- 正規表現 Regex_canada_bank_account_transit_number がパターンに一致するコンテンツを検出した。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。
- Keyword_canada_bank_account_number のキーワードを検出した。

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_canada_bank_account_number"></a>Keyword_canada_bank_account_number

- canada savings bonds
- canada revenue agency
- canadian financial institution
- direct deposit form
- canadian citizen
- legal representative
- notary public
- commissioner for oaths
- child care benefit
- universal child care
- canada child tax benefit
- income tax benefit
- harmonized sales tax
- social insurance number
- income tax refund
- child tax benefit
- territorial payments
- institution number
- deposit request
- banking information
- direct deposit


## <a name="canada-drivers-license-number"></a>カナダの運転免許証番号

### <a name="format"></a>フォーマット

州によって異なります

### <a name="pattern"></a>パターン

カバーするさまざまなパターン:
- アルバータ州
- British Columbia
- マニトバ州
- New Brunswick
- Newfoundland/Labrador
- Nova Scotia
- Ontario
- Prince Edward Island
- ケベック州
- サスカチュワン州

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_[province_name]_drivers_license_number がパターンに一致するコンテンツを検出した。
- Keyword_[province_name]_drivers_license_name のキーワードを検出した。
- Keyword_canada_drivers_license のキーワードを検出した。

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_[province_name]_drivers_license_name

- 州の略号、AB など
- 州名 (Alberta など)

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- DL
- DLS
- CDL
- CDLS
- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Lics
- Driver License
- Driver Licenses
- Driver Licence
- Driver Licences
- DriversLic
- DriversLics
- DriversLicence
- DriversLicences
- DriversLicense
- DriversLicenses
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Drivers Licence
- Drivers Licences
- Driver'Lic
- Driver'Lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- Driver' Lic
- Driver' Lics
- Driver' License
- Driver' Licenses
- Driver' Licence
- Driver' Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's License
- Driver's Licenses
- Driver's Licence
- Driver's Licences
- Permis de Conduire
- id
- ids
- idcard number
- idcard numbers
- idcard #
- idcard #s
- idcard card
- idcard cards
- idcard
- identification number
- identification numbers
- identification #
- identification #s
- identification card
- identification cards
- ID
- DL#
- DLS#
- CDL#
- CDLS#
- DriverLic#
- DriverLics#
- DriverLicense#
- DriverLicenses#
- DriverLicence#
- DriverLicences#
- Driver Lic#
- Driver Lics#
- Driver License#
- Driver Licenses#
- Driver License#
- Driver Licences#
- DriversLic#
- DriversLics#
- DriversLicense#
- DriversLicenses#
- DriversLicence#
- DriversLicences#
- Drivers Lic#
- Drivers Lics#
- Drivers License#
- Drivers Licenses#
- Drivers Licence#
- Drivers Licences#
- Driver'Lic#
- Driver'Lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- Driver' Lic#
- Driver' Lics#
- Driver' License#
- Driver' Licenses#
- Driver' Licence#
- Driver' Licences#
- Driver'sLic#
- Driver'sLics#
- Driver'sLicense#
- Driver'sLicenses#
- Driver'sLicence#
- Driver'sLicences#
- Driver's Lic#
- Driver's Lics#
- Driver's License#
- Driver's Licenses#
- Driver's Licence#
- Driver's Licences#
- Permis de Conduire#
- id#
- ids#
- idcard card#
- idcard cards#
- idcard#
- identification card#
- identification cards#
- ID#


## <a name="canada-health-service-number"></a>カナダの正常性サービス番号

### <a name="format"></a>フォーマット

 10 桁の数字

### <a name="pattern"></a>パターン

10 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現 Regex_canada_health_service_number がパターンに一致するコンテンツを検出した。
- Keyword_canada_health_service_number のキーワードを検出した。

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_canada_health_service_number"></a>Keyword_canada_health_service_number

- personal health number
- patient information
- health services
- speciality services
- automobile accident
- patient hospital
- 精神科医
- workers compensation
- 障がい


## <a name="canada-passport-number"></a>カナダのパスポート番号

### <a name="format"></a>フォーマット

2 つの大文字と 6 桁の数字

### <a name="pattern"></a>パターン

2 つの大文字と 6 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現 Regex_canada_passport_number がパターンに一致するコンテンツを検出した。
- ユーザーまたはユーザーのKeyword_canada_passport_numberキーワードKeyword_passport見つかりました。

```xml
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_canada_passport_number"></a>Keyword_canada_passport_number

- canadian citizenship
- canadian passport
- passport application
- passport photos
- certified translator
- canadian citizens
- processing times
- renewal application

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport #
- Passport#
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- [万]Num
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- パスポート#
- PasseportNon
- Passeportn °


## <a name="canada-personal-health-identification-number-phin"></a>カナダの個人の健康識別番号 (PHIN)

### <a name="format"></a>フォーマット

9 桁

### <a name="pattern"></a>パターン

9 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現 Regex_canada_phin がパターンに一致するコンテンツを検出した。
- 2 つ以上のキーワードがKeyword_canada_phinまたはKeyword_canada_provinces見つかりました。

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_canada_phin"></a>Keyword_canada_phin

- social insurance number
- health information act
- income tax information
- manitoba health
- health registration
- prescription purchases
- benefit eligibility
- personal health
- power of attorney
- registration number
- personal health number
- practitioner referral
- wellness professional
- patient referral
- health and wellness

#### <a name="keyword_canada_provinces"></a>Keyword_canada_provinces

- Nunavut
- ケベック州
- Northwest Territories
- Ontario
- British Columbia
- アルバータ州
- サスカチュワン州
- マニトバ州
- ユーコン語
- Newfoundland and Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- カナダ


## <a name="canada-social-insurance-number"></a>カナダの社会保険番号

### <a name="format"></a>フォーマット

オプションのハイフンまたはスペースを含む 9 桁の数字

### <a name="pattern"></a>パターン

書式設定:
- 3 桁の数字
- ハイフンまたはスペース
- 3 桁の数字
- ハイフンまたはスペース
- 3 桁の数字

書式設定されていない: 9 桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数 Func_canadian_sin がパターンに一致するコンテンツを検出した。
- 次のパターンのうち少なくとも 2 つ。
    - Keyword_sin のキーワードを検出した。
    - Keyword_sin_collaborative のキーワードを検出した。
    - 関数 Func_eu_date が適切な日付形式の日付を検出した。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_unformatted_canadian_sin がパターンに一致するコンテンツを検出した。
- Keyword_sin のキーワードを検出した。
- チェックサムが渡される。

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_sin"></a>Keyword_sin

- sin
- social insurance
- numero d'assurance sociale
- 罪
- ssn
- ssns
- social security
- numero d'assurance social
- national identification number
- national id
- sin#
- soc ins
- social ins

#### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- driver's license
- drivers license
- driver's licence
- drivers licence
- DOB
- 誕生日
- Birthday
- Date of Birth


## <a name="chile-identity-card-number"></a>チリの ID カード番号

### <a name="format"></a>フォーマット

7 桁から 8 桁の数字と、チェック桁または文字の区切り記号

### <a name="pattern"></a>パターン

7 ~ 8 桁の数字と区切り記号:
- 1 桁から 2 桁の数字
- オプションの期間
- 3 桁の数字
- オプションの期間
- 3 桁の数字
- ダッシュ
- 1 桁または 1 文字 (大文字と小文字を区別しない) (チェック桁)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_chile_id_card一致するコンテンツを検索します。
- ユーザーからのキーワードKeyword_chile_id_card見つかりました。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_chile_id_card一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- cédula de identidad
- identificación
- national identification
- national identification number
- national id
- número de identificación nacional
- rol único nacional
- rol único tributario
- RUN
- RUT
- tarjeta de identificación
- Rol Unico Nacional
- Rol Unico Tributario
- RUN#
- RUT#
- nationaluniqueroleID#
- nacional identidad
- número identificación
- identidad número
- numero identificacion
- identidad numero
- チリの ID いいえ。
- チリの ID 番号
- チリの ID#
- 一意の税レジストリ
- 一意のトリビュートロール
- 一意の税の役割
- 一意の支流番号
- 一意の国番号
- 固有の国の役割
- 国内固有の役割
- チリの ID いいえ。
- チリの ID 番号
- チリの ID#
- R.U.T
- R.U.N


## <a name="china-resident-identity-card-prc-number"></a>中国在住の ID カード (PRC) 番号

### <a name="format"></a>フォーマット

18 桁の数字

### <a name="pattern"></a>パターン

18 桁の数字:
- アドレス コードである 6 桁の数字
- YYYYYMMDD という形式の 8 桁の数字 (生年月日)
- 注文コードである 3 桁の数字
- チェックディジットである 1 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_china_resident_id一致するコンテンツを検索します。
- ユーザーからのキーワードKeyword_china_resident_id見つかりました。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_china_resident_id一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

### <a name="keyword_china_resident_id"></a>Keyword_china_resident_id

- Resident Identity Card
- PRC
- National Identification Card
- 身份证
- 居民 身份证
- 居民身份证
- 鉴定
- 身分證
- 居民 身份證
- 鑑定


## <a name="credit-card-number"></a>クレジット カード番号

### <a name="format"></a>フォーマット

書式設定または書式設定されていない 14 ~ 19 桁の数字 (dddddddd

### <a name="pattern"></a>パターン

Visa、MasterCard、Discover Card、JCB、American Express、ギフト カード、ダイナーのカード、Rupay、China UnionPay など、世界中のすべての主要ブランドのカードを検出します。

### <a name="checksum"></a>チェックサム

はい、Luhn チェック

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数 Func_credit_card がパターンに一致するコンテンツを検出した。
- 次のいずれかの条件に該当する:
    - Keyword_cc_verification のキーワードを検出した。
    - このページのKeyword_cc_name見つかりました。
    - 関数 Func_expiration_date が適切な日付形式の日付を検出した。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- 関数 Func_credit_card がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_cc_verification"></a>Keyword_cc_verification

- card verification
- card identification number
- cvn
- cid
- cvc2
- cvv2
- pin block
- security code
- security number
- security no
- issue number
- issue no
- cryptogramme
- numéro de sécurité
- numero de securite
- kreditkartenprüfnummer
- kreditkartenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- cod。 sicurezza
- cod sicurezza
- n autorizzazione
- código
- codigo
- cod。 seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- 
cód. segurança
- cod. seguranca

- cod. segurança

- cód. seguranca
- cód segurança
- cod seguranca
- cod segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- data scad
- fecha de expiracion
- fecha de venc
- vencimiento
- válido hasta
- valido hasta
- vto
- data de expiração
- data de expiracao
- data em que expira
- validade
- valor
- vencimento
- トランザクション
- トランザクション番号
- 参照番号
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- amex
- american express
- americanexpress
- americano espresso
- Visa
- mastercard
- master card
- mc
- mastercards
- master cards
- diner's Club
- diners club
- dinersclub
- discover
- discover card
- discovercard
- discover cards
- JCB
- BrandSmart
- japanese card bureau
- carte blanche
- carteblanche
- credit card
- cc#
- cc#:
- expiration date
- exp date
- expiry date
- date d’expiration
- date d'exp
- date expiration
- bank card
- bankcard
- card number
- card num
- cardnumber
- cardnumbers
- card numbers
- クレジット カード
- credit cards
- クレジット カード
- ccn
- card holder
- cardholder
- card holders
- カード所有者
- check card
- checkcard
- check cards
- checkcards
- debit card
- デビットカード
- debit cards
- デビットカード
- atm card
- atmcard
- atm cards
- atmcards
- enroute
- en route
- card type
- Cardmember Acct
- cardmember アカウント
- Cardno
- コーポレート カード
- 企業カード
- カードの種類
- カード アカウント番号
- カード メンバー アカウント
- Cardmember Acct.
- card no.
- カードなし
- card number
- carte bancaire
- carte de crédit
- carte de credit
- numéro de carte
- numero de carte
- nº de la carte
- nº de carte
- kreditkarte
- karte
- karteninhaber
- karteninhabers
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
- carta di credito
- carta credito
- n. carta
- n carta
- nr. carta
- nr carta
- numero carta
- numero della carta
- numero di carta
- tarjeta credito
- tarjeta de credito
- tarjeta crédito
- tarjeta de crédito
- tarjeta de atm
- tarjeta atm
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- nº de tarjeta
- 違います。 de tarjeta
- no de tarjeta
- numero de tarjeta
- número de tarjeta
- tarjeta no
- tarjetahabiente
- cartão de crédito
- cartão de credito
- cartao de crédito
- cartao de credito
- cartão de débito
- cartao de débito
- cartão de debito
- cartao de debito
- débito automático
- debito automatico
- número do cartão
- numero do cartão
- número do cartao
- numero do cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- nº do cartão
- nº do cartao
- nº。 do cartão
- no do cartão
- no do cartao
- 違います。 do cartão
- no. do cartao

- rupay
- 労働組合の支払い
- unionpay
- diner's
- ダイナー
- クレジットカード番号
- クレジットカードナンバー
- クレジットカード＃
- クレジットカード
- クレジット
- クレカ
- カード番号
- カードナンバー
- カード＃
- アメックス
- アメリカンエクスプレス
- アメリカン エクスプレス
- Visa カード
- Visa カード
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード
- 中国银联
- 银联



## <a name="croatia-drivers-license-number"></a>クロアチアの運転免許証番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 8 桁の数字

### <a name="pattern"></a>パターン

8 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。

- 正規表現は、  `Regex_croatia_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見 `Keywords_eu_driver's_license_number` `Keywords_croatia_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Croatia Driver's License Number -->
      <Entity id="005b3ef1-47dd-4e68-bb02-c6db484d00f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_croatia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver's_license_number

- vozačka dozvola
- vozačke dozvole


## <a name="croatia-identity-card-number"></a>クロアチアの ID カード番号
このエンティティは、EU の国民識別番号の機密情報の種類に含まれています。 スタンドアロンの機密情報の種類エンティティとして使用できます。

### <a name="format"></a>フォーマット

9 桁

### <a name="pattern"></a>パターン

9 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_croatia_id_card一致するコンテンツを検索します。
- ユーザーのキーワードKeyword_croatia_id_card見つかりました。

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- majstorski broj građana
- マスター市民番号
- nacionalni identifikacijski broj
- national identification number
- oib#
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- 個人識別番号
- porezni broj
- porezni identifikacijski broj
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#


## <a name="croatia-passport-number"></a>クロアチアのパスポート番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 9 桁の数字

### <a name="pattern"></a>パターン

9 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_croatia_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_croatia_eu_passport_number` つかったか、検索されます。
- 正規表現が `Regex_eu_passport_date1` DD.MM.YYYYY 形式の日付を検索するか、キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_croatia_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_croatia_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Croatia Passport Number -->
      <Entity id="7d7a729d-32d8-4204-8d01-d5e6a6c25581" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putovnice
- br。 Putovnice
- br putovnice

## <a name="croatia-personal-identification-oib-number"></a>クロアチアの個人識別 (OIB) 番号

### <a name="format"></a>フォーマット

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の数字:
- 10 桁の数字
- 最終桁はチェック桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_croatia_oib_number一致するコンテンツを検索します。
- このページのKeywords_croatia_eu_tax_file_numberが見つかりました。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_croatia_oib_number一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
      <!-- Croatia Personal Identification (OIB) Number -->
      <Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_oib_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_oib_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- majstorski broj građana
- マスター市民番号
- nacionalni identifikacijski broj
- national identification number
- oib#
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- 個人識別番号
- porezni broj
- porezni identifikacijski broj
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#

## <a name="cyprus-drivers-license-number"></a>キプロスのドライバーのライセンス番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 12 桁の数字

### <a name="pattern"></a>パターン

12 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_cyprus_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_cyprus_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Cyprus Driver's License Number -->
      <Entity id="356fa104-f9ac-4aff-a0e4-2e6e65ea06c4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver's_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>キプロスの ID カード
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースと区切り記号のない 10 桁の数字

### <a name="pattern"></a>パターン

10 桁の数字

### <a name="checksum"></a>チェックサム

該当なし

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_cyprus_eu_national_id_card` パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_cyprus_eu_national_id_card` 見つかりました。

```xml
      <!-- Cyprus Identity Card -->
      <Entity id="3ba8afe5-7a6c-4929-8247-0001b6878438" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- ID カード番号
- ID カード番号
- kimlik karti
- national identification number
- 個人用 ID 番号
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>キプロスのパスポート番号

### <a name="format"></a>フォーマット

1 文字の後に 6 ~ 8 桁の数字が続き、スペースや区切り記号はありません。

### <a name="pattern"></a>パターン

1 文字の後に 6 ~ 8 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_cyprus_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_cyprus_eu_passport_number` つかったか、検索されます。
- 正規表現が `Regex_cyprus_eu_passport_date` DD/MM/YYYYY 形式の日付を検索するか、キーワードが `Keywords_cyprus_eu_passport_date` 見つかった

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_cyprus_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_cyprus_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Cyprus Passport Number -->
      <Entity id="9193e2e8-7f8c-43c1-a274-ac40d651936f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_cyprus_eu_passport_date" />
            <Match idRef="Keywords_cyprus_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- αριθμό διαβατηρίου
- pasaportu
- Αριθμός Διαβατηρίου
- κυπριακό διαβατήριο
- διαβατήριο#
- διαβατήριο
- αριθμός διαβατηρίου
- Pasaport Kimliği
- pasaport numarası
- Pasaport no.
- Αρ. Διαβατηρίου

#### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- 有効期限が切れる
- 発行日


## <a name="cyprus-tax-identification-number"></a>キプロスの税金の識別番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

指定したパターンの 8 桁の数字と 1 文字

### <a name="pattern"></a>パターン

8 桁の数字と 1 文字:

- "0" または "9"
- 7 桁
- 1 文字 (大文字と小文字は区別されません)

### <a name="checksum"></a>チェックサム

該当なし

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_cyprus_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_cyprus_eu_tax_file_number` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数  `Func_cyprus_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Cyprus Tax Identification Number -->
      <Entity id="40e64bd9-55f3-4a09-9bd6-1db18dced9dd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

- tax id
- 税の識別コード
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tic#
- tic
- tin id
- tin いいえ
- tin#
- vergi kimlik kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>チェコの運転免許証番号

### <a name="format"></a>フォーマット

2 文字の後に 6 桁の数字が続く

### <a name="pattern"></a>パターン

8 文字と数字:

- レター 'E' (大文字と小文字は区別されません)
- レター
- スペース (オプション)
- 6 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_czech_republic_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_czech_republic_eu_driver's_license_number` つかったか、検索されます。

```xml
      <Entity id="86b40d3b-d8ea-4c36-aab0-ef9416a6769c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver's_license_number

- řidičský prúkaz
- řidičské prčkazy
- číslo řidičského prčkazu
- čísla řidičských prčkazů


## <a name="czech-passport-number"></a>チェコのパスポート番号

### <a name="format"></a>フォーマット

スペースまたは区切り記号のない 8 桁の数字

### <a name="pattern"></a>パターン

スペースまたは区切り記号のない 8 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_czech_republic_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_czech_republic_eu_passport_number` つかったか、検索されます。
- 正規表現が `Regex_eu_passport_date1` DD.MM.YYYYY 形式の日付を検索するか、キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_czech_republic_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_czech_republic_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Czech Republic Passport Number -->
      <Entity id="7bcd8ce8-5e92-4bbe-bc92-fa669f0369fa" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- cestovní pas
- číslo pasu
- cestovní pasu
- passeport no
- čísla pasu

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="czech-personal-identity-number"></a>チェコの個人 ID 番号

### <a name="format"></a>フォーマット

オプションのスラッシュ付き 9 桁 (古い形式) 10 桁 、オプションのスラッシュ (新しい形式)

### <a name="pattern"></a>パターン

9 桁 (古い形式):
- 生年月日を表す 6 桁の数字
- オプションのスラッシュ
- 3 桁の数字

10 桁 (新しい形式):
- 生年月日を表す 6 桁の数字
- オプションのスラッシュ
- 最後の数字がチェック桁である 4 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。

- この関数はFunc_czech_id_card一致するコンテンツを検索します。
- ユーザーからのキーワードKeyword_czech_id_card見つかりました。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。

- この関数Func_czech_id_card_new_format一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- Czech Personal Identity Number -->
      <!-- Czech Personal Identity Number -->
      <Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_id_card" />
          <Match idRef="Keyword_czech_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.3000.000">
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Func_czech_id_card_new_format" />
          </Pattern>
        </Version>
      </Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keyword_czech_id_card"></a>Keyword_czech_id_card

- 出生番号
- チェコ共和国 ID
- czechidno#
- daňové číslo
- identifikační číslo
- ID なし
- ID 番号
- identityno#
- identityno
- 保険番号
- national identification number
- nationalnumber#
- 国番号
- osobní číslo
- personalidnumber#
- 個人用 ID 番号
- 個人識別番号
- 個人番号
- pid#
- pid
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- ssn
- ssn#
- social security number
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#
- 一意の ID 番号


## <a name="denmark-drivers-license-number"></a>デンマークの運転免許証番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 8 桁の数字

### <a name="pattern"></a>パターン

8 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_denmark_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_denmark_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Denmark Driver's License Number -->
      <Entity id="98a95812-6203-451a-a220-d39870ebef0e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_denmark_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver's_license_number

- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>デンマークのパスポート番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 9 桁の数字

### <a name="pattern"></a>パターン

9 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_denmark_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_denmark_eu_passport_number` つかったか、検索されます。
- 正規表現が DD MM YY 形式の日付を検索するか、キーワード `Regex_eu_passport_date2` が `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_denmark_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_denmark_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Denmark Passport Number -->
      <Entity id="25e8c47e-e6fe-4884-a211-74898f8c0196" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- パスポート n°
- pasnumre

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="denmark-personal-identification-number"></a>デンマークの個人識別番号

### <a name="format"></a>フォーマット

ハイフンを 1 つ含む 10 桁の数字

### <a name="pattern"></a>パターン

10 桁の数字:
- DDMMYY 形式の 6 桁の数字 (生年月日)
- オプションのスペースまたはハイフン
- 最後の数字がチェック桁である 4 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、Func_denmark_eu_tax_file_number一致するコンテンツを検索します。
- ユーザーのキーワードKeyword_denmark_id見つかりました。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- 正規表現は、Func_denmark_eu_tax_file_number一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- Denmark Personal Identification Number -->
    <!-- Denmark Personal Identification Number -->
      <Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keyword_denmark_id" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personregister
- civilt registreringssystem
- cpr
- cpr#
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- 正常性カード
- 健康保険証番号
- 健康保険番号
- identification number
- identifikationsnummer
- identifikationsnummer#
- ID 番号
- krankenkassennummer
- nationalid#
- nationalnumber#
- 国番号
- personalidnumber#
- personalidentityno#
- 個人用 ID 番号
- personnummer
- personnummer#
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- ssn
- ssn#
- スケート ID
- スケート kode
- スケートのしびれ
- skattenummer
- social security number
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- 税コード
- 旅行健康保険証
- uniqueidentityno#
- 税番号
- 税登録番号
- tax id
- 税の識別番号
- タクシー#
- taxnumber#
- tax no
- taxno#
- taxnumber
- 税の識別なし
- tin#
- taxidno#
- taxidnumber#
- tax no#
- tin id
- tin いいえ
- cpr.nr
- cprnr
- cprnummer
- personnr
- personregister
- sygesikringsbevis
- sygesikringsbevisnr
- sygesikringsbevisnummer
- sygesikringskort
- sygesikringskortnr
- sygesikringskortnummer
- sygesikringsnr
- sygesikringsnummer


## <a name="drug-enforcement-agency-dea-number"></a>麻薬取締局 (DEA) 番号

### <a name="format"></a>フォーマット

2 文字の後に 7 桁の数字を付け

### <a name="pattern"></a>パターン

パターンには、以下のすべてが含まれる必要があります。
- 可能な文字のこのセットからの 1 文字 (大文字と小文字は区別されません): abcdefghjklmnprstux (レジストリ コード)
- 1 文字 (大文字と小文字を区別しない) (登録者の名または数字 '9' の最初の文字)
- 7 桁の数字で、最後の数字はチェック桁です。

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数 Func_dea_number がパターンに一致するコンテンツを検出した。
- キーワードが `Keyword_dea_number` 見つかりました
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_dea_number がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
    <!-- DEA Number -->
    <Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_dea_number" />
      </Pattern>
      <Version minEngineVersion="15.20.1207.000" maxEngineVersion="15.20.3134.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
        </Pattern>
      </Version>
      <Version minEngineVersion="15.20.3135.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
          <Match idRef="Keyword_dea_number" />
        </Pattern>
      </Version>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_dea_number"></a>Keyword_dea_number

- dea
- dea#
- 麻薬取締局
- 麻薬取締局


## <a name="estonia-drivers-license-number"></a>エストニアの運転免許証番号

### <a name="format"></a>フォーマット

2 文字の後に 6 桁の数字が続く

### <a name="pattern"></a>パターン

2 文字と 6 桁の数字:

- 文字 "ET" (大文字と小文字は区別されません)
- 6 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_estonia_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_estonia_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Estonia Driver's License Number -->
      <Entity id="51da8171-da70-4cc1-9d65-055a59ca4f83" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_estonia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver's_license_number

- permis de conduire
- juhilubade numbrid
- juhiloa 番号
- juhiluba

## <a name="estonia-personal-identification-code"></a>エストニアの個人識別コード

この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースと区切り記号のない 11 桁の数字

### <a name="pattern"></a>パターン

11 桁の数字:

- 性別と出生世紀に対応する 1 桁の数字 (奇数男性、偶数女性、1-2:19 世紀、3-4: 20 世紀、5~6:21 世紀)
- 生年月日 (YYMMDD) に対応する 6 桁の数字
- 同じ日付に生まれた人を区切るシリアル番号に対応する 3 桁の数字
- 1 つのチェックディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_estonia_eu_national_id_card` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_estonia_eu_national_id_card` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数  `Func_estonia_eu_national_id_card` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Estonia Personal Identification Code -->
      <Entity id="bfb26de6-dad5-4d48-ab72-4789cdd0654c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_estonia_eu_telephone_number" />
            <Match idRef="Keywords_estonia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- id-kaart
- ik
- isikukood#
- isikukood
- maksu id
- maksukohustuslase identifitseerimisnumber
- maksunumber
- national identification number
- 国番号
- 個人用コード
- 個人用 ID 番号
- 個人識別コード
- 個人識別番号
- personalidnumber#
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#


## <a name="estonia-passport-number"></a>エストニアのパスポート番号

### <a name="format"></a>フォーマット

1 文字の後にスペースまたは区切り記号を付けない 7 桁の数字

### <a name="pattern"></a>パターン

1 文字の後に 7 桁の数字が続く

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_estonia_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_estonia_eu_passport_number` つかったか、検索されます。
- 正規表現が `Regex_eu_passport_date1` DD.MM.YYYYY 形式の日付を検索するか、キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_estonia_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_estonia_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Estonia Passport Number -->
      <Entity id="61f7073a-509e-425b-a754-bc01bb5d5b8c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti kodaniku passi number passinumbrid document number document no dokumendi nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="eu-debit-card-number"></a>EU のデビット カード番号

### <a name="format"></a>フォーマット

16 桁の数字

### <a name="pattern"></a>パターン

複雑で堅牢なパターン

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数 Func_eu_debit_card がパターンに一致するコンテンツを検出した。
- 次の条件のうち 1 つ以上に該当する:
    - Keyword_eu_debit_card のキーワードを検出した。
    - Keyword_card_terms_dict のキーワードを検出した。
    - Keyword_card_security_terms_dict のキーワードを検出した。
    - Keyword_card_expiration_terms_dict のキーワードを検出した。
    - 関数 Func_expiration_date が適切な日付形式の日付を検出した。
- チェックサムが渡される。

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_eu_debit_card"></a>Keyword_eu_debit_card

- account number
- card number
- card no.
- security number
- cc#

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- acct nbr
- acct num
- acct no
- american express
- americanexpress
- americano espresso
- amex
- atm card
- atm cards
- atm kaart
- atmcard
- atmcards
- atmkaart
- atmkaarten
- bancontact
- bank card
- bankkaart
- card holder
- card holders
- card num
- card number
- card numbers
- card type
- cardano numerico
- cardholder
- カード所有者
- cardnumber
- cardnumbers
- carta bianca
- carta credito
- carta di credito
- cartao de credito
- cartao de crédito
- cartao de debito
- cartao de débito
- carte bancaire
- carte blanche
- carte bleue
- carte de credit
- carte de crédit
- carte di credito
- carteblanche
- cartão de credito
- cartão de crédito
- cartão de debito
- cartão de débito
- cb
- ccn
- check card
- check cards
- checkcard
- checkcards
- chequekaart
- cirrus
- cirrus-edc-maestro
- controlekaart
- controlekaarten
- credit card
- credit cards
- クレジット カード
- クレジット カード
- debetkaart
- debetkaarten
- debit card
- debit cards
- デビットカード
- デビットカード
- debito automatico
- diners club
- dinersclub
- discover
- discover card
- discover cards
- discovercard
- discovercards
- débito automático
- edc
- eigentümername
- european debit card
- hoofdkaart
- hoofdkaarten
- in viaggio
- japanese card bureau
- japanse kaartdienst
- jcb
- kaart
- kaart num
- kaartaantal
- kaartaantallen
- kaarthouder
- kaarthouders
- karte
- karteninhaber
- karteninhabers
- kartennr
- kartennummer
- kreditkarte
- kreditkarten-nummer
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartennummer
- kreditkartentyp
- maestro
- master card
- master cards
- mastercard
- mastercards
- mc
- mister cash
- n carta
- carta
- no de tarjeta
- no do cartao
- no do cartão
- no. de tarjeta

- no. do cartao

- no. do cartão

- nr carta
- nr. carta

- numeri di scheda
- numero carta
- numero de cartao
- numero de carte
- numero de cartão
- numero de tarjeta
- numero della carta
- numero di carta
- numero di scheda
- numero do cartao
- numero do cartão
- numéro de carte
- nº carta
- nº de carte
- nº de la carte
- nº de tarjeta
- nº do cartao
- nº do cartão
- nº. do cartão

- número de cartao
- número de cartão
- número de tarjeta
- número do cartao
- scheda dell'assegno
- scheda dell'atmosfera
- scheda dell'atmosfera
- scheda della banca
- scheda di controllo
- scheda di debito
- scheda matrice
- schede dell'atmosfera
- schede di controllo
- schede di debito
- schede matrici
- scoprono la scheda
- scoprono le schede
- ソロ
- supporti di scheda
- supporto di scheda
- スイッチ
- tarjeta atm
- tarjeta credito
- tarjeta de atm
- tarjeta de credito
- tarjeta de debito
- tarjeta debito
- tarjeta no
- tarjetahabiente
- tipo della scheda
- ufficio giapponese della
- scheda
- v pay
- v-pay
- visa
- visa plus
- visa electron
- visto
- visum
- vpay

#### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

- card identification number
- card verification
- cardi la verifica
- cid
- cod seg
- cod seguranca
- cod segurança
- cod sicurezza
- cod. seg

- cod. seguranca

- cod. segurança

- cod. sicurezza

- codice di sicurezza
- codice di verifica
- codigo
- codigo de seguranca
- codigo de segurança
- crittogramma
- cryptogram
- cryptogramme
- cv2
- cvc
- cvc2
- cvn
- cvv
- cvv2
- cód seguranca
- cód segurança
- cód. seguranca

- cód. segurança

- código
- código de seguranca
- código de segurança
- de kaart controle
- geeft nr uit
- issue no
- issue number
- kaartidentificatienummer
- kreditkartenprufnummer
- kreditkartenprüfnummer
- kwestieaantal
- no. dell'edizione

- no. di sicurezza

- numero de securite
- numero de verificacao
- numero dell'edizione
- numero di identificazione della
- scheda
- numero di sicurezza
- numero van veiligheid
- numéro de sécurité
- nº autorizzazione
- número de verificação
- perno il blocco
- pin block
- prufziffer
- prüfziffer
- security code
- security no
- security number
- sicherheits kode
- sicherheitscode
- sicherheitsnummer
- speldblok
- veiligheid nr
- veiligheidsaantal
- veiligheidscode
- veiligheidsnummer
- verfalldatum

#### <a name="keyword_card_expiration_terms_dict"></a>Keyword_card_expiration_terms_dict

- ablauf
- data de expiracao
- data de expiração
- data del exp
- data di exp
- data di scadenza
- data em que expira
- data scad
- data scadenza
- date de validité
- datum afloop
- datum van exp
- de afloop
- espira
- espira
- exp date
- exp datum
- 有効期限
- 有効期限
- 有効期限
- 有効期限
- fecha de expiracion
- fecha de venc
- gultig bis
- gultigkeitsdatum
- gültig bis
- gültigkeitsdatum
- la scadenza
- scadenza
- valable
- validade
- valido hasta
- valor
- venc
- vencimento
- vencimiento
- verloopt
- vervaldag
- vervaldatum
- vto
- válido hasta


## <a name="eu-drivers-license-number"></a>EU の運転免許証番号

これらのエンティティは EU の運転免許証番号に含み、機密情報の種類です。

- [Austria](#austria-drivers-license-number)
- [Belgium](#belgium-drivers-license-number)
- [ブルガリア](#bulgaria-drivers-license-number)
- [Croatia](#croatia-drivers-license-number)
- [キプロス](#cyprus-drivers-license-number)
- [チェコ語](#czech-drivers-license-number)
- [デンマーク](#denmark-drivers-license-number)
- [エストニア](#estonia-drivers-license-number)
- [フィンランド](#finland-drivers-license-number)
- [France](#france-drivers-license-number)
- [Germany](#germany-drivers-license-number)
- [ギリシャ](#greece-drivers-license-number)
- [ハンガリー](#hungary-drivers-license-number)
- [アイルランド](#ireland-drivers-license-number)
- [イタリア](#italy-drivers-license-number)
- [ラトビア](#latvia-drivers-license-number)
- [Lithuania](#lithuania-drivers-license-number)
- [ルクセンブルク](#luxemburg-drivers-license-number)
- [マルタ](#malta-drivers-license-number)
- [オランダ](#netherlands-drivers-license-number)
- [ポーランド](#poland-drivers-license-number)
- [Portugal](#portugal-drivers-license-number)
- [ルーマニア](#romania-drivers-license-number)
- [スロバキア](#slovakia-drivers-license-number)
- [スロベニア](#slovenia-drivers-license-number)
- [スペイン](#spain-drivers-license-number)
- [スウェーデン](#sweden-drivers-license-number)
- [英国](#uk-drivers-license-number)


## <a name="eu-national-identification-number"></a>EU の国民識別番号

これらのエンティティは EU の国民識別番号に含め、機密情報の種類です。

- [Austria](#austria-identity-card)
- [Belgium](#belgium-national-number)
- [ブルガリア](#bulgaria-uniform-civil-number)
- [Croatia](#croatia-identity-card-number)
- [キプロス](#cyprus-identity-card)
- [チェコ語](#czech-personal-identity-number)
- [デンマーク](#denmark-personal-identification-number)
- [エストニア](#estonia-personal-identification-code)
- [フィンランド](#finland-national-id)
- [France](#france-national-id-card-cni)
- [Germany](#germany-identity-card-number)
- [ギリシャ](#greece-national-id-card)
- [ハンガリー](#hungary-personal-identification-number)
- [アイルランド](#ireland-personal-public-service-pps-number)
- [イタリア](#italy-fiscal-code)
- [ラトビア](#latvia-personal-code)
- [Lithuania](#lithuania-personal-code)
- [ルクセンブルク](#luxemburg-national-identification-number-natural-persons)
- [マルタ](#malta-identity-card-number)
- [オランダ](#netherlands-citizens-service-bsn-number)
- [ポーランド](#poland-national-id-pesel)
- [Portugal](#portugal-citizen-card-number)
- [ルーマニア](#romania-personal-numeric-code-cnp)
- [スロバキア](#slovakia-personal-number)
- [スロベニア](#slovenia-unique-master-citizen-number)
- [スペイン](#spain-dni)
- [英国](#uk-national-insurance-number-nino)


## <a name="eu-passport-number"></a>EU パスポート番号

これらのエンティティは EU パスポート番号に含め、機密情報の種類です。 これらのエンティティは、EU パスポート番号バンドルに含まれています。

- [Austria](#austria-passport-number)
- [Belgium](#belgium-passport-number)
- [ブルガリア](#bulgaria-passport-number)
- [Croatia](#croatia-passport-number)
- [キプロス](#cyprus-passport-number)
- [チェコ語](#czech-passport-number)
- [デンマーク](#denmark-passport-number)
- [エストニア](#estonia-passport-number)
- [フィンランド](#finland-passport-number)
- [France](#france-passport-number)
- [Germany](#germany-passport-number)
- [ギリシャ](#greece-passport-number)
- [ハンガリー](#hungary-passport-number)
- [アイルランド](#ireland-passport-number)
- [イタリア](#italy-passport-number)
- [ラトビア](#latvia-passport-number)
- [Lithuania](#lithuania-passport-number)
- [ルクセンブルク](#luxemburg-passport-number)
- [マルタ](#malta-passport-number)
- [オランダ](#netherlands-passport-number)
- [ポーランド](#poland-passport-number)
- [Portugal](#portugal-passport-number)
- [ルーマニア](#romania-passport-number)
- [スロバキア](#slovakia-passport-number)
- [スロベニア](#slovenia-passport-number)
- [スペイン](#spain-passport-number)
- [スウェーデン](#sweden-passport-number)
- [英国](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>EU 社会保障番号または同等の ID

EU 社会保障番号または同等の ID に含み、機密情報の種類であるこれらのエンティティ。

- [Austria](#austria-social-security-number)
- [Belgium](#belgium-national-number)
- [Croatia](#croatia-personal-identification-oib-number)
- [チェコ語](#czech-personal-identity-number)
- [デンマーク](#denmark-personal-identification-number)
- [フィンランド](#finland-national-id)
- [France](#france-social-security-number-insee)
- [Germany](#germany-identity-card-number)
- [ギリシャ](#greece-national-id-card)
- [ハンガリー](#hungary-social-security-number-taj)
- [Portugal](#portugal-citizen-card-number)
- [スペイン](#spain-social-security-number-ssn)
- [スウェーデン](#sweden-national-id)


## <a name="eu-tax-identification-number"></a>EU 税の識別番号

これらのエンティティは、EU 税の識別番号の機密情報の種類です。

- [Austria](#austria-tax-identification-number)
- [Belgium](#belgium-national-number)
- [ブルガリア](#bulgaria-uniform-civil-number)
- [Croatia](#croatia-identity-card-number)
- [キプロス](#cyprus-tax-identification-number)
- [チェコ語](#czech-personal-identity-number)
- [デンマーク](#denmark-personal-identification-number)
- [エストニア](#estonia-personal-identification-code)
- [フィンランド](#finland-national-id)
- [France](#france-tax-identification-number)
- [Germany](#germany-tax-identification-number)
- [ギリシャ](#greece-tax-identification-number)
- [ハンガリー](#hungary-tax-identification-number)
- [アイルランド](#ireland-personal-public-service-pps-number)
- [イタリア](#italy-fiscal-code)
- [ラトビア](#latvia-personal-code)
- [Lithuania](#lithuania-personal-code)
- [ルクセンブルク](#luxemburg-national-identification-number-non-natural-persons)
- [マルタ](#malta-tax-identification-number)
- [オランダ](#netherlands-tax-identification-number)
- [ポーランド](#poland-tax-identification-number)
- [Portugal](#portugal-tax-identification-number)
- [ルーマニア](#romania-personal-numeric-code-cnp)
- [スロバキア](#slovakia-personal-number)
- [スロベニア](#slovenia-tax-identification-number)
- [スペイン](#spain-tax-identification-number)
- [スウェーデン](#sweden-tax-identification-number)
- [英国](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>フィンランドの運転免許証番号

### <a name="format"></a>フォーマット

ハイフンを 1 つ含む 10 桁の数字

### <a name="pattern"></a>パターン

ハイフンを含む 10 桁の数字:

- 6 桁
- ハイフン
- 3 桁の数字
- 数字または文字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_finland_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_finland_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Finland Driver's License Number -->
      <Entity id="bb3b27a3-79bd-4ac4-81a7-f9fca3c7d1a7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_finland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver's_license_number

- ajokortti
- permis de conduire
- ajokortin numero
- kuljettaja lic.
- körkort
- körkortnummer
- förare lic.
- ajokortit
- ajokortin numerot


## <a name="finland-european-health-insurance-number"></a>フィンランド のヨーロッパの健康保険番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

20 桁の番号

### <a name="pattern"></a>パターン

20 桁の番号:

- 10 桁 - 8024680246
- オプションのスペースまたはハイフン
- 10 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現はRegex_Finland_European_Health_Insurance_Number一致するコンテンツを検索します。
- ユーザーのキーワードKeyword_Finland_European_Health_Insurance_Number見つかりました。

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- ehic#
- ehic
- フィンランド語#
- finska sjukförsäkringskort
- 正常性カード
- 健康保険証
- 健康保険番号
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsäkring nummer
- sjukförsäkringskort
- suomen sairausvakuutuskortti
- terveyskortti


## <a name="finland-national-id"></a>フィンランドの国民 ID

### <a name="format"></a>フォーマット

6 桁の数字と、1 世紀と 3 桁の数字とチェック桁を示す文字

### <a name="pattern"></a>パターン

パターンには、以下のすべてが含まれる必要があります。
- DDMMYY という形式の 6 桁の数字 (生年月日)
- century マーカー ('-','+' または 'a')
- 3 桁の個人識別番号
- チェック桁である数字または文字 (大文字と小文字を区別しない)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- パターンにFunc_finnish_national_id一致するコンテンツを検索する関数
- 見つかったKeyword_finnish_national_idキーワード
- チェックサム パス

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- パターンにFunc_finnish_national_id一致するコンテンツを検索する関数
- チェックサム パス

```xml
      <!-- Finnish National ID-->
      <Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finnish_national_id" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero#
- henkilötunnusnumero
- hetu
- id no
- id 番号
- identification number
- identiteetti numero
- ID 番号
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- 国の ID カード
- national id no.
- 個人用 ID
- 個人 ID コード
- personalidnumber#
- personbeteckning
- personnummer
- social security number
- sosiaaliturvatunnus
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>フィンランドのパスポート番号

このエンティティは、EU Passport Number 機密情報の種類で使用できます。スタンドアロンの機密情報の種類エンティティとして使用できます。

### <a name="format"></a>フォーマット
9 つの文字と数字の組み合わせ

### <a name="pattern"></a>パターン
9 つの文字と数字の組み合わせ:
- 2 文字 (大文字と小文字は区別されません)
- 7 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、 `Regex_finland_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見 `Keywords_eu_passport_number` `Keyword_finland_passport_number` つかったか、検索されます。
- 正規表現が `Regex_eu_passport_date1` DD.MM.YYYYY 形式の日付を検索するか、キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、 `Regex_finland_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見 `Keywords_eu_passport_number` `Keyword_finland_passport_number` つかったか、検索されます。

```xml
      <!-- Finland Passport Number -->
      <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suomalainen passi
- passin numero
- passin numero.#
- passin numero#
- passin numero.
- passi#
- passi 番号

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付

## <a name="france-drivers-license-number"></a>フランスの運転免許証番号

このエンティティは、EU ドライバーのライセンス番号の機密情報の種類で使用できます。スタンドアロンの機密情報の種類エンティティとして使用できます。

### <a name="format"></a>フォーマット

12 桁の数字

### <a name="pattern"></a>パターン

フランスの電話番号などの同様のパターンと区別するための検証付きの 12 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_french_drivers_license一致するコンテンツを検索します。
- 検索されたKeyword_french_drivers_licenseが見つかりました。

```xml
    <!-- France Driver's License Number -->
    <Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Match idRef="Keyword_french_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers
- numéros de ライセンス


## <a name="france-health-insurance-number"></a>フランスの健康保険番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

21 桁の番号

### <a name="pattern"></a>パターン

21 桁の番号:

- 10 桁の数字
- オプションのスペース
- 10 桁の数字
- オプションのスペース
- 数字


### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現はRegex_France_Health_Insurance_Number一致するコンテンツを検索します。
- 検索されたKeyword_France_Health_Insurance_Numberが見つかりました。

```xml
      <!-- France Health Insurance Number -->
      <Entity id="9bc2069e-76df-4ff9-ac02-2f519469e236" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_France_Health_Insurance_Number"/>
          <Match idRef="Keyword_France_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keyword_france_health_insurance_number"></a>Keyword_France_health_insurance_number

- 保険証
- デカルトバイタル
- デカルト d'assuré social


## <a name="france-national-id-card-cni"></a>フランスの国民 ID カード (CNI)

### <a name="format"></a>フォーマット

12 桁の数字

### <a name="pattern"></a>パターン

12 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- 正規表現 Regex_france_cni がパターンに一致するコンテンツを検出した。
- このページのKeywords_france_eu_national_id_cardが見つかりました。

```xml
    <!-- France CNI -->
    <Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
        <Match idRef="Keywords_france_eu_national_id_card" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_france_eu_national_id_card"></a>Keywords_france_eu_national_id_card

- card number
- デカルト nationale d'identité
- デカルト nationale d'idenite no
- cni#
- cni
- compte bancaire
- national identification number
- 国の ID
- nationalidno#
- numéro d'assurance maladie
- numéro de carte vitale


## <a name="france-passport-number"></a>フランスのパスポート番号
このエンティティは、EU パスポート番号の機密情報の種類で使用できます。 また、スタンドアロンの機密情報の種類エンティティとして利用できます。

### <a name="format"></a>フォーマット

9 桁の数字と文字

### <a name="pattern"></a>パターン

9 桁の数字と文字:
- 2 桁
- 2 文字 (大文字と小文字は区別されません)
- 5 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数 `Func_fr_passport` は、パターンに一致するコンテンツを検索します。
- キーワードが見 `Keywords_eu_passport_number` `Keywords_france_eu_passport_number` つかったか、検索されます。
- 正規表現が DD MM YYYY の形式で日付を検索するか、キーワード `Regex_eu_passport_date3` が `Keywords_eu_passport_date` 見つかった

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数 `Func_fr_passport` は、パターンに一致するコンテンツを検索します。
- キーワードが見 `Keywords_eu_passport_number` `Keywords_france_eu_passport_number` つかったか、検索されます。


```xml
    <!-- France Passport Number -->
    <Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_france_eu_passport_number"></a>Keywords_france_eu_passport_number

- numéro de passeport
- passeport n °
- passeport non
- passeport#
- passeport#
- passeportnon
- passeportn °
- passeport français
- passeport livre
- パスポート のデカルト
- numéro パスポート
- passeport n°
- n° du passeport
- n° パスポート

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="france-social-security-number-insee"></a>フランスの社会保障番号 (INSEE)

### <a name="format"></a>フォーマット

15 桁の数字

### <a name="pattern"></a>パターン

次のいずれかのパターンに一致する:
- 13 桁の後にスペースが続き、2 桁の数字が続きます。<br/>
または
- 15 桁の連続する数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数 `Func_french_insee` は、パターンに一致するコンテンツを検索します。
- Keyword_fr_insee のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_french_inseeまたはFunc_fr_insee一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
    <!-- France INSEE -->
    <Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Keyword_fr_insee" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- code sécu
- d'identité nationale
- insee
- fssn#
- le numéro d'identification nationale
- le code de la sécurité sociale
- national id
- national identification
- no d'identité
- 
no. d'identité
- numéro d'assurance
- numéro d'identité
- numero d'identite
- numéro de sécu
- numéro de sécurité sociale
- no d'identite
- 
no. d'identite
- ssn
- ssn#
- sécurité sociale
- securité sociale
- securite sociale
- socialsecuritynumber
- social security number
- social security code
- social insurance number


## <a name="france-tax-identification-number"></a>フランスの納税者番号

### <a name="format"></a>フォーマット

13 桁の数字

### <a name="pattern"></a>パターン

13 桁の数字

- 0、1、2、または 3 である必要があります。
- 1 桁の数字
- スペース 1 つ (省略可能) 
- 2 桁の数字
- スペース 1 つ (省略可能) 
- 3 桁の数字
- スペース 1 つ (省略可能) 
- 3 桁の数字
- スペース 1 つ (省略可能) 
- 3 つのチェックの数字


### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_france_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_france_eu_tax_file_number` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数  `Func_france_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- France Tax Identification Number (numéro SPI.) -->
      <Entity id="ed59e77e-171d-442c-9ec1-88e2ebcb5b0a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_france_eu_telephone_number" />
            <Match idRef="Keywords_france_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>キーワード

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

- numéro d'id fiscale
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#


## <a name="france-value-added-tax-number"></a>フランスの付加価値税番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

13 文字の英数字パターン

### <a name="pattern"></a>パターン

13 文字の英数字パターン:

- 2 文字 - FR (大文字と小文字を区別しない)
- オプションのスペースまたはハイフン
- 2 文字または数字
- オプションのスペース、ドット、ハイフン、またはコンマ
- 3 桁の数字
- オプションのスペース、ドット、ハイフン、またはコンマ
- 3 桁の数字
- オプションのスペース、ドット、ハイフン、またはコンマ
- 3 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_france_value_added_tax_number一致するコンテンツを検索します。
- ユーザーからのキーワードKeywords_france_value_added_tax_number見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_france_value_added_tax_number一致するコンテンツを検索します。

```xml
      <!-- France Value Added Tax Number -->
      <Entity id="949121e6-ad9f-4379-8731-710342baea78" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_value_added_tax_number" />
          <Match idRef="Keywords_france_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keyword_france_value_added_tax_number"></a>Keyword_France_value_added_tax_number

- vat 番号
- vat いいえ
- vat#
- 付加価値税
- siren id no numéro d'id taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n° tva
- numéro de tva
- numéro d'id siren


## <a name="germany-drivers-license-number"></a>ドイツの運転免許証番号

この機密情報の種類エンティティは、EU ドライバーのライセンス番号の機密情報の種類に含まれています。 また、スタンドアロンの機密情報の種類エンティティとして利用できます。

### <a name="format"></a>フォーマット

11 桁の数字と文字の組み合わせ

### <a name="pattern"></a>パターン

11 桁の数字と文字 (大文字と小文字は区別されません):
- 数字または文字
- 2 桁
- 6 桁の数字または文字
- 数字
- 数字または文字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_german_drivers_license がパターンに一致するコンテンツを検出した。
- Keyword_german_drivers_license_number のキーワードを検出した。
- チェックサムが渡される。

```xml
    <!-- German Driver's License Number -->
    <Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Match idRef="Keyword_german_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde
- führerschein
- fuhrerschein
- fuehrerschein
- führerscheinnummer
- fuhrerscheinnummer
- fuehrerscheinnummer
- führerschein- 
- fuhrerschein- 
- fuehrerschein- 
- führerscheinnummernr
- fuhrerscheinnummernr
- fuehrerscheinnummernr
- führerscheinnummerklasse
- fuhrerscheinnummerklasse
- fuehrerscheinnummerklasse
- nr-führerschein
- nr-fuhrerschein
- nr-fuehrerschein
- no-führerschein
- no-fuhrerschein
- no-fuehrerschein
- n-führerschein
- n-fuhrerschein
- n-fuehrerschein
- permis de conduire
- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dlno


## <a name="germany-identity-card-number"></a>ドイツの ID カード番号

### <a name="format"></a>フォーマット

2010 年 11 月 1 日以降: 9 から 11 の文字と数字

1987 年 4 月 1 日から 2010 年 10 月 31 日まで: 10 桁

### <a name="pattern"></a>パターン

2010 年 11 月 1 日以降: 9 ~ 11 文字の英数字パターン
- 1 L、M、N、P、R、T、V、W、X、Y (大文字と小文字を区別しない)
- C、F、G、H、J、K、L、M、P、R、T、V、W、X、Y、Z の 8 桁の数字 (大文字と小文字を区別しない)
- オプションのチェックディジット
- オプションの d/D

1987 年 4 月 1 日から 2010 年 10 月 31 日まで:
- 10 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数 `Func_german_id_card_with_check` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_germany_id_card` 見つかりました。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、パターンに一致するコンテンツを検索します (2010 年より前に発行されたチェック桁または 10 桁のパターンが 2010 年より前に発行された `Regex_germany_id_card` 9 文字)。
- ユーザーからのキーワードKeyword_germany_id_card見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数 `Func_german_id_card_with_check` は、パターンに一致するコンテンツを検索します。
- チェックサムが渡される。


```xml
      <!-- Germany Identity Card Number -->
      <Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" patternsProximity="300" recommendedConfidence="75"> 
        <Pattern confidenceLevel="75">
         <IdMatch idRef="Regex_germany_id_card" /> 
         <Match idRef="Keyword_germany_id_card" /> 
        </Pattern>
        <Version minEngineVersion="15.20.4545.000"> 
          <Pattern confidenceLevel="85">
           <IdMatch idRef="Func_german_id_card_with_check" />
            <Match idRef="Keyword_germany_id_card" /> 
          </Pattern> 
          <Pattern confidenceLevel="65">
           <IdMatch idRef="Func_german_id_card_with_check" /> 
          </Pattern> 
        </Version>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- ausweis
- gpid
- ID
- identifikation
- identifizierungsnummer
- Identity card
- ID 番号
- id-nummer
- 個人用 ID
- personalausweis
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer


## <a name="germany-passport-number"></a>ドイツのパスポート番号

### <a name="format"></a>フォーマット

9 ~ 11 文字

### <a name="pattern"></a>パターン

- C、F、G、H、J、K の 1 文字 (大文字と小文字を区別しない)
- C、F、G、H、J、K、L、M、P、R、T、V、W、X、Y、Z の 8 桁の数字 (大文字と小文字を区別しない)
- オプションのチェックディジット
- オプションの d/D

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数 `Func_german_passport_checksum` は、パターンに一致するコンテンツを検索します。
- キーワードが見 `Keyword_german_passport` `Keywords_eu_passport_number_common` つかったか、検索されます。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数は、9 文字のパターンに一致するコンテンツを検索します (チェックディジットと `Func_german_passport` オプションの d/D なし)。
- キーワードが見 `Keyword_german_passport` `Keywords_eu_passport_number_common` つかったか、検索されます。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数 `Func_german_passport_checksum` は、パターンに一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
    <!-- German Passport Number -->
    <Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
      <Version minEngineVersion="15.20.4570.0">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_german_passport_checksum" />
          <Any minMatches="1">
            <Match idRef="Keyword_german_passport" />
            <Match idRef="Keywords_eu_passport_number_common" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_german_passport_checksum" />
        </Pattern>
      </Version>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepasse
- reisepassnummer
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe
- passeport no.
- passeport no

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号


## <a name="germany-tax-identification-number"></a>ドイツの納税者番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 11 桁の数字

### <a name="pattern"></a>パターン

11 桁の数字

- 2 桁の数字
- 省略可能なスペース
- 3 桁の数字
- 省略可能なスペース
- 3 桁の数字
- 省略可能なスペース
- 2 桁の数字
- 1 つのチェックディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_germany_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_germany_eu_tax_file_number` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数  `Func_germany_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Germany Tax Identification Number -->
      <Entity id="43316a89-9880-40cf-b980-04bc7eefcec5" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

- identifikationsnummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#
- zinn#
- zinn
- zinnnummer


## <a name="germany-value-added-tax-number"></a>ドイツの付加価値税番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

11 文字の英数字パターン

### <a name="pattern"></a>パターン

11 文字の英数字パターン:

- 文字 D または d
- E または e の文字
- オプションのスペース
- 3 桁の数字
- 省略可能なスペースまたはコンマ
- 3 桁の数字
- 省略可能なスペースまたはコンマ
- 3 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数Func_germany_value_added_tax_number一致するコンテンツを検索します。
- ユーザーのキーワードKeywords_germany_value_added_tax_number見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数Func_germany_value_added_tax_number一致するコンテンツを検索します。

```xml
      <!-- Germany Value Added Tax Number -->
      <Entity id="db177eb2-8811-4842-bffc-128c14aa219f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
          <Match idRef="Keywords_germany_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keyword_germany_value_added_tax_number"></a>Keyword_germany_value_added_tax_number

- vat 番号
- vat いいえ
- vat#
- vat# mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer


## <a name="greece-drivers-license-number"></a>ギリシャの運転免許証番号

このエンティティは、EU ドライバーのライセンス番号の機密情報の種類に含まれています。 また、スタンドアロンの機密情報の種類エンティティとして使用できます。

### <a name="format"></a>フォーマット

スペースと区切り記号のない 9 桁の数字

### <a name="pattern"></a>パターン

9 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_greece_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_greece_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Greece Driver's License Number -->
      <Entity id="7a2200b5-aacf-4e3c-ab36-136d3e68b7da" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_greece_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver's_license_number

- δεια οδήγησης
- Adeia odigisis
- Άδεια οδήγησης
- Δίπλωμα οδήγησης


## <a name="greece-national-id-card"></a>ギリシャの国民 ID カード

### <a name="format"></a>フォーマット

7 ～ 8 桁の文字と数字の組み合わせとハイフン 1 つ

### <a name="pattern"></a>パターン

7 桁の文字と数字 (従来の形式):
- 1 桁の文字 (ギリシャ語のアルファベット文字) 
- ハイフン 1 つ 
- 6 桁の数字

8 桁の文字と数字 (現在の形式):
- ギリシャ語にもラテン語にも大文字がある文字 (ABEZHIKMNOPTYX) を使用した 2 桁の文字 
- ハイフン 1 つ 
- 6 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、Regex_greece_id_card一致するコンテンツを検索します。
- ユーザーのキーワードKeyword_greece_id_card見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- 正規表現は、Regex_greece_id_card一致するコンテンツを検索します。

```xml
      <!-- Greece National ID Card -->
      <Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_id_card" />
          <Match idRef="Keyword_greece_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- ギリシャ語 ID
- ギリシャ語の国 ID
- ギリシャの個人用 ID カード
- ギリシャの警察 ID
- Identity card
- tautotita
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>ギリシャのパスポート番号

### <a name="format"></a>フォーマット

2 文字の後に 7 桁の数字が続き、スペースまたは区切り記号は使用されません。

### <a name="pattern"></a>パターン

2 桁の文字の後に 7 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_greece_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_greece_eu_passport_number` つかったか、検索されます。
- 正規表現は `Regex_greece_eu_passport_date` 、DD MMM YY (例 - 8 月 19 日) の形式で日付を検索するか、キーワードが `Keywords_greece_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_greece_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_greece_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Greece Passport Number -->
      <Entity id="7e65eb47-cdf9-4f52-8f90-2a27d5ee67e3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_greece_eu_passport_date" />
            <Match idRef="Keywords_greece_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο


## <a name="greece-social-security-number-amka"></a>ギリシャの社会保障番号 (AMKA)
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースと区切り記号のない 11 桁の数字

### <a name="pattern"></a>パターン

- 生年月日 YYMMDD として 6 桁の数字
- 4 桁の数字
- チェックの数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_greece_eu_ssn` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_greece_eu_ssn_or_equivalent` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数  `Func_greece_eu_ssn` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Greece Social Security Number (AMKA) -->
      <Entity id="e39b03f4-50ea-41ae-af7a-a4b9539596ad" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_greece_eu_ssn" />
          <Match idRef="Keywords_greece_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_greece_eu_ssn" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_greece_eu_ssn_or_equivalent"></a>Keywords_greece_eu_ssn_or_equivalent

- ssn
- ssn#
- 社会保障なし
- socialsecurityno#
- social security number
- amka
- a.m.k.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης


## <a name="greece-tax-identification-number"></a>ギリシャの納税者番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースと区切り記号のない 9 桁の数字

### <a name="pattern"></a>パターン

9 桁の数字

### <a name="checksum"></a>チェックサム

該当なし

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。

- 正規表現は、  `Regex_greece_eu_tax_file_number` パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_greece_eu_tax_file_number` 見つかりました。

```xml
      <!-- Greek Tax Identification Number -->
      <Entity id="15a54a5a-53d4-4080-ad43-a2a4fe1d3bf7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

- afm#
- afm
- aφμ|aφμ αρρθμι
- aφμ
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- 税レジストリなし
- 税のレジストリ番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- taxregistryno#
- tin id
- tin いいえ
- tin#
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>香港の ID カード (HKID) 番号

### <a name="format"></a>フォーマット

8 ～ 9 桁の文字と数字の組み合わせ、最後の文字はかっこで囲むことも可能

### <a name="pattern"></a>パターン

8 ～ 9 桁の文字の組み合わせ:
- 1 ~ 2 文字 (大文字と小文字は区別されません)
- 6 桁の数字
- チェック ディジットとして機能する最後の文字 (任意の数字か文字 A) はかっこで囲むことも可能。

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_hong_kong_id_card一致するコンテンツを検索します。
- ユーザーからのキーワードKeyword_hong_kong_id_card見つかりました。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数はFunc_hong_kong_id_card一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- 香港の ID カード
- HKIDC
- id card
- Identity card
- hk ID カード
- 香港 ID
- 香港身份證
- 香港永久性居民身份證
- 身份證
- 身份証
- 身分證
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證
- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證
- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証


## <a name="hungary-drivers-license-number"></a>ハンガリーの運転免許証番号

### <a name="format"></a>フォーマット

2 文字の後に 6 桁の数字が続く

### <a name="pattern"></a>パターン

2 文字と 6 桁の数字:

- 2 文字 (大文字と小文字は区別されません)
- 6 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。

- 正規表現は、  `Regex_hungary_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_hungary_eu_driver's_license_number` つかったか、検索されます。

```xml
      <Entity id="9d31c46b-6e6b-444c-aeb1-6dd7e604bb24" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_hungary_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver's_license_number

- vezetoi engedely
- vezetői engedély
- vezetői engedélyek


## <a name="hungary-personal-identification-number"></a>ハンガリーの個人識別番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の数字:

- 性別に対応する 1 桁、男性の場合は 1、女性の場合は 2 桁。 1900 年以前に生まれた市民や二重国籍を持つ市民の場合も、その他の番号を使用できます。
- 生年月日に対応する 6 桁の数字 (YYMMDD)
- シリアル番号に対応する 3 桁の数字
- 1 つのチェックディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。

- この関数  `Func_hungary_eu_national_id_card` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_hungary_eu_national_id_card` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。

- この関数  `Func_hungary_eu_national_id_card` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Hungary Personal Identification Number -->
      <Entity id="7b5cc218-7046-47d9-80c9-f325b50896ca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- id 番号
- identification number
- sz ig
- sz。 ig.
- sz.ig.
- személyazonosító igazolvány
- személyi igazolvány


## <a name="hungary-passport-number"></a>ハンガリーのパスポート番号

### <a name="format"></a>フォーマット

2 つの文字の後に 6 桁または 7 桁の数字が続き、スペースまたは区切り記号はありません。

### <a name="pattern"></a>パターン

2 文字の後に 6 桁または 7 桁の数字が続く

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_hungary_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_hungary_eu_passport_number` つかったか、検索されます。
- 正規表現は `Regex_hungary_eu_passport_date` 、DD MMM/MMM YY (例 - 01 MÁR/MAR 12) 形式の日付を検索するか、キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_hungary_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_hungary_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Hungary Passport Number -->
      <Entity id="5b483910-9aa7-4c99-9917-f4001464bda7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_hungary_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="hungary-social-security-number-taj"></a>ハンガリーの社会保障番号 (TAJ)

### <a name="format"></a>フォーマット

スペースと区切り記号のない 9 桁の数字

### <a name="pattern"></a>パターン

9 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。

- この関数  `Func_hungary_eu_ssn_or_equivalent` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_hungary_eu_ssn_or_equivalent` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。

- この関数  `Func_hungary_eu_ssn_or_equivalent` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Hungarian Social Security Number (TAJ) -->
      <Entity id="0de78315-9537-47f5-95ab-b3e77eba3993" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

- ハンガリーの社会保障番号
- social security number
- socialsecuritynumber#
- hssn#
- socialsecuritynno
- hssn
- taj
- taj#
- ssn
- ssn#
- 社会保障なし
- áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>ハンガリーの納税者番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースまたは区切り記号がない 10 桁

### <a name="pattern"></a>パターン

10 桁の数字:

- "8" である必要があります 1 桁
- 8 桁の数字
- 1 つのチェックディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。

- この関数  `Func_hungary_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_hungary_eu_tax_file_number` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。

- この関数  `Func_hungary_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Hungary Tax Identification Number -->
      <Entity id="ede42eb4-59d9-49eb-9603-d7853fbda91d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

- adóazonosító szám
- adóhatóság szám
- adószám
- ハンガリーのスズ
- hungatiantin#
- 税務当局 なし
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#
- vat 番号


## <a name="hungary-value-added-tax-number"></a>ハンガリーの付加価値税番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

10 文字の英数字パターン

### <a name="pattern"></a>パターン

10 文字の英数字パターン:

- 2 文字 - HU または hu
- オプションのスペース
- 8 桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。

- この関数はFunc_hungarian_value_added_tax_number一致するコンテンツを検索します。
- ユーザーのキーワードKeywords_hungarian_value_added_tax_number見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。

- この関数はFunc_hungarian_value_added_tax_number一致するコンテンツを検索します。

```xml
      <!-- Hungarian Value Added Tax Number -->
      <Entity id="976349a0-683b-477a-90f8-ff0a220d5592" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
          <Match idRef="Keywords_hungarian_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_hungary_value_added_tax_number"></a>Keyword_Hungary_value_added_tax_number

- vat
- 付加価値税番号
- vat#
- vatno#
- hungarianvatno#
- tax no.
- 付加価値税 áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-drivers-license-number"></a>インドの運転免許証番号

### <a name="format"></a>フォーマット

15 文字の英数字パターン

### <a name="pattern"></a>パターン

15 文字または数字:
- 状態コードを示す 2 文字
- オプションのスペースまたはダッシュ
- 都市コードを示す 2 桁の数字
- オプションのスペースまたはダッシュ
- 発行年を示す 4 桁の数字
- オプションのスペースまたはダッシュ
- 7 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、 `Regex_india_driving_license` パターンに一致するコンテンツを検索します。
- キーワードが `Keywords_eu_driver's_license_number_common` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、 `Regex_india_driving_license` パターンに一致するコンテンツを検索します。


```xml
      <!-- India Driver's License Number -->
        <Entity id="680788a3-53b6-455a-b891-c38cd76dc917" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
          <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_india_driving_license" />
            <Match idRef="Keywords_eu_driver's_license_number_common" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_india_driving_license" />
            </Pattern>
        </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number_common"></a>Keywords_eu_driver's_license_number_common

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号



## <a name="india-gst-number"></a>インドの GST 番号

### <a name="format"></a>フォーマット

15 文字の英数字パターン

### <a name="pattern"></a>パターン

15 文字または数字:
- 有効な状態コードを表す 2 桁の数字
- オプションのスペースまたはダッシュ
- 永続的なアカウント番号 (PAN) を表す 10 文字 
- 1 文字または数字
- オプションのスペースまたはダッシュ
- 1 文字 'z' または 'Z'
- オプションのスペースまたはダッシュ
- 1 つのチェックディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数 `Func_india_gst_number` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_india_gst_number` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数 `Func_india_gst_number` は、パターンに一致するコンテンツを検索します。


```xml
    <!-- India GST number  -->
      <Entity id="9f5a721c-2fd2-446a-a27e-0c02fbe4630c" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_india_gst_number" />
          <Match idRef="Keyword_india_gst_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_india_gst_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_india_gst_number"></a>Keyword_india_gst_number

- gst
- gstin
- 商品およびサービス税
- 商品およびサービス税


## <a name="india-permanent-account-number-pan"></a>インドの永続的なアカウント番号 (PAN)

### <a name="format"></a>フォーマット

10 桁の文字または数字

### <a name="pattern"></a>パターン

10 桁の文字または数字:
- 3 文字 (大文字と小文字は区別されません)
- C、P、H、F、A、T、B、L、J、G の文字 (大文字と小文字は区別されません)
- レター
- 4 桁の数字
- 英字チェックの数字である文字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、Regex_india_permanent_account_number一致するコンテンツを検索します。
- ユーザーからのキーワードKeyword_india_permanent_account_number見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- 正規表現は、Regex_india_permanent_account_number一致するコンテンツを検索します。


```xml
      <!-- India Permanent Account Number -->
      <Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_india_permanent_account_number" />
          <Match idRef="Keyword_india_permanent_account_number" />
        </Pattern>
        <Version minEngineVersion="15.20.3520.000">
          <Pattern confidenceLevel="65">
            <IdMatch idRef="Regex_india_permanent_account_number" />
          </Pattern>
        </Version>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Permanent Account Number
- PAN

## <a name="india-unique-identification-aadhaar-number"></a>インドの一意の ID (Aadhaar) 番号

### <a name="format"></a>フォーマット

省略可能なスペースまたはハイフンを含む 12 桁の数字

### <a name="pattern"></a>パターン

12 桁の数字:
- 0 または 1 ではない数字
- 3 桁の数字
- スペースまたはハイフン 1 つ (省略可能) 
- 4 桁の数字
- スペースまたはハイフン 1 つ (省略可能) 
- 最後の数字 (チェック桁)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数Func_india_aadhaar一致するコンテンツを検索します。
- ユーザーのキーワードKeyword_india_aadhar見つかりました。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。

- この関数Func_india_aadhaar一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar
- aadhaar
- aadhar
- aadhar#
- uid
- आधार
- uidai


## <a name="india-voter-id-card"></a>インドの投票者 ID カード

### <a name="format"></a>フォーマット

10 文字の英数字パターン

### <a name="pattern"></a>パターン

10 桁の文字または数字:
- 3 文字
- 7 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、 `Regex_india_voter_id_card` パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_india_voter_id_card` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- 正規表現は、 `Regex_india_voter_id_card` パターンに一致するコンテンツを検索します。


```xml
      <!-- India Voter Id Card  -->
        <Entity id="646d643f-5228-4408-acc8-f2e81a6df897" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
           <Pattern confidenceLevel="75">
             <IdMatch idRef="Regex_india_voter_id_card" />
             <Match idRef="Keyword_india_voter_id_card" />
            </Pattern>
           <Pattern confidenceLevel="65">
              <IdMatch idRef="Regex_india_voter_id_card" />
            </Pattern>
        </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_india_voter_id_card"></a>Keyword_india_voter_id_card

- 投票者
- voterid
- votercard
- voteridcard
- 選挙用写真の ID カード
- EPIC
- ECI
- 選挙のコンミション


## <a name="indonesia-identity-card-ktp-number"></a>インドネシアの ID カード (KTP) 番号

### <a name="format"></a>フォーマット

省略可能なピリオドを含む 16 桁の数字

### <a name="pattern"></a>パターン

16 桁の数字:
- 2 桁の行政区コード 
- ピリオド 1 つ (省略可能) 
- 2 桁の行政区または市コード 
- 2 桁の分区コード 
- ピリオド 1 つ (省略可能) 
- DDMMYY という形式の 6 桁の数字 (生年月日)
- ピリオド 1 つ (省略可能) 
- 4 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。

- 正規表現は、Regex_indonesia_id_card一致するコンテンツを検索します。
- ユーザーからのキーワードKeyword_indonesia_id_card見つかりました。

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk
- Nomor Induk Kependudukan

## <a name="international-banking-account-number-iban"></a>国際銀行口座番号 (IBAN)

### <a name="format"></a>フォーマット

国コード (2 文字) プラスチェックの数字 (2 桁) プラス bban 番号 (最大 30 文字)

### <a name="pattern"></a>パターン

パターンには、以下のすべてが含まれる必要があります。

- 2 文字の国コード
- 2 桁のチェック数字 (その後にオプションのスペース)
- 4 つの文字または数字の 1 ~ 7 グループ (スペースで区切って指定できます)
- 1 ～ 3 個の文字または数字

国ごとに形式が若干異なります。 IBAN の機密情報の種類は、次の 60 か国を対象とします。

- ad
- ae
- al
- 場所
- az
- ba
- be
- bg
- bh
- ch
- cr
- cy
- cz
- de
- dk
- do
- ee
- es
- fi
- fo
- fr
- gb
- ge
- gi
- gl
- gr
- hr
- hu
- すなわち
- il
- is
- it
- kw
- kz
- lb
- li
- lt
- lu
- lv
- mc
- md
- me
- mk
- mr
- mt
- mu
- nl
- いいえ
- pl
- pt
- ro
- rs
- sa
- se
- si
- sk
- sm
- tn
- tr
- vg

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。

- 関数 Func_iban がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

なし


## <a name="international-classification-of-diseases-icd-10-cm"></a>病気の国際分類 (ICD-10-CM)

### <a name="format"></a>フォーマット

Dictionary

### <a name="pattern"></a>パターン

キーワード

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- ユーザーからのキーワードDictionary_icd_10_updated見つかりました。
- ユーザーのキーワードDictionary_icd_10_codes見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 更新されたDictionary_icd_10_キーワードが見つかりました。

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

### <a name="keywords"></a>キーワード

病気の国際分類、第 10 リビジョン、臨床変更 [(ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604)に基づく、Dictionary_icd_10_updated キーワード 辞書の任意の用語。 この型は、保険コードではなく、用語のみを検索します。

病気の国際分類、第 10 リビジョン、臨床変更 [(ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604)に基づく、Dictionary_icd_10_codes キーワード 辞書の任意の用語。 この型は、説明ではなく、保険コードのみを検索します。

## <a name="international-classification-of-diseases-icd-9-cm"></a>病気の国際分類 (ICD-9-CM)

### <a name="format"></a>フォーマット

Dictionary

### <a name="pattern"></a>パターン

キーワード

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- このページのDictionary_icd_9_updatedが見つかりました。
- ユーザーのキーワードDictionary_icd_9_codes見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- このページのDictionary_icd_9_updatedが見つかりました。

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

病気の国際分類、第 9 改訂、臨床変更 [(ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605)に基づく、Dictionary_icd_9_updated キーワード 辞書からの任意の用語。 この型は、保険コードではなく、用語のみを検索します。

病気の国際分類、第 9 改訂、臨床変更 [(ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605)に基づく、Dictionary_icd_9_codes キーワード 辞書からの任意の用語。 この型は、説明ではなく、保険コードのみを検索します。

## <a name="ip-address"></a>IP アドレス

### <a name="format"></a>フォーマット

#### <a name="ipv4"></a>IPv4:
IPv4 アドレスの書式付き (ピリオド) バージョンと書式設定されていない (ピリオドなし) バージョンをアカウントする複雑なパターン

#### <a name="ipv6"></a>IPv6:
書式設定された IPv6 番号を表す複雑なパターン (コロンを含む)

### <a name="pattern"></a>パターン

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

IPv6 の場合、DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。
- Keyword_ipaddress のキーワードを検出しなかった。

IPv4 の場合、DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現 Regex_ipv4_address がパターンに一致するコンテンツを検出した。
- Keyword_ipaddress のキーワードを検出した。

IPv6 の場合、DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。
- Keyword_ipaddress のキーワードを検出しなかった。

```xml
    <!-- IP Address --> 
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (このキーワードでは大文字と小文字が区別されます)
- ip address
- ip addresses
- internet protocol
- IP-כתובת ה


## <a name="ip-address-v4"></a>IP アドレス v4

### <a name="format"></a>フォーマット

IPv4 アドレスの書式付き (ピリオド) バージョンと書式設定されていない (ピリオドなし) バージョンをアカウントする複雑なパターン

### <a name="pattern"></a>パターン


### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、 `Regex_ipv4_address` パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_ipaddress` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、 `Regex_ipv4_address` パターンに一致するコンテンツを検索します。


```xml
      <!-- IP Address v4--> 
      <Entity id="a7dd5e5f-e7f9-4626-a2c6-86a8cb6830d2" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ipv4_address" />
          <Match idRef="Keyword_ipaddress" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ipv4_address" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (大文字と小文字の区別)
- ip address
- ip addresses
- internet protocol
- IP-כתובת ה


## <a name="ip-address-v6"></a>IP アドレス v6

### <a name="format"></a>フォーマット

書式設定された IPv6 番号を表す複雑なパターン (コロンを含む)

### <a name="pattern"></a>パターン


### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、 `Regex_ipv6_address` パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_ipaddress` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、 `Regex_ipv6_address` パターンに一致するコンテンツを検索します。


```xml
      <!-- IP Address v6-->
      <Entity id="3f691089-7413-4926-ab3b-3c5ea8a1c17e" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ipv6_address" />
          <Match idRef="Keyword_ipaddress" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ipv6_address" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (大文字と小文字の区別)
- ip address
- ip addresses
- internet protocol
- IP-כתובת ה


## <a name="ireland-drivers-license-number"></a>アイルランドの運転免許証番号

### <a name="format"></a>フォーマット

6 桁の数字の後に 4 文字

### <a name="pattern"></a>パターン

6 桁の数字と 4 文字:

- 6 桁の数字
- 4 文字 (大文字と小文字は区別されません)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。

- 正規表現は、  `Regex_ireland_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_ireland_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Ireland Driver's License Number -->
      <Entity id="e01bccd9-eb4d-414f-ace1-e9b6a4c4a2ca" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_ireland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver's_license_number

- ceadúnas tiomána
- ceadúnais tiomána

## <a name="ireland-passport-number"></a>アイルランドのパスポート番号

### <a name="format"></a>フォーマット

2 つの文字または数字の後に、スペースまたは区切り記号がない 7 桁の数字

### <a name="pattern"></a>パターン

2 つの文字または数字の後に 7 桁の数字が続きます。

- 2 桁または 1 文字 (大文字と小文字は区別されません)
- 7 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_ireland_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_ireland_eu_passport_number` つかったか、検索されます。
- 正規表現は `Regex_ireland_eu_passport_date` 、DD MMM/MMM YYYY (例 - 01 BEA/MAY 1988) の形式で日付を検索するか、キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_ireland_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_ireland_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Ireland Passport Number -->
      <Entity id="a2130f27-9ee2-4103-84f9-a6b1ee7d0cbf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_ireland_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport numero
- uimhreacha pasanna
- uimhir pas
- uimhir phas
- uimhreacha pas
- uimhir cárta
- uimhir chárta

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="ireland-personal-public-service-pps-number"></a>アイルランドの個人公開サービス (PPS) 番号

### <a name="format"></a>フォーマット

古い形式 (2012 年 12 月 31 日まで):
- 7 桁の数字の後に 1 ~ 2 文字

新しい形式 (2013 年 1 月 1 日以降):
- 7 桁の数字の後に 2 文字

### <a name="pattern"></a>パターン

古い形式 (2012 年 12 月 31 日まで):
- 7 桁
- 1 ~ 2 文字 (大文字と小文字は区別されません)

新しい形式 (2013 年 1 月 1 日以降):
- 7 桁
- 英字チェックの数字である文字 (大文字と小文字を区別しない)
- 範囲 A から I、または "W" のオプションの文字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_ireland_pps一致するコンテンツを検索します。
- ユーザーからのキーワードKeywords_ireland_eu_national_id_card見つかりました。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数はFunc_ireland_pps一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
      <!-- Ireland Personal Public Service (PPS) Number -->
      <Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_pps" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_ireland_pps" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- クライアント ID サービス
- identification number
- 個人用 ID 番号
- 個人のパブリック サービス番号
- 個人用サービスなし
- phearsanta seirbhíse poiblí
- pps no
- pps 番号
- pps num
- pps サービスなし
- ppsn
- ppsno#
- ppsno
- psp
- パブリック サービスなし
- publicserviceno#
- publicserviceno
- 収益と社会保険番号
- rsi いいえ
- rsi 番号
- rsin
- seirbhís aitheantais クライアント
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#


## <a name="israel-bank-account-number"></a>イスラエルの銀行口座番号

### <a name="format"></a>フォーマット

13 桁の数字

### <a name="pattern"></a>パターン

書式設定:
- 2 桁
- ダッシュ
- 3 桁の数字
- ダッシュ
- 8 桁

Unformatted:
- 	13 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現 Regex_israel_bank_account_number がパターンに一致するコンテンツを検出した。
- Keyword_israel_bank_account_number のキーワードを検出した。

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Bank Account Number
- Bank Account
- Account Number
- מספר חשבון בנק

## <a name="israel-national-identification-number"></a>イスラエルの国民識別番号

### <a name="format"></a>フォーマット

9 桁

### <a name="pattern"></a>パターン

9 桁の連続する数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_israeli_national_id_number がパターンに一致するコンテンツを検出した。
- Keyword_Israel_National_ID のキーワードを検出した。
- チェックサムが渡される。

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

-   מספר זהות
-   מספר זיה וי
-   מספר זיהוי ישר אלי      
-   זהותישר אלית
-   هو ية اسرائيل ية عدد
-   هوية إسرائ يلية
-   رقم الهوية
-   عدد هوية فريدة من نوعها
-   idnumber#
-   id 番号
-   ID なし        
-   identitynumber#
-   ID 番号
-   イスラエルの国番号       
-   個人用 ID
-   一意の ID  


## <a name="italy-drivers-license-number"></a>イタリアの運転免許証番号

この種類のエンティティは、EU ドライバーのライセンス番号の機密情報の種類に含まれています。 また、スタンドアロンの機密情報の種類エンティティとして使用できます。

### <a name="format"></a>フォーマット

10 文字と数字の組み合わせ

### <a name="pattern"></a>パターン

10 文字と数字の組み合わせ:
- 1 文字 (大文字と小文字は区別されません)
- 文字 "A" または "V" (大文字と小文字は区別されません)
- 7 桁
- 1 文字 (大文字と小文字は区別されません)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、 `Regex_italy_drivers_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見 `Keywords_eu_driver's_license_number` `Keyword_italy_drivers_license_number` つかったか、検索されます。

```xml
    <!-- Italy Driver's license Number -->
    <Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keyword_italy_drivers_license_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente
- patente di guida
- patente guida
- patenti di guida
- patenti guida


## <a name="italy-fiscal-code"></a>イタリアの会計コード
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

指定したパターンの文字と数字の 16 文字の組み合わせ

### <a name="pattern"></a>パターン

16 文字の文字と数字の組み合わせ:
- ファミリ名の最初の 3 つの子文字に対応する 3 文字
- 最初の名前、3 番目、4 番目の子名に対応する 3 文字
- 出生年の最後の数字に対応する 2 桁の数字
- 出生月の文字に対応する 1 つの文字 - 文字はアルファベット順で使用されますが、A から E、H、L、M、P、R から T の文字だけが使用されます (したがって、1 月は A で、10 月は R です)
- 性別を区別するために、出生日に対応する 2 桁の数字、女性の出生日に 40 が追加されます。
- 人が生まれた市区町村に固有の市外コードに対応する 4 桁の数字 (国全体のコードは外国で使用されます)
- 1 つのパリティディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_italy_eu_national_id_card` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_italy_eu_national_id_card` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数  `Func_italy_eu_national_id_card` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Italy Fiscal Code -->
      <Entity id="4cd79172-8da9-4ff5-9188-98b1e7e2eca6" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

- codice の会計
- codice fiscale
- codice id personale
- codice personale
- 会計コード
- numero certificato personale
- numero di identificazione Fiscale
- numero id personale
- numero personale
- 個人証明書番号
- 個人用コード
- 個人用 ID コード
- 個人用 ID 番号
- personalcodeno#
- 税コード
- tax id
- 税の識別なし
- 税の識別番号
- 税 ID 番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#


## <a name="italy-passport-number"></a>イタリアのパスポート番号

### <a name="format"></a>フォーマット

2 つの文字または数字の後にスペースまたは区切り記号を付けない 7 桁の数字

### <a name="pattern"></a>パターン

2 つの文字または数字の後に 7 桁の数字が続きます。

- 2 桁の数字または文字 (大文字と小文字を区別しない)
- 7 桁

### <a name="checksum"></a>チェックサム

該当なし

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_italy_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_italy_eu_passport_number` つかったか、検索されます。
- 正規表現は `Regex_italy_eu_passport_date` 、DD MMM/MMM YYYY (例 - 01 GEN/JAN 1988) 形式の日付を検索するか、キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_italy_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_italy_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Italy Passport Number -->
      <Entity id="39811019-4750-445f-b26d-4c0e6c431544" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_italy_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiana
- passaporto numero
- numéro パスポート
- numero di passaporto
- numeri del passaporto
- passeport italien

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="italy-value-added-tax-number"></a>イタリアの付加価値税番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

13 文字の英数字パターン (オプションの区切り記号付き)

### <a name="pattern"></a>パターン

13 文字の英数字パターン (オプションの区切り記号付き):

- I または i
- T または t
- オプションのスペース、ドット、ハイフン、またはコンマ
- 11 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_italy_value_added_tax_number一致するコンテンツを検索します。
- このページのKeywords_italy_value_added_tax_number見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_italy_value_added_tax_number一致するコンテンツを検索します。

```xml
      <!-- Italy Value Added Tax -->
      <Entity id="26a8cc07-2283-4a2a-ab1d-4ab643c4c67f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
          <Match idRef="Keywords_italy_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_italy_value_added_tax_number"></a>Keyword_italy_value_added_tax_number

- vat 番号
- vat いいえ
- vat#
- iva
- iva#


## <a name="japan-bank-account-number"></a>日本の銀行口座番号

### <a name="format"></a>フォーマット

7 桁または 8 桁

### <a name="pattern"></a>パターン

銀行口座番号:
- 7 桁または 8 桁
- 銀行口座のブランチ コード:
- 4 桁
- スペースまたはダッシュ (オプション)
- 3 桁の数字

チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。
- Keyword_jp_bank_account のキーワードを検出した。
- 次のいずれかの条件に該当する:
- 関数 Func_jp_bank_account_branch_code がパターンに一致するコンテンツを検出した。
- Keyword_jp_bank_branch_code のキーワードを検出した。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。
- Keyword_jp_bank_account のキーワードを検出した。

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_jp_bank_account"></a>Keyword_jp_bank_account

- Checking Account Number
- Checking Account
- Checking Account #
- Checking Acct Number
- Checking Acct #
- Checking Acct No.
- Checking Account No.
- Bank Account Number
- Bank Account
- Bank Account #
- Bank Acct Number
- Bank Acct #
- Bank Acct No.
- Bank Account No.
- Savings Account Number
- Savings Account
- Savings Account #
- Savings Acct Number
- Savings Acct #
- Savings Acct No.
- Savings Account No.
- Debit Account Number
- Debit Account
- Debit Account #
- Debit Acct Number
- Debit Acct #
- Debit Acct No.
- Debit Account No.
- 口座番号
- 銀行口座
- 銀行口座番号
- 総合口座
- 普通預金口座
- 普通口座
- 当座預金口座
- 当座口座
- 預金口座
- 振替口座
- 銀行
- バンク

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

- 支店番号
- 支店コード
- 店番号

## <a name="japan-drivers-license-number"></a>日本の運転免許証番号

### <a name="format"></a>フォーマット

12 桁の数字

### <a name="pattern"></a>パターン

12 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_jp_drivers_license_number がパターンに一致するコンテンツを検出した。
- Keyword_jp_drivers_license_number のキーワードを検出した。

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_jp_drivers_license_number"></a>Keyword_jp_drivers_license_number

- driverlicense
- driverslicense
- driver'slicense
- driverslicenses
- driver'slicenses
- driverlicenses
- dl#
- dls#
- lic#
- lics#
- 運転免許証
- 運転免許
- 免許証
- 免許
- 運転免許証番号
- 運転免許番号
- 免許証番号
- 免許番号
- 運転免許証ナンバー
- 運転免許ナンバー
- 免許証ナンバー
- (2)
- (1)(2)(2
- 証証ノ
- 予約の変更
- 運転経歴証明書番号
- 運転経歴証明書
- 彼は、その他の方法を使用します。
- (1)
- [証証]
- (1)(2)(2
- 運転免許証#
- 運転免許#
- 免許証#
- 免許#


## <a name="japan-my-number---corporate"></a>日本のマイナンバー - 企業

この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

13 桁の数字

### <a name="pattern"></a>パターン

13 桁の番号:

- 1 から 9 の 1 桁
- 12 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_japanese_my_number_corporate一致するコンテンツを検索します。
- ユーザーからのキーワードKeywords_japanese_my_number_corporate見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_japanese_my_number_corporate一致するコンテンツを検索します。

```xml
      <!-- Japanese My Number – Corporate -->
      <Entity id="9e0eaf79-ff20-4ffb-b3e4-e7368d5db6ff" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
          <Match idRef="Keywords_japanese_my_number_corporate" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_japan_my_number_corporate"></a>Keyword_japan_my_number_corporate

- 会社番号
- マイナンバー
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 法人番号
- 指定通知書


## <a name="japan-my-number---personal"></a>日本のマイナンバー - 個人用

この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

12 桁の番号

### <a name="pattern"></a>パターン

12 桁の番号:

- 4 桁
- オプションのスペース、ドット、またはハイフン
- 4 桁
- オプションのスペース、ドット、またはハイフン
- 4 桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_japanese_my_number_personal一致するコンテンツを検索します。
- ユーザーのキーワードKeywords_japanese_my_number_personal見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数はFunc_japanese_my_number_personal一致するコンテンツを検索します。

```xml
      <!-- Japanese My Number – Personal -->
      <Entity id="98da8e66-7299-4ebd-9f82-c871ab37d3ef" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_personal" />
          <Match idRef="Keywords_japanese_my_number_personal" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_japanese_my_number_personal" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_japan_my_number_personal"></a>Keyword_japan_my_number_personal

- my number
- マイナンバー
- 個人番号
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 通知カード


## <a name="japan-passport-number"></a>日本のパスポート番号

### <a name="format"></a>フォーマット

2 文字の後に 7 桁の数字を付け

### <a name="pattern"></a>パターン

2 文字 (大文字と小文字は区別されません) の後に 7 桁の数字が続く

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_jp_passport がパターンに一致するコンテンツを検出した。
- Keyword_jp_passport のキーワードを検出した。

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- Passport
- Passport Number
- Passport No.
- Passport #
- パスポート
- パスポート番号
- パスポートナンバー
- パスポート＃
- パスポート#
- 下に示すのは、1 つの
- 旅券番号
- 旅券番号＃
- 旅券番号♯
- 旅券ナンバー


## <a name="japan-residence-card-number"></a>日本の在留カード番号

### <a name="format"></a>フォーマット

12 文字と数字

### <a name="pattern"></a>パターン

12 文字と数字:
- 2 文字 (大文字と小文字は区別されません)
- 8 桁
- 2 文字 (大文字と小文字は区別されません)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、Regex_jp_residence_card_number一致するコンテンツを検索します。
- ユーザーのキーワードKeyword_jp_residence_card_number見つかりました。

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- 在留カード番号
- 在留カードなし
- 在留カード#
- 在留カード番号
- 在留カード
- 在留番号

## <a name="japan-resident-registration-number"></a>日本居住者登録番号

### <a name="format"></a>フォーマット

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_jp_resident_registration_number がパターンに一致するコンテンツを検出した。
- Keyword_jp_resident_registration_number のキーワードを検出した。

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_jp_resident_registration_number"></a>Keyword_jp_resident_registration_number

- Resident Registration Number
- Residents Basic Registry Number
- Resident Registration No.
- Resident Register No.
- Residents Basic Registry No.
- Basic Resident Register No.
- 外国人登録証明書番号
- 証明書番号
- 登録番号
- 外国人登録証


## <a name="japan-social-insurance-number-sin"></a>日本の社会保険番号 (SIN)

### <a name="format"></a>フォーマット

7～ 12 桁の数字

### <a name="pattern"></a>パターン

7 ～ 12 桁の数字:
- 4 桁
- ハイフン (オプション)
- 6 桁の OR
- 7 ～ 12 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数 Func_jp_sin がパターンに一致するコンテンツを検出した。
- Keyword_jp_sin のキーワードを検出した。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_jp_sin_pre_1997 がパターンに一致するコンテンツを検出した。
- Keyword_jp_sin のキーワードを検出した。

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- Social Insurance No.
- Social Insurance Num
- Social Insurance Number
- 健康保険被保険者番号
- 健保番号
- 基礎年金番号
- 雇用保険被保険者番号
- 雇用保険番号
- 保険証番号
- 社会保険番号
- 社会保険No.
- 社会保険
- 介護保険
- 介護保険被保険者番号
- 健康保険被保険者整理番号
- 雇用保険被保険者整理番号
- 厚生年金
- 厚生年金被保険者整理番号


## <a name="latvia-drivers-license-number"></a>ラトビアの運転免許証番号

### <a name="format"></a>フォーマット

3 文字の後に 6 桁の数字が続く

### <a name="pattern"></a>パターン

3 文字と 6 桁の数字:

- 3 文字 (大文字と小文字は区別されません)
- 6 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_latvia_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_latvia_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Latvia Driver's License Number -->
      <Entity id="ec996de0-30f2-46b1-b192-4d2ff8805fa7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_latvia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver's_license_number

- autovadītāja apliecība
- autovadītāja apliecības
- vadītāja apliecība

## <a name="latvia-personal-code"></a>ラトビアの個人用コード

### <a name="format"></a>フォーマット

11 桁の数字とオプションのハイフン

### <a name="pattern"></a>パターン

古い形式

11 桁の数字とハイフン:

- 生年月日に対応する 6 桁の数字 (DDMMYY)
- ハイフン
- 生後世紀に対応する 1 桁の数字 (19 世紀は "0"、20 世紀は "1"、21 世紀は "2")
- 4 桁の数字、ランダムに生成される

新しい形式

11 桁の数字

- 2 桁の "32"
- 9 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数または  `Func_latvia_eu_national_id_card` 正規表現は、 `Regex_latvia_eu_national_id_card_new_format` パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_latvia_eu_national_id_card` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数または  `Func_latvia_eu_national_id_card` 正規表現は、 `Regex_latvia_eu_national_id_card_new_format` パターンに一致するコンテンツを検索します。

```xml
      <!-- Latvia Personal Code -->
      <Entity id="03fcf763-27c2-49ed-9422-2641c6c895c9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>キーワード

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- 管理番号
- alvas nē
- 出生番号
- 市民番号
- 民事番号
- 電子国勢調査番号
- 電子番号
- 会計コード
- 医療ユーザー番号
- id#
- id-code
- identification number
- identifikācijas numurs
- id-number
- 個々の番号
- latvija alva
- nacionālais id
- national id
- 国の識別番号
- 国の ID 番号
- national insurance number
- 国内登録番号
- nodokは numurs
- nodok
- nodokijau identifikācija numurs
- 個人証明書番号
- 個人用コード
- 個人用 ID コード
- 個人用 ID 番号
- 個人識別コード
- 個人識別子
- 個人 ID 番号
- 個人番号
- 個人の数値コード
- personalcodeno#
- personas kods
- 母集団識別コード
- パブリック サービス番号
- registration number
- 収益番号
- social insurance number
- social security number
- 州税コード
- tax file number
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#
- 投票者の番号

## <a name="latvia-passport-number"></a>ラトビアのパスポート番号

### <a name="format"></a>フォーマット

2 つの文字または数字の後にスペースまたは区切り記号を付けない 7 桁の数字

### <a name="pattern"></a>パターン

2 つの文字または数字の後に 7 桁の数字が続きます。

- 2 桁の数字または文字 (大文字と小文字を区別しない)
- 7 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_latvia_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_latvia_eu_passport_number` つかったか、検索されます。
- 正規表現が `Regex_eu_passport_date1` DD.MM.YYYYY 形式の日付を検索するか、キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_latvia_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_latvia_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Latvia Passport Number -->
      <Entity id="23ae25ec-cc28-421b-b77a-3054eadf1ede" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase numurs
- pase numur
- pases numuri
- pases nr
- passeport no
- n° du Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="lithuania-drivers-license-number"></a>リトアニアの運転免許証番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 8 桁の数字

### <a name="pattern"></a>パターン

8 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_lithuania_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_lithuania_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Lithuania Driver's License Number -->
      <Entity id="86f7628b-e0f4-4dc3-9fbc-e4300e4c7d78" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver's_license_number

- vairuotojo pažymėjimas
- vairuotojo pažymėjimo numeris
- vairuotojo pažymėjimo numeriai

## <a name="lithuania-personal-code"></a>リトアニアの個人用コード
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースと区切り記号のない 11 桁の数字

### <a name="pattern"></a>パターン

スペースと区切り記号のない 11 桁の数字:

- 人の性別と出生世紀に対応する 1 桁の数字 (1 ~ 6)
- 生年月日に対応する 6 桁の数字 (YYMMDD)
- 生年月日のシリアル番号に対応する 3 桁の数字
- 1 つのチェックディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_lithuania_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_lithuania_eu_tax_file_number` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数  `Func_lithuania_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Lithuania Personal Code -->
      <Entity id="cd6d3786-8ec3-4524-a2cf-1e0095379171" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_lithuania_eu_telephone_number" />
            <Match idRef="Keywords_lithuania_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

- asmeninis skaitmeninis kodas
- asmens kodas
- 市民サービス番号
- mokesči id
- mokesči identifikavimas numeris
- mokesči identifikavimo numeris
- mokesčič numeris
- national identification number
- 個人用コード
- 個人の数値コード
- piliečio paslaugos numeris
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#
- unikalus identifikavimo kodas
- unikalus identifikavimo numeris
- 一意の ID 番号
- 一意の ID 番号
- uniqueidentityno#

## <a name="lithuania-passport-number"></a>リトアニアのパスポート番号

### <a name="format"></a>フォーマット

スペースまたは区切り記号を含む 8 桁の数字または文字

### <a name="pattern"></a>パターン

8 桁の数字または文字 (大文字と小文字は区別されません)

### <a name="checksum"></a>チェックサム

該当なし

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_lithuania_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_lithuania_eu_passport_number` つかったか、検索されます。
- 正規表現が DD MM YYYY の形式で日付を検索するか、キーワード `Regex_eu_passport_date3` が `Keywords_eu_passport_date` 見つかった

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_lithuania_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_lithuania_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Lithuania Passport Number -->
      <Entity id="1b79900f-047b-4c3f-846f-7d73b5534bce" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- paso numeris
- paso numeriai
- paso nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="luxemburg-drivers-license-number"></a>ルクセンブルクの運転免許証番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 6 桁の数字

### <a name="pattern"></a>パターン

6 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_luxemburg_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_luxemburg_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Luxemburg Driver's License Number -->
      <Entity id="89daf717-1544-4860-9a2e-fc9166dd8852" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver's_license_number

- fahrerlaubnis
- Führerschäin

## <a name="luxemburg-national-identification-number-natural-persons"></a>ルクセンブルクの国民識別番号 (自然人)
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースまたは区切り記号がない 13 桁の数字

### <a name="pattern"></a>パターン

13 桁の数字:

- 11 桁の数字
- 2 つのチェックの数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_luxemburg_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_luxemburg_eu_national_id_card` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数  `Func_luxemburg_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。


```xml
      <!-- Luxemburg National Identification Number (Natural persons) -->
      <Entity id="aaf661ed-29ec-426d-8bf9-880cad298ebb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- eindeutige id
- eindeutige id-nummer
- eindeutigeid#
- id personnelle
- idpersonnelle#
- idpersonnelle
- 個々のコード
- 個々の ID
- 個人識別
- 個々の ID
- numéro d'ID の担当者
- 個人用 ID
- 個人識別
- 個人の ID
- personalidno#
- personalidnumber#
- persönliche identifikationsnummer
- 一意の ID
- 一意の ID
- uniqueidkey#

## <a name="luxemburg-passport-number"></a>ルクセンブルクのパスポート番号

### <a name="format"></a>フォーマット

スペースまたは区切り記号を含む 8 桁の数字または文字

### <a name="pattern"></a>パターン

8 桁の数字または文字 (大文字と小文字は区別されません)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_luxemburg_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_luxemburg_eu_passport_number` つかったか、検索されます。
- 正規表現が DD MM YYYY の形式で日付を検索するか、キーワード `Regex_eu_passport_date3` が `Keywords_eu_passport_date` 見つかった

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_luxemburg_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_luxemburg_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Luxemburg Passport Number -->
      <Entity id="81d5c027-bed9-4421-91a0-3b2e55b3eb85" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- ausweisnummer
- ルクセンブルク パス
- ルクセンブルク パスポート
- ルクセンブルクのパスポート
- de passeport なし
- no-reisepass
- nr-reisepass
- numéro de passeport
- pass net
- pass nr
- passnummer
- passeport nombre
- reisepässe
- reisepass-nr
- reisepassnummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="luxemburg-national-identification-number-non-natural-persons"></a>ルクセンブルクの国民識別番号 (非自然人)

### <a name="format"></a>フォーマット

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の数字

- 2 桁
- オプションのスペース
- 3 桁の数字
- オプションのスペース
- 3 桁の数字
- オプションのスペース
- 2 桁
- 1 つのチェックディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_luxemburg_eu_tax_file_number_non_natural` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_luxemburg_eu_tax_file_number` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数  `Func_luxemburg_eu_tax_file_number_non_natural` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Luxemburg National Identification Number (Non-natural persons) -->
      <Entity id="84bffa3a-d805-4788-a613-b1e4df3804cf" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- carte de sécurité sociale
- étain non
- étain#
- 特定の d'impôt
- ルクセンブルグの税の識別
- numéro d'étain
- numéro d'id fiscal ルクセンブルク語
- numéro d'id fiscale
- social security
- sozialunterstützung
- sozialversécherung
- sozialversicherungsausweis
- steier id
- steier identifikatiounsnummer
- steier nummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#
- zinn#
- zinn
- zinnzahl


## <a name="malaysia-identification-card-number"></a>マレーシアの ID カード番号

### <a name="format"></a>フォーマット

省略可能なハイフンを含む 12 桁の数字

### <a name="pattern"></a>パターン

12 桁の数字:
- YYMMDD 形式の 6 桁の数字 (生年月日)
- ダッシュ (オプション)
- 2 文字の出生場所コード
- ダッシュ (オプション)
- 3 つのランダムな数字
- 1 桁の性別コード

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、Regex_malaysia_id_card_number一致するコンテンツを検索します。
- ユーザーからのキーワードKeyword_malaysia_id_card_number見つかりました。

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- デジタル アプリケーション カード
- i/c
- i/c いいえ
- ic
- ic いいえ
- id card
- ID カード
- Identity card
- k/p
- k/p いいえ
- kad akuan diri
- kad aplikasi デジタル
- kad pengenalan マレーシア
- kp
- kp いいえ
- mykad
- mykas
- mykid
- mypr
- mytentera
- マレーシアの ID カード
- マレーシアの ID カード
- nric
- 個人識別カード

## <a name="malta-drivers-license-number"></a>マルタの運転免許証番号

### <a name="format"></a>フォーマット

指定したパターンの 2 文字と 6 桁の組み合わせ

### <a name="pattern"></a>パターン

2 文字と 6 桁の組み合わせ:

- 2 文字 (大文字と小文字を区別しない数字または文字)
- スペース (オプション)
- 3 桁の数字
- スペース (オプション)
- 3 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_malta_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_malta_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Malta Driver's License Number -->
      <Entity id="a3bdaa4a-8371-4735-8fa5-56ee0fb4afc4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_malta_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver's_license_number

- liċenzja tas-sewqan
- liċenzji tas-sewwieq


## <a name="malta-identity-card-number"></a>マルタの ID カード番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

7 桁の数字の後に 1 文字

### <a name="pattern"></a>パターン

7 桁の数字の後に 1 文字が続きます。

- 7 桁
- "M、G、A、P、L、H、B、Z" の 1 文字 (大文字と小文字を区別しない)

### <a name="checksum"></a>チェックサム

該当なし

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_malta_eu_national_id_card` パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_malta_eu_national_id_card` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- 正規表現は、  `Regex_malta_eu_national_id_card` パターンに一致するコンテンツを検索します。

```xml
      <!-- Malta Identity Card Number -->
      <Entity id="854b36b3-a388-4ac8-a4ec-677c2b5e4356" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

- 市民サービス番号
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi数字の個人用
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 個人の数値コード
- 一意の ID 番号
- 一意の ID 番号
- uniqueidentityno#


## <a name="malta-passport-number"></a>マルタのパスポート番号

### <a name="format"></a>フォーマット

スペースまたは区切り記号のない 7 桁の数字

### <a name="pattern"></a>パターン

7 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_malta_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_malta_eu_passport_number` つかったか、検索されます。
- キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_malta_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_malta_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Malta Passport Number -->
      <Entity id="b2b21198-48f9-4d13-b2a5-03969bff0fb8" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
          <Match idRef="Keywords_eu_passport_date" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- Nru tal-passaport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="malta-tax-identification-number"></a>マルタの納税者番号

### <a name="format"></a>フォーマット

マルタ国民の場合:
- 指定したパターンの 7 桁の数字と 1 文字

マルタ以外の国民およびマルタ人のエンティティ:
- 9 桁

### <a name="pattern"></a>パターン

マルタ国民: 7 桁の数字と 1 文字

- 7 桁
- 1 文字 (大文字と小文字は区別されません)

マルタ以外の国民およびマルタのエンティティ: 9 桁

- 9 桁

### <a name="checksum"></a>チェックサム

該当なし

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現または  `Regex_malta_eu_tax_file_number`  パターン `Regex_malta_eu_tax_file_number_non_maltese_national` に一致するコンテンツを検索します。
- キーワードが  `Keywords_malta_eu_tax_file_number` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- 正規表現または  `Regex_malta_eu_tax_file_number` パターン `Regex_malta_eu_tax_file_number_non_maltese_national` に一致するコンテンツを検索します。

```xml
      <!-- Malta Tax ID Number -->
      <Entity id="ec830c63-65f4-45d0-9d8c-910dc8334b20" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- 市民サービス番号
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi数字の個人用
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 個人の数値コード
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#
- 一意の ID 番号
- 一意の ID 番号
- uniqueidentityno#


## <a name="medicare-beneficiary-identifier-mbi-card"></a>メディケア受益者識別子 (MBI) カード

### <a name="format"></a>フォーマット

11 文字の英数字パターン

### <a name="pattern"></a>パターン

- 1 ~ 9 の 1 桁
- S、L、O、I、B、Z を除く 1 文字
- S、L、O、I、B、Z を除く 1 桁または文字
- 1 桁
- オプションのハイフン
- S、L、O、I、B、Z を除く 1 文字
- S、L、O、I、B、Z を除く 1 桁または文字
- 1 桁
- オプションのハイフン
- S、L、O、I、B、Z を除く 2 つの文字
- 2 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_mbi_card` パターンに一致するコンテンツを検索します。
- キーワードが  `Keyword_mbi_card` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_mbi_card` パターンに一致するコンテンツを検索します。

```xml
    <!-- Medicare Beneficiary Identifier (MBI) card -->
      <Entity id="f753a286-f5cc-47e6-a592-4be25fd02591" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_mbi_card" />
          <Match idRef="Keyword_mbi_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_mbi_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_mbi_card"></a>Keyword_mbi_card

- mbi
- mbi#
- medicare 受益者#
- medicare 受益者識別子
- medicare 受益者なし
- medicare 受益者番号
- medicare 受益者#


## <a name="mexico-unique-population-registry-code-curp"></a>メキシコ固有の人口レジストリ コード (CURP)

### <a name="format"></a>フォーマット

18 文字の英数字パターン

### <a name="pattern"></a>パターン

- 4 文字 (大文字と小文字を区別しない)
- 有効な日付を示す 6 桁の数字
- 文字 - H/h または M/m
- 有効なメキシコの州コードを示す 2 文字
- 3 文字
- 1 文字または数字
- 1 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_mexico_population_registry_code` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keyword_mexico_population_registry_code` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数  `Func_mexico_population_registry_code` は、パターンに一致するコンテンツを検索します。

```xml
    <!-- Mexico Unique Population Registry Code (CURP) -->
      <Entity id="e905ad4d-5a74-406d-bf36-b1efca798af4" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_mexico_population_registry_code" />
          <Match idRef="Keyword_mexico_population_registry_code" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_mexico_population_registry_code" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_mexico_population_registry_code"></a>Keyword_mexico_population_registry_code

- Clave Única de Registro de Población
- Clave Unica de Registro de Poblacion
- 一意の母集団レジストリ コード 
- 一意の母集団コード
- CURP
- 個人用 ID
- 一意な ID
- personalid
- personalidnumber
- uniqueidkey
- uniqueidnumber
- clave única
- clave unica
- clave 個人用 Identidad
- 個人用 Identidad Clave
- ClaveÚnica
- claveunica
- clavepersonalIdentidad


## <a name="netherlands-citizens-service-bsn-number"></a>オランダの市民サービス (BSN) 番号

### <a name="format"></a>フォーマット

オプションのスペースを含む 8 桁または 9 桁の数字

### <a name="pattern"></a>パターン

89 桁の数字:
- 3 桁の数字
- スペース (オプション)
- 3 桁の数字
- スペース (オプション)
- 2 桁の 3 桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_netherlands_bsn一致するコンテンツを検索します。
- このページのKeyword_netherlands_bsnが見つかりました。
- チェックサムが渡される。

```xml
      <!-- Netherlands Citizen's Service (BSN) Number -->
      <Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_bsn" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

- bsn#
- bsn
- burgerservicenummer
- 市民サービス番号
- ユーザー番号
- 個人番号
- 個人の数値コード
- ユーザー関連の番号
- persoonlijk nummer
- persoonlijke numerieke コード
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- ソーシャル会計番号
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- 一意の ID 番号
- 一意の ID 番号
- uniqueidentityno#

## <a name="netherlands-drivers-license-number"></a>オランダの運転免許証番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 10 桁の数字

### <a name="pattern"></a>パターン

10 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_netherlands_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_netherlands_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Netherlands Driver's License Number -->
      <Entity id="6247fbea-ab80-4be5-8233-308b7c031401" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
            </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver's_license_number

- permis de conduire
- rijbewijs
- rijbewijsnummer
- rijbewijzen
- rijbewijs nummer
- rijbewijsnummers


## <a name="netherlands-passport-number"></a>オランダのパスポート番号

### <a name="format"></a>フォーマット

スペースまたは区切り記号がない 9 文字または数字

### <a name="pattern"></a>パターン

9 文字または数字

### <a name="checksum"></a>チェックサム

該当なし

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_netherlands_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_netherlands_eu_passport_number` つかったか、検索されます。
- 正規表現は `Regex_netherlands_eu_passport_date` 、DD MMM/MMM YYYYY 形式の日付を検索します (例 - 26 MAA/MAR 2012)

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_netherlands_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_netherlands_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Netherlands Passport Number -->
      <Entity id="61786727-bafd-45f6-94d9-888d815e228e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Regex_netherlands_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- paspoort nummer
- paspoortnummers
- paspoortnummer
- paspoort nr

## <a name="netherlands-tax-identification-number"></a>オランダの納税者番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースまたは区切り記号のない 9 桁の数字

### <a name="pattern"></a>パターン

9 桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_netherlands_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_netherlands_eu_tax_file_number` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数  `Func_netherlands_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Netherlands Tax Identification Number -->
      <Entity id="01f42a64-eba7-4892-a67b-398237e4ade2" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- btw nummer
- hollânske 税の識別
- hulandes impuesto id number
- hulandes impuesto ID
- identificatienummer belasting
- identificatienummer van belasting
- impuesto ID 番号
- impuesto number
- nederlands belasting id nummer
- nederlands belasting identificatie
- nederlands belasting identificatienummer
- nederlands belastingnummer
- nederlandse belasting identificatie
- オランダの税金の識別
- netherland の税の識別
- オランダのスズ
- netherland's tin
- tax id
- 税の識別なし
- 税の識別番号
- 税の識別 tal
- tax no#
- tax no
- 税番号
- 税登録番号
- tax tal
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#


## <a name="netherlands-value-added-tax-number"></a>オランダの付加価値税番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

14 文字の英数字パターン

### <a name="pattern"></a>パターン

14 文字の英数字パターン:

- N または n
- L または l
- オプションのスペース、ドット、またはハイフン
- 9 桁
- オプションのスペース、ドット、またはハイフン
- B または b
- 2 桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_netherlands_value_added_tax_number一致するコンテンツを検索します。
- このページのKeywords_netherlands_value_added_tax_numberが見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_netherlands_value_added_tax_number一致するコンテンツを検索します。

```xml
      <!-- Netherlands Value Added Tax Number -->
      <Entity id="4f320d9b-4972-41ae-b337-88d499bb1ade" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
          <Match idRef="Keywords_netherlands_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_netherlands_value_added_tax_number"></a>Keyword_netherlands_value_added_tax_number

- vat 番号
- vat いいえ
- vat#
- wearde tafoege tax getal
- btw nûmer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>ニュージーランドの銀行口座番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

14 桁から 16 桁のパターン (オプションの区切り文字付き)

### <a name="pattern"></a>パターン

14 桁から 16 桁のパターン (オプションの区切り記号付き):

- 2 桁
- オプションのハイフンまたはスペース
- 3 ~ 4 桁
- オプションのハイフンまたはスペース
- 7 桁
- オプションのハイフンまたはスペース
- 2 ~ 3 桁の数字
- オプションのハイフンまたはスペース

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_new_zealand_bank_account_number一致するコンテンツを検索します。
- ユーザーのキーワードKeywords_new_zealand_bank_account_number見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_new_zealand_bank_account_number一致するコンテンツを検索します。

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zFealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- account number
- 銀行口座
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>ニュージーランドの運転免許証番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

8 文字の英数字パターン

### <a name="pattern"></a>パターン

8 文字の英数字パターン

- 2 文字
- 6 桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数Func_newzealand_driver_license_number一致するコンテンツを検索します。
- ユーザーのキーワードKeywords_newzealand_driver_license_number見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数Func_newzealand_driver_license_number一致するコンテンツを検索します。

```xml
      <!-- New Zealand Driver License Number -->
      <Entity id="1924b377-d287-49c9-a737-cfe7a8a2615a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
          <Match idRef="Keywords_newzealand_driver_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_new_zealand_drivers_license_number"></a>Keyword_new_zealand_drivers_license_number

- driverlicence
- driverlicences
- ドライバー lic
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslicence
- driverslicences
- ドライバー lic
- ドライバー lics
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's licence
- 運転免許証
- driverlic#
- driverlics#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- 運転免許証#
- international driving permit
- international driving permits
- nz 自動車協会
- ニュージーランド自動車協会


## <a name="new-zealand-inland-revenue-number"></a>ニュージーランド内陸の収益番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

8 桁または 9 桁の数字 (オプションの区切り記号付き)

### <a name="pattern"></a>パターン

8 桁または 9 桁の数字 (オプションの区切り記号付き)

- 2 桁または 3 桁の数字
- オプションのスペースまたはハイフン
- 3 桁の数字
- オプションのスペースまたはハイフン
- 3 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_new_zealand_inland_revenue_number一致するコンテンツを検索します。
- このページのKeywords_new_zealand_inland_revenue_numberが見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_new_zealand_inland_revenue_number一致するコンテンツを検索します。

```xml
      <!-- New Zealand Inland Revenue Number -->
      <Entity id="dd0fe2bc-7bcf-455f-bac1-83b1e3eb25fd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
          <Match idRef="Keywords_new_zealand_inland_revenue_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_new_zealand_inland_revenue_number"></a>Keyword_new_zealand_inland_revenue_number

- ird いいえ。
- ird いいえ#
- nz ird
- ニュージーランド ird
- ird 番号
- 内陸の収益番号


## <a name="new-zealand-ministry-of-health-number"></a>ニュージーランド保健省番号

### <a name="format"></a>フォーマット

3 文字と 4 桁の数字

### <a name="pattern"></a>パターン

- 'I' と 'O' 以外の 3 文字 (大文字と小文字は区別されません)
- 4 桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数 Func_new_zealand_ministry_of_health_number がパターンに一致するコンテンツを検出した。
- Keyword_nz_terms のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_new_zealand_ministry_of_health_number がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
    <!-- New Zealand Health Number -->
    <Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
          <Match idRef="Keyword_nz_terms" />
      </Pattern>
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
       </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI
- New Zealand
- 国民健康指数
- NHI#
- 国民健康指数#

## <a name="new-zealand-social-welfare-number"></a>ニュージーランドのソーシャル 福利厚生番号

この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

9 桁

### <a name="pattern"></a>パターン

9 桁

- 3 桁の数字
- オプションのハイフン
- 3 桁の数字
- オプションのハイフン
- 3 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_newzealand_social_welfare_number一致するコンテンツを検索します。
- ユーザーのキーワードKeywords_newzealand_social_welfare_number見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数はFunc_newzealand_social_welfare_number一致するコンテンツを検索します。

```xml
      <!-- Newzealand Social Welfare Number -->
      <Entity id="20f3c48d-4ac1-4cd2-86bd-34ecc1826e9d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
          <Match idRef="Keywords_newzealand_social_welfare_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- ソーシャル 福利厚生#
- ソーシャル 福利厚生#
- ソーシャル 福利厚生 No.
- ソーシャル 福利厚生番号
- swn#


## <a name="norway-identification-number"></a>ノルウェーの ID 番号

### <a name="format"></a>フォーマット

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の数字:
- DDMMYY 形式の 6 桁の数字 (生年月日)
- 3 桁の個人番号
- 2 つのチェックの数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_norway_id_number一致するコンテンツを検索します。
- このページのKeyword_norway_id_numberが見つかりました。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_norway_id_numbe一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Personal identification number
- Norwegian ID Number
- ID Number
- ID
- Personnummer
- Fødselsnummer


## <a name="philippines-unified-multi-purpose-identification-number"></a>フィリピンの統合多目的識別番号

### <a name="format"></a>フォーマット

ハイフンで区切られた 12 桁の数字

### <a name="pattern"></a>パターン

12 桁の数字:
- 4 桁
- ハイフン
- 7 桁
- ハイフン
- 1 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、Regex_philippines_unified_id一致するコンテンツを検索します。
- ユーザーのキーワードKeyword_philippines_id見つかりました。

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- Unified Multi-Purpose ID
- UMID
- Identity Card
- Pinag-isang Multi-Layunin ID

## <a name="poland-drivers-license-number"></a>ポーランドの運転免許証番号

### <a name="format"></a>フォーマット

2 つのスラッシュを含む 14 桁

### <a name="pattern"></a>パターン

14 桁の数字と 2 つのスラッシュ:

- 5 桁
- スラッシュ
- 2 桁
- スラッシュ
- 7 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_poland_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_poland_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Poland Driver's License Number -->
      <Entity id="24d51f99-ee9e-4060-a077-cae58cab1ee4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_poland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver's_license_number

- prawo jazdy
- prawa jazdy

## <a name="poland-identity-card"></a>ポーランドの ID カード

### <a name="format"></a>フォーマット

3 文字と 6 桁の数字

### <a name="pattern"></a>パターン

3 文字 (大文字と小文字を区別しない) の後に 6 桁の数字が続く

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_polish_national_id がパターンに一致するコンテンツを検出した。
- Keyword_polish_national_id_passport_number のキーワードを検出した。
- チェックサムが渡される。

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Dowód osobisty
- Numer dowodu osobistego
- Nazwa i numer dowodu osobistego
- Nazwa i nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- dow. os.



## <a name="poland-national-id-pesel"></a>ポーランドの国民 ID (PESEL)

### <a name="format"></a>フォーマット

11 桁の数字

### <a name="pattern"></a>パターン

- YYMMDD 形式の生年月日を表す 6 桁の数字
- 4 桁
- 1 つのチェックディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数 Func_pesel_identification_number がパターンに一致するコンテンツを検出した。
- Keyword_pesel_identification_number のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_pesel_identification_number がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
      <!-- Poland National ID (PESEL) -->
      <Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_pesel_identification_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_pesel_identification_number"></a>Keyword_pesel_identification_number

- dowód osobisty
- dowódosobisty
- niepowtarzalny numer
- niepowtarzalnynumer
- nr.-pesel
- nr-pesel
- numer identyfikacyjny
- pesel
- tożsamości narodowej


## <a name="poland-passport-number"></a>ポーランドのパスポート番号
この機密情報の種類エンティティは、EU Passport Number 機密情報の種類に含まれています。 また、スタンドアロンの機密情報の種類エンティティとして利用できます。

### <a name="format"></a>フォーマット

2 文字と 7 桁

### <a name="pattern"></a>パターン

2 文字 (大文字と小文字を区別しない) の後に 7 桁の数字が続く

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数 `Func_polish_passport_number_v2` は、パターンに一致するコンテンツを検索します。
- チェックサムが渡される。
- キーワードが見 `Keywords_eu_passport_number` `Keyword_polish_national_passport_number` つかったか、検索されます。
- キーワードが `Keywords_eu_passport_date` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数 `Func_polish_passport_number_v2` は、パターンに一致するコンテンツを検索します。
- チェックサムが渡される。
- キーワードが見 `Keywords_eu_passport_number` `Keyword_polish_national_passport_number` つかったか、検索されます。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数 `Func_polish_passport_number_v2` は、パターンに一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
      <!-- Poland Passport Number -->
      <Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_passport_number_v2" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keyword_polish_national_passport_number"></a>Keyword_polish_national_passport_number

- numer paszportu
- numery paszportów
- numery paszportowe
- nr paszportu
- nr. paszportu
- nr paszportów
- n° パスポート
- passeport n°

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="poland-regon-number"></a>ポーランド REGON 番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

9 桁または 14 桁の番号

### <a name="pattern"></a>パターン

9 桁または 14 桁の番号:

- 9 桁または
- 9 桁
- ハイフン
- 5 桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_polish_regon_number一致するコンテンツを検索します。
- このページのKeywords_polish_regon_numberが見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数はFunc_polish_regon_number一致するコンテンツを検索します。

```xml
      <!-- Polish REGON Number  -->
      <Entity id="fc87b421-f437-4f8b-b739-29a735ead0d9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_regon_number" />
          <Match idRef="Keywords_polish_regon_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_regon_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- regon id
- 統計番号
- 統計 ID
- 統計なし
- regon number
- regonid#
- regonno#
- 会社 ID
- companyid#
- companyidno#
- numer statystyczny
- numeru regon
- numerstatystyczny#
- numeruregon#


## <a name="poland-tax-identification-number"></a>ポーランドの納税者番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースまたは区切り記号がない 11 桁の数字

### <a name="pattern"></a>パターン

11 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_poland_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_poland_eu_tax_file_number` 見つかりました。


```xml
      <!-- Poland Tax Identification Number -->
      <Entity id="1ff28b4d-40f2-49e9-b677-9606a88e2bca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

- nip#
- nip
- numer identyfikacji podatkowej
- numeridentyficjipodatkowej#
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#
- vat id#
- vat id
- vat いいえ
- vat 番号
- vatid#
- vatid
- vatno#


## <a name="portugal-citizen-card-number"></a>ポルトガルの市民カード番号

### <a name="format"></a>フォーマット

8 桁

### <a name="pattern"></a>パターン

8 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、Regex_portugal_citizen_card一致するコンテンツを検索します。
- ユーザーからのキーワードKeyword_portugal_citizen_card見つかりました。

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- bilhete de identidade
- cartão de cidadão
- 市民カード
- ドキュメント番号
- documento de identificação
- id 番号
- ID なし
- identification number
- ID カードなし
- ID カード番号
- 国の ID カード
- nic
- número bi de ポルトガル
- número de identificação civil
- número de identificação Fiscal
- número do documento
- ポルトガルのバイナンバー


## <a name="portugal-drivers-license-number"></a>ポルトガルの運転免許証番号

### <a name="format"></a>フォーマット

2 つのパターン - 2 文字の後に特殊文字を含む 5 ~ 8 桁の数字

### <a name="pattern"></a>パターン

パターン 1: 2 文字の後に特殊文字を含む 5/6 が続きます。
- 2 文字 (大文字と小文字は区別されません)
- ハイフン 1 つ 
- 5 桁または 6 桁
- スペース
- 1 桁の数字

パターン 2: 1 文字の後に特殊文字を含む 6/8 桁の数字が続きます。
- 1 文字 (大文字と小文字は区別されません)
- ハイフン 1 つ 
- 6 桁または 8 桁の数字
- スペース
- 1 桁の数字


### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_portugal_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_portugal_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Portugal Driver's License Number -->
      <Entity id="977f1e5a-2c33-4bcc-b516-95bb275cff23" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_portugal_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver's_license_number

- carteira de motorista
- carteira motorista
- carteira de habilitação
- carteira habilitação
- número de licença
- número licença
- permissão de condução
- permissão condução
- Licença condução ポルトガル
- carta de condução

## <a name="portugal-passport-number"></a>ポルトガルのパスポート番号

### <a name="format"></a>フォーマット

1 文字の後にスペースまたは区切り記号がない 6 桁の数字

### <a name="pattern"></a>パターン

1 文字の後に 6 桁の数字が続きます。

- 1 文字 (大文字と小文字は区別されません)
- 6 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_portugal_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_portugal_eu_passport_number` つかったか、検索されます。
- 正規表現が `Regex_eu_passport_date1` DD.MM.YYYYY 形式の日付を検索するか、キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_portugal_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_portugal_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Portugal Passport Number -->
      <Entity id="080a52fd-a7bc-431e-b54d-51f08f59db11" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do passaporte
- ポルトガルのパスポート
- ポルトガル語のパスポート
- ポルトガル語 passaporte
- passaporte nº
- passeport nº
- números de passaporte
- ポルトガルのパスポート
- número passaporte
- números passaporte

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="portugal-tax-identification-number"></a>ポルトガルの納税者番号

### <a name="format"></a>フォーマット

オプションのスペースを含む 9 桁の数字

### <a name="pattern"></a>パターン

- 3 桁の数字
- オプションのスペース
- 3 桁の数字
- オプションのスペース
- 3 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_portugal_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_portugal_eu_tax_file_number` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数  `Func_portugal_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Portugal Tax Identification Number -->
      <Entity id="65372402-3131-4f1e-9983-4439841d1f15" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

- cpf#
- cpf
- nif#
- nif
- número de identificação fisca
- numero fiscal
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#


## <a name="romania-drivers-license-number"></a>ルーマニアの運転免許証番号

### <a name="format"></a>フォーマット

1 文字の後に 8 桁の数字を付け

### <a name="pattern"></a>パターン

1 文字の後に 8 桁の数字が続きます。
- 1 文字 (大文字と小文字を区別しない) または数字
- 8 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_romania_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_romania_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Romania Driver's License Number -->
      <Entity id="b5511ace-2fd8-4ae4-b6fc-c7c6e4689e3c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_romania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver's_license_number

- permis de
- permisului de conducere
- permisului
- permisele de conducere
- permisele
- permis

## <a name="romania-personal-numeric-code-cnp"></a>ルーマニアの個人数値コード (CNP)
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースと区切り記号のない 13 桁の数字

### <a name="pattern"></a>パターン

- 1 ~ 9 の 1 桁
- 生年月日 (YYMMDD) を表す 6 桁の数字
- 2 桁の数字 (01 ~ 52 または 99)
- 4 桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_romania_eu_national_id_card` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_romania_eu_national_id_card` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数  `Func_romania_eu_national_id_card` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Romania Personal Numerical Code (CNP) -->
      <Entity id="eb5fa399-fe28-4c67-8188-d63a616ed89c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

- cnp#
- cnp
- cod identificare personal
- cod 数値個人用
- cod unic identificare
- codnumericpersonal#
- codul fiscal nr.
- identificarea Fiscală nr#
- id-ul taxei
- 保険番号
- insurancenumber#
- 国 ID#
- national id
- national identification number
- număr identificare Personal
- număr identitate
- număr 個人用 unic
- număridentitate#
- număridentitate
- numărpersonalunic#
- numărpersonalunic
- număru de identificare Fiscală
- numărul de identificare Fiscală
- 個人の数値コード
- pin#
- pin
- tax file no
- tax file number
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#
- 一意の ID 番号
- 一意の ID 番号
- uniqueidentityno#
- uniqueidentityno

## <a name="romania-passport-number"></a>ルーマニアのパスポート番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 8 桁または 9 桁の数字

### <a name="pattern"></a>パターン

8 桁または 9 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_romania_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_romania_eu_passport_number` つかったか、検索されます。
- 正規表現は `Regex_romania_eu_passport_date` 、DD MMM/MMM YY (例- 01 FEB/FEB 10) 形式の日付を検索するか、キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_romania_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_romania_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Romania Passport Number -->
      <Entity id="5d31b90c-7fe2-4a76-a14b-767b8fd19d6c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_romania_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numărul paărul paăaportului numarul pasaportului numerele pa ăaportului Paăaport nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="russia-passport-number-domestic"></a>ロシアのパスポート番号 (国内)
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

10 桁の番号

### <a name="pattern"></a>パターン

10 桁の番号:

- 2 桁
- オプションのスペースまたはハイフン
- 2 桁
- オプションのスペース
- 6 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現はRegex_Russian_Passport_Number_Domestic一致するコンテンツを検索します。
- ユーザーのキーワードKeyword_Russian_Passport_Number見つかりました。

```xml
      <!-- Russian Passport Number Domestic -->
      <Entity id="76ec2f5d-cedb-48e1-8070-1998794af445" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_Domestic" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_russia_passport_number_domestic"></a>Keyword_russia_passport_number_domestic

- passport number
- パスポートなし
- パスポート#
- パスポート ID
- passportno#
- passportnumber#
- паспорт нет
- паспорт ID
- pоссийской паспорт
- pусский номер паспорта
- паспорт#
- паспортid#
- номер паспорта
- номерпаспорта#


## <a name="russia-passport-number-international"></a>ロシアのパスポート番号国際
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

9 桁の数字

### <a name="pattern"></a>パターン

9 桁の番号:

- 2 桁
- オプションのスペースまたはハイフン
- 7 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現はRegex_Russian_Passport_Number_International一致するコンテンツを検索します。
- ユーザーのキーワードKeyword_Russian_Passport_Number見つかりました。

```xml
      <!-- Russian Passport Number International -->
      <Entity id="ac5f4878-75e4-4b82-af2d-02e13ea9f411" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_International" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_russia_passport_number_international"></a>Keywords_russia_passport_number_international

- passport number
- パスポートなし
- パスポート#
- パスポート ID
- passportno#
- passportnumber#
- паспорт нет
- паспорт ID
- pоссийской паспорт
- pусский номер паспорта
- паспорт#
- паспортid#
- номер паспорта
- номерпаспорта#


## <a name="saudi-arabia-national-id"></a>サウジアラビアの国民 ID

### <a name="format"></a>フォーマット

10 桁の数字

### <a name="pattern"></a>パターン

10 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現 Regex_saudi_arabia_national_id がパターンに一致するコンテンツを検出した。
- Keyword_saudi_arabia_national_id のキーワードを検出した。

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- Identification Card
- I card number
- ID number
- الوطنية الهوية بطاقة رقم


## <a name="singapore-national-registration-identity-card-nric-number"></a>シンガポールの国民登録 ID カード (NRIC) 番号

### <a name="format"></a>フォーマット

9 文字と数字

### <a name="pattern"></a>パターン

- 9 文字と数字:
- 文字 "F"、"G"、"S"、または "T" (大文字と小文字を区別しない)
- 7 桁
- 英字チェックの数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、Regex_singapore_nric一致するコンテンツを検索します。
- このページのKeyword_singapore_nric見つかりました。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、Regex_singapore_nric一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- National Registration Identity Card
- Identity Card Number
- NRIC
- IC
- Foreign Identification Number
- FIN
- 身份证
- 身份證

## <a name="slovakia-drivers-license-number"></a>スロバキアの運転免許証番号

### <a name="format"></a>フォーマット

1 文字の後に 7 桁の数字を付け

### <a name="pattern"></a>パターン

1 文字の後に 7 桁の数字を付け

- 1 文字 (大文字と小文字を区別しない) または数字
- 7 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_slovakia_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_slovakia_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Slovakia Driver's License Number -->
      <Entity id="14240c22-b6de-4ce5-a90b-137f74252513" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver's_license_number

- vodičský preukaz
- vodičské preukazy
- vodičského preukazu
- vodičských preukazov

## <a name="slovakia-personal-number"></a>スロバキアの個人番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

オプションの円記号を含む 9 桁または 10 桁

### <a name="pattern"></a>パターン

- 生年月日を表す 6 桁の数字
- 省略可能なスラッシュ (/)
- 3 桁の数字
- オプションのチェックディジット 1 つ

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_slovakia_eu_national_id_card` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_slovakia_eu_national_id_card` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数  `Func_slovakia_eu_national_id_card` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Slovakia Personal Number -->
      <Entity id="951c26b7-3b35-4f73-924b-15dd599cb9ab" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- 出生番号
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- id 番号
- ID なし
- identification number
- identifikačná karta č
- identifikačné číslo
- ID カードなし
- ID カード番号
- národná identifikačná značka č
- 国番号
- nationalnumber#
- nemzeti személyazonosító igazolvány
- personalidnumber#
- rč
- rodne cislo
- rodné číslo
- social security number
- ssn#
- ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- tax file no
- tax file number
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#

## <a name="slovakia-passport-number"></a>スロバキアのパスポート番号

### <a name="format"></a>フォーマット

1 桁または文字の後にスペースまたは区切り記号を付けない 7 桁の数字

### <a name="pattern"></a>パターン

1 桁または文字 (大文字と小文字を区別しない) の後に 7 桁の数字が続く

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_slovakia_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_slovakia_eu_passport_number` つかったか、検索されます。
- 正規表現が `Regex_eu_passport_date1` DD.MM.YYYYY 形式の日付を検索するか、キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_slovakia_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_slovakia_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Slovakia Passport Number -->
      <Entity id="238e1f08-d80e-4793-af33-9b57918335b7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- číslo pasu
- čísla pasov
- pas č.
- パスポート n°
- n° パスポート

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="slovenia-drivers-license-number"></a>スロベニアの運転免許証番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 9 桁の数字

### <a name="pattern"></a>パターン

9 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_slovenia_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_slovenia_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Slovenia Driver's License Number -->
      <Entity id="d5bc089a-f2ee-433d-a6b1-5c253051d6f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver's_license_number

- vozniško dovoljenje
- vozniška številka ライセンス
- vozniških dovoljenj
- številka vozniškega dovoljenja
- številke vozniških dovoljenj

## <a name="slovenia-unique-master-citizen-number"></a>スロベニアの一意のマスター市民番号

この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースまたは区切り記号のない 13 桁の数字

### <a name="pattern"></a>パターン

指定したパターンの 13 桁:

- "LLL" が生年月日の最後の 3 桁に対応する生年月日 (DDMMLLL) に対応する 7 桁の数字
- 出生領域 "50" に対応する 2 桁の数字
- 同じ日に生まれた人の性別とシリアル番号の組み合わせに対応する 3 桁の数字。 男性は 000 ~499、女性は 500 ~999 です。
- 1 つのチェックディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_slovenia_eu_national_id_card` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_slovenia_eu_national_id_card` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数  `Func_slovenia_eu_national_id_card` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Slovenia Unique Master Citizen Number -->
      <Entity id="68948b27-803d-41e4-adf1-13e05eb541bb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- edinstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- id card
- identification number
- identifikacijska številka
- Identity card
- nacionalna id
- nacionalni potni リスト
- national id
- osebna izkaznica
- osebni koda
- osebni ne
- osebni številka
- 個人用コード
- 個人番号
- 個人の数値コード
- številka državljana
- 一意の市民番号
- 一意の ID 番号
- 一意の ID 番号
- 一意のマスター市民番号
- 一意の登録番号
- uniqueidentityno#
- uniqueidentityno#

## <a name="slovenia-passport-number"></a>スロベニアのパスポート番号

### <a name="format"></a>フォーマット

2 文字の後に 7 桁の数字が続き、スペースまたは区切り記号は使用されません。

### <a name="pattern"></a>パターン

2 文字の後に 7 桁の数字が続きます。

- 文字 "P"
- 大文字 1 文字
- 7 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_slovenia_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_slovenia_eu_passport_number` つかったか、検索されます。
- 正規表現が `Regex_eu_passport_date1` DD.MM.YYYYY 形式の日付を検索するか、キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_slovenia_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_slovenia_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Slovenia Passport Number -->
      <Entity id="235b7976-7bbe-4df5-bb40-08678e749d1a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- številka potnega lista
- potek veljavnosti
- potni リスト#
- datum rojstva
- potni リスト
- številke potnih listov

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="slovenia-tax-identification-number"></a>スロベニアの納税者番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースまたは区切り記号がない 8 桁の数字

### <a name="pattern"></a>パターン

- 1 ~ 9 の 1 桁
- 6 桁
- 1 つのチェックディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_slovenia_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_slovenia_eu_tax_file_number` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数  `Func_slovenia_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Slovenia Tax Identification Number -->
      <Entity id="e47b071e-c352-4d70-8241-8c215ad65505" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
          <Match idRef="Keywords_slovenia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

- davčna številka
- identifikacijska številka davka
- številka davčne datoteke
- tax file no
- tax file number
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#


## <a name="south-africa-identification-number"></a>南アフリカの ID 番号

### <a name="format"></a>フォーマット

省略可能なスペースを含む 13 桁の数字

### <a name="pattern"></a>パターン

13 桁の数字:
- YYMMDD 形式の 6 桁の数字 (生年月日)
- 4 桁
- 1 桁の市民権インジケーター
- 数字 "8" または "9"
- 1 桁(チェックサム桁)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数Func_south_africa_identification_number一致するコンテンツを検索します。
- このページのKeyword_south_africa_identification_numberが見つかりました。
- チェックサムが渡される。

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- Identity card
- ID
- ID

## <a name="south-korea-resident-registration-number"></a>韓国居住者登録番号

### <a name="format"></a>フォーマット

ハイフンを 1 つ含む 13 桁の数字

### <a name="pattern"></a>パターン

13 桁の数字:
- YYMMDD 形式の 6 桁の数字 (生年月日)
- ハイフン
- 世紀と性別によって決まる 1 桁の数字
- 4 桁の出生地域コード
- 前の番号が同一のユーザーを区別するために使用される 1 桁の数字
- チェックの数字を指定します。

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_south_korea_resident_number一致するコンテンツを検索します。
- ユーザーのキーワードKeyword_south_korea_resident_number見つかりました。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_south_korea_resident_number一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- National ID card
- Citizen's Registration Number
- Jumin deungnok beonho
- RRN
- 주민등록번호

## <a name="spain-drivers-license-number"></a>スペインの運転免許証番号

### <a name="format"></a>フォーマット

8 桁の数字の後に 1 文字

### <a name="pattern"></a>パターン

8 桁の数字の後に 1 文字が続きます。

- 8 桁
- 1 桁または 1 文字 (大文字と小文字は区別されません)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- パターンに  `Func_spain_eu_DL_and_NI_number_citizen` 一 `Func_spain_eu_DL_and_NI_number_foreigner` 致するコンテンツを関数または検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_spain_eu_driver's_license_number` つかったか、検索されます。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- パターンに  `Func_spain_eu_DL_and_NI_number_citizen` 一 `Func_spain_eu_DL_and_NI_number_foreigner` 致するコンテンツを関数または検索します。

```xml
      <!-- Spain Driver's License Number -->
      <Entity id="d5a82922-b501-4f40-8868-341321146aa2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver's_license_number

- permiso de conducción
- permiso
- licencia de
- licencia
- permiso
- permiso de
- permisos de
- permisos
- carnet
- carnet de
- licencia de manejo
- licencia manejo

## <a name="spain-dni"></a>スペイン DNI

この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

8 桁の数字の後に 1 文字

### <a name="pattern"></a>パターン

7 桁の数字の後に 1 文字

- 8 桁
- オプションのスペースまたはハイフン
- 1 つのチェック文字 (大文字と小文字は区別されません)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- パターンに  `Func_spain_eu_DL_and_NI_number_citizen` 一 `Func_spain_eu_DL_and_NI_number_foreigner` 致するコンテンツを関数または検索します。
- キーワードが  `Keywords_spain_eu_national_id_card"` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- パターンに  `Func_spain_eu_DL_and_NI_number_citizen` 一 `Func_spain_eu_DL_and_NI_number_foreigner` 致するコンテンツを関数または検索します。


```xml
      <!-- Spain DNI -->
      <Entity id="8e6251b9-47b4-40e8-a42b-0f80876be192" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- carné de identidad
- dni#
- dni
- dninúmero#
- documento nacional de identidad
- identidad único
- identidadúnico#
- 保険番号
- national identification number
- 国の ID
- nationalid#
- nationalidno#
- nie#
- nie
- nienúmero#
- número de identificación
- número nacional identidad
- 個人識別番号
- 個人 ID なし
- 一意の ID 番号
- uniqueid#

## <a name="spain-passport-number"></a>スペインのパスポート番号

### <a name="format"></a>フォーマット

8 文字または 9 文字の文字と数字の組み合わせで、スペースや区切り記号はありません。

### <a name="pattern"></a>パターン

文字と数字の 8 文字または 9 文字の組み合わせ。

- 2 桁の数字または文字
- 1 桁または 1 文字 (オプション)
- 6 桁

### <a name="checksum"></a>チェックサム

該当なし

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、  `Regex_spain_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_spain_eu_passport_number` つかったか、検索されます。
- 正規表現が `Regex_spain_eu_passport_date` DD-MM-YYYY 形式の日付を検索するか、キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_spain_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_passport_number` `Keywords_spain_eu_passport_number` つかったか、検索されます。

```xml
      <!-- Spain Passport Number -->
      <Entity id="d17a57de-9fa5-4e9f-85d3-85c26d89686e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_spain_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- libreta pasaporte
- número pasaporte
- españa pasaporte
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte no
- パスポート n°
- n° パスポート
- pasaporte No.
- pasaporte n°
- スペインのパスポート

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="spain-social-security-number-ssn"></a>スペインの社会保障番号 (SSN)


### <a name="format"></a>フォーマット

11 ～ 12 桁の数字

### <a name="pattern"></a>パターン

11 ~ 12 桁の数字:
- 2 桁
- スラッシュ (省略可能)
- 7 桁から 8 桁
- スラッシュ (省略可能)
- 2 桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数 Func_spanish_social_security_number がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。
- - キーワードが  `Keywords_spain_eu_ssn_or_equivalent` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_spanish_social_security_number がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
    <!-- Spain SSN -->
    <Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85" relaxProximity="true" >
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spanish_social_security_number" />
          <Match idRef="Keywords_spain_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spanish_social_security_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- ssn
- ssn#
- socialsecurityno
- 社会保障なし
- social security number
- número de la seguridad social

## <a name="spain-tax-identification-number"></a>スペインの納税者番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

指定したパターンの 7 桁または 8 桁の数字と 1 文字または 2 文字

### <a name="pattern"></a>パターン

スペインの国民 ID カードを持つスペインの自然人:

- 8 桁
- 大文字 1 文字 (大文字と小文字を区別)

スペイン国民 ID カードのない非居住者のスペイン語

- 1 つの大文字 "L" (大文字と小文字を区別)
- 7 桁
- 大文字 1 文字 (大文字と小文字を区別)

スペイン国民 ID カードのない 14 歳未満のスペイン居住者:

- 1 つの大文字 "K" (大文字と小文字を区別)
- 7 桁
- 大文字 1 文字 (大文字と小文字を区別)

外国人の身分証明番号を持つ外国人

- "X"、"Y"、または "Z" である 1 つの大文字 (大文字と小文字を区別)
- 7 桁
- 大文字 1 文字 (大文字と小文字を区別)

外国人の身分証明番号を持つ外国人

- "M" の 1 つの大文字 (大文字と小文字を区別)
- 7 桁
- 大文字 1 文字 (大文字と小文字を区別)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- パターンに  `Func_spain_eu_tax_file_number` 一 `Func_spain_eu_DL_and_NI_number_citizen` 致するコンテンツを関数または検索します。
- キーワードが  `Keywords_spain_eu_tax_file_number` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- パターンに  `Func_spain_eu_tax_file_number` 一 `Func_spain_eu_DL_and_NI_number_citizen` 致するコンテンツを関数または検索します。

```xml
      <!-- Spain Tax Identification Number -->
      <Entity id="10f0d113-b0e1-47dc-872a-a4f45b9376a3" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- cif
- cifid#
- cifnúmero#
- número de contribuyente
- número de identificación Fiscal
- número de impuesto corporativo
- spanishcifid#
- spanishcifid
- spanishcifno#
- spanishcifno
- tax file no
- tax file number
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#


## <a name="sql-server-connection-string"></a>SQL Server接続文字列

### <a name="format"></a>フォーマット

文字列 "User Id"、"User ID"、"uid"、または "UserId" の後に、以下のパターンで概説されている文字と文字列が続きます。

### <a name="pattern"></a>パターン

- 文字列 "User Id"、"User ID"、"uid"、または "UserId"
- 1 ~ 200 文字の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- "pwd" の前に小文字が付かされていない文字列 "Password" または "pwd"
- 等号 (=)
- ドル記号 ($)、パーセント記号 (%)、記号 (> より大きい)、記号 (@)、引用符 (")、セミコロン (;)、左中かっこ([)、または左かっこ ({) 以外の文字
- セミコロンではない 7 ~ 128 文字の任意の組み合わせ (;)、スラッシュ (/)、または引用符 (")
- セミコロン (;)または引用符 (")

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、CEP_Regex_SQLServerConnectionString一致するコンテンツを検索します。
- ユーザーからのCEP_GlobalFilterが見つかりません。
- パターンに一CEP_PasswordPlaceHolder一致するコンテンツが見当たらない正規表現。
- パターンに一CEP_CommonExampleKeywords一致するコンテンツが見当たらない正規表現。

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- 一部のパスワード
- somepassword
- secretPassword
- サンプル

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

この機密情報の種類は、キーワード リストではなく正規表現を使用して、これらのキーワードを識別します。

- パスワードまたは pwd の後に 0 ~ 2 スペース、等号 (=)、0 ~ 2 スペース、およびアスタリスク (*) -OR- が続きます。
- パスワードまたは pwd の後に次の情報が表示されます。
    - 等号 (=)
    - シンボル未満 (<)
    - 大文字または小文字、数字、アスタリスク (*)、ハイフン (-)、下線 (_)、または空白文字である 1 ~ 200 文字の任意の組み合わせ
    - 記号より大きい (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

この機密情報の種類は、キーワード リストではなく正規表現を使用して、これらのキーワードを識別します。

- contoso
- fabrikam
- northwind
- サンドボックス
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->net

## <a name="sweden-drivers-license-number"></a>スウェーデンの運転免許証番号

### <a name="format"></a>フォーマット

ハイフンを 1 つ含む 10 桁の数字

### <a name="pattern"></a>パターン

ハイフンを含む 10 桁の数字:

- 6 桁
- ハイフン
- 4 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、  `Regex_sweden_eu_driver's_license_number` パターンに一致するコンテンツを検索します。
- キーワードが見  `Keywords_eu_driver's_license_number` `Keywords_sweden_eu_driver's_license_number` つかったか、検索されます。

```xml
      <!-- Sweden Driver's License Number -->
      <Entity id="70088720-90dd-47f5-805e-5525f3567391" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_sweden_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver's_license_number

- ajokortti
- permis de
- ajokortin numero
- kuljettajat lic.
- drivere lic。
- körkort
- numărul permisului de conducere
-  שאָפער דערלויבעניש נומער
- förare lic.
-  דריווערס דערלויבעניש
- körkortsnummer

## <a name="sweden-national-id"></a>スウェーデンの国民 ID

### <a name="format"></a>フォーマット

10 桁または 12 桁の数字とオプションの区切り記号 1 つ

### <a name="pattern"></a>パターン

10 桁または 12 桁の数字と省略可能な区切り記号:
- 2 桁 (オプション)
- YYMMDD という日付形式の 6 桁の数字
- "-" または "+" の区切り記号 (省略可能)
- 4 桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数 `Func_swedish_national_identifier` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keywords_swedish_national_identifier` 見つかりました
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数 `Func_swedish_national_identifier` は、パターンに一致するコンテンツを検索します。
- チェックサムが渡される。


```xml
    <!-- Sweden National ID -->
    <Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
        <Match idRef="Keywords_swedish_national_identifier" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_swedish_national_identifier" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_swedish_national_identifier"></a>Keywords_swedish_national_identifier

- id no
- id 番号
- id#
- ID なし
- identification number
- identifikationsnumret#
- identifikationsnumret
- identitetshandling
- ID ドキュメント
- ID なし
- ID 番号
- id-nummer
- 個人用 ID
- personnummer#
- personnummer
- skatteidentifikationsnummer

## <a name="sweden-passport-number"></a>スウェーデンのパスポート番号

### <a name="format"></a>フォーマット

8 桁

### <a name="pattern"></a>パターン

8 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 正規表現は、Regex_sweden_passport_number一致するコンテンツを検索します。
- キーワードが見 `Keywords_eu_passport_number` `Keyword_sweden_passport` つかったか、検索されます。
- 正規表現は `Regex_sweden_eu_passport_date` 、DD MMM/MMM YY (01 JAN/JAN 12) 形式の日付を検索するか、キーワードが `Keywords_eu_passport_date` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、Regex_sweden_passport_number一致するコンテンツを検索します。
- キーワードが見 `Keywords_eu_passport_number` `Keyword_sweden_passport` つかったか、検索されます。


```xml
    <!-- Sweden Passport Number -->
    <Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_sweden_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- エイリアン登録カード
- g3 処理手数料
- 複数のエントリ
- Numéro de passeport
- passeport n °
- passeport non
- passeport#
- passeport#
- passeportnon
- passeportn °
- passnummer
- pass nr
- schengen visa
- schengen visas
- 単一エントリ
- sverige パス
- visa requirements
- visa 処理
- visa の種類

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 発行日
- 有効期限の日付


## <a name="sweden-tax-identification-number"></a>スウェーデンの納税者番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

10 桁の数字と指定したパターンの記号

### <a name="pattern"></a>パターン

10 桁の数字と記号:

- 生年月日に対応する 6 桁の数字 (YYMMDD)
- プラス記号またはマイナス記号
- 識別番号を一意にする 3 桁の数字。
  - 1990 年以前に発行された番号の場合、7 桁目と 8 桁目は出生国または外国生まれの人々を識別します。
  - 9 番目の位置の数字は、性別を男性または女性の場合は奇数で示します。
- 1 つのチェックディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数  `Func_sweden_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_sweden_eu_tax_file_number` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数  `Func_sweden_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- Sweden Tax Identification Number -->
      <Entity id="139acba0-a5bc-4fbb-876d-f7a493ae8a40" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_sweden_eu_telephone_number" />
            <Match idRef="Keywords_sweden_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- 個人用 ID 番号
- personnummer
- skatt id nummer
- スケートの識別
- skattebetalarens identifikationsnummer
- sverige tin
- tax ファイル
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#


## <a name="swift-code"></a>SWIFT コード

### <a name="format"></a>フォーマット

4 文字の後に 5 ~ 31 文字または数字

### <a name="pattern"></a>パターン

4 文字の後に 5 ~ 31 文字または数字が続きます。
- 4 文字の銀行コード (大文字と小文字は区別されません)
- オプションのスペース
- 4 ～ 28 個の文字または数字 (基本的銀行口座番号 (BBAN))
- オプションのスペース
- 1 ~ 3 文字または数字 (BBAN の残りの部分)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現 Regex_swift がパターンに一致するコンテンツを検出した。
- Keyword_swift のキーワードを検出した。

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_swift"></a>Keyword_swift

- international organization for standardization 9362
- iso 9362
- iso9362
- swift#
- swiftcode
- swiftnumber
- swiftroutingnumber
- swift code
- swift number #
- swift routing number
- bic number
- bic code
- bic #
- bic#
- bank identifier code
- Organisation internationale de normalisation 9362
- rapide #
- code SWIFT
- le numéro de swift
- swift numéro d'acheminement
- le numéro BIC
- # <a name="bic"></a>BIC
- code identificateur de banque
- SWIFT コード
- SWIFT の数
- BIC の数
- BIC コード
- SWIFT コード
- SWIFT
- BIC
- BIC コード
- 金融機関識別コード
- 金融機関コード
- 銀行コード

## <a name="switzerland-ssn-ahv-number"></a>スイス SSN AHV 番号
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

13 桁の数字

### <a name="pattern"></a>パターン

13 桁の番号:

- 3 桁の数字 - 756
- オプションのドット
- 4 桁
- オプションのドット
- 4 桁
- オプションのドット
- 2 桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_swiss_social_security_number_ahv一致するコンテンツを検索します。
- ユーザーのキーワードKeywords_swiss_social_security_number_ahv見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_swiss_social_security_number_ahv一致するコンテンツを検索します。

```xml
      <!-- Swiss SSN AHV Number -->
      <Entity id="277cfa4b-6eaa-4a1b-9492-099dec849971" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
          <Match idRef="Keywords_swiss_social_security_number_ahv" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_swiss_ssn_ahv_number"></a>Keyword_swiss_ssn_AHV_number

- ahv
- ssn
- pid
- 保険番号
- personalidno#
- social security number
- 個人用 ID 番号
- 個人識別番号。
- insuranceno#
- uniqueidno#
- 一意の ID いいえ。
- avs 番号
- 個人 ID no versicherungsnummer
- identifikationsnummer
- einzigartige identität nicht
- sozialversicherungsnummer
- ID 要員 ID
- numéro de sécurité sociale


## <a name="taiwan-national-identification-number"></a>台湾の国民識別番号

### <a name="format"></a>フォーマット

1 文字 (英語) の後に 9 桁

### <a name="pattern"></a>パターン

1 文字 (英語) の後に 9 桁の数字が続きます。
- 1 文字 (英語、大文字と小文字は区別されません)
- 数字 "1" または "2"
- 8 桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数 Func_taiwanese_national_id がパターンに一致するコンテンツを検出した。
- Keyword_taiwanese_national_id のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_taiwanese_national_id がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
       <Pattern confidenceLevel="75">
         <IdMatch idRef="Func_taiwanese_national_id" />
       </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_taiwan_national_id"></a>Keyword_taiwan_national_id

- 身份證字號
- 身份證
- 身份證號碼
- 身份證號
- 身分證字號
- 身分證
- 身分證號碼
- 身份證號
- 身分證統一編號
- 國民身分證統一編號
- 簽名
- 蓋章
- 簽名或蓋章
- 簽章

## <a name="taiwan-passport-number"></a>台湾のパスポート番号

### <a name="format"></a>フォーマット

- 生体認証パスポート番号: 9 桁
- 生体認証以外のパスポート番号: 9 桁

### <a name="pattern"></a>パターン
生体認証パスポート番号:
- 文字 "3"
- 8 桁

生体認証以外のパスポート番号:
- 9 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、Regex_taiwan_passport一致するコンテンツを検索します。
- ユーザーからのキーワードKeyword_taiwan_passport見つかりました。

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_taiwan_passport"></a>Keyword_taiwan_passport

- ROC passport number
- Passport number
- Passport no
- Passport Num
- Passport #
- 护照
- 中華民國護照
- Zhōnghuá Mínguó hùzhào

## <a name="taiwan-resident-certificate-arctarc-number"></a>台湾在住証明書 (ARC/TARC) 番号

### <a name="format"></a>フォーマット

10 桁の文字と数字

### <a name="pattern"></a>パターン

10 桁の文字と数字:
- 2 文字 (大文字と小文字は区別されません)
- 8 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、Regex_taiwan_resident_certificate一致するコンテンツを検索します。
- このページのKeyword_taiwan_resident_certificate見つかりました。

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_taiwan_resident_certificate"></a>Keyword_taiwan_resident_certificate

- Resident Certificate
- Resident Cert
- Resident Cert.
- Identification card
- Alien Resident Certificate
- ARC
- Taiwan Area Resident Certificate
- TARC
- 居留證
- 外僑居留證
- 台灣地區居留證

## <a name="thai-population-identification-code"></a>タイの人口識別コード

### <a name="format"></a>フォーマット

13 桁の数字

### <a name="pattern"></a>パターン

13 桁の数字:
- 1 桁目が 0 または 9 ではない
- 12 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_Thai_Citizen_Id一致するコンテンツを検索します。
- ユーザーのキーワードKeyword_Thai_Citizen_Id見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_Thai_Citizen_Id一致するコンテンツを検索します。

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_thai_citizen_id"></a>Keyword_thai_citizen_Id

- ID 番号
- ID 番号
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน

## <a name="turkish-national-identification-number"></a>トルコの国民識別番号

### <a name="format"></a>フォーマット

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数はFunc_Turkish_National_Id一致するコンテンツを検索します。
- ユーザーからのキーワードKeyword_Turkish_National_Id見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数はFunc_Turkish_National_Id一致するコンテンツを検索します。

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_turkish_national_id"></a>Keyword_turkish_national_id

- TC Kimlik No
- TC Kimlik numarası
- Vatandaşlık numarası
- Vatandaşlık no

## <a name="uk-drivers-license-number"></a>英国 運転免許証番号

### <a name="format"></a>フォーマット

指定の形式で組み合わせた 18 桁の文字と数字

### <a name="pattern"></a>パターン

18 個の文字と数字:
- 5 文字 (大文字と小文字は区別されません) または文字の代りとして数字 "9" を指定します。
- 1 桁の数字。
- 生年月日の日付形式 MMDDY の 5 桁。 ドライバーが女性の場合、7 番目の文字は 50 ずつ増加します。exampe の場合は、01 ~ 12 ではなく 51 ~ 62 です。
- 2 文字 (大文字と小文字は区別されません) または文字の代りとして"9" という数字を指定します。
- 5 桁の数字。

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数 `Func_uk_drivers_license` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keywords_eu_driver's_license_number` 見つかりました。
- チェックサムが渡される。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数 `Func_uk_drivers_license` は、パターンに一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
    <!-- U.K. Driver's License Number -->
    <Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75" relaxProximity="true" >
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_drivers_license" />
          <Match idRef="Keywords_eu_driver's_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_uk_drivers_license" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- ドライバー lic
- ドライバー lics
- driver license
- driver licenses
- ドライバー ライセンス
- ドライバー ライセンス
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- ドライバー lic
- ドライバー lics
- drivers license
- drivers licenses
- drivers licence
- ドライバー ライセンス
- driver'lic
- driver'lics
- 運転免許証
- 運転免許証
- 運転免許証
- 運転免許証
- ドライバーの lic
- ドライバーの lics
- 運転免許証
- ドライバーのライセンス
- 運転免許証
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- ドライバーの lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- 運転免許証
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- ドライバー lic#
- ドライバー lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- 運転免許証#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- ドライバーの lic#
- ドライバーの lics#
- 運転免許証#
- ドライバーのライセンス#
- 運転免許証#
- 運転免許証#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- ドライバー licen
- ドライバー licen
- ドライバーの licen
- lic の駆動
- licen の駆動
- ライセンスの運転
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号


## <a name="uk-electoral-roll-number"></a>英国 選挙ロール番号

### <a name="format"></a>フォーマット

2 文字の後に 1 ~ 4 桁の数字が続く

### <a name="pattern"></a>パターン

2 文字 (大文字と小文字を区別しない) の後に 1 ~ 4 の数字が続く

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現 Regex_uk_electoral がパターンに一致するコンテンツを検出した。
- Keyword_uk_electoral のキーワードを検出した。

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- council nomination
- nomination form
- electoral register
- electoral roll


## <a name="uk-national-health-service-number"></a>英国 国民保健サービス番号

### <a name="format"></a>フォーマット

スペースで区切られた 10 ～ 17 桁の数字

### <a name="pattern"></a>パターン

10 ～ 17 桁の数字:
- 3 桁または 10 桁の数字
- スペース
- 3 桁の数字
- スペース
- 4 桁

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数 Func_uk_nhs_number がパターンに一致するコンテンツを検出した。
- 次のいずれかの条件に該当する:
    - Keyword_uk_nhs_number のキーワードを検出した。
    - Keyword_uk_nhs_number1 のキーワードを検出した。
    - Keyword_uk_nhs_number_dob のキーワードを検出した。
- チェックサムが渡される。

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_uk_nhs_number"></a>Keyword_uk_nhs_number

- national health service
- nhs
- health services authority
- health authority

#### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- patient id
- patient identification
- patient no
- patient number

#### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- GP
- DOB
- D.O.B
- Date of Birth
- Birth Date

## <a name="uk-national-insurance-number-nino"></a>英国 国民保険番号 (NINO)
この機密情報の種類エンティティは、EU の国民識別番号の機密情報の種類に含まれています。 また、スタンドアロンの機密情報の種類エンティティとして利用できます。

### <a name="format"></a>フォーマット

スペースまたはダッシュで区切られた 7 文字または 9 文字

### <a name="pattern"></a>パターン

次の 2 つのパターンを使用できます。

- 2 つの文字 (有効な NINOs は、このプレフィックスで特定の文字のみを使用します。このパターンは検証しますが、大文字と小文字は区別されません)
- 6 桁
- 'A'、'B'、'C'、または 'D' のどちらか (プレフィックスと同様に、サフィックスでは特定の文字のみを使用できます。大文字と小文字は区別されません)

または

- 2 文字
- スペースまたはダッシュ
- 2 桁
- スペースまたはダッシュ
- 2 桁
- スペースまたはダッシュ
- 2 桁
- スペースまたはダッシュ
- 'A'、'B'、'C'、または 'D'

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数 Func_uk_nino がパターンに一致するコンテンツを検出した。
- Keyword_uk_nino のキーワードを検出した。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_uk_nino がパターンに一致するコンテンツを検出した。

```xml
    <!-- U.K. NINO -->
    <Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Match idRef="Keyword_uk_nino" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- national insurance number
- national insurance contributions
- protection act
- 保険
- social security number
- insurance application
- medical application
- social insurance
- medical attention
- social security
- great britain
- NI 番号
- NI No.
- NI#
- NI#
- 保険#
- insurancenumber
- nationalinsurance#
- nationalinsurancenumber


## <a name="uk-unique-taxpayer-reference-number"></a>英国 一意の納税者参照番号

この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースと区切り記号のない 10 桁の数字


### <a name="pattern"></a>パターン

10 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- この関数  `Func_uk_eu_tax_file_number` は、パターンに一致するコンテンツを検索します。
- キーワードが  `Keywords_uk_eu_tax_file_number` 見つかりました。

```xml
      <!-- U.K. Unique Taxpayer Reference Number -->
      <Entity id="ad4a8116-0db8-439a-b545-6d967642f0ec" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

- 税番号
- tax ファイル
- tax id
- 税の識別なし
- 税の識別番号
- tax no#
- tax no
- 税登録番号
- タクシー#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin いいえ
- tin#

## <a name="us-bank-account-number"></a>米国の銀行口座番号

### <a name="format"></a>フォーマット

6 ~ 17 桁

### <a name="pattern"></a>パターン

6 ~ 17 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、Regex_usa_bank_account_number一致するコンテンツを検索します。
- Keyword_usa_Bank_Account のキーワードを検出した。

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_usa_bank_account"></a>Keyword_usa_Bank_Account

- Checking Account Number
- Checking Account
- Checking Account #
- Checking Acct Number
- Checking Acct #
- Checking Acct No.
- Checking Account No.
- Bank Account Number
- Bank Account #
- Bank Acct Number
- Bank Acct #
- Bank Acct No.
- Bank Account No.
- Savings Account Number
- Savings Account.
- Savings Account #
- Savings Acct Number
- Savings Acct #
- Savings Acct No.
- Savings Account No.
- Debit Account Number
- Debit Account
- Debit Account #
- Debit Acct Number
- Debit Acct #
- Debit Acct No.
- Debit Account No.

## <a name="us-drivers-license-number"></a>米国の運転免許証番号

### <a name="format"></a>フォーマット

州に応じて異なる

### <a name="pattern"></a>パターン

状態によって異なります 。たとえば、ニューヨーク:
- ddd ddd ddd のように書式設定された 9 桁の数字が一致します。
- dddddddddd のような 9 桁の数字は一致しません。

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。
- Keyword_[state_name]_drivers_license_name のキーワードを検出した。
- ユーザーのキーワードKeyword_us_drivers_license見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- 関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。
- Keyword_[state_name]_drivers_license_name のキーワードを検出した。
- Keyword_us_drivers_license_abbreviations のキーワードを検出した。
- Keyword_us_drivers_license のキーワードを検出しなかった。

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_us_drivers_license_abbreviations"></a>Keyword_us_drivers_license_abbreviations

- DL
- DLS
- CDL
- CDLS
- ID
- IDs
- DL#
- DLS#
- CDL#
- CDLS#
- ID#
- IDs#
- ID number
- ID numbers
- LIC
- LIC#

#### <a name="keyword_us_drivers_license"></a>Keyword_us_drivers_license

- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- Driver Lic
- Driver Lics
- Driver License
- Driver Licenses
- DriversLic
- DriversLics
- DriversLicense
- DriversLicenses
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Driver'Lic
- Driver'Lics
- 運転免許証
- 運転免許証
- Driver' Lic
- Driver' Lics
- Driver' License
- Driver' Licenses
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver's Lic
- Driver's Lics
- Driver's License
- Driver's Licenses
- identification number
- identification numbers
- identification #
- id card
- id cards
- identification card
- identification cards
- DriverLic#
- DriverLics#
- DriverLicense#
- DriverLicenses#
- Driver Lic#
- Driver Lics#
- Driver License#
- Driver Licenses#
- DriversLic#
- DriversLics#
- DriversLicense#
- DriversLicenses#
- Drivers Lic#
- Drivers Lics#
- Drivers License#
- Drivers Licenses#
- Driver'Lic#
- Driver'Lics#
- 運転免許証#
- 運転免許証#
- Driver' Lic#
- Driver' Lics#
- Driver' License#
- Driver' Licenses#
- Driver'sLic#
- Driver'sLics#
- Driver'sLicense#
- Driver'sLicenses#
- Driver's Lic#
- Driver's Lics#
- Driver's License#
- Driver's Licenses#
- id card#
- id cards#
- identification card#
- identification cards#


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_[state_name]_drivers_license_name

- 状態の省略形 ("NY" など)
- 状態名 (たとえば、"New York")

## <a name="us-individual-taxpayer-identification-number-itin"></a>米国の個人納税者 ID 番号 (ITIN)

### <a name="format"></a>フォーマット

"9" で始まる 9 桁の数字で、4 桁目として "7" または "8" を含み、必要に応じてスペースまたはダッシュで書式設定されます。

### <a name="pattern"></a>パターン

書式設定:
- 数字 "9"
- 2 桁
- スペースまたはダッシュ
- "7" または "8"
- 数字
- スペース、またはダッシュ
- 4 桁

unformatted:
- 数字 "9"
- 2 桁
- "7" または "8"
- 5 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数 Func_formatted_itin がパターンに一致するコンテンツを検出した。
- Keyword_itin のキーワードを検出した。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_unformatted_itin がパターンに一致するコンテンツを検出した。
- Keyword_itin のキーワードを検出した。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- この関数はFunc_formatted_itin一Func_unformatted_itin一致するコンテンツを検索します。

```xml
    <!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
    <Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_formatted_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_unformatted_itin" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_itin"></a>Keyword_itin

- 納税者
- tax id
- tax identification
- itin
- i.t.i.n.
- ssn
- tin
- social security
- tax payer
- itins
- タクシー
- individual taxpayer


## <a name="us-social-security-number-ssn"></a>米国の社会保障番号 (SSN)

### <a name="format"></a>フォーマット

9 桁の数字 (書式付きまたは書式設定されていないパターンの場合があります)

> [!NOTE]
> 2011 年半ばより前に発行された場合、SSN には強力な書式が設定されています。この場合、数値の特定の部分が有効な範囲内に入る必要があります (チェックサムはありません)。

### <a name="pattern"></a>パターン

4 つの関数は、4 つの異なるパターンで SSN を探します。
- Func_ssn は、2011 年以前の厳密な書式の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。
- Func_unformatted_ssn は、2011 年以前の厳密な書式の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。
- Func_randomized_formatted_ssn は、2011 年以降の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。
- Func_randomized_unformatted_ssn は、2011 年以降の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。

### <a name="checksum"></a>チェックサム

いいえ


### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- この関数 `Func_ssn` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_ssn` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数はFunc_unformatted_ssn一致するコンテンツを検索します。
- キーワードが `Keyword_ssn` 見つかりました。

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという信頼性が低いです。
- パターンに `Func_randomized_formatted_ssn` 一 `Func_randomized_unformatted_ssn` 致するコンテンツを関数または検索します。
- キーワードが `Keyword_ssn` 見つかりました。


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_ssn"></a>Keyword_ssn

- SSA 番号
- social security number
- 社会保障#
- 社会保障#
- 社会保障なし
- Social Security#
- Soc Sec
- SSN
- SSNS
- SSN#
- SS#
- SSID

## <a name="us--uk-passport-number"></a>米国/英国 passport number

### <a name="format"></a>フォーマット

9 桁

### <a name="pattern"></a>パターン

- 1 文字または数字
- 8 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたと高い信頼性を持っています。
- 関数 Func_usa_uk_passport がパターンに一致するコンテンツを検出した。
- キーワードが見 `Keywords_eu_passport_number` `Keywords_uk_eu_passport_number` つかったか、検索されます。
- キーワードが `Keywords_eu_passport_date` 見つかりました

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 関数 Func_usa_uk_passport がパターンに一致するコンテンツを検出した。
- キーワードが見 `Keywords_eu_passport_number` `Keywords_uk_eu_passport_number` つかったか、検索されます。

```xml
    <!-- U.S. / U.K. Passport Number -->
    <Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
       <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- パスポート#
- パスポート#
- passportid
- パスポート
- passportno
- パスポートなし
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_uk_eu_passport_number"></a>Keywords_uk_eu_passport_number

- 英国のパスポート
- 英国のパスポート


## <a name="ukraine-passport-domestic"></a>ウクライナのパスポート国内
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

9 桁

### <a name="pattern"></a>パターン

9 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現はRegex_Ukraine_Passport_Domestic一致するコンテンツを検索します。
- このページのKeyword_Ukraine_Passport_Domesticが見つかりました。

```xml
      <!-- Ukraine Passport Domestic -->
      <Entity id="1817a540-221f-4459-9202-3bd78b81d803" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_Ukraine_Passport_Domestic"/>
          <Match idRef="Keyword_Ukraine_Passport_Domestic"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_ukraine_passport_domestic"></a>Keyword_ukraine_passport_domestic

- ウクライナのパスポート
- passport number
- パスポートなし
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>ウクライナのパスポート国際
この機密情報の種類は、次の場所でのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

8 文字の英数字パターン

### <a name="pattern"></a>パターン

8 文字の英数字パターン:
- 2 文字または数字
- 6 桁

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現はRegex_Ukraine_Passport_International一致するコンテンツを検索します。
- ユーザーからのキーワードKeyword_Ukraine_Passport_International見つかりました。

```xml
      <!-- Ukraine Passport International -->
      <Entity id="cfbe032d-22e0-4f28-ab68-d66e9641f1e2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Ukraine_Passport_International"/>
          <Match idRef="Keyword_Ukraine_Passport_International"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_ukraine_passport_international"></a>Keyword_ukraine_passport_international

- ウクライナのパスポート
- passport number
- パスポートなし
- паспорт України
- номер паспорта
