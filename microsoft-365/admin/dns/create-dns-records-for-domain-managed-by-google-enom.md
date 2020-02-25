---
title: Google がドメインを管理している場合に DNS レコードを作成する (eNom)
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: '[Google Domains] ページを使用して、eNom にアクセスし、DNS を作成する方法について説明します。'
ms.openlocfilehash: 7a1de0887b96678fb95372633b621d96f7855225
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241049"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a><span data-ttu-id="69898-103">Google がドメインを管理している場合に DNS レコードを作成する (eNom)</span><span class="sxs-lookup"><span data-stu-id="69898-103">Create DNS records when your domain is managed by Google (eNom)</span></span>

 <span data-ttu-id="69898-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="69898-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="69898-105">メール アカウントを Office 365 に移行するには、ドメイン レジストラーに DNS レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69898-105">To migrate your mail accounts to Office 365, you need to create a DNS record at your domain registrar.</span></span>
  
<span data-ttu-id="69898-106">**Google Apps for Work** アカウントへのサインアップ時に Google 経由でドメインを購入した場合、DNS レコードは Google が管理し、eNom が登録します。</span><span class="sxs-lookup"><span data-stu-id="69898-106">If you purchased your domain through Google while signing up for your **Google Apps for Work** account, your DNS records are managed by Google but registered with eNom.</span></span> 
  
<span data-ttu-id="69898-107">[Google **Domains** ] ページで、enom にアクセスし、DNS を作成できます。</span><span class="sxs-lookup"><span data-stu-id="69898-107">You can access eNom, and create DNS, through the Google **Domains** page.</span></span> <span data-ttu-id="69898-108">この記事の手順を実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="69898-108">Just follow the steps in this article.</span></span> 
  
## <a name="create-the-dns-record"></a><span data-ttu-id="69898-109">DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="69898-109">Create the DNS record</span></span>

1. <span data-ttu-id="69898-110">[Google 管理コンソール](https://www.google.com/work/apps/business)で、[**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69898-110">At the [Google Admin console](https://www.google.com/work/apps/business), select **Sign In**.</span></span>
    
    ![Google-Apps-Configure-1-1-0](../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. <span data-ttu-id="69898-112">ドメイン名を入力し、[**移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69898-112">Enter your domain name, and then select **Go**.</span></span>
    
    ![Google-Apps-Configure-1-1-1](../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. <span data-ttu-id="69898-114">ページの下部にある [**その他のコントロール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69898-114">At the bottom of the page, select **More controls**.</span></span>
    
    ![Google-Apps-Configure-1-2-0](../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. <span data-ttu-id="69898-116">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69898-116">Select **Domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-1](../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. <span data-ttu-id="69898-118">[**ドメイン**] ページで、[**ドメインの追加と削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69898-118">On the **Domains** page, select **Add/remove domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-2](../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. <span data-ttu-id="69898-120">[**ドメイン**] ページで、[ **Advanced DNS settings**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69898-120">On the **Domains** page, select **Advanced DNS settings**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="69898-121">**Google Apps for Work** アカウントへのサインアップ時に Google 経由でドメイン名を購入しなかった場合は、[ **Domains**] ページで [ **Advanced DNS settings**] を使用できません。</span><span class="sxs-lookup"><span data-stu-id="69898-121">If you didn't purchase a domain name through Google while signing up for your **Google Apps for Work** account, you won't have **Advanced DNS settings** on your **Domains** page.</span></span> <span data-ttu-id="69898-122">代わりに、ユーザーがドメインのホストの Web サイトに直接移動し、DNS 設定にアクセスして、この手順と次の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="69898-122">Instead, you must go directly to your domain host's web site to access your DNS settings and to perform this and the following steps.</span></span> <span data-ttu-id="69898-123">詳細については[、「G Suite ドメイン設定にアクセス](https://support.google.com/a/answer/54693?hl=en)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69898-123">See [Access your G Suite domain settings](https://support.google.com/a/answer/54693?hl=en) for more information.</span></span> 
  
    ![Google-アプリ-eNom-Configure-1-3](../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. <span data-ttu-id="69898-125">[ **ADVANCED dns settings** ] ページで、[ **Dns コンソールにサインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69898-125">On the **Advanced DNS settings** page, select **Sign in to DNS Console**.</span></span> <span data-ttu-id="69898-126">[ **Sign-in name**] と [ **Password**] の情報をメモします。</span><span class="sxs-lookup"><span data-stu-id="69898-126">Note the **Sign-in name** and **Password** information.</span></span> <span data-ttu-id="69898-127">次の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="69898-127">You'll need it in the next step.</span></span> 
    
    ![Google-アプリ-eNom-Configure-1-4](../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. <span data-ttu-id="69898-129">[ **Advanced DNS settings**] ページから [ **Sign-in name**] と [ **Password**] を使用して Google **Domain Manager** にログインします。</span><span class="sxs-lookup"><span data-stu-id="69898-129">Log in to the Google **Domain Manager** using the **Sign-in name** and **Password** from the **Advanced DNS settings** page.</span></span> 
    
    ![Google-アプリ-eNom-Configure-1-5](../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. <span data-ttu-id="69898-131">[ ***Domain_name*** ] ページの [**ホストレコード**] セクションで、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69898-131">On the ***domain_name*** page, in the **Host Records** section, select **Edit**.</span></span>
    
    ![Google-アプリ-eNom-Configure-1-6](../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. <span data-ttu-id="69898-133">[ **Host Records** ] セクションで、[ **Add New**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69898-133">In the **Host Records** section, select **Add New**.</span></span>
    
    ![Google-アプリ-eNom-Configure-1-7](../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. <span data-ttu-id="69898-135">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="69898-135">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="69898-136">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="69898-136">**HOST**</span></span>|<span data-ttu-id="69898-137">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="69898-137">**TXT VALUE**</span></span>|<span data-ttu-id="69898-138">**レコードの種類**</span><span class="sxs-lookup"><span data-stu-id="69898-138">**RECORD TYPE**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> ||<span data-ttu-id="69898-139">TXT</span><span class="sxs-lookup"><span data-stu-id="69898-139">TXT</span></span>  <br/> |

    > [!NOTE]
    > <span data-ttu-id="69898-140">This is an example.</span><span class="sxs-lookup"><span data-stu-id="69898-140">This is an example.</span></span> <span data-ttu-id="69898-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span><span class="sxs-lookup"><span data-stu-id="69898-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> 
  
    [<span data-ttu-id="69898-142">確認する方法</span><span class="sxs-lookup"><span data-stu-id="69898-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
  
12. <span data-ttu-id="69898-143">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69898-143">Select **Save**.</span></span>
    
    ![Google-アプリ-eNom-Configure-1-9](../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. <span data-ttu-id="69898-145">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="69898-145">Select **Save Changes**.</span></span>
    
    ![Google-Apps-Configure-1-11](../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  <span data-ttu-id="69898-p105">通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69898-p105">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
