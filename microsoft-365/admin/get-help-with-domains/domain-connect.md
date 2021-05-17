---
title: ドメイン の使用Connect
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
description: ドメイン 管理者が有効なレジストラー Connectを使用して、ドメインをドメインに追加する方法Microsoft 365。
ms.openlocfilehash: 5dec69f70273e6a9430ce5926ed07888e197adcd
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860657"
---
# <a name="using-domain-connect"></a><span data-ttu-id="58a99-103">ドメイン の使用Connect</span><span class="sxs-lookup"><span data-stu-id="58a99-103">Using Domain Connect</span></span>

 <span data-ttu-id="58a99-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58a99-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="58a99-105">[ドメイン Connect](https://www.domainconnect.org/)有効なレジストラーを使用すると、数分かかる 3 Microsoft 365プロセスでドメインをドメインに追加できます。</span><span class="sxs-lookup"><span data-stu-id="58a99-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="58a99-106">ウィザードでは、ドメインを所有していることを確認してから、ドメインのレコードを自動的に設定するため、Microsoft 365 にメールが送信されます。Teams などの他の Microsoft 365 サービスはドメインを操作します。</span><span class="sxs-lookup"><span data-stu-id="58a99-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="58a99-107">セットアップ ウィザードを開始する前に、ブラウザーのポップアップ ブロック機能が無効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="58a99-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="58a99-108">Microsoft 365 と統合するドメイン接続レジストラ</span><span class="sxs-lookup"><span data-stu-id="58a99-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="58a99-109">1&amp;1 IONOS</span><span class="sxs-lookup"><span data-stu-id="58a99-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="58a99-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="58a99-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="58a99-111">Go Daddy</span><span class="sxs-lookup"><span data-stu-id="58a99-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="58a99-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="58a99-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="58a99-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="58a99-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="58a99-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="58a99-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="58a99-115">SecureServer または WildWestDomains (SecureServer DNS ホスティングを使用する GoDaddy リセラー)</span><span class="sxs-lookup"><span data-stu-id="58a99-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="58a99-116">MadDog Web ホスティング</span><span class="sxs-lookup"><span data-stu-id="58a99-116">MadDog Web Hosting</span></span>](https://maddogwebhosting.com/domains/)
    - [<span data-ttu-id="58a99-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="58a99-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="58a99-118">メールと Web サイトはどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="58a99-118">What happens to my email and website?</span></span>

<span data-ttu-id="58a99-119">セットアップを終了すると、ユーザーのドメインの MX レコードが Microsoft 365 を指定されるように更新され、そのドメイン宛てのすべてのメールが Microsoft 365 に送信されるようになります。</span><span class="sxs-lookup"><span data-stu-id="58a99-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="58a99-120">ユーザーのドメインにメールを持つすべてのユーザーが Microsoft 365 に追加され、メールボックスが設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="58a99-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="58a99-121">ビジネスで使用している Web サイトがある場合は、そのままの場所で稼働し続けます。</span><span class="sxs-lookup"><span data-stu-id="58a99-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="58a99-122">ドメイン接続 のセットアップ手順は、自分の Web サイトには影響しません。</span><span class="sxs-lookup"><span data-stu-id="58a99-122">The Domain Connect setup steps don't affect your website.</span></span>
