---
title: 特定の優先Microsoft 365グループを作成する
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: 複数地域環境で指定された優先Microsoft 365場所を持つグループを作成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41984dc24e0f30e5e7b7eb0f9672c75b6d65388f
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086826"
---
# <a name="create-a-microsoft-365-group-with-a-specific-preferred-data-location"></a>特定の優先Microsoft 365グループを作成する

複数地域環境のユーザーがグループグループをMicrosoft 365すると、グループ優先データの場所 (PDL) がユーザーの優先データの場所に自動的に設定されます。 グローバル管理者、SharePoint 管理者、Exchange 管理者は、選択した任意の地域にグループを作成できます。 

特定の PDL でグループを作成する必要がある場合は、SharePoint 管理センターから、または Exchange Online New-unifiedgroup Microsoft PowerShell コマンドレットを使用して作成できます。 これを実行すると、グループ メールボックスとグループに関連付けられている SharePoint サイトは両方とも、指定した PDL でプロビジョニングされます。

指定した PDL Microsoft 365グループを作成するには、グループ サイトを作成する地域の場所にある SharePoint 管理センターに移動します。

例:

オーストラリアの場所でグループ サイトを作成する場合は、https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement に移動します

1. **[+ 作成]** を選択します。
2. プロセスに従って、グループ サイトを作成します。

グループ サイトは、サイト作成要求を開始した SharePoint 管理センターに対応する地域の場所にプロビジョニングされます。 

Exchange PowerShell の使用 

Exchange Online PowerShell に接続して、パラメーター *-MailBoxRegion* を地域の場所コードとともに渡します。

次に例を示します。 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![構文を使用した New-UnifiedGroup PowerShell コマンドレットのスクリーンショット](../media/multi-geo-new-group-with-pdl-powershell.png)

SharePoint グループのサイト プロビジョニングがオンデマンドであることに注意してください。 サイトは、グループの所有者またはメンバーが初めてアクセスを試みたときにプロビジョニングされます。

## <a name="geo-location-codes"></a>地域の場所コード

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>関連項目

[Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)
