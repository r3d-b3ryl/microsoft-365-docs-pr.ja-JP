---
title: Advanced eDiscovery の関連モジュールのサポート
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Advanced eDiscovery の関連モジュールは、2021 年 3 月 10 日に廃止されます。 この記事では、関連性が廃止される前に実行する方法について説明します。 具体的には、バッチ計算を実行して、未完成のモデルを完成し、モデルからメタデータを保持できます。
ms.openlocfilehash: 22a7fc37a62dc665d4d798525d5e1e55250d0cb1
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122536"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a>Advanced eDiscovery の関連モジュールのサポート

2021 年 3 月 10 日に、Advanced eDiscovery の関連モジュールが廃止されます。 このサポート終了は、組織が関連性モジュールにアクセスできなくなったり  >  (Advanced eDiscovery ケースのレビュー セットの関連性の管理にアクセスしたり)、既存の関連性モデルにアクセスしたりしなくなるという意味です。 廃止される現在の関連性モジュールは、Q2 CY 2021 の新しい予測コーディング ソリューションに置き換えられる予定です。 この新機能により、組織は、より簡単で直感的なワークフローで独自の予測コーディング モデルを構築できます。

この今後のサポートを準備するために、関連モジュールを使用する組織では、既存のすべてのモデルに対して Batch 計算を実行して、モデルの出力を終了日より前にエクスポートすることをお勧めします。 モデルのすべての関連性スコアは、対応するレビュー セットに完全に保存され、ドキュメントがエクスポートされた場合にアクセスできます。 関連性スコアも読み込みファイル内のメタデータとして保持されます。 また、関連性スコアに基づいてレビュー セット内のコンテンツをフィルター処理し、関連性モデルによって生成されたメタデータにアクセスできます。

## <a name="complete-unfinished-models"></a>完全な未完成のモデル

未完成の関連性モデルについては、レビュー セット内のドキュメントにモデルを適用できるよう、評価、トレーニング、バッチ計算を完了してください。 Batch 計算を完了すると、関連モジュールの終了日後に情報が保持されます。

未完成のモデルを完了する手順を次に示します。

1. モデルが安定してバッチ計算の準備が整うまで、モデルをトレーニングします。 「 [タグ付けと関連性のトレーニング」を参照してください](tagging-and-relevance-training-in-advanced-ediscovery.md)。

   次のスクリーンショットは、バッチ計算の準備ができているモジュールを示しています。 Assessment とトレーニングが完了し、次の手順ではバッチ計算を実行します。

   ![バッチ計算の準備ができたモデルのスクリーンショット](../media/ReadyForBatchCalculation.png)

2. バッチ計算を実行します。 「 [バッチ計算の実行」を参照してください](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)。

3. バッチ計算が正常に行されたことを確認します。 バッチ計算 [の結果を参照してください](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)。

未完成の関連性モデルの完成については、Microsoft サポートにお問い合わせください。
