---
title: Azure Storage アカウント キー (汎用) エンティティ定義
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
description: Azure Storage アカウント キー (汎用) 機密情報の種類エンティティ定義。
ms.openlocfilehash: 88139dfe26e654e664d74e8543ea791fd171da63
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996422"
---
# <a name="azure-storage-account-key-generic"></a>Azure Storage のアカウント キー (一般)

## <a name="format"></a>フォーマット

86 個の小文字または大文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ。前または後に、下のパターンで説明されている文字が続きます。

## <a name="pattern"></a>パターン

- 0 から記号 (>)、apostrophe (')、等号 (=)、引用符 (")、または数値記号 (#)
- 小文字または大文字、数字、スラッシュ (/)、またはプラス記号 (+) である 86 文字の任意の組み合わせ
- 2 つの等号 (=)

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `CEP_Regex_AzureStorageAccountKeyGeneric` は、パターンに一致するコンテンツを検索します。

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```