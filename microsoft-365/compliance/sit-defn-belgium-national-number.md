---
title: ベルギーの国番号エンティティ定義
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
description: ベルギー国内番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 5fc644a8dcb275cba2986139dfdd16444e47c218
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950811"
---
# <a name="belgium-national-number"></a>ベルギーの国内番号

## <a name="format"></a>フォーマット

11 桁の数字とオプションの区切り記号

## <a name="pattern"></a>パターン

11 の数字と区切り文字:

- YY 形式の 6 桁の数字と 2 つの省略可能なピリオド。生年月日の MM.DD
- ドット、ダッシュ、スペースからの区切り記号 (省略可能)
- 3 桁の連続した数字 (男性の場合は奇数、女性の場合も奇数)
- ドット、ダッシュ、スペースからの区切り記号 (省略可能)
- 2 つのチェック 数字

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという中程度の信頼を持っています。

- この関数 `Func_belgium_national_number` は、パターンに一致するコンテンツを検索します。
- キーワードが `Keyword_belgium_national_number` 見つかりました。
- チェックサムが渡される。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- この関数 `Func_belgium_national_number` は、パターンに一致するコンテンツを検索します。
- チェックサムが渡される。

```xml
<!-- Belgium National Number -->
       <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_national_number" />
          <Match idRef="Keyword_belgium_national_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_belgium_national_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- belasting aantal
- Bnn#
- Bnn
- carte d'identité
- idant national
- identifiantnational#
- identificatie
- 識別
- identifikation
- identifikationsnummer
- identifizie
- identité
- identiteit
- identiteitskaart
- Id
- 碑文
- 国内番号
- 国内登録
- nationalnumber#
- nationalnumber
- Nif#
- Nif
- numéro d'assuré
- numéro de registre national
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- numéro national
- numéronational#
- 個人 ID 番号
- personalausweis
- personalidnumber#
- registratie
- 登録
- registrationsnumme
- registrie
- social security number
- Ssn#
- Ssn
- steuernummer
- tax id
- 税の識別番号なし
- 税識別番号
- tax no#
- tax no
- 税番号
- 税登録番号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- tin ID
- tin no
- 錫#