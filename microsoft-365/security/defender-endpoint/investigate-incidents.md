---
title: Microsoft Defender for Endpoint でインシデントを調査する
description: 関連付けられたアラートの表示、インシデントの管理、インシデントの調査に役立つアラート メタデータの表示
keywords: 調査、インシデント、アラート、メタデータ、リスク、検出ソース、影響を受けるデバイス、パターン、相関関係
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6453ce0607ed7dee66622b64705d88e91cd67bf4
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58575818"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint でインシデントを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


ネットワークに影響を与えるインシデントを調査し、その意味を理解し、証拠を照合して解決します。

インシデントを調査すると、次の情報が表示されます。

- インシデントの詳細
- インシデントのコメントとアクション
- タブ (アラート、デバイス、調査、証拠、グラフ)

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUV]

## <a name="analyze-incident-details"></a>インシデントの詳細を分析する

インシデントをクリックすると、[インシデント] ウィンドウ **が表示されます**。 [ **インシデントを開く] ページ** を選択して、インシデントの詳細と関連情報 (アラート、デバイス、調査、証拠、グラフ) を表示します。

![インシデントの詳細の画像 1.](images/atp-incident-details.png)

### <a name="alerts"></a>アラート

アラートを調査し、インシデントでどのようにリンクされたのか確認できます。 アラートは、次の理由に基づいてインシデントにグループ化されます。

- 自動調査 - 自動調査によって、元のアラートの調査中にリンクされたアラートがトリガーされました。
- ファイルの特性 - アラートに関連付けられているファイルの特性は類似しています
- 手動関連付け - ユーザーが手動でアラートをリンクした
- 近位時刻 - アラートは、特定の時間枠内に同じデバイスでトリガーされました
- 同じファイル - アラートに関連付けられているファイルは、まったく同じです
- 同じ URL - アラートをトリガーした URL は、まったく同じです。

![[アラート] タブの画像で、そのインシデントでアラートがリンクされた理由を示すインシデントの詳細ページが表示されます。](images/atp-incidents-alerts-reason.png)

アラートを管理し、他の情報と共にアラート メタデータを表示できます。 詳細については、「アラートの調査 [」を参照してください](investigate-alerts.md)。

### <a name="devices"></a>デバイス

また、特定のインシデントの一部または関連するデバイスを調査することもできます。 詳細については、「デバイスの調査 [」を参照してください](investigate-machines.md)。

![インシデントの詳細ページの [デバイス] タブのイメージ。](images/atp-incident-device-tab.png)

### <a name="investigations"></a>調査

[ **調査] を** 選択して、インシデント通知に応答してシステムによって起動された自動調査を表示します。

![インシデントの詳細ページの [調査] タブのイメージ。](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a>証拠を確認する

Microsoft Defender for Endpoint は、インシデントがサポートしているすべてのイベントと、アラート内の不審なエンティティを自動的に調査し、自動応答と重要なファイル、プロセス、サービスなどの情報を提供します。

分析された各エンティティは、感染、修復、または疑わしいとマークされます。

![インシデントの詳細ページの [証拠] タブの画像。](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a>関連するサイバーセキュリティの脅威を視覚化する

Microsoft Defender for Endpoint は、脅威情報をインシデントに集約し、さまざまなデータ ポイントから入ってくるパターンと相関関係を確認できます。 このような相関関係は、インシデント グラフを使用して表示できます。

### <a name="incident-graph"></a>インシデント グラフ

この **Graph、** サイバーセキュリティ攻撃のストーリーを伝えます。 たとえば、どのデバイスで侵害またはアクティビティが観察されたかを示すエントリ ポイントが表示されます。 など

![インシデント グラフのイメージ。](images/atp-incident-graph-tab.png)

インシデント グラフの円をクリックすると、悪意のあるファイルの詳細、関連するファイルの検出、世界中に発生したインスタンスの数、組織で観察されている場合は、インスタンス数を表示できます。

![インシデントの詳細のイメージ。](images/atp-incident-graph-details.png)

## <a name="related-topics"></a>関連項目

- [インシデント キュー](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Microsoft Defender for Endpoint でインシデントを調査する](/microsoft-365/security/defender-endpoint/investigate-incidents)
- [エンドポイント インシデントの Microsoft Defender の管理](/microsoft-365/security/defender-endpoint/manage-incidents)
