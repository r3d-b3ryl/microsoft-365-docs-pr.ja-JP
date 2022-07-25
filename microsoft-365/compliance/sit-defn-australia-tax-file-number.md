---
title: オーストラリアの税ファイル番号エンティティ定義
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
description: オーストラリアの税ファイル番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 155bdbd2142d0c6c097907b0ab651ff74cfac46d
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997247"
---
# <a name="australia-tax-file-number"></a>オーストラリアの納税者番号

## <a name="format"></a>フォーマット

8 ~ 9 桁

## <a name="pattern"></a>パターン

通常、8 から 9 桁の数字には、次のようにスペースが表示されます。

- 3 桁
- 省略可能な領域
- 3 桁
- 省略可能な領域
- 最後の数字がチェック 桁である 2 ~ 3 桁の数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 Func_australian_tax_file_number がパターンに一致するコンテンツを検出した。
- Keyword_Australia_Tax_File_Number または Keyword_number_exclusions のキーワードを検出しなかった。
- チェックサムが渡される。

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_australia_tax_file_number"></a>Keyword_australia_tax_file_number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number
- Tfn
