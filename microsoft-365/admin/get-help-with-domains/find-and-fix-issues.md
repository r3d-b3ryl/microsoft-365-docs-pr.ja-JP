---
title: Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する
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
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: DNS レコードが正しく設定されていることを確認して、カスタムドメインのセットアップ中に発生した問題を追跡する方法について説明します。
ms.openlocfilehash: 277e87ad6b06db0b1ef3b3cb5eaaa45a2e77ed6f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255140"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records-in-office-365"></a><span data-ttu-id="07944-103">Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する</span><span class="sxs-lookup"><span data-stu-id="07944-103">Find and fix issues after adding your domain or DNS records in Office 365</span></span>

 <span data-ttu-id="07944-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07944-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="07944-p101">Office 365 と連携するようにドメインをセットアップすることは、骨の折れる作業になる場合があります。 DNS システムは、操作するには細かい設定があり、ドメインに対する DNS のセットアップ内容は、メールなどの重要な業務活動にも影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="07944-p101">Getting your domain set up to work with Office 365 can be challenging. The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="07944-107">ドメインに問題があるかどうかは、その状態を確認することで確認できます。</span><span class="sxs-lookup"><span data-stu-id="07944-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="07944-108">[**設定** > ] の [**ドメイン**] に移動し、[**状態**] 列に通知を表示します。</span><span class="sxs-lookup"><span data-stu-id="07944-108">Go to **Settings** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="07944-109">問題が発生した場合は、[その他のアクション (3 つのドット)] を選択して、[**状態の確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="07944-109">If you see an issue, select More actions (three dots), and then choose **Check health**.</span></span> <span data-ttu-id="07944-110">開いているウィンドウには、ドメインで発生している問題が表示されます。</span><span class="sxs-lookup"><span data-stu-id="07944-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="07944-111">何が起こっているのでしょうか?</span><span class="sxs-lookup"><span data-stu-id="07944-111">What's going on?</span></span>

- [<span data-ttu-id="07944-112">ドメインを確認できませんか?</span><span class="sxs-lookup"><span data-stu-id="07944-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="07944-113">Outlook が動作していませんか?</span><span class="sxs-lookup"><span data-stu-id="07944-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="07944-114">すべてのユーザーのメールが Office 365 に切り替えられ、メールの切り替えのみが必要になりましたか?</span><span class="sxs-lookup"><span data-stu-id="07944-114">Everyone's email got switched to Office 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="07944-115">非営利団体または学校のアカウントの状態を確認できませんか?</span><span class="sxs-lookup"><span data-stu-id="07944-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="07944-116">ドメインでサービスが動作していませんか?</span><span class="sxs-lookup"><span data-stu-id="07944-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="07944-117">Web サイトへのアクセスが機能しない場合</span><span class="sxs-lookup"><span data-stu-id="07944-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="07944-118">ドメインを確認できませんか?</span><span class="sxs-lookup"><span data-stu-id="07944-118">Can't verify your domain?</span></span>
<span data-ttu-id="07944-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="07944-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="07944-120">ドメイン検証が機能しない現象には共通の原因があることが確認されています。</span><span class="sxs-lookup"><span data-stu-id="07944-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="07944-p103">**検証レコードの値が正しくない。** DNS ホストで正確な値をコピーし、TXT 検証レコードに貼り付けたことを二重に確認してください。共通の原因の 1 つに、レコードの「MS=」部分を含めていないことが挙げられています。この部分も含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="07944-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="07944-p104">**レコードが保存されていない。** DNS ホストによっては、インターネット全体で更新されるようにゾーン ファイル (DNS レコードが保存されているファイル) を保存するという作業も必要になります。Office 365 がレコードを表示し、確認できるように、変更内容を必ず保存してください。</span><span class="sxs-lookup"><span data-stu-id="07944-p104">**The record hasn't been saved.** At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet. Make sure you've saved your changes so Office 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="07944-128">**レコードはインターネット経由で更新されていません。**</span><span class="sxs-lookup"><span data-stu-id="07944-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="07944-129">通常、ユーザーへの新しいレコードの表示には数分しかかかりませんが、場合によっては、数時間かかることもあります。</span><span class="sxs-lookup"><span data-stu-id="07944-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="07944-130">Outlook が機能していませんか?</span><span class="sxs-lookup"><span data-stu-id="07944-130">Outlook isn't working?</span></span>
<span data-ttu-id="07944-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="07944-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="07944-132">ドメインに MX レコードとその他の DNS レコードを正しく設定しているが、メールが機能しない場合、弊社が [Outlook 問題の解消](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx)を支援します。</span><span class="sxs-lookup"><span data-stu-id="07944-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span></span>
  
## <a name="everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="07944-133">すべてのユーザーのメールが Office 365 に切り替えられ、メールの切り替えのみが必要になりましたか?</span><span class="sxs-lookup"><span data-stu-id="07944-133">Everyone's email got switched to Office 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="07944-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="07944-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="07944-135">Office 365 にドメインを追加すると、通常は、ドメインの MX レコードが (ユーザーまたは Office 365 によって) Office 365 をポイントするように更新され、そのドメインに送信されるすべての電子メールが Office の365に送られ始めます。</span><span class="sxs-lookup"><span data-stu-id="07944-135">When you add your domain to Office 365, typically your domain's MX record is updated (by you or Office 365) to point to Office 365, and ALL email sent to that domain will start coming to Office 365.</span></span> <span data-ttu-id="07944-136">MX レコードを変更する前に、自分のドメインにメールを持っているすべてのユーザーに対して Office 365 でメールボックスを作成していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="07944-136">Make sure you've created mailboxes in Office 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="07944-137">ドメイン上のすべてのユーザーのメールを Office 365 に移動したくない場合は、どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="07944-137">What if you don't want to move email for everyone on your domain to Office 365?</span></span> <span data-ttu-id="07944-138">[代わりに、少数のメールアドレスで Office 365 のパイロット](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx)を実施するための手順を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="07944-138">You can take steps to [pilot Office 365 with just a few email addresses instead](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="07944-139">非営利団体または学校のアカウントの状態を確認できませんか?</span><span class="sxs-lookup"><span data-stu-id="07944-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="07944-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="07944-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="07944-141">組織のドメインを検証するだけで、サービスをセットアップしない場合は、いくつかのシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="07944-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="07944-142">たとえば、組織が学校のサブスクリプションを認定していることを Office 365 に証明する場合などです。</span><span class="sxs-lookup"><span data-stu-id="07944-142">For example, to prove to Office 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="07944-143">[「Office 365 ドメインの確認」を参照して、所有権、非営利団体または教育機関の状態を証明するか、Yammer を有効](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590)にして必要なすべての手順を完了したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="07944-143">Check out the guidance in [Verify your Office 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="07944-144">状況によって、これは少し異なります。</span><span class="sxs-lookup"><span data-stu-id="07944-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="07944-145">自分のドメインでサービスが機能しませんか?</span><span class="sxs-lookup"><span data-stu-id="07944-145">Services not working with your domain?</span></span>
<span data-ttu-id="07944-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="07944-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="07944-147">Microsoft では、ドメインの DNS セットアップに関わる問題を解消するためのサポートを用意しています。</span><span class="sxs-lookup"><span data-stu-id="07944-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="07944-148">Office 365 でドメインのトラブルシューティング ツールを起動すると、修正が必要なすべてのレコードと、レコードに設定する必要がある内容そのものが表示されます。</span><span class="sxs-lookup"><span data-stu-id="07944-148">The domains troubleshooter in Office 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="07944-p111">DNS は正しくセットアップされたが、デスクトップの Outlook でメールが機能しない場合は、「 [different mail flow scenarios you can have with Office 365 (Office 365 で実現できるその他のメール フローのシナリオ)](https://go.microsoft.com/fwlink/?LinkId=787530)」を参照して、お客様のビジネスに合わせて正しく設定されていることをご確認ください。または、次のサイトでメールに関するトラブルシューティングを参照してください。[Outlook でのエラーを修正する](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx)</span><span class="sxs-lookup"><span data-stu-id="07944-p111">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop? Check out the [different mail flow scenarios you can have with Office 365](https://go.microsoft.com/fwlink/?LinkId=787530) to make sure you've got things set up correctly for your business. Or get more troubleshooting help with email here: [Fix Outlook problems](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="07944-152">自分の Web サイトにアクセスできませんか?</span><span class="sxs-lookup"><span data-stu-id="07944-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="07944-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="07944-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="07944-154">DNS の問題を解決しても、引き続き問題が発生する場合は、次のいずれかを試してください。</span><span class="sxs-lookup"><span data-stu-id="07944-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="07944-155">他のユーザーが Web サイト (www.mydomain.com) にアクセスできない場合: [Web サイトの問題を特定する](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)</span><span class="sxs-lookup"><span data-stu-id="07944-155">People can't get to your website at www.mydomain.com: [Track down website issues](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)</span></span>
    
- <span data-ttu-id="07944-156">A レコードまたは CNAME レコードが Web サイトを示すように更新できない場合: [Office 365 でカスタムの DNS レコードを更新する](../dns/add-or-edit-custom-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="07944-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Office 365](../dns/add-or-edit-custom-dns-records.md)</span></span>
    
