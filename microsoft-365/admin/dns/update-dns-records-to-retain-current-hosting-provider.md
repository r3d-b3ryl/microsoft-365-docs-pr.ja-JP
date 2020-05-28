---
title: DNS レコードを更新して現在のホスティング プロバイダーに Web サイトを維持する
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: カスタムドメインの DNS レコードを管理するように Microsoft を設定している場合は、Microsoft 外でホストされている既存のパブリック web サイトにトラフィックをルーティングする方法について説明します。
ms.openlocfilehash: c33dd9253da2e8833ec6ae4693be34739b31ea63
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400222"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="7d4e1-103">DNS レコードを更新して現在のホスティング プロバイダーに Web サイトを維持する</span><span class="sxs-lookup"><span data-stu-id="7d4e1-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="7d4e1-104">**DNS ホスティングプロバイダーでドメインの Microsoft レコードを管理する場合**は、このトピックの手順について心配する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="7d4e1-105">Web サイトは現在の状態のままで、引き続きサイトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="7d4e1-106">Microsoft が**DNS レコードを管理している場合**、microsoft の外部でホストされている既存のパブリック web サイトにトラフィックをルーティングするには、ドメインを microsoft に追加した後、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="7d4e1-107">Microsoft 365 管理センターで DNS レコードを更新する</span><span class="sxs-lookup"><span data-stu-id="7d4e1-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="7d4e1-108">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="7d4e1-109">[ **ドメイン** ] ページで、ドメインの一覧から、Web サイトで使用しているドメインを選択し、管理ウィンドウで [ **DNS 設定** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-109">On the **Domains** page, in the list of domains, select the domain you're using for your website, and then select **DNS settings** in the management pane.</span></span> 
    
3. <span data-ttu-id="7d4e1-110">[**+ 新しいカスタム レコード**] を選択し、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-110">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="7d4e1-111">[ **DNS の種類** ] には、「 **A (アドレス)** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-111">For **DNS type** enter: **A (Address)**</span></span>
    
  - <span data-ttu-id="7d4e1-112">[ **ホスト名またはエイリアス** ] には、「 **@** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-112">For **Host name or Alias**, type the following: **@**</span></span>
    
  - <span data-ttu-id="7d4e1-113">[ **IP アドレス** ] には、Web サイトが現在ホストされている場所の静的 IP アドレス (たとえば、172.16.140.1) を入力します。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
    <span data-ttu-id="7d4e1-p102">これは、Web サイトの *動的*  IP アドレスではなく、  *静的*  IP アドレスでなければなりません。 Web サイトがホストされているサイトで、一般向け Web サイトの静的 IP アドレスを取得できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
3. <span data-ttu-id="7d4e1-116">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-116">Select **Save**.</span></span> 
    
<span data-ttu-id="7d4e1-117">さらに、CNAME レコードを作成して、Web サイトを顧客が簡単に見つけることができるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="7d4e1-118">[ **+ 新しいカスタム レコード** ] を選択し、次の項目を入力します。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-118">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="7d4e1-119">[ **DNS の種類** ] には、「 **CNAME (エイリアス)** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-119">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
  - <span data-ttu-id="7d4e1-120">[ **ホスト名またはエイリアス** ] には、「 **www** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-120">For **Host name or Alias**, type the following: **www**</span></span>
    
  - <span data-ttu-id="7d4e1-121">[ **ポイント先のアドレス** ] には、Web サイトの完全修飾ドメイン名 (FQDN) を入力します (例: contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="7d4e1-122">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-122">Select **Save**.</span></span> 
    
<span data-ttu-id="7d4e1-123">最後に、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-123">Finally, do the following:</span></span>
  
<span data-ttu-id="7d4e1-124">Microsoft を参照するように[、ドメインの NS レコードを更新](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)します。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-124">[Update your domain's NS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to point to Microsoft.</span></span> 
  
<span data-ttu-id="7d4e1-125">NS レコードが Microsoft を指すように更新されている場合、ドメインはすべて設定されています。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-125">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="7d4e1-126">メールは Microsoft にルーティングされ、web サイトのアドレスへのトラフィックは引き続き現在の web サイトのホストに送られます。</span><span class="sxs-lookup"><span data-stu-id="7d4e1-126">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
 
