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
ms.openlocfilehash: ceef82345e562e2aa4c291f416c454fb831ee45b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915976"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="4dd84-103">DNS レコードを更新して現在のホスティング プロバイダーに Web サイトを維持する</span><span class="sxs-lookup"><span data-stu-id="4dd84-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="4dd84-104">**DNS ホスティング プロバイダーで** ドメインの Microsoft レコードを管理する場合は、このトピックの手順について心配する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4dd84-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="4dd84-105">Web サイトは現在の状態のままで、引き続きサイトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4dd84-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="4dd84-106">**Microsoft が DNS レコードを管理** している場合は、ドメインを Microsoft に追加した後、Microsoft の外部でホストされている既存のパブリック Web サイトにトラフィックをルーティングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4dd84-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="4dd84-107">管理センターで DNS レコードMicrosoft 365更新する</span><span class="sxs-lookup"><span data-stu-id="4dd84-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="4dd84-108">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4dd84-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="4dd84-109">[ドメイン **] ページで** 、ドメインを選択し、[DNS レコード] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4dd84-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="4dd84-110">[DNS **設定] で、[** カスタム レコード **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4dd84-110">Under **DNS settings**, select **Custom Records**.</span></span>

4. <span data-ttu-id="4dd84-111">[ **+ 新しいカスタム レコード** ] を選択し、次の項目を入力します。</span><span class="sxs-lookup"><span data-stu-id="4dd84-111">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="4dd84-112">[ **DNS の種類** ] には、「 **A (アドレス)** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4dd84-112">For **DNS type** enter: **A (Address)**</span></span>
    
   - <span data-ttu-id="4dd84-113">[ **ホスト名またはエイリアス** ] には、「 **@** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4dd84-113">For **Host name or Alias**, type the following: **@**</span></span>
    
   - <span data-ttu-id="4dd84-114">[ **IP アドレス** ] には、Web サイトが現在ホストされている場所の静的 IP アドレス (たとえば、172.16.140.1) を入力します。</span><span class="sxs-lookup"><span data-stu-id="4dd84-114">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
   <span data-ttu-id="4dd84-p102">これは、Web サイトの *動的*  IP アドレスではなく、  *静的*  IP アドレスでなければなりません。 Web サイトがホストされているサイトで、一般向け Web サイトの静的 IP アドレスを取得できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4dd84-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
5. <span data-ttu-id="4dd84-117">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dd84-117">Select **Save**.</span></span> 
    
<span data-ttu-id="4dd84-118">さらに、CNAME レコードを作成して、Web サイトを顧客が簡単に見つけることができるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4dd84-118">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="4dd84-119">[ **+ 新しいカスタム レコード** ] を選択し、次の項目を入力します。</span><span class="sxs-lookup"><span data-stu-id="4dd84-119">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="4dd84-120">[ **DNS の種類** ] には、「 **CNAME (エイリアス)** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4dd84-120">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
   - <span data-ttu-id="4dd84-121">[ **ホスト名またはエイリアス** ] には、「 **www** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4dd84-121">For **Host name or Alias**, type the following: **www**</span></span>
    
   - <span data-ttu-id="4dd84-122">[ **ポイント先のアドレス** ] には、Web サイトの完全修飾ドメイン名 (FQDN) を入力します (例: contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="4dd84-122">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="4dd84-123">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dd84-123">Select **Save**.</span></span> 
    
<span data-ttu-id="4dd84-124">最後に、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4dd84-124">Finally, do the following:</span></span>
  
<span data-ttu-id="4dd84-125">[Microsoft を指すドメインの NS](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) レコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="4dd84-125">[Update your domain's NS records](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to point to Microsoft.</span></span> 
  
<span data-ttu-id="4dd84-126">NS レコードが Microsoft をポイントするために更新された場合、ドメインはすべてセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="4dd84-126">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="4dd84-127">メールは Microsoft にルーティングされ、Web サイトアドレスへのトラフィックは引き続き現在の Web サイトのホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="4dd84-127">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
