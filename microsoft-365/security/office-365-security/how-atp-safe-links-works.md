---
title: ATP の安全なリンク機能のしくみ
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '[安全なリンク] 機能を使用すると、Office ドキュメントや電子メールメッセージ内のハイパーリンクの時間を確認できます。 ATP の安全なリンクのしくみについては、この記事をお読みください。'
ms.openlocfilehash: 09357b20173e2609587137764737c8aba044190e
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201470"
---
# <a name="how-atp-safe-links-works"></a><span data-ttu-id="645c1-104">ATP の安全なリンク機能のしくみ</span><span class="sxs-lookup"><span data-stu-id="645c1-104">How ATP Safe Links works</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT] 
> <span data-ttu-id="645c1-105">Office 365 の ATP の安全なリンクが正しく動作するためには、すべてのサービスが同じバージョンになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="645c1-105">For Office 365 ATP Safe Links to operate correctly, all of the services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works"></a><span data-ttu-id="645c1-106">ATP の安全なリンク機能のしくみ</span><span class="sxs-lookup"><span data-stu-id="645c1-106">How ATP Safe Links works</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]
 <span data-ttu-id="645c1-107">メール内の Url</span><span class="sxs-lookup"><span data-stu-id="645c1-107">with URLs in email</span></span>

<span data-ttu-id="645c1-108">高レベルでは、(オンプレミスではなく Office 365 でホストされている) 電子メール内の Url に対して、 [ATP の安全なリンク](atp-safe-links.md) 保護がどのように機能するかを説明します。</span><span class="sxs-lookup"><span data-stu-id="645c1-108">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="645c1-109">ユーザーが電子メールメッセージを受信します。その中には、Url が含まれています。</span><span class="sxs-lookup"><span data-stu-id="645c1-109">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="645c1-110">すべての電子メールは、インターネットプロトコル (IP) とエンベロープフィルター、署名ベースのマルウェア対策、スパム対策およびマルウェア対策フィルターを適用する Exchange Online Protection によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="645c1-110">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="645c1-111">電子メールは、ユーザーの受信トレイで到着します。</span><span class="sxs-lookup"><span data-stu-id="645c1-111">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="645c1-112">ユーザーが Office 365 にサインインし、電子メールの受信トレイに進みます。</span><span class="sxs-lookup"><span data-stu-id="645c1-112">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="645c1-113">ユーザーが電子メールメッセージを開き、電子メールメッセージ内の URL をクリックしたとき。</span><span class="sxs-lookup"><span data-stu-id="645c1-113">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="645c1-114">ATP の安全なリンク機能は、web サイトを開く前に、すぐに URL をチェックします。</span><span class="sxs-lookup"><span data-stu-id="645c1-114">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="645c1-115">URL は、ブロック、悪意、または安全として識別されます。</span><span class="sxs-lookup"><span data-stu-id="645c1-115">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="645c1-116">URL が組織のカスタムブロックされた [url リスト](set-up-a-custom-blocked-urls-list-atp.md)に含まれる web サイトに対するものである場合は、 [警告ページ](atp-safe-links-warning-pages.md) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="645c1-116">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="645c1-117">悪意があると判断された web サイトへの URL の場合は、 [警告のページ](atp-safe-links-warning-pages.md) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="645c1-117">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="645c1-118">URL がダウンロード可能なファイルに送られ、組織の [ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md) がそのようなコンテンツをスキャンするように構成されている場合は、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="645c1-118">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="645c1-119">URL が安全であると判断された場合は、web サイトが開きます。</span><span class="sxs-lookup"><span data-stu-id="645c1-119">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works"></a><span data-ttu-id="645c1-120">ATP の安全なリンク機能のしくみ</span><span class="sxs-lookup"><span data-stu-id="645c1-120">How ATP Safe Links works</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]
 <span data-ttu-id="645c1-121">Office ドキュメント内の Url の場合</span><span class="sxs-lookup"><span data-stu-id="645c1-121">with URLs in Office documents</span></span> 

<span data-ttu-id="645c1-122">高レベルでは、エンタープライズまたはビジネスプレミアムアプリケーション用の Microsoft 365 アプリ (Windows、Mac、またはブラウザー、iOS または Android デバイス上の Office アプリ、ブラウザーでの OneNote) の Url に対して、 [ATP の安全なリンク](atp-safe-links.md) 保護がどのように機能するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="645c1-122">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Microsoft 365 Apps for enterprise or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="645c1-123">ユーザーは、お客様のコンピューター、スマートフォン、またはタブレットに Microsoft 365 Apps for enterprise または Business Premium をインストールしています。</span><span class="sxs-lookup"><span data-stu-id="645c1-123">People have installed Microsoft 365 Apps for enterprise or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="645c1-124">(または、ユーザーがブラウザーで Office を使用している場合)。</span><span class="sxs-lookup"><span data-stu-id="645c1-124">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="645c1-125">ユーザーが Word、Excel、PowerPoint、OneNote (ブラウザー)、または Visio (デスクトップ) を開き、職場または学校のアカウントを使用して Office 365 Enterprise にサインインします。</span><span class="sxs-lookup"><span data-stu-id="645c1-125">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="645c1-126">ドキュメントに Url が含まれている。</span><span class="sxs-lookup"><span data-stu-id="645c1-126">The document contains URLs.</span></span>
    
3. <span data-ttu-id="645c1-127">ユーザーがドキュメント内の URL をクリックすると、そのリンクは ATP の安全なリンクサービスによってチェックされます。</span><span class="sxs-lookup"><span data-stu-id="645c1-127">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="645c1-128">URL が組織のカスタムブロックされた [url リスト](set-up-a-custom-blocked-urls-list-atp.md)に含まれる web サイトに対するものである場合、ユーザーは [警告ページ](atp-safe-links-warning-pages.md)に移動されます。</span><span class="sxs-lookup"><span data-stu-id="645c1-128">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="645c1-129">悪意があると判断された web サイトに URL が設定されている場合、ユーザーは [警告ページ](atp-safe-links-warning-pages.md)にジャンプします。</span><span class="sxs-lookup"><span data-stu-id="645c1-129">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="645c1-130">URL がダウンロード可能なファイルに送られ、そのようなダウンロードをスキャンするように [ATP の安全なリンクポリシー](set-up-atp-safe-links-policies.md) が構成されている場合は、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="645c1-130">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="645c1-131">URL が安全であると判断された場合は、ユーザーが web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="645c1-131">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="645c1-132">URL チェックに失敗すると、安全なリンクの保護はトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="645c1-132">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="645c1-133">デスクトップクライアントでは、ユーザーはサイトに進む前に警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="645c1-133">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="645c1-134">各セッションの開始時に数秒間かかることがあり、ユーザーが Office 用の ATP の安全なリンクを有効にしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="645c1-134">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
