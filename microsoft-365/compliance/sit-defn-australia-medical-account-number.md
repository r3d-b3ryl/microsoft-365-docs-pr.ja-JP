---
title: オーストラリアの医療アカウント番号エンティティ定義
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
description: オーストラリアの医療アカウント番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: c17de71ef0c16b5c14ba118c66ae0d9274ce4468
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996157"
---
# <a name="australia-medical-account-number"></a>オーストラリアの医療口座番号

## <a name="format"></a>フォーマット

10 ～ 11 桁の数字

## <a name="pattern"></a>パターン

10 ～ 11 桁の数字:

- 最初の桁は 2 ～ 6 のいずれか
- 9 桁目はチェック ディジット
- 10 桁目は発行桁
- 11 桁目 (省略可能) は個々の番号です

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。
- Keyword_Australia_Medical_Account_Number のキーワードを検出した。
- チェックサムが渡される。

```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_australia_medical_account_number"></a>Keyword_Australia_Medical_Account_Number

- bank account details
- medicare payments
- mortgage account
- bank payments
- information branch
- credit card loan
- department of human services
- local service
- メディケア
