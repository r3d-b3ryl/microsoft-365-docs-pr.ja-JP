---
title: キプロスの税識別番号エンティティ定義
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
description: キプロスの税識別番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: fb24f1841483e48b6cfec5167772be13743297e0
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367601"
---
# <a name="cyprus-tax-identification-number"></a>キプロスの納税者番号

## <a name="format"></a>フォーマット

指定したパターンの 8 桁の数字と 1 文字

## <a name="pattern"></a>パターン

8 桁の数字と 1 文字:

- "0" または "9"
- 7 桁
- 1 文字 (大文字と小文字は区別されません)

## <a name="checksum"></a>チェックサム

該当なし

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、高い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_cyprus_eu_tax_file_number` がパターンに一致するコンテンツを検出した。
- `Keywords_cyprus_eu_tax_file_number` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_cyprus_eu_tax_file_number` がパターンに一致するコンテンツを検出した。

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

## <a name="keywords"></a>キーワード

### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

- tax id
- 税識別コード
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
- Tic#
- Tic
- tin ID
- tin no
- 錫#
- vergi kimlik kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού