---
title: ドメイン接続の使用
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
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: ドメイン接続が有効なレジストラーを使用して、ドメインを Microsoft 365 に追加する方法について説明します。
ms.openlocfilehash: 59e2f94fe83f87a5426064e49f0441356fbd732e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362182"
---
# <a name="using-domain-connect"></a><span data-ttu-id="84ad5-103">ドメイン接続の使用</span><span class="sxs-lookup"><span data-stu-id="84ad5-103">Using Domain Connect</span></span>

 <span data-ttu-id="84ad5-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84ad5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="84ad5-105">[ドメイン接続](https://www.domainconnect.org/)が有効な登録機関は、数分かかる3つのステップのプロセスで、ドメインを Microsoft 365 に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="84ad5-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="84ad5-106">このウィザードでは、ドメインを所有していることを確認し、ドメインのレコードを自動的に設定することを確認します。そのため、Microsoft 365 およびその他の Microsoft 365 サービス (Teams など) が自分のドメインで作業します。</span><span class="sxs-lookup"><span data-stu-id="84ad5-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="84ad5-107">セットアップ ウィザードを開始する前に、ブラウザーのポップアップ ブロック機能が無効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="84ad5-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="84ad5-108">Microsoft 365 と統合するドメイン接続レジストラー</span><span class="sxs-lookup"><span data-stu-id="84ad5-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="84ad5-109">1&amp;IONOS</span><span class="sxs-lookup"><span data-stu-id="84ad5-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="84ad5-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="84ad5-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="84ad5-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="84ad5-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="84ad5-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="84ad5-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="84ad5-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="84ad5-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="84ad5-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="84ad5-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="84ad5-115">SecureServer または WildWestDomains (SecureServer DNS ホスティングを使用する GoDaddy 販売店)</span><span class="sxs-lookup"><span data-stu-id="84ad5-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="84ad5-116">MadDog ドメイン</span><span class="sxs-lookup"><span data-stu-id="84ad5-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="84ad5-117">不正名</span><span class="sxs-lookup"><span data-stu-id="84ad5-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="84ad5-118">電子メールと web サイトはどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="84ad5-118">What happens to my email and website?</span></span>

<span data-ttu-id="84ad5-119">セットアップが完了すると、ドメインの MX レコードが更新され、Microsoft 365 をポイントするようになり、ドメインのすべての電子メールが Microsoft 365 に送られ始めます。</span><span class="sxs-lookup"><span data-stu-id="84ad5-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="84ad5-120">ユーザーのドメインにメールを持つすべてのユーザーが Office 365 に追加され、メールボックスが設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="84ad5-120">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="84ad5-121">ビジネスで使用している Web サイトがある場合は、そのままの場所で稼働し続けます。</span><span class="sxs-lookup"><span data-stu-id="84ad5-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="84ad5-122">ドメイン接続のセットアップ手順は、web サイトには影響しません。</span><span class="sxs-lookup"><span data-stu-id="84ad5-122">The Domain Connect setup steps don't affect your website.</span></span>
