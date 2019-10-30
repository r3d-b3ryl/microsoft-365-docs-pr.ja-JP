---
title: Office 365 の ATP の安全なリンクのしくみ
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/19/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '[安全なリンク] 機能を使用すると、Office ドキュメントや電子メールメッセージ内のハイパーリンクの時間を確認できます。 ATP の安全なリンクのしくみについては、この記事をお読みください。'
ms.openlocfilehash: bb60d57a422d908b013caf7267f21f390769cfb4
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772201"
---
# <a name="how-office-365-atp-safe-links-works"></a><span data-ttu-id="7f16a-104">Office 365 の ATP の安全なリンクのしくみ</span><span class="sxs-lookup"><span data-stu-id="7f16a-104">How Office 365 ATP Safe Links works</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="7f16a-105">ATP の安全なリンクが電子メール内の Url と連携する方法</span><span class="sxs-lookup"><span data-stu-id="7f16a-105">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="7f16a-106">高レベルでは、(オンプレミスではなく Office 365 でホストされている) 電子メール内の Url に対して、 [ATP の安全なリンク](atp-safe-links.md)保護がどのように機能するかを説明します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-106">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="7f16a-107">ユーザーが電子メールメッセージを受信します。その中には、Url が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7f16a-107">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="7f16a-108">すべての電子メールは、インターネットプロトコル (IP) とエンベロープフィルター、署名ベースのマルウェア対策、スパム対策およびマルウェア対策フィルターを適用する Exchange Online Protection によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-108">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="7f16a-109">電子メールは、ユーザーの受信トレイで到着します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-109">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="7f16a-110">ユーザーが Office 365 にサインインし、電子メールの受信トレイに進みます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-110">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="7f16a-111">ユーザーが電子メールメッセージを開き、電子メールメッセージ内の URL をクリックしたとき。</span><span class="sxs-lookup"><span data-stu-id="7f16a-111">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="7f16a-112">ATP の安全なリンク機能は、web サイトを開く前に、すぐに URL をチェックします。</span><span class="sxs-lookup"><span data-stu-id="7f16a-112">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="7f16a-113">URL は、ブロック、悪意、または安全として識別されます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-113">The URL is identified as blocked, malicious, or safe.</span></span>
    
    - <span data-ttu-id="7f16a-114">ユーザーに適用されるポリシーの["リライト not リライト" url リスト](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)に含まれる web サイトへの url がある場合は、その web サイトが開きます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-114">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, the website opens.</span></span> 
    
    - <span data-ttu-id="7f16a-115">URL が組織のカスタムブロックされた[url リスト](set-up-a-custom-blocked-urls-list-wtih-atp.md)に含まれる web サイトに対するものである場合は、[警告ページ](atp-safe-links-warning-pages.md)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="7f16a-116">悪意があると判断された web サイトへの URL の場合は、[警告のページ](atp-safe-links-warning-pages.md)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="7f16a-117">URL がダウンロード可能なファイルに送られ、組織の[ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)がそのようなコンテンツをスキャンするように構成されている場合は、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
    - <span data-ttu-id="7f16a-118">URL が安全であると判断された場合は、web サイトが開きます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="7f16a-119">Office ドキュメントの Url で ATP の安全なリンクが機能するしくみ</span><span class="sxs-lookup"><span data-stu-id="7f16a-119">How ATP Safe Links works with URLs in Office documents</span></span>

<span data-ttu-id="7f16a-120">大まか[に説明する](atp-safe-links.md)と、Office 365 ProPlus またはビジネスプレミアムアプリケーション (Windows、Mac、またはブラウザーでの現在のバージョンの Word、Excel、PowerPoint の場合)、またはブラウザー、iOS または Android デバイスの Office アプリ、Visio onWindows、ブラウザーの OneNote):</span><span class="sxs-lookup"><span data-stu-id="7f16a-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Office 365 ProPlus or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="7f16a-121">ユーザーは、コンピューター、スマートフォン、またはタブレットに Office 365 ProPlus または Business Premium をインストールしています。</span><span class="sxs-lookup"><span data-stu-id="7f16a-121">People have installed Office 365 ProPlus or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="7f16a-122">(または、ユーザーがブラウザーで Office を使用している場合)。</span><span class="sxs-lookup"><span data-stu-id="7f16a-122">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="7f16a-123">ユーザーが Word、Excel、PowerPoint、OneNote (web)、または Visio (デスクトップ) を開き、職場または学校のアカウントを使用して Office 365 Enterprise にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7f16a-123">A user opens a Word, Excel, PowerPoint, OneNote (on the web), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="7f16a-124">ドキュメントに Url が含まれている。</span><span class="sxs-lookup"><span data-stu-id="7f16a-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="7f16a-125">ユーザーがドキュメント内の URL をクリックすると、そのリンクは ATP の安全なリンクサービスによってチェックされます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
      - <span data-ttu-id="7f16a-126">ユーザーに適用されるポリシーの["リライト not リライト" url リスト](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)に含まれる web サイトへの url がの場合、そのユーザーが web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-126">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, that user is taken to the website.</span></span> 
    
      - <span data-ttu-id="7f16a-127">URL が組織のカスタムブロックされた[url リスト](set-up-a-custom-blocked-urls-list-wtih-atp.md)に含まれる web サイトに対するものである場合、ユーザーは[警告ページ](atp-safe-links-warning-pages.md)に移動されます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-127">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
      - <span data-ttu-id="7f16a-128">悪意があると判断された web サイトに URL が設定されている場合、ユーザーは[警告ページ](atp-safe-links-warning-pages.md)にジャンプします。</span><span class="sxs-lookup"><span data-stu-id="7f16a-128">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
      - <span data-ttu-id="7f16a-129">URL がダウンロード可能なファイルに送られ、そのようなダウンロードをスキャンするように[ATP の安全なリンクポリシー](set-up-atp-safe-links-policies.md)が構成されている場合は、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-129">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
      - <span data-ttu-id="7f16a-130">URL が安全であると判断された場合は、ユーザーが web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-130">If the URL is considered safe, the user is taken to the website.</span></span>
      
      - <span data-ttu-id="7f16a-131">URL チェックに失敗すると、安全なリンクの保護はトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="7f16a-131">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="7f16a-132">デスクトップクライアントでは、ユーザーはサイトに進む前に警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-132">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>

