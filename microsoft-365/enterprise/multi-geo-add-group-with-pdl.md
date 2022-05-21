---
title: 特定の優先データの場所を持つMicrosoft 365 グループを作成する
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
description: 複数地域環境で指定された優先データの場所を持つMicrosoft 365 グループを作成する方法について説明します。
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
ms.openlocfilehash: 162f499a783c23ec45ec75610833c61978beaafb
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2022
ms.locfileid: "65623367"
---
# <a name="create-a-microsoft-365-group-with-a-specific-preferred-data-location"></a>特定の優先データの場所を持つMicrosoft 365 グループを作成する

複数地域環境のユーザーが Microsoft 365 グループを作成すると、グループ優先データの場所 (PDL) が自動的にユーザーの場所に設定されます。 グローバル管理者、SharePoint 管理者、Exchange 管理者は、選択した任意の地域にグループを作成できます。 

特定の PDL を使用してグループを作成する必要がある場合は、<a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">SharePoint管理センターまたはExchange Online New-UnifiedGroup</a> Microsoft PowerShell コマンドレットを使用して行うことができます。 これを実行すると、グループ メールボックスとグループに関連付けられている SharePoint サイトは両方とも、指定した PDL でプロビジョニングされます。

指定した PDL を使用してMicrosoft 365 グループを作成するには、グループ サイトを作成する地理的な場所にある<a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">SharePoint管理センター</a>に移動します。

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

![構文New-UnifiedGroup PowerShell コマンドレットのスクリーンショット。](../media/multi-geo-new-group-with-pdl-powershell.png)

> [!Note]
> SharePoint グループ サイトのプロビジョニングはオンデマンドです。 サイトは、グループの所有者またはメンバーが初めてアクセスを試みたときにプロビジョニングされます。

## <a name="geo-location-codes"></a>地域の場所コード

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>関連項目

[Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)

[Graph APIを使用して、特定の優先データの場所を持つグループを作成する](/graph/api/group-post-groups)
