---
title: 秘密度ラベルを使用してインシデント対応に優先順位を付ける
description: インシデントの優先順位付けと調査に感度ラベルを使用する方法について学習する
keywords: 情報、保護、データ、損失、防止、ラベル、dlp、インシデント、調査、調査
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: fb21eb0d52f62c49a9406bd92697dccaff290d7e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60156284"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a>秘密度ラベルを使用してインシデント対応に優先順位を付ける

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

一般的な高度な永続的な脅威ライフサイクルには、データの取り込みが含まれる。 セキュリティ インシデントでは、機密ファイルが危険にさらされる可能性がある調査に優先順位を付け、企業のデータと情報を保護することが重要です。

Defender for Endpoint は、セキュリティ インシデントの事前設定を、感度ラベルを使用して、はるかに簡単に行うのに役立ちます。 機密ラベルは、機密情報などの機密情報を持つデバイスに関連する可能性のあるインシデントをすばやく識別します。

## <a name="investigate-incidents-that-involve-sensitive-data"></a>機密データを含むインシデントを調査する

データの感度ラベルを使用してインシデント調査の優先順位を設定する方法について学習します。

> [!NOTE]
> ラベルは、1 つ以上のWindows 10 Version 1809検出されます。

1. [Microsoft 365 Defender] ポータルで、[インシデント]**を選択&インシデント** \> **を通知します**。

2. 右にスクロールすると、[データの感度 **] 列が表示** されます。 この列は、インシデントに関連するデバイスで観察された機密ラベルを反映し、機密ファイルがインシデントの影響を受ける可能性があるかどうかを示します。

    ![[データの感度] 列のイメージ。](images/data-sensitivity-column.png)

    また、データの感度に基 **づいてフィルター処理を実行できます。**

    ![データの感度フィルターのイメージ。](images/data-sensitivity-filter.png)

3. インシデント ページを開き、さらに調査します。

    ![インシデント ページの詳細のイメージ。](images/incident-page.png)

4. [デバイス] **タブを** 選択して、感度ラベル付きファイルを格納するデバイスを識別します。

    ![[デバイス] タブのイメージ。](images/investigate-devices-tab.png)

5. 機密データを格納するデバイスを選択し、タイムラインを検索して、影響を受ける可能性のあるファイルを特定し、データが保護される適切なアクションを実行します。

   デバイスのタイムラインに表示されるイベントを絞り込むには、データの感度ラベルを検索します。 これにより、ラベル名が指定されたファイルに関連付けられたイベントだけが表示されます。

    ![ラベルに基づいて検索結果を絞り込むデバイスタイムラインの画像。](images/machine-timeline-labels.png)

> [!TIP]
> これらのデータ ポイントは、高度な検索で 'DeviceFileEvents' を通じて公開され、高度なクエリとスケジュール検出で、感度ラベルとファイル保護の状態を考慮に入れることができるようになりました。
