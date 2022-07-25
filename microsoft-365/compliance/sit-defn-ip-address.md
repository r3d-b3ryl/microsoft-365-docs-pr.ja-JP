---
title: IP アドレス エンティティ定義
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
description: IP アドレスの機密情報の種類のエンティティ定義。
ms.openlocfilehash: 19c883cccdc45682514bcd553f1b8e4a09d90e12
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996932"
---
# <a name="ip-address"></a>IP アドレス

## <a name="format"></a>フォーマット

### <a name="ipv4"></a>IPv4:
IPv4 アドレスの書式設定された (ピリオド) バージョンと書式設定されていない (ピリオドなし) バージョンを考慮する複雑なパターン

### <a name="ipv6"></a>IPv6:
書式設定された IPv6 番号を考慮する複雑なパターン (コロンを含む)

## <a name="pattern"></a>パターン

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

IPv6 の場合、DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_ipv6_address` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_ipaddress` 見つかりません。

IPv4 の場合、DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_ipv4_address` は、パターンに一致するコンテンツを検索します。
- `Keyword_ipaddress` のキーワードを検出した。

IPv6 の場合、DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_ipv6_address` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_ipaddress` 見つかりません。

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (このキーワードでは大文字と小文字が区別されます)
- ip address
- ip addresses
- internet protocol
- IP-כתובת ה