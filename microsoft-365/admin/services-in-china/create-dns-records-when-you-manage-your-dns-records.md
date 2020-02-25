---
title: DNS レコードを管理するときに Office 365 の DNS レコードを作成する
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'DNS レコードを管理するときに21Vianet が運用する Office 365 の DNS レコードを作成する方法について説明します。 '
monikerRange: o365-21vianet
ms.openlocfilehash: 1f7b8330b45d6704d2d56b2c68cfcd37de84207a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257094"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a>DNS レコードを管理するときに Office 365 の DNS レコードを作成する

メールのルーティングに必要な MX レコードなど、21Vianet が運用している Office 365 用の DNS レコードを作成する方法の詳細については、「[任意の dns ホスティングプロバイダーで office 365 用](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)の dns レコードを作成する」を参照してください。 
  
  
その他のオプションと注意事項:
      
-  ドメインの DNS ホスティング プロバイダーまたはドメイン レジストラーがわからない場合は、「[ドメイン レジストラーまたは DNS ホスティング プロバイダーを探す](../get-help-with-domains/find-your-domain-registrar.md)」を参照してください。 DNS レコードの機能の詳細については、「 [dns の基礎](../get-help-with-domains/dns-basics.md)」を参照してください。
    
-  DNS ホスティングプロバイダーによっては、必要なすべてのレコードの種類を作成できない場合があります。これにより、[ホスティングプロバイダーが SRV、CNAME、TXT、またはリダイレクトをサポートしていない場合にサービスの制限](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)が発生します。 プロバイダーが SRV、TXT、CNAME のレコードをサポートしていない場合は、[必要なすべてのレコードの種類をサポートするプロバイダー](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)に[ドメインを転送](https://support.office.com/article/a6689b24-eeca-41f1-afe6-19917936b73c.aspx)することをお勧めします。 
    
- 必要な DNS レコードを確認し、各レコードに対して使用する値 (電子メールの MX レコードなど) を検索するには、「 [Office 365 の dns レコードの作成に必要な情報を収集](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)する」を参照してください。 DNS レコードの機能の詳細については、「 [dns の基礎](../get-help-with-domains/dns-basics.md)」を参照してください。
    

