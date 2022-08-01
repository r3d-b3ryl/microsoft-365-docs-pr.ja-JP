---
title: Microsoft Defender 脅威インテリジェンス (Defender TI) Analyst Insights
description: この概要記事では、Microsoft Defender 脅威インテリジェンス (Defender TI) のアナリスト分析情報機能について説明します。
author: alexroland24
ms.author: aroland
ms.service: threat-intelligence
ms.topic: overview
ms.date: 08/02/2022
ms.custom: template-overview
ms.openlocfilehash: 9efcb78a50f8b91ab2a6d094718edbd205fcdbc4
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2022
ms.locfileid: "67108752"
---
# <a name="analyst-insights"></a>アナリストの分析情報

Microsoft Defender 脅威インテリジェンス (Defender TI) の Analyst Insights セクションでは、調査の次の手順を決定するのに役立つ可能性があるアーティファクトに関する簡単な分析情報を提供します。 このセクションでは、アーティファクトに適用されるすべての分析情報と、追加の可視性に適用されない分析情報を一覧表示します。 次の例では、IP アドレスがルーティング可能であり、Web サーバーをホストし、過去 5 日以内にポートが開いていたことを迅速に判断できます。 さらに、システムにはトリガーされなかったルールが表示されます。これは、調査を開始するときに同様に役立ちます。

![Analyst Insights Edge のスクリーンショット](media/analystInsightsEdgeScreenshot.png)

## <a name="analyst-insight-types-and-questions-they-can-address"></a>アナリストの分析情報の種類と対処できる質問

| アナリスト分析情報の種類                      | 対処できる質問                                                                                                |
|--------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| Blocklisted                                | ドメイン、ホスト、または IP アドレスがブロックリストされたのはいつですか?                                                                  |
|                                            | Defender TI でドメイン、ホスト、または IP がブロックリストに登録された回数はどれくらいですか?                                                            |
| 登録済み&更新済み                       | ドメインが登録された日数、数か月、何年前か。                                                               |
|                                            | ドメイン WHOIS レコードが更新されたのはいつですか?                                                                                 |
| サブドメインの IP 数                         | ドメインのサブドメインに関連付けられている IP の数はどれくらいですか?                                                  |
| 新しいサブドメインの観察                 | Microsoft が問題のドメインの新しいサブドメインを最後に観察したのはいつですか?                                     |
| 登録済み&解決 | クエリ対象のドメインは存在しますか?                                                                                            |
|                                            | ドメインは IP アドレスに解決されますか?                                                                                 |
| WHOIS レコードを共有するドメインの数 | 同じ WHOIS レコードを共有する他のドメインは何ですか?                                                                           |
| ネーム サーバーを共有するドメインの数  | 同じネーム サーバー レコードを共有する他のドメインは何ですか?                                                                     |
| RiskIQ によってクロールされる                          | このホストまたはドメインが Microsoft によって最後にクロールされたのはいつですか?                                                                   |
| 国際ドメイン                       | ドメインに対して国際ドメイン名 (IDN) のクエリが実行されますか?                                                             |
| サード パーティによってブロックリストされる                 | このインジケーターはサード パーティによってブロックリストされていますか?                                                                           |
| Tor Exit ノードの状態                       | 問題の IP アドレスは、Onion ルーター ネットワーク (Tor) に関連付けられているか。                                            |
| 検出されたポートを開く                        | Microsoft の最後のポートでこの IP アドレスがスキャンされたのはいつですか?                                                                        |
| プロキシの状態                               | このインジケーターのプロキシの状態は何ですか?                                                                               |
| Host Last Observed                         | 問題の IP アドレスはインターネットにアクセスできますか?                                                                        |
| Web サーバーをホストする                         | IP アドレスには、そのリソースを使用して適切な Web サーバーの名前を解決する DNS サーバーがありますか? |

## <a name="next-steps"></a>次の手順

詳細については、以下を参照してください。

- [評判スコアリング](reputation-scoring.md)
- [タグの使用](using-tags.md)