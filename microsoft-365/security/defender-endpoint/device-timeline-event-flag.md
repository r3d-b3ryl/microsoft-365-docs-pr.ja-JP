---
title: デバイス タイムライン イベント フラグをMicrosoft Defender for Endpointする
description: デバイス のタイムライン イベント フラグMicrosoft Defender for Endpoint使用して、
keywords: Defender for Endpoint デバイスのタイムライン、イベント フラグ
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 44292893249872c1c4b8dc3b4f66d10085fb0a2b
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64471189"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a>デバイス タイムライン イベント フラグをMicrosoft Defender for Endpointする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint デバイス タイムラインのイベント フラグは、潜在的な攻撃を調査するときに、特定のイベントをフィルター処理して整理するのに役立ちます。

Defender for Endpoint デバイスタイムラインは、デバイスで観察されたイベントと関連するアラートの時系列ビューを提供します。 このイベントの一覧は、デバイスで観察されたすべてのイベント、ファイル、および IP アドレスを完全に可視化します。 リストが長い場合があります。 デバイス タイムライン イベント フラグは、関連する可能性のあるイベントを追跡するのに役立ちます。

デバイスタイムラインを通過したら、フラグを設定した特定のイベントを並べ替え、フィルター処理、エクスポートできます。

デバイスのタイムラインを移動するときに、特定のイベントを検索してフィルター処理できます。 イベント フラグは、次の方法で設定できます。

- 最も重要なイベントの強調表示
- 詳細を確認する必要があるイベントのマーキング
- クリーンな違反タイムラインを構築する

## <a name="flag-an-event"></a>イベントにフラグを設定する

1. フラグを設定するイベントを見つける

2. [フラグ] 列のフラグ アイコンをクリックします。 

:::image type="content" source="images/device-flags.png" alt-text="デバイスのタイムライン フラグ" lightbox="images/device-flags.png":::

## <a name="view-flagged-events"></a>フラグが設定されたイベントを表示する

1. タイムラインの **[フィルター]** セクションで、 **フラグ付きイベントを** 有効にします。
2. [**適用**] をクリックします。 フラグが設定されたイベントのみが表示されます。

タイム バーをクリックすると、追加のフィルターを適用できます。 フラグが設定されたイベントより前のイベントのみが表示されます。  

:::image type="content" source="images/device-flag-filter.png" alt-text="フィルターがオンになっているデバイス タイムライン フラグ" lightbox="images/device-flag-filter.png":::