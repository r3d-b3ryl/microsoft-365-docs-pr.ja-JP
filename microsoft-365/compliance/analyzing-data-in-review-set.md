---
title: Advanced eDiscovery のレビュー セット内のデータを分析する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery ケースを分析するときにドキュメント セットを整理するために使用できるツールについて説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c63e7eca2e032bfa11c4d4e6f961bb7a7700a4e
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751372"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>Advanced eDiscovery のレビュー セット内のデータを分析する

収集されたドキュメントの数が多い場合、すべてのドキュメントを確認するのは困難な場合があります。 Advanced eDiscovery には、ドキュメントを分析して情報を損失することなくレビューするドキュメントの量を減らし、ドキュメントを一貫性のある方法で整理するためのツールが多数備えています。 これらの機能の詳細については、以下を参照してください。

- [準重複の検出](near-duplicate-detection-in-advanced-ediscovery.md)

- [電子メールのスレッド化](email-threading-in-advanced-ediscovery.md)

- [テーマ](themes-in-advanced-ediscovery.md)

レビュー セット内のデータを分析するには:

1. ケースの分析設定を構成します。 詳細については、「検索と分析 [の設定を構成する」を参照してください](configure-search-and-analytics-settings-in-advanced-ediscovery.md)。

2. 分析するレビュー セットを開きます。

3. [レビュー **セットの管理] をクリックします**。

4. [ **レビュー セットの分析の実行] をクリックします**。

ケースの [ジョブ] タブで **分析の** 進行状況を確認できます。

 分析が完了したら、分析レポートを表示し、分析の出力に対してレビュー セット内でクエリを実行し ([](review-set-search.md)レビュー セット内のクエリを参照)、特定のドキュメントの関連ドキュメントを表示できます (「[レビュー](reviewing-data-in-review-set.md)セット内のデータの確認」を参照)。

## <a name="analytics-report"></a>分析レポート

レビュー セットの分析レポートを表示するには:

1. レビュー セットを開きます。

2. [レビュー **セットの管理] をクリックします**。

3. [レポート **の表示] をクリックします**。

レポートには分析から 7 つのコンポーネントがあります。

- **対象となる母集団:** レビュー セットで見つかった電子メール メッセージ、添付ファイル、および緩やかなドキュメントの数。

- **ドキュメント (添付ファイルを除く):** ピボット、ピボットの一意の近くの重複、または別のドキュメントの完全な複製である緩やかなドキュメントの数。

- **メール:** 包括的なコピー、包括的なマイナス、または上記のいずれの電子メール メッセージも含めない電子メール メッセージの数。

- **添付ファイル:** レビュー セット内の別の電子メール添付ファイルの一意または重複する電子メールの添付ファイルの数。

- **ファイルの種類別の数:** ファイル拡張子で識別されるファイルの数。

- **ソース別のドキュメント:** 元のデータ ソースによるコンテンツの概要。

- **プロセス別に集計されたドキュメント:** レビュー セット プロセス別のコンテンツの概要。 
