---
title: カスタム ドメインを使うように電子メール アドレスを変更する
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
description: '最初のメール アドレスを設定したメール アドレスのわかりやすいメール アドレス (たとえばtom@fourthcoffee.com。 これを行うには、ドメイン名を購入して、Microsoft 365 に追加する必要があります。 '
ms.openlocfilehash: dc6d418961fe29a363aa6a787d8c0bb2d11d7e97
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814482"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a><span data-ttu-id="ca292-104">カスタム ドメインを使うように電子メール アドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="ca292-104">Change your email address to use your custom domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="ca292-105">管理センターは変更されました。</span><span class="sxs-lookup"><span data-stu-id="ca292-105">The admin center is changing.</span></span> <span data-ttu-id="ca292-106">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca292-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="ca292-107">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca292-107">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="ca292-108">Microsoft 365 の初期メール アドレスには、.onmicrosoft.com、たとえばクライアントtom@fourthcoffee.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="ca292-108">Your initial email address in Microsoft 365 includes .onmicrosoft.com, like tom@fourthcoffee.onmicrosoft.com.</span></span> <span data-ttu-id="ca292-109">これを tom@fourthcoffee.com のようなわかりやすいアドレスに変更できます。</span><span class="sxs-lookup"><span data-stu-id="ca292-109">You can change it to a friendlier address like tom@fourthcoffee.com.</span></span> <span data-ttu-id="ca292-110">このためには、自分のドメイン (例: fourthcoffee.com) を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca292-110">You'll need your own domain name, like fourthcoffee.com first.</span></span> <span data-ttu-id="ca292-111">既に持っている場合は、それをご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="ca292-111">If you already have one, great!</span></span> <span data-ttu-id="ca292-112">持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca292-112">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="ca292-113">Office 365 Germany の最初のメール アドレスには、.onmicrosoft.de など .onmicrosoft.de が含tom@fourthcoffee.onmicrosoft.de。</span><span class="sxs-lookup"><span data-stu-id="ca292-113">Your initial email address in Office 365 Germany includes .onmicrosoft.de, like tom@fourthcoffee.onmicrosoft.de.</span></span> <span data-ttu-id="ca292-114">このアドレスを、使用するドメインシリアのアドレスtom@fourthcoffee.de。</span><span class="sxs-lookup"><span data-stu-id="ca292-114">You can change it to a friendlier address like tom@fourthcoffee.de.</span></span> <span data-ttu-id="ca292-115">最初のドメイン名など、独自のドメインfourthcoffee.deがあります。</span><span class="sxs-lookup"><span data-stu-id="ca292-115">You'll need your own domain name, like fourthcoffee.de first.</span></span> <span data-ttu-id="ca292-116">既に持っている場合は、それをご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="ca292-116">If you already have one, great!</span></span> <span data-ttu-id="ca292-117">持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca292-117">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="ca292-118">Office 365 が運用している Office 365 の最初の電子メール アドレスには、次のようなpartner.onmschina.cnが含tom@fourthcoffee.partner.onmschina.cn。</span><span class="sxs-lookup"><span data-stu-id="ca292-118">Your initial email address in Office 365 operated by 21Vianet includes partner.onmschina.cn, like tom@fourthcoffee.partner.onmschina.cn.</span></span> <span data-ttu-id="ca292-119">このパラメーターは、メッセージを作成したいなどのわかりやすいアドレスtom@fourthcoffee.cn。</span><span class="sxs-lookup"><span data-stu-id="ca292-119">You can change it to a friendlier address like tom@fourthcoffee.cn.</span></span> <span data-ttu-id="ca292-120">最初に、自分のドメイン名 (たとえば、最初fourthcoffee.cn必要です。</span><span class="sxs-lookup"><span data-stu-id="ca292-120">You'll need your own domain name, like fourthcoffee.cn first.</span></span> <span data-ttu-id="ca292-121">既に持っている場合は、それをご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="ca292-121">If you already have one, great!</span></span> <span data-ttu-id="ca292-122">持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca292-122">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

<span data-ttu-id="ca292-123">セットアップ中にドメインの MX レコードを更新して、ドメインのメールを Microsoft 365 に移行すると、そのドメインに送信されたすべてのメールが Microsoft 365 に送信されるされるはずです。</span><span class="sxs-lookup"><span data-stu-id="ca292-123">When you change your domain's email to come to Microsoft 365, by updating your domain's MX record during setup, ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="ca292-124">MX レコードを変更する前に、ドメインにメールを持つすべてのユーザーについて、Microsoft 365 にユーザーを追加してメールボックスを作成したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ca292-124">Make sure you've added users and created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span> <span data-ttu-id="ca292-125">ドメイン上のすべてのユーザーのメールを Microsoft 365 に移動したくない場合</span><span class="sxs-lookup"><span data-stu-id="ca292-125">Don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="ca292-126">代わりに、少数のメール [アドレスで Microsoft 365 をパイロット運用する手順を実行できます](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="ca292-126">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide).</span></span>
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a><span data-ttu-id="ca292-127">Microsoft 365 管理センターを使用して、カスタム ドメインを使うメール アドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="ca292-127">Change your email address to use your custom domain using the Microsoft 365 admin center</span></span>

<span data-ttu-id="ca292-128">これらの手順を実行するには、全体管理者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="ca292-128">You must have a global admin account to perform these steps.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ca292-129"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ca292-129">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <span data-ttu-id="ca292-130"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ca292-130">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span> 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ca292-131">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>admin center at.</span><span class="sxs-lookup"><span data-stu-id="ca292-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>.</span></span> 

::: moniker-end 

2. <span data-ttu-id="ca292-132">[セットアップ ドメイン]**ページ**  >  **に移動**します。</span><span class="sxs-lookup"><span data-stu-id="ca292-132">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="ca292-133">[**ドメイン**] ページで、[**ドメインの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca292-133">On the **Domains** page, select **Add domain**.</span></span>
    
4. <span data-ttu-id="ca292-134">自分がドメインを所有していることを確認して、メール アドレスを変更する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ca292-134">Follow the steps to confirm that you own your domain and to change your email address.</span></span>
    
<span data-ttu-id="ca292-135">すべてのドメインを Microsoft 365 で正しくセットアップするガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca292-135">You'll be guided to get everything set up correctly with your domain in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="ca292-136">Exchange ライセンスを使用していない場合は、そのドメインを使用して Microsoft 365 テナントの電子メールを送受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="ca292-136">If you are not using an Exchange license, you cannot use the domain to send or receive emails from the Microsoft 365 tenant.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="ca292-137">関連記事</span><span class="sxs-lookup"><span data-stu-id="ca292-137">Related articles</span></span>

[<span data-ttu-id="ca292-138">Microsoft 365 を使用したカスタム ドメインの購入</span><span class="sxs-lookup"><span data-stu-id="ca292-138">Buy a custom domain using Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)
 
