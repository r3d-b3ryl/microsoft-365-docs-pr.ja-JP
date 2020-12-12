---
title: 内部管理者の引き受け取りを実行する
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Microsoft 365 で管理されていないテナントを引き継ぐメールとドメインの所有権を確認する方法について説明します。
ms.openlocfilehash: 28359908576260218459d13b8c1c1b662b9a2c8f
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658065"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="72b0e-103">内部管理者の引き受け取りを実行する</span><span class="sxs-lookup"><span data-stu-id="72b0e-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="72b0e-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72b0e-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="72b0e-105">管理者であり、セルフサービス ユーザーサインアップによって作成された管理されていないテナントを引き継ぐ場合は、内部管理者の引き継ぎを使用してこれを行います。</span><span class="sxs-lookup"><span data-stu-id="72b0e-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="72b0e-106">Azure AD を使用するクラウド サービスのセルフサービス サインアップでは、ユーザーが管理されていない Azure AD ディレクトリまたは "シャドウ" ディレクトリに追加され、アンマネージ テナントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="72b0e-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="72b0e-107">管理されていないテナントは、グローバル管理者が存在しないディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="72b0e-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="72b0e-108">テナントが管理されているかどうかを判断するには、「テナントの種類の決定」を [参照してください](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。</span><span class="sxs-lookup"><span data-stu-id="72b0e-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="72b0e-109">手順 1: メール アドレスを確認する</span><span class="sxs-lookup"><span data-stu-id="72b0e-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="72b0e-110">テナントでセルフサービスが有効になっている場合、ユーザーは Power BI などの無料サービスを自分で購読できます。</span><span class="sxs-lookup"><span data-stu-id="72b0e-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="72b0e-111">これらの手順では、セルフサービス ユーザー サブスクリプションによって、管理者として引き継ぐ管理されていないテナントが作成されたと想定しています。最初の手順では、管理されていないテナントにユーザー コンテキストを作成し、Power BI を使用して管理者の引き継ぎパスを示します。</span><span class="sxs-lookup"><span data-stu-id="72b0e-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="72b0e-112">Power BI にサインアップするには[、Power BI](https://powerbi.com)サイトに移動し、[無料スタート無料試用版を開始する] を選択します (Power BI Pro と共有  >  するボックス)。</span><span class="sxs-lookup"><span data-stu-id="72b0e-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="72b0e-113">組織のドメイン名 (例: ) を使用するユーザー アカウントでサインアップします `powerbiadmin@contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="72b0e-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="72b0e-114">アカウントが既に使用されている場合は、現在のパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="72b0e-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="72b0e-115">メールで確認コードを **確認し、** メール アドレスを検証するコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="72b0e-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="72b0e-116">手順 2: 新しいアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="72b0e-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="72b0e-117">確認コードを入力すると、新しいアカウントを作成できるページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="72b0e-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="72b0e-118">使用するアカウントをユーザー名とパスワードのフィールドに入力し、[スタート] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="72b0e-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="72b0e-119">手順 3: ドメインの所有権を確認し、管理者になる</span><span class="sxs-lookup"><span data-stu-id="72b0e-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="72b0e-120">[ **管理者になる] ウィザード** が開きます。</span><span class="sxs-lookup"><span data-stu-id="72b0e-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="72b0e-121">ウィザードが開始しない場合は、[管理] タイル **を探して** 選択します。</span><span class="sxs-lookup"><span data-stu-id="72b0e-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="72b0e-122">Select **Yes, I want to be the admin**.</span><span class="sxs-lookup"><span data-stu-id="72b0e-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="72b0e-123">TXT レコードをドメイン レジストラーに追加して、引き継ぐドメインを所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="72b0e-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="72b0e-124">ウィザードによって、追加する TXT レコードが表示されます。また、レジストラーの Web サイトへのリンクと、詳しい手順へのリンクも提供されます。</span><span class="sxs-lookup"><span data-stu-id="72b0e-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="72b0e-125">TXT レコードをレジストラー サイトに追加したら、ウィザードに戻り **、[Okay, I've added the record**.</span><span class="sxs-lookup"><span data-stu-id="72b0e-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="72b0e-126">シャドウ テナントを引き継ぐと、既存の情報やサービスに影響を与える可能性はありません。</span><span class="sxs-lookup"><span data-stu-id="72b0e-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="72b0e-127">ただし、ドメイン内のユーザーがライセンスを必要とするサービスにサインアップしている場合は、管理者ロールの引き継ぎの一環としてライセンスを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72b0e-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="72b0e-128">管理者のセットアップ プロセスが完了したら、ライセンスを購入または削除できます。</span><span class="sxs-lookup"><span data-stu-id="72b0e-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="72b0e-129">関連記事</span><span class="sxs-lookup"><span data-stu-id="72b0e-129">Related articles</span></span>

<span data-ttu-id="72b0e-130">YouTube: Power BI と[Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)の IT 管理者の引き受け取りを行う 3 つの手順</span><span class="sxs-lookup"><span data-stu-id="72b0e-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="72b0e-131">Azure AD での管理者の引きAD</span><span class="sxs-lookup"><span data-stu-id="72b0e-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="72b0e-132">組織でのセルフサービス サインアップの使用</span><span class="sxs-lookup"><span data-stu-id="72b0e-132">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="72b0e-133">Power BI サービス管理者の役割について</span><span class="sxs-lookup"><span data-stu-id="72b0e-133">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

