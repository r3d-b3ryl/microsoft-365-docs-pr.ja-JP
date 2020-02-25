---
title: Office 365 の DNS レコードの作成に必要な情報を収集する
f1.keywords:
- NOCSH
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Office 365 の DNS レコードを作成するために必要な値と情報を検索する方法について説明します。 '
ms.custom: okr_smb
ms.openlocfilehash: 7b995aedc21305367e4a6621781e138d0d60efd1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255085"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a><span data-ttu-id="55c32-103">Office 365 の DNS レコードの作成に必要な情報を収集する</span><span class="sxs-lookup"><span data-stu-id="55c32-103">Gather the information you need to create Office 365 DNS records</span></span>

 <span data-ttu-id="55c32-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55c32-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="55c32-105">手順 1: TXT レコード値を検索して確認する</span><span class="sxs-lookup"><span data-stu-id="55c32-105">Step 1: Find the TXT record value and verify</span></span>

1. <span data-ttu-id="55c32-106">Microsoft 365 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**セットアップ** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="55c32-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="55c32-107">Office 365 Germany を使用している場合は、この [<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">ドメイン</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="55c32-107">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="55c32-108">21Vianet が運営する Office 365 を使用している場合は、この [<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">ドメイン</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="55c32-108">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="55c32-109">[**ドメイン**] ページで、ドメインを選択し、[**セットアップの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="55c32-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="55c32-110">追加する必要がある特定の値を確認するには、ドメインのセットアップ ウィザードに戻ります。</span><span class="sxs-lookup"><span data-stu-id="55c32-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="55c32-111">[**ドメインの確認**] ページで、[**代わりに TXT レコードを追加する**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="55c32-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="55c32-112">表示されている**TXT 値**をコピーします。</span><span class="sxs-lookup"><span data-stu-id="55c32-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="55c32-113">次のようになります。 **MS = msXXXXXXXX**。</span><span class="sxs-lookup"><span data-stu-id="55c32-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="55c32-114">「[任意の dns ホスティングプロバイダーで dns レコードを作成](create-dns-records-at-any-dns-hosting-provider.md)する」に移動し、レジストラーのリストから dns ホストを選択し、手順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="55c32-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="55c32-115">DNS ホストで TXT レコード (または MX レコード) を作成する手順を実行し、Office 365 でドメインを確認します。</span><span class="sxs-lookup"><span data-stu-id="55c32-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Office 365.</span></span>

7. <span data-ttu-id="55c32-116">Office 365 でドメインが検証されたら、DNS ホストから TXT レコード (または MX レコード) を削除します。</span><span class="sxs-lookup"><span data-stu-id="55c32-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Office 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="55c32-117">手順 2: メールの MX レコード値を検索する</span><span class="sxs-lookup"><span data-stu-id="55c32-117">Step 2: Find the MX record value for email and more</span></span>

1. <span data-ttu-id="55c32-118">Microsoft 365 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**セットアップ** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="55c32-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="55c32-119">Office 365 Germany を使用している場合は、この [<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">ドメイン</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="55c32-119">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="55c32-120">21Vianet が運営する Office 365 を使用している場合は、この [<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">ドメイン</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="55c32-120">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="55c32-121">[ **ドメイン**] ページで、ドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="55c32-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="55c32-122">[ **必要な DNS 設定**] に、追加する DNS レコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="55c32-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="55c32-123">DNS ホストで変更を行う際もこの情報を使用できるように、値をコピーして貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="55c32-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="55c32-124">このページにリストされる DNS レコードのグループは、[ **ドメインの目的**] における選択によって変わります。</span><span class="sxs-lookup"><span data-stu-id="55c32-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="55c32-125">「[任意の dns ホスティングプロバイダーで dns レコードを作成](create-dns-records-at-any-dns-hosting-provider.md)する」に移動して、レジストラーのリストから dns ホストを選択し、その dns ホストの web サイトにレコードを追加するための手順を順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="55c32-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="55c32-126">手順に従って、DNS ホストでレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="55c32-126">Follow the steps for creating the records at your DNS host.</span></span>
