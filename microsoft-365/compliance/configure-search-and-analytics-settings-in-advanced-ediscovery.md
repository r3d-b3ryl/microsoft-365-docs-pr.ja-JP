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
description: ケースAdvanced eDiscoveryすべてのレビュー セットに適用されるユーザー設定を構成します。 これには、分析と光学式文字認識の設定が含まれます。
ms.openlocfilehash: fd1d71a7f617ad836b5c8d2cdcc2beea4b37fdc5aeb14031c80984ca2676db5b
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53892369"
---
# <a name="configure-search-and-analytics-settings-in-advanced-ediscovery"></a>[検索と分析] の設定を構成Advanced eDiscovery

次の機能を制御するために、Advanced eDiscoveryケースごとに設定を構成できます。

- 準重複と電子メールスレッド

- テーマ

- 自動生成されたレビューセットクエリ

- テキストの無視

- 光学式文字認識

ケースの検索と分析の設定を構成するには:

1. **Advanced eDiscovery** ページで、ケースを選択します。

2. [**設定**]タブの[**検索と分析**]で、[**選択**]をクリックします。

   ケース設定ページが表示されます。 これらの設定は、ケース内のすべてのレビュー セットに適用されます。

   ![分析と検索の設定を構成して、Advanced eDiscoveryする](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>準重複と電子メールスレッド

このセクションでは、重複検出、重複検出に近い、電子メール スレッドのパラメーターを設定できます。 詳細については、「Near [duplicate detection and Email](near-duplicate-detection-in-advanced-ediscovery.md) [threading」を参照してください](email-threading-in-advanced-ediscovery.md)。

- **重複/メールスレッドに近い:** オンにすると、レビュー セット内のデータに対して分析を実行すると、重複検出、重複検出に近い、電子メール スレッドがワークフローの一部として含まれます。

- **ドキュメントと電子メールの類似度のしきい値:** 2 つのドキュメントの類似度レベルがしきい値を超える場合、両方のドキュメントが同じほぼ重複セットに置かされます。

- **単語の最小/最大数:** これらの設定では、少なくとも最小単語数と最大単語数を持つドキュメントに対してのみ、ほぼ重複および電子メール スレッド分析が実行されます。

## <a name="themes"></a>テーマ

このセクションでは、テーマのパラメーターを設定できます。 詳細については、「テーマ」を [参照してください](themes-in-advanced-ediscovery.md)。

- **テーマ:** オンにすると、レビュー セット内のデータに対して分析を実行するときに、テーマのクラスタリングがワークフローの一部として実行されます。

- **テーマの最大数:** レビュー セット内のデータに対して分析を実行するときに生成できるテーマの最大数を指定します。

- **テーマに数値を含める:** オンにすると、テーマの生成時に数値 (テーマを識別する) が含まれます。 

- **テーマの最大数を動的に調整します。** 特定の状況では、必要な数のテーマを作成するのに十分なドキュメントがレビュー セットに含めされていない場合があります。 この設定を有効にすると、Advanced eDiscovery はテーマの最大数を強制するのではなく、テーマの最大数を動的に調整します。

## <a name="review-set-query"></a>セットクエリの確認

[分析後に **保存済** み検索を自動的に作成する] チェック ボックスをオンにした場合は、[Advanced eDiscoveryレビュー] という名前のレビュー セット クエリを **自動生成します。** 

![For Review の自動生成クエリ](../media/AeDForReviewQuery.png)

このクエリは基本的に、レビュー セットから重複するアイテムをフィルター処理します。 これにより、レビュー セット内の一意のアイテムを確認できます。 このクエリは、ケースのレビューセットの分析を実行したときにのみ作成されます。 詳細については、「Review set querys」を参照[してください。](review-set-search.md)

## <a name="ignore-text"></a>テキストの無視

電子メールの内容に関係なく、電子メール メッセージに追加される長い免責事項など、特定のテキストによって分析の品質が低下する状況があります。 無視した方がよいテキストがわかっている場合は、テキスト文字列と、テキストを除外する分析機能（準重複、メールのスレッド化、テーマ、関連性）を指定することで、そのテキストを分析から除外できます。 無視されるテキストとして正規表現 (RegEx) を使用することもできます。

## <a name="optical-character-recognition-ocr"></a>光学式文字認識（OCR）

この設定をオンにすると、イメージ ファイルで OCR 処理が実行されます。 OCR 処理は、次の状況で実行されます。

- カストディアンと [非保管](non-custodial-data-sources.md) データ ソースがケースに追加される場合。 イメージ ファイルに OCR を適用すると、コレクション中にそれらのファイル内のテキストを検索できます。 OCR 処理は、高度なインデックス作成 [プロセス中に実行](indexing-custodian-data.md) されます。 OCR は、高度なインデックス作成中に処理されるアイテムでのみ実行されます。 たとえば、高度なインデックス作成中に、部分的にインデックスが作成された、または他のインデックスエラーが発生した大きな PDF ファイルが処理された場合、そのファイルには OCR も適用されます。 つまり、OCR 処理は、高度なインデックス作成プロセス中に再インデックスが作成されたファイルでのみ発生します。 つまり、保管担当者がケースに追加される場合がありますが、高度なインデックス作成中にそれらのファイルは処理されないので、一部の電子メール添付ファイルは OCR 用に処理されません。

- 他のデータ ソース (保管担当者に関連付けされていないコンテンツで、保管されていないデータ ソースのケースに追加されたコンテンツ) がレビュー セットに追加される場合。

データをレビュー セットに追加すると、画像テキストを確認、検索、タグ付け、分析できます。 抽出されたテキストは、レビュー セットで選択したイメージ ファイルのテキスト ビューアーで表示できます。 詳細については、以下を参照してください。

- [カストディアン データの詳細なインデックス処理](indexing-custodian-data.md)

- [検索結果をレビュー セットに追加する](add-data-to-review-set.md#optical-character-recognition)

- [サポートされているイメージ ファイルの種類](supported-filetypes-ediscovery20.md#image)
