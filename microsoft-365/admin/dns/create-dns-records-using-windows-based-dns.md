---
title: Windows ベースの DNS を使用して Microsoft の DNS レコードを作成する
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: ドメインを確認し、Windows ベースの DNS for Microsoft で電子メール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 9e5e42f847e740571944ea3db205282ec9a7a0e6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916048"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a><span data-ttu-id="0f4b3-103">Windows ベースの DNS を使用して Microsoft の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="0f4b3-103">Create DNS records for Microsoft using Windows-based DNS</span></span>

 <span data-ttu-id="0f4b3-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
   
<span data-ttu-id="0f4b3-105">Windows ベースの DNS を使用して独自の DNS レコードをホストする場合は、この記事の手順に従って、電子メール、Skype for Business Online などのためにレコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-105">If you host your own DNS records using Windows-based DNS, follow the steps in this article to set up your records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="0f4b3-106">開始するには [、Windows](#find-your-dns-records-in-windows-based-dns) ベースの DNS で DNS レコードを見つけて更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-106">To get started, you need to [find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns) so you can update them.</span></span> <span data-ttu-id="0f4b3-107">また、オンプレミスの Active Directory と Microsoft の同期を計画している場合は [、「On-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)で UPN として使用される展開不可の電子メール アドレス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-107">Also, if you're planning to synchronize your on-premises Active Directory with Microsoft, see [Non-routable email address used as a UPN in your on-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).</span></span>
  
<span data-ttu-id="0f4b3-108">DNS レコードを追加した後のメール フローなどの問題に関する問題については、「ドメイン名または DNS レコードを変更した後の問題のトラブルシューティング [」を参照してください](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-108">Trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a><span data-ttu-id="0f4b3-109">Windows ベース DNS 内の DNS レコードを検索する</span><span class="sxs-lookup"><span data-stu-id="0f4b3-109">Find your DNS records in Windows-based DNS</span></span>
<span data-ttu-id="0f4b3-110"><a name="BKMK_find_your_dns_1"></a>ドメインの DNS レコードがあるページに移動します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-110"><a name="BKMK_find_your_dns_1"> </a> Go to the page that has the DNS records for your domain.</span></span> <span data-ttu-id="0f4b3-111">Windows Server 2008 で作業している場合は、[実行の開始]**に移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-111">If you're working in Windows Server 2008, go to **Start** > **Run**.</span></span> <span data-ttu-id="0f4b3-112">このウィンドウで作業している場合Windows Server 2012 Windows キーを押して r を **押します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-112">If you're working in Windows Server 2012, press the Windows key and **r**.</span></span> <span data-ttu-id="0f4b3-113">**「dnsmgmnt.msc」と** 入力し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-113">Type **dnsmgmnt.msc**, and then select **OK**.</span></span> <span data-ttu-id="0f4b3-114">DNS マネージャーで、[前方参照領域 **\<DNS server name\> \> ] を展開します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-114">In DNS Manager, expand **\<DNS server name\>  \> Forward Lookup Zones**.</span></span> <span data-ttu-id="0f4b3-115">ドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-115">Select your domain.</span></span> <span data-ttu-id="0f4b3-116">これで、DNS レコードを作成する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-116">You're now ready to create the DNS records.</span></span>
   
## <a name="add-mx-record"></a><span data-ttu-id="0f4b3-117">MX レコードの追加</span><span class="sxs-lookup"><span data-stu-id="0f4b3-117">Add MX record</span></span>
<span data-ttu-id="0f4b3-118"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0f4b3-118"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="0f4b3-119">ドメインのメールが Microsoft に送信される MX レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-119">Add an MX record so email for your domain will come to Microsoft.</span></span>
- <span data-ttu-id="0f4b3-120">追加する MX レコードには、MSxxxxxxx のような値である .mail.protection.outlook.com のような値 (アドレスのポイント値) が含 \<MX token\> \<MX token\> まれます。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-120">The MX record you'll add includes a value (the **Points to address** value) that looks something like this: \<MX token\>.mail.protection.outlook.com, where \<MX token\> is a value like MSxxxxxxx.</span></span> 
- <span data-ttu-id="0f4b3-121">Microsoft の [DNS レコードの追加] ページの [Exchange Online] セクションの MX 行から、[ポイント先アドレス] の下に一覧表示されている値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-121">From the MX row in the Exchange Online section of the Add DNS records page in Microsoft, copy the value listed under Points to address.</span></span> <span data-ttu-id="0f4b3-122">この値は、このタスクで作成するレコードで使用します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-122">You'll use this value in the record you're creating in this task.</span></span> 
- <span data-ttu-id="0f4b3-123">ドメインの [DNS マネージャー] ページで、[アクション メール エクスチェンジャー  >  **( MX) ] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-123">On the DNS Manager page for the domain, go to **Action** > **Mail Exchanger (MX)**.</span></span> <span data-ttu-id="0f4b3-124">ドメインのこのページを見つけるには、「Windows ベースの DNS で DNS レコードを検索 [する」を参照してください](#find-your-dns-records-in-windows-based-dns)。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-124">To find this page for the domain, see [Find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns).</span></span>  
- <span data-ttu-id="0f4b3-125">[新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-125">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span> 
    - <span data-ttu-id="0f4b3-126">Host Name: </span><span class="sxs-lookup"><span data-stu-id="0f4b3-126">Host Name:</span></span> 
    - <span data-ttu-id="0f4b3-127">@Address: ここで、Microsoft からコピーしたアドレス値にポイントを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-127">@Address: Paste the Points to address  value that you just copied from Microsoft here.</span></span>  
    - <span data-ttu-id="0f4b3-128">Pref:</span><span class="sxs-lookup"><span data-stu-id="0f4b3-128">Pref:</span></span> 
- <span data-ttu-id="0f4b3-129">[変更 **の保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-129">Select **Save Changes**.</span></span>
- <span data-ttu-id="0f4b3-130">古い MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-130">Remove any obsolete MX records.</span></span> <span data-ttu-id="0f4b3-131">電子メールを別の場所にルーティングするこのドメインの古い MX レコードがある場合は、各古いレコードの横にあるチェックボックスをオンにし、[OK の削除] を  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-131">If you have any old MX records for this domain that route email somewhere else, select the check box next to each old record, and then select **Delete** > **OK**.</span></span> 
   
## <a name="add-cname-records"></a><span data-ttu-id="0f4b3-132">CNAME レコードの追加</span><span class="sxs-lookup"><span data-stu-id="0f4b3-132">Add CNAME records</span></span>
<span data-ttu-id="0f4b3-133"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0f4b3-133"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="0f4b3-134">Microsoft に必要な CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-134">Add the CNAME records that are required for Microsoft.</span></span> <span data-ttu-id="0f4b3-135">Microsoft に追加の CNAME レコードが表示されている場合は、ここに示すのと同じ一般的な手順に従ってレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-135">If additional CNAME records are listed in Microsoft, add those following the same general steps shown here.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0f4b3-136">Microsoft 用のモバイル デバイス管理 (MDM) がある場合は、2 つの追加の CNAME レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-136">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="0f4b3-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0f4b3-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="0f4b3-138">(MDM を使用していない場合は、この手順を省略できます)。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-138">(If you do not have MDM, you can skip this step.)</span></span> 

- <span data-ttu-id="0f4b3-139">ドメインの [DNS マネージャー] ページで、[アクション  >  **CNAME] (CNAME) に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-139">On the DNS Manager page for the domain, go to **Action** > **CNAME (CNAME)**.</span></span>
- <span data-ttu-id="0f4b3-140">[新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-140">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="0f4b3-141">ホスト名: 自動検出</span><span class="sxs-lookup"><span data-stu-id="0f4b3-141">Host Name: autodiscover</span></span>
    - <span data-ttu-id="0f4b3-142">種類:</span><span class="sxs-lookup"><span data-stu-id="0f4b3-142">Type:</span></span> 
    - <span data-ttu-id="0f4b3-143">CNAMEAddress: autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0f4b3-143">CNAMEAddress: autodiscover.outlook.com</span></span>
- <span data-ttu-id="0f4b3-144">[O **K] を** 選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-144">Select **O** K.</span></span>

<span data-ttu-id="0f4b3-145">SIP CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-145">Add the SIP CNAME record.</span></span> 
- <span data-ttu-id="0f4b3-146">ドメインの [DNS マネージャー] ページで、[アクション \> **CNAME] (CNAME) に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-146">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="0f4b3-147">[新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-147">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="0f4b3-148">ホスト名: sip</span><span class="sxs-lookup"><span data-stu-id="0f4b3-148">Host Name: sip</span></span>
    - <span data-ttu-id="0f4b3-149">種類: CNAME</span><span class="sxs-lookup"><span data-stu-id="0f4b3-149">Type: CNAME</span></span>
    - <span data-ttu-id="0f4b3-150">アドレス: sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0f4b3-150">Address: sipdir.online.lync.com</span></span>
- <span data-ttu-id="0f4b3-151">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-151">Select **OK**.</span></span>

<span data-ttu-id="0f4b3-152">Skype for Business Online 自動検出 CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-152">Add the Skype for Business Online Autodiscover CNAME record.</span></span>  
- <span data-ttu-id="0f4b3-153">ドメインの [DNS マネージャー] ページで、[アクション \> **CNAME] (CNAME) に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-153">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> <span data-ttu-id="0f4b3-154">[新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-154">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="0f4b3-155">ホスト名: lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0f4b3-155">Host Name: lyncdiscover</span></span>
    - <span data-ttu-id="0f4b3-156">種類: CNAME</span><span class="sxs-lookup"><span data-stu-id="0f4b3-156">Type: CNAME</span></span>
    - <span data-ttu-id="0f4b3-157">アドレス: webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0f4b3-157">Address: webdir.online.lync.com</span></span>
- <span data-ttu-id="0f4b3-158">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-158">Select **OK**.</span></span>
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a><span data-ttu-id="0f4b3-159">Microsoft のモバイル デバイス管理 (MDM) に 2 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="0f4b3-159">Add two CNAME records for Mobile Device Management (MDM) for Microsoft</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f4b3-160">Microsoft 用のモバイル デバイス管理 (MDM) がある場合は、2 つの追加の CNAME レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-160">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="0f4b3-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0f4b3-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="0f4b3-162">>(MDM をお持ちではない場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-162">>(If you do not have MDM, you can skip this step.)</span></span> 
  

<span data-ttu-id="0f4b3-163">MDM Enterpriseregistration CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-163">Add the MDM Enterpriseregistration CNAME record.</span></span>  
- <span data-ttu-id="0f4b3-164">ドメインの [DNS マネージャー] ページで、[アクション \> **CNAME] (CNAME) に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-164">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="0f4b3-165">[新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-165">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
- <span data-ttu-id="0f4b3-166">ホスト名: enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0f4b3-166">Host Name: enterpriseregistration</span></span>
- <span data-ttu-id="0f4b3-167">種類: CNAME</span><span class="sxs-lookup"><span data-stu-id="0f4b3-167">Type: CNAME</span></span>
- <span data-ttu-id="0f4b3-168">アドレス: enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="0f4b3-168">Address: enterpriseregistration.windows.net</span></span>
- <span data-ttu-id="0f4b3-169">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-169">Select **OK**.</span></span> 

<span data-ttu-id="0f4b3-170">MDM Enterpriseenrollment CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-170">Add the MDM Enterpriseenrollment CNAME record.</span></span> 
-  <span data-ttu-id="0f4b3-171">ドメインの [DNS マネージャー] ページで、[アクション \> **CNAME] (CNAME) に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-171">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
-  <span data-ttu-id="0f4b3-172">[新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-172">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="0f4b3-173">ホスト名: enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0f4b3-173">Host Name: enterpriseenrollment</span></span>
    - <span data-ttu-id="0f4b3-174">種類: CNAME</span><span class="sxs-lookup"><span data-stu-id="0f4b3-174">Type: CNAME</span></span>
    - <span data-ttu-id="0f4b3-175">アドレス: enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0f4b3-175">Address: enterpriseenrollment-s.manage.microsoft.com</span></span>
- <span data-ttu-id="0f4b3-176">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-176">Select **OK**.</span></span>
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0f4b3-177">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="0f4b3-177">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0f4b3-178"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="0f4b3-178"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f4b3-179">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-179">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0f4b3-180">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-180">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0f4b3-181">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-181">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="0f4b3-182">代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1*  つの SPF レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-182">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="0f4b3-183">ドメインの SPF TXT レコードを追加して、メールスパムを防止します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-183">Add the SPF TXT record for your domain to help prevent email spam.</span></span>
  
- <span data-ttu-id="0f4b3-184">このレコードの TXT 値に他の文字列 (マーケティングメール用の文字列など) が既に含まれる場合があります。これは問題ありません。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-184">You might already have other strings in the TXT value for this record (such as strings for marketing email), which is fine.</span></span> <span data-ttu-id="0f4b3-185">これらの文字列はそのままにし、この文字列を追加し、各文字列を二重引用符で囲み、それらを分離します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-185">Leave those strings in place and add this one, placing double-quotes around each string to separate them.</span></span> 
- <span data-ttu-id="0f4b3-186">ドメインの [DNS マネージャー] ページで、[アクション テキスト ] \> **(TXT) に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-186">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-  <span data-ttu-id="0f4b3-187">[新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-187">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 
 > [!IMPORTANT]
> <span data-ttu-id="0f4b3-188">一部のバージョンの Windows DNS Manager では、txt レコードを作成するときにホーム名が既定で親ドメインに設定されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-188">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="0f4b3-189">この状況では、TXT レコードを追加するときに、ホスト名を @ またはドメイン名に設定する代わりに、ホスト名を空白 (値なし) に設定します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-189">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

-  <span data-ttu-id="0f4b3-190">ホストの種類:@</span><span class="sxs-lookup"><span data-stu-id="0f4b3-190">Host type: @</span></span>
-  <span data-ttu-id="0f4b3-191">レコードの種類: TXT</span><span class="sxs-lookup"><span data-stu-id="0f4b3-191">Record Type: TXT</span></span>
-  <span data-ttu-id="0f4b3-192">アドレス: v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0f4b3-192">Address: v=spf1 include:spf.protection.outlook.com -all</span></span> 
         
-  <span data-ttu-id="0f4b3-193">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-193">Select **OK**.</span></span>
   
## <a name="add-srv-records"></a><span data-ttu-id="0f4b3-194">SRV レコードの追加</span><span class="sxs-lookup"><span data-stu-id="0f4b3-194">Add SRV records</span></span>
<span data-ttu-id="0f4b3-195"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="0f4b3-195"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="0f4b3-196">Microsoft に必要な 2 つの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-196">Add the two SRV records that are required for Microsoft.</span></span>

<span data-ttu-id="0f4b3-197">Skype for Business Online Web 会議の SIP SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-197">Add the SIP SRV record for Skype for Business Online web conferencing.</span></span>  <br/> 
-  <span data-ttu-id="0f4b3-198">ドメインの [DNS マネージャー] ページで、[アクション] [その他の **新しい** \> **レコード] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-198">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span> 
-   <span data-ttu-id="0f4b3-199">[リソース **レコードの種類] ウィンドウで** 、[サービスの場所 **] (SRV)** を選択し、[レコードの作成] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-199">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="0f4b3-200">[新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-200">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="0f4b3-201">サービス: _sip</span><span class="sxs-lookup"><span data-stu-id="0f4b3-201">Service: _sip</span></span>
    -  <span data-ttu-id="0f4b3-202">プロトコル: _tls</span><span class="sxs-lookup"><span data-stu-id="0f4b3-202">Protocol: _tls</span></span>
    -  <span data-ttu-id="0f4b3-203">優先度: 100</span><span class="sxs-lookup"><span data-stu-id="0f4b3-203">Priority: 100</span></span>
    -  <span data-ttu-id="0f4b3-204">重み: 1</span><span class="sxs-lookup"><span data-stu-id="0f4b3-204">Weight: 1</span></span>
    -  <span data-ttu-id="0f4b3-205">ポート: 443</span><span class="sxs-lookup"><span data-stu-id="0f4b3-205">Port: 443</span></span>
    -  <span data-ttu-id="0f4b3-206">ターゲット (ホスト名): sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0f4b3-206">Target (Hostname): sipdir.online.lync.com</span></span>
-  <span data-ttu-id="0f4b3-207">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-207">Select **OK**.</span></span> 


<span data-ttu-id="0f4b3-208">Skype for Business Online フェデレーションの SIP SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-208">Add the SIP SRV record for Skype for Business Online federation.</span></span>  
-  <span data-ttu-id="0f4b3-209">ドメインの [DNS マネージャー] ページで、[アクション] [その他の **新しい** \> **レコード] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-209">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span>  
-  <span data-ttu-id="0f4b3-210">[リソース **レコードの種類] ウィンドウで** 、[サービスの場所 **] (SRV)** を選択し、[レコードの作成] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-210">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="0f4b3-211">[新しい **リソース レコード]** ダイアログ ボックスで、フィールドが次の値に正確に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-211">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="0f4b3-212">サービス: _sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="0f4b3-212">Service: _sipfederationtls</span></span>
    -  <span data-ttu-id="0f4b3-213">プロトコル: _tcp</span><span class="sxs-lookup"><span data-stu-id="0f4b3-213">Protocol: _tcp</span></span>
    -  <span data-ttu-id="0f4b3-214">優先度: 100</span><span class="sxs-lookup"><span data-stu-id="0f4b3-214">Priority: 100</span></span>
    -  <span data-ttu-id="0f4b3-215">重み: 1</span><span class="sxs-lookup"><span data-stu-id="0f4b3-215">Weight: 1</span></span>
    -  <span data-ttu-id="0f4b3-216">ポート: 5061</span><span class="sxs-lookup"><span data-stu-id="0f4b3-216">Port: 5061</span></span>
    -  <span data-ttu-id="0f4b3-217">ターゲット (ホスト名): sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0f4b3-217">Target (Hostname): sipfed.online.lync.com</span></span>
-  <span data-ttu-id="0f4b3-218">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-218">Select **OK**.</span></span> 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a><span data-ttu-id="0f4b3-219">まだドメインを所有していない場合は、レコードを追加してドメインを所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-219">Add a record to verify that you own the domain, if you haven't already</span></span>
<span data-ttu-id="0f4b3-220"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0f4b3-220"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="0f4b3-221">Microsoft サービスをセットアップするために DNS レコードを追加する前に、追加するドメインを所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-221">Before you add the DNS records to set up your Microsoft services, Microsoft has to confirm that you own the domain you're adding.</span></span> <span data-ttu-id="0f4b3-222">これを行うには、以下の手順に従ってレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-222">To do this, you add a record, following the steps below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0f4b3-223">このレコードは、ドメインを所有していることを確認する場合にのみ使用します。その他には影響しません。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-223">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> 
  

1. <span data-ttu-id="0f4b3-224">Microsoft から情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-224">Gather information from Microsoft.</span></span>  <br/> 
2. <span data-ttu-id="0f4b3-225">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-225">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span> 
3. <span data-ttu-id="0f4b3-226">[ドメイン **] ページで**、確認するドメインの [アクション] 列で、[セットアップの開始]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-226">On the **Domains** page, in the **Actions** column for the domain that you are verifying, select **Start setup**.</span></span> 
4. <span data-ttu-id="0f4b3-227">[Microsoft に **ドメインを追加する] ページで** 、[手順 **1 の開始] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-227">On the **Add a domain to Microsoft** page, select **Start step 1**.</span></span> 
5. <span data-ttu-id="0f4b3-228">[自分の **ドメインを所有することを確認** する] ページの [この手順を実行するための手順を表示する] ドロップダウン リストで、[全般手順]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-228">On the **Confirm that you own your domain** page, in the **See instructions for performing this step with** drop-down list, choose **General instructions**.</span></span> 
6. <span data-ttu-id="0f4b3-229">表から、[宛先] または [ポイントからアドレス] の値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-229">From the table, copy the Destination or Points to Address value.</span></span> <span data-ttu-id="0f4b3-230">次の手順に必要です。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-230">You'll need it for the next step.</span></span> <span data-ttu-id="0f4b3-231">この値をコピーして貼り付け、すべての間隔が正しいままにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-231">We recommend copying and pasting this value, so that all of the spacing stays correct.</span></span>

<span data-ttu-id="0f4b3-232">TXT レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-232">Add a TXT record.</span></span> 
-  <span data-ttu-id="0f4b3-233">ドメインの [DNS マネージャー] ページで、[アクション テキスト ] \> **(TXT) に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-233">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-   <span data-ttu-id="0f4b3-234">[新しい **リソース レコード] ダイアログ ボックス** で、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-234">In the **New Resource Record** dialog box, select **Edit**.</span></span>  
-  <span data-ttu-id="0f4b3-235">[新 **しいリソース レコード]** ダイアログ ボックスの [カスタム ホスト名] 領域で、フィールドが次の値に正確に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-235">In the **Custom Host Names** area of the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 

> [!IMPORTANT] 
> <span data-ttu-id="0f4b3-236">一部のバージョンの Windows DNS Manager では、txt レコードを作成するときにホーム名が既定で親ドメインに設定されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-236">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="0f4b3-237">この状況では、TXT レコードを追加するときに、ホスト名を @ またはドメイン名に設定する代わりに、ホスト名を空白 (値なし) に設定します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-237">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

- <span data-ttu-id="0f4b3-238">ホスト名:@</span><span class="sxs-lookup"><span data-stu-id="0f4b3-238">Host Name: @</span></span>
- <span data-ttu-id="0f4b3-239">タイプ: TXT</span><span class="sxs-lookup"><span data-stu-id="0f4b3-239">Type: TXT</span></span>
- <span data-ttu-id="0f4b3-240">[アドレス]: Microsoft からコピーした [宛先] または [ポイント先アドレス] の値をここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-240">Address: Paste the Destination or Points to Address value that you just copied from Microsoft here.</span></span>  
- <span data-ttu-id="0f4b3-241">[OK **完了] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-241">Select **OK** > **Done**.</span></span>

<span data-ttu-id="0f4b3-242">Microsoft でドメインを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-242">Verify your domain in Microsoft.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="0f4b3-243">これを行う前に約 15 分待つ必要があります。そのため、作成したレコードはインターネットを通して更新できます。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-243">Wait about 15 minutes before you do this, so the record you just created can update across the Internet.</span></span>       

- <span data-ttu-id="0f4b3-244">Microsoft に戻り、以下の手順に従って検証チェックを要求します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-244">Go back to Microsoft and follow the steps below to request a verification check.</span></span> <span data-ttu-id="0f4b3-245">このチェックでは、前の手順で追加した TXT レコードが確認されます。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-245">The check looks for the TXT record you added in the previous step.</span></span> <span data-ttu-id="0f4b3-246">正しい TXT レコードが見つけたら、ドメインが検証されます。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-246">When it finds the correct TXT record, the domain is verified.</span></span>  
1. <span data-ttu-id="0f4b3-247">管理センターで、[セットアップ ドメイン] **ページ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">に移動</a> します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-247">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
2. <span data-ttu-id="0f4b3-248">[ドメイン **] ページで**、確認するドメインの [アクション] 列で、[セットアップの開始]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-248">On the **Domains** page, in the **Action** column for the domain you are verifying, select **Start setup**.</span></span> 
3. <span data-ttu-id="0f4b3-249">[ドメイン **の所有を確認** する] ページで、[完了] を選択し、[今すぐ確認] を選択し、[確認] ダイアログ ボックスで [完了] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-249">On the **Confirm that you own your domain** page, select **done, verify now**, and then in the confirmation dialog box, select **Finish**.</span></span> 
   
> [!NOTE]
>  <span data-ttu-id="0f4b3-p117">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a><span data-ttu-id="0f4b3-253">on-prem Active Directory で UPN として使用される、ルートできない電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="0f4b3-253">Non-routable email address used as a UPN in your on-prem Active Directory</span></span>
<span data-ttu-id="0f4b3-254"><a name="BKMK_ADNote"> </a></span><span class="sxs-lookup"><span data-stu-id="0f4b3-254"><a name="BKMK_ADNote"> </a></span></span>

<span data-ttu-id="0f4b3-255">オンプレミスの Active Directory と Microsoft の同期を計画している場合は、Active Directory ユーザー プリンシパル名 (UPN) サフィックスが有効なドメイン サフィックスであり、@contoso.local などのサポートされていないドメイン サフィックスで構成されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-255">If you're planning to synchronize your on-premises Active Directory with Microsoft, you'll want to make sure that the Active Directory user principal name (UPN) suffix is a valid domain suffix, and not an unsupported domain suffix such as @contoso.local.</span></span> <span data-ttu-id="0f4b3-256">UPN サフィックスを変更する必要がある場合は、「ディレクトリ同期用にルートできないドメインを準備する方法」 [を参照してください](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-256">If you need to change your UPN suffix, see [How to prepare a non-routable domain for directory synchronization](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="0f4b3-p119">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f4b3-p119">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
