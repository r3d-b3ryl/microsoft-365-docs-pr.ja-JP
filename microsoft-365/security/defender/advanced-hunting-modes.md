---
title: Microsoft 365 Defenderでの捜索のためのガイド付きモードと高度なモードの間で選択する
description: 高度な捜索ではクエリを最初から記述できますが、Microsoft 365 Defenderでのガイド付きハンティングには KQL の知識は必要ありません。
keywords: ガイドモード, 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, カスタム検出, スキーマ, kusto
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: f94ef320b24fe95d1e08e7deafff85a18d6010b1
ms.sourcegitcommit: 7374c7b013890744d74e5214f7f8d69ca7874466
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2022
ms.locfileid: "67406791"
---
# <a name="choose-between-guided-and-advanced-modes-to-hunt-in-microsoft-365-defender"></a>ガイド付きモードと詳細モードの中から選択して、Microsoft 365 Defenderでハントします

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

**高度なハンティング** ページを見つけるには、Microsoft 365 Defenderの左側のナビゲーション バーに移動し、[高度 **なハンティング****のハンティング** > ] を選択します。 ナビゲーション バーが折りたたまれている場合は、ハンティング アイコンのハンティング アイコン ![を選択します](../../media/guided-hunting/hunting-icon.png)。 

**高度なハンティング** ページでは、次の 2 つのモードがサポートされています。
- **ガイド モード** – クエリ ビルダーを使用してクエリを実行する
- **詳細モード** – Kusto 照会言語 (KQL) を使用してクエリ エディターを使用してクエリを実行する

2 つのモードの主な違いは、ガイド モードでは、データベースに対するクエリを実行するために KQL を知る必要 *がない* のに対し、高度なモードでは KQL の知識が必要です。 

ガイドモードには、使用可能なフィルターと条件を含むドロップダウン メニューを使用してクエリを作成する、使いやすい視覚的で構成要素のスタイルを持つクエリ ビルダーが備わります。 ガイド付きモードを使用するには、「 [ガイド付きハンティング モードの概要](advanced-hunting-modes.md#get-started-with-guided-hunting-mode)」を参照してください。

高度なモードでは、ユーザーが最初からクエリを作成できるクエリ エディター領域が備わります。 詳細モードを使用するには、「 [高度なハンティング モードの概要](advanced-hunting-modes.md#get-started-with-advanced-hunting-mode)」を参照してください。

## <a name="get-started-with-guided-hunting-mode"></a>ガイド付きハンティング モードの使用を開始する

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

ガイド付きハンティングが利用可能になった後に初めて高度なハンティング ページを開くと、ツアーに参加して、タブやクエリ領域などのページのさまざまな部分の詳細を確認するように招待されます。 

ツアーを行うには、このバナーが表示されたら [ **ツアーを行う** ] を選択します。


[![ツアー](../../media/guided-hunting/1-guided-hunting-banner-tb.png)に参加するようユーザーを招待するバナー ](../../media/guided-hunting/1-guided-hunting-banner.png#lightbox)

ページ全体に表示される青い教示のバブルに従い、[ **次へ** ] を選択して、あるステップから次のステップに移動します。

ヘルプ **リソース** > **の詳細を確認** し、[ツアーの実行] を選択すると、いつでも **ツアーに** 参加できます。

![ヘルプ リソースのスクリーンショット](../../media/guided-hunting/help-resources.png)


その後、脅威を検出するためのクエリの構築を開始できます。 次の記事は、ガイド付きモードでハンティングを最大限に活用するのに役立ちます。


| 学習目標 | 説明 | リソース |
|--|--|--|
| **最初のクエリを作成する** | データ ドメインの指定や、意味のあるクエリの作成に役立つ条件とフィルターの追加など、クエリ ビルダーの基本について説明します。 サンプル クエリを実行して詳細を確認します。 | [ガイド モードを使用してハンティング クエリを作成する](advanced-hunting-query-builder.md) |
| **さまざまなクエリ ビルダー機能について説明します** |  サポートされているさまざまなデータ型とガイド付きモード機能を理解し、ニーズに応じてクエリを微調整するのに役立ちます。 | [ガイド モードでクエリを絞り込む](advanced-hunting-query-builder-details.md) |
| **クエリ結果でできることについて説明します** | 結果ビューと、生成された結果 (アクションの実行方法やインシデントへのリンク方法など) について理解します。 | - [ガイド モードでクエリ結果を操作する](advanced-hunting-query-builder-results.md)<br /> - [クエリ結果に対してアクションを実行する](advanced-hunting-take-action.md) <br /> - [クエリ結果をインシデントにリンクする](advanced-hunting-link-to-incident.md) |
| **検出ルールの作成** | 高度なハンティング クエリを使用してアラートをトリガーし、応答アクションを自動的に実行する方法について説明します。 | - [カスタム検出の概要](custom-detections-overview.md) <br />- [カスタム検出ルール](custom-detection-rules.md) |

## <a name="get-started-with-advanced-hunting-mode"></a>高度なハンティング モードの使用を開始する
高度な捜索をすばやく開始するには、次の手順を実行することをお勧めします。 

| 学習目標 | 説明 | リソース |
|--|--|--|
| **言語を学習する** | 高度なハンティングは [Kusto クエリ言語](/azure/kusto/query/)に基づいており、同じ構文と演算子をサポートしています。 最初のクエリを実行して、クエリ言語を学習します。 | [クエリ言語の概要](advanced-hunting-query-language.md) |
| **クエリ結果を使用する方法について説明します** | グラフと、結果を表示またはエクスポートするさまざまな方法について説明します。 クエリをすばやく調整し、ドリルダウンしてより豊富な情報を取得し、応答アクションを実行する方法について説明します。 | - [詳細モードでクエリ結果を操作する](advanced-hunting-query-results.md)<br /> - [クエリ結果に対してアクションを実行する](advanced-hunting-take-action.md) <br /> - [クエリ結果をインシデントにリンクする](advanced-hunting-link-to-incident.md)  |
| **スキーマを理解する** | スキーマとその列のテーブルについて、高レベルで十分に理解してください。 クエリを作成するときにデータを検索する場所について説明します。 | - [スキーマリファレンス](advanced-hunting-schema-tables.md) <br />- [Microsoft Defender for Endpointからの移行](advanced-hunting-migrate-from-mde.md) |
| **エキスパートのヒントと例を入手する** | Microsoft エキスパートのガイドを使用して無料でトレーニングします。 さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。 | - [エキスパート トレーニングを受ける](advanced-hunting-expert-training.md) <br />- [共有クエリを使用する](advanced-hunting-shared-queries.md) <br />- [ハントに行く](advanced-hunting-go-hunt.md) <br />- [デバイス、電子メール、アプリ、ID 間で脅威を検出する](advanced-hunting-query-emails-devices.md) |
| **クエリを最適化し、エラーを処理する** | 効率的でエラーのないクエリを作成する方法について説明します。 | - [クエリのベスト プラクティス](advanced-hunting-best-practices.md)<br />- [エラーを処理する](advanced-hunting-errors.md) |
| **検出ルールの作成** | 高度なハンティング クエリを使用してアラートをトリガーし、応答アクションを自動的に実行する方法について説明します。 | - [カスタム検出の概要](custom-detections-overview.md) <br />- [カスタム検出ルール](custom-detection-rules.md)|

## <a name="see-also"></a>関連項目
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [ガイド モードを使用してハンティング クエリを作成する](advanced-hunting-query-builder.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)