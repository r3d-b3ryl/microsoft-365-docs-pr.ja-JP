---
title: 関連モジュールのAdvanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
description: 2021 年 3 月 10 日Advanced eDiscoveryの関連性モジュールは廃止されます。 この記事では、関連性が廃止される前の操作について説明します。 具体的には、バッチ計算を実行して未完成のモデルを終了し、モデルからメタデータを保持できます。
ms.openlocfilehash: 1005c7a1c065adba039f6f07197dbca758d20ea4
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58565406"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a>[関連] モジュールを使用Advanced eDiscovery

2021 年 3 月 10 日に、関連モジュールは 2021 年 3 月 10 日に廃止Advanced eDiscovery。 この削除は、組織が関連性モジュールにアクセスできなくなった  >  ([Advanced eDiscovery ケースでレビュー セットの関連性を管理する] にアクセスするか、既存の関連性モデルにアクセスできなくなるという意味です。 廃止される現在の関連性モジュールは、Q2 CY 2021 の新しい予測コーディング ソリューションに置き換えられる予定です。 この新機能により、組織は、より簡単で直感的なワークフローで独自の予測コーディング モデルを構築できます。

この今後の退職に備え、関連性モジュールを使用する組織は、既存のすべてのモデルに対してバッチ計算を実行して、モデルの出力を退職日より前にエクスポートすることをお勧めします。 モデルのすべての関連性スコアは、対応するレビュー セットに完全に保存され、ドキュメントをエクスポートするときにアクセスできます。 関連性スコアは、読み込みファイル内のメタデータとして保持されます。 また、関連性スコアに基づいてレビュー セット内のコンテンツをフィルター処理し、関連性モデルによって生成されたメタデータにアクセスできます。

## <a name="complete-unfinished-models"></a>完全な未完成モデル

未完成の関連性モデルについては、レビュー セット内のドキュメントにモデルを適用できるよう、評価、トレーニング、およびバッチ計算を完了してください。 バッチ計算を完了すると、関連性モジュールの終了日後に情報が保持されます。

未完成のモデルを完了する手順を次に示します。

1. モデルが安定してバッチ計算の準備が整うまで、モデルをトレーニングします。 「 [タグ付けと関連性のトレーニング」を参照してください](tagging-and-relevance-training-in-advanced-ediscovery.md)。

   次のスクリーンショットは、バッチ計算の準備ができているモジュールを示しています。 評価とトレーニングが完了し、次にバッチ計算を実行します。

   ![バッチ計算の準備ができているモデルのスクリーンショット。](../media/ReadyForBatchCalculation.png)

2. バッチ計算を実行します。 「 [バッチ計算の実行」を参照してください](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)。

3. バッチ計算が成功したと確認します。 「 [バッチ計算の結果」を参照してください](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)。

未完成の関連性モデルの完成に関するヘルプについては、Microsoft サポートにお問い合わせください。
