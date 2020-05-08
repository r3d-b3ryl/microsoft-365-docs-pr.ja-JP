---
title: DNS レコードを管理するときに Office 365 の DNS レコードを作成する
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
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
ms.openlocfilehash: f6ba0f891bbc207bf7d56c4527760a5c8caf90b0
ms.sourcegitcommit: d688a296dc2b094b70da55334c9a3ad91236cf6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44155399"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="b79c2-103">DNS レコードを管理するときに Office 365 の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="b79c2-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="b79c2-104">メールのルーティングに必要な MX レコードなど、21Vianet が運用している Office 365 用の DNS レコードを作成する方法の詳細については、「[任意の dns ホスティングプロバイダーで office 365 用](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)の dns レコードを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b79c2-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="b79c2-105">その他のオプションと注意事項:</span><span class="sxs-lookup"><span data-stu-id="b79c2-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="b79c2-106">ドメインの DNS ホスティング プロバイダーまたはドメイン レジストラーがわからない場合は、「[ドメイン レジストラーまたは DNS ホスティング プロバイダーを探す](../get-help-with-domains/find-your-domain-registrar.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b79c2-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="b79c2-107">DNS レコードの機能の詳細については、「 [dns の基礎](../get-help-with-domains/dns-basics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b79c2-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="b79c2-108">DNS ホスティングプロバイダーによっては、必要なすべてのレコードの種類を作成できない場合があります。これにより、[ホスティングプロバイダーが SRV、CNAME、TXT、またはリダイレクトをサポートしていない場合にサービスの制限](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)が発生します。</span><span class="sxs-lookup"><span data-stu-id="b79c2-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="b79c2-109">プロバイダーが SRV、TXT、CNAME のレコードをサポートしていない場合は、[必要なすべてのレコードの種類をサポートするプロバイダー](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)に[ドメインを転送](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name)することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b79c2-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) to a [provider that supports all required record types](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="b79c2-110">必要な DNS レコードを確認し、各レコードに対して使用する値 (電子メールの MX レコードなど) を検索するには、「 [Office 365 の dns レコードの作成に必要な情報を収集](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b79c2-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).</span></span> <span data-ttu-id="b79c2-111">DNS レコードの機能の詳細については、「 [dns の基礎](../get-help-with-domains/dns-basics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b79c2-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    

