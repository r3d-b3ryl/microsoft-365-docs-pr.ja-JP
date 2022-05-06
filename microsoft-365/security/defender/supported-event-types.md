---
title: Event Streaming API でサポートされているストリーミング イベントの種類をMicrosoft 365 Defenderする
description: ストリーミング API でサポートされているストリーミング イベントの種類 (テーブル) について説明します
keywords: 生データのエクスポート, ストリーミング API, API, Event Hubs, Azure Storage, ストレージ アカウント, ハンティング, 生データ共有
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
ms.openlocfilehash: e8264ccb9e3181f6b58a6206417eb2b842bec6e7
ms.sourcegitcommit: 317fab13e84b2867087a6ba0a593313ecf43bbed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2021
ms.locfileid: "60364798"
---
# <a name="supported-microsoft-365-defender-streaming-event-types-in-event-streaming-api"></a>イベント ストリーミング API でサポートされているMicrosoft 365 Defenderストリーミング イベントの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


Event Streaming API は、より多くのイベントの種類をサポートするために絶えず拡張されています。 現在パブリック プレビュー中、またはまだサポートされていない、一般公開されているハンティング テーブルについて説明します。 
**新規 - 電子メール イベントの種類/テーブルが GA になりました**

## <a name="hunting-tables-support-status-in-event-streaming-api"></a>イベント ストリーミング API でのハンティング テーブルのサポート状態

次の表には、ストリーミング API でサポートされているテーブルの一覧のみが含まれており、すべての AH スキーマを含むわけではありません。 API の完全な一覧については、「 [スキーマ テーブルについて」を](advanced-hunting-schema-tables.md#learn-the-schema-tables)参照してください。


| テーブル名 | 状態 |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | GA |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | GA  |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** |GA |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** |GA |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | GA |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | GA |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | GA |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | GA |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** |GA |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | GA |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | GA |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | GA |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | GA |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | GA |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | GA |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | GA |


