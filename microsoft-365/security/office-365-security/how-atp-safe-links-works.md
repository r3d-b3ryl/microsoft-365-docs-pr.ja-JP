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
ms.openlocfilehash: e79c44b91eb5de7564058b4dc50c94d2a4223f08
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046366"
---
# <a name="how-atp-safe-links-works"></a><span data-ttu-id="1a324-104">ATP の安全なリンク機能のしくみ</span><span class="sxs-lookup"><span data-stu-id="1a324-104">How ATP Safe Links works</span></span>
> [!IMPORTANT] 
> <span data-ttu-id="1a324-105">Office 365 の ATP の安全なリンクが正しく動作するためには、すべてのサービスが同じバージョンになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a324-105">For Office 365 ATP Safe Links to operate correctly, all of the services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="1a324-106">ATP の安全なリンクが電子メール内の Url と連携する方法</span><span class="sxs-lookup"><span data-stu-id="1a324-106">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="1a324-107">高レベルでは、(オンプレミスではなく Office 365 でホストされている) 電子メール内の Url に対して、 [ATP の安全なリンク](atp-safe-links.md)保護がどのように機能するかを説明します。</span><span class="sxs-lookup"><span data-stu-id="1a324-107">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="1a324-108">ユーザーが電子メールメッセージを受信します。その中には、Url が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a324-108">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="1a324-109">すべての電子メールは、インターネットプロトコル (IP) とエンベロープフィルター、署名ベースのマルウェア対策、スパム対策およびマルウェア対策フィルターを適用する Exchange Online Protection によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="1a324-109">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="1a324-110">電子メールは、ユーザーの受信トレイで到着します。</span><span class="sxs-lookup"><span data-stu-id="1a324-110">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="1a324-111">ユーザーが Office 365 にサインインし、電子メールの受信トレイに進みます。</span><span class="sxs-lookup"><span data-stu-id="1a324-111">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="1a324-112">ユーザーが電子メールメッセージを開き、電子メールメッセージ内の URL をクリックしたとき。</span><span class="sxs-lookup"><span data-stu-id="1a324-112">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="1a324-113">ATP の安全なリンク機能は、web サイトを開く前に、すぐに URL をチェックします。</span><span class="sxs-lookup"><span data-stu-id="1a324-113">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="1a324-114">URL は、ブロック、悪意、または安全として識別されます。</span><span class="sxs-lookup"><span data-stu-id="1a324-114">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="1a324-115">URL が組織のカスタムブロックされた[url リスト](set-up-a-custom-blocked-urls-list-atp.md)に含まれる web サイトに対するものである場合は、[警告ページ](atp-safe-links-warning-pages.md)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a324-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="1a324-116">悪意があると判断された web サイトへの URL の場合は、[警告のページ](atp-safe-links-warning-pages.md)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a324-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="1a324-117">URL がダウンロード可能なファイルに送られ、組織の[ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)がそのようなコンテンツをスキャンするように構成されている場合は、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="1a324-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="1a324-118">URL が安全であると判断された場合は、web サイトが開きます。</span><span class="sxs-lookup"><span data-stu-id="1a324-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="1a324-119">Office ドキュメントの Url で ATP の安全なリンクが機能するしくみ</span><span class="sxs-lookup"><span data-stu-id="1a324-119">How ATP Safe Links works with URLs in Office documents</span></span> 

<span data-ttu-id="1a324-120">高レベルでは、エンタープライズまたはビジネスプレミアムアプリケーション用の Microsoft 365 アプリ (Windows、Mac、またはブラウザー、iOS または Android デバイス上の Office アプリ、ブラウザーでの OneNote) の Url に対して、 [ATP の安全なリンク](atp-safe-links.md)保護がどのように機能するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1a324-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Microsoft 365 Apps for enterprise or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="1a324-121">ユーザーは、お客様のコンピューター、スマートフォン、またはタブレットに Microsoft 365 Apps for enterprise または Business Premium をインストールしています。</span><span class="sxs-lookup"><span data-stu-id="1a324-121">People have installed Microsoft 365 Apps for enterprise or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="1a324-122">(または、ユーザーがブラウザーで Office を使用している場合)。</span><span class="sxs-lookup"><span data-stu-id="1a324-122">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="1a324-123">ユーザーが Word、Excel、PowerPoint、OneNote (ブラウザー)、または Visio (デスクトップ) を開き、職場または学校のアカウントを使用して Office 365 Enterprise にサインインします。</span><span class="sxs-lookup"><span data-stu-id="1a324-123">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="1a324-124">ドキュメントに Url が含まれている。</span><span class="sxs-lookup"><span data-stu-id="1a324-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="1a324-125">ユーザーがドキュメント内の URL をクリックすると、そのリンクは ATP の安全なリンクサービスによってチェックされます。</span><span class="sxs-lookup"><span data-stu-id="1a324-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="1a324-126">URL が組織のカスタムブロックされた[url リスト](set-up-a-custom-blocked-urls-list-atp.md)に含まれる web サイトに対するものである場合、ユーザーは[警告ページ](atp-safe-links-warning-pages.md)に移動されます。</span><span class="sxs-lookup"><span data-stu-id="1a324-126">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="1a324-127">悪意があると判断された web サイトに URL が設定されている場合、ユーザーは[警告ページ](atp-safe-links-warning-pages.md)にジャンプします。</span><span class="sxs-lookup"><span data-stu-id="1a324-127">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="1a324-128">URL がダウンロード可能なファイルに送られ、そのようなダウンロードをスキャンするように[ATP の安全なリンクポリシー](set-up-atp-safe-links-policies.md)が構成されている場合は、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="1a324-128">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="1a324-129">URL が安全であると判断された場合は、ユーザーが web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="1a324-129">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="1a324-130">URL チェックに失敗すると、安全なリンクの保護はトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="1a324-130">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="1a324-131">デスクトップクライアントでは、ユーザーはサイトに進む前に警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a324-131">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="1a324-132">各セッションの開始時に数秒間かかることがあり、ユーザーが Office 用の ATP の安全なリンクを有効にしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a324-132">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
