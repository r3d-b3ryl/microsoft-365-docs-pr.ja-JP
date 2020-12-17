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
localization_priority: Normal
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
description: セキュリティ コンプライアンス センターのデータ損失防止 (DLP) には、DLP ポリシーですぐに使用できる 80 種類の機密情報が &amp; 含まれています。 このトピックでは、機密情報の種類をすべて一覧表示し、各種類を検出したときに DLP ポリシーが調査する内容を示します。
ms.openlocfilehash: cb45d613da95c977f56b82e64ad3332434e08cd8
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698510"
---
# <a name="sensitive-information-type-entity-definitions"></a>機密情報の種類のエンティティ定義

コンプライアンス センターのデータ損失防止 (DLP) には、DLP ポリシーですぐに使用できる多くの機密情報の種類が含まれています。 このトピックでは、機密情報の種類をすべて一覧表示し、各種類を検出したときに DLP ポリシーが調査する内容を示します。 機密情報の種類はパターンで定義され、正規表現または関数で識別できます。 機密情報の種類はさらに、キーワードやチェックサムなどの確証的な証拠を使用して識別することもできます。 また、評価プロセスでは信頼度や近接度も使用されます。

機密情報の種類には、次のいずれかのサブスクリプションが必要です。
- Microsoft 365 E3
- Microsoft 365 E5

## <a name="aba-routing-number"></a>ABA ルーティング番号

### <a name="format"></a>フォーマット

書式付きまたは書式設定されていないパターンの 9 桁の数字

### <a name="pattern"></a>パターン

書式設定:
- 0、1、2、3、6、7、または 8 で始まる 4 桁の数字
- ハイフン
- 4 桁の数字
- ハイフン
- 1 桁の数字

書式設定されていない場合: 0、1、2、3、6、7、または 8 で始まる 9 桁の連続する数字 

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_aba_routing がパターンに一致するコンテンツを検出した。
- Keyword_ABA_Routing のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- routing#
- ルーティングなし
- ルーティング番号
- routing transit number
- routing#
- RTN


## <a name="argentina-national-identity-dni-number"></a>アルゼンチンの国民識別番号 (DNI)

### <a name="format"></a>フォーマット

ピリオド付きまたはピリオドなしの 8 桁の数字

### <a name="pattern"></a>パターン

8 桁の数字:
- 2 桁の数字
- 省略可能な期間
- 3 桁の数字
- 省略可能な期間
- 3 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Regex_argentina_national_idコンテンツを検索する正規表現。
- 検索されたKeyword_argentina_national_id検索されます。

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
   
## <a name="australia-bank-account-number"></a>オーストラリアの銀行口座番号

### <a name="format"></a>フォーマット

銀行の州の支店番号の付きまたはなし 6 ~ 10 桁の数字

### <a name="pattern"></a>パターン

アカウント番号は 6 ~ 10 桁の数字です。

オーストラリアの銀行の州支店番号:
- 3 桁の数字 
- ハイフン 
- 3 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。
- Keyword_australia_bank_account_number のキーワードを検出した。
- 正規表現 Regex_australia_bank_account_number_bsb がパターンに一致するコンテンツを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。
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
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ


### <a name="format"></a>フォーマット

11 桁の数字とオプションの区切り文字

### <a name="pattern"></a>パターン

11 桁の数字とオプションの区切り文字:

- 2 桁の数字
- 任意指定のハイフンまたはスペース
- 3 桁の数字
- 任意指定のハイフンまたはスペース
- 3 桁の数字
- 任意指定のハイフンまたはスペース
- 3 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_australian_business_numberパターンに一致するコンテンツを検索します。
- 検索されたKeywords_australian_business_number検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_australian_business_numberパターンに一致するコンテンツを検索します。

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

- australia business no
- ビジネス番号
- abn#
- businessid#
- ビジネス ID
- abn
- businessno#

## <a name="australia-company-number"></a>オーストラリアの会社番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

区切り記号付き 9 桁の数字

### <a name="pattern"></a>パターン

区切り記号付き 9 桁の数字:

- 3 桁の数字
- スペース
- 3 桁の数字
- スペース
- 3 桁の数字


### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_Australian_Company_Numberパターンに一致するコンテンツを検索します。
- 検索されたKeyword_Australian_Company_Number検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_Australian_Company_Numberパターンに一致するコンテンツを検索します。

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
- オーストラリアの会社いいえ
- オーストラリアの会社なし#
- オーストラリアの会社番号

## <a name="australia-drivers-license-number"></a>オーストラリアの運転免許証番号

### <a name="format"></a>フォーマット

9 桁の文字と数字

### <a name="pattern"></a>パターン

9 桁の文字と数字: 

- 2 桁の数字または文字 (大文字小文字を区別しない) 
- 2 桁の数字 
- 5 桁の数字または文字 (大文字小文字を区別しない)

OR

- 1 ~ 2 文字のオプションの文字 (大文字小文字を区別しない) 
- 4 ~ 9 桁の数字

OR

- 9 桁の数字または文字 (大文字と小文字を区別しない)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- Driver'Licence
- Driver'Licences
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
- Driver'Licence#
- Driver'Licences#
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
- Driver'Licenses
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
- Driver'Licenses#
- Driver' License#
- Driver' Licenses#
- Driver'sLicense#
- Driver'sLicenses#
- Driver's License#
- Driver's Licenses#
   
## <a name="australia-medical-account-number"></a>オーストラリアの医療口座番号

### <a name="format"></a>フォーマット

10 ～ 11 桁の数字

### <a name="pattern"></a>パターン

10 ～ 11 桁の数字:
- 1 桁目が 2 ~ 6 の範囲
- 9 桁目はチェック ディジット
- 10 桁目が問題の数字
- 1 桁目の数字 (省略可能) は個々の数字です。

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- care

   
## <a name="australia-passport-number"></a>オーストラリアのパスポート番号

### <a name="format"></a>フォーマット

1 桁の文字の後に 7 桁の数字

### <a name="pattern"></a>パターン

1 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_australia_passport_number がパターンに一致するコンテンツを検出した。
- 特定のユーザーまたはKeyword_passportキーワードKeyword_australia_passport_number検出された。

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a>キーワード

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
- 万の表示
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport#
- PasseportNon
- Passeportn °

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- passport
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- residential address
- department of immigration and citizenship
- visa
- national identity card
- passport number
- travel document
- issuing authority
   
## <a name="australia-tax-file-number"></a>オーストラリアの税ファイル番号

### <a name="format"></a>フォーマット

8 桁から 9 桁の数字

### <a name="pattern"></a>パターン

通常、8 ~ 9 桁の数字には、次のようにスペースが表示されます。
- 3 桁の数字 
- 省略可能なスペース 
- 3 桁の数字 
- 省略可能なスペース 
- 2 ~ 3 桁の数字 (最後の数字がチェック ディジット)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
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

8 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現は、  `Regex_austria_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_austria_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver's_license_number

- fuhrerschein
- fcheerschein
- Fcheerscheine
- Fcheerscheinnummer
- Fchehrerscheinnummern

## <a name="austria-identity-card"></a>オーストリアの ID カード
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

24 文字の文字、数字、特殊文字の組み合わせ
  
### <a name="pattern"></a>パターン

24 文字:
  
-  22 文字 (大文字小文字を区別しない)、数字、円記号、スラッシュ、またはプラス記号 
    
- 2 文字 (大文字小文字を区別しない)、数字、円記号、スラッシュ、プラス記号、または等号
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現は、  `Regex_austria_eu_national_id_card` パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_austria_eu_national_id_card` 検出した。 
   
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
- personalausweis repubwei ösichich

## <a name="austria-passport-number"></a>オーストリアのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

1 文字の後にオプションのスペースと 7 桁の数字
  
### <a name="pattern"></a>パターン

1 文字、7 桁の数字、および 1 つのスペースの組み合わせ:
  
- 1 文字 (大文字小文字を区別しない)
- 1 つのスペース (省略可能)
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_austria_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_austria_eu_passport_number` 検出した。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
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
- reisep sse

## <a name="austria-social-security-number-or-equivalent-identification"></a>オーストリアの社会保障番号または同等の識別情報
この機密情報の種類のエンティティは、EU 社会保障番号または同等の ID の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

指定された形式の 10 桁の数字
  
### <a name="pattern"></a>パターン

10 桁の数字:
  
- シリアル番号に対応する 3 桁の数字 
- 1 桁のチェック ディジット
- 生年月日に対応する 6 桁の数字 (DDMMYY)
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 'Func_austria_eu_
- _or_equivalentパターンに一致するコンテンツを検索します。 
- キーワードが  `Keywords_austria_eu_ssn_or_equivalent` 見つかりました。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_austria_eu_ssn_or_equivalent` 、パターンに一致するコンテンツを検索します。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- 社会保障なし
- social security number
- social security code
- insurance number
- の ssn
- ssn#
- ssn
- insurance code
- insurance code#
- socialsecurityno#
- sozialversicherungsnummer
- socherle sicherheit n
- versicherungsnummer

## <a name="austria-tax-identification-number"></a>オーストリアの税金の識別番号

### <a name="format"></a>フォーマット

9 桁の数字とオプションのハイフンとスラッシュ
  
### <a name="pattern"></a>パターン

9 桁の数字とオプションのハイフンとスラッシュ:
  
- 2 桁の数字
- ハイフン (省略可能)
- 3 桁の数字
- スラッシュ (省略可能)
- 4 桁の数字
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_austria_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_austria_eu_tax_file_number` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_austria_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
    
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

- ösichich
- st.nr。
- steuernummer
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- tax number
 
## <a name="austria-value-added-tax"></a>オーストリアの付加価値税
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

11 文字の英数字パターン

### <a name="pattern"></a>パターン

11 文字の英数字のパターン:

- A または a
- T または t
- 省略可能なスペース
- U または u
- 省略可能なスペース
- 2 桁または 3 桁の数字
- 省略可能なスペース
- 4 桁の数字
- 省略可能なスペース
- 1 桁または 2 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_Austria_Value_Added_Taxパターンに一致するコンテンツを検索します。
- 検索されたKeyword_Austria_Value_Added_Tax検出された。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_Austria_Value_Added_Taxパターンに一致するコンテンツを検索します。

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

- vat number
- vat#
- vat number
- vat no.
- vatno#
- 付加価値税番号
- vat
- wbst
- umsatzsteuernummer
- wbstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- vat identification number
- atu number
- uid number


## <a name="azure-documentdb-auth-key"></a>Azure DocumentDB 認証キー

### <a name="format"></a>フォーマット

文字列 "DocumentDb" の後に、次のパターンでアウトラインで示されている文字と文字列を指定します。

### <a name="pattern"></a>パターン

- 文字列 "DocumentDb"
- 3 ~ 200 文字の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')
- 86 文字の小文字または大文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ
- 2 つの等号 (=)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一CEP_Regex_AzureDocumentDBAuthKeyコンテンツを検索する正規表現。
- パターンに一CEP_CommonExampleKeywordsコンテンツ **が** 見つからない正規表現。

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

(技術的には、この機密情報の種類はキーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure IAAS データベース接続文字列と Azure SQL接続文字列

### <a name="format"></a>フォーマット

文字列 "Server"、"server"、または "data source" の後に、文字列 "cloudapp.azure" を含む、以下のパターンで概説されている文字と文字列が続きます。<!--no-hyperlink-->com" または "cloudapp.azure" です。<!--no-hyperlink-->net" または "database.windows.<!--no-hyperlink-->net"、および文字列 "Password" または "password" または "pwd" です。

### <a name="pattern"></a>パターン

- 文字列 "Server"、"server"、または "data source"
- 0 から 2 文字の空白文字
- 等号 (=)
- 0 から 2 文字の空白文字
- 1 ~ 200 文字の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 文字列 "cloudapp.azure。<!--no-hyperlink-->com"、"cloudapp.azure。<!--no-hyperlink-->net"、または "database.windows.<!--no-hyperlink-->net"
- 1 ~ 300 文字の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 文字列 "Password"、"password"、または "pwd"
- 0 から 2 文字の空白文字
- 等号 (=)
- 0 から 2 文字の空白文字
- セミコロン (;)、引用符 (")、またはアポストロフィ (') ではない 1 つ以上の文字
- セミコロン (;)、引用符 (")、またはアポストロフィ (')

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一CEP_Regex_AzureConnectionStringコンテンツを検索する正規表現。
- パターンに一CEP_CommonExampleKeywordsコンテンツ **が** 見つからない正規表現。

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

(技術的には、この機密情報の種類はキーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iot-connection-string"></a>Azure IoT 接続文字列

### <a name="format"></a>フォーマット

文字列 "HostName" の後に、次のパターンでアウトラインで示されている文字と文字列 ("azure-devices" という文字列を含む)。<!--no-hyperlink-->net" および "SharedAccessKey"。

### <a name="pattern"></a>パターン

- 文字列 "HostName"
- 0 から 2 文字の空白文字
- 等号 (=)
- 0 から 2 文字の空白文字
- 1 ~ 200 文字の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 文字列 "azure-devices"<!--no-hyperlink-->net"
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

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一CEP_Regex_AzureIoTConnectionStringコンテンツを検索する正規表現。
- パターンに一CEP_CommonExampleKeywordsコンテンツ **が** 見つからない正規表現。

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

(技術的には、この機密情報の種類はキーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-publish-setting-password"></a>Azure 発行設定パスワード

### <a name="format"></a>フォーマット

文字列 "userqpd=" の後に英数字の文字列を指定します。

### <a name="pattern"></a>パターン

- 文字列 "userqpd="
- 60 桁の小文字または数字の任意の組み合わせ
- 引用符 (")

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一CEP_Regex_AzurePublishSettingPasswordsコンテンツを検索する正規表現。
- パターンに一CEP_CommonExampleKeywordsコンテンツ **が** 見つからない正規表現。


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

(技術的には、この機密情報の種類はキーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-redis-cache-connection-string"></a>Azure Redis キャッシュ接続文字列

### <a name="format"></a>フォーマット

文字列 "redis.cache.windows。<!--no-hyperlink-->net" の後に、文字列 "password" または "pwd" を含む、以下のパターンでアウトラインで示されている文字と文字列が続きます。

### <a name="pattern"></a>パターン

- 文字列 "redis.cache.windows。<!--no-hyperlink-->net"
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

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一CEP_Regex_AzureRedisCacheConnectionStringコンテンツを検索する正規表現。
- パターンに一CEP_CommonExampleKeywordsコンテンツ **が** 見つからない正規表現。

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

(技術的には、この機密情報の種類はキーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>フォーマット

文字列 "sig" の後に、次のパターンでアウトラインで示されている文字と文字列を指定します。

### <a name="pattern"></a>パターン

- 文字列 "sig"
- 0 から 2 文字の空白文字
- 等号 (=)
- 0 から 2 文字の空白文字
- 43 ~ 53 文字の任意の組み合わせで、小文字または大文字、数字、またはパーセント記号 (%)
- 文字列 "%3d"
- 小文字または大文字ではない文字、数字、またはパーセント記号 (%)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一CEP_Regex_AzureSASコンテンツを検索する正規表現。

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Azure サービス バス接続文字列

### <a name="format"></a>フォーマット

文字列 "EndPoint" の後に、文字列 "servicebus.windows" を含む、以下のパターンでアウトラインで示されている文字と文字列が続きます。<!--no-hyperlink-->net" および "SharedAccesKey"。

### <a name="pattern"></a>パターン

- 文字列 "EndPoint"
- 0 から 2 文字の空白文字
- 等号 (=)
- 0 から 2 文字の空白文字
- 1 ~ 200 文字の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 文字列 "servicebus.windows。<!--no-hyperlink-->net"
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

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現はCEP_Regex_AzureServiceBusConnectionStringパターンに一致するコンテンツを検索します。
- パターンに一CEP_CommonExampleKeywordsコンテンツ **が** 見つからない正規表現。

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

(技術的には、この機密情報の種類はキーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key"></a>Azure ストレージ アカウント キー

### <a name="format"></a>フォーマット

文字列 "DefaultEndpointsProtocol" の後に、文字列 "AccountKey" を含む、以下のパターンでアウトラインで示されている文字と文字列が続きます。

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

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一CEP_Regex_AzureStorageAccountKeyコンテンツを検索する正規表現。
- パターンに一CEP_AzureEmulatorStorageAccountFilterコンテンツ **が** 見つからない正規表現。
- パターンに一CEP_CommonExampleKeywordsコンテンツ **が** 見つからない正規表現。

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

(技術的には、この機密情報の種類はキーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- Eby8vdM02xNOcqFlqUwLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(技術的には、この機密情報の種類はキーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key-generic"></a>Azure Storage アカウント キー (汎用)

### <a name="format"></a>フォーマット

86 文字の小文字または大文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ。前または後に、次のパターンでアウトラインで示される文字。

### <a name="pattern"></a>パターン

- 0 から大きい記号 (>)、アポストロフィ (')、等号 (=)、引用符 (")、または数値記号 (#)
- 小文字または大文字、数字、スラッシュ (/)、またはプラス記号 (+) である 86 文字の任意の組み合わせ
- 2 つの等号 (=)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一CEP_Regex_AzureStorageAccountKeyGenericコンテンツを検索する正規表現。

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

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_belgium_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出 `Keywords_eu_driver's_license_number` `Keywords_belgium_eu_driver's_license_number` された、または検出された。
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver's_license_number

- rijbewijs
- rijbewijsnummer
- fcheerschein
- fcheinnummer
- fcheinnummer
- fuhrerschein
- fuehrerschein
- fuhrerscheinnummer
- fuehrerscheinnummer
- permis de conduire
- numéro permis conduire


## <a name="belgium-national-number"></a>ベルギーの国民番号

### <a name="format"></a>フォーマット

11 桁の数字とオプションの区切り文字

### <a name="pattern"></a>パターン

11 の数字と区切り文字:
- YY 形式の 6 桁の数字と 2 つのオプションのピリオド。MM.DDの日付 
- ドット、ダッシュ、スペースの区切り記号 (省略可能) 
- 3 桁の連続する数字 (男性の場合は奇数、女性の場合も) 
- ドット、ダッシュ、スペースの区切り記号 (省略可能) 
- 2 桁のチェック ディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_belgium_national_numberパターンに一致するコンテンツを検索します。
- 検索されたKeyword_belgium_national_number検索されます。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_belgium_national_numberパターンに一致するコンテンツを検索します。
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
- identifiant national
- identifiantnational#
- identificatie
- identification
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- identity
- inscription
- national number
- national register
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
- registration
- registrationsnumme
- registrierung
- social security number
- ssn#
- ssn
- steuernummer
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#

## <a name="belgium-passport-number"></a>ベルギーのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

2 桁の文字の後に 6 桁の数字 (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

2 桁の文字、その後に 6 桁の数字
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_belgium_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_belgium_eu_passport_number` 検出した。

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro passeport
- paspoort nr
- paspoort-nr
- paspoortnummer
- paspoortnummers
- Passeport carte
- Passeport の数
- Pass-Nr
- Passnummer
- reisepasspass

## <a name="belgium-social-security-number-or-equivalent-identification"></a>ベルギーの社会保障番号または同等の識別情報
この機密情報の種類のエンティティは、EU 社会保障番号または同等の ID の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

11 桁の数字 (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

11 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- この関数は  `Func_belgium_eu_ssn_or_equivalent` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_belgium_eu_ssn_or_equivalent` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_belgium_eu_ssn_or_equivalent` 、パターンに一致するコンテンツを検索します。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

- national number
- national number
- social security number
- nationalnumber#
- ssn#
- ssn
- nationalnumber
- bnn#
- bnn
- 個人用 ID 番号
- personalidnumber#
- numéro national
- numéro de sécurité
- numéro d'assuré
- identifiant national
- identifiantnational#
- numéronational#


## <a name="belgium-value-added-tax-number"></a>ベルギーの付加価値税番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

12 文字の英数字パターン

### <a name="pattern"></a>パターン

12 文字の英数字のパターン:

- 文字 B または b
- E または e の文字
- 0 桁の数字
- 1 ~ 9 の数字
- オプションのドットまたはハイフンまたはスペース
- 4 桁の数字
- オプションのドットまたはハイフンまたはスペース
- 4 桁の数字


### <a name="checksum"></a>チェックサム

はい


### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_belgium_value_added_tax_numberパターンに一致するコンテンツを検索します。
- 検索されたKeywords_belgium_value_added_tax_number検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_belgium_value_added_tax_numberパターンに一致するコンテンツを検索します。

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

- nTv tva
- vat number
- vat no
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
- チェック ディジットである 2 桁の数字

書式設定されていない場合:
- 11 桁の数字 (最後の 2 桁はチェック ディジット)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_brazil_cpfパターンに一致するコンテンツを検索します。
- 検索されたKeyword_brazil_cpf検出された。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_brazil_cpfパターンに一致するコンテンツを検索します。
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
- Id
- Registration
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

- 2 桁の数字 
- ピリオド 
- 3 桁の数字 
- ピリオド 
- 3 桁の数字 (この最初の 8 桁は登録番号) 
- スラッシュ 
- 4 桁の分岐番号 
- ハイフン 
- チェック ディジットである 2 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_brazil_cnpjパターンに一致するコンテンツを検索します。
- 検索されたKeyword_brazil_cnpj検索されます。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_brazil_cnpjパターンに一致するコンテンツを検索します。
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

Registro Geral (旧形式): 9 桁の数字

Registro de Identidade (RIC) (新しい形式): 11 桁の数字

### <a name="pattern"></a>パターン

Registro Geral (従来の形式):
- 2 桁の数字 
- ピリオド 
- 3 桁の数字 
- ピリオド 
- 3 桁の数字 
- ハイフン 
- チェック ディジットである 1 桁の数字

Registro de Identidade (RIC) (新しい形式):
- 10 桁の数字 
- ハイフン 
- チェック ディジットである 1 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_brazil_rgパターンに一致するコンテンツを検索します。
- 検索されたKeyword_brazil_rg検索されます。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_brazil_rgパターンに一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
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

9 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_bulgaria_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_bulgaria_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver's_license_number

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка
- шофьорски книжки

## <a name="bulgaria-uniform-civil-number"></a>ブルガリアの均一な市民番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースと区切り記号のない 10 桁の数字
  
### <a name="pattern"></a>パターン

スペースと区切り記号のない 10 桁の数字
  
- 生年月日 (YYMMDD) に対応する 6 桁の数字 
- 出生順に対応する 2 桁の数字
- 性別に対応する 1 桁の数字: 男性の偶数桁と女性の奇数桁
- 1 桁のチェック ディジット

### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_bulgaria_eu_national_id_card` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_bulgaria_eu_national_id_card` 検出した。 

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_bulgaria_eu_national_id_card` 、パターンに一致するコンテンツを検索します。 
    
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
- nomer
- egn#
- egn
- identification number
- national id
- national number
- nationalnumber#
- nationalnumber
- 個人用 ID
- personal no
- 個人番号
- personalidnumber#
- social security number
- ssn#
- ssn
- uniform の市民 ID
- uniform civil no
- 均一な市民番号
- uniformcivilno#
- uniformcivilno
- uniformcivilnumber#
- uniformcivilnumber
- 一意の国籍番号
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
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

スペースと区切り記号のない 9 桁の数字
  
### <a name="pattern"></a>パターン

9 桁の数字 
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_bulgaria_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_bulgaria_eu_passport_number` `Keywords_eu_passport_number_common` された、または検出された。 

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- паспортいいえ

## <a name="canada-bank-account-number"></a>カナダの銀行口座番号

### <a name="format"></a>フォーマット

7 桁または 12 桁の数字

### <a name="pattern"></a>パターン

カナダの銀行口座番号は 7 桁または 12 桁の数字です。

カナダの銀行口座転送番号は次のとおりです。
- 5 桁の数字 
- ハイフン 
- 3 桁の数字 OR
- ゼロ "0" 
- 8 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。
- Keyword_canada_bank_account_number のキーワードを検出した。
- 正規表現 Regex_canada_bank_account_transit_number がパターンに一致するコンテンツを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
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

アルバータ州、ブリティッシュ コロンビア州、マニトバ州、ニュー ブランズウィック州、ニューファンドランド・ラブラドール州、ノバスコシア州、オンタリオ州、プリンス エドワード アイランド州、ケベック州、およびサスカチュワン州の各種パターン

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- Driver'Licenses
- Driver'Licence
- Driver'Licences
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
- identification 
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
- Driver'Licenses# 
- Driver'Licence# 
- Driver'Licences# 
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
- identification# 

   
## <a name="canada-health-service-number"></a>カナダの医療サービス番号

### <a name="format"></a>フォーマット

10 桁の数字

### <a name="pattern"></a>パターン

10 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- ist
- workers compensation
- disability

      
## <a name="canada-passport-number"></a>カナダのパスポート番号

### <a name="format"></a>フォーマット

2 桁の大文字、その後に 6 桁の数字

### <a name="pattern"></a>パターン

2 桁の大文字と 6 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_canada_passport_number がパターンに一致するコンテンツを検出した。
- 検索または検索Keyword_canada_passport_numberキーワードKeyword_passport検出されました。

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
- 万の表示
- パスポート#
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport#
- PasseportNon
- Passeportn °

   
## <a name="canada-personal-health-identification-number-phin"></a>カナダの個人健康識別番号 (PHIN)

### <a name="format"></a>フォーマット

9 桁の数字

### <a name="pattern"></a>パターン

9 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_canada_phin がパターンに一致するコンテンツを検出した。
- 2 つ以上のキーワードが検出Keyword_canada_phinまたはKeyword_canada_provinces検出されました。

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
- ベド
- Northwest Territories
- On、on
- British Columbia
- アルバサ
- ササカチワン島
- マニートバ島
- ナズン語
- Newfoundland and Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- カナダ

   
## <a name="canada-social-insurance-number"></a>カナダの社会保険番号

### <a name="format"></a>フォーマット

9 桁の数字とオプションのハイフンまたはスペース

### <a name="pattern"></a>パターン

書式設定:
- 3 桁の数字 
- ハイフンまたはスペース 
- 3 桁の数字 
- ハイフンまたはスペース 
- 3 桁の数字

書式設定されていない場合: 9 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_canadian_sin がパターンに一致するコンテンツを検出した。
- 以下の 2 つ以上の条件に該当する:
    - Keyword_sin のキーワードを検出した。
    - Keyword_sin_collaborative のキーワードを検出した。
    - 関数 Func_eu_date が適切な日付形式の日付を検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- はい 
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

7 桁から 8 桁の数字と、チェック ディジットまたは文字の区切り文字

### <a name="pattern"></a>パターン

7 ~ 8 桁の数字と区切り文字:
- 1 桁から 2 桁の数字 
- 省略可能な期間 
- 3 桁の数字 
- 省略可能な期間 
- 3 桁の数字 
- ダッシュ 
- チェック ディジットである 1 桁の数字または文字 (大文字小文字を区別しない)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_chile_id_cardパターンに一致するコンテンツを検索します。
- 検索されたKeyword_chile_id_card検索されます。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_chile_id_cardパターンに一致するコンテンツを検索します。
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
- rol ico nacional
- rol ico tribuico
- RUN
- RUT
- tarjeta de identificación
- Rol Unico Nacional
- Rol Unico Tribuico
- RUN#
- RUT#
- nationaluniqueroleID#
- nacional identidad
- número identificación
- identidad número
- numero identificacion
- identidad numero
- チリの ID いいえ
- チリの ID 番号
- チリの ID#
- 固有の Tax Registry
- Unique Tributary Role
- Unique Tax Role
- 一意のトリビュート番号
- 一意の国番号
- 固有の国民的役割
- 国固有の役割
- チリの ID いいえ。
- チリの ID 番号
- チリの ID#

   
## <a name="china-resident-identity-card-prc-number"></a>中国の住民識別カード (PRC) 番号

### <a name="format"></a>フォーマット

18 桁の数字

### <a name="pattern"></a>パターン

18 桁の数字:
- アドレス コードである 6 桁の数字 
- YYYYMMDD という形式の 8 桁の数字 (生年月日) 
- 注文コードである 3 桁の数字 
- チェック ディジットである 1 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_china_resident_idパターンに一致するコンテンツを検索します。
- 検索されたKeyword_china_resident_id検索されます。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_china_resident_idパターンに一致するコンテンツを検索します。
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

14 ~ 16 桁の数字。書式設定または書式設定解除が可能で (dddd)、Luhn テストに合格する必要があります。

### <a name="pattern"></a>パターン

世界規模の主要ブランドのカード (Visa、MasterCard、Discover Card、JCB、American Express、ギフト カード、Dinars Club Card など) を検出する非常に複雑で信頼性の高いパターンです。

### <a name="checksum"></a>チェックサム

あり (Luhn のチェックサム)

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_credit_card がパターンに一致するコンテンツを検出した。
- 次のいずれかの条件に該当する:
    - Keyword_cc_verification のキーワードを検出した。
    - 検索されたKeyword_cc_name見つかりました。
    - 関数 Func_expiration_date が適切な日付形式の日付を検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- kredit kredit kr krtenprのfnummer
- kreditkrtenprufnummer
- pr最も近い
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- cod. sicurezza
- cod sicurezza
- n autorizzazione
- códó
- cod、cod、cod、
- cod. seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- cód. segurança
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
- gtigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadcadcad
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
- transaction
- transaction number
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
- carte carte cartehe
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
- creditcard
- credit cards
- creditcards
- ccn
- card holder
- cardholder
- card holders
- cardholders
- check card
- checkcard
- check cards
- checkcards
- debit card
- debitcard
- debit cards
- debitcards
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
- 会社のカード
- 会社のカード
- カードの種類
- card account number
- card member account
- Cardmember Acct。
- card no.
- card no
- card number
- carte bancaire
- carte de crédit
- carte de credit
- numéro de carte
- numero de carte
- nº de la carte
- nº de carte
- kredit kreditte
- karte
- karteninhaber
- karteninhabers
- kredit kredit krteninhaber
- kredit kredit krteninstitut
- kredit kredit krtentyp
- eigentigmername
- kartennr
- kartennummer
- kreditkrtennummer
- kreditkrten-nummer
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
- nº. do cartão
- no do cartão
- no do cartao
- 違います。 do cartão
- 違います。 do cartao
- クレジットカード番号
- クレジットカードナンバー
- クレジットカード#
- クレジットカード
- クレジット
- クレカ
- カード番号
- カードナンバー
- カード#
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


## <a name="croatia-drivers-license-number"></a>クロアチアの運転免許証番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 8 桁の数字
  
### <a name="pattern"></a>パターン

8 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現は、  `Regex_croatia_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出 `Keywords_eu_driver's_license_number` `Keywords_croatia_eu_driver's_license_number` された、または検出された。 

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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver's_license_number

- vozačka dozvola
- vozačke dozvole


## <a name="croatia-identity-card-number"></a>クロアチアの ID カード番号
この機密情報の種類のエンティティは、EU の国民識別番号の機密情報の種類に含まれており、スタンドアロンの機密情報の種類のエンティティとして使用できます。

### <a name="format"></a>フォーマット

9 桁の数字

### <a name="pattern"></a>パターン

9 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_croatia_id_cardパターンに一致するコンテンツを検索します。
- 検索されたKeyword_croatia_id_card検索されます。

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

- grastorski broj građana
- マスターの市民番号
- nacionalni identifikacijski broj
- national identification number
- oib#
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- 個人識別番号
- brozni broj
- skizni identifikacijski broj
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="croatia-passport-number"></a>クロアチアのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

スペースと区切り記号のない 9 桁の数字
  
### <a name="pattern"></a>パターン

9 桁の数字 
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_croatia_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_croatia_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putovovov
- br. Putovovov
- br putovov
   
## <a name="croatia-personal-identification-oib-number"></a>クロアチアの個人識別 (OIB) 番号

### <a name="format"></a>フォーマット

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の数字:
- 10 桁の数字 
- 最終桁はチェック ディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_croatia_oib_numberパターンに一致するコンテンツを検索します。
- 検索されたKeywords_croatia_eu_tax_file_number検索されます。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_croatia_oib_numberパターンに一致するコンテンツを検索します。
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

- grastorski broj građana
- マスターの市民番号
- nacionalni identifikacijski broj
- national identification number
- oib#
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- 個人識別番号
- brozni broj
- skizni identifikacijski broj
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#

## <a name="croatia-social-security-number-or-equivalent-identification"></a>クロアチアの社会保障番号または同等の識別情報
この機密情報の種類のエンティティは、EU 社会保障番号または同等の ID の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

スペースと区切り記号を含めずに 11 桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字:
  
- 10 桁の数字
- 1 桁のチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- この関数は  `Func_croatia_eu_ssn_or_equivalent` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_croatia_eu_ssn_or_equivalent` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- この関数は  `Func_croatia_eu_ssn_or_equivalent` 、パターンに一致するコンテンツを検索します。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

- 個人識別番号
- マスターの市民番号
- national identification number
- social security number
- nationalnumber#
- ssn#
- ssn
- nationalnumber
- bnn#
- bnn
- 個人用 ID 番号
- personalidnumber#
- oib
- osobni identifikacijski broj

   
## <a name="cyprus-drivers-license-number"></a>キプロスの運転免許証番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 12 桁の数字
  
### <a name="pattern"></a>パターン

12 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_cyprus_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_cyprus_eu_driver's_license_number` された、または検出された。

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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver's_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>キプロスの ID カード
この機密情報の種類は、次の場合にのみ使用できます。
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

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_cyprus_eu_national_id_card` パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_cyprus_eu_national_id_card` 検出した。 
    
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

- id card number
- ID カード番号
- kim kim karti
- national identification number
- 個人用 ID 番号
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>キプロスのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

1 文字の後に 6 ~ 8 桁の数字 (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

1 文字の後に 6 ~ 8 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_cyprus_eu_passport_number` パターンに一致するコンテンツを検索します。
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_cyprus_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
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
- Pasaport Kimli pasii
- pasaport numaras の数
- Pasaport no.
- Αρ. Διαβατηρίου

## <a name="cyprus-tax-identification-number"></a>キプロスの税金の識別番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

指定されたパターンの 8 桁の数字と 1 文字
  
### <a name="pattern"></a>パターン

8 桁の数字と 1 文字:
  
- "0" または "9"
- 7 桁の数字
- 1 文字 (大文字と小文字を区別しない)
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_cyprus_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_cyprus_eu_tax_file_number` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_cyprus_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
    
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
- 税識別コード
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tic#
- tic
- tin id
- tin no
- tin#
- vergi kimino kodu
- vergi kim numaras Numaras の数
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>チェコの運転免許証番号

### <a name="format"></a>フォーマット

2 桁の文字の後に 6 桁の数字
  
### <a name="pattern"></a>パターン

8 桁の文字と数字:
  
- 文字 'E' (大文字と小文字を区別しない)
- レター
- スペース (省略可能)
- 6 桁の数字

### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_czech_republic_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_czech_republic_eu_driver's_license_number` された、または検出された。 

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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver's_license_number

- idičsksksk prúkaz
- idičské prékakaka
- číslo idičského préidi
- čísla idičskskskch príkazí


## <a name="czech-passport-number"></a>チェコのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

スペースまたは区切り記号を含めずに 8 桁の数字
  
### <a name="pattern"></a>パターン

スペースまたは区切り記号を含めずに 8 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_czech_republic_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_czech_republic_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
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


## <a name="czech-personal-identity-number"></a>チェコの個人識別番号

### <a name="format"></a>フォーマット

オプションのスラッシュ (古い形式) を使用する 9 桁の数字とオプションのスラッシュ (新しい形式) を使用する 10 桁の数字

### <a name="pattern"></a>パターン

9 桁の数字 (古い形式):
- 生年月日を表す 6 桁の数字
- オプションのスラッシュ
- 3 桁の数字

10 桁の数字 (新しい形式):
- 生年月日を表す 6 桁の数字
- オプションのスラッシュ 
- 最後の数字がチェック ディジットである 4 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。

- この関数はFunc_czech_id_cardパターンに一致するコンテンツを検索します。
- 検索されたKeyword_czech_id_card検索されます。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。

- この関数はFunc_czech_id_card_new_formatパターンに一致するコンテンツを検索します。
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

- 生年月日
- チェコ共和国 ID
- czechidno#
- daéové číslo
- identifikační číslo
- ID no
- ID 番号
- identityno#
- identityno
- insurance number
- national identification number
- nationalnumber#
- national number
- osobní číslo
- personalidnumber#
- 個人用 ID 番号
- 個人識別番号
- 個人番号
- pid#
- pid
- pojiítíní číslo
- rč
- rodne cislo
- rodné číslo
- ssn
- ssn#
- social security number
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- 一意の ID 番号


## <a name="czech-social-security-number-or-equivalent-identification"></a>チェコの社会保障番号または同等の識別情報

この機密情報の種類のエンティティは、EU 社会保障番号または同等の ID の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

指定したパターンの 10 桁の数字と円記号
  
### <a name="pattern"></a>パターン

10 桁の数字と円記号:
  
- 生年月日 (YYMMDD) に対応する 6 桁の数字: 
- 円記号
- 同じ日付に生まれた人物を分け合うシリアル番号に対応する 3 桁の数字
- 1 桁のチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_czech_republic_eu_ssn_or_equivalent` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_czech_republic_eu_ssn_or_equivalent` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_czech_republic_eu_ssn_or_equivalent` 、パターンに一致するコンテンツを検索します。 

```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

- 生年月日
- national identification number
- 個人識別番号
- social security number
- nationalnumber#
- ssn#
- ssn
- national number
- 個人用 ID 番号
- personalidnumber#
- rč
- rodné číslo
- rodne cislo


## <a name="denmark-drivers-license-number"></a>デンマークの運転免許証番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 8 桁の数字
  
### <a name="pattern"></a>パターン

8 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_denmark_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_denmark_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver's_license_number

- k最も近い
- krekortnummer


## <a name="denmark-passport-number"></a>デンマークのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

スペースと区切り記号のない 9 桁の数字
  
### <a name="pattern"></a>パターン

9 桁の数字 
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_denmark_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_denmark_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- Passeport n°
- pasnumre


## <a name="denmark-personal-identification-number"></a>デンマークの個人識別番号

### <a name="format"></a>フォーマット

ハイフンを含む 10 桁の数字

### <a name="pattern"></a>パターン

10 桁の数字:
- DDMMYY という形式で、生年月日を表す 6 桁の数字 
- ハイフン 
- 最後の桁がチェック ディジットである 4 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Func_denmark_eu_tax_file_numberコンテンツを検索する正規表現。
- 検索されたKeyword_denmark_id検索されます。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Func_denmark_eu_tax_file_numberコンテンツを検索する正規表現。
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
- gesundheitsversicherungcherte nummer
- health card
- 医療保険証番号
- 医療保険番号
- identification number
- identifikationsnummer
- identifikationsnummer#
- ID 番号
- 1000,000,000,000
- nationalid#
- nationalnumber#
- national number
- personalidnumber#
- personalidentityno#
- 個人用 ID 番号
- personnummer
- personnummer#
- reisekrankenversicherungschertenummer
- rejsesygesikringskort
- ssn
- ssn#
- の id
- kode
- nummer
- (1)、1000,00
- social security number
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- tax code
- 旅行保険証
- uniqueidentityno#
- tax number
- tax registration number
- tax id
- 税識別番号
- はい#
- taxnumber#
- tax no
- taxno#
- taxnumber
- tax identification no
- tin#
- (2013 年 1 月#
- (2013 年 3 月)#
- tax no#
- tin id
- tin no
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


## <a name="denmark-social-security-number-or-equivalent-identification"></a>デンマークの社会保障番号または同等の識別情報
この機密情報の種類のエンティティは、EU 社会保障番号または同等の ID の機密情報の種類のみを使用できます。

### <a name="format"></a>フォーマット

指定されたパターンの 10 桁の数字とハイフン
  
### <a name="pattern"></a>パターン

10 桁の数字とハイフン:
  
- 生年月日に対応する 6 桁の数字 (DDMMYY) 
- ハイフン
- シーケンス番号に対応する 4 桁の数字

### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_denmark_eu_ssn_or_equivalent` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_denmark_eu_ssn_or_equivalent` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_denmark_eu_ssn_or_equivalent` 、パターンに一致するコンテンツを検索します。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

- 個人識別番号
- national identification number
- social security number
- nationalnumber#
- ssn#
- ssn
- national number
- 個人用 ID 番号
- personalidnumber#
- cpr-nummer
- personnummer


## <a name="drug-enforcement-agency-dea-number"></a>ドラッグ執行機関 (DEA) 番号

### <a name="format"></a>フォーマット

2 桁の文字の後に 7 桁の数字

### <a name="pattern"></a>パターン

パターンには、以下のすべてが含まれる必要があります。
- 考えられる一連の文字から 1 文字 (大文字小文字を区別しない): abcdefghjklmnprstux(レジストリ コード) 
- 1 文字 (大文字と小文字は区別されません)。これは、登録者の名の最初の文字または数字 '9' です。
- 7 桁の数字、最後の数字はチェック ディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_dea_number がパターンに一致するコンテンツを検出した。
- キーワード `Keyword_dea_number` の検索
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- ドラッグの実施の管理
- ドラッグ執行機関


## <a name="estonia-drivers-license-number"></a>エストニアの運転免許証番号

### <a name="format"></a>フォーマット

2 桁の文字の後に 6 桁の数字
  
### <a name="pattern"></a>パターン

2 桁の文字と 6 桁の数字:
  
- 文字 "ET" (大文字と小文字を区別しない) 
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_estonia_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_estonia_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver's_license_number

-- permis de conduire
- juhilubade numbrid
- juhiloa number
- juhiluba


## <a name="estonia-personal-identification-code"></a>エストニアの個人識別コード
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースと区切り記号を含めずに 11 桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字:
  
- 性と生年月日に対応する 1 桁の数字 (奇数の男性、偶数の女性、1 から 2: 19th century、3 から 4: 20th century、5 から 6: 21st century)
- 生年月日 (YYMMDD) に対応する 6 桁の数字
- 同じ日付に生まれた人を区切るシリアル番号に対応する 3 桁の数字
- 1 桁のチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_estonia_eu_national_id_card` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_estonia_eu_national_id_card` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_estonia_eu_national_id_card` 、パターンに一致するコンテンツを検索します。 
    
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
- iskokood#
- iskokood
- maksu id
- makshuhustuslase identifitseerimisnumber
- maksunumber
- national identification number
- national number
- 個人用コード
- 個人用 ID 番号
- 個人識別コード
- 個人識別番号
- personalidnumber#
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="estonia-passport-number"></a>エストニアのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

1 文字の後に 7 桁の数字 (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

1 文字の後に 7 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_estonia_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_estonia_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti ko、passi number passinumbrid document number document no dokumendi nr

## <a name="eu-debit-card-number"></a>EU のデビット カード番号

### <a name="format"></a>フォーマット

16 桁の数字

### <a name="pattern"></a>パターン

非常に複雑で信頼性の高いパターン

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- cardholders 
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
- carte carte cartehe 
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
- cirrus-edc-cistro 
- controlartart 
- controlartarten 
- credit card 
- credit cards 
- creditcard 
- creditcards 
- debetkaart 
- debetkaarten 
- debit card 
- debit cards 
- debitcard 
- debitcards 
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
- eigentigmername 
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
- kredit kreditte 
- kreditkrten-nummer 
- kredit kredit krteninhaber 
- kredit kredit krteninstitut 
- kreditkrtennummer 
- kredit kredit krtentyp 
- (2013 年 1 月 
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
- 違います。 de tarjeta 
- 違います。 do cartao 
- 違います。 do cartão 
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
- solo 
- supporti di scheda 
- supporto di scheda 
- switch 
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
- cod、cod、cod、 
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
- códó 
- código de seguranca 
- código de segurança 
- de kaart controle 
- geeft nr uit 
- issue no 
- issue number 
- kaartidentificatienummer 
- kreditkrtenprufnummer 
- kredit kredit kr krtenprのfnummer 
- kwestieaantal 
- 違います。 dell'dellzione 
- 違います。 di sicurezza 
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
- pr最も近い 
- security code 
- security no 
- security number 
- sicherheits kode 
- sicherheitscode 
- sicherheitsnummer 
- speldb数 
- veiligheid nr 
- heiigheidsaantal 
- heiigheidscode 
- heiigheidsnummer 
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
- expiration 
- expire 
- expires 
- expiry 
- fecha de expiracion 
- fecha de venc 
- gultig bis 
- gultigkeitsdatum 
- gültig bis 
- gtigkeitsdatum 
- la scadenza 
- scadcadcad 
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

これらは、EU の運転免許証番号の機密情報の種類のエンティティです。

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
- [ンジェムバー](#luxemburg-drivers-license-number)
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

これらは、EU の国民識別番号の機密情報の種類のエンティティです。

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
- [ンジェムバー](#luxemburg-national-identification-number-natural-persons)
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

これらは EU パスポート番号の機密情報の種類のエンティティです。これは EU パスポート番号バンドルのエンティティです。

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
- [ンジェムバー](#luxemburg-passport-number)
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


## <a name="eu-social-security-number-or-equivalent-identification"></a>EU 社会保障番号または同等の識別情報

これらは、EU 社会保障番号または同等の識別機密情報の種類に含んでいるエンティティです。

- [Austria](#austria-social-security-number-or-equivalent-identification)
- [Belgium](#belgium-social-security-number-or-equivalent-identification)
- [Croatia](#croatia-social-security-number-or-equivalent-identification)
- [チェコ語](#czech-social-security-number-or-equivalent-identification)
- [デンマーク](#denmark-social-security-number-or-equivalent-identification)
- [フィンランド](#finland-social-security-number-or-equivalent-identification)
- [France](#france-social-security-number-insee-or-equivalent-identification)
- [Germany](#germany-identity-card-number)
- [ギリシャ](#greece-national-id-card)
- [ハンガリー](#hungary-social-security-number-or-equivalent-identification)
- [Portugal](#portugal-citizen-card-number)
- [スペイン](#spain-social-security-number-ssn)
- [スウェーデン](#sweden-social-security-number-or-equivalent-identification)


## <a name="eu-tax-identification-number"></a>EU の税識別番号

これらのエンティティは、EU の税金識別番号の機密情報の種類です。

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
- [ンジェムバー](#luxemburg-national-identification-number-non-natural-persons)
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

ハイフンを含む 10 桁の数字と文字
  
### <a name="pattern"></a>パターン

ハイフンを含む 10 桁の数字と文字:
  
- 6 桁の数字 
- ハイフン
- 3 桁の数字 
- 1 桁の数字または文字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_finland_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_finland_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver's_license_number

- ajokortti
- permis de conduire
- ajokortin numero
- kuljja lic.
- körkort
- körkortnummer
- fの lic.
- ajokortit
- ajokortin numerot


## <a name="finland-european-health-insurance-number"></a>フィンランドの欧州の医療保険番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

20 桁の数字

### <a name="pattern"></a>パターン

20 桁の数字:

- 10 桁の数字 - 8024680246
- オプションのスペースまたはハイフン
- 10 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現はRegex_Finland_European_Health_Insurance_Numberパターンに一致するコンテンツを検索します。
- 検索されたKeyword_Finland_European_Health_Insurance_Number検索されます。

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
- finlandehicnumber#
- finska sjukfkfkfskringskort
- health card
- 医療保険証
- 医療保険番号
- hlsokort
- sairaanhoitokortin
- sai、v、utuskortti
- saierosveroutusnumero
- sjukfkfskring nummer
- sjukfkfskringskort
- suomen sai、v、utuskortti
- terveyskortti


## <a name="finland-national-id"></a>フィンランドの国民 ID

### <a name="format"></a>フォーマット

6 桁の数字と、100 年に 3 桁の数字とチェック ディジットを示す文字

### <a name="pattern"></a>パターン

パターンには、以下のすべてが含まれる必要があります。
- DDMMYY という形式で生年月日を表す 6 桁の数字 
- century マーカー ('-'、'+'、または 'a') 
- 3 桁の個人識別番号 
- チェック ディジットである数字または文字 (大文字と小文字を区別しない)

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数はFunc_finnish_national_idパターンに一致するコンテンツを検索します。
- 検索されたKeyword_finnish_national_id検出された
- チェックサムが渡される

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数はFunc_finnish_national_idパターンに一致するコンテンツを検索します。
- チェックサムが渡される

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
- id number
- identification number
- identiteetti numero
- ID 番号
- idnumber
- nen henkilötunnus
- llisen henkilökortin
- national id card
- national id no.
- 個人用 ID
- 個人用 ID コード
- personalidnumber#
- personbeteckning
- personnummer
- social security number
- sosiaaliturvatunnus
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- tunnistenumero
- tunnus numero
- tunnusl取
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>フィンランドのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類で利用できます。スタンドアロンの機密情報の種類のエンティティとして使用できます。

### <a name="format"></a>フォーマット
9 桁の文字と数字の組み合わせ

### <a name="pattern"></a>パターン
9 桁の文字と数字の組み合わせ:
- 2 文字 (大文字小文字を区別しない) 
- 7 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Regex_finland_passport_numberコンテンツを検索する正規表現。
- 検索または検索Keywords_eu_passport_number_commonキーワードKeyword_finland_passport_number検出されました。

```xml
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
</Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
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
- passi number


## <a name="finland-social-security-number-or-equivalent-identification"></a>フィンランドの社会保障番号または同等の識別情報
この機密情報の種類のエンティティは、EU 社会保障番号または同等の ID の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

指定された形式の 11 文字の組み合わせ
  
### <a name="pattern"></a>パターン

指定された形式の 11 文字の組み合わせ:
  
- 6 桁の数字 
- 次のいずれかのインスタンス:
  - プラス記号
  - マイナス記号
  - 文字 "A" (大文字と小文字を区別しない)
- 3 桁の数字
- 1 文字または 1 桁の数字
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_finland_eu_ssn_or_equivalent` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_finland_eu_ssn_or_equivalent` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_finland_eu_ssn_or_equivalent` 、パターンに一致するコンテンツを検索します。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a>Keywords_finland_eu_ssn_or_equivalent

- identification number
- 個人用 ID
- ID 番号
- フィンランドの国民 ID 番号
- personalidnumber#
- national identification number
- id number
- national id no.
- national id number
- id no
- tunnistenumero
- henkilötunnus
- yksilöeronen henkilökohtainen tunnistenumero
- ainutlaatuinen henkilökohtainen tunnus
- identiteetti numero
- suomennen henkilötunnus
- henkilötunnusnumero#
- erosen tunnistenumero
- tunnusnumero
- numeronen tunnus numero
- hetu


## <a name="france-drivers-license-number"></a>フランスの運転免許証番号

### <a name="format"></a>フォーマット

12 桁の数字

### <a name="pattern"></a>パターン

フランスの電話番号などの同様のパターンと区別するための検証付きの 12 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数はFunc_french_drivers_licenseパターンに一致するコンテンツを検索します。
- 検索されたKeyword_french_drivers_license検索されます。

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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers
- numéros de licence


## <a name="france-health-insurance-number"></a>フランスの医療保険番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

21 桁の数字

### <a name="pattern"></a>パターン

21 桁の数字:

- 10 桁の数字
- 省略可能なスペース
- 10 桁の数字
- 省略可能なスペース
- 1 桁の数字


### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- regex はRegex_France_Health_Insurance_Numberパターンに一致するコンテンツを検索します。
- 検索されたKeyword_France_Health_Insurance_Number検索されます。

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

- insurance card
- carte vitale
- carte d'assuré social


## <a name="france-national-id-card-cni"></a>フランスの国民 ID カード (CNI)

### <a name="format"></a>フォーマット

12 桁の数字

### <a name="pattern"></a>パターン

12 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_france_cni がパターンに一致するコンテンツを検出した。
- 検索されたKeywords_france_eu_national_id_card検索されます。

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
- carte nationale d'identité
- carte nationale d'ide ide ideide no
- cni#
- cni
- compte bancaire
- national identification number
- national identity
- nationalidno#
- numéro d'assurance maladie
- numéro de carte vitale

   
## <a name="france-passport-number"></a>フランスのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類で利用できます。スタンドアロンの機密情報の種類のエンティティとして使用できます。

### <a name="format"></a>フォーマット

9 桁の数字と文字

### <a name="pattern"></a>パターン

9 桁の数字と文字:
- 2 桁の数字 
- 2 文字 (大文字小文字を区別しない) 
- 5 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_fr_passport がパターンに一致するコンテンツを検出した。
- Keyword_passport のキーワードを検出した。

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

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
- 万の表示
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport#
- PasseportNon
- Passeportn °

      
## <a name="france-social-security-number-insee-or-equivalent-identification"></a>フランスの社会保障番号 (INSEE) または同等の識別情報
この機密情報の種類のエンティティは、EU 社会保障番号と同等の ID の機密情報の種類に含まれており、スタンドアロンの機密情報の種類のエンティティとして使用できます。

### <a name="format"></a>フォーマット

15 桁の数字

### <a name="pattern"></a>パターン

次のいずれかのパターンに一致する:
- 13 桁の数字の後にスペース、その後に 2 桁の数字<br/>
または
- 15 桁の連続する数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_french_inseeまたはFunc_fr_inseeパターンに一致するコンテンツを検索します。
- Keyword_fr_insee のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_french_inseeまたはFunc_fr_inseeパターンに一致するコンテンツを検索します。
- Keyword_fr_insee のキーワードを検出しなかった。
- チェックサムが渡される。

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- insee
- securité sociale
- securite sociale
- national id
- national identification
- numéro d'identité
- no d'identité
- 違います。 d'identité
- numero d'identite
- no d'identite
- 違います。 d'identite
- social security number
- social security code
- social insurance number
- le numéro d'identification nationale
- d'identité nationale
- numéro de sécurité sociale
- le code de la sécurité sociale
- numéro d'assurance sociale
- numéro de sécu
- code sécu 

## <a name="france-tax-identification-number"></a>フランスの税識別番号

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
- 3 桁のチェック ディジット 

  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_france_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_france_eu_tax_file_number` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_france_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
    
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

- numéro d'identification fiscale
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="france-value-added-tax-number"></a>フランスの付加価値税番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

13 文字の英数字パターン

### <a name="pattern"></a>パターン

13 文字の英数字のパターン:

- 2 文字 - FR (大文字と小文字を区別しない)
- オプションのスペースまたはハイフン
- 2 桁の文字または数字
- 省略可能なスペース、ドット、ハイフン、またはコンマ
- 3 桁の数字
- オプションのスペース、ドット、ハイフン、またはコンマ
- 3 桁の数字
- 省略可能なスペース、ドット、ハイフン、またはコンマ
- 3 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_france_value_added_tax_numberパターンに一致するコンテンツを検索します。
- 検索されたKeywords_france_value_added_tax_number検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_france_value_added_tax_numberパターンに一致するコンテンツを検索します。

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

- vat number
- vat no
- vat#
- 付加価値税
- siren identification no numéro d'identification taxe sur sur surur ajoutée
- taxe taxur ajoutée
- taxe sur la surjoutée
- n° tva
- numéro de tva
- numéro d'identification siren


## <a name="germany-drivers-license-number"></a>ドイツの運転免許証番号

### <a name="format"></a>フォーマット

11 桁の数字と文字の組み合わせ

### <a name="pattern"></a>パターン

11 個の数字と文字 (大文字小文字を区別しない):
- 1 桁の数字または文字 
- 2 桁の数字 
- 6 桁の数字または文字 
- 1 桁の数字 
- 1 桁の数字または文字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- fcheerschein
- fuhrerschein
- fuehrerschein
- fcheinnummer
- fuhrerscheinnummer
- fuehrerscheinnummer
- fchehrerschein- 
- fuhrerschein- 
- fuehrerschein- 
- fcheerscheinnummernr
- fuhrerscheinnummernr
- fuehrerscheinnummernr
- fcheerscheinnummercheasse
- fuhrerscheinnummer fuasse
- fuehrerscheinnummer fuasse
- nr-fのhrerschein
- nr-fuhrerschein
- nr-fuehrerschein
- no-fcheerschein
- no-fuhrerschein
- no-fuehrerschein
- n-fcheerschein
- n-fuhrerschein
- n-fuehrerschein
- permis de conduire
- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dlno


## <a name="germany-identity-card-number"></a>ドイツの ID カード番号

### <a name="format"></a>フォーマット

2010 年 11 月 1 日以降: 9 桁の文字と数字

1987 年 4 月 1 日から 2010 年 10 月 31 日まで: 10 桁の数字

### <a name="pattern"></a>パターン

2010 年 11 月 1 日以降:
- 1 文字 (大文字小文字を区別しない) 
- 8 桁の数字

1987 年 4 月 1 日から 2010 年 10 月 31 日まで:
- 10 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Regex_germany_id_cardコンテンツを検索する正規表現。
- 検索されたKeyword_germany_id_card検索されます。

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- ausweis
- gpid
- identification
- identifikation
- identifizierungsnummer
- Identity card
- ID 番号
- id-nummer
- 個人用 ID
- personalausweis
- pers、liche id nummer
- pers、liche identifikationsnummer
- pers、liche-id-nummer


## <a name="germany-passport-number"></a>ドイツのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類に含まれており、スタンドアロンの機密情報の種類のエンティティとして使用できます。

### <a name="format"></a>フォーマット

10 桁の数字または文字

### <a name="pattern"></a>パターン

パターンには、以下のすべてが含まれる必要があります。
- 最初の文字は、このセットの数字または文字 (C、F、G、H、J、K) です。 
- 3 桁の数字 
- このセットの 5 桁の数字または文字 (C、-H、J-N、P、R、T、V-Z) 
- 1 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_german_passport がパターンに一致するコンテンツを検出した。
- キーワードを `Keyword_german_passport` 検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_german_passport_data がパターンに一致するコンテンツを検出した。
- キーワードを `Keyword_german_passport` 検出した。
- チェックサムが渡される。

```xml
    <!-- German Passport Number -->
    <Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Match idRef="Keyword_german_passport" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Match idRef="Keyword_german_passport" />
      </Pattern>
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
- reisep sse
- passeport no.
- passeport no

## <a name="germany-tax-identification-number"></a>ドイツの税金の識別番号

### <a name="format"></a>フォーマット

スペースと区切り記号を含めずに 11 桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字:
  
- 2 桁の数字 
- 省略可能なスペース
- 3 桁の数字 
- 省略可能なスペース
- 3 桁の数字 
- 省略可能なスペース
- 2 桁の数字
- 1 桁のチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_germany_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_germany_eu_tax_file_number` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_germany_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
    
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
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- z最も近い#
- z最も近い
- znummer


## <a name="germany-value-added-tax-number"></a>ドイツの付加価値税番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

11 文字の英数字パターン

### <a name="pattern"></a>パターン

11 文字の英数字のパターン:

- D または d の文字
- E または e の文字
- 省略可能なスペース
- 3 桁の数字
- 省略可能なスペースまたはコンマ
- 3 桁の数字
- 省略可能なスペースまたはコンマ
- 3 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_germany_value_added_tax_numberパターンに一致するコンテンツを検索します。
- 検索されたKeywords_germany_value_added_tax_number検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_germany_value_added_tax_numberパターンに一致するコンテンツを検索します。

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

- vat number
- vat no
- vat#
- vat# mehrwertsteuer
- wbst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer


## <a name="greece-drivers-license-number"></a>ギリシャの運転免許証番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 9 桁の数字
  
### <a name="pattern"></a>パターン

9 桁の数字 
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_greece_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_greece_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver's_license_number

- δεια οδήγησης
- Adeia odigigigs
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

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Regex_greece_id_cardコンテンツを検索する正規表現。
- 検索されたKeyword_greece_id_card検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Regex_greece_id_cardコンテンツを検索する正規表現。

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
- ギリシャの国民 ID
- ギリシャの個人用 ID カード
- ギリシャ語の警察 ID
- Identity card
- tautotita
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>ギリシャのパスポート番号

この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

2 桁の文字の後に 7 桁の数字 (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

2 桁の文字の後に 7 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現は、  `Regex_greece_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_greece_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο

## <a name="greece-tax-identification-number"></a>ギリシャの税金の識別番号
この機密情報の種類は、次の場合にのみ使用できます。
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

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現は、  `Regex_greece_eu_tax_file_number` パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_greece_eu_tax_file_number` 検出した。 
    
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
- a μ|a α μ α α≦
- a μ
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- tax registry no
- tax registry number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- taxregistryno#
- tin id
- tin no
- tin#
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>香港の ID カード (HKID) 番号

### <a name="format"></a>フォーマット

8 ～ 9 桁の文字と数字の組み合わせ、最後の文字はかっこで囲むことも可能

### <a name="pattern"></a>パターン

8 ～ 9 桁の文字の組み合わせ:
- 1 ～ 2 桁の文字 (大文字小文字の区別なし)  
- 6 桁の数字 
- チェック ディジットとして機能する最後の文字 (任意の数字か文字 A) はかっこで囲むことも可能。

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_hong_kong_id_cardパターンに一致するコンテンツを検索します。
- 検索されたKeyword_hong_kong_id_card検出された。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_hong_kong_id_cardパターンに一致するコンテンツを検索します。
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
- hk identity card
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

2 桁の文字の後に 6 桁の数字
  
### <a name="pattern"></a>パターン

2 桁の文字と 6 桁の数字:
  
- 2 文字 (大文字と小文字を区別しない) 
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現は、  `Regex_hungary_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_hungary_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver's_license_number

- vezetoi engedely
- vezetéi engedély
- vezetéi engedélyek


## <a name="hungary-personal-identification-number"></a>ハンガリーの個人識別番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

11 桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字:
  
- 性別に対応する 1 桁の数字 (1900 年以前に生まれた市民または二重国籍を持つ市民の場合は、1 人の男性、2 人の女性、その他の数字も可能) 
- 生年月日 (YYMMDD) に対応する 6 桁の数字
- シリアル番号に対応する 3 桁の数字
- 1 桁のチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- この関数は  `Func_hungary_eu_national_id_card` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_hungary_eu_national_id_card` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- この関数は  `Func_hungary_eu_national_id_card` 、パターンに一致するコンテンツを検索します。 
    
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

- id number
- identification number
- sz ig
- sz. ig.
- sz.ig.
- személyazonosító zonzolvzony
- személyi zolvlvy


## <a name="hungary-passport-number"></a>ハンガリーのパスポート番号

この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

2 桁の文字の後に 6 桁または 7 桁の数字 (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

2 桁の文字の後に 6 桁または 7 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現は、  `Regex_hungary_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_hungary_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```
### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám

## <a name="hungary-social-security-number-or-equivalent-identification"></a>ハンガリーの社会保障番号または同等の識別情報

この機密情報の種類のエンティティは、EU 社会保障番号または同等の ID の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

スペースと区切り記号のない 9 桁の数字
  
### <a name="pattern"></a>パターン

9 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- この関数は  `Func_hungary_eu_ssn_or_equivalent` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_hungary_eu_ssn_or_equivalent` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- この関数は  `Func_hungary_eu_ssn_or_equivalent` 、パターンに一致するコンテンツを検索します。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
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
- 、
- általtaltalos forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>ハンガリーの税金の識別番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースまたは区切り記号を含めない 10 桁の数字
  
### <a name="pattern"></a>パターン

10 桁の数字:
  
- "8" でなければならない 1 桁の数字 
- 8 桁の数字
- 1 桁のチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- この関数は  `Func_hungary_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_hungary_eu_tax_file_number` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- この関数は  `Func_hungary_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
    
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
- ハンガリースズ
- hungatiantin#
- tax authority no
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- vat number


## <a name="hungary-value-added-tax-number"></a>ハンガリーの付加価値税番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

10 文字の英数字パターン

### <a name="pattern"></a>パターン

10 文字の英数字のパターン:

- 2 文字 - HU または hu
- 省略可能なスペース
- 8 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。

- この関数はFunc_hungarian_value_added_tax_numberパターンに一致するコンテンツを検索します。
- 検索されたKeywords_hungarian_value_added_tax_number検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。

- この関数はFunc_hungarian_value_added_tax_numberパターンに一致するコンテンツを検索します。

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
- 、
- általtaltalos forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-permanent-account-number-pan"></a>インドの永続的なアカウント番号 (PAN)

### <a name="format"></a>フォーマット

10 桁の文字または数字

### <a name="pattern"></a>パターン

10 桁の文字または数字:
- 3 文字 (大文字小文字を区別しない) 
- C、P、H、F、A、T、B、L、J、G の文字 (大文字小文字を区別しない)
- レター
- 4 桁の数字 
- 文字 (大文字と小文字を区別しない)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Regex_india_permanent_account_numberコンテンツを検索する正規表現。
- 検索されたKeyword_india_permanent_account_number検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Regex_india_permanent_account_numberコンテンツを検索する正規表現。


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
   
## <a name="india-unique-identification-aadhaar-number"></a>インド固有の識別番号 (Aadhaar)

### <a name="format"></a>フォーマット

省略可能なスペースまたはハイフンを含む 12 桁の数字

### <a name="pattern"></a>パターン

12 桁の数字:
- 0 または 1 ではない数字
- 3 桁の数字 
- スペースまたはハイフン 1 つ (省略可能)  
- 4 桁の数字 
- スペースまたはハイフン 1 つ (省略可能)  
- 最後の数字はチェック ディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_india_aadhaarパターンに一致するコンテンツを検索します。
- 検索されたKeyword_india_aadhar検索されます。
- チェックサムが渡される。
- 
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。

- この関数はFunc_india_aadhaarパターンに一致するコンテンツを検索します。
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
- DDMMYY の形式の生年月日を表す 6 桁の数字  
- ピリオド 1 つ (省略可能)  
- 4 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。

- パターンに一Regex_indonesia_id_cardコンテンツを検索する正規表現。
- 検索されたKeyword_indonesia_id_card検索されます。

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

国コード (2 文字) とチェックディジット (2 桁の数字) と bban 番号 (最大 30 文字)

### <a name="pattern"></a>パターン

パターンには、以下のすべてが含まれる必要があります。

- 2 文字の国コード
- 2 桁のチェックディジット (オプションのスペースが続く) 
- 4 桁の文字または数字で構成される 1 ~ 7 個のグループ (スペースで区切り可能)
- 1 ～ 3 個の文字または数字

国ごとに形式が少し異なります。 IBAN の機密情報の種類は、次の 60 か国を対象とします。

ad、ae、al、at、az、ba、be、bg、bh、ch、 cr、cy、cz、de、dk、do、ee、es、fi、fo、fr、gb、ge、gi、gl、gr、hr、hu、ie、il、is、it、kw、kz、lb、li、lt、lu、lv、mc、md、me、mk、mr、mt、mu、nl、no、pl、pt、ro、rs、sa、se、si、sk、sm、tn、tr、vg

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。

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

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 検索されたDictionary_icd_10_updated検索されます。
- 検索されたDictionary_icd_10_codes検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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

Dictionary_icd_10_updated キーワード ディクショナリの任意の用語。これは、国際化の分類、10 番目のリビジョン、変更 [(ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604)に基づいて作成されます。 この型は、保険コードではなく、用語のみを検索します。

Dictionary_icd_10_codes キーワード ディクショナリの任意の用語。これは、国際言語の分類、10 番目のリビジョン、変更 [(ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604)に基づいて作成されます。 この型は、説明ではなく、保険コードのみを検索します。

## <a name="international-classification-of-diseases-icd-9-cm"></a>病気の国際分類 (ICD-9-CM)

### <a name="format"></a>フォーマット

Dictionary

### <a name="pattern"></a>パターン

キーワード

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 検索されたDictionary_icd_9_updated検索されます。
- 検索されたDictionary_icd_9_codes検出された。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 検索されたDictionary_icd_9_updated検索されます。

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

Dictionary_icd_9_updated キーワード ディクショナリの任意の用語。これは、国際化の分類、9 番目のリビジョン、変更 [(ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605)に基づくもの。 この型は、保険コードではなく、用語のみを検索します。

Dictionary_icd_9_codes キーワード ディクショナリからの任意の用語。これは、国際化の分類、9 番目のリビジョン、変更の修正 [(ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605)に基づくもの。 この型は、説明ではなく、保険コードのみを検索します。

## <a name="ip-address"></a>IP アドレス

### <a name="format"></a>フォーマット

#### <a name="ipv4"></a>IPv4:
書式設定あり (ピリオド付き) または書式設定なし (ピリオドなし) のIPv4 アドレスを表す複雑なパターン

#### <a name="ipv6"></a>IPv6:
 書式設定あり (コロン付き) の IPv6 番号を表す複雑なパターン

### <a name="pattern"></a>パターン

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。
- Keyword_ipaddress のキーワードを検出しなかった。

IPv4 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_ipv4_address がパターンに一致するコンテンツを検出した。
- Keyword_ipaddress のキーワードを検出した。

IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。
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

## <a name="ireland-drivers-license-number"></a>アイルランドの運転免許証番号

### <a name="format"></a>フォーマット

6 桁の数字の後に 4 文字
  
### <a name="pattern"></a>パターン

6 桁の数字と 4 桁の文字:
  
- 6 桁の数字
- 4 文字 (大文字小文字を区別しない)
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現は、  `Regex_ireland_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_ireland_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver's_license_number

- cead数as tiom tiom tiom tiom tia
- cead tiais tiom tiom数a

## <a name="ireland-passport-number"></a>アイルランドのパスポート番号

この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

2 桁の文字または数字の後に 7 桁の数字 (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

2 桁の文字または数字、その後に 7 桁の数字:
  
- 2 つの数字または文字 (大文字小文字を区別しない)
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
  
- 正規表現は、  `Regex_ireland_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_ireland_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport numero
- uimhreacha pas pas数
- uimhir pas
- uimhirphas
- uimhreacha pas
- uimhir chirta
- uimhir chhirta

## <a name="ireland-personal-public-service-pps-number"></a>アイルランドの個人公共サービス (PPS) 番号

### <a name="format"></a>フォーマット

古い形式 (2012 年 12 月 31 日まで):
- 7 桁の数字の後に 1 ~ 2 桁の文字 

新しい形式 (2013 年 1 月 1 日以降):
- 7 桁の数字の後に 2 文字

### <a name="pattern"></a>パターン

古い形式 (2012 年 12 月 31 日まで):
- 7 桁の数字 
- 1 ~ 2 文字 (大文字小文字を区別しない) 

新しい形式 (2013 年 1 月 1 日以降):
- 7 桁の数字 
- アルファベットのチェック ディジットである文字 (大文字小文字を区別しない) 
- A ~ I の範囲の省略可能な文字、または "W"

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_ireland_ppsパターンに一致するコンテンツを検索します。
- 検索されたKeywords_ireland_eu_national_id_card検索されます。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_ireland_ppsパターンに一致するコンテンツを検索します。
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
- 個人の公共サービス番号
- 個人用サービスなし
- phearsantarbrbhíse poiblí
- pps no
- pps number
- pps num
- pps service no
- ppsn
- ppsno#
- ppsno
- psp
- パブリック サービスなし
- publicserviceno#
- publicserviceno
- 収益と社会保険番号
- rsi no
- rsi number
- rsin
- rbhís aitheantais クライアント
- uimh
- uimhir aitheantais chachach
- uimhir aitheantais phearsanta
- uimhir phearsantarbhíse poiblí
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="israel-bank-account-number"></a>イスラエルの銀行口座番号

### <a name="format"></a>フォーマット

13 桁の数字

### <a name="pattern"></a>パターン

書式設定:
- 2 桁の数字 
- ダッシュ 
- 3 桁の数字 
- ダッシュ 
- 8 桁の数字

書式設定されていない場合:
- 	13 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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

9 桁の数字

### <a name="pattern"></a>パターン

9 桁の連続する数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
-   id number
-   ID no        
-   identitynumber#
-   ID 番号
-   identitynumber       
-   個人用 ID
-   一意の ID  

   
## <a name="italy-drivers-license-number"></a>イタリアの運転免許証番号

### <a name="format"></a>フォーマット

10 桁の文字と数字の組み合わせ

### <a name="pattern"></a>パターン

10 桁の文字と数字の組み合わせ:
- 1 文字 (大文字小文字を区別しない) 
- 文字 "A" または "V" (大文字小文字を区別しない) 
- 7 桁の数字
- 1 文字 (大文字小文字を区別しない)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現 Regex_italy_drivers_license_number がパターンに一致するコンテンツを検出した。
- Keyword_italy_drivers_license_number のキーワードを検出した。

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente
- patente di guida 
- patente guida
- patenti di guida
- patenti guida

## <a name="italy-fiscal-code"></a>イタリアの会計コード
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

指定したパターンの 16 文字の文字と数字の組み合わせ
  
### <a name="pattern"></a>パターン

16 文字の文字と数字の組み合わせ:
- ファミリ名の最初の 3 つの子に対応する 3 文字
- 名の最初、3 番目、および 4 番目の子に対応する 3 文字
- 生年月日の最後の数字に対応する 2 桁の数字
- 1 文字が出生月のレターに対応します。文字はアルファベット順で使用されますが、A から E、H、L、M、P、R ~ T の文字だけが使用されます (したがって、1 月は A、10 月は R です)。
- 生年月日に対応する 2 桁の数字—性別を区別するために、40 が女性の生年月日に追加されます。
- 人物が生まれた場所に固有の市外コードに対応する 4 桁の数字 (国外では国全体のコードが使用されます)
- 1 つのパリティ ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_italy_eu_national_id_card` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_italy_eu_national_id_card` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_italy_eu_national_id_card` 、パターンに一致するコンテンツを検索します。 
    
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

- codice fiscal
- codice fiscale
- codice id personale
- codice personale
- 会計コード
- numero certificato personale
- numero di identific di identific di fiscale
- numero id personale
- numero personale
- 個人の証明書番号
- 個人用コード
- 個人用 ID コード
- 個人用 ID 番号
- personalcodeno#
- tax code
- tax id
- tax identification no
- 税識別番号
- tax identity number
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="italy-passport-number"></a>イタリアのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

2 桁の文字または数字の後に 7 桁の数字 (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

2 桁の文字または数字、その後に 7 桁の数字:
  
- 2 桁の数字または文字 (大文字小文字を区別しない)
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_italy_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_italy_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiana
- passaporto numero
- numéro passeport
- numero di passaporto
- numeri del passaporto
- passeport italien

## <a name="italy-value-added-tax-number"></a>イタリアの付加価値税番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

13 文字の英数字パターンとオプションの区切り文字

### <a name="pattern"></a>パターン

13 文字の英数字パターンとオプションの区切り文字:

- I または i
- T または t
- オプションのスペース、ドット、ハイフン、またはコンマ
- 11 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_italy_value_added_tax_numberパターンに一致するコンテンツを検索します。
- 検索されたKeywords_italy_value_added_tax_number見つかりました。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_italy_value_added_tax_numberパターンに一致するコンテンツを検索します。

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

- vat number
- vat no
- vat#
- 最も近い
- 最も近い#


## <a name="japan-bank-account-number"></a>日本の銀行口座番号

### <a name="format"></a>フォーマット

7 桁または 8 桁の数字

### <a name="pattern"></a>パターン

銀行口座番号:
- 7 桁または 8 桁の数字
- 銀行口座のブランチ コード:
- 4 桁の数字 
- スペースまたはダッシュ (省略可能) 
- 3 桁の数字

チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。
- Keyword_jp_bank_account のキーワードを検出した。
- 次のいずれかの条件に該当する:
- 関数 Func_jp_bank_account_branch_code がパターンに一致するコンテンツを検出した。
- Keyword_jp_bank_branch_code のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- "最も近い"
- "最も近い"
- データの変更
- 最も近い
- 運転経歴証明書番号
- 運転経歴証明書
- [最も近い]
- "最も近い"
- ?証。??
- 最も近い
- 運転免許証#
- 運転免許#
- 免許証#
- 免許#


## <a name="japan-my-number---corporate"></a>日本のマイ ナンバー - 企業
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

13 桁の数字

### <a name="pattern"></a>パターン

13 桁の数字:

- 1 から 9 の 1 桁の数字
- 12 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_japanese_my_number_corporateパターンに一致するコンテンツを検索します。
- 検索されたKeywords_japanese_my_number_corporate検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_japanese_my_number_corporateパターンに一致するコンテンツを検索します。

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


## <a name="japan-my-number---personal"></a>日本のマイ ナンバー - 個人用
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

12 桁の数字

### <a name="pattern"></a>パターン

12 桁の数字:

- 4 桁の数字
- オプションのスペース、ドットまたはハイフン
- 4 桁の数字
- オプションのスペース、ドットまたはハイフン
- 4 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_japanese_my_number_personalパターンに一致するコンテンツを検索します。
- 検索されたKeywords_japanese_my_number_personal検出された。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_japanese_my_number_personalパターンに一致するコンテンツを検索します。

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

2 桁の文字の後に 7 桁の数字

### <a name="pattern"></a>パターン

2 桁の文字 (大文字小文字を区別しない) の後に 7 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- パスポート#
- パスポート#
- が表示されます。
- 旅券番号
- 旅券番号#
- 旅券番号♯
- 旅券ナンバー


## <a name="japan-residence-card-number"></a>日本の名刺番号

### <a name="format"></a>フォーマット

12 桁の文字と数字

### <a name="pattern"></a>パターン

12 桁の文字と数字:
- 2 文字 (大文字小文字を区別しない)
- 8 桁の数字 
- 2 文字 (大文字小文字を区別しない)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Regex_jp_residence_card_numberコンテンツを検索する正規表現。
- 検索されたKeyword_jp_residence_card_number検索されます。

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

- 名刺番号
- 名刺なし
- 名刺#
- 在留カード番号
- 在留カード
- 在留番号

## <a name="japan-resident-registration-number"></a>日本の住民登録番号

### <a name="format"></a>フォーマット

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- 4 桁の数字 
- ハイフン (省略可能) 
- 6 桁の数字 OR
- 7 ～ 12 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_jp_sin がパターンに一致するコンテンツを検出した。
- Keyword_jp_sin のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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

3 桁の文字の後に 6 桁の数字
  
### <a name="pattern"></a>パターン

3 桁の文字と 6 桁の数字:
  
- 3 文字 (大文字と小文字を区別しない) 
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_latvia_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_latvia_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver's_license_number

- autovadvatāja apliecvaba
- autovadvatāja apliecvas
- vadvatāja apliecva

## <a name="latvia-personal-code"></a>ラトビアの個人コード

### <a name="format"></a>フォーマット

11 桁の数字とオプションのハイフン
  
### <a name="pattern"></a>パターン

古い形式

11 桁の数字とハイフン:
  
- 生年月日に対応する 6 桁の数字 (DDMMYY) 
- ハイフン
- 1 桁の数字 (19th century の場合は "0"、20th century の場合は "1"、21st century の場合は "2")
- 4 桁の数字(ランダムに生成)

新しい形式

11 桁の数字

- 2 桁の数字 "32"
- 9 桁の数字
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数または  `Func_latvia_eu_national_id_card` 正規表現が `Regex_latvia_eu_national_id_card_new_format` パターンに一致するコンテンツを見つける。 
- キーワードを  `Keywords_latvia_eu_national_id_card` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数または  `Func_latvia_eu_national_id_card` 正規表現が `Regex_latvia_eu_national_id_card_new_format` パターンに一致するコンテンツを見つける。 
    
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

- 管理用番号
- a最も近い
- 生年月日
- citizen number
- ユーザー番号
- electronic census number
- 電子番号
- 会計コード
- 医療ユーザー番号
- id#
- id-code
- identification number
- identifikāc numurs
- id-number
- 個別の番号
- latv、a、
- nacionālais id
- national id
- national identifying number
- national identity number
- national insurance number
- national register number
- nodok a numurs
- nodok の id
- nodok、identifikāc、 numurs
- 個人の証明書番号
- 個人用コード
- 個人用 ID コード
- 個人用 ID 番号
- 個人識別コード
- 個人識別子
- 個人の ID 番号
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
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- 投票者の番号

## <a name="latvia-passport-number"></a>ラトビアのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

2 桁の文字または数字の後に 7 桁の数字 (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

2 桁の文字または数字、その後に 7 桁の数字:
  
- 2 桁の数字または文字 (大文字小文字を区別しない)
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_latvia_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_latvia_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
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

## <a name="lithuania-drivers-license-number"></a>リトアニアの運転免許証番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 8 桁の数字
  
### <a name="pattern"></a>パターン

8 桁の数字 
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_lithuania_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_lithuania_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver's_license_number

- vair、tojo pa、ym、および
- vaireritojo paのymjimo numeris
- vair、tojo pa、ym、jimo numeriai

## <a name="lithuania-personal-code"></a>リトアニアの個人コード
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースと区切り記号を含めずに 11 桁の数字
  
### <a name="pattern"></a>パターン

スペースと区切り記号のない 11 桁の数字:
  
- 性別と出生時の年齢に対応する 1 桁の数字 (1 ~ 6)
- 生年月日に対応する 6 桁の数字 (YYMMDD) 
- 生年月日のシリアル番号に対応する 3 桁の数字
- 1 桁のチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_lithuania_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_lithuania_eu_tax_file_number` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_lithuania_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
    
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
- citizen service number
- mokesčič id
- mokesčiの identifikavimas numeris
- mokesčiの identifikavimo numeris
- mokesči numeris
- national identification number
- 個人用コード
- 個人の数値コード
- piliečio paslaugos numeris
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- unlulus identifikavimo kodas
- unerilus identifikavimo numeris
- 一意の ID 番号
- 一意の ID 番号
- uniqueidentityno#

## <a name="lithuania-passport-number"></a>リトアニアのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

スペースまたは区切り文字を含めない 8 桁の数字または文字
  
### <a name="pattern"></a>パターン

8 桁の数字または文字 (大文字と小文字を区別しない)
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_lithuania_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_lithuania_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- paso numeris
- paso numeriai
- paso nr

## <a name="luxemburg-drivers-license-number"></a>ジェムバーガーの運転免許証番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 6 桁の数字
  
### <a name="pattern"></a>パターン

6 桁の数字 
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_luxemburg_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_luxemburg_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver's_license_number

- fahrerlaubnis
- Führerschschのin

## <a name="luxemburg-national-identification-number-natural-persons"></a>ウレンザフの国民識別番号 (自然人)
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

13 桁の数字 (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

13 桁の数字:
  
- 11 桁の数字 
- 2 桁のチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_luxemburg_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_luxemburg_eu_national_id_card` 検出した。 

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_luxemburg_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 


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
- individual id
- 個別の識別
- 個別の ID
- numéro d'identification personnel
- 個人用 ID
- 個人識別
- 個人用 ID
- personalidno#
- personalidnumber#
- pers、liche identifikationsnummer
- 一意の ID
- 一意の ID
- uniqueidkey#

## <a name="luxemburg-passport-number"></a>ジェムザフのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

スペースまたは区切り文字を含めない 8 桁の数字または文字
  
### <a name="pattern"></a>パターン

8 桁の数字または文字 (大文字と小文字を区別しない)
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_nation_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_nation_eu_passport_number` 検出した。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_nation_eu_passport_number"></a>Keywords_nation_eu_passport_number

- passport number
- ラトビアのパスポート番号
- passport no
- passnummer

## <a name="luxemburg-national-identification-number-non-natural-persons"></a>ウレンザフの国民識別番号 (非自然人)

### <a name="format"></a>フォーマット

11 桁の数字
  
### <a name="pattern"></a>パターン

11 桁の数字
  
- 2 桁の数字
- 省略可能なスペース 
- 3 桁の数字 
- 省略可能なスペース
- 3 桁の数字 
- 省略可能なスペース
- 2 桁の数字
- 1 桁のチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_luxemburg_eu_tax_file_number_non_natural` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_luxemburg_eu_tax_file_number` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_luxemburg_eu_tax_file_number_non_natural` 、パターンに一致するコンテンツを検索します。 
    
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
- identifiant d'impôt
- ルクセンブルクの税金 identifikatiounsnummer
- numéro d'étain
- numéro d'identification fiscal luxembourgeois
- numéro d'identification fiscale
- social security
- so最も近い
- sounglversécherung
- sozialversicherungsausweis
- steier id
- steier identifikatiounsnummer
- steier nummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- z最も近い#
- z最も近い
- zzazahl


## <a name="malaysia-identification-card-number"></a>マレーシアの識別カード番号

### <a name="format"></a>フォーマット

省略可能なハイフンを含む 12 桁の数字

### <a name="pattern"></a>パターン

12 桁の数字:
- YYMMDD 形式で生年月日を表す 6 桁の数字 
- ダッシュ (省略可能) 
- 2 文字の出生時コード 
- ダッシュ (省略可能) 
- 3 桁のランダムな数字 
- 1 桁の性別コード

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現はRegex_malaysia_id_card_numberパターンに一致するコンテンツを検索します。
- 検索されたKeyword_malaysia_id_card_number検索されます。

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
- i/c no
- ic
- ic no
- id card
- identification Card
- Identity card
- k/p
- k/p no
- kad akuan diri
- kad aplkasi digital
- kad pengenalan マレーシア
- kp
- kp no
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

指定したパターンでの 2 文字と 6 桁の数字の組み合わせ
  
### <a name="pattern"></a>パターン

2 文字と 6 桁の数字の組み合わせ:
  
- 2 文字 (数字または文字、大文字と小文字を区別しない)
- スペース (省略可能)
- 3 桁の数字
- スペース (省略可能)
- 3 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_malta_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_malta_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver's_license_number

- liċenzja tas-liċenzja qan
- liċenzji tas-liċenzji wieq


## <a name="malta-identity-card-number"></a>マルタの ID カード番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

7 桁の数字の後に 1 文字
  
### <a name="pattern"></a>パターン

7 桁の数字の後に 1 文字
  
- 7 桁の数字 
- "M, G, A, P, L, H, B, Z" の 1 文字 (大文字と小文字を区別しない)
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_malta_eu_national_id_card` パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_malta_eu_national_id_card` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
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

- citizen service number
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni un un"
- numru ta' identità un un un"
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 個人の数値コード
- 一意の ID 番号
- 一意の ID 番号
- uniqueidentityno#


## <a name="malta-passport-number"></a>マルタのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

スペースまたは区切り記号のない 7 桁の数字
  
### <a name="pattern"></a>パターン

7 桁の数字 
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_malta_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_malta_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- Nru tal-passaport

## <a name="malta-tax-identification-number"></a>マルタの税識別番号

### <a name="format"></a>フォーマット

マルタの国民の場合:
- 指定されたパターンの 7 桁の数字と 1 文字
  
マルタ以外の国民およびマルタのエンティティ:
- 9 桁の数字
  
### <a name="pattern"></a>パターン

マルタの国民: 7 桁の数字と 1 文字
  
- 7 桁の数字 
- 1 文字 (大文字と小文字を区別しない)
    
マルタ以外の国民およびマルタのエンティティ: 9 桁の数字
  
- 9 桁の数字 
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- regex  `Regex_malta_eu_tax_file_number`  または `Regex_malta_eu_tax_file_number_non_maltese_national` パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_malta_eu_tax_file_number` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- regex  `Regex_malta_eu_tax_file_number` または `Regex_malta_eu_tax_file_number_non_maltese_national` パターンに一致するコンテンツを検索します。 
    
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

- citizen service number
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni un un"
- numru ta' identità un un un"
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 個人の数値コード
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- 一意の ID 番号
- 一意の ID 番号
- uniqueidentityno#

## <a name="netherlands-citizens-service-bsn-number"></a>オランダの市民サービス (BSN) 番号

### <a name="format"></a>フォーマット

省略可能なスペースを含む 89 桁の数字

### <a name="pattern"></a>パターン

8 桁の数字:
- 3 桁の数字 
- スペース (省略可能) 
- 3 桁の数字 
- スペース (省略可能) 
- 2 桁の 3 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_netherlands_bsnパターンに一致するコンテンツを検索します。
- 検索されたKeyword_netherlands_bsn検索されます。
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
- servicenummer
- citizen service number
- ユーザー番号
- 個人番号
- 個人の数値コード
- 人物関連の番号
- persoonlijk nummer
- persoonlijke numjkke コード
- persoonsge最も近い
- persoonsnummer
- sociaal-fiscaal nummer
- social-fiscal number
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

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_netherlands_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_netherlands_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver's_license_number

- permis de conduire
- rijbewijs
- rijbewijsnummer
- rijbewzenzen
- rijbewijs nummer
- rijbewijsnummers


## <a name="netherlands-passport-number"></a>オランダのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

スペースまたは区切り記号を含めない 9 桁の文字または数字
  
### <a name="pattern"></a>パターン

9 桁の文字または数字
  
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_netherlands_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_netherlands_eu_passport_number` 検出した。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- オランダのパスポート番号
- passport number
- オランダのパスポート番号
- nederlanden paspoort nummer
- paspoort
- nederlanden paspoortnummer
- paspoortnummer

## <a name="netherlands-tax-identification-number"></a>オランダの税識別番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースまたは区切り記号のない 9 桁の数字
  
### <a name="pattern"></a>パターン

9 桁の数字 
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_netherlands_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_netherlands_eu_tax_file_number` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_netherlands_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
    
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
- hollânske の税金の識別
- hulandes impuesto id number
- hulandes impuesto identification
- identificatienummer belasting
- identificatienummer van belasting
- impuesto id number
- impuesto number
- nederlands belasting id nummer
- nederlands belasting identificatie
- nederlands belasting identificatienummer
- nederlands belastingnummer
- nederlandse belasting identificatie
- オランダの税金の識別
- netherland の税金の識別
- オランダの tin
- netherland's tin
- tax id
- tax identification no
- 税識別番号
- tax identification tal
- tax no#
- tax no
- tax number
- tax registration number
- tax tal
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="netherlands-value-added-tax-number"></a>オランダの付加価値税番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

14 文字の英数字パターン

### <a name="pattern"></a>パターン

14 文字の英数字のパターン:

- N または n
- L または l
- オプションのスペース、ドットまたはハイフン
- 9 桁の数字
- オプションのスペース、ドットまたはハイフン
- B または b
- 2 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_netherlands_value_added_tax_numberパターンに一致するコンテンツを検索します。
- 検索されたKeywords_netherlands_value_added_tax_number検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_netherlands_value_added_tax_numberパターンに一致するコンテンツを検索します。

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

- vat number
- vat no
- vat#
- wearde tafoege tax getal
- btw ntwmer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>ニュージーランドの銀行口座番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

14 ~ 16 桁のパターンとオプションの区切り文字

### <a name="pattern"></a>パターン

14 ~ 16 桁のパターンとオプションの区切り文字:

- 2 桁の数字
- 任意指定のハイフンまたはスペース
- 3 ~ 4 桁の数字
- 任意指定のハイフンまたはスペース
- 7 桁の数字
- 任意指定のハイフンまたはスペース
- 2 ~ 3 桁の数字
- オプションのハイフンまたはスペース

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_new_zealand_bank_account_numberパターンに一致するコンテンツを検索します。
- 検索されたKeywords_new_zealand_bank_account_number検出された。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_new_zealand_bank_account_numberパターンに一致するコンテンツを検索します。

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
- bank account
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>ニュージーランドの運転免許証番号
この機密情報の種類は、次の場合にのみ使用できます。
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
- 6 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_newzealand_driver_license_numberパターンに一致するコンテンツを検索します。
- 検索されたKeywords_newzealand_driver_license_number検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_newzealand_driver_license_numberパターンに一致するコンテンツを検索します。

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
- driver lic
- driver licence
- driver licences
- driverslic
- driverslicence
- driverslicences
- drivers lic
- drivers lics
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's licence
- driver's licences
- driverlic#
- driverlics#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver licence#
- driver licences#
- driverslic#
- driverslics#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's licence#
- driver's licences#
- international driving permit
- international driving permits
- nz 自動車の関連付け
- ニュージーランド自動車関連付け


## <a name="new-zealand-inland-revenue-number"></a>ニュージーランドの内陸部の収益番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

8 桁または 9 桁の数字とオプションの区切り文字

### <a name="pattern"></a>パターン

8 桁または 9 桁の数字とオプションの区切り文字

- 2 桁または 3 桁の数字
- オプションのスペースまたはハイフン
- 3 桁の数字
- オプションのスペースまたはハイフン
- 3 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_new_zealand_inland_revenue_numberパターンに一致するコンテンツを検索します。
- 検索されたKeywords_new_zealand_inland_revenue_number検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_new_zealand_inland_revenue_numberパターンに一致するコンテンツを検索します。

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

- ird no.
- ird no#
- nz ird
- ニュージーランド ird
- ird number
- 内陸部の収益数


## <a name="new-zealand-ministry-of-health-number"></a>ニュージーランド保健省

### <a name="format"></a>フォーマット

3 桁の文字、スペース (オプション)、および 4 桁の数字

### <a name="pattern"></a>パターン

- 3 文字 (大文字小文字を区別しない) ('I' と 'O' を除く)
- スペース (省略可能) 
- 4 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_new_zealand_ministry_of_health_number がパターンに一致するコンテンツを検出した。
- Keyword_nz_terms のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- 正常性
- 処理
- National Health Index Number
- nhi number
- nhi no.
- NHI#
- National Health Index No.
- National Health Index Id
- 国民健康インデックス#

## <a name="new-zealand-social-wlefare-number"></a>ニュージーランドのソーシャル wlefare 番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

9 桁の数字

### <a name="pattern"></a>パターン

9 桁の数字

- 3 桁の数字
- オプションのハイフン
- 3 桁の数字
- オプションのハイフン
- 3 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_newzealand_social_welfare_numberパターンに一致するコンテンツを検索します。
- 検索されたKeywords_newzealand_social_welfare_number検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_newzealand_social_welfare_numberパターンに一致するコンテンツを検索します。

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

- social social sociale#
- social social sociale#
- social sociale No.
- social social sociale number
- swn#

   
## <a name="norway-identification-number"></a>ノルウェーの識別番号

### <a name="format"></a>フォーマット

11 桁の数字

### <a name="pattern"></a>パターン

11 桁の数字:
- DDMMYY という形式で、生年月日を表す 6 桁の数字 
- 3 桁の個人番号 
- 2 桁のチェック ディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_norway_id_numberパターンに一致するコンテンツを検索します。
- 検索されたKeyword_norway_id_number検索されます。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_norway_id_numbeパターンに一致するコンテンツを検索します。
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
- Id
- Personnummer
- Fselsnummer

   
## <a name="philippines-unified-multi-purpose-identification-number"></a>フィリピンの統一された多目的識別番号

### <a name="format"></a>フォーマット

ハイフンで区切られた 12 桁の数字

### <a name="pattern"></a>パターン

12 桁の数字:
- 4 桁の数字 
- ハイフン 
- 7 桁の数字 
- ハイフン 
- 1 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Regex_philippines_unified_idコンテンツを検索する正規表現。
- 検索されたKeyword_philippines_id検索されます。

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

2 つのスラッシュを含む 14 桁の数字
  
### <a name="pattern"></a>パターン

14 桁の数字と 2 つのスラッシュ:
  
- 5 桁の数字 
- スラッシュ
- 2 桁の数字
- スラッシュ
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_poland_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_poland_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver's_license_number

- prawo jazdy
- prawa jazdy

## <a name="poland-identity-card"></a>ポーランドの ID カード

### <a name="format"></a>フォーマット

3 桁の文字と 6 桁の数字

### <a name="pattern"></a>パターン

3 桁の文字 (大文字小文字を区別しない) の後に 6 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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

- YYMMDD の形式で生年月日を表す 6 桁の数字
- 4 桁の数字
- 1 桁のチェック ディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_pesel_identification_number がパターンに一致するコンテンツを検出した。
- Keyword_pesel_identification_number のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- niepowtartartarny numer
- niepowtartarnynumer
- nr.-pesel
- nr-pesel
- numer identyfikacyjny
- pesel
- to数

   
## <a name="poland-passport-number"></a>ポーランドのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類に含まれており、スタンドアロンの機密情報の種類のエンティティとして使用できます。

### <a name="format"></a>フォーマット

2 桁の文字と 7 桁の数字

### <a name="pattern"></a>パターン

2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_polish_passport_number がパターンに一致するコンテンツを検出した。
- Keyword_polish_national_id_passport_number のキーワードを検出した。
- チェックサムが渡される。

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Numer paszportu
- Nr. Paszportu
- Paszport

## <a name="poland-regon-number"></a>ポーランドの REGON 番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

9 桁または 14 桁の数字

### <a name="pattern"></a>パターン

9 桁または 14 桁の数字:

- 9 桁の数字または 
- 9 桁の数字
- hyphen
- 5 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_polish_regon_numberパターンに一致するコンテンツを検索します。
- 検索されたKeywords_polish_regon_number検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_polish_regon_numberパターンに一致するコンテンツを検索します。

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
- 統計数値
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


## <a name="poland-tax-identification-number"></a>ポーランドの税識別番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

11 桁の数字 (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

11 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_poland_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_poland_eu_tax_file_number` 検出した。 
    
  
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
- numeridentyfikacjipodatkowej#
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- vat id#
- vat id
- vat no
- vat number
- vatid#
- vatid
- vatno#
   

## <a name="portugal-citizen-card-number"></a>ポルトガルの市民カード番号

### <a name="format"></a>フォーマット

8 桁の数字

### <a name="pattern"></a>パターン

8 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Regex_portugal_citizen_cardコンテンツを検索する正規表現。
- 検索されたKeyword_portugal_citizen_card検索されます。

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
- citizen card
- ドキュメント番号
- documento de identificação
- id number
- id no
- identification number
- ID カードなし
- ID カード番号
- national id card
- nic
- número bi de portugal
- número de identificação
- número de identificação fiscal
- número do documento
- portugal bi number


## <a name="portugal-drivers-license-number"></a>ポルトガルの運転免許証番号

### <a name="format"></a>フォーマット

2 つのパターン - 2 文字の後に特殊文字を含む 5 ~ 8 桁の数字
  
### <a name="pattern"></a>パターン

パターン 1: 2 文字、その後に特殊文字を含む 5/6。
- 2 文字 (大文字と小文字を区別しない)
- ハイフン 1 つ 
- 5 桁または 6 桁の数字
- スペース
- 1 桁の数字

パターン 2: 1 文字の後に特殊文字を含む 6/8 桁の数字:
- 1 文字 (大文字と小文字を区別しない)
- ハイフン 1 つ 
- 6 桁または 8 桁の数字
- スペース
- 1 桁の数字

    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_portugal_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_portugal_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver's_license_number

- carteira de motorista
- carteira motorista
- carteira de habilitação
- carteira habilitação
- número de licença
- número licença
- permissão de condução
- permissão condução
- リセンチャ語 (ポルトガル)
- carta de condução

## <a name="portugal-passport-number"></a>ポルトガルのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

1 文字の後に 6 桁の数字 (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

1 文字の後に 6 桁の数字:
  
- 1 文字 (大文字小文字を区別しない)
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_portugal_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_portugal_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
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

## <a name="portugal-tax-identification-number"></a>ポルトガルの税識別番号

### <a name="format"></a>フォーマット

9 桁の数字と省略可能なスペース
  
### <a name="pattern"></a>パターン

- 3 桁の数字
- 省略可能なスペース
- 3 桁の数字
- 省略可能なスペース
- 3 桁の数字
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_portugal_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_portugal_eu_tax_file_number` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_portugal_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
    
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
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="romania-drivers-license-number"></a>ルーマニアの運転免許証番号

### <a name="format"></a>フォーマット

1 文字の後に 8 桁の数字
  
### <a name="pattern"></a>パターン

1 文字の後に 8 桁の数字:
- 1 文字 (大文字と小文字を区別しない) または数字 
- 8 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_romania_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_romania_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver's_license_number

- permis de
- permismisi de
- permismisihere
- permisele de
- permisele
- permis

## <a name="romania-personal-numeric-code-cnp"></a>ルーマニアの個人数値コード (CNP)
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースと区切り記号のない 13 桁の数字
  
### <a name="pattern"></a>パターン

- 1 ~ 9 の 1 桁の数字
- 生年月日を表す 6 桁の数字 (YYMMDD)
- 01 ~ 52 または 99 の 2 桁の数字
- 4 桁の数字

### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_romania_eu_national_id_card` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_romania_eu_national_id_card` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_romania_eu_national_id_card` 、パターンに一致するコンテンツを検索します。 
    
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
- cod numeric personal
- cod unic identificare
- codnumericpersonal#
- codul fiscal nr.
- identificarea fiscală nr#
- id-ul taxei
- insurance number
- insurancenumber#
- national id#
- national id
- national identification number
- număr identificare personal
- număr identitate
- număr personal unic
- număridentitate#
- număridentitate
- numărpersonănic#
- numărpersonănic
- număru de identificare fiscală
- numărul de identificare fiscală
- 個人の数値コード
- pin#
- pin
- tax file no
- tax file number
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- 一意の ID 番号
- 一意の ID 番号
- uniqueidentityno#
- uniqueidentityno

## <a name="romania-passport-number"></a>ルーマニアのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

スペースと区切り記号のない 8 桁または 9 桁の数字
  
### <a name="pattern"></a>パターン

8 桁または 9 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_romania_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_romania_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numărul paărul paăaportăi nuăl pasaportăi numerele paăaportăi Paăaport nr

## <a name="russia-passport-number-domestic"></a>ロシアのパスポート番号 (国内)
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

10 桁の数字

### <a name="pattern"></a>パターン

10 桁の数字:

- 2 桁の数字
- オプションのスペースまたはハイフン
- 2 桁の数字
- 省略可能なスペース
- 6 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現はRegex_Russian_Passport_Number_Domesticパターンに一致するコンテンツを検索します。
- 検索されたKeyword_Russian_Passport_Number検索されます。

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
- passport no
- passport#
- passport id
- passportno#
- passportnumber#
- паспорт нет
- паспорт ID
- p最も近いпаспорт
- pррр паспорта
- паспорт#
- паспортid#
- номер паспорта
- номерпаспорта#


## <a name="russia-passport-number-international"></a>ロシアのパスポート番号国際番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

9 桁の数字

### <a name="pattern"></a>パターン

9 桁の数字:

- 2 桁の数字
- オプションのスペースまたはハイフン
- 7 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現はRegex_Russian_Passport_Number_Internationalパターンに一致するコンテンツを検索します。
- 検索されたKeyword_Russian_Passport_Number検索されます。

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
- passport no
- passport#
- passport id
- passportno#
- passportnumber#
- паспорт нет
- паспорт ID
- p最も近いпаспорт
- pррр паспорта
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

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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

9 桁の文字と数字

### <a name="pattern"></a>パターン

- 9 桁の文字と数字:
- 文字 "F"、"G"、"S"、または "T" (大文字小文字を区別しない) 
- 7 桁の数字 
- アルファベットのチェック ディジット

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Regex_singapore_nricコンテンツを検索する正規表現。
- 検索されたKeyword_singapore_nric検索されます。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Regex_singapore_nricコンテンツを検索する正規表現。
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

1 文字の後に 7 桁の数字
  
### <a name="pattern"></a>パターン

1 文字の後に 7 桁の数字
  
- 1 文字 (大文字と小文字を区別しない) または数字
- 7 桁の数字 
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_slovakia_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_slovakia_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver's_license_number

- vodičsksksk preskz
- vodičské preskzy
- vodičského preu、
- vodičsksksk prezov

## <a name="slovakia-personal-number"></a>スロバキアの個人番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

オプションの円記号を含む 9 桁または 10 桁の数字
  
### <a name="pattern"></a>パターン

- 生年月日を表す 6 桁の数字
- オプションのスラッシュ (/)
- 3 桁の数字
- オプションのチェック ディジット 1 つ
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_slovakia_eu_national_id_card` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_slovakia_eu_national_id_card` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_slovakia_eu_national_id_card` 、パターンに一致するコンテンツを検索します。 
    
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
- 生年月日
- číslo nのodnej identifikačnej karty
- číslo občianského preu、
- daéové číslo
- id number
- id no
- identification number
- identifikačná karta č
- identifikačné číslo
- ID カードなし
- ID カード番号
- nのodná identifikačná značka č
- national number
- nationalnumber#
- nemzeti személyazonosító zonzolvzony
- personalidnumber#
- rč
- rodne cislo
- rodné číslo
- social security number
- ssn#
- ssn
- személyi zolvlvy szám
- személyi zolvlvy száma
- személyzolvlvy szám
- tax file no
- tax file number
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#

## <a name="slovakia-passport-number"></a>スロバキアのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

1 桁の数字または文字の後に 7 桁の数字(スペースまたは区切り文字なし)
  
### <a name="pattern"></a>パターン

1 桁または文字 (大文字小文字を区別しない) の後に 7 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_slovakia_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_slovakia_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- číslo pasu
- čísla pasov
- pas č.
- Passeport n°
- n° Passeport

## <a name="slovenia-drivers-license-number"></a>スロベニアの運転免許証番号

### <a name="format"></a>フォーマット

スペースと区切り記号のない 9 桁の数字
  
### <a name="pattern"></a>パターン

9 桁の数字
  
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_slovenia_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_slovenia_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver's_license_number

- voznizko dovoljenje
- voznizka tevilka licence
- voznizkih dovoljejeje
- tevilka voznizkega dovoljenja
- tevilke voznijekih dovolje数

## <a name="slovenia-unique-master-citizen-number"></a>スロベニア固有のマスター市民番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

13 桁の数字 (スペースまたは区切り文字なし)
  
### <a name="pattern"></a>パターン

指定したパターンの 13 桁の数字:
  
- 生年月日 (DDMMLLL) に対応する 7 桁の数字。"LLL" は生年月日の最後の 3 桁の数字に対応します。 
- 生年月日の領域 "50" に対応する 2 桁の数字
- 同じ日に生まれた人の性別とシリアル番号の組み合わせに対応する 3 桁の数字 (男性の場合は 000 ~ 499、女性の場合は 500 ~ 999)
- 1 桁のチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_slovenia_eu_national_id_card` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_slovenia_eu_national_id_card` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_slovenia_eu_national_id_card` 、パターンに一致するコンテンツを検索します。 
    
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

- edinstvena tevilkalavnega dr avljana
- em最も近い
- enotna maticna のtevilka obcana
- id card
- identification number
- identifikacijka tevilka
- Identity card
- nacionalna id
- nacionalni potni リスト
- national id
- osebna iczaznica
- osebni koda
- osebni ne
- osebni tevilka
- 個人用コード
- 個人番号
- 個人の数値コード
- tevilka dr avljana
- 一意の市民番号
- 一意の ID 番号
- 一意の ID 番号
- 一意のマスターの市民番号
- 一意の登録番号
- uniqueidentityno#
- uniqueidentityno#

## <a name="slovenia-passport-number"></a>スロベニアのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

2 桁の文字の後に 7 桁の数字 (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

2 桁の文字の後に 7 桁の数字:
  
- 文字 "P"
- 1 文字の大文字
- 7 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_slovenia_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_slovenia_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- tevilka potnega lista
- potek potjavnosti
- potni list#
- datum rojstva
- potni list
- tevilke potnih listov

## <a name="slovenia-tax-identification-number"></a>スロベニアの税金の識別番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

スペースまたは区切り記号を含めない 8 桁の数字
  
### <a name="pattern"></a>パターン

- 1 ~ 9 の 1 桁の数字
- 6 桁の数字
- 1 桁のチェック ディジット
  
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_slovenia_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_slovenia_eu_tax_file_number` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_slovenia_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
    
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

- davčna čtevilka
- identifikacijka のtevilka davka
- čtevilka davčne datoteke
- tax file no
- tax file number
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="south-africa-identification-number"></a>南アフリカの識別番号

### <a name="format"></a>フォーマット

省略可能なスペースを含む 13 桁の数字

### <a name="pattern"></a>パターン

13 桁の数字:
- YYMMDD 形式で生年月日を表す 6 桁の数字 
- 4 桁の数字 
- 1 桁の市民権インジケーター 
- 数字 "8" または "9" 
- チェックサム ディジットである 1 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_south_africa_identification_numberパターンに一致するコンテンツを検索します。
- 検索されたKeyword_south_africa_identification_number検出された。
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
- Id 
   
## <a name="south-korea-resident-registration-number"></a>韓国の住民登録番号

### <a name="format"></a>フォーマット

ハイフンを 1 つ含む 13 桁の数字

### <a name="pattern"></a>パターン

13 桁の数字:
- YYMMDD 形式で生年月日を表す 6 桁の数字 
- ハイフン 
- 1 桁の数字は、年齢と性別によって決まります。 
- 4 桁の出生地域コード 
- 前の数字が同一の人を区別するために使用される 1 桁の数字 
- チェック ディジット。

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_south_korea_resident_numberパターンに一致するコンテンツを検索します。
- 検索されたKeyword_south_korea_resident_number検索されます。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_south_korea_resident_numberパターンに一致するコンテンツを検索します。
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

8 桁の数字の後に 1 文字
  
- 8 桁の数字 
- 1 桁または 1 文字 (大文字と小文字を区別しない)
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに  `Func_spain_eu_DL_and_NI_number_citizen` 一 `Func_spain_eu_DL_and_NI_number_foreigner` 致するコンテンツを関数または検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_spain_eu_driver's_license_number` された、または検出された。 

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver's_license_number

- permiso deisoción
- permisoisoción
- lice、
- lice、
- permiso
- permiso deir
- permisos de
- permisos
- carnet のサービル
- carnet de
- lice、de man、
- lice、man、

## <a name="spain-dni"></a>スペイン DNI
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

8 桁の数字の後に 1 文字
  
### <a name="pattern"></a>パターン

7 桁の数字の後に 1 文字
  
- 8 桁の数字
- 省略可能なスペースまたはハイフン
- 1 つのチェック 文字 (大文字と小文字を区別しない)
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに  `Func_spain_eu_DL_and_NI_number_citizen` 一 `Func_spain_eu_DL_and_NI_number_foreigner` 致するコンテンツを関数または検索します。 
- キーワードを  `Keywords_spain_eu_national_id_card"` 検出した。 

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- identidad ico
- identidadicoico#
- insurance number
- national identification number
- national identity
- nationalid#
- nationalidno#
- nie#
- nie
- nienúmero#
- número de identificación
- número nacional identidad
- 個人識別番号
- 個人用 ID なし
- 一意の ID 番号
- uniqueid#

## <a name="spain-passport-number"></a>スペインのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

8 文字または 9 文字の文字と数字の組み合わせ (スペースまたは区切り記号なし)
  
### <a name="pattern"></a>パターン

文字と数字の 8 文字または 9 文字の組み合わせ:
  
- 2 桁の数字または文字 
- 1 桁または 1 文字 (省略可能)
- 6 桁の数字
    
### <a name="checksum"></a>チェックサム

該当なし
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_spain_eu_passport_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_passport_number_common` `Keywords_spain_eu_passport_number` された、または検出された。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- パスポート番号

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- libreta pasaporte
- número pasaporte
- espa pasaporte
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte no
- Passeport n°
- n° Passeport
- pasaporte no.
- pasaporte n°
- スペインの passport


## <a name="spain-social-security-number-ssn"></a>スペインの社会保障番号 (SSN)
この機密情報の種類のエンティティは、EU 社会保障番号または同等の ID の機密情報の種類に含まれており、スタンドアロンの機密情報の種類のエンティティとして使用できます。

### <a name="format"></a>フォーマット

11 ～ 12 桁の数字

### <a name="pattern"></a>パターン

11 ~ 12 桁の数字:
- 2 桁の数字 
- スラッシュ (省略可能) 
- 7 桁から 8 桁の数字 
- スラッシュ (省略可能) 
- 2 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_spanish_social_security_number がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

なし

## <a name="spain-tax-identification-number"></a>スペインの税識別番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

指定されたパターンの 7 桁または 8 桁の数字と 1 文字または 2 文字
  
### <a name="pattern"></a>パターン

スペインの国民識別カードを持つスペインの自然人:
  
- 8 桁の数字 
- 大文字 1 文字 (大文字と小文字を区別) 
    
スペインの国民識別カードのない非居住者の Spaniards
  
- 1 文字の大文字 "L" (大文字と小文字を区別)
- 7 桁の数字
- 大文字 1 文字 (大文字と小文字を区別) 
    
スペインの国民識別カードのない 14 歳未満の住民スペイン人:
  
- 1 文字の大文字 "K" (大文字と小文字を区別)
- 7 桁の数字 
- 大文字 1 文字 (大文字と小文字を区別)
    
部下の識別番号を持つ部下
  
- "X"、"Y"、または "Z" である 1 つの大文字 (大文字と小文字を区別) 
- 7 桁の数字
- 大文字 1 文字 (大文字と小文字を区別) 
    
子の識別番号を持たなくても
  
- "M" である 1 つの大文字 (大文字と小文字を区別) 
- 7 桁の数字
- 大文字 1 文字 (大文字と小文字を区別) 
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに  `Func_spain_eu_tax_file_number` 一 `Func_spain_eu_DL_and_NI_number_citizen` 致するコンテンツを関数または検索します。 
- キーワードを  `Keywords_spain_eu_tax_file_number` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- número de identificación fiscal
- número de impuesto corporativo
- spanishcifid#
- spanishcifid
- spanishcifno#
- spanishcifno
- tax file no
- tax file number
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="sql-server-connection-string"></a>SQL Server接続文字列

### <a name="format"></a>フォーマット

文字列 "User Id"、"User ID"、"uid"、または "UserId" の後に、以下のパターンでアウトラインで示されている文字と文字列が続きます。

### <a name="pattern"></a>パターン

- 文字列 "User Id"、"User ID"、"uid"、または "UserId"
- 1 ~ 200 文字の小文字または大文字、数字、記号、特殊文字、またはスペースの任意の組み合わせ
- 文字列 "Password" または "pwd" ("pwd" の前に小文字が付いない)
- 等号 (=)
- ドル記号 ($)、パーセント記号 (%)、記号 (> より大きい)、記号 (@)、引用符 (")、セミコロン (;)、左中かっこ([)、または左角かっこ ({) 以外の任意の文字
- セミコロン (;)、スラッシュ (/)、または引用符 (") ではない 7 ~ 128 文字の任意の組み合わせ
- セミコロン (;)または引用符 (")

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一CEP_Regex_SQLServerConnectionStringコンテンツを検索する正規表現。
- 指定されたCEP_GlobalFilter **が見** つかりません。
- パターンに一CEP_PasswordPlaceHolderコンテンツ **が** 見つからない正規表現。
- パターンに一CEP_CommonExampleKeywordsコンテンツ **が** 見つからない正規表現。

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

- some-password
- somepassword
- secretPassword
- サンプル

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

(技術的には、この機密情報の種類はキーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- パスワードまたは pwd の後に 0 ~ 2 スペース、等号 (=)、0 ~ 2 スペース、およびアスタリスク (*) --OR--
- パスワードまたは pwd の後に次の情報が続きます。
    - 等号 (=)
    - 記号より小さい (<)
    - 大文字または小文字、数字、アスタリスク (*)、ハイフン (-)、下線 (_)、または空白文字の 1 ~ 200 文字の任意の組み合わせ
    - 記号より大きい (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(技術的には、この機密情報の種類はキーワード リストではなく正規表現を使用してこれらのキーワードを識別します)。

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="sweden-drivers-license-number"></a>スウェーデンの運転免許証番号

### <a name="format"></a>フォーマット

ハイフンを含む 10 桁の数字
  
### <a name="pattern"></a>パターン

ハイフンを含む 10 桁の数字:
  
- 6 桁の数字 
- ハイフン
- 4 桁の数字
    
### <a name="checksum"></a>チェックサム

いいえ
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現は、  `Regex_sweden_eu_driver's_license_number` パターンに一致するコンテンツを検索します。 
- キーワードが検出  `Keywords_eu_driver's_license_number` `Keywords_sweden_eu_driver's_license_number` された、または検出された。 
    
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
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- ドライバー ライセンス#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- license
- licenses
- licencev
- licencev licences
- driver licen
- drivers licen
- driver's licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver's_license_number

- ajokortti
- permis de
- ajokortin numero
- kuljjat lic.
- drivere lic.
- körkort
- numărul permisăi de numere
-  שאָפער דערלויבעניש נומער
- fの lic.
-  דריווערס דערלויבעניש
- の

## <a name="sweden-national-id"></a>スウェーデンの国民 ID

### <a name="format"></a>フォーマット

10 桁または 12 桁の数字とオプションの区切り文字

### <a name="pattern"></a>パターン

10 桁または 12 桁の数字とオプションの区切り文字:
- 2 桁の数字 (省略可能) 
- YYMMDD という日付形式の 6 桁の数字 
- "-" または "+" の区切り記号 (省略可能)
- 4 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は `Func_swedish_national_identifier` 、パターンに一致するコンテンツを検索します。
- キーワード `Keywords_swedish_national_identifier` の検索
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は `Func_swedish_national_identifier` 、パターンに一致するコンテンツを検索します。
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
- id number
- id#
- id no
- identification number
- identifikationsnumret#
- identifikationsnumret
- identitetshandling
- ID ドキュメント
- ID no
- ID 番号
- id-nummer
- 個人用 ID
- personnummer#
- personnummer
- (2013 年 12 月 1 日)
   
## <a name="sweden-passport-number"></a>スウェーデンのパスポート番号
この機密情報の種類のエンティティは、EU パスポート番号の機密情報の種類に含まれており、スタンドアロンの機密情報の種類のエンティティとして使用できます。

### <a name="format"></a>フォーマット

8 桁の数字

### <a name="pattern"></a>パターン

8 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現を使用Regex_sweden_passport_numberパターンに一致するコンテンツを検索します。
- 次のいずれかの条件が満たされます。
    - 検索されたKeyword_passport検索されます。
    - 検索されたKeyword_sweden_passport。

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード
   
#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- visa requirements 
- Alien Registration Card 
- Schengen visas 
- Schengen visa 
- Visa Processing 
- Visa Type 
- Single Entry 
- Multiple Entry 
- G3 Processing Fees 

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
- 万の表示 
- パスポート# 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport # 
- Passeport# 
- PasseportNon 
- Passeportn ° 

## <a name="sweden-social-security-number-or-equivalent-identification"></a>スウェーデンの社会保障番号または同等の識別情報
この機密情報の種類のエンティティは、EU 社会保障番号または同等の ID の機密情報の種類でのみ使用できます。

### <a name="format"></a>フォーマット

スペースと区切り記号のない 12 桁の数字
  
### <a name="pattern"></a>パターン

12 桁の数字:
  
- 生年月日に対応する 8 桁の数字 (YYYYMMDD) 
- シリアル番号に対応する次の 3 桁の数字 
  - シリアル番号の最後の数字は、男性の奇数と女性の偶数の割り当てによって性別を示します。
  - 1990 年までのシリアル番号の割り当ては、番号のベアラーが生まれた郡に対応し、1947 年 1 月 1 日に税記録に従い、特別なコード (通常は 7 桁目は 9 番目の数字) を持つ番号が住んでいる (1947 年以前に生まれた場合) 
- 1 桁のチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_sweden_eu_ssn_or_equivalent` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_sweden_eu_ssn_or_equivalent` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_sweden_eu_ssn_or_equivalent` 、パターンに一致するコンテンツを検索します。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

- 個人用 ID 番号
- identification number
- 個人用 ID いいえ
- ID no
- id no
- 個人識別なし
- personnummer id
- personligt id-nummer
- unikt id-nummer
- personnummer
- identifikationsnumret
- personnummer#
- identifikationsnumret#

## <a name="sweden-tax-identification-number"></a>スウェーデンの税金の識別番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

指定されたパターンの 10 桁の数字と記号
  
### <a name="pattern"></a>パターン

10 桁の数字と記号:
  
- 生年月日 (YYMMDD) に対応する 6 桁の数字 
- プラス記号または負符号
- ID 番号を一意にする 3 桁の数字。 
  - 1990 年以前に発行された数値の場合、7 番目と 8 番目の数字は出生または外生の人々の郡を示します。
  - 9 番目の位置の数字は、性別が男性の場合は奇数、女性の場合は偶数で示されます。
- 1 桁のチェック ディジット
    
### <a name="checksum"></a>チェックサム

はい
  
### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_sweden_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_sweden_eu_tax_file_number` 検出した。 
    
DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_sweden_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
    
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
- nummer
- identifikation
- alatebetalarens identifikationsnummer
- sverige tin
- tax file
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax number
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="swift-code"></a>SWIFT コード

### <a name="format"></a>フォーマット

4 文字の後に 5 ~ 31 桁の文字または数字

### <a name="pattern"></a>パターン

4 文字の後に 5 ~ 31 桁の文字または数字:
- 4 文字の銀行コード (大文字と小文字を区別しない) 
- 省略可能なスペース 
- 4 ～ 28 個の文字または数字 (基本的銀行口座番号 (BBAN)) 
- 省略可能なスペース 
- 1 ~ 3 桁の文字または数字 (BBAN の残りの部分)

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- SWIFT
- BIC の数
- BIC コード
- SWIFT コード
- SWIFT
- BIC の数
- BIC コード
- 金融機関識別コード
- 金融機関コード
- 銀行コード

## <a name="switzerland-ssn-ahv-number"></a>スイスの SSN AHV 番号
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

13 桁の数字

### <a name="pattern"></a>パターン

13 桁の数字:

- 3 桁の数字 - 756
- オプションのドット
- 4 桁の数字
- オプションのドット
- 4 桁の数字
- オプションのドット
- 2 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_swiss_social_security_number_ahvパターンに一致するコンテンツを検索します。
- 検索されたKeywords_swiss_social_security_number_ahv検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_swiss_social_security_number_ahvパターンに一致するコンテンツを検索します。

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
- insurance number
- personalidno#
- social security number
- 個人用 ID 番号
- 個人識別なし
- insuranceno#
- uniqueidno#
- 一意の識別なし。
- avs 番号
- 個人用 ID なし versicherungsnummer
- identifikationsnummer
- einzigartige identitzit nicht
- sozialversicherungsnummer
- identification personnelle id
- numéro de sécurité sociale

   
## <a name="taiwan-national-identification-number"></a>台湾の国民識別番号

### <a name="format"></a>フォーマット

1 文字 (英語) の後に 9 桁の数字

### <a name="pattern"></a>パターン

1 文字 (英語) の後に 9 桁の数字:
- 1 文字 (英語、大文字小文字を区別しない) 
- 数字 "1" または "2" 
- 8 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_taiwanese_national_id がパターンに一致するコンテンツを検出した。
- Keyword_taiwanese_national_id のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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

- 生体認証パスポート番号: 9 桁の数字
- 生体認証以外のパスポート番号: 9 桁の数字

### <a name="pattern"></a>パターン
生体認証のパスポート番号:
- 文字 "3" 
- 8 桁の数字

生体認証以外のパスポート番号:
- 9 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Regex_taiwan_passportコンテンツを検索する正規表現。
- 検索されたKeyword_taiwan_passport検出された。

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
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>台湾の住民証明書 (ARC/TARC) 番号

### <a name="format"></a>フォーマット

10 桁の文字と数字

### <a name="pattern"></a>パターン

10 桁の文字と数字:
- 2 文字 (大文字小文字を区別しない) 
- 8 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Regex_taiwan_resident_certificateコンテンツを検索する正規表現。
- 検索されたKeyword_taiwan_resident_certificate検索されます。

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

## <a name="thai-population-identification-code"></a>タイ語の母集団識別コード

### <a name="format"></a>フォーマット

13 桁の数字

### <a name="pattern"></a>パターン

13 桁の数字:
- 1 桁目が 0 または 9 ではない 
- 12 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_Thai_Citizen_Idパターンに一致するコンテンツを検索します。
- 検索されたKeyword_Thai_Citizen_Idが見つかりました。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_Thai_Citizen_Idパターンに一致するコンテンツを検索します。

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
- Id 番号
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

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_Turkish_National_Idパターンに一致するコンテンツを検索します。
- 検索されたKeyword_Turkish_National_Id検出された。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_Turkish_National_Idパターンに一致するコンテンツを検索します。

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

- TC Kim tc No
- TC Kimaras numaras Tc
- Vatandavatl の numaras の数
- Vatandavatl のいいえ

## <a name="uk-drivers-license-number"></a>英国 driver's license number
この機密情報の種類のエンティティは、EU の運転免許証番号の機密情報の種類に含まれており、スタンドアロンの機密情報の種類のエンティティとして使用できます。

### <a name="format"></a>フォーマット

指定の形式で組み合わせた 18 桁の文字と数字

### <a name="pattern"></a>パターン

18 個の文字と数字:
- 5 文字 (大文字小文字を区別しない) または文字の代用の数字 "9" 
- 1 桁の数字 
- 生年月日の日付形式 MMDDY の 5 桁の数字 (ドライバーが女性の場合、7 番目の文字は 50 ずつ増加します。つまり、01 ~ 12 ではなく 51 ~ 62)。
- 2 文字 (大文字小文字を区別しない) または文字の代用の数字 "9" 
- 5 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_uk_drivers_license がパターンに一致するコンテンツを検出した。
- Keyword_uk_drivers_license のキーワードを検出した。
- チェックサムが渡される。

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_uk_drivers_license"></a>Keyword_uk_drivers_license

- DVLA 
- light vans 
- quadbikes 
- motor cars 
- 125cc 
- sidecar 
- tricycles 
- (1) 
- photocard licence 
- learner drivers 
- licence holder 
- licence holders 
- driving licences 
- driving licence 
- dual control car 
   
## <a name="uk-electoral-roll-number"></a>英国 electoral roll number

### <a name="format"></a>フォーマット

2 桁の文字の後に 1 ~ 4 桁の数字

### <a name="pattern"></a>パターン

2 文字 (大文字小文字を区別しない) の後に 1 ~ 4 つの数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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

   
## <a name="uk-national-health-service-number"></a>英国 national health service number

### <a name="format"></a>フォーマット

スペースで区切られた 10 ～ 17 桁の数字

### <a name="pattern"></a>パターン

10 ～ 17 桁の数字:
- 3 桁または 10 桁の数字 
- スペース 
- 3 桁の数字 
- スペース 
- 4 桁の数字

### <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
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
この機密情報の種類のエンティティは、EU の国民識別番号の機密情報の種類に含まれており、スタンドアロンの機密情報の種類のエンティティとして使用できます。

### <a name="format"></a>フォーマット

スペースまたはダッシュで区切られた 7 文字または 9 文字

### <a name="pattern"></a>パターン

次の 2 つのパターンを使用できます。

- 2 文字 (有効な IOS は、このプレフィックスで特定の文字のみを使用します。このパターンでは検証されます。大文字と小文字は区別されません)。
- 6 桁の数字
- 'A'、'B'、'C'、または 'D' (プレフィックスと同様に、サフィックスでは特定の文字のみ許可され、大文字と小文字は区別されません)

OR

- 2 文字
- スペースまたはダッシュ
- 2 桁の数字
- スペースまたはダッシュ
- 2 桁の数字
- スペースまたはダッシュ
- 2 桁の数字
- スペースまたはダッシュ
- 'A'、'B'、'C'、または 'D' のいずれか

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_uk_nino がパターンに一致するコンテンツを検出した。
- Keyword_uk_nino のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- insurance
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
- insurance#
- insurancenumber
- nationalinsurance#
- nationalinsurancenumber

    
## <a name="uk-unique-taxpayer-reference-number"></a>英国 一意の納税者参照番号
この機密情報の種類は、次の場合にのみ使用できます。
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

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数は  `Func_uk_eu_tax_file_number` 、パターンに一致するコンテンツを検索します。 
- キーワードを  `Keywords_uk_eu_tax_file_number` 検出した。 
    
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

- tax number
- tax file
- tax id
- tax identification no
- 税識別番号
- tax no#
- tax no
- tax registration number
- はい#
- (2013 年 1 月#
- (2013 年 3 月)#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#

## <a name="us-bank-account-number"></a>米国の銀行口座番号

### <a name="format"></a>フォーマット

6 ~ 17 桁の数字

### <a name="pattern"></a>パターン

6 ~ 17 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- パターンに一Regex_usa_bank_account_numberコンテンツを検索する正規表現。
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

州 (ニューヨークなど) によって異なります。
- ddd のように書式設定された 9 桁の数字が一致します。
- ddddd のような 9 桁の数字は一致しません。

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。
- Keyword_[state_name]_drivers_license_name のキーワードを検出した。
- 検索されたKeyword_us_drivers_license検索されます。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
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
- Driver'Licenses 
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
- Driver'Licenses# 
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

- 州の省略形 (例: "NY") 
- 状態名 (例: "New York")

## <a name="us-individual-taxpayer-identification-number-itin"></a>米国の個人納税者識別番号 (ITIN)

### <a name="format"></a>フォーマット

"9" で始まる 9 桁の数字。4 桁目には "7" または "8" が含まれます。必要に応じて、スペースまたはダッシュで書式設定されます。

### <a name="pattern"></a>パターン

書式設定:
- 数字 "9" 
- 2 桁の数字 
- スペースまたはダッシュ 
- "7" または "8" 
- 1 桁の数字 
- スペースまたはダッシュ 
- 4 桁の数字

unformatted:
- 数字 "9" 
- 2 桁の数字 
- "7" または "8" 
- 5 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_formatted_itin がパターンに一致するコンテンツを検出した。
- Keyword_itin のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_unformatted_itin がパターンに一致するコンテンツを検出した。
- Keyword_itin のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_formatted_itinまたはFunc_unformatted_itinパターンに一致するコンテンツを検索します。

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

- taxpayer 
- tax id 
- tax identification 
- itin 
- i.t.i.n.
- ssn 
- tin 
- social security 
- tax payer 
- itins 
- はい 
- individual taxpayer 


## <a name="us-social-security-number-ssn"></a>米国の社会保障番号 (SSN)

### <a name="format"></a>フォーマット

9 桁の数字(書式設定されたパターンまたは書式設定されていないパターンの場合があります)

> [!NOTE]
> 2011 年半ばより前に発行された場合、SSN には強力な書式が設定されています。この書式では、数値の特定の部分が有効な範囲内に含む必要があります (チェックサムはありません)。

### <a name="pattern"></a>パターン

4 つの関数は、4 つの異なるパターンで SSN を探します。
- Func_ssn は、2011 年以前の厳密な書式の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。
- Func_unformatted_ssn は、2011 年以前の厳密な書式の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。
- Func_randomized_formatted_ssn は、2011 年以降の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。
- Func_randomized_unformatted_ssn は、2011 年以降の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。

### <a name="checksum"></a>チェックサム

いいえ


### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_ssn がパターンに一致するコンテンツを検出した。
- Keyword_ssn のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- この関数はFunc_unformatted_ssnパターンに一致するコンテンツを検索します。
- Keyword_ssn のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_randomized_formatted_ssn がパターンに一致するコンテンツを検出した。
- Keyword_ssn のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に 55% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_randomized_unformatted_ssn がパターンに一致するコンテンツを検出した。
- Keyword_ssn のキーワードを検出した。


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
英国 passport number sensitive information type entity is available in the EU Passport Number sensitive information type and is available as a stand alone sensitive information type entity.

### <a name="format"></a>フォーマット

9 桁の数字

### <a name="pattern"></a>パターン

9 桁の連続する数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 関数 Func_usa_uk_passport がパターンに一致するコンテンツを検出した。
- Keyword_passport のキーワードを検出した。

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

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
- 万の表示 
- パスポート# 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport # 
- Passeport# 
- PasseportNon 
- Passeportn ° 

## <a name="ukraine-passport-domestic"></a>ウクライナのパスポート(国内)
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

9 桁の数字

### <a name="pattern"></a>パターン

9 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現はRegex_Ukraine_Passport_Domesticパターンに一致するコンテンツを検索します。
- 検索されたKeyword_Ukraine_Passport_Domestic検索されます。

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

- passport
- passport number
- passport no
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>ウクライナのパスポート国際
この機密情報の種類は、次の場合にのみ使用できます。
- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- 情報ガバナンス
- レコード管理
- Microsoft クラウド アプリのセキュリティ

### <a name="format"></a>フォーマット

8 文字の英数字パターン

### <a name="pattern"></a>パターン

8 文字の英数字パターン:
- 2 桁の文字または数字
- 6 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。
- 正規表現はRegex_Ukraine_Passport_Internationalパターンに一致するコンテンツを検索します。
- 検索されたKeyword_Ukraine_Passport_International検索されます。

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

- passport
- passport number
- passport no
- паспорт України
- номер паспорта
