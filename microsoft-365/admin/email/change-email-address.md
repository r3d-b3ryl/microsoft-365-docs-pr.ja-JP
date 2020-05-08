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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: '最初の電子メールアドレスを、tom@fourthcoffee.com のようなわかりやすい電子メールアドレスに変更します。 これを行うには、ドメイン名を購入して、Microsoft 365 に追加する必要があります。 '
ms.openlocfilehash: 50739c01fda9528140870798324dd69a1c68abce
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140502"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a><span data-ttu-id="38a85-104">カスタム ドメインを使うように電子メール アドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="38a85-104">Change your email address to use your custom domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="38a85-105">管理センターが変更されています。</span><span class="sxs-lookup"><span data-stu-id="38a85-105">The admin center is changing.</span></span> <span data-ttu-id="38a85-106">ここに示されている詳細情報とは異なる場合は、「[新しい Microsoft 365 管理センターについ](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38a85-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="38a85-107">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38a85-107">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="38a85-108">Microsoft 365 の最初の電子メールアドレス onmicrosoft.com は、tom@fourthcoffee.onmicrosoft.com のようになります。</span><span class="sxs-lookup"><span data-stu-id="38a85-108">Your initial email address in Microsoft 365 includes .onmicrosoft.com, like tom@fourthcoffee.onmicrosoft.com.</span></span> <span data-ttu-id="38a85-109">これを tom@fourthcoffee.com のようなわかりやすいアドレスに変更できます。</span><span class="sxs-lookup"><span data-stu-id="38a85-109">You can change it to a friendlier address like tom@fourthcoffee.com.</span></span> <span data-ttu-id="38a85-110">このためには、自分のドメイン (例: fourthcoffee.com) を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="38a85-110">You'll need your own domain name, like fourthcoffee.com first.</span></span> <span data-ttu-id="38a85-111">既に持っている場合は、それをご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="38a85-111">If you already have one, great!</span></span> <span data-ttu-id="38a85-112">持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38a85-112">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="38a85-113">Office 365 ドイツの最初の電子メールアドレスには、tom@fourthcoffee.onmicrosoft.de などの onmicrosoft.de が含まれています。</span><span class="sxs-lookup"><span data-stu-id="38a85-113">Your initial email address in Office 365 Germany includes .onmicrosoft.de, like tom@fourthcoffee.onmicrosoft.de.</span></span> <span data-ttu-id="38a85-114">Tom@fourthcoffee.de のようなわかりやすいアドレスに変更することができます。</span><span class="sxs-lookup"><span data-stu-id="38a85-114">You can change it to a friendlier address like tom@fourthcoffee.de.</span></span> <span data-ttu-id="38a85-115">Fourthcoffee.de など、独自のドメイン名が必要になります。</span><span class="sxs-lookup"><span data-stu-id="38a85-115">You'll need your own domain name, like fourthcoffee.de first.</span></span> <span data-ttu-id="38a85-116">既に持っている場合は、それをご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="38a85-116">If you already have one, great!</span></span> <span data-ttu-id="38a85-117">持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38a85-117">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="38a85-118">21Vianet が運用している Office 365 の最初の電子メールアドレスには、tom@fourthcoffee.partner.onmschina.cn などの partner.onmschina.cn が含まれています。</span><span class="sxs-lookup"><span data-stu-id="38a85-118">Your initial email address in Office 365 operated by 21Vianet includes partner.onmschina.cn, like tom@fourthcoffee.partner.onmschina.cn.</span></span> <span data-ttu-id="38a85-119">Tom@fourthcoffee.cn のようなわかりやすいアドレスに変更することができます。</span><span class="sxs-lookup"><span data-stu-id="38a85-119">You can change it to a friendlier address like tom@fourthcoffee.cn.</span></span> <span data-ttu-id="38a85-120">Fourthcoffee.cn など、独自のドメイン名が必要になります。</span><span class="sxs-lookup"><span data-stu-id="38a85-120">You'll need your own domain name, like fourthcoffee.cn first.</span></span> <span data-ttu-id="38a85-121">既に持っている場合は、それをご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="38a85-121">If you already have one, great!</span></span> <span data-ttu-id="38a85-122">持っていない場合は、「[ドメイン名の購入方法](../get-help-with-domains/buy-a-domain-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38a85-122">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

<span data-ttu-id="38a85-123">セットアップ時にドメインの MX レコードを更新することによって、ドメインの電子メールを Microsoft 365 にするように変更すると、そのドメインに送信されるすべての電子メールが Microsoft 365 に送られ始めます。</span><span class="sxs-lookup"><span data-stu-id="38a85-123">When you change your domain's email to come to Microsoft 365, by updating your domain's MX record during setup, ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="38a85-124">MX レコードを変更する前に、自分のドメインに電子メールを持っているすべてのユーザーに対して、Microsoft 365 でユーザーを追加し、メールボックスを作成していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="38a85-124">Make sure you've added users and created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span> <span data-ttu-id="38a85-125">ドメイン上のすべてのユーザーのメールを Microsoft 365 に移動したくありませんか。</span><span class="sxs-lookup"><span data-stu-id="38a85-125">Don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="38a85-126">[代わりに、少数のメールアドレスを使用して Microsoft 365 をパイロット](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)処理する手順を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="38a85-126">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span></span>
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a><span data-ttu-id="38a85-127">Microsoft 365 管理センターを使用してカスタムドメインを使用するように電子メールアドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="38a85-127">Change your email address to use your custom domain using the Microsoft 365 admin center</span></span>

<span data-ttu-id="38a85-128">これらの手順を実行するには、グローバル管理者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="38a85-128">You must have a global admin account to perform these steps.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="38a85-129"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="38a85-129">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <span data-ttu-id="38a85-130"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="38a85-130">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span> 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="38a85-131">の管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="38a85-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>.</span></span> 

::: moniker-end 

2. <span data-ttu-id="38a85-132">[**セットアップ** > **ドメイン**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="38a85-132">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="38a85-133">[**ドメイン**] ページで、[**ドメインの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38a85-133">On the **Domains** page, select **Add domain**.</span></span>
    
4. <span data-ttu-id="38a85-134">自分がドメインを所有していることを確認して、メール アドレスを変更する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="38a85-134">Follow the steps to confirm that you own your domain and to change your email address.</span></span>
    
<span data-ttu-id="38a85-135">Microsoft 365 のドメインですべての設定を適切に設定するようにガイドされます。</span><span class="sxs-lookup"><span data-stu-id="38a85-135">You'll be guided to get everything set up correctly with your domain in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="38a85-136">Exchange ライセンスを使用していない場合、ドメインを使用して Microsoft 365 テナントからメールを送受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="38a85-136">If you are not using an Exchange license, you cannot use the domain to send or receive emails from the Microsoft 365 tenant.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="38a85-137">関連記事</span><span class="sxs-lookup"><span data-stu-id="38a85-137">Related articles</span></span>

[<span data-ttu-id="38a85-138">Microsoft 365 を使用してカスタムドメインを購入する</span><span class="sxs-lookup"><span data-stu-id="38a85-138">Buy a custom domain using Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)
 
