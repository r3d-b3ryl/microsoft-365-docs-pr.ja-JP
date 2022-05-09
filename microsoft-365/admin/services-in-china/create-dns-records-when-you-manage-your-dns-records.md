---
title: DNS レコードを管理するときにOffice 365の DNS レコードを作成する
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'DNS レコードを管理するときに、21Vianet によって運用Office 365の DNS レコードを作成する方法について説明します。 '
monikerRange: o365-21vianet
ms.openlocfilehash: b1254ed341fb73f17f457798f14d01d89063f920
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313456"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a>DNS レコードを管理するときにOffice 365の DNS レコードを作成する

メール ルーティングに必要な MX レコードを含む、21Vianet によって運用されるOffice 365の DNS レコードを作成する方法の詳細については、「[Office 365用の DNS ホスティング プロバイダーで DNS レコードを作成する](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)」を参照してください。 
  
  
その他のオプションと、注意すべき点がいくつかあります。
      
-  ドメインの DNS ホスティング プロバイダーまたはドメイン レジストラーがわからない場合は、「[ドメイン レジストラーまたは DNS ホスティング プロバイダーを探す](../get-help-with-domains/find-your-domain-registrar.md)」を参照してください。 DNS レコードの操作の説明については、 [DNS の基本](../get-help-with-domains/dns-basics.md)に関するセクションを参照してください。
    
-  一部の DNS ホスティング プロバイダーでは、必要なすべてのレコードの種類を作成できないので、 [ホスティング プロバイダーが SRV、CNAME、TXT、またはリダイレクトをサポートしていない場合にサービスの制限](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)が発生します。 プロバイダーが SRV、TXT、または CNAME レコードをサポートしていない場合は、[必要なすべてのレコードの種類をサポートするプロバイダー](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)に[ドメインを転送](../get-help-with-domains/buy-a-domain-name.md)することをお勧めします。 
    
- 必要な DNS レコードを確認し、電子メール用の MX レコードを含む各レコードに使用する値を見つけるには、「[OFFICE 365 DNS レコードを作成するために必要な情報を収集する](../get-help-with-domains/information-for-dns-records.md)」を参照してください。 DNS レコードの操作の説明については、 [DNS の基本](../get-help-with-domains/dns-basics.md)に関するセクションを参照してください。
