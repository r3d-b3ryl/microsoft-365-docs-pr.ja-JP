---
title: Microsoft の easyDNS で DNS レコードを作成する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: ドメインを確認し、電子メール、Skype for Business Online、および easyDNS のその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.openlocfilehash: b7b29900108ab94f0fd99dcf3404cfa137ce92ff
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631359"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="3a056-103">Microsoft の easyDNS で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="3a056-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="3a056-104">探している内容が見つからない場合は、[ドメインに関する FAQ](../setup/domains-faq.md) を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3a056-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3a056-105">メールを Microsoft にルーティングするには、レジストラーの web サイトで以下の DNS レコードをすべて追加し、Teams や Skype for Business のドメインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a056-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="3a056-106">注: SRV レコードは、現在、すべての easyDNS サービスパッケージでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="3a056-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="3a056-107">Skype for Business に必要な SRV レコードを追加するには、easyDNS を使用して、より高いサービスレベルにアップグレードする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3a056-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="3a056-108">TXT レコードを使用してドメインを所有していることを確認する</span><span class="sxs-lookup"><span data-stu-id="3a056-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="3a056-109">に[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)移動して、資格情報でログインします。</span><span class="sxs-lookup"><span data-stu-id="3a056-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="3a056-110">[**すべてのドメイン**] 見出しの下で、[dns] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="3a056-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="3a056-111">[ **TXT records** ] の見出しの下で、編集ボタン (レンチアイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a056-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="3a056-112">次のレコードをテキストフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="3a056-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="3a056-113">**Host**</span><span class="sxs-lookup"><span data-stu-id="3a056-113">**Host**</span></span>|<span data-ttu-id="3a056-114">**テキスト**</span><span class="sxs-lookup"><span data-stu-id="3a056-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="3a056-115">MS: msXXXXXXXX (管理センターの [ドメイン] ページでユーザーに提供された値を使用します)</span><span class="sxs-lookup"><span data-stu-id="3a056-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="3a056-116">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a056-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="3a056-117">レコードが正しいことを確認してから、[**確認**] を選択してください。</span><span class="sxs-lookup"><span data-stu-id="3a056-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="3a056-118">数分待ってから続行すると、作成したレコードがインターネット経由で伝達され、Microsoft によって検出されるようになります。</span><span class="sxs-lookup"><span data-stu-id="3a056-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="3a056-119">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。</span><span class="sxs-lookup"><span data-stu-id="3a056-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="3a056-120">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="3a056-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="3a056-121">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="3a056-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="3a056-122">[**セットアップ**] ページで、[セットアップの開始] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="3a056-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="3a056-123">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a056-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="3a056-124">Microsoft に電子メールをルーティングするための MX レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3a056-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="3a056-125">に[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)移動して、資格情報でログインします。</span><span class="sxs-lookup"><span data-stu-id="3a056-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="3a056-126">[**すべてのドメイン**] 見出しの下で、[dns] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="3a056-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="3a056-127">[ **MX records** ] の見出しの下で、編集ボタン (レンチアイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a056-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="3a056-128">次のレコードをテキストフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="3a056-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="3a056-129">**ゾーン用のメール**</span><span class="sxs-lookup"><span data-stu-id="3a056-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="3a056-130">**メールサーバー**</span><span class="sxs-lookup"><span data-stu-id="3a056-130">**MAIL SERVER**</span></span>|<span data-ttu-id="3a056-131">**PREF**</span><span class="sxs-lookup"><span data-stu-id="3a056-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3a056-132">\<\>mail.protection.outlook.com ([管理センタードメイン] ページ\<からドメインキー\>の値を取得する)</span><span class="sxs-lookup"><span data-stu-id="3a056-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="3a056-133">.0</span><span class="sxs-lookup"><span data-stu-id="3a056-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="3a056-134">バックアップのために他の MX レコードを保存する場合は、その MX レコードを任意の場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="3a056-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="3a056-135">に進む前に、ここで他のすべての MX レコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="3a056-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="3a056-136">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a056-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="3a056-137">レコードが正しいことを確認してから、[**確認**] を選択してください。</span><span class="sxs-lookup"><span data-stu-id="3a056-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="3a056-138">必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3a056-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="3a056-139">に[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)移動して、資格情報でログインします。</span><span class="sxs-lookup"><span data-stu-id="3a056-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="3a056-140">[**すべてのドメイン**] 見出しの下で、[dns] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="3a056-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="3a056-141">[ **CNAME/Alias records** ] の見出しで、編集ボタン (レンチアイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a056-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="3a056-142">次のレコードをテキストフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="3a056-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="3a056-143">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="3a056-143">**HOST**</span></span>|<span data-ttu-id="3a056-144">**Address (末尾に "." を指定する必要があります)**</span><span class="sxs-lookup"><span data-stu-id="3a056-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="3a056-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3a056-145">autodiscover</span></span>  <br/> |<span data-ttu-id="3a056-146">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="3a056-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="3a056-147">sip</span><span class="sxs-lookup"><span data-stu-id="3a056-147">sip</span></span>  <br/> |<span data-ttu-id="3a056-148">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="3a056-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="3a056-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3a056-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3a056-150">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="3a056-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="3a056-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3a056-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3a056-152">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="3a056-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="3a056-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3a056-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3a056-154">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="3a056-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="3a056-155">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a056-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="3a056-156">レコードが正しいことを確認してから、[**確認**] を選択してください。</span><span class="sxs-lookup"><span data-stu-id="3a056-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3a056-157">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3a056-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="3a056-158">に[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)移動して、資格情報でログインします。</span><span class="sxs-lookup"><span data-stu-id="3a056-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="3a056-159">[**すべてのドメイン**] 見出しの下で、[dns] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="3a056-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="3a056-160">[ **TXT records** ] の見出しの下で、編集ボタン (レンチアイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a056-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="3a056-161">次のレコードをテキストフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="3a056-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="3a056-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="3a056-162">**Host**</span></span>|<span data-ttu-id="3a056-163">**テキスト**</span><span class="sxs-lookup"><span data-stu-id="3a056-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="3a056-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3a056-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="3a056-165">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a056-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="3a056-166">レコードが正しいことを確認してから、[**確認**] を選択してください。</span><span class="sxs-lookup"><span data-stu-id="3a056-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3a056-167">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3a056-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="3a056-168">注: SRV レコードは現在、easyDNS ' ドメインおよびサービスレベルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="3a056-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="3a056-169">SRV レコードを追加するには、easyDNS を使用して、より高いサービスレベルにアップグレードする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3a056-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="3a056-170">に[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)移動して、資格情報でログインします。</span><span class="sxs-lookup"><span data-stu-id="3a056-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="3a056-171">[**すべてのドメイン**] 見出しの下で、[dns] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="3a056-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="3a056-172">[ **SRV records** ] の見出しの下で、[編集] ボタン (レンチアイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a056-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="3a056-173">次のレコードをテキストフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="3a056-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="3a056-174">**サービス**</span><span class="sxs-lookup"><span data-stu-id="3a056-174">**SERVICE**</span></span>|<span data-ttu-id="3a056-175">**MASK**</span><span class="sxs-lookup"><span data-stu-id="3a056-175">**PROTO**</span></span>|<span data-ttu-id="3a056-176">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="3a056-176">**HOST**</span></span>|<span data-ttu-id="3a056-177">**度**</span><span class="sxs-lookup"><span data-stu-id="3a056-177">**PRI**</span></span>|<span data-ttu-id="3a056-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="3a056-178">**WGT**</span></span>|<span data-ttu-id="3a056-179">**ポート**</span><span class="sxs-lookup"><span data-stu-id="3a056-179">**PORT**</span></span>|<span data-ttu-id="3a056-180">**TARGET (末尾に "." を指定する必要があります)**</span><span class="sxs-lookup"><span data-stu-id="3a056-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="3a056-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3a056-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3a056-182">_sip</span><span class="sxs-lookup"><span data-stu-id="3a056-182">_sip</span></span>  <br/> |<span data-ttu-id="3a056-183">TLS</span><span class="sxs-lookup"><span data-stu-id="3a056-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="3a056-184">100</span><span class="sxs-lookup"><span data-stu-id="3a056-184">100</span></span>  <br/> |<span data-ttu-id="3a056-185">1-d</span><span class="sxs-lookup"><span data-stu-id="3a056-185">1</span></span>  <br/> |<span data-ttu-id="3a056-186">443</span><span class="sxs-lookup"><span data-stu-id="3a056-186">443</span></span>  <br/> |<span data-ttu-id="3a056-187">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="3a056-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="3a056-188">1800</span><span class="sxs-lookup"><span data-stu-id="3a056-188">1800</span></span>  <br/> |
    |<span data-ttu-id="3a056-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="3a056-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="3a056-190">TCP</span><span class="sxs-lookup"><span data-stu-id="3a056-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="3a056-191">100</span><span class="sxs-lookup"><span data-stu-id="3a056-191">100</span></span>  <br/> |<span data-ttu-id="3a056-192">1-d</span><span class="sxs-lookup"><span data-stu-id="3a056-192">1</span></span>  <br/> |<span data-ttu-id="3a056-193">5061</span><span class="sxs-lookup"><span data-stu-id="3a056-193">5061</span></span>  <br/> |<span data-ttu-id="3a056-194">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="3a056-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="3a056-195">1800</span><span class="sxs-lookup"><span data-stu-id="3a056-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="3a056-196">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a056-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="3a056-197">レコードが正しいことを確認してから、[**確認**] を選択してください。</span><span class="sxs-lookup"><span data-stu-id="3a056-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

