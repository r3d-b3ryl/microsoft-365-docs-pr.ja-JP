---
title: インドネシア ID カード (KTP) 番号エンティティ定義
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
description: インドネシア ID カード (KTP) 番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: d70e6ca902c6246e6faa67a91c5b52ae65e4fd47
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995472"
---
# <a name="indonesia-identity-card-ktp-number"></a>インドネシアの身分証明書 (KTP) 番号

## <a name="format"></a>フォーマット

省略可能なピリオドを含む 16 桁の数字

## <a name="pattern"></a>パターン

16 桁の数字:

- 2 桁の行政区コード 
- ピリオド 1 つ (省略可能) 
- 2 桁の行政区または市コード 
- 2 桁の分区コード 
- ピリオド 1 つ (省略可能) 
- DDMMYY 形式の 6 桁 (生年月日)
- ピリオド 1 つ (省略可能) 
- 4 桁の数字

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 正規表現 `Regex_indonesia_id_card` は、パターンに一致するコンテンツを検索します。
- `Keyword_indonesia_id_card` のキーワードを検出した。

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk
- Nomor Induk Kependudukan