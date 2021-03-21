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
description: この記事では、複数地域環境で SharePoint サイトを指定した地理的位置に制限する方法について説明します。
ms.openlocfilehash: 74255db19b2ecf9b333d33208c63da260b2bd747
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927266"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a><span data-ttu-id="ccefd-103">SharePoint サイトのコンテンツを地域の場所に制限する</span><span class="sxs-lookup"><span data-stu-id="ccefd-103">Restrict SharePoint site content to a geo location</span></span>

<span data-ttu-id="ccefd-104">状況によっては、サイトが移動されないようにするか、サイトのファイル コンテンツが別の地域の場所にキャッシュされないようにすることで、サイトが作成された地域の場所にサイトとそのファイル コンテンツを保持するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="ccefd-104">Under some circumstances you may choose to enforce a site and its file content to remain in the geo location where the site was created, either by preventing the site from being moved or by preventing the caching of the site's file content in another geo location.</span></span>

<span data-ttu-id="ccefd-105">これを行うには、[Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) コマンドレットを **RestrictedToGeo** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="ccefd-105">You can do this by using the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) cmdlet with the **RestrictedToGeo** parameter.</span></span> <span data-ttu-id="ccefd-106">このパラメーターの既定値は NULL ですが、次のいずれかに変更できます。</span><span class="sxs-lookup"><span data-stu-id="ccefd-106">This parameter has a default value of NULL, but you can change it to one of the following:</span></span>

|<span data-ttu-id="ccefd-107">制限</span><span class="sxs-lookup"><span data-stu-id="ccefd-107">Restriction</span></span>|<span data-ttu-id="ccefd-108">説明</span><span class="sxs-lookup"><span data-stu-id="ccefd-108">Description</span></span>|
|:----------|:----------|
|<span data-ttu-id="ccefd-109">NoRestriction</span><span class="sxs-lookup"><span data-stu-id="ccefd-109">NoRestriction</span></span>|<span data-ttu-id="ccefd-110">サイトを別の地域の場所に移動できます。</span><span class="sxs-lookup"><span data-stu-id="ccefd-110">The site can be moved to another geo location.</span></span>|
|<span data-ttu-id="ccefd-111">BlockMoveOnly</span><span class="sxs-lookup"><span data-stu-id="ccefd-111">BlockMoveOnly</span></span>|<span data-ttu-id="ccefd-112">サイトを別の地域の場所に移動することはできませんが、サイトのコンテンツを別の地域の場所にキャッシュすることができます。</span><span class="sxs-lookup"><span data-stu-id="ccefd-112">Site cannot be moved to another geo location, but site content can be cached in other geo locations.</span></span>|
|<span data-ttu-id="ccefd-113">BlockFull</span><span class="sxs-lookup"><span data-stu-id="ccefd-113">BlockFull</span></span>|<span data-ttu-id="ccefd-114">サイトを別の地域の場所に移動することはできません。また、ファイルのすべてのコンテンツも他の地域の場所にキャッシュされません。</span><span class="sxs-lookup"><span data-stu-id="ccefd-114">Site cannot be moved to another geo location, and full file content is not cached in other geo locations.</span></span> <span data-ttu-id="ccefd-115">ファイルのタイトル (コンテンツから取得)、ファイル名、およびファイルの他のプロパティは、引き続き別の地域の場所にキャッシュできます。</span><span class="sxs-lookup"><span data-stu-id="ccefd-115">Files' title (harvested from the content), file name, and other properties of the file can still be cached in other geo-locations.</span></span><br><span data-ttu-id="ccefd-116">BlockFull に構成される前にサイトに保存されたコンテンツは、引き続き他の地域の場所にキャッシュされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ccefd-116">Content stored in the site before it was configured to BlockFull, may continue to be cached in other geo locations.</span></span>|

<span data-ttu-id="ccefd-117">次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ccefd-117">Use the following syntax:</span></span>

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

<span data-ttu-id="ccefd-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ccefd-118">For example:</span></span>

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`