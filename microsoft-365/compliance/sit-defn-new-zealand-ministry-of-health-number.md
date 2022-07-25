---
title: ニュージーランドの正常性番号エンティティ定義省
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
description: ニュージーランドの省の正常性番号の機密情報の種類のエンティティ定義。
ms.openlocfilehash: 62a7b181626d36930da36451ccd109ecc6d04812
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997507"
---
# <a name="new-zealand-ministry-of-health-number"></a>ニュージーランドの保健省番号

## <a name="format"></a>フォーマット

3 文字と 4 桁

## <a name="pattern"></a>パターン

- 'I' と 'O' を除く 3 文字 (大文字と小文字は区別されません)
- 4 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_new_zealand_ministry_of_health_number` がパターンに一致するコンテンツを検出した。
- `Keyword_nz_terms` のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_new_zealand_ministry_of_health_number` がパターンに一致するコンテンツを検出した。
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

## <a name="keywords"></a>キーワード

### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI
- New Zealand
- 国民健康指数
- NHI#
- 国民健康指数#