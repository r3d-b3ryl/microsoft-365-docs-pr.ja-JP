---
title: オーストリア ID カード エンティティ定義
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
description: オーストリア ID カードの機密情報の種類エンティティ定義。
ms.openlocfilehash: 5a7cae0eabfa179bda83a09dc6a70a3e6e5048a6
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997232"
---
# <a name="austria-identity-card"></a>オーストリアの ID カード

この機密情報の種類は、次の場合にのみ使用できます。

- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- データ ライフサイクル管理
- レコード管理
- Microsoft Defender for Cloud Apps

## <a name="format"></a>フォーマット

文字、数字、特殊文字の 24 文字の組み合わせ

## <a name="pattern"></a>パターン

24 文字:

- 22 文字 (大文字と小文字は区別されません)、数字、円記号、スラッシュ、またはプラス記号

- 2 文字 (大文字と小文字は区別されません)、数字、円記号、スラッシュ、プラス記号、または等号

## <a name="checksum"></a>チェックサム

該当なし

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_austria_eu_national_id_card` は、パターンに一致するコンテンツを検索します。
- `Keywords_austria_eu_national_id_card` のキーワードを検出した。

```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- ID 番号
- national id
- personalausweis republik österreich