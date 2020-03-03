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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: カスタムドメインの DNS レコードを管理するように Office 365 を設定している場合、Office 365 の外部でホストされている既存のパブリック web サイトにトラフィックをルーティングする方法について説明します。
ms.openlocfilehash: b92e778fb2fe0353a0d1d6bf83a4c617ab4541e2
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362412"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="6ebf6-103">DNS レコードを更新して現在のホスティング プロバイダーに Web サイトを維持する</span><span class="sxs-lookup"><span data-stu-id="6ebf6-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="6ebf6-p101">**DNS ホスティング プロバイダーでドメインの Office 365 レコードを管理する場合は** 、このトピックの手順を考慮する必要はありません。Web サイトは現在の状態のままで、引き続きサイトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-p101">**If you manage your domain's Office 365 records at your DNS hosting provider**, you don't have to worry about the steps in this topic. Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="6ebf6-106">**Office 365 が DNS レコードを管理する場合** 、Office 365 の外部でホストされている既存の一般向け Web サイトにトラフィックをルーティングするには、ドメインを Office 365 に追加した後で、次のように操作します。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-106">**If Office 365 manages your DNS records**, to route traffic to an existing public website hosted outside of Office 365, after you add your domain to Office 365, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6ebf6-107">Microsoft 365 管理センターで DNS レコードを更新する</span><span class="sxs-lookup"><span data-stu-id="6ebf6-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="6ebf6-108">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="6ebf6-109">[ **ドメイン** ] ページで、ドメインの一覧から、Web サイトで使用しているドメインを選択し、管理ウィンドウで [ **DNS 設定** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-109">On the **Domains** page, in the list of domains, select the domain you're using for your website, and then select **DNS settings** in the management pane.</span></span> 
    
3. <span data-ttu-id="6ebf6-110">[**+ 新しいカスタム レコード**] を選択し、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-110">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="6ebf6-111">[ **DNS の種類** ] には、「 **A (アドレス)** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-111">For **DNS type** enter: **A (Address)**</span></span>
    
  - <span data-ttu-id="6ebf6-112">[ **ホスト名またはエイリアス** ] には、「 **@** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-112">For **Host name or Alias**, type the following: **@**</span></span>
    
  - <span data-ttu-id="6ebf6-113">[ **IP アドレス** ] には、Web サイトが現在ホストされている場所の静的 IP アドレス (たとえば、172.16.140.1) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
    <span data-ttu-id="6ebf6-p102">これは、Web サイトの *動的*  IP アドレスではなく、  *静的*  IP アドレスでなければなりません。 Web サイトがホストされているサイトで、一般向け Web サイトの静的 IP アドレスを取得できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
3. <span data-ttu-id="6ebf6-116">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-116">Select **Save**.</span></span> 
    
<span data-ttu-id="6ebf6-117">さらに、CNAME レコードを作成して、Web サイトを顧客が簡単に見つけることができるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="6ebf6-118">[ **+ 新しいカスタム レコード** ] を選択し、次の項目を入力します。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-118">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="6ebf6-119">[ **DNS の種類** ] には、「 **CNAME (エイリアス)** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-119">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
  - <span data-ttu-id="6ebf6-120">[ **ホスト名またはエイリアス** ] には、「 **www** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-120">For **Host name or Alias**, type the following: **www**</span></span>
    
  - <span data-ttu-id="6ebf6-121">[ **ポイント先のアドレス** ] には、Web サイトの完全修飾ドメイン名 (FQDN) を入力します (例: contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="6ebf6-122">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-122">Select **Save**.</span></span> 
    
<span data-ttu-id="6ebf6-123">最後に、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-123">Finally, do the following:</span></span>
  
<span data-ttu-id="6ebf6-124">[TE102827792 を指すようにドメインの NS レコードを更新します](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-124">[Update your domain's NS records](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) to point to Office 365.</span></span> 
  
<span data-ttu-id="6ebf6-p103">NS レコードが更新され、Office 365 を指すようになると、ドメインはすべてセットアップ済みです。メールは Office 365 にルーティングされ、Web サイト アドレスへのトラフィックは引き続き現在の Web サイト ホストに流れます。</span><span class="sxs-lookup"><span data-stu-id="6ebf6-p103">When the NS records have been updated to point to Office 365, your domain is all set up. Email will be routed to Office 365, and traffic to your website address will continue to go to your current website host.</span></span>
 
