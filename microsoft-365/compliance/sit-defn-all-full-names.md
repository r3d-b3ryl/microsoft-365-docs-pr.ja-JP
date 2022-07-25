---
title: すべてのフルネーム エンティティ定義
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
description: すべてのフルネームの機密情報の種類のエンティティ定義。
ms.openlocfilehash: 727448848dbc3a4ea46b83ec404b4c9151ea192e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997212"
---
# <a name="all-full-names"></a>すべての氏名

すべての完全な名前はバンドルされた名前付きエンティティです。 サポートされているすべての国/地域 (オーストラリア、中国、日本、米国、EU 内の国を含む) のユーザーの完全な名前を検出します。 この SIT を使用して、完全な名前と一致する可能性のあるすべての一致を検出します。

## <a name="format"></a>フォーマット

各種。

## <a name="pattern"></a>パターン

各種。

## <a name="checksum"></a>チェックサム

いいえ。

## <a name="description"></a>説明

この名前付きエンティティ SIT は、人間が信頼度の高い名前として識別する個人名と一致します。 たとえば、特定の名前で構成される文字列が見つかり、その後にファミリ名が続く場合、一致は高い信頼度で行われます。 次の 3 つのプライマリ リソースが使用されます。

- 指定された名前のディクショナリ。
- ファミリ名のディクショナリ。
- 名前の形成方法のパターン。

3 つのリソースは国ごとに異なります。  *文字列 Olivia Wilson* は一致をトリガーします。 一般的な特定の名前/ファミリ名には、まれな名前よりも高い信頼度が与えられます。 ただし、このパターンでは部分一致も許可されます。 ディクショナリから指定された名前が見つかり、その後にディクショナリ内にないファミリ名が続く場合は、部分一致がトリガーされます。 たとえば、 *TomasRich は* 部分一致をトリガーします。 部分一致は信頼度が低くなります。

さらに、人間が名前の指標として見るパターンも、適切な信頼度と一致します。 *O. Wilson*、*O.P. Wilson*、*Dr. O. P. Wilson*、*Wilson、O.P. と同様です。* または *T.Rich, Jr.* は一致します。

## <a name="supported-languages"></a>サポートされている言語

- 英語
- ブルガリア語
- クロアチア語
- チェコ語
- デンマーク語
- エストニア語
- フィンランド語
- フランス語
- ドイツ語
- ハンガリー語
- アイスランド語
- アイルランド語
- イタリア語
- 日本語
- ラトビア語
- リトアニア語
- マルタ語
- オランダ語
- ノルウェー語
- ポーランド語
- ポルトガル語
- ルーマニア語
- スロバキア語
- スロベニア語
- スペイン語
- スウェーデン語
- トルコ語