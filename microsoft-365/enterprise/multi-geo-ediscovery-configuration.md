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
ms.localizationpriority: medium
ms.collection: Strat_SP_gtc
description: Region パラメーターを使用して、複数地域のサテライトの場所で使用する電子情報開示をMicrosoft 365する方法について説明します。
ms.openlocfilehash: b0366470984abbdc0ed0b3e407ca8ef6b5a5743f
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2022
ms.locfileid: "63400938"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Microsoft 365 Multi-Geo 電子情報開示の構成

[Advanced eDiscovery機能を使用](../compliance/overview-ediscovery-20.md)すると、複数地域の電子情報開示管理者が"地域" セキュリティ フィルターを使用せずにすべての地域を検索できます。 データは、複数地域テナントの中央の場所の Azure インスタンスにエクスポートされます。 ただし、保管担当者に保留を適用しても同じことが起こりますが、保留内の保留統計は"Region" セキュリティ フィルターなしでは表示されません。 0 を示す保留統計は、保留状態が On (成功) を示している限り、保留が失敗したという意味ではありません。

高度な電子情報開示機能がない場合、複数地域テナントの電子情報開示マネージャーまたは管理者は、そのテナントの中央の場所でのみ電子情報開示を実行できます。 サテライトの場所に対して電子情報開示を実行する機能をサポートするために、PowerShell を介して"Region" という名前の新しいコンプライアンス セキュリティ フィルター パラメーターを使用できます。 このパラメーターは、中央の場所が北アメリカ、ヨーロッパ、またはアジア太平洋にあるテナントで使用できます。 Advanced eDiscovery、北アメリカ、ヨーロッパ、アジア太平洋に中央の場所ではなく、サテライトの地理的な場所で電子情報開示を実行する必要があるテナントに推奨されます。 

Microsoft 365 グローバル管理者は、電子情報開示マネージャーのアクセス許可を割り当て、他のユーザーが電子情報開示を実行し、該当するコンプライアンス セキュリティ フィルターで "Region" パラメーターを割り当て、電子情報開示をサテライトの場所として実行する地域を指定する必要があります。それ以外の場合は、サテライトの場所に対して電子情報開示は実行できません。 ユーザーあたり 1 つの "地域" セキュリティ フィルターだけがサポートされています。そのため、すべての地域が同じセキュリティ フィルター内にある必要があります。

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
