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
localization_priority: Normal
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
ms.openlocfilehash: 1eaa2bcc7263eaa12e53131246abd591006b0536
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914356"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="82701-103">DNS レコードを管理するときにOffice 365 DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="82701-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="82701-104">メール ルーティングに必要な MX レコードなど、21Vianet が運用する Office 365 の DNS レコードを作成する方法の詳細については、「Office 365 の任意の DNS ホスティング プロバイダーで DNS レコードを作成する[」を参照してください](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="82701-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="82701-105">その他のオプションと注意点:</span><span class="sxs-lookup"><span data-stu-id="82701-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="82701-106">ドメインの DNS ホスティング プロバイダーまたはドメイン レジストラーがわからない場合は、「[ドメイン レジストラーまたは DNS ホスティング プロバイダーを探す](../get-help-with-domains/find-your-domain-registrar.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82701-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="82701-107">DNS レコードの機能の詳細については、「DNS の基本」 [を参照してください](../get-help-with-domains/dns-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="82701-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="82701-108">一部の DNS ホスティング プロバイダーでは、必要なすべてのレコードの種類を作成できないので、ホスティング プロバイダーが [SRV、CNAME、TXT、](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)またはリダイレクトをサポートしていない場合にサービスの制限が発生します。</span><span class="sxs-lookup"><span data-stu-id="82701-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="82701-109">プロバイダーが SRV、TXT、または CNAME レコードをサポートしない場合は、必要[](../get-help-with-domains/buy-a-domain-name.md)なすべてのレコードの種類をサポートするプロバイダーにドメインを[転送することをお勧めします](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)。</span><span class="sxs-lookup"><span data-stu-id="82701-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](../get-help-with-domains/buy-a-domain-name.md) to a [provider that supports all required record types](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="82701-110">必要な DNS レコードを確認し、電子メールの MX レコードを含む各レコードに使用する値を見つけるには、「DNS レコードを作成するために必要な情報を収集する」を参照Office 365[してください](../get-help-with-domains/information-for-dns-records.md)。</span><span class="sxs-lookup"><span data-stu-id="82701-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](../get-help-with-domains/information-for-dns-records.md).</span></span> <span data-ttu-id="82701-111">DNS レコードの機能の詳細については、「DNS の基本」 [を参照してください](../get-help-with-domains/dns-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="82701-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
