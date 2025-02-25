---
title: 検索と分析の設定を構成する - 電子情報開示 (Premium)
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
ms.custom: seo-marvel-mar2020
description: ケース内のすべてのレビュー セットに適用されるMicrosoft Purview eDiscovery (Premium) 設定を構成します。 これには、分析と光学式文字認識の設定が含まれます。
ms.openlocfilehash: 315448606e99a768bacd8d7d4ac7f858c79c7bed
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66624567"
---
# <a name="configure-search-and-analytics-settings-in-ediscovery-premium"></a>電子情報開示 (Premium) で検索と分析の設定を構成する

各Microsoft Purview eDiscovery (Premium) ケースの設定を構成して、次の機能を制御できます。

- 準重複と電子メールスレッド

- テーマ

- 自動生成されたレビューセットクエリ

- テキストの無視

- 光学式文字認識

ケースの検索と分析の設定を構成するには:

1. [**電子情報開示 (プレミアム)**] ページで、ケースを選択します。

2. [**設定**]タブの[**検索と分析**]で、[**選択**]をクリックします。

   ケース設定ページが表示されます。 これらの設定は、ケース内のすべてのレビュー セットに適用されます。

   ![電子情報開示 (Premium) ケースの分析と検索の設定を構成します。](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>準重複と電子メールスレッド

このセクションでは、重複データ検出、ほぼ重複データ検出、電子メール スレッドのパラメーターを設定できます。 詳細については、「 [ほぼ重複データ検出](near-duplicate-detection-in-advanced-ediscovery.md) と [電子メール スレッド」](email-threading-in-advanced-ediscovery.md)を参照してください。

- **ほぼ重複/電子メール スレッド:** オンにすると、レビュー セット内のデータに対して分析を実行するときに、重複データ検出、ほぼ重複検出、電子メール スレッドがワークフローの一部として含まれます。

- **ドキュメントと電子メールの類似性のしきい値:** 2 つのドキュメントの類似性レベルがしきい値を超えている場合、両方のドキュメントは同じほぼ重複するセットに配置されます。

- **単語の最小/最大数:** これらの設定では、ほぼ重複する単語と電子メール スレッド分析が、少なくとも単語数と最大単語数を持つドキュメントでのみ実行されるように指定します。

## <a name="themes"></a>テーマ

このセクションでは、テーマのパラメーターを設定できます。 詳細については、「 [テーマ](themes-in-advanced-ediscovery.md)」を参照してください。

- **テーマ：** オンにすると、レビュー セット内のデータに対して分析を実行するときに、テーマ クラスタリングがワークフローの一部として実行されます。

- **テーマの最大数:** レビュー セット内のデータに対して分析を実行するときに生成できるテーマの最大数を指定します。

- **テーマに数値を含める:** オンにすると、テーマの生成時に数値 (テーマを識別する) が含まれます。 

- **テーマの最大数を動的に調整します。** 特定の状況では、必要な数のテーマを生成するのに十分なドキュメントがレビュー セットに含まれていない場合があります。 この設定を有効にすると、電子情報開示 (プレミアム) はテーマの最大数を強制するのではなく、テーマの最大数を動的に調整します。

## <a name="review-set-query"></a>セット クエリの確認

**[分析後に保存された検索を自動的に作成** する] チェック ボックスをオンにした場合、電子情報開示 (Premium) は **、For Review** という名前のレビュー セット クエリを自動生成します。 

![For Review の自動生成されたクエリ。](../media/AeDForReviewQuery.png)

このクエリは基本的に、レビュー セットから重複するアイテムを除外します。 これにより、レビュー セット内の一意のアイテムを確認できます。 このクエリは、ケースのレビューセットの分析を実行したときにのみ作成されます。 レビュー セットのクエリの詳細については、「 [レビュー セット内のデータのクエリ](review-set-search.md)」を参照してください。

## <a name="ignore-text"></a>テキストの無視

電子メールの内容に関係なく電子メール メッセージに追加される長い免責事項など、特定のテキストが分析の品質を低下させる状況があります。 無視した方がよいテキストがわかっている場合は、テキスト文字列と、テキストを除外する分析機能（準重複、メールのスレッド化、テーマ、関連性）を指定することで、そのテキストを分析から除外できます。 無視されたテキストとして正規表現 (RegEx) を使用することもサポートされています。

## <a name="optical-character-recognition-ocr"></a>光学式文字認識（OCR）

この設定をオンにすると、画像ファイルに対して OCR 処理が実行されます。 OCR 処理は、次の状況で実行されます。

- カストディアンと [非カストディアン データ ソース](non-custodial-data-sources.md) がケースに追加される場合。 OCR をイメージ ファイルに適用すると、それらのファイル内のテキストはコレクション中に検索できるようになります。 OCR 処理は、 [高度なインデックス作成](indexing-custodian-data.md) プロセス中に実行されます。 OCR は、高度なインデックス作成中に処理される項目でのみ実行されます。 たとえば、部分的にインデックスが作成された、または他のインデックス作成エラーが発生した大きな PDF ファイルが高度なインデックス作成中に処理された場合、ファイルには OCR も適用されます。 つまり、OCR 処理は、高度なインデックス作成プロセス中にインデックスが再作成されるファイルでのみ行われます。 つまり、ケースにカストディアンが追加される一方で、高度なインデックス作成中にファイルが処理されないため、一部のメール添付ファイルは OCR 用に処理されない場合があります。

- 他のデータ ソースのコンテンツ (カストディアンに関連付けられていない、非保管データ ソースのケースに追加されたコンテンツ) がレビュー セットに追加される場合。

データをレビュー セットに追加した後、画像テキストを確認、検索、タグ付け、分析できます。 抽出されたテキストは、レビュー セット内の選択したイメージ ファイルのテキスト ビューアーで表示できます。 詳細については、以下を参照してください。

- [カストディアン データの詳細なインデックス処理](indexing-custodian-data.md)

- [検索結果をレビュー セットに追加する](add-data-to-review-set.md#optical-character-recognition)

- [サポートされているイメージ ファイルの種類](supported-filetypes-ediscovery20.md#image)
