---
title: 'Microsoft Defender 脅威インテリジェンス (Defender TI): インフラストラクチャ チェーン'
description: この概念記事では、インフラストラクチャ チェーンについて説明し、そのプロセスを適用して、Microsoft Defender 脅威インテリジェンス (Defender TI) を使用して脅威インフラストラクチャ分析を実行する方法について説明します。
author: alexroland24
ms.author: aroland
ms.service: threat-intelligence
ms.topic: conceptual
ms.date: 08/02/2022
ms.custom: template-concept
ms.openlocfilehash: 5b094971d4004cb1c58dcf058af68c1182670f92
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2022
ms.locfileid: "67108898"
---
# <a name="infrastructure-chaining"></a>インフラストラクチャ チェーン

インフラストラクチャ チェーンは、高度に接続されたデータセット間のリレーションシップを利用して、調査を構築します。 このプロセスは脅威インフラストラクチャ分析の中核であり、組織は新しい接続を表面化し、同様の攻撃アクティビティをグループ化し、インシデント対応時に想定を立証することができます。

![インフラストラクチャ チェーン](media/infrastructureChaining.png)

## <a name="prerequisites"></a>前提条件

1. [Microsoft Defender 脅威インテリジェンス (Defender TI) のデータ セットの概要に関する記事を確認](data-sets.md)する
2. [Microsoft Defender 脅威インテリジェンス (Defender TI) の検索とピボットの方法に関する記事を確認する](searching-and-pivoting.md)

## <a name="all-you-need-is-a-starting-point"></a>必要なのは出発点です。..

攻撃キャンペーンでは、単純な地理フィルター処理やパッシブ OS フィンガープリントなどの複雑な戦術など、さまざまな難読化手法が採用されています。 これにより、そのトラック内のポイント イン タイム調査が停止される可能性があります。 上のスクリーンショットは、インフラストラクチャ チェーンの概念を示しています。 データ エンリッチメント機能を使用すると、IP アドレス (場合によっては C2) に接続しようとするマルウェアから始めることができました。 その IP アドレスは、ドメイン名などの共通名を持つ SSL 証明書をホストしている可能性があります。 そのドメインは、NewRelicID や他の場所で観察した可能性のあるその他の分析 ID など、コード内の一意のトラッカーを含むページに接続されている可能性があります。 または、ドメインが過去に他のインフラストラクチャに接続されていた可能性があります。このインフラストラクチャは、調査に影響を受ける可能性があります。 主な取り組みは、コンテキストから取り出された 1 つのデータ ポイントが特に役に立たない可能性があるということですが、この他のすべての技術データとの自然な接続を観察すると、ストーリーを結合し始めることができます。

## <a name="an-adversarys-outside-in-perspective"></a>敵対者の外部の視点

敵対者の外部の観点から見ると、ファイアウォールの外部で動作する継続的に拡大する Web とモバイルのプレゼンスを利用できます。

実際のユーザーとして Web およびモバイルのプロパティにアプローチして対話することで、Microsoft のクロール、スキャン、機械学習テクノロジは、ユーザー セッション データを収集し、フィッシング、マルウェア、不正なアプリ、不要なコンテンツ、ドメイン侵害を大規模に検出することで、敵対者の回避手法を解除できます。 これにより、敵対者のインフラストラクチャに関連付けられた [脅威インテリジェンス](what-is-microsoft-defender-threat-intelligence-defender-tI.md)、 [システム タグ](using-tags.md)、 [アナリスト分析情報](analyst-insights.md)、 [および評判スコア](reputation-scoring.md) の形式で、実用的なイベントベースの脅威アラートとワークフローを提供できます。

より多くの脅威データが利用できるようになると、アナリストがデータセットとそれに対応する脅威を理解するために、より多くのツール、教育、労力が必要になります。 Microsoft Defender 脅威インテリジェンス (Defender TI) は、複数のデータ ソースに 1 つのビューを提供することで、これらの取り組みを統合します。

## <a name="next-steps"></a>次の手順
詳細については、「 [チュートリアル: 脅威インテリジェンスとインフラストラクチャ チェーンの収集](gathering-threat-intelligence-and-infrastructure-chaining.md)」を参照してください。