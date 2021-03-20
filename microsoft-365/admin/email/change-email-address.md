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
description: '最初の電子メール アドレスを 、ユーザー設定のような使い tom@fourthcoffee.com。 これを行うには、ドメイン名を購入し、Microsoft 365 に追加する必要があります。 '
ms.openlocfilehash: 10dff4e0523062ae763c08a972563dc8b5582038
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915928"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a><span data-ttu-id="f0388-104">カスタム ドメインを使うように電子メール アドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="f0388-104">Change your email address to use your custom domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f0388-105">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="f0388-105">The admin center is changing.</span></span> <span data-ttu-id="f0388-106">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0388-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="f0388-107">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0388-107">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="f0388-108">Microsoft 365 の最初の電子メール アドレスには、次のような .onmicrosoft.com が含 tom@fourthcoffee.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="f0388-108">Your initial email address in Microsoft 365 includes .onmicrosoft.com, like tom@fourthcoffee.onmicrosoft.com.</span></span> <span data-ttu-id="f0388-109">これを tom@fourthcoffee.com のようなわかりやすいアドレスに変更できます。</span><span class="sxs-lookup"><span data-stu-id="f0388-109">You can change it to a friendlier address like tom@fourthcoffee.com.</span></span> <span data-ttu-id="f0388-110">このためには、自分のドメイン (例: fourthcoffee.com) を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0388-110">You'll need your own domain name, like fourthcoffee.com first.</span></span> <span data-ttu-id="f0388-111">既に持っている場合は、それをご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="f0388-111">If you already have one, great!</span></span> <span data-ttu-id="f0388-112">持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0388-112">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="f0388-113">365 ドイツ 365 Officeの最初の電子メール アドレスには、次のような .onmicrosoft.de が tom@fourthcoffee.onmicrosoft.de。</span><span class="sxs-lookup"><span data-stu-id="f0388-113">Your initial email address in Office 365 Germany includes .onmicrosoft.de, like tom@fourthcoffee.onmicrosoft.de.</span></span> <span data-ttu-id="f0388-114">このアドレスは、他のユーザーと同じフレンドリアドレス tom@fourthcoffee.de。</span><span class="sxs-lookup"><span data-stu-id="f0388-114">You can change it to a friendlier address like tom@fourthcoffee.de.</span></span> <span data-ttu-id="f0388-115">最初に使用するドメイン名など、独自の fourthcoffee.de があります。</span><span class="sxs-lookup"><span data-stu-id="f0388-115">You'll need your own domain name, like fourthcoffee.de first.</span></span> <span data-ttu-id="f0388-116">既に持っている場合は、それをご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="f0388-116">If you already have one, great!</span></span> <span data-ttu-id="f0388-117">持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0388-117">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="f0388-118">21Vianet がOffice 365 の初期メール アドレスには、partner.onmschina.cn のような tom@fourthcoffee.partner.onmschina.cn。</span><span class="sxs-lookup"><span data-stu-id="f0388-118">Your initial email address in Office 365 operated by 21Vianet includes partner.onmschina.cn, like tom@fourthcoffee.partner.onmschina.cn.</span></span> <span data-ttu-id="f0388-119">このアドレスは、他のユーザーと同じフレンドリなアドレス tom@fourthcoffee.cn。</span><span class="sxs-lookup"><span data-stu-id="f0388-119">You can change it to a friendlier address like tom@fourthcoffee.cn.</span></span> <span data-ttu-id="f0388-120">最初に使用するドメイン名など、独自の fourthcoffee.cn があります。</span><span class="sxs-lookup"><span data-stu-id="f0388-120">You'll need your own domain name, like fourthcoffee.cn first.</span></span> <span data-ttu-id="f0388-121">既に持っている場合は、それをご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="f0388-121">If you already have one, great!</span></span> <span data-ttu-id="f0388-122">持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0388-122">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

<span data-ttu-id="f0388-123">ドメインのメールを Microsoft 365 に変更すると、セットアップ中にドメインの MX レコードを更新すると、そのドメインに送信されるメールはすべて Microsoft 365 に送信されます。</span><span class="sxs-lookup"><span data-stu-id="f0388-123">When you change your domain's email to come to Microsoft 365, by updating your domain's MX record during setup, ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="f0388-124">MX レコードを変更する前に、ドメインにメールを送信しているすべてのユーザーにユーザーを追加し、Microsoft 365 でメールボックスを作成してください。</span><span class="sxs-lookup"><span data-stu-id="f0388-124">Make sure you've added users and created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span> <span data-ttu-id="f0388-125">ドメインのすべてのユーザーのメールを Microsoft 365 に移動したくない場合</span><span class="sxs-lookup"><span data-stu-id="f0388-125">Don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="f0388-126">代わりに、少数の電子メール アドレスで [Microsoft 365 をパイロットするための手順を実行できます](../misc/pilot-microsoft-365-from-my-custom-domain.md?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="f0388-126">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](../misc/pilot-microsoft-365-from-my-custom-domain.md?view=o365-worldwide).</span></span>
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a><span data-ttu-id="f0388-127">Microsoft 365 管理センターを使用してカスタム ドメインを使用するメール アドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="f0388-127">Change your email address to use your custom domain using the Microsoft 365 admin center</span></span>

<span data-ttu-id="f0388-128">これらの手順を実行するには、グローバル管理者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="f0388-128">You must have a global admin account to perform these steps.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f0388-129"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f0388-129">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <span data-ttu-id="f0388-130"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f0388-130">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span> 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f0388-131">で管理センターに移動します<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>。</span><span class="sxs-lookup"><span data-stu-id="f0388-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>.</span></span> 

::: moniker-end 

2. <span data-ttu-id="f0388-132">[セットアップ ドメイン **]**  >  **ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="f0388-132">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="f0388-133">[**ドメイン**] ページで、[**ドメインの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0388-133">On the **Domains** page, select **Add domain**.</span></span>
    
4. <span data-ttu-id="f0388-134">自分がドメインを所有していることを確認して、メール アドレスを変更する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f0388-134">Follow the steps to confirm that you own your domain and to change your email address.</span></span>
    
<span data-ttu-id="f0388-135">Microsoft 365 のドメインですべてが正しく設定されるようにガイドされます。</span><span class="sxs-lookup"><span data-stu-id="f0388-135">You'll be guided to get everything set up correctly with your domain in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="f0388-136">Exchange ライセンスを使用していない場合は、ドメインを使用して Microsoft 365 テナントからの電子メールの送受信を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0388-136">If you are not using an Exchange license, you cannot use the domain to send or receive emails from the Microsoft 365 tenant.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="f0388-137">関連記事</span><span class="sxs-lookup"><span data-stu-id="f0388-137">Related articles</span></span>

[<span data-ttu-id="f0388-138">Microsoft 365 を使用してカスタム ドメインを購入する</span><span class="sxs-lookup"><span data-stu-id="f0388-138">Buy a custom domain using Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)
