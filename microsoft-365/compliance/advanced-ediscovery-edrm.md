---
title: EDRM との高度な電子情報開示の配置
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
- m365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 の Advanced eDiscovery の組み込みのワークフローは、電子情報開示参照モデル (EDRM) で概説されている電子情報開示プロセスに合わせて調整されます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2e7886eb67a58b43e9fb638fafb358fd9ee832c
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727490"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a>電子情報開示参照モデルとの高度な電子情報開示の配置

Microsoft 365 の Advanced eDiscovery の組み込みのワークフローは、電子情報開示参照モデル (EDRM) で概説されている電子情報開示プロセスに合わせて調整されます。

![電子探索参照モデル (EDRM)](../media/EDRMv1.png)

(画像ソース提供:edrm.net。 ソース イメージは、クリエイティブ コモンズ アトリビューション 3.0 [報告されていないライセンス] で利用できます。

高度な電子情報開示が EDRM ワークフローをサポートする方法は次の高レベルです。

- **ID。** 調査に関心のある潜在的な人物を特定した後、高度な電子情報開示ケースに保管担当者 (データ保管担当者とも呼ばれる)を追加できます。 ユーザーが保管担当者として追加された後、保管担当者のドキュメントを保存、収集、および確認するのは簡単です。

- **保持。** 調査に関連するデータを保持および保護するために、Advanced eDiscovery を使用すると、ケース内の保管担当者に関連付けられたデータ ソースに法的なホールドを設定できます。 保管以外のデータを保留に設定できます。 高度な電子情報開示には、通信ワークフローも組み込みなので、法的保持通知を保管担当者に送信し、確認応答を追跡できます。

- **コレクション。** 調査に関連するデータ ソースを特定 (および保存) した後、ケースに関連する可能性のある保管データ ソース (および該当する場合は保管されていないデータ ソース) のライブ データを高度な電子情報開示検索で組み込みの検索ツールを使用して収集できます。

- **処理。** ケースに関連するすべてのデータを収集した後、次の手順でケースを処理して、詳細なレビューと分析を行います。 Advanced eDiscovery では、コレクション フェーズで識別したインプレイス データが Azure Storage の場所 (レビュー セットと呼ばれる) にコピーされ、ケース データの静的ビューが提供されます。 

- **確認します。** データをレビュー セットに追加した後、特定のドキュメントを表示し、追加のクエリを実行して、データをケースに最も関連のあるものに減らします。 また、特定のドキュメントに注釈を付け、タグ付けできます。

- **分析。** 高度な電子情報開示には、調査に関連していないと判断したレビュー セットからデータをさらに作成するのに役立つ統合分析ツールが提供されています。 関連するデータの量を減らすだけでなく、Advance eDiscovery を使用すると、コンテンツを整理してレビュー プロセスをより簡単かつ効率的に行って、法的レビューコストを節約できます。

- **実稼働** と **プレゼンテーション。** 準備ができたら、法的レビュー用のレビュー セットからドキュメントをエクスポートできます。 ドキュメントをネイティブ形式または EDRM で指定した形式でエクスポートして、サードパーティのレビュー アプリケーションにインポートできます。

## <a name="more-information"></a>詳細情報

Advanced eDiscovery の使用を開始するには、以下を参照してください。

- [Advanced eDiscovery を設定する](get-started-with-advanced-ediscovery.md)

- [高度な電子情報開示ケースの作成と管理](create-and-manage-advanced-ediscoveryv2-case.md)