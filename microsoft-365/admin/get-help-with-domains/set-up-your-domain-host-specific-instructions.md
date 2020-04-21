---
title: ドメインを設定する (ホストに固有の手順)
f1.keywords:
- NOCSH
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
- Adm_TOC
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: 独自の DNS レコードを管理する方法や、Microsoft が DNS レコードを管理できるようにする方法について説明します。
ms.custom: okr_smb
ms.openlocfilehash: ea3a62c048706f36cd7b1590851d8b372e0a1677
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628424"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="4a1c1-103">ドメインを設定する (ホストに固有の手順)</span><span class="sxs-lookup"><span data-stu-id="4a1c1-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="4a1c1-104">Office 365 でカスタムドメイン (contoso.com) の使用を開始するには、ドメインを確認して、ドメインの DNS レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a1c1-104">To start using a custom domain (contoso.com) with Office 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="4a1c1-105">ドメインホストの管理ツールを使用して DNS レコードを追加および管理するか、またはドメインレコードの Microsoft コントロールを付与することができます。</span><span class="sxs-lookup"><span data-stu-id="4a1c1-105">You can add and manage DNS records using the administrative tools at your domain host, or give Microsoft control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="4a1c1-106">正確な手順については、以下のドメインホストを選択してください。</span><span class="sxs-lookup"><span data-stu-id="4a1c1-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="4a1c1-107">ホストの場所がわからない場合は、「[ドメインレジストラーを検索](find-your-domain-registrar.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a1c1-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-office-365-manage-your-dns-records"></a><span data-ttu-id="4a1c1-108">Office 365 で DNS レコードを管理できるようにする</span><span class="sxs-lookup"><span data-stu-id="4a1c1-108">Let Office 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="4a1c1-109">1&IONOS</span><span class="sxs-lookup"><span data-stu-id="4a1c1-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="4a1c1-110">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="4a1c1-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="4a1c1-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="4a1c1-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="4a1c1-112">Google ドメイン</span><span class="sxs-lookup"><span data-stu-id="4a1c1-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="4a1c1-113">Hostgator</span><span class="sxs-lookup"><span data-stu-id="4a1c1-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="4a1c1-114">,</span><span class="sxs-lookup"><span data-stu-id="4a1c1-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="4a1c1-115">Namecheap</span><span class="sxs-lookup"><span data-stu-id="4a1c1-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="4a1c1-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="4a1c1-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="4a1c1-117">または、すべての[ドメインレジストラーで Office 365 をセットアップするためにネームサーバーを変更](change-nameservers-at-any-domain-registrar.md)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a1c1-117">Or, learn how to [change nameservers to set up Office 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="4a1c1-118">自分の DNS レコードを管理する</span><span class="sxs-lookup"><span data-stu-id="4a1c1-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="4a1c1-119">1&IONOS</span><span class="sxs-lookup"><span data-stu-id="4a1c1-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="4a1c1-120">Hover</span><span class="sxs-lookup"><span data-stu-id="4a1c1-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="4a1c1-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="4a1c1-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="4a1c1-122">Google による管理 (eNom)</span><span class="sxs-lookup"><span data-stu-id="4a1c1-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="4a1c1-123">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="4a1c1-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="4a1c1-124">,</span><span class="sxs-lookup"><span data-stu-id="4a1c1-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="4a1c1-125">Azure DNS ゾーン</span><span class="sxs-lookup"><span data-stu-id="4a1c1-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="4a1c1-126">name.com</span><span class="sxs-lookup"><span data-stu-id="4a1c1-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="4a1c1-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="4a1c1-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="4a1c1-128">Namecheap</span><span class="sxs-lookup"><span data-stu-id="4a1c1-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="4a1c1-129">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="4a1c1-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="4a1c1-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="4a1c1-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="4a1c1-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="4a1c1-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="4a1c1-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="4a1c1-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="4a1c1-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="4a1c1-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="4a1c1-134">ネットワークソリューション</span><span class="sxs-lookup"><span data-stu-id="4a1c1-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="4a1c1-135">Dreamhost</span><span class="sxs-lookup"><span data-stu-id="4a1c1-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="4a1c1-136">OVH</span><span class="sxs-lookup"><span data-stu-id="4a1c1-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="4a1c1-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="4a1c1-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="4a1c1-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="4a1c1-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="4a1c1-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="4a1c1-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="4a1c1-140">Register365 for Office 365</span><span class="sxs-lookup"><span data-stu-id="4a1c1-140">Register365 for Office 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="4a1c1-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="4a1c1-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="4a1c1-142">web.com</span><span class="sxs-lookup"><span data-stu-id="4a1c1-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="4a1c1-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="4a1c1-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="4a1c1-144">Windows ベースの DNS</span><span class="sxs-lookup"><span data-stu-id="4a1c1-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="4a1c1-145">Google Domains</span><span class="sxs-lookup"><span data-stu-id="4a1c1-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="4a1c1-146">Wix</span><span class="sxs-lookup"><span data-stu-id="4a1c1-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="4a1c1-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="4a1c1-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="4a1c1-148">Yahoo!  小規模企業</span><span class="sxs-lookup"><span data-stu-id="4a1c1-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="4a1c1-149">ドメインホストがこの一覧にはないため、一般的な手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="4a1c1-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   
