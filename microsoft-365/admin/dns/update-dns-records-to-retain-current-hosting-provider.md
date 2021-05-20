---
title: DNS レコードを更新して現在のホスティング プロバイダーに Web サイトを維持する
f1.keywords:
- NOCSH
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
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: カスタム ドメインの DNS レコードを管理するために Microsoft を設定している場合は、Microsoft の外部でホストされている既存のパブリック Web サイトにトラフィックをルーティングする方法について説明します。
ms.openlocfilehash: 2a1559bbb902375bbc363180cdb4f98ec2b3a939
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572143"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="46831-103">DNS レコードを更新して現在のホスティング プロバイダーに Web サイトを維持する</span><span class="sxs-lookup"><span data-stu-id="46831-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="46831-104">**DNS ホスティング プロバイダーで** ドメインの Microsoft レコードを管理する場合は、このトピックの手順について心配する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="46831-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="46831-105">Web サイトは現在の状態のままで、引き続きサイトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="46831-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="46831-106">**Microsoft が DNS レコードを管理** している場合は、ドメインを Microsoft に追加した後、Microsoft の外部でホストされている既存のパブリック Web サイトにトラフィックをルーティングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="46831-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="46831-107">管理センターで DNS レコードMicrosoft 365更新する</span><span class="sxs-lookup"><span data-stu-id="46831-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="46831-108">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="46831-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

1. <span data-ttu-id="46831-109">[ドメイン **] ページで** 、ドメインを選択し、[DNS レコード] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="46831-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

1. <span data-ttu-id="46831-110">[+ **レコードの追加] を選択** し、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="46831-110">Select **+ Add record** and enter the following:</span></span> 
    
   - <span data-ttu-id="46831-111">型 **の** 場合は Enter: **A (Address)**</span><span class="sxs-lookup"><span data-stu-id="46831-111">For **type** enter: **A (Address)**</span></span>
    
   - <span data-ttu-id="46831-112">[ **ホスト名またはエイリアス** ] には、「 **@** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="46831-112">For **Host name or Alias**, type the following: **@**</span></span>
    
   - <span data-ttu-id="46831-113">[ **IP アドレス** ] には、Web サイトが現在ホストされている場所の静的 IP アドレス (たとえば、172.16.140.1) を入力します。</span><span class="sxs-lookup"><span data-stu-id="46831-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
   <span data-ttu-id="46831-p102">これは、Web サイトの *動的*  IP アドレスではなく、  *静的*  IP アドレスでなければなりません。 Web サイトがホストされているサイトで、一般向け Web サイトの静的 IP アドレスを取得できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="46831-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
1. <span data-ttu-id="46831-116">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="46831-116">Select **Save**.</span></span> 
    
<span data-ttu-id="46831-117">さらに、CNAME レコードを作成して、Web サイトを顧客が簡単に見つけることができるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="46831-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="46831-118">[+ **レコードの追加] を選択** し、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="46831-118">Select **+ Add record** and enter the following:</span></span> 
    
   - <span data-ttu-id="46831-119">型 **の** enter: **CNAME (Alias)**</span><span class="sxs-lookup"><span data-stu-id="46831-119">For **type** enter: **CNAME (Alias)**</span></span>
    
   - <span data-ttu-id="46831-120">[ **ホスト名またはエイリアス** ] には、「 **www** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="46831-120">For **Host name or Alias**, type the following: **www**</span></span>
    
   - <span data-ttu-id="46831-121">[ **ポイント先のアドレス** ] には、Web サイトの完全修飾ドメイン名 (FQDN) を入力します (例: contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="46831-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="46831-122">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="46831-122">Select **Save**.</span></span> 
    
<span data-ttu-id="46831-123">最後に、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="46831-123">Finally, do the following:</span></span>
  
<span data-ttu-id="46831-124">[Microsoft を指すドメインの NS](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) レコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="46831-124">[Update your domain's NS records](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to point to Microsoft.</span></span> 
  
<span data-ttu-id="46831-125">NS レコードが Microsoft をポイントするために更新された場合、ドメインはすべてセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="46831-125">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="46831-126">メールは Microsoft にルーティングされ、Web サイトアドレスへのトラフィックは引き続き現在の Web サイトのホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="46831-126">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
