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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: DNS レコードが正しく設定されていることを確認して、カスタム ドメインのセットアップ中に発生した問題を追跡する方法について説明します。
ms.openlocfilehash: dfb3c93c169a3d31c14d912ddd2cc94fb1e4ace1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915640"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="49ddf-103">ドメインまたは DNS レコードを追加後に問題を特定して解決する</span><span class="sxs-lookup"><span data-stu-id="49ddf-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="49ddf-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ddf-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="49ddf-105">Microsoft 365 で動作するドメインを設定するには、困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="49ddf-105">Getting your domain set up to work with Microsoft 365 can be challenging.</span></span> <span data-ttu-id="49ddf-106">DNS システムは、操作するには細かい設定があり、ドメインに対する DNS のセットアップ内容は、メールなどの重要な業務活動にも影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="49ddf-106">The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="49ddf-107">ドメインの状態を確認することで、ドメインに関する問題を確認できます。</span><span class="sxs-lookup"><span data-stu-id="49ddf-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="49ddf-108">[ドメインの **セットアップ**  >  **] に移動** し、[状態] 列に通知 **を表示** します。</span><span class="sxs-lookup"><span data-stu-id="49ddf-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="49ddf-109">問題が発生した場合は、[その他のアクション (3 つのドット) を選択し、[正常性の確認] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="49ddf-109">If you see an issue, select More actions (three dots), and then choose **Check health**.</span></span> <span data-ttu-id="49ddf-110">開くウィンドウは、ドメインで発生する問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="49ddf-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="49ddf-111">何が起こっているのでしょうか?</span><span class="sxs-lookup"><span data-stu-id="49ddf-111">What's going on?</span></span>

- [<span data-ttu-id="49ddf-112">ドメインを確認できない場合</span><span class="sxs-lookup"><span data-stu-id="49ddf-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="49ddf-113">Outlook が動作していませんか?</span><span class="sxs-lookup"><span data-stu-id="49ddf-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="49ddf-114">すべてのユーザーのメールが Microsoft 365 に切り替え、メールの切り替えのみを望んだ場合</span><span class="sxs-lookup"><span data-stu-id="49ddf-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="49ddf-115">非営利団体または学校のアカウントの状態を確認できませんか?</span><span class="sxs-lookup"><span data-stu-id="49ddf-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="49ddf-116">サービスがドメインで動作しない場合</span><span class="sxs-lookup"><span data-stu-id="49ddf-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="49ddf-117">Web サイトへのアクセスが機能していませんか?</span><span class="sxs-lookup"><span data-stu-id="49ddf-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="49ddf-118">ドメインを確認できませんか?</span><span class="sxs-lookup"><span data-stu-id="49ddf-118">Can't verify your domain?</span></span>
<span data-ttu-id="49ddf-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="49ddf-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="49ddf-120">ドメイン検証が機能しない現象には共通の原因があることが確認されています。</span><span class="sxs-lookup"><span data-stu-id="49ddf-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="49ddf-p103">**検証レコードの値が正しくない。** DNS ホストで正確な値をコピーし、TXT 検証レコードに貼り付けたことを二重に確認してください。共通の原因の 1 つに、レコードの「MS=」部分を含めていないことが挙げられています。この部分も含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="49ddf-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="49ddf-125">**レコードが保存されていない。**</span><span class="sxs-lookup"><span data-stu-id="49ddf-125">**The record hasn't been saved.**</span></span> <span data-ttu-id="49ddf-126">DNS ホストによっては、インターネット全体で更新されるようにゾーン ファイル (DNS レコードが保存されているファイル) を保存するという作業も必要になります。</span><span class="sxs-lookup"><span data-stu-id="49ddf-126">At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet.</span></span> <span data-ttu-id="49ddf-127">Microsoft 365 がレコードを表示および確認できるよう、変更を保存済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="49ddf-127">Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="49ddf-128">**レコードがインターネット上で更新されません。**</span><span class="sxs-lookup"><span data-stu-id="49ddf-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="49ddf-129">通常、ユーザーへの新しいレコードの表示には数分しかかかりませんが、場合によっては、数時間かかることもあります。</span><span class="sxs-lookup"><span data-stu-id="49ddf-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="49ddf-130">Outlook が機能していませんか?</span><span class="sxs-lookup"><span data-stu-id="49ddf-130">Outlook isn't working?</span></span>
<span data-ttu-id="49ddf-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="49ddf-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="49ddf-132">ドメインに MX レコードとその他の DNS レコードを正しく設定しているが、メールが機能しない場合、弊社が [Outlook 問題の解消](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)を支援します。</span><span class="sxs-lookup"><span data-stu-id="49ddf-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="49ddf-133">すべてのユーザーのメールが Microsoft 365 に切り替え、メールの切り替えのみを望んだ場合</span><span class="sxs-lookup"><span data-stu-id="49ddf-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="49ddf-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="49ddf-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="49ddf-135">ドメインを Microsoft 365 に追加すると、通常、ドメインの MX レコードが Microsoft 365 を指す (ユーザーまたは Microsoft 365 によって) 更新され、そのドメインに送信されたメールはすべて Microsoft 365 に送信されます。</span><span class="sxs-lookup"><span data-stu-id="49ddf-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="49ddf-136">MX レコードを変更する前に、ドメインにメールを送信しているすべてのユーザーに対して Microsoft 365 でメールボックスを作成してください。</span><span class="sxs-lookup"><span data-stu-id="49ddf-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="49ddf-137">ドメイン上のすべてのユーザーのメールを Microsoft 365 に移動しない場合は、</span><span class="sxs-lookup"><span data-stu-id="49ddf-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="49ddf-138">代わりに、少数の電子メール アドレスで [Microsoft 365 をパイロットするための手順を実行できます](../setup/domains-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="49ddf-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](../setup/domains-faq.yml).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="49ddf-139">非営利団体または学校のアカウントの状態を確認できませんか?</span><span class="sxs-lookup"><span data-stu-id="49ddf-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="49ddf-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="49ddf-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="49ddf-141">組織のドメインを確認し、サービスを設定しない場合は、いくつかのシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="49ddf-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="49ddf-142">たとえば、組織が学校のサブスクリプションの資格を持っていることを Microsoft 365 に証明します。</span><span class="sxs-lookup"><span data-stu-id="49ddf-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="49ddf-143">「Microsoft [365](../setup/domains-faq.yml) ドメインの確認」のガイダンスを参照して、所有権、非営利団体、または教育の状態を証明するか、Yammer をアクティブ化して、必要なすべての手順を完了してください。</span><span class="sxs-lookup"><span data-stu-id="49ddf-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](../setup/domains-faq.yml) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="49ddf-144">状況ごとに少し異なります。</span><span class="sxs-lookup"><span data-stu-id="49ddf-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="49ddf-145">自分のドメインでサービスが機能しませんか?</span><span class="sxs-lookup"><span data-stu-id="49ddf-145">Services not working with your domain?</span></span>
<span data-ttu-id="49ddf-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="49ddf-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="49ddf-147">Microsoft では、ドメインの DNS セットアップに関わる問題を解消するためのサポートを用意しています。</span><span class="sxs-lookup"><span data-stu-id="49ddf-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="49ddf-148">Microsoft 365 のドメインのトラブルシューティング ツールには、修正が必要なレコードと、レコードを設定する必要があるレコードが正確に表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ddf-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="49ddf-149">DNS が正しく設定されましたが、デスクトップ上の Outlook でメールが機能しない場合</span><span class="sxs-lookup"><span data-stu-id="49ddf-149">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop?</span></span> <span data-ttu-id="49ddf-150">[Microsoft 365](/exchange/mail-flow-best-practices/mail-flow-best-practices)で使用できるさまざまなメール フロー シナリオを確認して、ビジネスに合った設定が正しく行なされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="49ddf-150">Check out the [different mail flow scenarios you can have with Microsoft 365](/exchange/mail-flow-best-practices/mail-flow-best-practices) to make sure you've got things set up correctly for your business.</span></span> <span data-ttu-id="49ddf-151">または、電子メールに関するトラブルシューティングのヘルプの詳細については [、Outlook の問題を解決してください](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)。</span><span class="sxs-lookup"><span data-stu-id="49ddf-151">Or get more troubleshooting help with email here: [Fix Outlook problems](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="49ddf-152">自分の Web サイトにアクセスできませんか?</span><span class="sxs-lookup"><span data-stu-id="49ddf-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="49ddf-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="49ddf-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="49ddf-154">DNS の問題を解決しても、引き続き問題が発生する場合は、次のいずれかを試してください。</span><span class="sxs-lookup"><span data-stu-id="49ddf-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="49ddf-155">他のユーザーが Web サイト (www.mydomain.com) にアクセスできない場合: [Web サイトの問題を特定する](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="49ddf-155">People can't get to your website at www.mydomain.com: [Track down website issues](../setup/add-domain.md)</span></span>
    
- <span data-ttu-id="49ddf-156">Web サイトを指す A レコードまたは CNAME レコードを更新できない[:Microsoft 365](../setup/add-domain.md)のカスタム DNS レコードを更新する</span><span class="sxs-lookup"><span data-stu-id="49ddf-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../setup/add-domain.md)</span></span>

## <a name="related-content"></a><span data-ttu-id="49ddf-157">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="49ddf-157">Related content</span></span>

[<span data-ttu-id="49ddf-158">トラブルシューティング: 検証済みのドメイン変更に関するデータの監査</span><span class="sxs-lookup"><span data-stu-id="49ddf-158">Troubleshoot: Audit data on verified domain change</span></span>](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

