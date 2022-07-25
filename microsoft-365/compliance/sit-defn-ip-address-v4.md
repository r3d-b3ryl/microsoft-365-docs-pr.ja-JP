---
title: IP アドレス v4 エンティティ定義
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
description: IP アドレス v4 の機密情報の種類のエンティティ定義。
ms.openlocfilehash: e145b4342c5b276b66d0ed463a2094b7ada47b01
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996942"
---
# <a name="ip-address-v4"></a>IP アドレス v4

## <a name="format"></a>フォーマット

IPv4 アドレスの書式設定された (ピリオド) バージョンと書式設定されていない (ピリオドなし) バージョンを考慮する複雑なパターン。

## <a name="pattern"></a>パターン

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_ipv4_address` は、パターンに一致するコンテンツを検索します。
- `Keyword_ipaddress` のキーワードを検出した。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_ipv4_address` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- IP Address v4-->
      <Entity id="a7dd5e5f-e7f9-4626-a2c6-86a8cb6830d2" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ipv4_address" />
          <Match idRef="Keyword_ipaddress" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ipv4_address" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (大文字と小文字が区別されます)
- ip address
- ip addresses
- internet protocol
- IP-כתובת ה