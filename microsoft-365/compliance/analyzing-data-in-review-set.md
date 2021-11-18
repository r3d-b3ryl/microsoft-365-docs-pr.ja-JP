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
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ケースの分析時にドキュメント セットを整理するために使用できるツールAdvanced eDiscoveryします。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dc1bd7b8a717d5f53514209fe50499844644f27b
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2021
ms.locfileid: "61064465"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>レビュー セット内のデータを分析Advanced eDiscovery

収集されたドキュメントの数が多い場合は、それらをすべて確認するのが難しい場合があります。 Advanced eDiscoveryには、ドキュメントを分析して、情報を失わずにレビューするドキュメントの量を減らし、一貫性のある方法でドキュメントを整理するためのツールが多数提供されています。 これらの機能の詳細については、以下を参照してください。

- [準重複の検出](near-duplicate-detection-in-advanced-ediscovery.md)

- [電子メールのスレッド化](email-threading-in-advanced-ediscovery.md)

- [テーマ](themes-in-advanced-ediscovery.md)

## <a name="run-analytics-for-a-review-set"></a>レビュー セットの分析を実行する

レビュー セット内のデータを分析するには、次の方法を実行します。

1. ケースの分析設定を構成します。 詳細については、「検索と分析 [の設定を構成する」を参照してください](configure-search-and-analytics-settings-in-advanced-ediscovery.md)。

2. 分析するレビュー セットを開きます。

3. **[Analytics**  >  **Run document &メール分析] をクリックします**。

   ![[分析] ドロップダウン &から [ドキュメントの実行] を選択し、電子メール分析を実行します。](..\media\RunAnalytics1.png)

分析の進行状況は、ケースの [ **ジョブ]** タブで確認できます。

 分析が完了したら、分析レポートを表示し、分析の出力でレビュー セット内でクエリを実行し (「レビュー[](review-set-search.md)セット内のクエリ」を参照)、特定のドキュメントの関連ドキュメントを[](reviewing-data-in-review-set.md)参照できます (「レビュー セットのデータのレビュー」を参照)。

## <a name="using-the-for-review-filter-query"></a>For Review フィルター クエリの使用

レビュー セットの分析を実行した後、自動的に生成されたフィルター クエリ *(For Review)* を使用して、レビューをフィルター処理して、重要でないアイテム、重複するアイテム、または非包括的なアイテムを除外できます。 これにより、レビュー セット内の代表的で一意で包括的なアイテムだけが表示されます。

レビュー セットに **レビュー フィルター** クエリを適用するには、[保存済みフィルター クエリ] ドロップダウン リストを選択し **\[ 、[AutoGen] For Review を選択します**。

![[保存済みフィルター クエリ] ドロップダウン リストから [レビュー用] を選択する](..\media\ForReviewFilterQuery1.png)

For Review フィルター クエリの構文 **を次に** 示します。

`(((FileClass="Email") AND (InclusiveType="InclusiveMinus" OR InclusiveType="Inclusive")) OR ((FileClass="Attachment") AND (UniqueInEmailSet="true")) OR ((FileClass="Document") AND (MarkAsRepresentative="Unique")) OR (FileClass="Conversations"))`

次の一覧では、フィルター クエリの結果を、レビュー セットに適用した後に表示されるコンテンツについて説明します。

- **メール .** [包括] または [インクルーシブ]**としてマークされているアイテム****を表示します**。 包括的なアイテムは、電子メール スレッド内の最後のメッセージです。 メール スレッド内のすべての以前のコンテンツが含まれる。 電子メール スレッド内の特定のメッセージに関連付けられた 1 つ以上の添付ファイルを含む包括的なマイナス。 レビューアーは、包括的なマイナス値を使用して、電子メール スレッド内の特定のメッセージに関連付けられた添付ファイルを特定できます。

- **添付ファイル**. 同じメール セット内の重複する添付ファイルをフィルター処理します。 電子メール スレッドで一意の添付ファイルだけが表示されます。

- **ドキュメントと他の .** 重複するドキュメントをフィルター処理します。 レビュー セット内で一意のドキュメントだけが表示されます。

- **Teams会話**. レビュー Teams (およびYammer) のすべての会話が表示されます。

包括的な型とドキュメントの一意性の詳細については、「メール スレッド」を参照[Advanced eDiscovery。](email-threading-in-advanced-ediscovery.md)

> [!NOTE]
> Advanced eDiscovery の大きなケース形式のパブリック プレビュー中に [、For](advanced-ediscovery-large-cases.md) **Review** フィルター クエリは、2021 年 11 月 4 日より前に作成されたレビュー セット (大きなケース形式を使用する場合) の Teams または Yammer の会話を返しません。 この問題は解決されました。 つまり、大きなケース形式を使用する場合にレビュー セットに対して For **Review** クエリを再適用すると、すべての Teams または Yammer 会話が含まれているため、フィルター クエリに一致するアイテムが多く表示される可能性があります。

## <a name="analytics-report"></a>分析レポート

レビュー セットの分析レポートを表示するには、次の方法を実行します。

1. レビュー セットを開きます。

2. [**分析レポートの**  >  **表示] をクリックします**。

分析 **レポートには** 、分析の 7 つのコンポーネントがあります。

- **ターゲットの母集団:** レビュー セットで見つかった電子メール メッセージ、添付ファイル、および緩やかなドキュメントの数。

- **ドキュメント (添付ファイルを除く):** ピボット、ピボットの重複に近い固有のドキュメント、または別のドキュメントの正確な重複である緩いドキュメントの数。

- **メール:** 包括コピー、包括コピー、包括マイナス、または上記のいずれもマークしない電子メール メッセージの数。

- **添付ファイル:** レビュー セット内の別の電子メール添付ファイルの一意または重複する電子メール添付ファイルの数。

- **ファイルの種類別にドキュメントを番号付けします。** ファイル拡張子で識別されるファイルの数。

- **ソース別のドキュメント:** 元のデータ ソースによるコンテンツの概要。

- **プロセス別に集計されたドキュメント:** レビュー セット プロセス別のコンテンツの概要。 
