---
title: ドメインまたは DNS レコードを追加後に問題を特定して解決する
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: DNS レコードが正しく設定されていることを確認して、カスタムドメインのセットアップ中に発生した問題を追跡する方法について説明します。
ms.openlocfilehash: ce5aa65601a4fac763616cb67c6a4c466083a4c0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645337"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="2c90f-103">ドメインまたは DNS レコードを追加後に問題を特定して解決する</span><span class="sxs-lookup"><span data-stu-id="2c90f-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="2c90f-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c90f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2c90f-105">Microsoft 365 と連携するようにドメインを設定することは、困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="2c90f-105">Getting your domain set up to work with Microsoft 365 can be challenging.</span></span> <span data-ttu-id="2c90f-106">DNS システムは、操作するには細かい設定があり、ドメインに対する DNS のセットアップ内容は、メールなどの重要な業務活動にも影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="2c90f-106">The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="2c90f-107">ドメインに問題があるかどうかは、その状態を確認することで確認できます。</span><span class="sxs-lookup"><span data-stu-id="2c90f-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="2c90f-108">[**セットアップ**ドメイン] に移動して、[  >  **Domains** **状態**] 列に通知を表示します。</span><span class="sxs-lookup"><span data-stu-id="2c90f-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="2c90f-109">問題が発生した場合は、[その他のアクション (3 つのドット)] を選択して、[ **状態の確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c90f-109">If you see an issue, select More actions (three dots), and then choose **Check health**.</span></span> <span data-ttu-id="2c90f-110">開いているウィンドウには、ドメインで発生している問題が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c90f-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="2c90f-111">何が起こっているのでしょうか?</span><span class="sxs-lookup"><span data-stu-id="2c90f-111">What's going on?</span></span>

- [<span data-ttu-id="2c90f-112">ドメインを確認できませんか?</span><span class="sxs-lookup"><span data-stu-id="2c90f-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="2c90f-113">Outlook が動作していませんか?</span><span class="sxs-lookup"><span data-stu-id="2c90f-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="2c90f-114">すべてのユーザーのメールが Microsoft 365 に切り替えられ、電子メールの切り替えのみが必要になりましたか?</span><span class="sxs-lookup"><span data-stu-id="2c90f-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="2c90f-115">非営利団体または学校のアカウントの状態を確認できませんか?</span><span class="sxs-lookup"><span data-stu-id="2c90f-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="2c90f-116">ドメインでサービスが動作していませんか?</span><span class="sxs-lookup"><span data-stu-id="2c90f-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="2c90f-117">Web サイトへのアクセスが機能しない場合</span><span class="sxs-lookup"><span data-stu-id="2c90f-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="2c90f-118">ドメインを確認できませんか?</span><span class="sxs-lookup"><span data-stu-id="2c90f-118">Can't verify your domain?</span></span>
<span data-ttu-id="2c90f-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="2c90f-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="2c90f-120">ドメイン検証が機能しない現象には共通の原因があることが確認されています。</span><span class="sxs-lookup"><span data-stu-id="2c90f-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="2c90f-p103">**検証レコードの値が正しくない。** DNS ホストで正確な値をコピーし、TXT 検証レコードに貼り付けたことを二重に確認してください。共通の原因の 1 つに、レコードの「MS=」部分を含めていないことが挙げられています。この部分も含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c90f-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="2c90f-125">**レコードが保存されていない。**</span><span class="sxs-lookup"><span data-stu-id="2c90f-125">**The record hasn't been saved.**</span></span> <span data-ttu-id="2c90f-126">DNS ホストによっては、インターネット全体で更新されるようにゾーン ファイル (DNS レコードが保存されているファイル) を保存するという作業も必要になります。</span><span class="sxs-lookup"><span data-stu-id="2c90f-126">At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet.</span></span> <span data-ttu-id="2c90f-127">Microsoft 365 がレコードを参照および検証できるように、変更を保存したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2c90f-127">Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="2c90f-128">**レコードはインターネット経由で更新されていません。**</span><span class="sxs-lookup"><span data-stu-id="2c90f-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="2c90f-129">通常、ユーザーへの新しいレコードの表示には数分しかかかりませんが、場合によっては、数時間かかることもあります。</span><span class="sxs-lookup"><span data-stu-id="2c90f-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="2c90f-130">Outlook が機能していませんか?</span><span class="sxs-lookup"><span data-stu-id="2c90f-130">Outlook isn't working?</span></span>
<span data-ttu-id="2c90f-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="2c90f-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="2c90f-132">ドメインに MX レコードとその他の DNS レコードを正しく設定しているが、メールが機能しない場合、弊社が [Outlook 問題の解消](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)を支援します。</span><span class="sxs-lookup"><span data-stu-id="2c90f-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="2c90f-133">すべてのユーザーのメールが Microsoft 365 に切り替えられ、電子メールの切り替えのみが必要になりましたか?</span><span class="sxs-lookup"><span data-stu-id="2c90f-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="2c90f-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="2c90f-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="2c90f-135">Microsoft 365 にドメインを追加すると、通常、Microsoft 365 をポイントするようにドメインの MX レコードが365更新され、そのドメインに送信されたすべての電子メールが Microsoft の365に送られ始めます。</span><span class="sxs-lookup"><span data-stu-id="2c90f-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="2c90f-136">MX レコードを変更する前に、自分のドメインに電子メールを持っているすべてのユーザーに対して、Microsoft 365 でメールボックスを作成していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2c90f-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="2c90f-137">ドメイン上のすべてのユーザーのメールを Microsoft 365 に移動したくない場合は、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="2c90f-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="2c90f-138">[代わりに、少数のメールアドレスを使用して Microsoft 365 をパイロット](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)処理する手順を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="2c90f-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="2c90f-139">非営利団体または学校のアカウントの状態を確認できませんか?</span><span class="sxs-lookup"><span data-stu-id="2c90f-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="2c90f-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="2c90f-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="2c90f-141">組織のドメインを検証するだけで、サービスをセットアップしない場合は、いくつかのシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="2c90f-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="2c90f-142">たとえば、組織が学校のサブスクリプションに限定されていることを Microsoft 365 に証明するため。</span><span class="sxs-lookup"><span data-stu-id="2c90f-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="2c90f-143">[Microsoft 365 ドメインを検証して、所有権、非営利団体または教育機関の状態を証明する、または Yammer をアクティブに](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)して、必要なすべての手順が完了していることを確認するためのガイダンスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2c90f-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="2c90f-144">状況によって、これは少し異なります。</span><span class="sxs-lookup"><span data-stu-id="2c90f-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="2c90f-145">自分のドメインでサービスが機能しませんか?</span><span class="sxs-lookup"><span data-stu-id="2c90f-145">Services not working with your domain?</span></span>
<span data-ttu-id="2c90f-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="2c90f-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="2c90f-147">Microsoft では、ドメインの DNS セットアップに関わる問題を解消するためのサポートを用意しています。</span><span class="sxs-lookup"><span data-stu-id="2c90f-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="2c90f-148">Microsoft 365 のドメインのトラブルシューティングツールを使用すると、修正が必要なレコードと、レコードを正確に設定する必要があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="2c90f-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="2c90f-149">DNS は適切にセットアップされましたが、デスクトップ上の Outlook ではメールが機能しません。</span><span class="sxs-lookup"><span data-stu-id="2c90f-149">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop?</span></span> <span data-ttu-id="2c90f-150">[Microsoft 365 と共に使用できるさまざまなメールフローのシナリオ](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices)を確認して、ビジネスで適切に設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2c90f-150">Check out the [different mail flow scenarios you can have with Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) to make sure you've got things set up correctly for your business.</span></span> <span data-ttu-id="2c90f-151">詳細については、「Outlook の [問題を修正](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c90f-151">Or get more troubleshooting help with email here: [Fix Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="2c90f-152">自分の Web サイトにアクセスできませんか?</span><span class="sxs-lookup"><span data-stu-id="2c90f-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="2c90f-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="2c90f-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="2c90f-154">DNS の問題を解決しても、引き続き問題が発生する場合は、次のいずれかを試してください。</span><span class="sxs-lookup"><span data-stu-id="2c90f-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="2c90f-155">他のユーザーが Web サイト (www.mydomain.com) にアクセスできない場合: [Web サイトの問題を特定する](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="2c90f-155">People can't get to your website at www.mydomain.com: [Track down website issues](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span></span>
    
- <span data-ttu-id="2c90f-156">A レコードまたは CNAME レコードを更新して web サイトを参照することはできません。 [Microsoft 365 でのカスタム DNS レコードの更新](../dns/add-or-edit-custom-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="2c90f-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)</span></span>

## <a name="related-content"></a><span data-ttu-id="2c90f-157">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="2c90f-157">Related content</span></span>

[<span data-ttu-id="2c90f-158">トラブルシューティング: 検証済みドメインの変更の監査データ</span><span class="sxs-lookup"><span data-stu-id="2c90f-158">Troubleshoot: Audit data on verified domain change</span></span>](https://docs.microsoft.com/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

    
