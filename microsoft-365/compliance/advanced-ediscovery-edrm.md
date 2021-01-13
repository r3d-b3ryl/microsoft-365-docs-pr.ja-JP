---
title: EDRM を使用した高度な電子情報開示の調整
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 の Advanced eDiscovery の組み込みワークフローは、電子情報開示参照モデル (EDRM) で概説されている電子情報開示プロセスに沿っています。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ca94baf1fc57ac014a32a80ddc5705feeb2c842
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841635"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a>電子情報開示参照モデルを使用した Advanced eDiscovery の配置

Microsoft 365 の Advanced eDiscovery の組み込みワークフローは、電子情報開示参照モデル (EDRM) で概説されている電子情報開示プロセスに沿っています。

![電子探索参照モデル (EDRM)](../media/EDRMv1.png)

(画像ソース: edrm.net。 ソース 画像は、Creative Commons Attribution 3.0 Unported License (Creative Commons Attribution 3.0 Unported License) で利用できます)。

大きなレベルでは、Advanced eDiscovery が EDRM ワークフローをサポートする方法を次に示します。

- **Id。** 調査に関心のある人物を特定した後、Advanced eDiscovery ケースにカストディアン (データ保管担当者とも呼ばれる)、調査に関連する情報を保持している可能性がある管理者として追加できます。 ユーザーがカストディアンとして追加された後は、保管担当者のドキュメントを簡単に保持、収集、および確認できます。

- **保持。** 調査に関連するデータを保持および保護するために、Advanced eDiscovery を使用すると、ケース内の保管担当者に関連付けられているデータ ソースに法的情報保留を設定できます。 保管されていないデータを保留に設定できます。 Advanced eDiscovery には、法的情報保留通知を保管担当者に送信し、通知を追跡できる組み込みの通信ワークフローも用意されています。

- **コレクションです。** 調査に関連するデータ ソースを特定 (および保持) した後、Advanced eDiscovery 検索の組み込みの検索ツールを使用して、ケースに関連する可能性のある保管データ ソース (および該当する場合は保管されていないデータ ソース) からライブ データを収集できます。

- **処理。** ケースに関連するすべてのデータを収集した後、次の手順でケースを処理し、さらにレビューと分析を行います。 Advanced eDiscovery では、コレクション フェーズで特定したインセット データが Azure Storage の場所 (レビュー セットと呼ばれる) にコピーされ、ケース データの静的ビューが提供されます。 

- **確認します。** レビュー セットにデータが追加された後、特定のドキュメントを表示し、追加のクエリを実行して、データをケースに最も関連のあるものに減らします。 また、特定のドキュメントに注釈を付け、タグを付けできます。

- **分析。** Advanced eDiscovery は、調査に関連していないと判断したレビュー セットからさらにデータを収集するのに役立つ統合分析ツールを提供します。 Advance eDiscovery は、関連するデータの量を減らすだけでなく、コンテンツを整理してレビュー プロセスをより簡単かつ効率的に行え、法的レビューコストを節約するのにも役立ちます。

- **実稼働** および **プレゼンテーション。** 準備ができたら、法的レビュー用のレビュー セットからドキュメントをエクスポートできます。 ドキュメントは、ネイティブ形式または EDRM で指定された形式でエクスポートして、サード パーティ製のレビュー アプリケーションにインポートできます。

## <a name="more-information"></a>詳細

Advanced eDiscovery の使用を開始するには、以下を参照してください。

- [Advanced eDiscovery のセットアップ](get-started-with-advanced-ediscovery.md)

- [Advanced eDiscovery ケースの作成と管理](create-and-manage-advanced-ediscoveryv2-case.md)