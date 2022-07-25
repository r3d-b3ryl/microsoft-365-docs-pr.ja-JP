---
title: ニュージーランドのソーシャル ウェルフェア番号エンティティ定義
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
description: ニュージーランドのソーシャル ウェルフェア番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 9885956e7011f2c52a8b78d4e03822f8201c1b3a
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997497"
---
# <a name="new-zealand-social-welfare-number"></a>ニュージーランドの社会福祉番号

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

- 3 桁
- オプションのハイフン
- 3 桁
- オプションのハイフン
- 3 桁

## <a name="checksum"></a>チェックサム

はい

### <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_newzealand_social_welfare_number` がパターンに一致するコンテンツを検出した。
- `Keywords_newzealand_social_welfare_number` のキーワードを検出した。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 関数 `Func_newzealand_social_welfare_number` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Newzealand Social Welfare Number -->
      <Entity id="20f3c48d-4ac1-4cd2-86bd-34ecc1826e9d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
          <Match idRef="Keywords_newzealand_social_welfare_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
        </Pattern>
      </Entity>
    </Version>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- ソーシャル ウェルフェア#
- ソーシャル ウェルフェア#
- ソーシャル ウェルフェア No.
- 社会保障番号
- swn#