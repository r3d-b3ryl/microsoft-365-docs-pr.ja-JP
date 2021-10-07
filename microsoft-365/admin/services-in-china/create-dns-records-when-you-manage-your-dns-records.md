---
title: DNS レコードを管理するときにOffice 365 DNS レコードを作成する
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
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
description: 'DNS レコードを管理するときに、21Vianet Office 365の DNS レコードを作成する方法について学習します。 '
monikerRange: o365-21vianet
ms.openlocfilehash: 0b84926dbedf90752c994e76695c2d18d92fb9c4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191204"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a>DNS レコードを管理するときにOffice 365 DNS レコードを作成する

メール ルーティングに必要な MX レコードなど、21Vianet が運用する Office 365 の DNS レコードを作成する方法の詳細については、「Office 365 の任意の DNS ホスティング プロバイダーで DNS レコードを作成する[」を参照してください](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。 
  
  
その他のオプションと注意点:
      
-  ドメインの DNS ホスティング プロバイダーまたはドメイン レジストラーがわからない場合は、「[ドメイン レジストラーまたは DNS ホスティング プロバイダーを探す](../get-help-with-domains/find-your-domain-registrar.md)」を参照してください。 DNS レコードの機能の詳細については、「DNS の基本」 [を参照してください](../get-help-with-domains/dns-basics.md)。
    
-  一部の DNS ホスティング プロバイダーでは、必要なすべてのレコードの種類を作成できないので、ホスティング プロバイダーが [SRV、CNAME、TXT、](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)またはリダイレクトをサポートしていない場合にサービスの制限が発生します。 プロバイダーが SRV、TXT、または CNAME レコードをサポートしない場合は、必要[](../get-help-with-domains/buy-a-domain-name.md)なすべてのレコードの種類をサポートするプロバイダーにドメインを[転送することをお勧めします](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)。 
    
- 必要な DNS レコードを確認し、電子メールの MX レコードを含む各レコードに使用する値を見つけるには、「DNS レコードを作成するために必要な情報を収集する」を参照Office 365[してください](../get-help-with-domains/information-for-dns-records.md)。 DNS レコードの機能の詳細については、「DNS の基本」 [を参照してください](../get-help-with-domains/dns-basics.md)。
