---
title: ABA ルーティング番号エンティティ定義
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
description: ABA ルーティング番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 5efc835b5d5dced7fbfe9a0b1ce7c59b89b60ac0
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996507"
---
# <a name="aba-routing-number"></a>ABA ルーティング番号

## <a name="format"></a>フォーマット

書式設定または書式設定されていないパターンである可能性がある 9 桁の数字

## <a name="pattern"></a>パターン

- 00-12、21-32、61-72、または 80 の範囲の 2 桁
- 2 桁の数字
- オプションのハイフン
- 4 桁
- オプションのハイフン
- 数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという中程度の信頼を持っています。

- 関数 Func_aba_routing がパターンに一致するコンテンツを検出した。
- Keyword_ABA_Routing のキーワードを検出した。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 関数 Func_aba_routing がパターンに一致するコンテンツを検出した。

```xml
    <!-- ABA Routing Number -->
    <Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_aba_routing" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- aba number
- Aba#
- Aba
- abarouting#
- abaroutingnumber
- americanbankassociationrouting#
- americanbankassociationroutingnumber
- bankrouting#
- bankroutingnumber
- ルーティング#
- ルーティングなし
- ルーティング番号
- routing transit number
- ルーティング#
- RTN
