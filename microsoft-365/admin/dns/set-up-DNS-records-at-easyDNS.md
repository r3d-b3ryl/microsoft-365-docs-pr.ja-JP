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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: ドメインを確認し、電子メール、Skype for Business Online、および easyDNS のその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.openlocfilehash: 24f477d240af936975141c53d382e114a24c0ac5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400234"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="14634-103">Microsoft の easyDNS で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="14634-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="14634-104">探している内容が見つからない場合は、[ドメインに関する FAQ](../setup/domains-faq.md) を確認してください。</span><span class="sxs-lookup"><span data-stu-id="14634-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="14634-105">メールを Microsoft にルーティングするには、レジストラーの web サイトで以下の DNS レコードをすべて追加し、Teams や Skype for Business のドメインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14634-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="14634-106">注: SRV レコードは、現在、すべての easyDNS サービスパッケージでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="14634-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="14634-107">Skype for Business に必要な SRV レコードを追加するには、easyDNS を使用して、より高いサービスレベルにアップグレードする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="14634-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="14634-108">TXT レコードを使用してドメインを所有していることを確認する</span><span class="sxs-lookup"><span data-stu-id="14634-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="14634-109">に移動 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) して、資格情報でログインします。</span><span class="sxs-lookup"><span data-stu-id="14634-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="14634-110">[**すべてのドメイン**] 見出しの下で、[dns] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="14634-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="14634-111">[ **TXT records** ] の見出しの下で、編集ボタン (レンチアイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="14634-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="14634-112">次のレコードをテキストフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="14634-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="14634-113">**Host**</span><span class="sxs-lookup"><span data-stu-id="14634-113">**Host**</span></span>|<span data-ttu-id="14634-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="14634-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="14634-115">MS: msXXXXXXXX (管理センターの [ドメイン] ページでユーザーに提供された値を使用します)</span><span class="sxs-lookup"><span data-stu-id="14634-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="14634-116">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14634-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="14634-117">レコードが正しいことを確認してから、[**確認**] を選択してください。</span><span class="sxs-lookup"><span data-stu-id="14634-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="14634-118">数分待ってから続行すると、作成したレコードがインターネット経由で伝達され、Microsoft によって検出されるようになります。</span><span class="sxs-lookup"><span data-stu-id="14634-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="14634-119">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="14634-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="14634-120">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="14634-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="14634-121">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="14634-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="14634-122">[**セットアップ**] ページで、[セットアップの開始] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="14634-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="14634-123">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="14634-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="14634-124">Microsoft に電子メールをルーティングするための MX レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="14634-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="14634-125">に移動 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) して、資格情報でログインします。</span><span class="sxs-lookup"><span data-stu-id="14634-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="14634-126">[**すべてのドメイン**] 見出しの下で、[dns] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="14634-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="14634-127">[ **MX records** ] の見出しの下で、編集ボタン (レンチアイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="14634-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="14634-128">次のレコードをテキストフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="14634-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="14634-129">**ゾーン用のメール**</span><span class="sxs-lookup"><span data-stu-id="14634-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="14634-130">**メールサーバー**</span><span class="sxs-lookup"><span data-stu-id="14634-130">**MAIL SERVER**</span></span>|<span data-ttu-id="14634-131">**PREF**</span><span class="sxs-lookup"><span data-stu-id="14634-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="14634-132">\<domain-key\>. mail.protection.outlook.com ( \<domain-key\> [管理センタードメイン] ページから値を取得する)</span><span class="sxs-lookup"><span data-stu-id="14634-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="14634-133">.0</span><span class="sxs-lookup"><span data-stu-id="14634-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="14634-134">バックアップのために他の MX レコードを保存する場合は、その MX レコードを任意の場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="14634-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="14634-135">に進む前に、ここで他のすべての MX レコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="14634-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="14634-136">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14634-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="14634-137">レコードが正しいことを確認してから、[**確認**] を選択してください。</span><span class="sxs-lookup"><span data-stu-id="14634-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="14634-138">必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="14634-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="14634-139">に移動 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) して、資格情報でログインします。</span><span class="sxs-lookup"><span data-stu-id="14634-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="14634-140">[**すべてのドメイン**] 見出しの下で、[dns] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="14634-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="14634-141">[ **CNAME/Alias records** ] の見出しで、編集ボタン (レンチアイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="14634-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="14634-142">次のレコードをテキストフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="14634-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="14634-143">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="14634-143">**HOST**</span></span>|<span data-ttu-id="14634-144">**Address (末尾に "." を指定する必要があります)**</span><span class="sxs-lookup"><span data-stu-id="14634-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="14634-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="14634-145">autodiscover</span></span>  <br/> |<span data-ttu-id="14634-146">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="14634-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="14634-147">sip</span><span class="sxs-lookup"><span data-stu-id="14634-147">sip</span></span>  <br/> |<span data-ttu-id="14634-148">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="14634-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="14634-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="14634-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="14634-150">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="14634-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="14634-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="14634-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="14634-152">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="14634-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="14634-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="14634-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="14634-154">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="14634-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="14634-155">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14634-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="14634-156">レコードが正しいことを確認してから、[**確認**] を選択してください。</span><span class="sxs-lookup"><span data-stu-id="14634-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="14634-157">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="14634-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="14634-158">に移動 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) して、資格情報でログインします。</span><span class="sxs-lookup"><span data-stu-id="14634-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="14634-159">[**すべてのドメイン**] 見出しの下で、[dns] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="14634-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="14634-160">[ **TXT records** ] の見出しの下で、編集ボタン (レンチアイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="14634-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="14634-161">次のレコードをテキストフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="14634-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="14634-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="14634-162">**Host**</span></span>|<span data-ttu-id="14634-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="14634-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="14634-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="14634-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="14634-165">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14634-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="14634-166">レコードが正しいことを確認してから、[**確認**] を選択してください。</span><span class="sxs-lookup"><span data-stu-id="14634-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="14634-167">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="14634-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="14634-168">注: SRV レコードは現在、easyDNS ' ドメインおよびサービスレベルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="14634-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="14634-169">SRV レコードを追加するには、easyDNS を使用して、より高いサービスレベルにアップグレードする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="14634-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="14634-170">に移動 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) して、資格情報でログインします。</span><span class="sxs-lookup"><span data-stu-id="14634-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="14634-171">[**すべてのドメイン**] 見出しの下で、[dns] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="14634-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="14634-172">[ **SRV records** ] の見出しの下で、[編集] ボタン (レンチアイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="14634-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="14634-173">次のレコードをテキストフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="14634-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="14634-174">**サービス**</span><span class="sxs-lookup"><span data-stu-id="14634-174">**SERVICE**</span></span>|<span data-ttu-id="14634-175">**MASK**</span><span class="sxs-lookup"><span data-stu-id="14634-175">**PROTO**</span></span>|<span data-ttu-id="14634-176">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="14634-176">**HOST**</span></span>|<span data-ttu-id="14634-177">**度**</span><span class="sxs-lookup"><span data-stu-id="14634-177">**PRI**</span></span>|<span data-ttu-id="14634-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="14634-178">**WGT**</span></span>|<span data-ttu-id="14634-179">**ポート**</span><span class="sxs-lookup"><span data-stu-id="14634-179">**PORT**</span></span>|<span data-ttu-id="14634-180">**TARGET (末尾に "." を指定する必要があります)**</span><span class="sxs-lookup"><span data-stu-id="14634-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="14634-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14634-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="14634-182">_sip</span><span class="sxs-lookup"><span data-stu-id="14634-182">_sip</span></span>  <br/> |<span data-ttu-id="14634-183">TLS</span><span class="sxs-lookup"><span data-stu-id="14634-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="14634-184">100</span><span class="sxs-lookup"><span data-stu-id="14634-184">100</span></span>  <br/> |<span data-ttu-id="14634-185">1 </span><span class="sxs-lookup"><span data-stu-id="14634-185">1</span></span>  <br/> |<span data-ttu-id="14634-186">443</span><span class="sxs-lookup"><span data-stu-id="14634-186">443</span></span>  <br/> |<span data-ttu-id="14634-187">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="14634-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="14634-188">1800</span><span class="sxs-lookup"><span data-stu-id="14634-188">1800</span></span>  <br/> |
    |<span data-ttu-id="14634-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="14634-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="14634-190">TCP</span><span class="sxs-lookup"><span data-stu-id="14634-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="14634-191">100</span><span class="sxs-lookup"><span data-stu-id="14634-191">100</span></span>  <br/> |<span data-ttu-id="14634-192">1 </span><span class="sxs-lookup"><span data-stu-id="14634-192">1</span></span>  <br/> |<span data-ttu-id="14634-193">5061</span><span class="sxs-lookup"><span data-stu-id="14634-193">5061</span></span>  <br/> |<span data-ttu-id="14634-194">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="14634-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="14634-195">1800</span><span class="sxs-lookup"><span data-stu-id="14634-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="14634-196">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14634-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="14634-197">レコードが正しいことを確認してから、[**確認**] を選択してください。</span><span class="sxs-lookup"><span data-stu-id="14634-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

