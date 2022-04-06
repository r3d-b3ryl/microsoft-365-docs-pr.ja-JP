---
title: 秘密度ラベルを使用してインシデント対応に優先順位を付ける
description: インシデントの優先順位付けと調査に感度ラベルを使用する方法について学習する
keywords: 情報、保護、データ、損失、防止、ラベル、dlp、インシデント、調査、調査
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 465c149e3ad82384b574b43c66da917a46e4a2ce
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474159"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a>秘密度ラベルを使用してインシデント対応に優先順位を付ける

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

一般的な高度な永続的な脅威ライフサイクルには、データの取り込みが含まれる。 セキュリティ インシデントでは、機密ファイルが危険にさらされる可能性がある調査に優先順位を付け、企業のデータと情報を保護することが重要です。

Defender for Endpoint は、セキュリティ インシデントの事前設定を、感度ラベルを使用して、はるかに簡単に行うのに役立ちます。 機密ラベルは、機密情報などの機密情報を持つデバイスに関連する可能性のあるインシデントをすばやく識別します。

## <a name="investigate-incidents-that-involve-sensitive-data"></a>機密データを含むインシデントを調査する

データの感度ラベルを使用してインシデント調査の優先順位を設定する方法について学習します。

> [!NOTE]
> ラベルは、11 以降Windows 10 Version 1809検出され、Windowsされます。

1. [Microsoft 365 Defender] ポータルで、[インシデント] **を選択&通知** \> **します**。

2. 右にスクロールすると、[データの感度 **] 列が表示** されます。 この列は、インシデントに関連するデバイスで観察された機密ラベルを反映し、機密ファイルがインシデントの影響を受ける可能性があるかどうかを示します。

   :::image type="content" source="images/data-sensitivity-column.png" alt-text="[データの機密性] 列の [機密性の高い] オプション" lightbox="images/data-sensitivity-column.png":::

    また、データの感度に基 **づいてフィルター処理を実行できます。**

    :::image type="content" source="images/data-sensitivity-filter.png" alt-text="データの感度フィルター" lightbox="images/data-sensitivity-filter.png":::

3. インシデント ページを開き、さらに調査します。

   :::image type="content" source="images/incident-page.png" alt-text="インシデント ページの詳細" lightbox="images/incident-page.png":::

4. [デバイス] **タブを** 選択して、感度ラベル付きファイルを格納するデバイスを識別します。

   :::image type="content" source="images/investigate-devices-tab.png" alt-text="[デバイス] タブ" lightbox="images/investigate-devices-tab.png":::

5. 機密データを格納するデバイスを選択し、タイムラインを検索して、影響を受ける可能性のあるファイルを特定し、データが保護される適切なアクションを実行します。

   デバイスのタイムラインに表示されるイベントを絞り込むには、データの感度ラベルを検索します。 これにより、ラベル名が指定されたファイルに関連付けられたイベントだけが表示されます。

   :::image type="content" source="images/machine-timeline-labels.png" alt-text="ラベルに基づいて検索結果を絞り込むデバイスのタイムライン" lightbox="images/machine-timeline-labels.png":::

> [!TIP]
> これらのデータ ポイントは、高度な検索で 'DeviceFileEvents' を通じて公開され、高度なクエリとスケジュール検出で、感度ラベルとファイル保護の状態を考慮に入れることができるようになりました。
