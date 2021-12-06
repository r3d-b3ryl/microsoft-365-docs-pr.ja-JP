---
title: デバイスの一覧の CSV ファイル
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: ビジネス向け AutoPilot 用の CSV ファイルを作成するMicrosoft 365説明します。
ms.openlocfilehash: 62dbcddbdab1a08ab3b19c6616b814c421a57c04
ms.sourcegitcommit: 2a4dddf7c655b44b17d4fd7f5e1e5d8a6e2b7aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2021
ms.locfileid: "61311760"
---
# <a name="device-list-csv-file"></a>デバイスの一覧の CSV ファイル

## <a name="device-list-csv-file-format"></a>デバイスの一覧 (CSV ファイル形式)

Windows Autopilot を使用してデバイスを管理および展開するには、デバイスに関する特定の情報を含む CSV ファイルが必要です。
  
デバイスの一覧のファイルの列には、次のヘッダーが指定された順に含まれている必要があります。
  
- 列 A:デバイスのシリアル番号

- 列 B: 空白のままにする

- 列 C:ハードウェア ハッシュ

この情報は、ハードウェアの製造元から、または CSV ファイルを生成する [G-et-WindowsAutoPilotInfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)を使って、入手できます。 

デバイスを追加すると、プロファイルにも追加する必要があります。プロファイルは、デバイスまたはデバイスのグループに AutoPilot 展開プロファイルを適用するために使用されます。
  
## <a name="related-content"></a>関連コンテンツ

[Microsoft 365ドキュメントとリソースの詳細](../../index.yml)
  
[ビジネス向けMicrosoft 365を開始する](../../admin/admin-overview/what-is-microsoft-365.md)