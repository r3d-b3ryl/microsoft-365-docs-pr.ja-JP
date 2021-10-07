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
ms.localizationpriority: medium
description: 複数地域環境で指定された優先Microsoft 365場所を持つグループを作成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 05e910d82c44e37497b365a9d0757a80805c895a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201603"
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

![構文を使用New-UnifiedGroup PowerShell コマンドレットのスクリーンショット。](../media/multi-geo-new-group-with-pdl-powershell.png)

SharePoint グループのサイト プロビジョニングがオンデマンドであることに注意してください。 サイトは、グループの所有者またはメンバーが初めてアクセスを試みたときにプロビジョニングされます。

## <a name="geo-location-codes"></a>地域の場所コード

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>関連トピック

[Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)
