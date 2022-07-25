---
title: 病気の国際分類 (ICD-9-CM) エンティティ定義
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
description: 病気 (ICD-9-CM) の機密情報の種類エンティティ定義の国際分類。
ms.openlocfilehash: 1aceb3864638f2fa8658d4c88dc47812910dd588
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996742"
---
# <a name="international-classification-of-diseases-icd-9-cm"></a>国際疾病分類 (ICD-9-CM)

## <a name="format"></a>フォーマット

Dictionary

## <a name="pattern"></a>パターン

キーワード

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- `Dictionary_icd_9_updated` のキーワードを検出した。
- `Dictionary_icd_9_codes` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- `Dictionary_icd_9_updated` のキーワードを検出した。

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

国際[病気分類、9 番目の改訂、臨床変更 (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605) に基づくキーワード 辞書の`Dictionary_icd_9_updated`用語。 この種類は、保険コードではなく、用語のみを検索します。

国際[病気分類、9 番目の改訂、臨床変更 (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605) に基づくキーワード 辞書の`Dictionary_icd_9_codes`用語。 この種類は、説明ではなく、保険コードのみを検索します。