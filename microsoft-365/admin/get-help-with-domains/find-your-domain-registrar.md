---
title: Office 365 のドメイン レジストラーを探す
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: InterNIC 検索を使用して、ドメイン レジストラーと DNS ホスティング プロバイダーを探す方法を説明します。
ms.openlocfilehash: 058eb4468e073b6929fbc763b3d9bdb189063213
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255133"
---
# <a name="find-your-domain-registrar-for-office-365"></a><span data-ttu-id="462bb-103">Office 365 のドメイン レジストラーを探す</span><span class="sxs-lookup"><span data-stu-id="462bb-103">Find your domain registrar for Office 365</span></span>

 <span data-ttu-id="462bb-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462bb-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="462bb-105">ドメイン レジストラー</span><span class="sxs-lookup"><span data-stu-id="462bb-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="462bb-106">ドメイン名登録業者を探す</span><span class="sxs-lookup"><span data-stu-id="462bb-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="462bb-107">*.COM*、*.NET*、および *.EDU* で終わるドメインのみがこのツールで動作します。</span><span class="sxs-lookup"><span data-stu-id="462bb-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="462bb-108">[InterNIC の検索ページ](https://go.microsoft.com/fwlink/p/?LinkId=402770)の [**Whois Search**] ボックスに、ドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="462bb-108">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="462bb-109">たとえば、 *contoso.com のように入力します。*</span><span class="sxs-lookup"><span data-stu-id="462bb-109">For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="462bb-110">[**Domain**] オプションを選択し、[ **Submit**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="462bb-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="462bb-111">[ **Whois Search Results**] ページで [ **Registrar**] エントリを探します。</span><span class="sxs-lookup"><span data-stu-id="462bb-111">On the **Whois Search Results** page, locate the **Registrar** entry.</span></span> <span data-ttu-id="462bb-112">このエントリには、ドメインに対してレジストラー サービスを提供している組織が表示されます。</span><span class="sxs-lookup"><span data-stu-id="462bb-112">This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="462bb-113">DNS ホスティング プロバイダー</span><span class="sxs-lookup"><span data-stu-id="462bb-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="462bb-114">DNS ホスティング プロバイダーを探す</span><span class="sxs-lookup"><span data-stu-id="462bb-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="462bb-115">*.COM*、*.NET*、および *.EDU* で終わるドメインのみがこのツールで動作します。</span><span class="sxs-lookup"><span data-stu-id="462bb-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="462bb-116">[InterNIC の検索ページ]( https://go.microsoft.com/fwlink/p/?LinkId=402770)の [ **Whois Search**] ボックスに、ドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="462bb-116">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="462bb-117">たとえば contoso.com です。</span><span class="sxs-lookup"><span data-stu-id="462bb-117">For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="462bb-118">[**Domain**] オプションを選択し、[ **Submit**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="462bb-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="462bb-119">[**Whois Search Results**] ページで最初の [**Name Server**] エントリを探します。</span><span class="sxs-lookup"><span data-stu-id="462bb-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="462bb-120">コロン (:) の後に表示されるネーム サーバー (NS) 情報をコピーし、ページの先頭にある [ **Search**] ボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="462bb-120">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page.</span></span> <span data-ttu-id="462bb-121">[**Nameserver**] を選択し、[ **Submit**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="462bb-121">Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="462bb-p105">[**Whois Search Results**] ページで [**Registrar**] エントリを探します。このエントリには、DNS ホスティング プロバイダー (ドメインのネーム サーバーを所有している DNS プロバイダー) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="462bb-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---

