---
title: easyDNS で Microsoft 用の DNS レコードを作成する
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: ドメインを確認し、電子メール、Skype for Business Online、その他のサービスの DNS レコードを easyDNS for Microsoft でセットアップする方法について説明します。
ms.openlocfilehash: a971a722f071ef5df9ce0fba387cfacfeb409f5b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656821"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="6a564-103">easyDNS で Microsoft 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="6a564-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="6a564-104">探している内容が見つからない場合は、[ドメインに関する FAQ](../setup/domains-faq.yml) を確認してください。</span><span class="sxs-lookup"><span data-stu-id="6a564-104">[Check the Domains FAQ ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6a564-105">次のすべての DNS レコードをレジストラーの Web サイトに追加して、メールを Microsoft にルーティングし、Teams と Skype for Business のドメインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a564-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="6a564-106">注: 現在、SRV レコードは、すべての easyDNS サービス パッケージで利用できるではありません。</span><span class="sxs-lookup"><span data-stu-id="6a564-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="6a564-107">Skype for Business に必要な SRV レコードを追加するには、easyDNS を使用してより高いサービス レベルにアップグレードする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="6a564-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="6a564-108">TXT レコードを持つドメインを所有している</span><span class="sxs-lookup"><span data-stu-id="6a564-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="6a564-109">資格情報 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) を使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="6a564-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="6a564-110">[すべてのドメイン **] 見出しの下** で **、[dns]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a564-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="6a564-111">**[TXT レコード] 見出しの** 下で、[編集] ボタン (ボタンのアイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a564-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="6a564-112">テキスト フィールドに次のレコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="6a564-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="6a564-113">**Host**</span><span class="sxs-lookup"><span data-stu-id="6a564-113">**Host**</span></span>|<span data-ttu-id="6a564-114">**テキスト**</span><span class="sxs-lookup"><span data-stu-id="6a564-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="6a564-115">MS=msXXXXXXXX (管理センターの [ドメイン] ページで提供された値を使用します)</span><span class="sxs-lookup"><span data-stu-id="6a564-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="6a564-116">[次へ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6a564-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="6a564-117">レコードが正しいか確認し、[確認] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="6a564-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="6a564-118">数分待って続行すると、作成したレコードがインターネットに伝達され、Microsoft によって検出されます。</span><span class="sxs-lookup"><span data-stu-id="6a564-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="6a564-119">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="6a564-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="6a564-120">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6a564-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="6a564-121">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="6a564-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="6a564-122">[セットアップ **] ページで** 、[セットアップの開始] **を選択します。**</span><span class="sxs-lookup"><span data-stu-id="6a564-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="6a564-123">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a564-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="6a564-124">MX レコードを追加して Microsoft にメールをルーティングする</span><span class="sxs-lookup"><span data-stu-id="6a564-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="6a564-125">資格情報 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) を使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="6a564-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="6a564-126">[すべてのドメイン **] 見出しの** 下で **、[dns]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a564-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="6a564-127">[MX **レコード] 見出しの** 下で、[編集] ボタン (歯車アイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a564-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="6a564-128">テキスト フィールドに次のレコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="6a564-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="6a564-129">**領域のメール**</span><span class="sxs-lookup"><span data-stu-id="6a564-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="6a564-130">**メール サーバー**</span><span class="sxs-lookup"><span data-stu-id="6a564-130">**MAIL SERVER**</span></span>|<span data-ttu-id="6a564-131">**PREF**</span><span class="sxs-lookup"><span data-stu-id="6a564-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="6a564-132">\<domain-key\>.mail.protection.outlook.com (管理センター \<domain-key\> の [ドメイン] ページから値を取得する)</span><span class="sxs-lookup"><span data-stu-id="6a564-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="6a564-133">0</span><span class="sxs-lookup"><span data-stu-id="6a564-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="6a564-134">バックアップ目的で他の MX レコードを保存する場合は、どこかにコピーします。</span><span class="sxs-lookup"><span data-stu-id="6a564-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="6a564-135">次に進む前に、ここに他のすべての MX レコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="6a564-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="6a564-136">[次へ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6a564-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="6a564-137">レコードが正しいか確認し、[確認] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="6a564-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="6a564-138">必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="6a564-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="6a564-139">資格情報 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) を使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="6a564-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="6a564-140">[すべてのドメイン **] 見出しの下** で **、[dns]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a564-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="6a564-141">**[CNAME/エイリアス レコード] 見出しの** 下で、[編集] ボタン (ボタンのアイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a564-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="6a564-142">テキスト フィールドに次のレコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="6a564-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="6a564-143">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="6a564-143">**HOST**</span></span>|<span data-ttu-id="6a564-144">**住所 (末尾に ".")**</span><span class="sxs-lookup"><span data-stu-id="6a564-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="6a564-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="6a564-145">autodiscover</span></span>  <br/> |<span data-ttu-id="6a564-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="6a564-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="6a564-147">sip</span><span class="sxs-lookup"><span data-stu-id="6a564-147">sip</span></span>  <br/> |<span data-ttu-id="6a564-148">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6a564-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="6a564-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6a564-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6a564-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6a564-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="6a564-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6a564-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6a564-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="6a564-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="6a564-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6a564-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6a564-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="6a564-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="6a564-155">[次へ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6a564-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="6a564-156">レコードが正しいか確認し、[確認] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="6a564-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6a564-157">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="6a564-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="6a564-158">資格情報 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) を使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="6a564-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="6a564-159">[すべてのドメイン **] 見出しの下** で **、[dns]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a564-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="6a564-160">**[TXT レコード] 見出しの** 下で、[編集] ボタン (ボタンのアイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a564-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="6a564-161">テキスト フィールドに次のレコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="6a564-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="6a564-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="6a564-162">**Host**</span></span>|<span data-ttu-id="6a564-163">**テキスト**</span><span class="sxs-lookup"><span data-stu-id="6a564-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="6a564-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6a564-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="6a564-165">[次へ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6a564-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="6a564-166">レコードが正しいか確認し、[確認] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="6a564-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="6a564-167">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="6a564-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="6a564-168">注: 現在、SRV レコードは easyDNS の Domain Plus サービス レベルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="6a564-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="6a564-169">SRV レコードを追加するには、easyDNS を使用してより高いサービス レベルにアップグレードする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="6a564-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="6a564-170">資格情報 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) を使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="6a564-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="6a564-171">[すべてのドメイン **] 見出しの下** で **、[dns]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a564-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="6a564-172">**[SRV レコード] 見出しの** 下で、[編集] ボタン (ボタンボタン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a564-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="6a564-173">テキスト フィールドに次のレコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="6a564-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="6a564-174">**サービス**</span><span class="sxs-lookup"><span data-stu-id="6a564-174">**SERVICE**</span></span>|<span data-ttu-id="6a564-175">**PROTO**</span><span class="sxs-lookup"><span data-stu-id="6a564-175">**PROTO**</span></span>|<span data-ttu-id="6a564-176">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="6a564-176">**HOST**</span></span>|<span data-ttu-id="6a564-177">**PRI**</span><span class="sxs-lookup"><span data-stu-id="6a564-177">**PRI**</span></span>|<span data-ttu-id="6a564-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="6a564-178">**WGT**</span></span>|<span data-ttu-id="6a564-179">**ポート**</span><span class="sxs-lookup"><span data-stu-id="6a564-179">**PORT**</span></span>|<span data-ttu-id="6a564-180">**TARGET(末尾に ".")**</span><span class="sxs-lookup"><span data-stu-id="6a564-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="6a564-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6a564-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6a564-182">_sip</span><span class="sxs-lookup"><span data-stu-id="6a564-182">_sip</span></span>  <br/> |<span data-ttu-id="6a564-183">TLS</span><span class="sxs-lookup"><span data-stu-id="6a564-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="6a564-184">100</span><span class="sxs-lookup"><span data-stu-id="6a564-184">100</span></span>  <br/> |<span data-ttu-id="6a564-185">1 </span><span class="sxs-lookup"><span data-stu-id="6a564-185">1</span></span>  <br/> |<span data-ttu-id="6a564-186">443</span><span class="sxs-lookup"><span data-stu-id="6a564-186">443</span></span>  <br/> |<span data-ttu-id="6a564-187">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6a564-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="6a564-188">1800</span><span class="sxs-lookup"><span data-stu-id="6a564-188">1800</span></span>  <br/> |
    |<span data-ttu-id="6a564-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="6a564-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="6a564-190">TCP</span><span class="sxs-lookup"><span data-stu-id="6a564-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="6a564-191">100</span><span class="sxs-lookup"><span data-stu-id="6a564-191">100</span></span>  <br/> |<span data-ttu-id="6a564-192">1 </span><span class="sxs-lookup"><span data-stu-id="6a564-192">1</span></span>  <br/> |<span data-ttu-id="6a564-193">5061</span><span class="sxs-lookup"><span data-stu-id="6a564-193">5061</span></span>  <br/> |<span data-ttu-id="6a564-194">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="6a564-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="6a564-195">1800</span><span class="sxs-lookup"><span data-stu-id="6a564-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="6a564-196">[次へ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6a564-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="6a564-197">レコードが正しいか確認し、[確認] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="6a564-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

