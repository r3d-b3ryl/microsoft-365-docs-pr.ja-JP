---
title: Azure SAS エンティティ定義
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
description: Azure SAS の機密情報の種類のエンティティ定義。
ms.openlocfilehash: c7d63497a94204b77f83c5b357700311bf332e8c
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996757"
---
# <a name="azure-sas"></a>Azure の SAS

## <a name="format"></a>フォーマット

文字列 `sig` の後に、次のパターンで説明されている文字と文字列が続きます。

## <a name="pattern"></a>パターン

- 文字列 `sig`
- 0 から 2 つの空白文字
- 等号 (=)
- 0 から 2 つの空白文字
- 小文字または大文字、数字、またはパーセント記号 (%) である 43 ~ 53 文字の任意の組み合わせ
- 文字列 `%3d`
- 小文字、大文字、数字、またはパーセント記号 (%) ではない任意の文字

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `CEP_Regex_AzureSAS` は、パターンに一致するコンテンツを検索します。

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```
