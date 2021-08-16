---
title: SharePoint サイトのコンテンツを地域の場所に制限する
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: この記事では、複数地域環境SharePoint地域の場所にサイトを制限する方法について学習します。
ms.openlocfilehash: 1a10ebe8042f2385fa1fa6d3ff3329bb7c066c424b0cb4135f0a29a186f23dc2
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53904625"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a>SharePoint サイトのコンテンツを地域の場所に制限する

状況によっては、サイトが移動されないようにするか、サイトのファイル コンテンツが別の地域の場所にキャッシュされないようにすることで、サイトが作成された地域の場所にサイトとそのファイル コンテンツを保持するように選択できます。

これを行うには、[Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) コマンドレットを **RestrictedToGeo** パラメーターと共に使用します。 このパラメーターの既定値は NULL ですが、次のいずれかに変更できます。

|制限|説明|
|:----------|:----------|
|NoRestriction|サイトを別の地域の場所に移動できます。|
|BlockMoveOnly|サイトを別の地域の場所に移動することはできませんが、サイトのコンテンツを別の地域の場所にキャッシュすることができます。|
|BlockFull|サイトを別の地域の場所に移動することはできません。また、ファイルのすべてのコンテンツも他の地域の場所にキャッシュされません。 ファイルのタイトル (コンテンツから取得)、ファイル名、およびファイルの他のプロパティは、引き続き別の地域の場所にキャッシュできます。<br>BlockFull に構成される前にサイトに保存されたコンテンツは、引き続き他の地域の場所にキャッシュされる可能性があります。|

次の構文を使用します。

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

次に例を示します。

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`