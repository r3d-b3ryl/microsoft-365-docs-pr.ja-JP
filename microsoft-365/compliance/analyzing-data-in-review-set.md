---
title: 電子情報開示のレビュー セット内のデータを分析する (プレミアム)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
description: Microsoft Purview 電子情報開示 (プレミアム) ケースを分析するときにドキュメント セットを整理するために使用できるツールについて説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: af34a790881cad2af5d278cf187b963f0aa58146
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65099831"
---
# <a name="analyze-data-in-a-review-set-in-ediscovery-premium"></a>電子情報開示のレビュー セット内のデータを分析する (プレミアム)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

収集されたドキュメントの数が多い場合、それらをすべて確認することは困難な場合があります。 Microsoft Purview 電子情報開示 (プレミアム) には、ドキュメントを分析して、情報を失うことなく確認するドキュメントの量を減らし、ドキュメントを一貫した方法で整理するのに役立つツールが多数用意されています。 これらの機能の詳細については、次を参照してください。

- [準重複の検出](near-duplicate-detection-in-advanced-ediscovery.md)

- [電子メールのスレッド化](email-threading-in-advanced-ediscovery.md)

- [テーマ](themes-in-advanced-ediscovery.md)

## <a name="run-analytics-for-a-review-set"></a>レビュー セットの分析を実行する

レビュー セット内のデータを分析するには:

1. ケースの分析設定を構成します。 詳細については、「 [検索と分析の設定を構成する」を](configure-search-and-analytics-settings-in-advanced-ediscovery.md)参照してください。

2. 分析するレビュー セットを開きます。

3. [**AnalyticsRun** >  **ドキュメント&電子メール分析**] をクリックします。

   ![[分析] ドロップダウン リストから [ドキュメント&電子メール分析の実行] を選択します。](..\media\RunAnalytics1.png)

分析の進行状況は、ケースの [ **ジョブ** ] タブで確認できます。

 分析が完了したら、分析レポートを表示し、分析の出力に対してレビュー セット内でクエリを実行できます ( [レビュー セット内のクエリを](review-set-search.md)参照し、特定のドキュメントの関連ドキュメントを表示します ( [レビュー セットのデータのレビューを](reviewing-data-in-review-set.md)参照してください)。

## <a name="using-the-for-review-filter-query"></a>For Review フィルター クエリの使用

レビュー セットの分析を実行した後、自動的に生成されたフィルター クエリ ( *For Review* と呼ばれます) を使用して、レビューをフィルター処理して、重要でないアイテム、重複アイテム、または非包含アイテムを除外できます。 これにより、レビュー セットの代表的で一意で包括的なアイテムのみが表示されます。

**レビュー用** フィルター クエリをレビュー セットに適用するには、[**保存されたフィルター クエリ**] ドロップダウン リストを選択し、[**AutoGen] For Review を選択\[** します。

![[保存されたフィルター クエリ] ドロップダウン リストから [確認対象] を選択する](..\media\ForReviewFilterQuery1.png)

**For Review** フィルター クエリの構文を次に示します。

`(((FileClass="Email") AND (InclusiveType="InclusiveMinus" OR InclusiveType="Inclusive")) OR ((FileClass="Attachment") AND (UniqueInEmailSet="true")) OR ((FileClass="Document") AND (MarkAsRepresentative="Unique")) OR (FileClass="Conversations"))`

次の一覧では、レビュー セットに適用した後に表示されるコンテンツの観点から、フィルター クエリの結果について説明します。

- **電子メール**。 包括または **InclusiveMinus** としてマークされたアイテムを表示します。 包括的なアイテムは、電子メール スレッドの最後のメッセージです。 電子メール スレッド内のすべての以前のコンテンツが含まれています。 包括的なマイナスには、電子メール スレッド内の特定のメッセージに関連付けられている 1 つ以上の添付ファイルが含まれます。 校閲者は、包含マイナス値を使用して、電子メール スレッド内のどの特定のメッセージに添付ファイルが関連付けられているかを判断できます。

- **添付ファイル**。 同じメール セット内の重複する添付ファイルを除外します。 メール スレッド内で一意の添付ファイルのみが表示されます。

- **ドキュメントとその他**。 重複するドキュメントを除外します。 レビュー セット内で一意のドキュメントのみが表示されます。

- **会話をTeamsします**。 レビュー セット内のすべてのTeams (およびYammer) 会話が表示されます。

包含型とドキュメントの一意性の詳細については、「[電子情報開示での電子メール スレッド (プレミアム)」](email-threading-in-advanced-ediscovery.md)を参照してください。

> [!NOTE]
> 電子情報開示 (プレミアム) の [新しいケース形式](advanced-ediscovery-new-case-format.md)のパブリック プレビュー中に、**For Review** フィルター クエリは、2021 年 11 月 4 日より前に作成されたレビュー セット (大きなケース形式を使用する場合) のTeamsまたはYammer会話を返しませんでした。 この問題は解決されました。 つまり、大きなケース形式を使用するケースでレビュー セットに **For Review** クエリを再適用すると、すべてのTeamsまたはYammerの会話が含まれるため、フィルター クエリに一致するアイテムが多く表示される可能性があります。

## <a name="analytics-report"></a>分析レポート

レビュー セットの分析レポートを表示するには:

1. レビュー セットを開きます。

2. **[AnalyticsShow** >  レポート] をクリック **します**。

**分析** レポートには、分析の 7 つのコンポーネントがあります。

- **ターゲット母集団:** レビュー セットで見つかった電子メール メッセージ、添付ファイル、および緩やかなドキュメントの数。

- **ドキュメント (添付ファイルを除く):** ピボット、ピボットの重複に近い一意、または別のドキュメントの正確な重複である緩やかなドキュメントの数。

- **メール：** 包括、包括コピー、包括マイナス、または上記のいずれもとしてマークされていない電子メール メッセージの数。

- **添付 ファイル：** レビュー セット内の別の電子メール添付ファイルの一意または重複する電子メール添付ファイルの数。

- **ファイルの種類別にドキュメントに番号を付け:** ファイル拡張子で識別されるファイルの数。

- **ソース別のドキュメント:** 元のデータ ソースによるコンテンツの概要。

- **プロセス別に集計されたドキュメント:** レビュー セット プロセスによるコンテンツの概要。 
