---
title: 香港 ID カード (HKID) 番号エンティティ定義
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
description: 香港 ID カード (HKID) 番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 6d382d50334036aaa0a7ff8fce698246b1e5ccb0
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997657"
---
# <a name="hong-kong-identity-card-hkid-number"></a>香港の ID カード (HKID) 番号

## <a name="format"></a>フォーマット

8 ～ 9 桁の文字と数字の組み合わせ、最後の文字はかっこで囲むことも可能

## <a name="pattern"></a>パターン

8 ～ 9 桁の文字の組み合わせ:

- 1 ~ 2 文字 (大文字と小文字は区別されません)
- 6 桁の数字
- 省略可能な領域
- チェック文字 (任意の数字または文字 A) (必要に応じてかっこで囲む)

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_hong_kong_id_card` がパターンに一致するコンテンツを検出した。
- `Keyword_hong_kong_id_card` のキーワードを検出した。
- チェックサムが渡される。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 関数 `Func_hong_kong_id_card` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- 香港 ID カード
- HKIDC
- id card
- Identity card
- hk ID カード
- 香港 ID
- 香港身份證
- 香港永久性居民身份證
- 身份證
- 身份証
- 身分證
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證
- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證
- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証