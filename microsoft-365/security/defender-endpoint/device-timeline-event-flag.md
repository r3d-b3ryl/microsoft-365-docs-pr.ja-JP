---
title: Microsoft Defender for Endpoint デバイスのタイムライン イベント フラグ
description: Microsoft Defender for Endpoint デバイスのタイムライン イベント フラグを使用して、
keywords: Defender for Endpoint デバイスのタイムライン、イベント フラグ
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 824a284d60964bfbf93743a15b0e3fca3e7543f3
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213003"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a>Microsoft Defender for Endpoint デバイスのタイムライン イベント フラグ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint デバイス タイムラインのイベント フラグは、潜在的な攻撃を調査するときに特定のイベントをフィルター処理して整理するのに役立ちます。

Defender for Endpoint デバイスのタイムラインは、デバイスで観察されるイベントと関連するアラートの時系列ビューを提供します。 このイベントの一覧は、デバイスで観察されたイベント、ファイル、および IP アドレスを完全に表示します。 リストには長い場合があります。 デバイス タイムラインイベント フラグは、関連する可能性があるイベントを追跡するのに役立ちます。

デバイスのタイムラインを通過した後、フラグを設定した特定のイベントを並べ替え、フィルター処理、エクスポートできます。

デバイスのタイムラインを移動するときに、特定のイベントを検索してフィルター処理できます。 イベント フラグは、次の方法で設定できます。

- 最も重要なイベントの強調表示
- 深く掘り下げが必要なイベントのマーキング
- クリーンな違反タイムラインの構築

## <a name="flag-an-event"></a>イベントにフラグを設定する

1. フラグを設定するイベントを検索する
2. [フラグ] 列のフラグ アイコンをクリックします。 
![デバイスのタイムライン フラグのイメージ。](images/device-flags.png)
2. [フラグ] 列のフラグ アイコンをクリックします。

   ![デバイスのタイムライン フラグのイメージ](images/device-flags.png)

## <a name="view-flagged-events"></a>フラグが設定されたイベントを表示する

1. [タイムライン のフィルター **] セクション** で、[フラグ付 **きイベント] を有効にします**。
2. **[適用]** をクリックします。 フラグが設定されたイベントだけが表示されます。
タイム バーをクリックすると、追加のフィルターを適用できます。 これにより、フラグが設定されたイベントより前のイベントだけが表示されます。  
![フィルターがオンのデバイス タイムライン フラグのイメージ。](images/device-flag-filter.png)
2. **[適用]** をクリックします。 フラグが設定されたイベントだけが表示されます。 タイム バーをクリックすると、追加のフィルターを適用できます。 これにより、フラグが設定されたイベントより前のイベントだけが表示されます。

   ![フィルターがオンのデバイス タイムライン フラグのイメージ](images/device-flag-filter.png)
