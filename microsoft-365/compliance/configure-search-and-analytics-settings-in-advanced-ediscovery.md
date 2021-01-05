---
title: 検索と分析の設定を構成する - Advanced eDiscovery
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
ms.custom: seo-marvel-mar2020
description: ケース内のすべてのレビュー セットに適用される Advanced eDiscovery 設定を構成します。 これには、分析と光学式文字認識の設定が含まれます。
ms.openlocfilehash: 11932d2172d797ae1913cf28e713d57805ace122
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751304"
---
# <a name="configure-search-and-analytics-settings-in-advanced-ediscovery"></a>Advanced eDiscovery で検索と分析の設定を構成する

Advanced eDiscovery ケースごとに設定を構成して、次の機能を制御できます。

- 準重複と電子メールスレッド

- テーマ

- 自動生成されたレビューセットクエリ

- テキストの無視

- 光学式文字認識

ケースの検索と分析の設定を構成するには:

1. **Advanced eDiscovery** ページで、ケースを選択します。

2. [**設定**]タブの[**検索と分析**]で、[**選択**]をクリックします。

   ケース設定ページが表示されます。 これらの設定は、ケース内のすべてのレビュー セットに適用されます。

   ![Advanced eDiscovery ケースの分析と検索設定を構成する](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>準重複と電子メールスレッド

このセクションでは、重複の検出、ほぼ重複した検出、および電子メールのスレッド処理のパラメーターを設定できます。 詳細については、「近い重複 [データの検出と電子](near-duplicate-detection-in-advanced-ediscovery.md) メール [のスレッド化」を参照してください](email-threading-in-advanced-ediscovery.md)。

- **重複/電子メールのスレッドに近い場合:** オンにすると、レビュー セット内のデータに対して分析を実行すると、重複の検出、ほぼ重複の検出、および電子メール スレッドがワークフローの一部として含まれます。

- **ドキュメントと電子メールの類似性のしきい値:** 2 つのドキュメントの類似レベルがしきい値を超える場合、両方のドキュメントが同じほぼ重複セットに入れらされます。

- **単語の最小/最大数:** これらの設定では、ほぼ重複し、電子メールのスレッド分析は、少なくとも単語の最小数と最大単語数を持つドキュメントに対してだけ実行されます。

## <a name="themes"></a>テーマ

このセクションでは、テーマのパラメーターを設定できます。 詳細については、「テーマ」を [参照してください](themes-in-advanced-ediscovery.md)。

- **テーマ:** オンにすると、レビュー セット内のデータに対して分析を実行すると、テーマのクラスタリングがワークフローの一部として実行されます。

- **テーマの最大数:** レビュー セット内のデータに対して分析を実行するときに生成できるテーマの最大数を指定します。

- **テーマに数字を含める:** オンにすると、テーマを生成するときに (テーマを識別する) 番号が含まれます。 

- **テーマの最大数を動的に調整します。** 状況によっては、必要な数のテーマを生成するのに十分なドキュメントがレビュー セットに含めされていない場合があります。 この設定を有効にすると、Advanced eDiscovery はテーマの最大数を強制するのではなく、テーマの最大数を動的に調整します。

## <a name="review-set-query"></a>セットクエリの確認

[分析後に自動的にレビュー用の保存済み検索を作成する] チェック ボックスをオンにした場合、Advanced eDiscovery は For Review という名前のレビュー セット クエリを **自動生成します。** 

![For Review の自動生成クエリ](../media/AeDForReviewQuery.png)

このクエリは基本的に、レビュー セットから重複するアイテムをフィルター処理します。 これにより、レビュー セット内の一意のアイテムを確認できます。 このクエリは、ケースのレビューセットの分析を実行したときにのみ作成されます。 詳細については、レビュー セットクエリの詳細については、「レビュー セット内 [のデータをクエリする」を参照してください](review-set-search.md)。

## <a name="ignore-text"></a>テキストの無視

特定のテキストが分析の品質を低下させる場合があります。電子メールの内容に関係なく、電子メール メッセージに追加される長い免責事項などです。 無視した方がよいテキストがわかっている場合は、テキスト文字列と、テキストを除外する分析機能（準重複、メールのスレッド化、テーマ、関連性）を指定することで、そのテキストを分析から除外できます。 無視されたテキストとして正規表現 (RegEx) を使用することもできます。 

## <a name="optical-character-recognition-ocr"></a>光学式文字認識（OCR）

この設定をオンにすると、イメージ ファイルに対して OCR 処理が実行されます。 OCR 処理は、次の状況で実行されます。

- カストディアンと [保管されていない](non-custodial-data-sources.md) データ ソースがケースに追加される場合。 OCR 処理は、高度なインデックス作成プロセス中に実行されます。 つまり、検索条件に一致する画像ファイル内のテキストがコレクション検索で返されます。

- 他のデータ ソースのコンテンツ (保管担当者に関連付けされていないコンテンツ、および保管されていないデータ ソースのケースに追加されたコンテンツ) がレビュー セットに追加される場合。

レビュー セットにデータを追加すると、画像テキストをレビュー、検索、タグ付け、分析できます。 抽出されたテキストは、レビュー セットで選択した画像ファイルのテキスト ビューアーで表示できます。 詳細については、以下を参照してください。

- [カストディアン データの詳細なインデックス処理](indexing-custodian-data.md)

- [検索結果をレビュー セットに追加する](add-data-to-review-set.md#optical-character-recognition)

- [サポートされるイメージ ファイルの種類](supported-filetypes-ediscovery20.md#image)
