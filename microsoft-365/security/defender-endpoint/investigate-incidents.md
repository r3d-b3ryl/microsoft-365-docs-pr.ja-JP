---
title: Microsoft Defender for Endpoint でインシデントを調査する
description: 関連するアラートの表示、インシデントの管理、インシデントの調査に役立つアラート メタデータの表示
keywords: 調査, インシデント, アラート, メタデータ, リスク, 検出元, 影響を受けるデバイス, パターン, 相関関係
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d66dde2c3f346449c7ecd03a7ef577e39cf98991
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468801"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint でインシデントを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


ネットワークに影響を与えるインシデントを調査し、その意味を理解し、証拠を照合して解決します。

インシデントを調査すると、次の情報が表示されます。

- インシデントの詳細
- インシデントのコメントとアクション
- タブ (アラート、デバイス、調査、証拠、グラフ)

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUV]

## <a name="analyze-incident-details"></a>インシデントの詳細を分析する

インシデントをクリックすると **、[インシデント] ウィンドウ** が表示されます。 [ **インシデントを開く] ページ** を選択して、インシデントの詳細と関連情報 (アラート、デバイス、調査、証拠、グラフ) を表示します。

:::image type="content" source="images/atp-incident-details.png" alt-text="インシデントの詳細" lightbox="images/atp-incident-details.png":::

### <a name="alerts"></a>アラート

アラートを調査し、インシデントでそれらがどのようにリンクされたかを確認できます。 アラートは、次の理由に基づいてインシデントにグループ化されます。

- 自動調査 - 自動調査により、元のアラートの調査中にリンクされたアラートがトリガーされました
- ファイルの特性 - アラートに関連付けられているファイルの特性は似ています
- 手動関連付け - アラートを手動でリンクしたユーザー
- 近接時間 - アラートは、特定の期間内に同じデバイスでトリガーされました
- 同じファイル - アラートに関連付けられているファイルがまったく同じ
- 同じ URL - アラートをトリガーした URL がまったく同じ

:::image type="content" source="images/atp-incidents-alerts-reason.png" alt-text="インシデントの詳細ページが表示された [アラート] タブには、そのインシデントでアラートがリンクされた理由が表示されます。" lightbox="images/atp-incidents-alerts-reason.png":::

また、アラートを管理し、他の情報と共にアラート メタデータを表示することもできます。 詳細については、「アラートの [調査](investigate-alerts.md)」を参照してください。

### <a name="devices"></a>デバイス

また、特定のインシデントの一部または関連するデバイスを調査することもできます。 詳細については、「デバイスの [調査](investigate-machines.md)」を参照してください。

:::image type="content" source="images/atp-incident-device-tab.png" alt-text="インシデントの詳細ページの [デバイス] タブ" lightbox="images/atp-incident-device-tab.png":::

### <a name="investigations"></a>調査

[ **調査** ] を選択すると、インシデント アラートに対応してシステムによって起動されたすべての自動調査が表示されます。

:::image type="content" source="images/atp-incident-investigations-tab.png" alt-text="インシデントの詳細ページの [調査] タブ" lightbox="images/atp-incident-investigations-tab.png":::

## <a name="going-through-the-evidence"></a>証拠を確認する

Microsoft Defender for Endpointは、アラート内のすべてのインシデントのサポートされているイベントと疑わしいエンティティを自動的に調査し、自動応答と重要なファイル、プロセス、サービスなどの情報を提供します。

分析された各エンティティは、感染、修復、または疑わしいとしてマークされます。

:::image type="content" source="images/atp-incident-evidence-tab.png" alt-text="インシデントの詳細ページの [証拠] タブ" lightbox="images/atp-incident-evidence-tab.png":::

## <a name="visualizing-associated-cybersecurity-threats"></a>関連するサイバーセキュリティの脅威を視覚化する

Microsoft Defender for Endpointは、脅威情報をインシデントに集約して、さまざまなデータ ポイントから発生するパターンと相関関係を確認できるようにします。 このような相関関係は、インシデント グラフを使用して表示できます。

### <a name="incident-graph"></a>インシデント グラフ

**Graph** は、サイバーセキュリティ攻撃のストーリーを示しています。 たとえば、どのデバイスで侵害またはアクティビティが観察されたかを示すエントリ ポイントを示します。 など。

:::image type="content" source="images/atp-incident-graph-tab.png" alt-text="インシデント グラフ" lightbox="images/atp-incident-graph-tab.png":::

インシデント グラフの円をクリックすると、悪意のあるファイルの詳細、関連するファイル検出、世界中に存在するインスタンスの数、組織で観察されたかどうか、インスタンスの数を表示できます。

:::image type="content" source="images/atp-incident-graph-details.png" alt-text="インシデントの詳細ページ" lightbox="images/atp-incident-graph-details.png":::

## <a name="related-topics"></a>関連項目

- [インシデント キュー](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Microsoft Defender for Endpoint でインシデントを調査する](/microsoft-365/security/defender-endpoint/investigate-incidents)
- [Microsoft Defender for Endpointインシデントを管理する](/microsoft-365/security/defender-endpoint/manage-incidents)
