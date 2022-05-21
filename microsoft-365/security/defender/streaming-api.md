---
title: ストリーム Microsoft 365 Defender イベント
description: Advanced Hunting イベントを Event Hubs または Azure ストレージ アカウントにストリーミングするようにMicrosoft 365 Defenderを構成する方法について説明します
keywords: 生データのエクスポート, ストリーミング API, API, Event Hubs, Azure Storage, ストレージ アカウント, Advanced Hunting, 生データ共有
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d9f980656df636632c5903853c2784de81131d81
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2022
ms.locfileid: "65621433"
---
# <a name="streaming-api"></a>ストリーミング API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>高度なハンティング イベントを Event Hubs または Azure ストレージ アカウントにストリーミングします。

Microsoft 365 Defenderでは[、Advanced Hunting](../defender/advanced-hunting-overview.md) を使用した [Event Hubs](/azure/event-hubs/) または [Azure ストレージ アカウント](/azure/event-hubs/)へのストリーミング イベントがサポートされます。

ストリーミング API のMicrosoft 365 Defenderの詳細については、[ビデオ](https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga)を参照してください。

## <a name="in-this-section"></a>このセクションの内容

トピック | 説明
:---|:---
[イベントをAzure Event Hubsにストリーミングする](streaming-api-event-hub.md)| テナントでストリーミング API を有効にし、[Advanced Hunting](../defender/advanced-hunting-overview.md) を Event Hubs にストリーミングするようにMicrosoft 365 Defenderを構成する方法について説明します。
[Azure ストレージ アカウントにイベントをストリーミングする](streaming-api-storage.md)| テナントでストリーミング API を有効にし、[Advanced Hunting](advanced-hunting-overview.md) を Azure ストレージ アカウントにストリーミングするようにMicrosoft 365 Defenderを構成する方法について説明します。
[サポートされているイベントの種類](supported-event-types.md) | Streaming API でサポートされている高度なハンティング イベントの種類について説明します。

この短いビデオでは、イベント情報を直接 Azure Event Hubs に送信して視覚化サービス、データ処理エンジン、または長期的なデータリテンションのために Azure Storage で使用するようにストリーミング API を設定する方法について説明します。  
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]

## <a name="related-topics"></a>関連項目
- [高度なハンティングの概要](../defender/advanced-hunting-overview.md)
- [Azure Event Hubsドキュメント](/azure/event-hubs/)
- [Azure Storage アカウントのドキュメント](/azure/storage/common/storage-account-overview)
