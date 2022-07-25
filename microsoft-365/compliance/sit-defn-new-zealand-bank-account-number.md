---
title: ニュージーランドの銀行口座番号エンティティ定義
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
description: ニュージーランドの銀行口座番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: b33eeb1e83f5efc9dd805c9ea036c6f30de600a0
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996182"
---
# <a name="new-zealand-bank-account-number"></a>ニュージーランド銀行口座番号

この機密情報の種類は、次の場合にのみ使用できます。

- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- データ ライフサイクル管理
- レコード管理
- Microsoft Defender for Cloud Apps

## <a name="format"></a>フォーマット

省略可能な区切り記号を含む 14 桁から 16 桁のパターン

## <a name="pattern"></a>パターン

省略可能な区切り記号を含む 14 桁から 16 桁のパターン:

- 2 桁の数字
- オプションのハイフンまたはスペース
- 3 ~ 4 桁
- オプションのハイフンまたはスペース
- 7 桁
- オプションのハイフンまたはスペース
- 2 ~ 3 桁
- オプションのハイフンまたはスペース

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_new_zealand_bank_account_number` がパターンに一致するコンテンツを検出した。
- `Keywords_new_zealand_bank_account_number` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_new_zealand_bank_account_number` がパターンに一致するコンテンツを検出した。

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zFealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- account number
- 銀行口座
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr