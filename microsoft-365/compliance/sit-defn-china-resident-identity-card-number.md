---
title: 中国居住者 ID カード (PRC) 番号エンティティ定義
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
description: 中国常駐 ID カード (PRC) 番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 9ab0f1af6de2c8ffdcb835824e1559ab1a574718
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995902"
---
# <a name="china-resident-identity-card-prc-number"></a>中国の居民身分証明書 (PRC) 番号

## <a name="format"></a>フォーマット

18 桁の数字

## <a name="pattern"></a>パターン

18 桁の数字:

- アドレス コードである 6 桁の数字
- YYYYMMDD 形式の 8 桁 (生年月日)
- 注文コードである 3 桁の数字
- チェック ディジットである 1 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_china_resident_id` がパターンに一致するコンテンツを検出した。
- `Keyword_china_resident_id` のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_china_resident_id` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

## <a name="keyword_china_resident_id"></a>Keyword_china_resident_id

- Resident Identity Card
- PRC
- National Identification Card
- 身份证
- 居民 身份证
- 居民身份证
- 鉴定
- 身分證
- 居民 身份證
- 鑑定