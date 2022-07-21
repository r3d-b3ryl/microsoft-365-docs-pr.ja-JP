---
title: 英国。 国民保険番号 (NINO) エンティティ定義
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
description: 英国。 国民保険番号 (NINO) の機密情報の種類エンティティ定義。
ms.openlocfilehash: 44b41cf2c19d001e142ff527b431990ebd3c80c6
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950558"
---
# <a name="uk-national-insurance-number-nino"></a>英国。 国民保険番号 (NINO)

この機密情報の種類エンティティは、EU 国民識別番号の機密情報の種類に含まれています。 スタンドアロンの機密情報の種類エンティティとしても使用できます。

## <a name="format"></a>フォーマット

スペースまたはダッシュで区切られた 7 文字または 9 文字

## <a name="pattern"></a>パターン

次の 2 つのパターンが考えられます。

- 2 文字 (有効な NINO では、このプレフィックス内の特定の文字のみが使用されます。このパターンでは検証されます。大文字と小文字は区別されません)
- 6 桁
- 'A'、'B'、'C'、または 'D' (プレフィックスと同様に、サフィックスでは特定の文字のみが許可され、大文字と小文字は区別されません)

または

- 2 文字
- スペースまたはダッシュ
- 2 桁の数字
- スペースまたはダッシュ
- 2 桁の数字
- スペースまたはダッシュ
- 2 桁の数字
- スペースまたはダッシュ
- 'A'、'B'、'C'、または 'D' のいずれか

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- この関数 `Func_uk_nino` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_uk_nino` 見つかりました。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという中程度の信頼を持っています。

- この関数 `Func_uk_nino` は、パターンに一致するコンテンツを検索します。

```xml
    <!-- U.K. NINO -->
    <Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Match idRef="Keyword_uk_nino" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- national insurance number
- national insurance contributions
- protection act
- 保険
- social security number
- insurance application
- medical application
- social insurance
- medical attention
- social security
- great britain
- NI 番号
- NI いいえ。
- NI#
- NI#
- 保険#
- insurancenumber
- nationalinsurance#
- nationalinsurancenumber