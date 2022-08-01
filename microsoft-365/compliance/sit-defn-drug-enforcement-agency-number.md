---
title: ドラッグ エンフォースメント エージェンシー (DEA) 番号エンティティ定義
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
description: ドラッグ エンフォースメント エージェンシー (DEA) 番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 7b1ade056621f619d8be0293708dd51cfc2e85dd
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66995822"
---
# <a name="drug-enforcement-agency-dea-number"></a>麻薬取締局 (DEA) 番号

## <a name="format"></a>フォーマット

2 文字の後に 7 桁の数字が続く

## <a name="pattern"></a>パターン

パターンには、以下のすべてが含まれる必要があります。

- この一連の文字から 1 文字 (大文字と小文字は区別されません): A/B/F/G/M/P/R(登録者コードです)
- 1 文字 (大文字と小文字は区別されません)、登録者の姓または数字 '9' の最初の文字です。
- 7 桁、最後がチェック 桁

## <a name="checksum"></a>チェックサム

はい

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_dea_number` がパターンに一致するコンテンツを検出した。
- キーワードが `Keyword_dea_number` 見つかりました
- チェックサムが渡される。

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 関数 `Func_dea_number` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
    <!-- DEA Number -->
    <Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_dea_number" />
      </Pattern>
      <Version minEngineVersion="15.20.1207.000" maxEngineVersion="15.20.3134.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
        </Pattern>
      </Version>
      <Version minEngineVersion="15.20.3135.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
          <Match idRef="Keyword_dea_number" />
        </Pattern>
      </Version>
    </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_dea_number"></a>Keyword_dea_number

- Dea
- Dea#
- ドラッグフォースメントの管理
- ドラッグエンフォースメントエージェンシー