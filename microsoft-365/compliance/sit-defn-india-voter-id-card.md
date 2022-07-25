---
title: インドの投票者 ID カード エンティティ定義
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
description: インドの投票者 ID カードの機密情報の種類エンティティ定義。
ms.openlocfilehash: 4556824999f44f6407e996fbca7c82e79fe2cafc
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996237"
---
# <a name="india-voter-id-card"></a>インドの投票者 ID カード

## <a name="format"></a>フォーマット

10 文字の英数字パターン

## <a name="pattern"></a>パターン

10 桁の文字または数字:

- 3 文字
- 7 桁

## <a name="checksum"></a>チェックサム

不要

## <a name="definition"></a>定義

DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に中程度の確証を持ってそれがこの種類の機密情報であると特定します。

- 正規表現 `Regex_india_voter_id_card` は、パターンに一致するコンテンツを検索します。
- `Keyword_india_voter_id_card` のキーワードを検出した。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 正規表現 `Regex_india_voter_id_card` は、パターンに一致するコンテンツを検索します。

```xml
      <!-- India Voter Id Card  -->
        <Entity id="646d643f-5228-4408-acc8-f2e81a6df897" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
           <Pattern confidenceLevel="75">
             <IdMatch idRef="Regex_india_voter_id_card" />
             <Match idRef="Keyword_india_voter_id_card" />
            </Pattern>
           <Pattern confidenceLevel="65">
              <IdMatch idRef="Regex_india_voter_id_card" />
            </Pattern>
        </Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_india_voter_id_card"></a>Keyword_india_voter_id_card

- 有権者
- voterid
- votercard
- voteridcard
- 電子写真付き ID カード
- 叙事詩
- ECI
- election commmision