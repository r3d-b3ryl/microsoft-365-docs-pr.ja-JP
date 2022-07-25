---
title: すべての物理アドレス エンティティ定義
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
description: すべての物理アドレスの機密情報の種類エンティティ定義。
ms.openlocfilehash: 3d8b40d6362c2a39525959467f524bc83c7cc3c8
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997027"
---
# <a name="all-physical-addresses"></a>すべての住所

すべての物理アドレスはバンドルされたエンティティ SIT であり、サポートされているすべての国/地域からの物理アドレスに関連するパターンを検出します。

## <a name="format"></a>フォーマット

各種

## <a name="pattern"></a>パターン

各種

## <a name="checksum"></a>チェックサム

不要

## <a name="description"></a>説明

住所の照合は、人が住所として識別する文字列と一致するように設計されています。 これを行うには、いくつかのプライマリ リソースを使用します。

- 入植地、郡、地域の辞書。
- 道路、通り、または通りなどの道路サフィックスの辞書。
- 郵便番号のパターン。
- アドレス形式のパターン。

リソースは国ごとに異なります。 主なリソースは、特定の国で使用されるアドレス形式のパターンです。 可能な限り多くのアドレスが一致するように、さまざまな形式が選択されます。 これらの形式を使用すると、住所が郵便番号を省略したり、都市名を省略したり、番地のサフィックスのない通りを持つ場合など、柔軟に対応できます。 いずれの場合も、このような一致は、一致の信頼度を高めるために使用されます。

パターンは、一般的な場所ではなく、個々の単一のアドレスに一致するように設計されています。 そのため *、Redmond、WA 98052、**Main Street、Albuquerque* などの文字列は一致しません。

## <a name="contains"></a>Contains

このバンドルされた名前付きエンティティ SIT には、次の個別の SIT が含まれています。

- オーストラリアの物理アドレス
- オーストリアの住所
- ベルギーの物理的な住所
- ブラジルの住所
- ブルガリアの住所
- カナダの住所
- クロアチアの住所
- キプロスの住所
- チェコ共和国の住所
- デンマークの住所
- エストニアの住所
- フィンランドの住所
- フランスの住所
- ドイツの住所
- ギリシャの住所
- ハンガリーの物理アドレス
- アイスランドの住所
- アイルランドの住所
- イタリアの住所
- ラトビアの住所
- リヒテンシュタインの住所
- リトアニアの物理アドレス
- ルクセンブルクの物理アドレス
- マルタの住所
- オランダの物理アドレス
- ニュージーランドの住所
- ノルウェーの住所
- ポーランドの住所
- ポルトガルの住所
- ルーマニアの住所
- スロバキアの物理アドレス
- スロベニアの物理アドレス
- スペインの物理アドレス
- スウェーデンの物理アドレス
- スイスの住所
- トルコの住所
- 英国の物理アドレス
- 米国物理アドレス

## <a name="supported-languages"></a>サポートされている言語

- 英語
- ブルガリア語
- 中国語
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