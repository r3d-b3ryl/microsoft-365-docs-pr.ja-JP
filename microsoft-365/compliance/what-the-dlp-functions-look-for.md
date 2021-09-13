---
title: データ損失防止 (DLP) 関数が探す機能
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
recommendations: false
description: データ損失防止 (DLP) 関数が何を探すのかについて説明します。
ms.openlocfilehash: 787abc1e7fb4c95392a76f7514ceffd3f7f4dda0
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216123"
---
# <a name="what-the-dlp-functions-look-for"></a>DLP 関数の検索対象

データ損失防止 (DLP) ポリシーでは、機密情報の種類を使用して機密情報を識別できます。 クレジット カード番号と EU デビットカード番号は、機密情報の種類の例です。 機密情報の種類は、特定のパターンを探します。 機密情報の種類は、データの形式、チェックサムを確認してデータを検証し、関連するキーワードや他の情報を探します。 この機能の一部は、内部関数によって実行されます。 たとえば、クレジット カード番号の機密情報の種類は、関数を使用して、有効期限のように書式設定された日付を検索します。 これは、番号がクレジット カード番号であるのを裏付けるのに役立ちます。

この記事では、定義済みの機密情報の種類がどのように機能するのかを理解するために、これらの関数が何を探すのかを説明します。 詳細については、「機密情報の [種類エンティティ定義」を参照してください。](sensitive-information-type-entity-definitions.md)

## <a name="table-of-functions"></a>関数の表

<br>

****

|関数名|function action|はバリデーターです|
|---|---|:---:|
|Func_Argentina_Unique_Tax_Key|アルゼンチン固有の税キーを検出して検証する|いいえ|
|Func_aba_routing|ABA ルーティング番号を検出する|はい|
|Func_alabama_drivers_license_number|アラバマ州の運転免許証番号を検出する|いいえ|
|Func_alaska_delaware_oregon_drivers_license_number|アラスカ州、デラウェア州、オレゴン州の運転免許証番号を検出する|いいえ|
|Func_alaska_drivers_license_number|アラスカ州の運転免許証番号を検出する|いいえ|
|Func_alberta_drivers_license_number|アルバータ州の運転免許証番号を検出する|いいえ|
|Func_Argentina_Unique_Tax_Key|アルゼンチンの一意の税キーを検出する|いいえ|
|Func_arizona_drivers_license_number|アリゾナ州の運転免許証番号を検出する|いいえ|
|Func_arkansas_drivers_license_number|アーカンソー州の運転免許証番号を検出する|いいえ|
|Func_australian_business_number|オーストラリアのビジネス番号を検出する|いいえ|
|Func_Australian_Company_Number|オーストラリアの会社番号を検出する|いいえ|
|Func_australian_medical_account_number|オーストラリアの医療アカウント番号を検出する|いいえ|
|Func_australian_tax_file_number|オーストラリアの税ファイル番号を検出する|はい|
|Func_austria_eu_ssn_or_equivalent|オーストリアの社会保障番号を検出する|いいえ|
|Func_austria_eu_tax_file_number|オーストリアの税ファイル番号を検出する|いいえ|
|Func_Austria_Value_Added_Tax|オーストリアの付加価値税を検出する|いいえ|
|Func_belgium_national_number|ベルギーの国番号を検出する|いいえ|
|Func_belgium_value_added_tax_number|ベルギーの付加価値税番号を検出する|いいえ|
|Func_brazil_cnpj|ブラジルの法人番号 (CNPJ) を検出します。|はい|
|Func_brazil_cpf|ブラジル CPF を検出する|はい|
|Func_brazil_rg|ブラジル RG を検出する|いいえ|
|Func_british_columbia_drivers_license_number|ブリティッシュ コロンビア州の運転免許証番号を検出する|いいえ|
|Func_bulgaria_eu_national_id_card|ブルガリアの一様な民事番号を検出する|いいえ|
|Func_california_drivers_license_number|カリフォルニア州の運転免許証番号を検出する|いいえ|
|Func_canadian_sin|カナダの罪を検出する|はい|
|Func_chile_id_card|チリ ID カードを検出する|いいえ|
|Func_china_resident_id|中国居住者 ID を検出する|いいえ|
|Func_colorado_drivers_license_number|コロラド州の運転免許証番号を検出する|いいえ|
|Func_connecticut_drivers_license_number|Connecticut のドライバーのライセンス番号を検出する|いいえ|
|Func_credit_card|クレジット カードを検出する|はい|
|Func_croatia_id_card|クロアチア ID カードを検出する|いいえ|
|Func_croatia_oib_number|クロアチアの OIB 番号を検出する|いいえ|
|Func_cyprus_eu_tax_file_number|キプロスの税ファイル番号を検出する|いいえ|
|Func_czech_id_card|チェコ ID カードを検出する|いいえ|
|Func_czech_id_card_new_format|新しい形式でチェコ ID カードを検出する|いいえ|
|Func_dea_number|DEA 番号を検出する|はい|
|Func_denmark_eu_tax_file_number|デンマークの個人識別番号を検出する|いいえ|
|Func_district_of_columbia_drivers_license_number|コロンビア特別区の運転免許証番号を検出する|いいえ|
|Func_estonia_eu_national_id_card|エストニアの個人識別コードを検出する|いいえ|
|Func_eu_debit_card|EU のデビットカードを検出する|いいえ|
|Func_finnish_national_id|フィンランドの国民 ID を検出する|いいえ|
|Func_florida_drivers_license_number|フロリダ州の運転免許証番号を検出する|いいえ|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|フロリダ州、メリーランド州、ミシガン州、ミネソタ州の運転免許証番号を検出する|いいえ|
|Func_formatted_itin|書式設定された US ITIN を検出する|はい|
|Func_fr_insee|フランス INSEE を検出する|いいえ|
|Func_fr_passport|フランスのパスポートを検出する|いいえ|
|Func_france_eu_tax_file_number|フランスの税ファイル番号を検出する|いいえ|
|Func_france_value_added_tax_number|フランスの付加価値税番号を検出する|いいえ|
|Func_french_drivers_license|フランスの運転免許証を検出する|いいえ|
|Func_french_insee|フランス語の INSEE を検出する|いいえ|
|Func_georgia_drivers_license_number|ジョージア州の運転免許証番号を検出する|いいえ|
|Func_german_drivers_license|ドイツの運転免許証を検出する|いいえ|
|Func_german_passport|ドイツのパスポートを検出する|いいえ|
|Func_german_passport_data|ドイツのパスポートを検出する|いいえ|
|Func_germany_eu_tax_file_number|ドイツの税ファイル番号を検出する|いいえ|
|Func_germany_value_added_tax_number|ドイツの付加価値税番号を検出する|いいえ|
|Func_greece_eu_ssn|ギリシャの罪 (AMKA) を検出する|いいえ|
|Func_hawaii_drivers_license_number|ハワイの運転免許証番号を検出する|いいえ|
|Func_hong_kong_id_card|香港 ID カードを検出する|いいえ|
|Func_hungarian_value_added_tax_number|ハンガリーの付加価値税番号を検出する|いいえ|
|Func_hungary_eu_national_id_card|ハンガリーの個人識別番号を検出する|いいえ|
|Func_hungary_eu_ssn_or_equivalent|ハンガリーの社会保障番号を検出する|いいえ|
|Func_hungary_eu_tax_file_number|ハンガリーの税ファイル番号を検出する|いいえ|
|Func_iban|IBAN を検出する|はい|
|Func_idaho_drivers_license_number|アイダホ州の運転免許証番号を検出する|いいえ|
|Func_illinois_drivers_license_number|イリノイ州の運転免許証番号を検出する|いいえ|
|Func_india_aadhaar|インドの aadhaar を検出する|はい|
|Func_indiana_drivers_license_number|インディアナ州の運転免許証番号を検出する|いいえ|
|Func_iowa_drivers_license_number|アイオワ州の運転免許証番号を検出する|いいえ|
|Func_ireland_pps|アイルランドの PPS を検出する|いいえ|
|Func_israeli_national_id_number|イスラエルの国 ID 番号を検出する|いいえ|
|Func_italy_eu_national_id_card|イタリアの会計コードを検出する|いいえ|
|Func_italy_value_added_tax_number|イタリアの付加価値税番号を検出する|いいえ|
|Func_japanese_my_number_corporate|日本のマイナンバー企業を検出する|はい|
|Func_japanese_my_number_personal|日本の個人用番号を検出する|はい|
|Func_jp_bank_account|日本の銀行口座を検出する|いいえ|
|Func_jp_bank_account_branch_code|日本の銀行口座の支店コードを検出する|いいえ|
|Func_jp_drivers_license_number|日本の運転免許証番号を検出する|いいえ|
|Func_jp_passport|日本のパスポートを検出する|いいえ|
|Func_jp_resident_registration_number|日本在住の登録番号を検出する|いいえ|
|Func_jp_sin|日本 SIN を検出する|いいえ|
|Func_jp_sin_pre_1997|日本の sin pre 1997 を検出する|いいえ|
|Func_kansas_drivers_license_number|カンザス州の運転免許証番号を検出する|いいえ|
|Func_kentucky_drivers_license_number|ケンタッキー州の運転免許証番号を検出する|いいえ|
|Func_kentucky_massachusetts_virginia_drivers_license_number|ケンタッキー州、マサチューセッツ州、バージニア州の運転免許証番号を検出する|いいえ|
|Func_latvia_eu_national_id_card|ラトビアの個人コードを検出する|いいえ|
|Func_lithuania_eu_tax_file_number|リトアニアの個人コードを検出する|いいえ|
|Func_louisiana_drivers_license_number|ルイジアナ州の運転免許証番号を検出する|いいえ|
|Func_luxemburg_eu_tax_file_number|ルクセンブルクの国民識別番号 (自然人) を検出します。|いいえ|
|Func_luxemburg_eu_tax_file_number_non_natural|ルクセンブルクの国民識別番号 (非自然人) を検出します。|いいえ|
|Func_maine_drivers_license_number|Maine の運転免許証番号を検出する|いいえ|
|Func_manitoba_drivers_license_number|Manitoba の運転免許証番号を検出する|いいえ|
|Func_maryland_drivers_license_number|メリーランド州の運転免許証番号を検出する|いいえ|
|Func_massachusetts_drivers_license_number|マサチューセッツ州の運転免許証番号を検出する|いいえ|
|Func_mexico_population_registry_code|メキシコの人口レジストリ コードを検出する|いいえ|
|Func_michigan_minnesota_drivers_license_number|ミシガン州、ミネソタ州の運転免許証番号を検出する|いいえ|
|Func_minnesota_drivers_license_number|ミネソタ州の運転免許証番号を検出する|いいえ|
|Func_mississippi_oklahoma_drivers_license_number|Mississippi、オクラホマ州の運転免許証番号を検出する|いいえ|
|Func_missouri_drivers_license_number|ミズーリ州の運転免許証番号を検出する|いいえ|
|Func_montana_drivers_license_number|Montana の運転免許証番号を検出する|いいえ|
|Func_nebraska_drivers_license_number|ネブラスカ州の運転免許証番号を検出する|いいえ|
|Func_netherlands_bsn|オランダの BSN を検出する|いいえ|
|Func_netherlands_eu_tax_file_number|オランダの税ファイル番号を検出する|いいえ|
|Func_netherlands_value_added_tax_number|オランダの付加価値税番号を検出する|いいえ|
|Func_nevada_drivers_license_number|ネバダ州の運転免許証番号を検出する|いいえ|
|Func_new_brunswick_drivers_license_number|新しい Brunswick の運転免許証番号を検出する|いいえ|
|Func_new_hampshire_drivers_license_number|ニューハンプシャー州の運転免許証番号を検出する|いいえ|
|Func_new_jersey_drivers_license_number|ニュージャージー州の運転免許証番号を検出する|いいえ|
|Func_new_mexico_drivers_license_number|新しいメキシコの運転免許証番号を検出する|いいえ|
|Func_new_york_drivers_license_number|ニューヨークの運転免許証番号を検出する|いいえ|
|Func_new_zealand_bank_account_number|ニュージーランドの銀行口座番号を検出する|いいえ|
|Func_new_zealand_inland_revenue_number|ニュージーランド内陸の収益番号を検出する|いいえ|
|Func_new_zealand_ministry_of_health_number|ニュージーランドの保健省番号を検出する|いいえ|
|Func_newfoundland_labrador_drivers_license_number|Newfoundland Labrador の運転免許証番号を検出する|いいえ|
|Func_newzealand_driver_license_number|ニュージーランドの運転免許証番号を検出する|いいえ|
|Func_newzealand_social_welfare_number|ニュージーランドのソーシャル 福利厚生番号を検出する|いいえ|
|Func_north_carolina_drivers_license_number|ノースカロライナ州の運転免許証番号を検出する|いいえ|
|Func_north_dakota_drivers_license_number|ノースダコタ州の運転免許証番号を検出する|いいえ|
|Func_norway_id_number|ノルウェーの ID 番号を検出する|いいえ|
|Func_nova_scotia_drivers_license_number|Nova Scotia の運転免許証番号を検出する|いいえ|
|Func_ohio_drivers_license_number|オハイオ州の運転免許証番号を検出する|いいえ|
|Func_ontario_drivers_license_number|オンタリオ州の運転免許証番号を検出する|いいえ|
|Func_pennsylvania_drivers_license_number|ペンシルベニア州の運転免許証番号を検出する|いいえ|
|Func_pesel_identification_number|ポーランドの国民 ID (PESEL) を検出します。|いいえ|
|Func_poland_eu_tax_file_number|ポーランドの税ファイル番号を検出する|いいえ|
|Func_polish_national_id|ポーランドの ID カードを検出する|いいえ|
|Func_polish_passport_number|ポーランドのパスポート番号を検出する|いいえ|
|Func_polish_regon_number|ポーランド語の REGON 番号を検出する|いいえ|
|Func_portugal_eu_tax_file_number|ポルトガルの納税者番号を検出する|いいえ|
|Func_prince_edward_island_drivers_license_number|プリンス エドワード島州の運転免許証番号を検出する|いいえ|
|Func_quebec_drivers_license_number|ケベック州の運転免許証番号を検出する|いいえ|
|Func_randomized_formatted_ssn|ランダムに書式設定された US SSN を検出する|はい|
|Func_randomized_unformatted_ssn|ランダム化されていない US SSN を検出する|はい|
|Func_rhode_island_drivers_license_number|ロードアイランド州の運転免許証番号を検出する|いいえ|
|Func_romania_eu_national_id_card|ルーマニアの個人数値コード (CNP) を検出します。|いいえ|
|Func_saskatchewan_drivers_license_number|サスカチュワン州の運転免許証番号を検出する|いいえ|
|Func_slovakia_eu_national_id_card|スロバキアの個人番号を検出する|いいえ|
|Func_slovenia_eu_national_id_card|スロベニアの一意のマスター市民番号を検出する|いいえ|
|Func_slovenia_eu_tax_file_number|スロベニアの税ファイル番号を検出する|いいえ|
|Func_south_africa_identification_number|南アフリカの識別番号を検出する|はい|
|Func_south_carolina_drivers_license_number|サウスカロライナ州の運転免許証番号を検出する|いいえ|
|Func_south_dakota_drivers_license_number|サウスダコタ州の運転免許証番号を検出する|いいえ|
|Func_south_korea_resident_number|韓国の居住者番号を検出する|いいえ|
|Func_spain_eu_DL_and_NI_number_citizen|スペインの DL と NI 番号の市民を検出する|いいえ|
|Func_spain_eu_DL_and_NI_number_foreigner|スペインの DL と NI 番号の外国人を検出します。|いいえ|
|Func_spain_eu_driver's_license_number|スペインの運転免許証番号を検出する|いいえ|
|Func_spain_eu_tax_file_number|スペインの税ファイル番号を検出する|いいえ|
|Func_spanish_social_security_number|スペインの社会保障番号を検出する|いいえ|
|Func_ssn|ランダム化されていない書式設定された US SSN を検出する関数|はい|
|Func_sweden_eu_tax_file_number|スウェーデンの税ファイル番号を検出する|いいえ|
|Func_swedish_national_identifier|スウェーデンの国識別子を検出する|はい|
|Func_swiss_social_security_number_ahv|スイスの社会保障番号 AHV を検出する|いいえ|
|Func_taiwanese_national_id|台湾の国民 ID を検出する|いいえ|
|Func_tennessee_drivers_license_number|テネシー州の運転免許証番号を検出する|いいえ|
|Func_texas_drivers_license_number|テキサス州の運転免許証番号を検出する|いいえ|
|Func_Thai_Citizen_Id|タイの市民 ID を検出する|いいえ|
|Func_Turkish_National_Id|トルコの国民 ID を検出する|はい|
|Func_uk_drivers_license|英国の運転免許証を検出する|いいえ|
|Func_uk_eu_tax_file_number|英国固有の納税者番号を検出する|いいえ|
|Func_uk_nhs_number|英国の NHS 番号を検出する|はい|
|Func_uk_nino|英国 NINO を検出する|いいえ|
|Func_unformatted_canadian_sin|フォーマットされていないカナダの SIN を検出する|いいえ|
|Func_unformatted_itin|未フォーマットの US ITIN を検出する|はい|
|Func_unformatted_ssn|ランダム化されていない未フォーマットの US SSN を検出する|はい|
|Func_usa_uk_passport|米国と英国のパスポートを検出する|はい|
|Func_utah_drivers_license_number|ユタ州の運転免許証番号を検出する|いいえ|
|Func_vermont_drivers_license_number|バーモント州の運転免許証番号を検出する|いいえ|
|Func_virginia_drivers_license_number|バージニア州の運転免許証番号を検出する|いいえ|
|Func_washington_drivers_license_number|ワシントン州の運転免許証番号を検出する|いいえ|
|Func_west_virginia_drivers_license_number|ウェストバージニア州の運転免許証番号を検出する|いいえ|
|Func_wisconsin_drivers_license_number|Wisconsin の運転免許証番号を検出する|いいえ|
|Func_wyoming_drivers_license_number|Wyoming の運転免許証番号を検出する|いいえ|
|

## <a name="func_us_date"></a>Func_us_date

Func_us_date一般的な米国の形式で日付を確認します。 一般的な形式は、"月/日/年"、"月日年"、"月日年" です。 月の名前または省略形は大文字と小文字を区別しません。

例:

- 2016 年 12 月 2 日
- 2016 年 12 月 2 日
- dec 02 2016
- 12/2/2016
- 12/02/16
- Dec-2-2016
- 12-2-16

受け入れ可能な月の名前:

- 英語
  - 1 月、2 月、3 月、4 月、5 月、6 月、7 月、8 月、9 月、10 月、11 月、12 月
  - 1 月 2 月 3 月 4 月 5 月 7 月 7 月 8 月 9 月 10 月 11 月 12 月

## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates E.U の日付を確認します。 形式 (および米国外のほとんどの場所) ("day/month/year"、"day-month-year"、"day month year" など)。 月の名前または省略形は大文字と小文字を区別しません。

例:

- 2016 年 12 月 2 日
- 2016 年 12 月 2 日
- 2 12 月 16 日
- 2/12/2016
- 02/12/16
- 2016 年 12 月 2 日
- 2-12-16

受け入れ可能な月の名前:

- 英語
  - 1 月、2 月、3 月、4 月、5 月、6 月、7 月、8 月、9 月、10 月、11 月、12 月
  - 1 月 2 月 3 月 4 月 5 月 7 月 7 月 8 月 9 月 10 月 11 月 12 月
- オランダ語
  - januari, februari, maart, April, mei, juni, juli, augustus, 9 月, ocktober, 10 月, 11 月, 12 月
  - jan feb maart apr mei jun 7月 8 月 9 月 9 月 okt 11 月 12 月
- フランス語
  - janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, novembre, décembre
  - janv. févr。 mars avril mai juin juil. août 9 月 oct. 11 月 déc.
- ドイツ語
  - jänuar, februar, märz, April, mai, juni juli, 8 月, 9 月, oktober, 11 月, dezember
  - Jan./Jän. 2 月 März Apr. Mai Juni Juli Aug. 9 月. Okt. 11 月 Dez.
- イタリア語
  - gennaio、febbraio、marzo、aprile、maggio、giugno、luglio、agosto、settembre、ottobre、novembre、dicembre
  - genn。 febbr。 mar. apr. magg。 giugno luglio ag. sett。 ott。 11 月 dic.
- ポルトガル語
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
  - jan fev mar abr mai jun jul ago set out nov dez
- スペイン語
  - enero、febrero、marzo、abril、mayo、junio、julio、agosto、septiembre、octubre、noviembre、diciembre
  - enero feb. marzo abr. mayo jun. jul. agosto 9/set. oct. 11 月 dic.

## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (非推奨)

> [!NOTE]
> この関数はポルトガル語の月名のみをサポートし、上記の関数に含まれているため  `Func_eu_date` 、非推奨です。

この関数は、ポルトガル語で一般的に使用される形式の日付を確認します。 この関数の形式は、使用する言語でのみ異  `Func_eu_date` なります。

例:

- 2 Dez 2016
- 02 dez 2016
- 2 Dez 16
- 2/12/2016
- 02/12/16
- 2-Dez-2016
- 2-12-16

受け入れ可能な月の名前:

- ポルトガル語
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
  - jan fev mar abr mai jun jul ago set out nov dez

## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (非推奨)

> [!NOTE]
> この関数は、上記の関数に含まれるオランダ語の月名のみをサポートしています  `Func_eu_date` 。

この関数は、オランダ語で一般的に使用される形式の日付を確認します。 この関数の形式は、使用する言語でのみ異  `Func_eu_date` なります。

例:

- 2 Mei 2016
- 02 mei 2016
- 2 Mei 16
- 2/12/2016
- 02/12/16
- 2-Mei-2016
- 2-12-16

受け入れ可能な月の名前:

- オランダ語
  - januari, februari, maart, April, mei, juni, juli, augustus, 9 月, ocktober, 10 月, 11 月, 12 月
  - jan feb maart apr mei jun 7月 8 月 9 月 9 月 out okt 11 月 12 月

## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date、クレジット カードやデビットカードでよく使用される形式の日付を確認します。 この関数は、"月/年"、"month-year"、"[month name] year"、および "[月の省略形] 年" の形式で日付と一致します。 月の名前または省略形は大文字と小文字を区別しません。

例:

- MM/YY -- たとえば、01/11 または 1/11 など
- MM/YYYY -- たとえば、01/2011 または 2011/1/2011
- MM-YY -- たとえば、01-22 または 1-11
- MM-YYYY -- たとえば、01~2000 または 1~2000

次の形式は、YY または YYYY をサポートしています。

- Month-YYYY -- 2010 年 1 月、2010 年 1 月、1 月 10 日、または 1 月から 1 月 10 日など
- 月 YYYY -- たとえば、'2010 年 1 月' または '2010 年 1 月' または '1 月 10 日' または '1 月 10'
- MonthYYYY -- たとえば、'1 月 2010' または 'Jan2010' または 'january10' または 'Jan10'
- Month/YYYY -- たとえば、'2010 年 1 月' または 'Jan/2010' または 'january/10' または 'Jan/10'

受け入れ可能な月の名前:

- 英語
  - 1 月、2 月、3 月、4 月、5 月、6 月、7 月、8 月、9 月、10 月、11 月、12 月
  - 1 月 2 月 3 月 4 月 5 月 6 月 7 月 8 月 9 月 10 月 11 月 12

## <a name="func_us_address"></a>Func_us_address

Func_us_addressは、米国の州名または郵便の省略形の後に有効な郵便番号を検索します。 郵便番号は、米国の州名または省略形に関連付けられている正しい郵便番号の 1 つである必要があります。 米国の州名と郵便番号は、句読点または文字で区切る必要があります。

例:

- ワシントン 98052
- Washington 98052-9998
- WA 98052
- WA 98052-9998
