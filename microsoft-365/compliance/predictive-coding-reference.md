---
title: 予測コーディングリファレンス
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
description: ''
ms.openlocfilehash: 90c76fade54c109fc02e145a49bbe93d11ad8b79
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822526"
---
# <a name="predictive-coding-reference-preview"></a>予測コーディング参照 (プレビュー)

この記事では、予測コーディング ツールの主要な概念と指標について説明します。Advanced eDiscovery。 記事のセクションはアルファベット順に一覧表示されます。

## <a name="confidence-level"></a>信頼度

信頼度は、予測コーディング モデルを作成するときに高度な設定です。 モデルのパフォーマンス メトリック (リッチネス、精度、リコールなど) が、モデルがレビュー セット内のアイテムに割り当てる予測スコアの真の値を表す、指定された範囲内 (モデルに対して定義された誤差幅を決定する) 内に含められると定義します。 信頼度と誤差幅の値は、コントロール セットに含まれるアイテムの数を決定するのにも役立ちます。 信頼度の既定値は 0.95 または 95% です。

## <a name="control-set"></a>コントロール セット

コントロール セットは、予測コーディング モデルのトレーニング プロセス中に使用されます。 コントロール セットは、トレーニング ラウンド中に実行するラベル付けを使用して、モデルがアイテムに割り当てる予測スコアを評価します。 コントロール セットのサイズは、レビュー セット内のアイテム数と、モデルの作成時に設定されるエラー値の信頼度と余白に基づいて設定されます。 コントロール セット内のアイテムは変更され、ユーザーに対して識別できません。 コントロール セット内のアイテムの総数は、トレーニング ラウンドのフライアウト ページに表示されます。

## <a name="control-set-confusion-matrix"></a>コントロール セットの混同行列

トレーニング ラウンドを完了すると、モデルは、トレーニング ラウンド中にラベル付けしたコントロール セット内の 10 アイテムに予測スコアを割り当てる。 モデルは、これらの 10 アイテムの予測スコアと、トレーニング ラウンド中にアイテムに割り当てた実際のラベルを比較します。 この比較に基づいて、モデルは次の分類を識別して、モデルの予測パフォーマンスを評価します。
  
  |          |モデルは、アイテムが関連すると予測します |モデルはアイテムが関連しないと予測します |
  |:---------|:---------|:---------|
  |**レビューアーのラベルアイテムを関連付け**| 正の正の値| 誤検知 |
  |**レビューアーがアイテムに関連性の高いラベルを付け**| False 負 |True 負 |
  ||||

  これらの比較に基づいて、モデルは、F スコア、精度、および呼び出しメトリックの値と、それぞれの誤差幅を導き出します。 マトリックスからの各混乱の種類の数は、トレーニング ラウンドのフライアウト ページに表示されます。

## <a name="f-score"></a>F スコア

F スコアは、精度と呼び出しの指標のスコアの加重平均です。  この指標のスコアの範囲は **0** ~ **1 です**。 1 に近い **スコア** は、モデルが関連するアイテムをより正確に検出します。 F スコアの指標は、モデル ダッシュボードと各トレーニング ラウンドのフライアウト ページに表示されます。

## <a name="margin-of-error"></a>エラーの余白

予測コーディング モードを作成する場合、エラーの余白は高度な設定です。 コントロール セット内のアイテムのランダム サンプリングから派生したパフォーマンス メトリック (リッチネス、精度、呼び出しなど) の誤差の程度を指定します。 誤差幅を小さくするには、モデルのパフォーマンス 指標が小さい範囲に入る範囲を確保するために、より大きなコントロール セットが必要です。 誤差と信頼度の余白の値は、コントロール セットに含まれるアイテムの数を決定するのにも役立ちます。 誤差幅の既定値は 0.05 または 5% です。

## <a name="model-stability"></a>モデルの安定性

モデルの安定性は、レビュー セット内のドキュメントが関連性が高いかどうかをモデルが正確に予測できるかどうかを示します。 モデルが不安定な場合、モデルの安定性を含めるには、より多くのトレーニング ラウンドを実行する必要があります。 モデルが安定している場合は、トレーニング ラウンドを実行する必要がもうない場合があります。 モデル ダッシュボードは、モデルの安定性の現在の状態を示します。 モデルが安定している場合、パフォーマンス指標は、信頼度と誤差幅の設定に一致するレベルに達しました。

## <a name="overturn-rate"></a>オーバーターン率

オーバーターン率は、トレーニング ラウンド間で予測スコアが変更されたレビュー セット内のアイテムの割合です。 モデルは、オーバーターン率が 5% 未満の場合に安定したと見なされます。 オーバーターン率の指標は、モデル ダッシュボードと各トレーニング ラウンドのフライアウト ページに表示されます。 最初のトレーニング ラウンドのオーバーターン率は、以前の予測スコアを覆す必要がないので、ゼロです。

## <a name="precision"></a>精度

精度メトリックは、モデルが関連すると予測したアイテム間で実際に関連するアイテムの割合を測定します。 つまり、コントロール セット内のアイテムは、ラベルがレビュー者によって関連性が高く、モデルによって関連性が高いと予測されます。 この指標のスコアの範囲は **0** ~ **1 です**。 1 に近い **スコア** は、モデルが関連性の低いアイテムを識別する数を示します。 精度メトリックは、モデル ダッシュボードと各トレーニング ラウンドのフライアウト ページに表示されます。

## <a name="prediction-score"></a>予測スコア

これは、モデルがレビュー セット内の各ドキュメントに割り当てるスコアです。 スコアは、トレーニング ラウンドからのモデルの学習と比較して、ドキュメントの関連性に基づいて決されます。 一般に、予測スコアが **0** ~ **0.5** のアイテムは関連性が高く、 **予測スコアが 0.5** ~ **1** のアイテムは関連性が高いと見なされます。 予測スコアは、ドキュメント メタデータ フィールドに含まれます。 予測フィルターを使用して、指定した予測範囲内にあるレビュー セット内のアイテムを表示できます。

## <a name="recall"></a>呼び出し

リコールメトリックは、モデルが実際に関連するアイテム間で関連していたと予測されるアイテムの割合を測定します。 つまり、モデルが関連すると予測されたコントロール セット内のアイテムも、レビューアーによって関連付けとしてラベル付けされます。 この指標のスコアの範囲は **0** ~ **1 です**。 1 に近い **スコア** は、モデルが関連するアイテムの大部分を識別します。 呼び出しの指標は、モデル ダッシュボードと各トレーニング ラウンドのフライアウト ページに表示されます。

## <a name="review-set"></a>レビュー セット

レビュー セットは、予測コーディング モデルの範囲を提供します。 レビュー セットの新しいモデルを作成すると、コントロール セットとトレーニング セットのアイテムがレビュー セットから選択されます。 モデルが予測スコアを割り当てると、レビュー内のアイテムにそれらのスコアが割り当てされます。 予測コーディング モデルを作成する前に、すべてのアイテムをレビュー セットに追加する必要があります。 モデルの作成後にアイテムを追加した場合、それらのアイテムには予測スコアは割り当てられていない。

## <a name="richness"></a>リッチネス

リッチ度メトリックは、モデルが予測するレビュー セットアイテムの割合を関連性のあるものとして測定します。 この指標のスコアの範囲は **0** ~ **1 です**。 リッチ度の指標がモデル ダッシュボードに表示されます。

## <a name="sampled-items"></a>サンプルアイテム

サンプルアイテム *という* 用語は、予測コーディング モデルを作成するときに選択され、コントロール セットに関連付けられるレビュー セット (テキストを含む) 内のアイテムのランダム なサンプルへの参照です。 また、トレーニング ラウンドごとにアイテムのランダムなサンプルも選択されます。 モデルのコントロール セットで選択されたアイテムは、その同じモデルのトレーニング セットに含まれません。 逆の場合も true です。トレーニング セットアイテムはコントロール セットに含まれません。

## <a name="training-set"></a>トレーニング セット

モデルは、レビュー セットからアイテムをランダムに選択し、トレーニング セットに追加します。 トレーニング ラウンド中に、トレーニング セットのアイテム (コントロール セットのアイテムに加えて) が表示され、各アイテムに "関連性" または "関連性はありません" というラベルを付けできます。 このラベル付けまたは "トレーニング" プロセスは、モデルがレビュー内のどのアイテムが関連性が高い、または関連しないのかを予測する方法を学習するのに役立ちます。 トレーニング ラウンドを実行する度に、モデルはレビューからより多くのアイテムを選択し、そのトレーニング ラウンドのトレーニング セットに追加します。 コントロール セットのアイテムは、トレーニング セットに対して選択されません。