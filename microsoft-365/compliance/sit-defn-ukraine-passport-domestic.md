---
title: ウクライナパスポートの国内エンティティ定義
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
description: ウクライナパスポート国内の機密情報の種類エンティティ定義。
ms.openlocfilehash: 6ef59f90149b87a726377100f8dc4bf14f267ccf
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996587"
---
# <a name="ukraine-passport-domestic"></a>ウクライナのパスポート国内番号

この機密情報の種類は、次の場合にのみ使用できます。

- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- データ ライフサイクル管理
- レコード管理
- Microsoft Defender for Cloud Apps

## <a name="format"></a>フォーマット

9 桁

## <a name="pattern"></a>パターン

9 桁

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_Ukraine_Passport_Domestic` は、パターンに一致するコンテンツを検索します。
- `Keyword_Ukraine_Passport_Domestic` のキーワードを検出した。

```xml
      <!-- Ukraine Passport Domestic -->
      <Entity id="1817a540-221f-4459-9202-3bd78b81d803" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_Ukraine_Passport_Domestic"/>
          <Match idRef="Keyword_Ukraine_Passport_Domestic"/>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_ukraine_passport_domestic"></a>Keyword_ukraine_passport_domestic

- ウクライナのパスポート
- passport number
- passport no
- паспорт України
- номер паспорта
- персональний