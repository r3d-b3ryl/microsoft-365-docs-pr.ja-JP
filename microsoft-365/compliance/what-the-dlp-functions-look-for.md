---
title: データ損失防止 (DLP) 関数の検索対象
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
description: データ損失防止 (DLP) 関数の検索方法について説明します。
ms.openlocfilehash: b77075b0b31ad5d6e6e2b7062c35e96649fa8365
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841448"
---
# <a name="what-the-dlp-functions-look-for"></a>DLP 関数の検索対象

データ損失防止 (DLP) ポリシーは、機密情報の種類を使用して機密アイテムを識別できます。 機密情報の種類の例としては、クレジットカード番号と EU デビットカード番号が挙げられます。 機密情報の種類は特定のパターンを検索します。 機密情報の種類は、データの形式を調べてチェックサムを調べ、関連するキーワードまたはその他の情報を検索することで、データを検証します。 この機能の一部は、内部機能によって実行されます。 たとえば、クレジットカード番号の機密情報の種類では、有効期限の日付に書式設定された日付を検索するために関数が使用されます。 これにより、番号がクレジットカード番号であることを corroborate できます。
  
この記事では、定義済みの機密情報の種類のしくみを理解するために役立つ関数について説明します。 詳細については、「[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」を参照してください。
  
## <a name="table-of-functions"></a>関数の表

|関数名  |関数のアクション  |バリデーター|
|---------|---------|---------|
|Func_Argentina_Unique_Tax_Key|アルゼンチンの一意の税キーを検出して検証します|no|
|Func_aba_routing|ABA ルーティング番号を検出します。| はい|
|Func_alabama_drivers_license_number|Alabama ドライバーのライセンス番号を検出します。|no|
|Func_alaska_delaware_oregon_drivers_license_number|アラスカ、デラウェア、オレゴンドライバーのライセンス番号を検出します。|no|
|Func_alaska_drivers_license_number|アラスカドライバーのライセンス番号を検出します。|no|
|Func_alberta_drivers_license_number|アルバータ州の運転免許証番号を検出します。|no|
|Func_Argentina_Unique_Tax_Key|アルゼンチンの一意の税キーを検出します|no|
|Func_arizona_drivers_license_number|アリゾナドライバーのライセンス番号を検出します。|no|
|Func_arkansas_drivers_license_number|Arkansas ドライバーのライセンス番号を検出します。|no|
|Func_australian_business_number|オーストラリアのビジネス番号を検出します。|no|
|Func_Australian_Company_Number|オーストラリアの会社番号を検出します。|no|
|Func_australian_medical_account_number|オーストラリアの医療口座番号を検出します。|no|
|Func_australian_tax_file_number|オーストラリアの税ファイル番号を検出します。|はい|
|Func_austria_eu_ssn_or_equivalent|オーストリアの社会保障番号を検出します。|no|
|Func_austria_eu_tax_file_number|オーストリアの税ファイル番号を検出します。|no|
|Func_Austria_Value_Added_Tax|オーストリアの付加価値税を検出します。|no|
|Func_belgium_national_number|ベルギーの国内番号を検出します。|no|
|Func_belgium_value_added_tax_number|ベルギーの付加価値税番号を検出します|no|
|Func_brazil_cnpj|ブラジルの法人番号を検出します (CNPJ)|はい|
|Func_brazil_cpf|ブラジルの CPF を検出します。|はい|
|Func_brazil_rg|ブラジルの RG を検出します|no|
|Func_british_columbia_drivers_license_number|英国コロンビアの運転免許証番号を検出します。|no|
|Func_bulgaria_eu_national_id_card|ブルガリアの一様な民事訴訟番号を検出します。|no|
|Func_california_drivers_license_number|カリフォルニア運転者のライセンス番号を検出します。|no|
|Func_canadian_sin|カナダのサインを検出する|はい|
|Func_chile_id_card|チリ ID カードを検出します|no|
|Func_china_resident_id|中国の常駐 ID を検出します。|no|
|Func_colorado_drivers_license_number|コロラドドライバーのライセンス番号を検出します。|no|
|Func_connecticut_drivers_license_number|コネチカットドライバーのライセンス番号を検出します。|no|
|Func_credit_card|クレジットカードの検出|はい|no|
|Func_croatia_id_card|クロアチアの ID カードを検出します|no|
|Func_croatia_oib_number|クロアチア語の OIB 番号を検出します。|no|
|Func_cyprus_eu_tax_file_number|キプロス税ファイル番号を検出します。|no|
|Func_czech_id_card|チェコ語の ID カードを検出します|no|
|Func_czech_id_card_new_format|新しい形式でチェコ語の ID カードを検出します|no|
|Func_dea_number|DEA を検出します。|はい|
|Func_denmark_eu_tax_file_number|デンマークの個人識別番号を検出する|no|
|Func_district_of_columbia_drivers_license_number|コロンビア運転免許証番号の地域を検出します。|no|
|Func_estonia_eu_national_id_card|エストニアの個人識別コードを検出する|no|
|Func_eu_debit_card|EU のデビットカードを検出します|no|
|Func_finnish_national_id|フィンランド語の national ID を検出します|no|
|Func_florida_drivers_license_number|フロリダ運転免許証番号を検出します。|no|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|フロリダ、メリーランド州、ミシガン、ミネソタ運転免許証番号を検出します。|no|
|Func_formatted_itin|書式設定された US ITIN を検出します。|はい|
|Func_fr_insee|フランスを検出します。|no|
|Func_fr_passport|フランスのパスポートを検出する|no|
|Func_france_eu_tax_file_number|フランスの税ファイル番号を検出します。|no|
|Func_france_value_added_tax_number|フランスの付加価値税番号を検出します。|no|
|Func_french_drivers_license|フランス語版のドライバーのライセンスを検出する|no|
|Func_french_insee|フランス語を検出します。|no|
|Func_georgia_drivers_license_number|ジョージアドライバーのライセンス番号を検出します|no|
|Func_german_drivers_license|ドイツの運転免許証を検出します。|no|
|Func_german_passport|ドイツのパスポートを検出する|no|
|Func_german_passport_data|ドイツのパスポートを検出する|no|
|Func_germany_eu_tax_file_number|ドイツの税ファイル番号を検出します|no|
|Func_germany_value_added_tax_number|ドイツの値が付加された税番号を検出します|no|
|Func_greece_eu_ssn|ギリシャの sin (AMKA) を検出します。|no|
|Func_hawaii_drivers_license_number|ハワイドライバーのライセンス番号を検出します。|no|
|Func_hong_kong_id_card |香港の ID カードを検出します|no|
|Func_hungarian_value_added_tax_number|ハンガリーの付加価値税番号を検出します。|no|
|Func_hungary_eu_national_id_card|ハンガリーの個人識別番号を検出します。|no|
|Func_hungary_eu_ssn_or_equivalent|ハンガリーのソーシャルセキュリティ番号を検出します。|no|
|Func_hungary_eu_tax_file_number|ハンガリーの税ファイル番号を検出します。|no|
|Func_iban|IBAN を検出する|はい|
|Func_idaho_drivers_license_number|Idaho ドライバーのライセンス番号を検出します。|no|
|Func_illinois_drivers_license_number|イリノイドライバーのライセンス番号を検出します。|no|
|Func_india_aadhaar|インドの aadhaar を検出します。|はい|
|Func_indiana_drivers_license_number|インディアナドライバーのライセンス番号を検出します。|no|
|Func_iowa_drivers_license_number|アイオワドライバーのライセンス番号を検出します。|no|
|Func_ireland_pps|アイルランド PPS を検出します。|no|
|Func_israeli_national_id_number|イスラエルの国民 ID 番号を検出します|no|
|Func_italy_eu_national_id_card |イタリアの会計コードを検出します。|no|
|Func_italy_value_added_tax_number|イタリアの付加価値税番号を検出します。|no|
|Func_japanese_my_number_corporate|会社の日本を検出します。|はい|
|Func_japanese_my_number_personal|日本の個人番号を検出します。|はい|
|Func_jp_bank_account|日本の銀行口座を検出する|no|
|Func_jp_bank_account_branch_code|日本の銀行口座のブランチコードを検出する|no|
|Func_jp_drivers_license_number|日本の運転免許証番号を検出します。|no|
|Func_jp_passport|日本のパスポートを検出する|no|
|Func_jp_resident_registration_number|日本に居住している登録番号を検出する|no|
|Func_jp_sin|日本のサインを検出する|no|
|Func_jp_sin_pre_1997|1997前の sin を検出します。|no|
|Func_kansas_drivers_license_number|カンザス運転者のライセンス番号を検出します。|no|
|Func_kentucky_drivers_license_number|ケンタッキードライバーのライセンス番号を検出します。|no|
|Func_kentucky_massachusetts_virginia_drivers_license_number|ケンタッキー、マサチューセッツ、バージニア運転免許証番号を検出します。|no|
|Func_latvia_eu_national_id_card|ラトビアの個人コードを検出する|no|
|Func_lithuania_eu_tax_file_number|リトアニアの個人コードを検出します|no|
|Func_louisiana_drivers_license_number|ルイジアナドライバーのライセンス番号を検出します。|no|
|Func_luxemburg_eu_tax_file_number|ルクセンブルク national の識別番号を検出します (自然人数)|no|
|Func_luxemburg_eu_tax_file_number_non_natural|ルクセンブルク国立識別番号を検出します (非自然人数)|no|
|Func_maine_drivers_license_number|Maine ドライバーのライセンス番号を検出します。|no|
|Func_manitoba_drivers_license_number|マニトバ州ドライバーのライセンス番号を検出します。|no|
|Func_maryland_drivers_license_number|メリーランド州ドライバーのライセンス番号を検出します。|no|
|Func_massachusetts_drivers_license_number|マサチューセッツ州の運転免許証番号を検出します。|no|
|Func_mexico_population_registry_code|メキシコ集団のレジストリコードを検出します|no|
|Func_michigan_minnesota_drivers_license_number|ミシガン、ミネソタドライバーのライセンス番号を検出します。|no|
|Func_minnesota_drivers_license_number|ミネソタドライバーのライセンス番号を検出します。|no|
|Func_mississippi_oklahoma_drivers_license_number|ミシシッピ、オクラホマドライバーのライセンス番号を検出します。|no|
|Func_missouri_drivers_license_number|ミズーリ運転免許証番号を検出します。|no|
|Func_montana_drivers_license_number|モンタナドライバーのライセンス番号を検出します。|no|
|Func_nebraska_drivers_license_number|ネブラスカドライバーのライセンス番号を検出します。|no|
|Func_netherlands_bsn|オランダ BSN を検出します|no|
|Func_netherlands_eu_tax_file_number|オランダの税ファイル番号を検出します。|no|
|Func_netherlands_value_added_tax_number|オランダ値の加算された税番号を検出します|no|
|Func_nevada_drivers_license_number|ネバダドライバーのライセンス番号を検出します。|no|
|Func_new_brunswick_drivers_license_number|新しいニューブランズウィックドライバーのライセンス番号を検出します。|no|
|Func_new_hampshire_drivers_license_number|新しいニューハンプシャードライバーのライセンス番号を検出します。|no|
|Func_new_jersey_drivers_license_number |新しいニュージャージー運転免許証番号を検出します。|no|
|Func_new_mexico_drivers_license_number |新しいメキシコ運転免許証番号を検出します。|no|
|Func_new_york_drivers_license_number   |ニューヨークの運転免許証番号を検出します。|no|
|Func_new_zealand_bank_account_number   |ニュージーランドの銀行口座番号を検出します|no|
|Func_new_zealand_inland_revenue_number |ニュージーランド inland 歳入番号を検出します。|no|
|Func_new_zealand_ministry_of_health_number|新ニュージーランドの健康保険の番号を検出します|no|
|Func_newfoundland_labrador_drivers_license_number|ニューファンドランド Labrador ドライバーのライセンス番号を検出します。|no|
|Func_newzealand_driver_license_number  |ニュージーランドドライバーライセンス番号を検出します|no|
|Func_newzealand_social_welfare_number  |ニュージーランドのソーシャル welfare 番号を検出します|no|
|Func_north_carolina_drivers_license_number|ノースカロライナ運転免許証番号を検出します。|no|
|Func_north_dakota_drivers_license_number|北米ののドライバーのライセンス番号を検出します。|no|
|Func_norway_id_number  |ノルウェーの ID 番号を検出します|no|
|Func_nova_scotia_drivers_license_number|Nova スコシアドライバーのライセンス番号を検出します。|no|
|Func_ohio_drivers_license_number   |オハイオドライバーのライセンス番号を検出します。|no|
|Func_ontario_drivers_license_number    |オンタリオ州ドライバーのライセンス番号を検出します。|no|
|Func_pennsylvania_drivers_license_number|ペンシルバニアドライバーのライセンス番号を検出します。|no|
|Func_pesel_identification_number   |ポーランドの National ID (PESEL) を検出します|no|
|Func_poland_eu_tax_file_number |ポーランドの税ファイル番号を検出します。|no|
|Func_polish_national_id    |ポーランドの id カードを検出します|no|
|Func_polish_passport_number    |ポーランド語のパスポート番号を検出する|no|
|Func_polish_regon_number   |ポーランド語の番号を検出します。|no|
|Func_portugal_eu_tax_file_number|ポルトガルの税識別番号を検出します|no|
|Func_prince_edward_island_drivers_license_number|Prince Edward アイランド運転免許証番号を検出します。|no|
|Func_quebec_drivers_license_number |ケベック運転免許証番号を検出します。|no|
|Func_randomized_formatted_ssn  |ランダムに書式化された US SSN を検出する|はい|
|Func_randomized_unformatted_ssn|ランダム化されていない US SSN を検出する|はい|
|Func_rhode_island_drivers_license_number|ロードアイランド運転免許証番号を検出します。|no|
|Func_romania_eu_national_id_card   |ルーマニアの個人数値コード (CNP) を検出します|no|
|Func_saskatchewan_drivers_license_number|Saskatchewan ドライバーのライセンス番号を検出します。|no|
|Func_slovakia_eu_national_id_card  |スロバキアの個人番号を検出します。|no|
|Func_slovenia_eu_national_id_card  |スロベニア固有のマスター市民番号を検出します。|no|
|Func_slovenia_eu_tax_file_number   |スロベニアの税ファイル番号を検出します|no|
|Func_south_africa_identification_number|南アフリカの識別番号を検出します。|はい|
|Func_south_carolina_drivers_license_number|サウスカロライナ運転免許証番号を検出します。|no|
|Func_south_dakota_drivers_license_number|南ダコタ運転免許証番号を検出します。|no|
|Func_south_korea_resident_number   |韓国の常駐番号を検出します。|no|
|Func_spain_eu_DL_and_NI_number_citizen |スペイン DL と NI 番号の市民を検出します|no|
|Func_spain_eu_DL_and_NI_number_foreigner|スペイン DL および NI 番号 foreigner を検出します。|no|
|Func_spain_eu_driver ' s_license_number  |スペインの運転免許証番号を検出します。|no|
|Func_spain_eu_tax_file_number  |スペインの税ファイル番号を検出します|no|
|Func_spanish_social_security_number|スペインの社会保障番号を検出します。|no|
|Func_ssn   |ランダムに書式設定されていない US SSN を検出する関数|はい|
|Func_sweden_eu_tax_file_number|スウェーデンの税ファイル番号を検出します。|no|
|Func_swedish_national_identifier|スウェーデンの national 識別子を検出します。|はい|
|Func_swiss_social_security_number_ahv|スイスのソーシャルセキュリティ番号の AHV を検出します。|no|
|Func_taiwanese_national_id |台湾各国の ID を検出します|no|
|Func_tennessee_drivers_license_number|テネシードライバーのライセンス番号を検出します。|no|
|Func_texas_drivers_license_number  |テキサス運転免許証番号の検出|no|
|Func_Thai_Citizen_Id   |タイの市民 ID を検出します|no|
|Func_Turkish_National_Id|トルコ語の国 ID を検出します|はい|
|Func_uk_drivers_license|UK ドライバーのライセンスを検出します。|no|
|Func_uk_eu_tax_file_number|英国固有の納税者番号を検出する|no|
|Func_uk_nhs_number |英国の NHS 番号を検出します。|はい|
|Func_uk_nino   |UK NINO を検出します。|no|
|Func_unformatted_canadian_sin|書式設定されていないカナダの SIN を検出|no|
|Func_unformatted_itin  |未フォーマットの US ITIN を検出します。|はい|
|Func_unformatted_ssn   |ランダム化されていない US SSN を検出します。|はい|
|Func_usa_uk_passport   |米国および英国のパスポートを検出する|はい|
|Func_utah_drivers_license_number|ユタ運転免許証番号を検出します。|no|
|Func_vermont_drivers_license_number|バーモントドライバーのライセンス番号を検出します。|no|
|Func_virginia_drivers_license_number|バージニアドライバーのライセンス番号を検出します。|no|
|Func_washington_drivers_license_number|ワシントン運転免許証番号を検出します。|no|
|Func_west_virginia_drivers_license_number|West バージニア運転免許証番号を検出します|no|
|Func_wisconsin_drivers_license_number  |ウィスコンシンドライバーのライセンス番号を検出します。|no|
|Func_wyoming_drivers_license_number    |ワイオミングドライバーのライセンス番号を検出します。|no|


## <a name="func_us_date"></a>Func_us_date

Func_us_date は、一般的な米国の形式で日付を検索します。 共通の形式は、"月/日/年"、"月-日-年"、"月の年" です。 月の名前または略称では大文字と小文字は区別されません。 
  
例:
  
- 2016年12月2日
    
- 2016年12月2
    
- 02 2016 年12月
    
- 12/2/2016
    
- 12/02/16
    
- 2-2016 年12月
    
- 12-2-16
    
受諾された月の名前:
  
- 英語
    
  - 1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月
    
  - Jan 7 月2日5月5日5月5日5月5日。
    
## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates 共通の E.U. で日付を検索します。 "日/月/年"、"日-月-年"、"年月日" などの形式 (米国以外の場所)。 月の名前または略称では大文字と小文字は区別されません。
  
例:
  
- 2016年12月2時
    
- 02 dec 2016
    
- 2月16時
    
- 2/12/2016
    
- 02/12/16
    
- 2016年12月2時
    
- 2-12-16
    
受諾された月の名前:
  
- 英語
    
  - 1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月
    
  - Jan 7 月2日5月5日5月5日5月5日。
    
- オランダ語
    
  - januari、februari、maart、エイプリル、mei、juni、juli、augustus、9月、ocktober、10月、11月、12月
    
  - 1月1日6月 (2001 年11月) (oct) 7 月7日9月 | 8 月7日 (oct)
    
- フランス語
    
  - janvier、février、mars、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre
    
  - janv. févr. mars avril mai juin juil。 août 9 月 oct. 年11月. déc.
    
- ドイツ語
    
  - jänuar、februar、märz、エイプリル、mai、juni juli、8月、9月、oktober、11月、dezember
    
  - Jan./Jän。 März Mai Juni Juli 年8月9日。 11月. Dez。
    
- イタリア語
    
  - gennaio、febbraio、marzo、aprile、maggio、gifeno、luglio、agosto、settembre、ottobre、novembre、dicembre
    
  - genn。 febbr。 年. 4. magg giluglio ag はありません。 設定. ott。 年11月. .dic.
    
- ポルトガル語
    
  - ジャネイロ、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro
    
  - jan fev 3 月 abr mai 6 月5日前にセットアップする
    
- スペイン語
    
  - enero、febrero、marzo、abril、ago、junio、julio、agosto、septiembre、octubre、noviembre、diciembre
    
  - enero feb marzo abr。 6月 o 日 年. /set. 年9月. oct. 年11月. .dic.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (非推奨)

> [!NOTE]
> この関数は、上記の関数に含まれているポルトガル語の月の名前のみをサポートしているため、廃止されました  `Func_eu_date` 。 
  
この関数は、ポルトガル語でよく使用される形式で日付を検索します。 この関数の形式は、使用されている  `Func_eu_date` 言語でのみ異なります。
  
例:
  
- 2 dez 2016
    
- 02 dez 2016
    
- 2 dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-dez-2016
    
- 2-12-16
    
受諾された月の名前:
  
- ポルトガル語
    
  - ジャネイロ、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro
    
  - jan fev 3 月 abr mai 6 月5日前にセットアップする
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (非推奨)

> [!NOTE]
> この関数は、上の関数に含まれるオランダ語の月の名前のみをサポートしているため、廃止されました  `Func_eu_date` 。 
  
この関数は、オランダ語でよく使用される形式で日付を検索します。 この関数の形式は、使用されている  `Func_eu_date` 言語でのみ異なります。
  
例:
  
- 2 mei 2016
    
- 02 mei 2016
    
- 2 mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-mei-2016
    
- 2-12-16
    
受諾された月の名前:
  
- オランダ語
    
  - januari、februari、maart、エイプリル、mei、juni、juli、augustus、9月、ocktober、10月、11月、12月
    
  - jan 2 月9日9月 (9 月) (9 月7日)
    
## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date は、クレジットカードとデビットカードでよく使用される形式の日付を検索します。 この関数は、日付を "月/年"、"月-年"、"[月名] 年"、"月の省略名] 年" の形式で照合します。 月の名前または略称では大文字と小文字は区別されません。
  
例:
  
- MM/YY--たとえば、01/11 または1/11
    
- MM/YYYY--たとえば、01/2011 または1/2011
    
- MM-YY--たとえば、01-22 または1-11
    
- MM-YYYY--たとえば、01-2000 または1-2000
    
次の形式では、YY または YYYY がサポートされています。
  
- 月--2010 または 2010 1 月-または Jan-10 または Jan-10 または1月10日
    
- 月 YYYY--たとえば、' january 2010 ' または ' Jan 2010 ' または ' Jan 10 ' または ' Jan 10 ' のようになります。
    
- 月 Yyyy--たとえば、' january2010 ' または ' Jan2010 ' または ' january10 ' または ' Jan10 '
    
- Month/YYYY--たとえば、' january/2010 '、' Jan/2010 '、' jan/10 '、または ' Jan/10 '
    
受諾された月の名前:
  
- 英語
    
  - 1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月
    
  - 1月2日から4月5日 (年7月)
    
## <a name="func_us_address"></a>Func_us_address

Func_us_address は、米国の州名または郵便の省略形の後に有効な郵便番号を検索します。 郵便番号は、米国の州名または略語に関連付けられている正しい zip コードのいずれかである必要があります。 米国の都道府県名と郵便番号は、句読点または文字で区切ることはできません。
  
例:
  
- ワシントン98052
    
- ワシントン98052-9998
    
- WA 98052
    
- WA 98052-9998
