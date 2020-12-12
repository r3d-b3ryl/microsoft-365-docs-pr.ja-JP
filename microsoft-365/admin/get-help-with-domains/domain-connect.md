---
title: ドメイン接続の使用
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: ドメイン接続が有効なレジストラーを使用して、ドメインを Microsoft 365 に追加する方法について説明します。
ms.openlocfilehash: 109255d82100e636e3472242866a519ff64a9e54
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655614"
---
# <a name="using-domain-connect"></a><span data-ttu-id="a68b8-103">ドメイン接続の使用</span><span class="sxs-lookup"><span data-stu-id="a68b8-103">Using Domain Connect</span></span>

 <span data-ttu-id="a68b8-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a68b8-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="a68b8-105">[ドメイン接続 ](https://www.domainconnect.org/) が有効なレジストラーを使用すると、数分かかる 3 段階のプロセスでドメインを Microsoft 365 に追加できます。</span><span class="sxs-lookup"><span data-stu-id="a68b8-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="a68b8-106">ウィザードでは、ドメインを所有し、ドメインのレコードを自動的にセットアップするだけなので、メールが Microsoft 365 や Teams などの他の Microsoft 365 サービスに届きます。</span><span class="sxs-lookup"><span data-stu-id="a68b8-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a68b8-107">セットアップ ウィザードを開始する前に、ブラウザーのポップアップ ブロック機能が無効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a68b8-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="a68b8-108">Microsoft 365 と統合されたドメイン接続レジストラー</span><span class="sxs-lookup"><span data-stu-id="a68b8-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="a68b8-109">1 &amp; 1</span><span class="sxs-lookup"><span data-stu-id="a68b8-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="a68b8-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="a68b8-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="a68b8-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="a68b8-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="a68b8-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="a68b8-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="a68b8-113">クシュク</span><span class="sxs-lookup"><span data-stu-id="a68b8-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="a68b8-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="a68b8-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="a68b8-115">SecureServer または WildWestDomains (SecureServer DNS ホスティングを使用する GoDaddy リセラー)</span><span class="sxs-lookup"><span data-stu-id="a68b8-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="a68b8-116">MadDog Domains</span><span class="sxs-lookup"><span data-stu-id="a68b8-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="a68b8-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="a68b8-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="a68b8-118">メールと Web サイトは何が起こりますか?</span><span class="sxs-lookup"><span data-stu-id="a68b8-118">What happens to my email and website?</span></span>

<span data-ttu-id="a68b8-119">セットアップが完了すると、ドメインの MX レコードが Microsoft 365 を指すまで更新され、ドメインのすべてのメールが Microsoft 365 に届きます。</span><span class="sxs-lookup"><span data-stu-id="a68b8-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="a68b8-120">ドメインでメールを受け取るすべてのユーザーに対して、ユーザーを追加し、Microsoft 365 でメールボックスを設定してください。</span><span class="sxs-lookup"><span data-stu-id="a68b8-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="a68b8-121">ビジネスで使用している Web サイトがある場合は、そのままの場所で稼働し続けます。</span><span class="sxs-lookup"><span data-stu-id="a68b8-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="a68b8-122">ドメイン接続のセットアップ手順は、Web サイトには影響を与えいません。</span><span class="sxs-lookup"><span data-stu-id="a68b8-122">The Domain Connect setup steps don't affect your website.</span></span>
