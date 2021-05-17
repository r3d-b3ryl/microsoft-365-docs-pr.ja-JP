---
title: 予測コーディング モジュール (Advanced eDiscovery)
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
description: Advanced eDiscovery の新しい予測コーディング モジュールは、機械学習を使用して、ケースまたは調査に関連するドキュメントを予測するレビュー セット内のドキュメントを分析します。
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382975"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a>予測コーディング モジュール (Advanced eDiscovery)

Advanced eDiscovery の新しい予測コーディング モジュールを使用すると、最も関連性の高いドキュメントから始まるドキュメントのレビューを優先するモデルを作成および構築できます。 開始するには、モデルを作成し、最大 50 のドキュメントにラベルを付け、モデル予測スコアでドキュメントをフィルター処理して、関連する関連しないドキュメントを確認できます。

ワークフローの概要を次に示します。

1. レビュー セットで予測コーディング モジュールを開きます。

   ![レビューの [分析] ドロップダウン リストをクリックして、[予測コーディング] モジュールに移動します。](..\media\PredictiveCoding1.png)

2. [予測 **コーディング モデル] ページで** 、[新しいモデル] **をクリックして** 、新しい予測コーディング モデルを作成します。

   ![新しいモデルを作成する](..\media\PredictiveCoding2.png)

3. 少なくとも 50 件のドキュメントに[関連] または [ **関連しない]** **のラベルを付けします**。 このラベル付けは、システムのトレーニングに使用されます。

   ![システムのトレーニングに関連する、または関連性の高い文書にラベルを付け](..\media\PredictiveCoding3.png)

4. モデルの **予測スコア フィルター** をレビュー セットに適用します。 これを行うには、次の手順を実行します。

   1. レビュー セットで、[フィルター] を **クリックします**。
   2. [フィルター **] フライ** アウト ページで、[分析/ML] セクションを展開し、**適用する** モデルの [予測スコア] チェック ボックスをオンにします。
   3. [予測スコア **] フィルター** で、予測スコアを指定します。 フィルターは、予測スコアに一致するレビュー セット内のドキュメントを表示します。

      ![予測スコアを指定してドキュメントをフィルター処理する](..\media\PredictiveCoding4.png)

5. モデルのパフォーマンス、状態、安定性を監視します。

   ![モデルのパフォーマンス、状態、安定性を監視する](..\media\PredictiveCoding5.png)
