---
title: DNS レコードの作成に必要な情報を収集する
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Microsoft 365 の DNS レコードを作成するために必要な値/情報を見つける方法について説明します。 '
ms.openlocfilehash: 45994139b11a2fd5a03b2e979dd6af334bc1f00b
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126373"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="a727c-103">DNS レコードの作成に必要な情報を収集する</span><span class="sxs-lookup"><span data-stu-id="a727c-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="a727c-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a727c-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="a727c-105">手順 1: TXT レコードの値を検索して確認する</span><span class="sxs-lookup"><span data-stu-id="a727c-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a727c-106">Microsoft 365 管理センターで、[セットアップ ドメイン] **ページ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">に移動</a> します。</span><span class="sxs-lookup"><span data-stu-id="a727c-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a727c-107">管理センターで、[セットアップ ドメイン] **ページ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">に移動</a> します。</span><span class="sxs-lookup"><span data-stu-id="a727c-107">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a727c-108">管理センターで、[セットアップ ドメイン] **ページ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">に移動</a> します。</span><span class="sxs-lookup"><span data-stu-id="a727c-108">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="a727c-109">On the **Domains** page, select your domain, then select **Start setup**.</span><span class="sxs-lookup"><span data-stu-id="a727c-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="a727c-110">追加する必要がある特定の値を確認するには、ドメインのセットアップ ウィザードに戻ります。</span><span class="sxs-lookup"><span data-stu-id="a727c-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="a727c-111">[ドメイン **の確認] ページで** 、代わりに **[TXT レコード** の追加] を選択し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="a727c-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="a727c-112">表示された **TXT 値をコピー** します。</span><span class="sxs-lookup"><span data-stu-id="a727c-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="a727c-113">**MS=msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="a727c-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="a727c-114">任意の DNS ホスティング [プロバイダーで DNS](create-dns-records-at-any-dns-hosting-provider.md)レコードを作成するに移動し、レジストラーの一覧から DNS ホストを選択して、詳しい手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="a727c-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="a727c-115">DNS ホストで TXT レコード (または MX レコード) を作成する手順に従い、Microsoft 365 でドメインを確認します。</span><span class="sxs-lookup"><span data-stu-id="a727c-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="a727c-116">ドメインが Microsoft 365 で確認された後、DNS ホストから TXT レコード (または MX レコード) を削除します。</span><span class="sxs-lookup"><span data-stu-id="a727c-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="a727c-117">手順 2: メールの MX レコード値を検索する</span><span class="sxs-lookup"><span data-stu-id="a727c-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a727c-118">Microsoft 365 管理センターで、[セットアップ ドメイン] **ページ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">に移動</a> します。</span><span class="sxs-lookup"><span data-stu-id="a727c-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="a727c-119">管理センターで、[セットアップ ドメイン] **ページ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">に移動</a> します。</span><span class="sxs-lookup"><span data-stu-id="a727c-119">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a727c-120">管理センターで、[セットアップ ドメイン] **ページ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">に移動</a> します。</span><span class="sxs-lookup"><span data-stu-id="a727c-120">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="a727c-121">[ **ドメイン**] ページで、ドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="a727c-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="a727c-122">[ **必要な DNS 設定**] に、追加する DNS レコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a727c-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="a727c-123">DNS ホストで変更を行う際もこの情報を使用できるように、値をコピーして貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="a727c-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="a727c-124">このページにリストされる DNS レコードのグループは、[ **ドメインの目的**] における選択によって変わります。</span><span class="sxs-lookup"><span data-stu-id="a727c-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="a727c-125">任意の DNS ホスティング プロバイダーで [DNS](create-dns-records-at-any-dns-hosting-provider.md)レコードを作成するに移動し、レジストラーの一覧から DNS ホストを選択して、その DNS ホストの Web サイトでレコードを追加する手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="a727c-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="a727c-126">手順に従って、DNS ホストでレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="a727c-126">Follow the steps for creating the records at your DNS host.</span></span>
