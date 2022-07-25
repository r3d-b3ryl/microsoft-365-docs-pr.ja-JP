---
title: マルタドライバーライセンス番号エンティティ定義
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
description: マルタのドライバーのライセンス番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: af50ea8bd508053b922cd55d26f299aa080e2bc3
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997709"
---
# <a name="malta-drivers-license-number"></a>マルタの運転免許証番号

## <a name="format"></a>フォーマット

指定したパターンの 2 文字と 6 桁の組み合わせ

## <a name="pattern"></a>パターン

2 文字と 6 桁の組み合わせ:

- 2 文字 (数字または文字、大文字と小文字は区別されません)
- スペース (省略可能)
- 3 桁
- スペース (省略可能)
- 3 桁

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_malta_eu_driver's_license_number` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keywords_eu_driver's_license_number` 見つかったか、見 `Keywords_malta_eu_driver's_license_number` つかりました。

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

## <a name="keywords"></a>キーワード

### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

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
- ドライバー ライセンス
- ドライバー ライセンス
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
- ドライバー ライセンス
- driver'lic
- driver'lics
- ドライバーのライセンス
- ドライバーのライセンス
- ドライバーのライセンス
- ドライバーのライセンス
- driver' lic
- driver' lics
- ドライバーのライセンス
- ドライバーのライセンス
- ドライバーのライセンス
- ドライバーのライセンス
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- ドライバーの lics
- driver's license
- driver's licenses
- driver's licence
- ドライバーのライセンス
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- ドライバー ライセンス#
- driver'lic#
- driver'lics#
- ドライバーのライセンス#
- ドライバーのライセンス#
- ドライバーのライセンス#
- ドライバーのライセンス#
- driver' lic#
- driver' lics#
- ドライバーのライセンス#
- ドライバーのライセンス#
- ドライバーのライセンス#
- ドライバーのライセンス#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- ドライバーの lics#
- ドライバーのライセンス#
- ドライバーのライセンス#
- ドライバーのライセンス#
- ドライバーのライセンス#
- driving licence
- driving license
- dlno#
- driv lic
- driv licen
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driv ライセンス
- driver licen
- drivers licen
- driver's licen
- lic を駆動する
- licen を駆動する
- ライセンスを運転する
- driving licence
- driving licences
- 運転許可
- dl no
- dlno
- dl 番号

### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver's_license_number

- liċenzja tas-sewqan
- liċenzji tas-sewwieq