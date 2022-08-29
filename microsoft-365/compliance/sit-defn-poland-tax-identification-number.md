---
title: ポーランドの税識別番号エンティティ定義
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
description: ポーランドの税識別番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 38909e64a5ab3d4756d9cc11e64041076e6ca7da
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367995"
---
# <a name="poland-tax-identification-number"></a>ポーランドの納税者番号

## <a name="format"></a>フォーマット

スペースまたは区切り記号のない 11 桁の数字

## <a name="pattern"></a>パターン

11 桁の数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、高い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_poland_eu_tax_file_number` がパターンに一致するコンテンツを検出した。
- `Keywords_poland_eu_tax_file_number` のキーワードを検出した。

```xml
      <!-- Poland Tax Identification Number -->
      <Entity id="1ff28b4d-40f2-49e9-b677-9606a88e2bca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

- ニップ#
- ニップ
- numer identyfikacji podatkowej
- numeridentyfikacjipodatkowej#
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
- vat ID#
- vat ID
- vat no
- vat 番号
- vatid#
- vatid
- vatno#