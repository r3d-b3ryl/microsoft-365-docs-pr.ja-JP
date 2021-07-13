---
title: DNS レコードを作成するために必要な情報を収集する
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: ドメインをサブスクリプションに接続するために DNS レコードを作成するために必要な値Microsoft 365します。
ms.openlocfilehash: c9869444da2ccb7f96ee01576d966767681c5b49
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393885"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="5491a-103">DNS レコードを作成するために必要な情報を収集する</span><span class="sxs-lookup"><span data-stu-id="5491a-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="5491a-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5491a-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="5491a-105">手順 1: TXT レコード値を検索して確認する</span><span class="sxs-lookup"><span data-stu-id="5491a-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5491a-106">[ドメイン] Microsoft 365 管理センター[ドメイン]**ページ設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="5491a-106">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5491a-107">管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="5491a-107">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5491a-108">管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="5491a-108">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="5491a-109">[ドメイン **] ページで** ドメインを選択し、[セットアップの開始] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5491a-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="5491a-110">追加する必要がある特定の値を確認するには、ドメインのセットアップ ウィザードに戻ります。</span><span class="sxs-lookup"><span data-stu-id="5491a-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="5491a-111">[ドメイン **検証] ページで** 、[ **ドメインの DNS** レコードに TXT レコードを追加する] を選択し、[続行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5491a-111">On the **Domain Verification** page, select **Add a TXT record to the domain's DNS records**, then select **Continue**.</span></span>
    
4. <span data-ttu-id="5491a-112">表示されている **TXT 値をコピー** します。</span><span class="sxs-lookup"><span data-stu-id="5491a-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="5491a-113">**MS=msXXXXXXXX は次のように見えます**。</span><span class="sxs-lookup"><span data-stu-id="5491a-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="5491a-114">[DNS レコード [の追加]](create-dns-records-at-any-dns-hosting-provider.md)に移動してドメインを接続し、DNS ホストの Web サイトでレコードを追加する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5491a-114">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>
    
6. <span data-ttu-id="5491a-115">DNS ホストで TXT レコード (または MX レコード) を作成する手順に従って、ドメインをドメインに戻Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5491a-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="5491a-116">ドメインがドメインで確認された後、DNS ホストから TXT レコード (または MX レコード) をMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="5491a-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="5491a-117">手順 2: メールの MX レコード値を検索する</span><span class="sxs-lookup"><span data-stu-id="5491a-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5491a-118">[ドメイン] Microsoft 365 管理センター[ドメイン]**ページ設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="5491a-118">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="5491a-119">管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="5491a-119">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5491a-120">管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="5491a-120">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="5491a-121">[ **ドメイン**] ページで、ドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="5491a-121">On the **Domains** page, select your domain.</span></span>
    
3. <span data-ttu-id="5491a-122">[DNS **の管理]** を選択し、[その他 **のオプション]** 独自の DNS を追加し、[続行] を選択して追加する  >  DNS レコードを表示します。 </span><span class="sxs-lookup"><span data-stu-id="5491a-122">Choose  **Manage DNS**, select **More Options** > **Add your own DNS** and select **Continue** to see the DNS records to add.</span></span>
    
    <span data-ttu-id="5491a-123">DNS ホストで変更を行う際もこの情報を使用できるように、値をコピーして貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="5491a-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="5491a-124">このページにリストされる DNS レコードのグループは、[ **ドメインの目的**] における選択によって変わります。</span><span class="sxs-lookup"><span data-stu-id="5491a-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="5491a-125">[DNS レコード [の追加]](create-dns-records-at-any-dns-hosting-provider.md)に移動してドメインを接続し、DNS ホストの Web サイトでレコードを追加する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5491a-125">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>

5. <span data-ttu-id="5491a-126">手順に従って、DNS ホストでレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="5491a-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="5491a-127">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="5491a-127">Related content</span></span>

<span data-ttu-id="5491a-128">[ドメインの FAQ](../setup/domains-faq.yml) (記事)</span><span class="sxs-lookup"><span data-stu-id="5491a-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>\
<span data-ttu-id="5491a-129">[ドメインまたは DNS レコードを追加後に問題を特定して解決する](find-and-fix-issues.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="5491a-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="5491a-130">[ドメインの管理](index.yml) (リンク ページ)</span><span class="sxs-lookup"><span data-stu-id="5491a-130">[Manage domains](index.yml) (link page)</span></span>