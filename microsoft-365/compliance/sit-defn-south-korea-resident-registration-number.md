---
title: 韓国の居住者登録番号エンティティ定義
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
description: 韓国の居住者登録番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 94de2ebb31e8bd7a0d9c175e318e166da691bbca
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995425"
---
# <a name="south-korea-resident-registration-number"></a>韓国の住民登録番号

## <a name="format"></a>フォーマット

ハイフンを 1 つ含む 13 桁の数字

## <a name="pattern"></a>パターン

13 桁の数字:

- YYMMDD 形式の 6 桁 (生年月日)
- ハイフン
- 世紀と性別で決まる 1 桁の数字
- 4 桁のリージョンオブバース コード
- 前の数字が同一であるユーザーを区別するために使用される 1 桁
- チェック ディジット。

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_south_korea_resident_number` がパターンに一致するコンテンツを検出した。
- `Keyword_south_korea_resident_number` のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_south_korea_resident_number` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- National ID card
- Citizen's Registration Number
- Jumin deungnok beonho
- RRN
- 주민등록번호