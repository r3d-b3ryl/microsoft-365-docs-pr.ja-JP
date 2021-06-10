---
title: 予測コーディング (Advanced eDiscovery - クイック スタート
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 予測コーディング モジュールの使用を開始する方法については、Advanced eDiscovery。 この記事では、予測コーディングを使用して、調査に最も関連性の高いレビュー セット内のコンテンツを識別するエンドツーエンドのプロセスについて説明します。
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822559"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a>クイック スタート: クイック スタートでの予測Advanced eDiscovery (プレビュー)

この記事では、予測コーディングを使用する方法のクイック スタートをAdvanced eDiscovery。 予測コーディング モジュールは、Advanced eDiscoveryのインテリジェントな機械学習機能をAdvanced eDiscovery、レビューするコンテンツの量を減らすのに役立ちます。 予測コーディングを使用すると、大量のケース コンテンツを、レビューに優先順位付けできる関連する一連のアイテムに対して削減し、調整するのに役立ちます。 これは、レビュー セット内の最も関連性の高いアイテムのレビューに優先順位を付けるのに役立つ、独自の予測コーディング モデルを作成してトレーニングすることで実現されます。

予測コーディング プロセスの概要を以下に示します。

![予測コーディングのクイック スタート プロセス](..\media\PredictiveCodingQuickStartProcess.png)

開始するには、モデルを作成し、関連性の高いアイテムまたは関連性の高いアイテムを 50 アイテムまでラベル付けします。 次に、システムはこのトレーニングを使用して、レビュー セット内のすべてのアイテムに予測スコアを適用します。 これにより、予測スコアに基づいてアイテムをフィルター処理できます。これにより、最も関連性の高い (または関連性の低い) アイテムを最初に確認できます。 より高い読み上げ率とリコール率を持つモデルをトレーニングする場合は、モデルが安定するまで、後続のトレーニング ラウンドでアイテムのラベル付けを続行できます。 モデルが安定化したら、最終的な予測フィルターを適用して、確認する項目の優先順位を設定できます。

予測コーディングの詳細な概要については、「[予測](predictive-coding-overview.md)コーディングの概要」を参照Advanced eDiscovery。

## <a name="step-1-create-a-new-predictive-coding-model"></a>手順 1: 新しい予測コーディング モデルを作成する

最初の手順は、レビュー セットに新しい予測コーディング モデルを作成します。

1. コンプライアンス センターでMicrosoft 365ケースを開Advanced eDiscovery、[レビュー セット]**タブを選択** します。

2. レビュー セットを開き **、[Analytics 予測** コーディングの  >  **管理 (プレビュー) ] をクリックします**。

   ![レビュー セットの [分析] ドロップダウン メニューをクリックして、[予測コーディング] ページに移動します。](..\media\ManagePredictiveCoding.png)

3. [予測 **コーディング モデル (プレビュー)]** ページで、[新しいモデル] **をクリックします**。

4. [フライアウト] ページで、モデルの名前とオプションの説明を入力します。

5. [保存 **] を** クリックしてモデルを作成します。

   システムがモデルを準備するには数分かかります。 準備ができたら、トレーニングの第 1 ラウンドを実行できます。

詳細な手順については、「予測コーディング モデルの [作成」を参照してください](predictive-coding-create-model.md)。

## <a name="step-2-perform-the-first-training-round"></a>手順 2: 最初のトレーニング ラウンドを実行する

モデルを作成した後、次の手順では、関連するアイテムまたは関連性のないラベルを付け、最初のトレーニング ラウンドを完了します。

1. レビュー セットを開き **、[Analytics 予測** コーディングの  >  **管理 (プレビュー) ] をクリックします**。

2. [予測 **コーディング モデル (プレビュー)] ページ** で、トレーニングするモデルを選択します。

3. [概要] **タブの** [ラウンド **1] で**、[次のトレーニング ラウンドの開始 **] をクリックします**。

   [ **トレーニング]** タブが表示され、ラベル付けするアイテムが 50 件含まれています。

4. 各ドキュメントを確認し、閲覧 **ウィンドウ** の下部にある [関連する] または [関連しない] ボタンを選択してラベルを付きます。

   ![各ドキュメントに関連性の高いラベルを付け、関連性の高いラベルを付けない](..\media\TrainModel1.png)

5. 50 アイテムのラベルを付け終わったら、[完了] を **クリックします**。

    システムがラベル付けから "学習" し、モデルを更新するには数分かかります。 このプロセスが完了すると、[予測コーディングモデル (プレビュー)] ページにモデルの状態が [準備完了 **] と表示** されます。

詳細な手順については、「予測コーディング モデルの [トレーニング」を参照してください](predictive-coding-train-model.md)。

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a>手順 3: レビュー セット内のアイテムに予測スコア フィルターを適用する

1 回のトレーニング ラウンドをリースで実行した後、レビュー セット内のアイテムに予測スコア フィルターを適用できます。 これにより、モデルが予測したアイテムを関連性の高いアイテムまたは関連性の高いアイテムとして確認できます。   

1. レビュー セットを開きます。

   ![[フィルター] をクリックして [フィルター] フライアウト ページを表示します。](..\media\PredictionScoreFilter0.png)

   事前に読み込まれた既定のフィルターは、レビュー セット ページの上部に表示されます。 これらの設定は Any のままに **できます**。

2. [フィルター **] を** クリックして 、[ **フィルター] フライアウト** ページを表示します。

3. **[Analytics &予測コーディング] セクションを展開** して、一連のフィルターを表示します。

      ![[Analytics &コーディング] セクションの予測スコア フィルター](..\media\PredictionScoreFilter1.png)

   予測スコア フィルターの名前付け規則は、 **予測スコア (モデル名) です**。 たとえば、モデル **A** という名前のモデルの予測スコア フィルター名は **、予測スコア (モデル A) です**。

4. 使用する予測スコア フィルターを選択し、[完了] を **クリックします**。

5. [レビュー セット] ページで、予測スコア フィルターのドロップダウンをクリックし、予測スコア範囲の最小値と最大値を入力します。 たとえば、次のスクリーンショットは、.5 ~ **1.0** の予測スコア **範囲を示しています**。

   ![予測スコア フィルターの最小値と最大値](..\media\PredictionScoreFilter2.png)

6. フィルターの外側をクリックすると、自動的にレビュー セットにフィルターが適用されます。

  指定した範囲内の予測スコアを持つドキュメントの一覧が、レビュー セット ページに表示されます。

詳細な手順については、「予測フィルターを [レビュー セットに適用する」を参照してください](predictive-coding-apply-prediction-filter.md)。

## <a name="step-4-perform-more-training-rounds"></a>手順 4: より多くのトレーニング ラウンドを実行する

多くの場合、モジュールをトレーニングするために、より多くのトレーニング ラウンドを実行して、レビュー セット内の関連性の高いアイテムや関連性の低いアイテムをより適切に予測する必要があります。 一般に、要件を満たすのに十分に安定するまで、モデルを十分な時間トレーニングします。

詳細については、「追加のトレーニング [ラウンドを実行する」を参照してください。](predictive-coding-train-model.md#perform-additional-training-rounds)

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a>手順 5: 最終的な予測スコア フィルターを適用してレビューの優先順位を設定する

手順 3 の手順を繰り返して、最終的な予測スコアをレビュー セットに適用し、すべてのトレーニング ラウンドを完了し、モデルを安定化した後、関連するアイテムと関連性の低いアイテムのレビューに優先順位を付ける。