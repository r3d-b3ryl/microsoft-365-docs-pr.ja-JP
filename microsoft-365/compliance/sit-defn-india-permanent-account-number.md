---
title: インドの永続アカウント番号 (PAN) エンティティ定義
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
description: インドの永続的なアカウント番号 (PAN) の機密情報の種類エンティティ定義。
ms.openlocfilehash: bf712e0949bba5f1e5396d61ff70f41b70ba579d
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995757"
---
# <a name="india-permanent-account-number-pan"></a>インドの永久口座番号 (PAN)

## <a name="format"></a>フォーマット

10 桁の文字または数字

## <a name="pattern"></a>パターン

10 桁の文字または数字:

- 3 文字 (大文字と小文字は区別されません)
- C、P、H、F、A、T、B、L、J、G の文字 (大文字と小文字は区別されません)
- 文字
- 4 桁の数字
- アルファベットチェックの数字である文字

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_india_permanent_account_number` は、パターンに一致するコンテンツを検索します。
- `Keyword_india_permanent_account_number` のキーワードを検出した。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 正規表現 `Regex_india_permanent_account_number` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- India Permanent Account Number -->
      <Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_india_permanent_account_number" />
          <Match idRef="Keyword_india_permanent_account_number" />
        </Pattern>
        <Version minEngineVersion="15.20.3520.000">
          <Pattern confidenceLevel="65">
            <IdMatch idRef="Regex_india_permanent_account_number" />
          </Pattern>
        </Version>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Permanent Account Number
- パン