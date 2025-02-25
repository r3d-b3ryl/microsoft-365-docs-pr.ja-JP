---
title: 電子情報開示で予測コーディング モデルを作成する (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 電子情報開示 (Premium) で予測コーディング モデルを作成する方法について説明します。 これは、電子情報開示 (Premium) の機械学習機能を使用して、レビュー セット内の関連するコンテンツと関連性のないコンテンツを識別するのに役立つ最初の手順です。
ms.openlocfilehash: 1105ff05d323ded2297a92d7b12b44a78c35b11f
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66635745"
---
# <a name="create-a-predictive-coding-model-preview"></a>予測コーディング モデルを作成する (プレビュー)

電子情報開示 (Premium) で予測コーディングの機械学習機能を使用する最初の手順は、予測コーディング モデルを作成することです。 モデルを作成した後、レビュー セット内の関連するコンテンツと非関連コンテンツを識別するトレーニングを行うことができます。

予測コーディング ワークフローを確認するには、「[電子情報開示での予測コーディングの詳細 (Premium)](predictive-coding-overview.md#the-predictive-coding-workflow)」を参照してください。

## <a name="before-you-create-a-model"></a>モデルを作成する前に

- 予測コーディング モデルを作成するには、レビュー セットに少なくとも 2,000 個の項目が必要です。

- モデルを作成する前に、必ずすべてのコレクションをレビュー セットにコミットしてください。 モデルの作成後にレビュー セットに追加されたアイテムは処理されず、モデルによって生成された予測スコアが割り当てられます。

- テキストを含まないレビュー セット内のアイテムは、モデルによって処理されたり、予測スコアが割り当てられません。 テキストを含む項目は、コントロール セットまたはトレーニング セットに含まれます。

## <a name="create-a-model"></a>モデルを作成する

1. Microsoft Purview コンプライアンス ポータルで、電子情報開示 (Premium) ケースを開き、[**校閲セット**] タブを選択します。

2. レビュー セットを開き、 **Analytics** > **[予測コーディングの管理 (プレビュー)]** をクリックします。

   ![レビュー セットの [分析] ドロップダウン メニューをクリックして、[予測コーディング] ページに移動します。](..\media\ManagePredictiveCoding.png)

3. [ **予測コーディング モデル (プレビュー)]** ページで、[ **新しいモデル**] をクリックします。

4. ポップアップ ページで、モデルの名前と省略可能な説明を入力します。

5. 必要に応じて、信頼レベルと誤差の余白に関連する詳細設定を構成できます (ポップアップ ページの **[詳細設定] を** クリックします)。 これらの設定は、コントロール セットに含まれる項目の数に影響します。 *コントロール セット* は、トレーニング ラウンド中に実行するラベル付けを使用して、モデルがアイテムに割り当てる予測スコアを評価するために、トレーニング プロセス中に使用されます。 ドキュメントレビューの信頼度レベルと誤差の余白に関するガイドラインが組織にある場合は、適切なボックスに指定します。 それ以外の場合は、既定の設定を使用します。

6. [ **保存] を** クリックしてモデルを作成します。

   システムがモデルを準備するには数分かかります。 準備ができたら、トレーニングの最初のラウンドを実行できます。

## <a name="what-happens-after-you-create-a-model"></a>モデルを作成した後の動作

モデルを作成した後、モデルの作成と準備中にバックグラウンドで次のことが発生します。

- コントロール セットの項目数が計算されます。 このサイズは、レビュー セット内のアイテムの数と、信頼レベルと誤差の余白の設定に基づきます。 コントロール セットの項目はランダムに選択され、コントロール セット項目として指定されます。 システムには、トレーニングの最初のラウンドでコントロール セットから 10 個の項目が含まれています。

- システムは、最初のトレーニング ラウンドのトレーニング セットに含まれるレビュー セットから 40 項目をランダムに選択します。 そのため、トレーニングの最初のラウンドには、ラベル付け用に 50 個のアイテムが含まれます。トレーニング セットから 40 項目、コントロール セットから 10 項目です。

## <a name="next-steps"></a>次の手順

レビュー セットのモデルを作成した後、次の手順では、モデルを "教える" トレーニング ラウンドを実行して、調査に関連するコンテンツを識別します。 詳細については、「 [予測コーディング モデルをトレーニングする](predictive-coding-train-model.md)」を参照してください。
