---
title: カスタム ドメインを使うように電子メール アドレスを変更する
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
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: '最初のメール アドレスを、メール アドレスのような使い方の良いメール アドレスにtom@fourthcoffee.com。 これを行うには、ドメイン名を購入し、Microsoft 365 に追加する必要があります。 '
ms.openlocfilehash: 445b78f759cee79a794f9656afd5b26051534e26
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114023"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a><span data-ttu-id="e66e9-104">カスタム ドメインを使うように電子メール アドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="e66e9-104">Change your email address to use your custom domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e66e9-105">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="e66e9-105">The admin center is changing.</span></span> <span data-ttu-id="e66e9-106">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e66e9-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

 <span data-ttu-id="e66e9-107">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e66e9-107">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="e66e9-108">Microsoft 365 の最初のメール アドレスには、次のような .onmicrosoft.com が含tom@fourthcoffee.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="e66e9-108">Your initial email address in Microsoft 365 includes .onmicrosoft.com, like tom@fourthcoffee.onmicrosoft.com.</span></span> <span data-ttu-id="e66e9-109">これを tom@fourthcoffee.com のようなわかりやすいアドレスに変更できます。</span><span class="sxs-lookup"><span data-stu-id="e66e9-109">You can change it to a friendlier address like tom@fourthcoffee.com.</span></span> <span data-ttu-id="e66e9-110">このためには、自分のドメイン (例: fourthcoffee.com) を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e66e9-110">You'll need your own domain name, like fourthcoffee.com first.</span></span> <span data-ttu-id="e66e9-111">既に持っている場合は、それをご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="e66e9-111">If you already have one, great!</span></span> <span data-ttu-id="e66e9-112">持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e66e9-112">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="e66e9-113">Office 365 Germany の最初のメール アドレスには、次のような .onmicrosoft.de が含tom@fourthcoffee.onmicrosoft.de。</span><span class="sxs-lookup"><span data-stu-id="e66e9-113">Your initial email address in Office 365 Germany includes .onmicrosoft.de, like tom@fourthcoffee.onmicrosoft.de.</span></span> <span data-ttu-id="e66e9-114">このアドレスは、次のような分tom@fourthcoffee.de。</span><span class="sxs-lookup"><span data-stu-id="e66e9-114">You can change it to a friendlier address like tom@fourthcoffee.de.</span></span> <span data-ttu-id="e66e9-115">最初に作成したドメイン名など、独自のfourthcoffee.deがあります。</span><span class="sxs-lookup"><span data-stu-id="e66e9-115">You'll need your own domain name, like fourthcoffee.de first.</span></span> <span data-ttu-id="e66e9-116">既に持っている場合は、それをご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="e66e9-116">If you already have one, great!</span></span> <span data-ttu-id="e66e9-117">持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e66e9-117">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="e66e9-118">21Vianet が運用している Office 365 の初期メール アドレスには、次のようなpartner.onmschina.cnが含tom@fourthcoffee.partner.onmschina.cn。</span><span class="sxs-lookup"><span data-stu-id="e66e9-118">Your initial email address in Office 365 operated by 21Vianet includes partner.onmschina.cn, like tom@fourthcoffee.partner.onmschina.cn.</span></span> <span data-ttu-id="e66e9-119">このアドレスは、次のような分tom@fourthcoffee.cn。</span><span class="sxs-lookup"><span data-stu-id="e66e9-119">You can change it to a friendlier address like tom@fourthcoffee.cn.</span></span> <span data-ttu-id="e66e9-120">最初に作成したドメイン名など、独自のドメインfourthcoffee.cnがあります。</span><span class="sxs-lookup"><span data-stu-id="e66e9-120">You'll need your own domain name, like fourthcoffee.cn first.</span></span> <span data-ttu-id="e66e9-121">既に持っている場合は、それをご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="e66e9-121">If you already have one, great!</span></span> <span data-ttu-id="e66e9-122">持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e66e9-122">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

<span data-ttu-id="e66e9-123">セットアップ中にドメインの MX レコードを更新して、ドメインの電子メールを Microsoft 365 に届く設定に変更すると、そのドメインに送信されたメールはすべて Microsoft 365 に届く開始されます。</span><span class="sxs-lookup"><span data-stu-id="e66e9-123">When you change your domain's email to come to Microsoft 365, by updating your domain's MX record during setup, ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="e66e9-124">MX レコードを変更する前に、ドメインにメールを持つすべてのユーザーのユーザーが追加され、Microsoft 365 にメールボックスが作成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e66e9-124">Make sure you've added users and created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span> <span data-ttu-id="e66e9-125">ドメイン上のすべてのユーザーのメールを Microsoft 365 に移動したくない場合</span><span class="sxs-lookup"><span data-stu-id="e66e9-125">Don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="e66e9-126">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="e66e9-126">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide).</span></span>
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a><span data-ttu-id="e66e9-127">Microsoft 365 管理センターを使用してカスタム ドメインを使用するメール アドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="e66e9-127">Change your email address to use your custom domain using the Microsoft 365 admin center</span></span>

<span data-ttu-id="e66e9-128">これらの手順を実行するには、グローバル管理者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="e66e9-128">You must have a global admin account to perform these steps.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e66e9-129"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e66e9-129">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <span data-ttu-id="e66e9-130"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e66e9-130">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span> 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e66e9-131">管理センターに移動します<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>。</span><span class="sxs-lookup"><span data-stu-id="e66e9-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>.</span></span> 

::: moniker-end 

2. <span data-ttu-id="e66e9-132">[セットアップ ドメイン **]**  >  **ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="e66e9-132">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="e66e9-133">[**ドメイン**] ページで、[**ドメインの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e66e9-133">On the **Domains** page, select **Add domain**.</span></span>
    
4. <span data-ttu-id="e66e9-134">自分がドメインを所有していることを確認して、メール アドレスを変更する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e66e9-134">Follow the steps to confirm that you own your domain and to change your email address.</span></span>
    
<span data-ttu-id="e66e9-135">Microsoft 365 でドメインに合った設定を正しく行うガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e66e9-135">You'll be guided to get everything set up correctly with your domain in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="e66e9-136">Exchange ライセンスを使用していない場合は、ドメインを使用して Microsoft 365 テナントとの間で電子メールを送受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="e66e9-136">If you are not using an Exchange license, you cannot use the domain to send or receive emails from the Microsoft 365 tenant.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="e66e9-137">関連記事</span><span class="sxs-lookup"><span data-stu-id="e66e9-137">Related articles</span></span>

[<span data-ttu-id="e66e9-138">Microsoft 365 を使用してカスタム ドメインを購入する</span><span class="sxs-lookup"><span data-stu-id="e66e9-138">Buy a custom domain using Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)
 
