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
localization_priority: Normal
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
ms.openlocfilehash: d3785d85654c1e055d0f1b36dad50485d4e82fd9
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59178832"
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
  
[ビジネス向けMicrosoft 365を開始する](../../business-video/what-is-microsoft-365.md)