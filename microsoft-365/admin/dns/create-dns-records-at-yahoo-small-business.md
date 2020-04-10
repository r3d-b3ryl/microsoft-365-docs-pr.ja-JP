---
title: Yahoo! Small Business で Office 365 用の DNS レコードを作成する
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
- BCS160
- MET150
- MOE150
ms.assetid: 034bd7bc-b098-4c4d-8a93-4d74ff24532a
description: Yahoo! で、ドメインを確認し、電子メール、Skype for Business Online、およびその他のサービスの DNS レコードを設定する方法について説明します。 Office 365 用 Small Business。
ms.openlocfilehash: 7b0d0b25a2895101e2f9a259a82fb18e9447441f
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211040"
---
# <a name="create-dns-records-at-yahoo-small-business-for-office-365"></a><span data-ttu-id="9f7a1-105">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="9f7a1-105">Create DNS records at Yahoo!</span></span> <span data-ttu-id="9f7a1-106">Small Business で Office 365 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="9f7a1-106">Small Business for Office 365</span></span>

 <span data-ttu-id="9f7a1-107">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-107">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9f7a1-p104">Yahoo!DNS ホスティング プロバイダーが Small Business であった場合、現在はそのプロバイダーが Aabaco Small Business に変更されていることに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-p104">If Yahoo! Small Business has been your DNS hosting provider, you should be aware that your provider is now Aabaco Small Business.</span></span>
  
<span data-ttu-id="9f7a1-110">Aabaco にアカウントを作成するには、この記事の手順を実行します。DNS を変更し、1 つ以上のドメインを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-110">Follow the steps in this article to create an account at Aabaco, where you can make DNS changes and renew your domain or domains.</span></span>
  
<span data-ttu-id="9f7a1-111">[DNS レコードを作成](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)する前に、Aabaco アカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-111">You must create your Aabaco account before you can [create DNS records](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

  
## <a name="create-an-aabaco-small-business-account"></a><span data-ttu-id="9f7a1-112">Aabaco Small Business アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="9f7a1-112">Create an Aabaco Small Business account</span></span>

1. <span data-ttu-id="9f7a1-113">まず、[このリンク](https://www.luminate.com/services/)を使用して Aabaco のドメインページに移動し、[ **Aabaco Small Business アカウントをセットアップ**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-113">To get started, go to your domains page at Aabaco by using [this link](https://www.luminate.com/services/), and select **Setup your Aabaco Small Business account**.</span></span>
    
    ![[Aabaco Small Business アカウントをセットアップする] を選択します。](../../media/d708f272-d42f-40a1-9aaf-d05d8cfd55cf.png)
  
2. <span data-ttu-id="9f7a1-115">Yahoo! を提供する</span><span class="sxs-lookup"><span data-stu-id="9f7a1-115">Provide your Yahoo!</span></span> <span data-ttu-id="9f7a1-116">Small Business の**電子メール/YAHOO ID**。 [**ロボット**ではない] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-116">Small Business **Email/Yahoo ID**, and then select **I'm not a robot**.</span></span>
    
    ![Select I am not a robot](../../media/ded4b5dd-4e04-4baa-ae31-8426b5799151.png)
  
3. <span data-ttu-id="9f7a1-118">[**開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-118">Select **Get started**.</span></span>
    
    ![[開始] を選択します。](../../media/6674707d-c222-4f0d-bec4-229d39ab2499.png)
  
4. <span data-ttu-id="9f7a1-p106">Yahoo!Small Business メール アカウントにサインインし、Aabaco Small Business から新しい電子メールを開きます。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-p106">Sign in to your Yahoo! Small Business email account and open the new email from Aabaco Small Business.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9f7a1-122">必要に応じて、[ **You've got mail**] ページの [ **resend the email link**] を選択してメッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-122">Resend the message, if necessary, by choosing the **resend the email link** on the **You've got mail** page.</span></span> 
  
    ![The You've got mail page](../../media/2e02fc30-6cca-40d6-bb64-131a41b4a369.png)
  
5. <span data-ttu-id="9f7a1-124">[Aabaco の**電子メールアドレスを確認してセットアップを続行する**] メールメッセージで、[**電子メールの確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-124">In the Aabaco **Confirm your email address to continue setup** email message, select **Confirm email**.</span></span>
    
    ![[電子メールの確認] を選択する](../../media/eb5f5526-6f90-4a10-83a7-5249a1ebd562.png)
  
6. <span data-ttu-id="9f7a1-126">[ **Choose your password**] ページで、Aabaco アカウントに使用するパスワードを入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-126">On the **Choose your password** page, type or copy and paste the password that you want to use for your Aabaco account.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9f7a1-p107">Yahoo!Small Business アカウントで使用したものと同じパスワードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-p107">You can use the same password that you used with your Yahoo! Small Business account.</span></span> 
  
    ![The Choose your password page](../../media/cc592345-72d1-4a41-9410-a1f3345cfd1d.png)
  
7. <span data-ttu-id="9f7a1-130">[使用条件**に同意**します] を選択し、[**パスワードの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-130">Select **I agree to the terms and conditions**, and then select **Create password**.</span></span>
    
    ![[パスワードの作成] を選択します。](../../media/434aa6a3-076e-4abf-a9cf-31145786e819.png)
  
8. <span data-ttu-id="9f7a1-p108">Yahoo!Small Business メール アカウントにサインインし、Aabaco Small Business から新しい電子メールを開きます。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-p108">Sign in to your Yahoo! Small Business email account, and then open the new email from Aabaco Small Business.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9f7a1-p109">必要に応じて、[ **You're almost done!**] ページの [ **resend the email link**] を選択してメッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-p109">Resend the message, if necessary, by choosing the **resend the email link** on the **You're almost done!** page.</span></span> 
  
    ![The You're almost done page](../../media/1a4142a3-e140-48a8-9c80-aa126ff08179.png)
  
9. <span data-ttu-id="9f7a1-137">Aabaco でほとんどの電子メールメッセージ**が表示**されたら、[**アカウントのアクティブ化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-137">In the Aabaco **You're almost there** email message, select **Activate my account**.</span></span>
    
    ![[アカウントのアクティブ化] を選択する](../../media/e76d5edc-d8ba-4d8d-872d-d916716c3618.png)
  
10. <span data-ttu-id="9f7a1-139">Aabaco Small Business アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-139">Sign in to your Aabaco Small Business account.</span></span>
    
    ![The sign-in page for Aabaco Small Business](../../media/4ef3cfc3-26da-4e03-932b-9346ef217848.png)
  
<span data-ttu-id="9f7a1-141">Aabaco アカウントを作成したので、[Aabaco Small Business に Office 365 用 DNS レコードを作成](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)できます。</span><span class="sxs-lookup"><span data-stu-id="9f7a1-141">Now that you have created your Aabaco account, you can [Create DNS records at Aabaco Small Business for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>
  
