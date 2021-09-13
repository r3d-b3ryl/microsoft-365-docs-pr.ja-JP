---
title: レビュー セット内のデータを分析Advanced eDiscovery
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
description: ケースの分析時にドキュメント セットを整理するために使用できるツールAdvanced eDiscoveryします。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c63e7eca2e032bfa11c4d4e6f961bb7a7700a4e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59190161"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>レビュー セット内のデータを分析Advanced eDiscovery

収集されたドキュメントの数が多い場合は、それらをすべて確認するのが難しい場合があります。 Advanced eDiscoveryには、ドキュメントを分析して、情報を失わずにレビューするドキュメントの量を減らし、一貫性のある方法でドキュメントを整理するためのツールが多数提供されています。 これらの機能の詳細については、以下を参照してください。

- [準重複の検出](near-duplicate-detection-in-advanced-ediscovery.md)

- [電子メールのスレッド化](email-threading-in-advanced-ediscovery.md)

- [テーマ](themes-in-advanced-ediscovery.md)

レビュー セット内のデータを分析するには、次の方法を実行します。

1. ケースの分析設定を構成します。 詳細については、「検索と分析 [の設定を構成する」を参照してください](configure-search-and-analytics-settings-in-advanced-ediscovery.md)。

2. 分析するレビュー セットを開きます。

3. [レビュー **セットの管理] をクリックします**。

4. レビュー **セットの [分析の実行] をクリックします**。

分析の進行状況は、ケースの [ **ジョブ]** タブで確認できます。

 分析が完了したら、分析レポートを表示し、分析の出力でレビュー セット内でクエリを実行し (「レビュー[](review-set-search.md)セット内のクエリ」を参照)、特定のドキュメントの関連ドキュメントを[](reviewing-data-in-review-set.md)参照できます (「レビュー セットのデータのレビュー」を参照)。

## <a name="analytics-report"></a>分析レポート

レビュー セットの分析レポートを表示するには、次の方法を実行します。

1. レビュー セットを開きます。

2. [レビュー **セットの管理] をクリックします**。

3. [レポート **の表示] をクリックします**。

レポートには、分析から 7 つのコンポーネントがあります。

- **ターゲットの母集団:** レビュー セットで見つかった電子メール メッセージ、添付ファイル、および緩やかなドキュメントの数。

- **ドキュメント (添付ファイルを除く):** ピボット、ピボットの重複に近い固有のドキュメント、または別のドキュメントの正確な重複である緩いドキュメントの数。

- **メール:** 包括、包括コピー、包括マイナス、または上記のいずれも含む電子メール メッセージの数。

- **添付ファイル:** レビュー セット内の別の電子メール添付ファイルの一意または重複する電子メール添付ファイルの数。

- **ファイルの種類別の数:** ファイル拡張子で識別されるファイルの数。

- **ソース別のドキュメント:** 元のデータ ソースによるコンテンツの概要。

- **プロセス別に集計されたドキュメント:** レビュー セット プロセス別のコンテンツの概要。 
