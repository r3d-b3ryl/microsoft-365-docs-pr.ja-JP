---
title: SWIFT コード エンティティ定義
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
description: SWIFT コードの機密情報の種類のエンティティ定義。
ms.openlocfilehash: b1bbadf8f2b56218a90eec1cfd2fac7d550efe0e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995404"
---
# <a name="swift-code"></a>SWIFT コード

## <a name="format"></a>フォーマット

4 文字の後に 5 ~ 31 文字または数字が続く

## <a name="pattern"></a>パターン

4 文字の後に 5 ~ 31 文字または数字を続けます。

- 4 文字の銀行コード (大文字と小文字は区別されません)
- 省略可能な領域
- 4 ～ 28 個の文字または数字 (基本的銀行口座番号 (BBAN))
- 省略可能な領域
- 1 ~ 3 文字または数字 (BBAN の残りの部分)

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_swift` は、パターンに一致するコンテンツを検索します。
- `Keyword_swift` のキーワードを検出した。

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_swift"></a>Keyword_swift

- international organization for standardization 9362
- iso 9362
- iso9362
- スウィフト#
- swiftcode
- swiftnumber
- swiftroutingnumber
- swift code
- swift number #
- swift routing number
- bic number
- bic code
- bic #
- ビックカメラ#
- bank identifier code
- Organisation internationale de normalisation 9362
- rapide #
- code SWIFT
- le numéro de swift
- swift numéro d'acheminement
- le numéro BIC
- \# ビックカメラ
- code identificateur de banque
- SWIFT コード
- SWIFT 番号
- BIC 番号
- BIC コード
- SWIFT コード
- SWIFT 番号
- BIC 番号
- BIC コード
- 金融機関識別コード
- 金融機関コード
- 銀行コード