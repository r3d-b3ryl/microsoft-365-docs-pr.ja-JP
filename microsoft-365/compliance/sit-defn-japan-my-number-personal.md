---
title: 日本の個人用マイ ナンバー エンティティ定義
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
description: 日本の個人用マイナンバー機密情報タイプ エンティティの定義。
ms.openlocfilehash: 343bc26e3310c4c8586a50b635ef3d5b2398967c
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67369810"
---
# <a name="japan-my-number---personal"></a>日本の個人用マイ ナンバー

## <a name="format"></a>フォーマット

12 桁の数字

## <a name="pattern"></a>パターン

12 桁の数字:

- 4 桁の数字
- 省略可能なスペース、ドット、またはハイフン
- 4 桁の数字
- 省略可能なスペース、ドット、またはハイフン
- 4 桁の数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、高い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_japanese_my_number_personal` がパターンに一致するコンテンツを検出した。
- `Keywords_japanese_my_number_personal` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、低い信頼度でそれがこの種類の機密情報であると特定します。

- 関数 `Func_japanese_my_number_personal` がパターンに一致するコンテンツを検出した。

```xml
      <!-- Japanese My Number – Personal -->
      <Entity id="98da8e66-7299-4ebd-9f82-c871ab37d3ef" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_personal" />
          <Match idRef="Keywords_japanese_my_number_personal" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_japanese_my_number_personal" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_japan_my_number_personal"></a>Keyword_japan_my_number_personal

- my number
- マイナンバー
- 個人番号
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 通知カード