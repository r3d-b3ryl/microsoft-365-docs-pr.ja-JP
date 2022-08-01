---
title: インド GST 番号エンティティ定義
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
description: インド GST Number の機密情報の種類エンティティ定義。
ms.openlocfilehash: 19d51294b8ff53b53bceba1a047976802359f09e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995762"
---
# <a name="india-gst-number"></a>インドの GST 番号

## <a name="format"></a>フォーマット

15 文字の英数字パターン

## <a name="pattern"></a>パターン

15 文字または数字:

- 有効な状態コードを表す 2 桁の数字
- 省略可能なスペースまたはダッシュ
- 永続アカウント番号 (PAN) を表す 10 文字
- 1 文字または 1 桁
- 省略可能なスペースまたはダッシュ
- 1 文字 'z' または 'Z'
- 省略可能なスペースまたはダッシュ
- 1 つのチェック ディジット

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_india_gst_number` がパターンに一致するコンテンツを検出した。
- `Keyword_india_gst_number` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_india_gst_number` がパターンに一致するコンテンツを検出した。

```xml
    <!-- India GST number  -->
      <Entity id="9f5a721c-2fd2-446a-a27e-0c02fbe4630c" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_india_gst_number" />
          <Match idRef="Keyword_india_gst_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_india_gst_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_india_gst_number"></a>Keyword_india_gst_number

- Gst
- gstin
- 商品とサービスの税金
- 商品とサービス税