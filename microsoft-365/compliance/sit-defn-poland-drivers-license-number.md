---
title: ポーランドのドライバー ライセンス番号エンティティ定義
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
description: ポーランドのドライバーのライセンス番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 120e000e5d7666d213062d812b2b5d6b6555c18e
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67325707"
---
# <a name="poland-drivers-license-number"></a>ポーランドの運転免許証番号

## <a name="format"></a>フォーマット

2 つのスラッシュを含む 11 または 14 桁の数字

## <a name="pattern"></a>パターン

2 つのスラッシュを含む 11 または 14 桁の数字

- 5 桁
- スラッシュ
- 2 桁の数字
- スラッシュ
- 4 桁または 7 桁

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_poland_eu_driver's_license_number` がパターンに一致するコンテンツを検出した。
- キーワードが `Keywords_eu_driver's_license_number` 見つかったか、見 `Keywords_poland_eu_driver's_license_number` つかりました。

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

### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver's_license_number

- prawo jazdy
- prawa jazdy
