---
title: 内部管理者の引き取りを実行する
f1.keywords:
- CSH
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: 電子メールとドメインの所有権を確認して、セルフサービス ユーザーサインアップによって作成された管理されていないテナントを引き継ぐ方法についてMicrosoft 365。
ms.openlocfilehash: f6378c708e0533c2da2d38bfe5eb8009515423c7
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393849"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="d9968-103">内部管理者の引き取りを実行する</span><span class="sxs-lookup"><span data-stu-id="d9968-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="d9968-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9968-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="d9968-105">管理者であり、セルフサービス ユーザーサインアップによって作成された管理されていないテナントを引き継ぐ場合は、内部管理者の引き継ぎでこれを行います。</span><span class="sxs-lookup"><span data-stu-id="d9968-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="d9968-106">Azure AD を使用するクラウド サービスにセルフサービスでサインアップすると、ユーザーは管理されていないまたは "シャドウ" な Azure AD ディレクトリに追加され、管理されていないテナントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d9968-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="d9968-107">管理されていないテナントは、グローバル管理者のないディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="d9968-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="d9968-108">テナントが管理されているかどうかを確認するには、「テナントの種類の決定」 [を参照してください](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。</span><span class="sxs-lookup"><span data-stu-id="d9968-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="d9968-109">手順 1: メール アドレスを確認する</span><span class="sxs-lookup"><span data-stu-id="d9968-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="d9968-110">テナントでセルフサービスが有効になっている場合、ユーザーは無料のサービス (Power BIなど) を自分でサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="d9968-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="d9968-111">これらの手順では、セルフサービス ユーザー サブスクリプションによって管理者として引き継ぐ管理されていないテナントが作成されたと仮定します。最初の手順では、管理されていないテナントにユーザー コンテキストを作成し、Power BIを使用して管理用の引き継ぎパスを説明します。</span><span class="sxs-lookup"><span data-stu-id="d9968-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="d9968-112">アカウントにサインアップするには、Power BI サイトに移動し、[[](https://powerbi.com)無料Power BI無料試用版の開始]を選択します ([ユーザーと共有する]  >  ボックスPower BI Proします。</span><span class="sxs-lookup"><span data-stu-id="d9968-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="d9968-113">組織のドメイン名 (など) を使用するユーザー アカウントにサインアップします `powerbiadmin@contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="d9968-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="d9968-114">アカウントが既に使用されている場合は、現在のパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="d9968-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="d9968-115">確認コードをメールで確認 **し、** メール アドレスを検証するコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="d9968-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="d9968-116">手順 2: 新しいアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="d9968-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="d9968-117">確認コードを入力すると、新しいアカウントを作成できるページに移動します。</span><span class="sxs-lookup"><span data-stu-id="d9968-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="d9968-118">使用するアカウントでユーザー名とパスワードフィールドを入力し、[スタート] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="d9968-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="d9968-119">手順 3: ドメインの所有権を確認し、管理者になる</span><span class="sxs-lookup"><span data-stu-id="d9968-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="d9968-120">[ **管理者になる] ウィザード** が開きます。</span><span class="sxs-lookup"><span data-stu-id="d9968-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="d9968-121">ウィザードが起動しない場合は、管理タイルを **探して** 選択します。</span><span class="sxs-lookup"><span data-stu-id="d9968-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="d9968-122">[ **はい] を選択します。管理者になる必要があります**。</span><span class="sxs-lookup"><span data-stu-id="d9968-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="d9968-123">ドメイン レジストラーに TXT レコードを追加して、引き継ぐドメインを所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9968-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="d9968-124">ウィザードは、追加する TXT レコードを提供し、レジストラーの Web サイトへのリンクと、詳細な手順へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="d9968-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="d9968-125">レジストラー サイトに TXT レコードを追加したら、ウィザードに戻り、[大丈夫] を選択します。レコード **を追加しました**。</span><span class="sxs-lookup"><span data-stu-id="d9968-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d9968-126">シャドウ テナントを引き継ぐと、既存の情報やサービスに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="d9968-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="d9968-127">ただし、ドメイン内のユーザーがライセンスを必要とするサービスにサインアップしている場合は、管理者ロールの引き継ぎの一環として、ライセンスの購入を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9968-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="d9968-128">管理者のセットアップ プロセスが完了したら、ライセンスを購入または削除できます。</span><span class="sxs-lookup"><span data-stu-id="d9968-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="d9968-129">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="d9968-129">Related content</span></span>

<span data-ttu-id="d9968-130">YouTube: IT 管理者の引き取りを行う[3](https://www.youtube.com/watch?v=xt5EsrQBZZk) Power BIとMicrosoft 365 (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="d9968-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk) (video)</span></span>\
<span data-ttu-id="d9968-131">[Azure での管理者の引き](/azure/active-directory/users-groups-roles/domains-admin-takeover) AD (記事)</span><span class="sxs-lookup"><span data-stu-id="d9968-131">[Admin takeover in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (article)</span></span>\
<span data-ttu-id="d9968-132">[組織でセルフサービス サインアップを使用](self-service-sign-up.md) する (記事)</span><span class="sxs-lookup"><span data-stu-id="d9968-132">[Using self-service sign up in your organization](self-service-sign-up.md) (article)</span></span>\
<span data-ttu-id="d9968-133">[サービス管理者Power BIロールについて](/power-bi/service-admin-role)(記事)</span><span class="sxs-lookup"><span data-stu-id="d9968-133">[Understanding the Power BI service administrator role](/power-bi/service-admin-role) (article)</span></span>