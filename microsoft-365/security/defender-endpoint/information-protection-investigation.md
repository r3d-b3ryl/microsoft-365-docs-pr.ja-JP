---
title: 秘密度ラベルを使用してインシデント対応に優先順位を付ける
description: 秘密度ラベルを使用してインシデントの優先順位付けと調査を行う方法について説明します
keywords: 情報, 保護, データ, 損失, 防止,ラベル, DLP, インシデント, 調査, 調査
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

一般的な高度な永続的な脅威ライフサイクルには、データ流出が含まれます。 セキュリティ インシデントでは、機密ファイルが危険にさらされる可能性がある調査に優先順位を付けて、企業のデータと情報を保護することが重要です。

Defender for Endpoint は、機密ラベルを使用することで、セキュリティ インシデントの優先順位付けをはるかに簡単にするのに役立ちます。 秘密度ラベルは、機密情報などの機密情報を持つデバイスに関係する可能性のあるインシデントを迅速に識別します。

## <a name="investigate-incidents-that-involve-sensitive-data"></a>機密データを含むインシデントを調査する

データ機密ラベルを使用してインシデント調査に優先順位を付ける方法について説明します。

> [!NOTE]
> ラベルは、Windows 10 Version 1809 以降およびWindows 11で検出されます。

1. Microsoft 365 Defender ポータルで、**インシデント&アラート** \> **インシデント** を選択します。

2. 右側にスクロールして、[ **データの秘密度** ] 列を表示します。 この列には、インシデントに関連するデバイスで観察された機密ラベルが反映され、機密ファイルがインシデントの影響を受ける可能性があるかどうかを示します。

   :::image type="content" source="images/data-sensitivity-column.png" alt-text="[データの機密性] 列の [機密性の高い] オプション" lightbox="images/data-sensitivity-column.png":::

    **データの機密性** に基づいてフィルター処理することもできます

    :::image type="content" source="images/data-sensitivity-filter.png" alt-text="データの秘密度フィルター" lightbox="images/data-sensitivity-filter.png":::

3. インシデント ページを開き、さらに調査します。

   :::image type="content" source="images/incident-page.png" alt-text="インシデント ページの詳細" lightbox="images/incident-page.png":::

4. [ **デバイス** ] タブを選択して、秘密度ラベルを持つファイルを格納しているデバイスを識別します。

   :::image type="content" source="images/investigate-devices-tab.png" alt-text="[デバイス] タブ" lightbox="images/investigate-devices-tab.png":::

5. 機密データを格納するデバイスを選択し、タイムラインを検索して影響を受ける可能性があるファイルを特定し、適切なアクションを実行してデータが保護されていることを確認します。

   データ秘密度ラベルを検索することで、デバイスタイムラインに表示されるイベントを絞り込むことができます。 これを行うと、ラベル名が指定されたファイルに関連付けられているイベントのみが表示されます。

   :::image type="content" source="images/machine-timeline-labels.png" alt-text="ラベルに基づいて検索結果を絞り込んだデバイス タイムライン" lightbox="images/machine-timeline-labels.png":::

> [!TIP]
> これらのデータ ポイントは、高度な捜索で "DeviceFileEvents" を通じて公開されるため、高度なクエリとスケジュール検出で機密ラベルとファイル保護の状態を考慮できます。
