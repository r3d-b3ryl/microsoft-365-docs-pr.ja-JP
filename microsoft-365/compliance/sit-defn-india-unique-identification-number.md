---
title: インド固有識別 (Aadhaar) 番号エンティティ定義
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
description: インド固有識別 (Aadhaar) 番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 37f0182050e4602ebeda9d9e5376df18b7971571
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996947"
---
# <a name="india-unique-identification-aadhaar-number"></a>インドの固有識別 (Aadhaar) 番号

## <a name="format"></a>フォーマット

省略可能なスペースまたはハイフンを含む 12 桁の数字

## <a name="pattern"></a>パターン

12 桁の数字:

- 0 または 1 ではない数字
- 3 桁の数字
- スペースまたはハイフン 1 つ (省略可能) 
- 4 桁の数字
- スペースまたはハイフン 1 つ (省略可能) 
- 最後の数字(チェック ディジット)

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_india_aadhaar` がパターンに一致するコンテンツを検出した。
- `Keyword_india_aadhar` のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_india_aadhaar` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar

- aadhaar
- aadhar
- aadhar#
- uid
- आधार
- uidai