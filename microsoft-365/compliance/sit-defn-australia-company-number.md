---
title: オーストラリアの会社番号エンティティ定義
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
description: オーストラリアの会社番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: a10addd7dee6bc481adbf9edf1380cdedf09bdd0
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995622"
---
# <a name="australia-company-number"></a>オーストラリアの会社番号

この機密情報の種類は、次の場合にのみ使用できます。

- データ損失防止ポリシー
- 通信コンプライアンス ポリシー
- データ ライフサイクル管理
- レコード管理
- Microsoft Defender for Cloud Apps

## <a name="format"></a>フォーマット

区切り記号を持つ 9 桁の数字

## <a name="pattern"></a>パターン

区切り記号を含む 9 桁の数字:

- 3 桁
- スペース
- 3 桁
- スペース
- 3 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- この関数Func_Australian_Company_Number、パターンに一致するコンテンツを検索します。
- Keyword_Australian_Company_Numberのキーワードが見つかりました。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- この関数Func_Australian_Company_Number、パターンに一致するコンテンツを検索します。

```xml
      <!-- Australia Company Number -->
      <Entity id="b1fba4f7-7b3e-4bb9-8f9a-9366df604dbb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Australian_Company_Number" />
          <Match idRef="Keyword_Australian_Company_Number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_Australian_Company_Number" />
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>キーワード

### <a name="keyword_australia_company_number"></a>Keyword_australia_company_number

- Cna
- オーストラリアの会社なし
- オーストラリアの会社なし#
- オーストラリアの会社番号
- オーストラリアの会社なし
- オーストラリアの会社なし#
- オーストラリアの会社番号
