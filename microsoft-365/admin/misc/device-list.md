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
description: ビジネス向けのMicrosoft 365で AutoPilot 用の CSV ファイルを作成する方法について説明します。
ms.openlocfilehash: af695448e31ea93d36b36a8831702acb84a92410
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2022
ms.locfileid: "65469560"
---
# <a name="windows-autopilot-device-list-csv-file"></a>autopilot デバイス リスト CSV-file をWindowsする

## <a name="device-list-csv-file-format"></a>デバイスの一覧 (CSV ファイル形式)

Windows Autopilot を使用してデバイスを管理および展開するには、デバイスに関する特定の情報を含む CSV ファイルが必要です。
  
デバイスの一覧のファイルの列には、次のヘッダーが指定された順に含まれている必要があります。
  
- 列 A:デバイスのシリアル番号

- 列 B: 空白のままにする

- 列 C:ハードウェア ハッシュ

この情報は、ハードウェアの製造元から、または CSV ファイルを生成する [G-et-WindowsAutoPilotInfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)を使って、入手できます。 

デバイスを追加すると、プロファイルにも追加する必要があります。プロファイルは、デバイスまたはデバイスのグループに AutoPilot 展開プロファイルを適用するために使用されます。
  
## <a name="related-content"></a>関連コンテンツ

[ビジネス ドキュメントとリソースのMicrosoft 365](../../index.yml)
  
[ビジネス向けのMicrosoft 365を使用した概要](../../admin/admin-overview/what-is-microsoft-365.md)