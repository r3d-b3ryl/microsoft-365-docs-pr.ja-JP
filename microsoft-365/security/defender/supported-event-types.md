---
title: Microsoft 365 Defenderストリーミング API でサポートされているイベントの種類
description: ストリーミング API でサポートされているハンティング イベントの種類 (テーブル) について説明します。
keywords: raw data export, Streaming API, API, Event hubs, Azure storage, storage account, Hunting, raw data sharing
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 93f5d54869c01e9a261fd9b6be7c5e5263a28621
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2021
ms.locfileid: "59356216"
---
# <a name="supported-microsoft-365-defender-event-types-in-event-streaming-api"></a>イベント ストリーミング API Microsoft 365 Defenderイベントの種類のサポート

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


イベント ストリーミング API は、より多くのイベントの種類をサポートするために絶えず拡張されています。 一般に使用できるハンティング テーブル、現在パブリック プレビュー中、またはまだサポートされていないハンティング テーブルについて学習します。 
**New - 電子メール イベントの種類/テーブルが GA に変更**

## <a name="hunting-tables-support-status-in-event-streaming-api"></a>イベント ストリーミング API でのハンティング テーブルのサポート状態

| テーブル名 | 状態 |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | GA |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | GA  |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | まだサポートされていません |
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
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | GA |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | GA  |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | GA |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | GA |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | GA |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | GA |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | GA |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | GA |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | GA |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | まだサポートされていません |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** |まだサポートされていません|
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | まだサポートされていません |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | まだサポートされていません |

