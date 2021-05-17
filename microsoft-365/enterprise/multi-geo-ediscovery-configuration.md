---
title: Microsoft 365 Multi-Geo 電子情報開示を構成する
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
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: Region パラメーターを使用して、複数地域のサテライトの場所で使用する電子情報開示をMicrosoft 365する方法について説明します。
ms.openlocfilehash: 4d3481fe8b72bb970893ce065293a7a2cc717331
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923722"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a><span data-ttu-id="13f8e-103">Microsoft 365 Multi-Geo 電子情報開示の構成</span><span class="sxs-lookup"><span data-stu-id="13f8e-103">Microsoft 365 Multi-Geo eDiscovery configuration</span></span>

<span data-ttu-id="13f8e-104">[Advanced eDiscovery機能を使用](../compliance/overview-ediscovery-20.md)すると、複数地域の電子情報開示管理者が"地域" セキュリティ フィルターを使用せずにすべての地域を検索できます。</span><span class="sxs-lookup"><span data-stu-id="13f8e-104">[Advanced eDiscovery capabilities](../compliance/overview-ediscovery-20.md) allow a multi-geo eDiscovery administrator to search all of the geos without needing to utilize a "Region" security filter.</span></span> <span data-ttu-id="13f8e-105">データは、複数地域テナントの中央の場所の Azure インスタンスにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="13f8e-105">Data is exported to the Azure instance of the central location of the multi-geo tenant.</span></span> 

<span data-ttu-id="13f8e-106">高度な電子情報開示機能がない場合、複数地域テナントの電子情報開示マネージャーまたは管理者は、そのテナントの中央の場所でのみ電子情報開示を実行できます。</span><span class="sxs-lookup"><span data-stu-id="13f8e-106">Without advanced eDiscovery capabilities, an eDiscovery manager or administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="13f8e-107">サテライトの場所に対して電子情報開示を実行する機能をサポートするために、PowerShell を介して"Region" という名前の新しいコンプライアンス セキュリティ フィルター パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="13f8e-107">To support the ability to conduct eDiscovery for satellite locations, a new compliance security filter parameter named "Region" is available via PowerShell.</span></span> <span data-ttu-id="13f8e-108">このパラメーターは、中央の場所が北アメリカ、ヨーロッパ、またはアジア太平洋にあるテナントで使用できます。</span><span class="sxs-lookup"><span data-stu-id="13f8e-108">This parameter can be used by tenants whose central location is in North America, Europe, or Asia Pacific.</span></span> <span data-ttu-id="13f8e-109">Advanced eDiscoveryは、中央の場所が北米、ヨーロッパ、アジア太平洋ではなく、サテライト地域の場所全体で電子情報開示を実行する必要があるテナントに推奨されます。</span><span class="sxs-lookup"><span data-stu-id="13f8e-109">Advanced eDiscovery is recommended for tenants whose central location is not in North America, Europe, or Asia Pacific and who need to perform eDiscovery across satellite geo locations.</span></span> 

<span data-ttu-id="13f8e-110">Microsoft 365 全体管理者は、別のユーザーが電子情報開示を実行できるように電子情報開示マネージャーのアクセス許可を割り当てる必要があります。また、サテライトの場所として電子情報開示を実施する地域を指定するために該当するコンプライアンス セキュリティ フィルターで "Region" パラメーターを割り当てる必要があります。それ以外の場合は、サテライトの場所で電子情報開示は実施されません。</span><span class="sxs-lookup"><span data-stu-id="13f8e-110">The Microsoft 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span>

<span data-ttu-id="13f8e-p103">電子情報開示マネージャーまたは管理者の役割が特定のサテライトの場所に設定されている場合、電子情報開示マネージャーまたは管理者は、そのサテライトの場所にある SharePoint サイトと OneDrive サイトに対してのみ電子情報開示の検索操作を実行できます。電子情報開示マネージャーまたは管理者が、指定のサテライトの場所以外の SharePoint サイトまたは OneDrive サイトを検索しようとしても、結果は返されません。さらに、あるサテライトの場所の電子情報開示マネージャーまたは管理者がエクスポートをトリガーすると、データは、その地域の Azure インスタンスにエクスポートされます。制御された境界を越えたコンテンツのエクスポートが許可されなくなることで、これが組織のコンプライアンスの維持に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="13f8e-p103">When the eDiscovery Manager or Administrator role is set for a particular satellite location, the eDiscovery Manager or Administrator will only be able to perform eDiscovery search actions against the SharePoint sites and OneDrive sites located in that satellite location. If an eDiscovery Manager or Administrator attempts to search SharePoint or OneDrive sites outside the specified satellite location, no results will be returned. Also, when the eDiscovery Manager or Administrator for a satellite location triggers an export, data is exported to the Azure instance of that region. This helps organizations stay in compliance by not allowing content to be exported across controlled borders.</span></span>

> [!NOTE]
> <span data-ttu-id="13f8e-115">電子情報開示マネージャーが複数の SharePoint のサテライトの場所全体で検索する必要がない場合は、OneDrive サイトまたは SharePoint サイトがある別のサテライトの場所を指定する電子情報開示マネージャー用の別のユーザー アカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13f8e-115">If it's necessary for an eDiscovery Manager to search across multiple SharePoint satellite locations, another user account will need to be created for the eDiscovery Manager which specifies the alternate satellite location where the OneDrive or SharePoint sites are located.</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

<span data-ttu-id="13f8e-116">地域のコンプライアンス セキュリティ フィルターを設定するには:</span><span class="sxs-lookup"><span data-stu-id="13f8e-116">To set the Compliance Security Filter for a Region:</span></span>

1. [<span data-ttu-id="13f8e-117">Microsoft 365 セキュリティ/コンプライアンス センター PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="13f8e-117">Connect to Microsoft 365 Security & Compliance Center PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell)

2. <span data-ttu-id="13f8e-118">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="13f8e-118">Use the following syntax:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   <span data-ttu-id="13f8e-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="13f8e-119">For example:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

<span data-ttu-id="13f8e-120">追加のパラメーターと構文については、「[New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13f8e-120">See the [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) article for additional parameters and syntax.</span></span>