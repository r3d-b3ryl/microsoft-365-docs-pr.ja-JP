---
title: アイルランドの個人パブリック サービス (PPS) 番号エンティティ定義
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
description: アイルランドの個人パブリック サービス (PPS) 番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 9473886085fe3ae5630becdeeb69efb82f428edd
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996877"
---
# <a name="ireland-personal-public-service-pps-number"></a>アイルランドの個人公共サービス (PPS) 番号

## <a name="format"></a>フォーマット

古い形式 (2012 年 12 月 31 日まで):

- 7 桁の数字の後に 1 ~ 2 文字

新しい形式 (2013 年 1 月 1 日以降):

- 7 桁の数字の後に 2 つの文字が続く

## <a name="pattern"></a>パターン

古い形式 (2012 年 12 月 31 日まで):

- 7 桁
- 1 文字から 2 文字 (大文字と小文字は区別されません)

新しい形式 (2013 年 1 月 1 日以降):

- 7 桁
- アルファベットチェックの数字である文字 (大文字と小文字は区別されません)
- A から I、または "W" の範囲の省略可能な文字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- パターンに一致する関数 `Func_ireland_pps finds` の内容。
- `Keywords_ireland_eu_national_id_card` のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 関数 `Func_ireland_pps` がパターンに一致するコンテンツを検出した。
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

## <a name="keywords"></a>キーワード

### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- クライアント ID サービス
- identification number
- 個人 ID 番号
- 個人のパブリック サービス番号
- personal service no
- phearsanta seirbhíse poiblí
- pps no
- pps 番号
- pps num
- pps service no
- ppsn
- ppsno#
- ppsno
- Psp
- public service no
- publicserviceno#
- publicserviceno
- 収益と社会保険番号
- rsi no
- rsi 番号
- rsin
- seirbhís aitheantais クライアント
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
- tax id
- 税の識別番号なし
- 税識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin ID
- tin no
- 錫#