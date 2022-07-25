---
title: 日本のドライバー ライセンス番号エンティティ定義
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
description: 日本の運転免許証番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 0c216f31482a0368db6f78e9c7ceb9583b1e8e13
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996487"
---
# <a name="japan-drivers-license-number"></a>日本の運転免許証番号

## <a name="format"></a>フォーマット

12 桁の数字

## <a name="pattern"></a>パターン

12 桁の連続する数字

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_jp_drivers_license_number` がパターンに一致するコンテンツを検出した。
- `Keyword_jp_drivers_license_number` のキーワードを検出した。

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_jp_drivers_license_number"></a>Keyword_jp_drivers_license_number

- driverlicense
- driverslicense
- driver'slicense
- driverslicenses
- driver'slicenses
- driverlicenses
- Dl#
- Dls#
- Lic#
- lics#
- 運転免許証
- 運転免許
- 免許証
- 免許
- 運転免許証番号
- 運転免許番号
- 免許証番号
- 免許番号
- 運転免許証ナンバー
- 運転免許ナンバー
- 免許証ナンバー
- 運転免許証
- 運転免許
- 免許証no
- 免許
- 運転経歴証明書番号
- 運転経歴証明書
- 運転免許証を使用します。
- 運転の場合は、次の方法を使用します。
- 免許証No.
- 免許を持つ必要があります。
- 運転免許証#
- 運転免許#
- 免許証#
- 免許#