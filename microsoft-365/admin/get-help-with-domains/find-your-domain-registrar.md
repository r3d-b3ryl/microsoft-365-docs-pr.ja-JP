---
title: ドメイン レジストラーを検索する
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: InterNIC 検索を使用して、ドメイン レジストラーと DNS ホスティング プロバイダーを探す方法を説明します。
ms.openlocfilehash: af883f53c8c45aee2594b0f5b8b9da57e5717f9e
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706396"
---
# <a name="find-your-domain-registrar"></a><span data-ttu-id="fe8ce-103">ドメイン レジストラーを検索する</span><span class="sxs-lookup"><span data-stu-id="fe8ce-103">Find your domain registrar</span></span>

 <span data-ttu-id="fe8ce-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe8ce-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="fe8ce-105">ドメイン レジストラー</span><span class="sxs-lookup"><span data-stu-id="fe8ce-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="fe8ce-106">ドメイン名登録業者を探す</span><span class="sxs-lookup"><span data-stu-id="fe8ce-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="fe8ce-107">*.COM*、*.NET*、および *.EDU* で終わるドメインのみがこのツールで動作します。</span><span class="sxs-lookup"><span data-stu-id="fe8ce-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="fe8ce-p101">[InterNIC の検索ページ](https://go.microsoft.com/fwlink/p/?LinkId=402770)の [**Whois Search**] ボックスに、ドメインを入力します。たとえば、*contoso.com のように入力します。*</span><span class="sxs-lookup"><span data-stu-id="fe8ce-p101">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="fe8ce-110">[**Domain**] オプションを選択し、[**Submit**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe8ce-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="fe8ce-p102">[**Whois Search Results**] ページで [**Registrar**] エントリを探します。このエントリには、ドメインに対してレジストラー サービスを提供している組織が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe8ce-p102">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="fe8ce-113">DNS ホスティング プロバイダー</span><span class="sxs-lookup"><span data-stu-id="fe8ce-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="fe8ce-114">DNS ホスティング プロバイダーを探す</span><span class="sxs-lookup"><span data-stu-id="fe8ce-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="fe8ce-115">*.COM*、*.NET*、および *.EDU* で終わるドメインのみがこのツールで動作します。</span><span class="sxs-lookup"><span data-stu-id="fe8ce-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="fe8ce-p103">[InterNIC の検索ページ]( https://go.microsoft.com/fwlink/p/?LinkId=402770)の [**Whois Search**] ボックスに、ドメインを入力します。たとえば、contoso.com のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fe8ce-p103">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="fe8ce-118">[**Domain**] オプションを選択し、[ **Submit**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe8ce-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="fe8ce-119">[**Whois Search Results**] ページで最初の [**Name Server**] エントリを探します。</span><span class="sxs-lookup"><span data-stu-id="fe8ce-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="fe8ce-p104">コロン (:) の後に表示されるネーム サーバー (NS) 情報をコピーし、ページの先頭にある [**Search**] ボックスに貼り付けます。[**Nameserver**] を選択し、[**Submit**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe8ce-p104">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page. Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="fe8ce-p105">[**Whois Search Results**] ページで [**Registrar**] エントリを探します。このエントリには、DNS ホスティング プロバイダー (ドメインのネーム サーバーを所有している DNS プロバイダー) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe8ce-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---

