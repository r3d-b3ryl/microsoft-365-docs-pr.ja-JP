---
title: 国際銀行口座番号 (IBAN) エンティティ定義
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
description: 国際銀行口座番号 (IBAN) の機密情報の種類エンティティ定義。
ms.openlocfilehash: 739c0a1fd90da1da817f46019cd1023be8ab27a3
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996702"
---
# <a name="international-banking-account-number-iban"></a>国際銀行口座番号 (IBAN)

## <a name="format"></a>フォーマット

国コード (2 文字) とチェック数字 (2 桁) と bban 番号 (最大 30 文字)

## <a name="pattern"></a>パターン

パターンには、以下のすべてが含まれる必要があります。

- 2 文字の国コード
- 2 桁のチェック 桁 (続いて省略可能なスペース)
- 4 文字または数字の 1 ~ 7 グループ (スペースで区切ることができます)
- 1 ～ 3 個の文字または数字

各国の形式は若干異なります。 IBAN の機密情報の種類は、次の 60 か国を対象とします。

- ad
- Ae
- アル
- 場所
- az
- Ba
- be
- bg
- Bh
- Ch
- Cr
- cy
- Cz
- de
- Dk
- do
- ee
- es
- fi
- fo
- fr
- Gb
- ge
- Gi
- gl
- Gr
- hr
- hu
- Ie
- イリノイ
- is
- it
- Kw
- カザフスタン
- lb
- 李
- lt
- Lu
- lv
- Mc
- md
- me
- mk
- mr
- mt
- Mu
- nl
- no
- pl
- pt
- ro
- Rs
- Sa
- se
- si
- sk
- Sm
- テネシー
- tr
- Vg

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_iban` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

なし