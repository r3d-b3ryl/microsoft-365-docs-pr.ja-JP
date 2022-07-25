---
title: オランダの税識別番号エンティティ定義
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
description: オランダの税識別番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 03dc229b91636644075428b9b01fee1503c80da1
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997142"
---
# <a name="netherlands-tax-identification-number"></a>オランダの納税者番号

この機密情報の種類は、次の場合にのみ使用できます。

- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- データ ライフサイクル管理
- レコード管理
- Microsoft Defender for Cloud Apps

## <a name="format"></a>フォーマット

スペースまたは区切り記号のない 9 桁

## <a name="pattern"></a>パターン

9 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_netherlands_eu_tax_file_number` がパターンに一致するコンテンツを検出した。
- `Keywords_netherlands_eu_tax_file_number` のキーワードを検出した。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 関数 `Func_netherlands_eu_tax_file_number` がパターンに一致するコンテンツを検出した。

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

## <a name="keywords"></a>キーワード

### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- btw nummer
- hollânske 税の識別
- hulandes impuesto id number
- hulandes impuesto 識別
- identificatienummer belasting
- identificatienummer van belasting
- impuesto 識別番号
- impuesto 数値
- nederlands belasting id nummer
- nederlands belasting identificatie
- nederlands belasting identificatienummer
- nederlands belastingnummer
- nederlandse belasting identificatie
- オランダの税金の識別
- オランダの税金の識別
- オランダの tin
- オランダのブリキ
- tax id
- 税の識別番号なし
- 税識別番号
- 税の識別 tal
- tax no#
- tax no
- 税番号
- 税登録番号
- tax tal
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin ID
- tin no
- 錫#