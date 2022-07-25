---
title: オーストリアの税識別番号エンティティ定義
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
description: オーストリアの税識別番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: d73bf75e554703b09ce073426f4671b296cdd884
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996852"
---
# <a name="austria-tax-identification-number"></a>オーストリアの納税者番号

## <a name="format"></a>フォーマット

オプションのハイフンとスラッシュを含む 9 桁の数字

## <a name="pattern"></a>パターン

オプションのハイフンとスラッシュを含む 9 桁:

- 2 桁の数字
- ハイフン (省略可能)
- 3 桁
- スラッシュ (省略可能)
- 4 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_austria_eu_tax_file_number` がパターンに一致するコンテンツを検出した。
- `Keywords_austria_eu_tax_file_number` のキーワードを検出した。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 関数 `Func_austria_eu_tax_file_number` がパターンに一致するコンテンツを検出した。

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

## <a name="keywords"></a>キーワード

### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

- österreich
- st.nr。
- steuernummer
- tax ID
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
- 税番号