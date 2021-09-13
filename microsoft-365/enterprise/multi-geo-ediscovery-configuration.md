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
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210674"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Microsoft 365 Multi-Geo 電子情報開示の構成

[Advanced eDiscovery機能を使用](../compliance/overview-ediscovery-20.md)すると、複数地域の電子情報開示管理者が"地域" セキュリティ フィルターを使用せずにすべての地域を検索できます。 データは、複数地域テナントの中央の場所の Azure インスタンスにエクスポートされます。 

高度な電子情報開示機能がない場合、複数地域テナントの電子情報開示マネージャーまたは管理者は、そのテナントの中央の場所でのみ電子情報開示を実行できます。 サテライトの場所に対して電子情報開示を実行する機能をサポートするために、PowerShell を介して"Region" という名前の新しいコンプライアンス セキュリティ フィルター パラメーターを使用できます。 このパラメーターは、中央の場所が北アメリカ、ヨーロッパ、またはアジア太平洋にあるテナントで使用できます。 Advanced eDiscoveryは、中央の場所が北米、ヨーロッパ、アジア太平洋ではなく、サテライト地域の場所全体で電子情報開示を実行する必要があるテナントに推奨されます。 

Microsoft 365 全体管理者は、別のユーザーが電子情報開示を実行できるように電子情報開示マネージャーのアクセス許可を割り当てる必要があります。また、サテライトの場所として電子情報開示を実施する地域を指定するために該当するコンプライアンス セキュリティ フィルターで "Region" パラメーターを割り当てる必要があります。それ以外の場合は、サテライトの場所で電子情報開示は実施されません。

電子情報開示マネージャーまたは管理者の役割が特定のサテライトの場所に設定されている場合、電子情報開示マネージャーまたは管理者は、そのサテライトの場所にある SharePoint サイトと OneDrive サイトに対してのみ電子情報開示の検索操作を実行できます。電子情報開示マネージャーまたは管理者が、指定のサテライトの場所以外の SharePoint サイトまたは OneDrive サイトを検索しようとしても、結果は返されません。さらに、あるサテライトの場所の電子情報開示マネージャーまたは管理者がエクスポートをトリガーすると、データは、その地域の Azure インスタンスにエクスポートされます。制御された境界を越えたコンテンツのエクスポートが許可されなくなることで、これが組織のコンプライアンスの維持に役立ちます。

> [!NOTE]
> 電子情報開示マネージャーが複数の SharePoint のサテライトの場所全体で検索する必要がない場合は、OneDrive サイトまたは SharePoint サイトがある別のサテライトの場所を指定する電子情報開示マネージャー用の別のユーザー アカウントを作成する必要があります。

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

地域のコンプライアンス セキュリティ フィルターを設定するには:

1. [Microsoft 365 セキュリティ/コンプライアンス センター PowerShell への接続](/powershell/exchange/connect-to-scc-powershell)

2. 次の構文を使用してください。

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   次に例を示します。

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

追加のパラメーターと構文については、「[New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter)」の記事を参照してください。