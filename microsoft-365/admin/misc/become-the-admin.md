---
title: 内部管理者の引き継ぎを実行する
f1.keywords:
- CSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Microsoft 365 で管理されていないテナントを電子メールとドメインの所有権を引き継ぐために確認する方法について説明します。
ms.openlocfilehash: 4c2dcdb0f6c4f6b795d9579c8796e9668ed2ed05
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399448"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="a167f-103">内部管理者の引き継ぎを実行する</span><span class="sxs-lookup"><span data-stu-id="a167f-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="a167f-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a167f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="a167f-105">管理者が、セルフサービスユーザーサインアップによって作成された管理されていないテナントを引き継ぐ場合は、内部管理者の引き継ぎを使用してこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a167f-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="a167f-106">Azure AD を使用するすべてのクラウドサービスに対してセルフサービスサインアップを行うと、非管理対象または "シャドウ" Azure AD ディレクトリにユーザーが追加され、管理されていないテナントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a167f-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="a167f-107">管理されていないテナントは、全体管理者のいないディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="a167f-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="a167f-108">テナントが管理されているかどうかを判断するには、「[テナントの種類を決定](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a167f-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="a167f-109">手順 1: メールアドレスを確認する</span><span class="sxs-lookup"><span data-stu-id="a167f-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="a167f-110">テナントでセルフサービスが有効になっている場合、ユーザーは Power BI などの無料のサービスを独自にサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="a167f-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="a167f-111">次の手順では、セルフサービスのユーザーサブスクリプションが管理者として引き継がれる非管理対象テナントを作成したと仮定します。最初の手順では、管理されていないテナントでユーザーコンテキストを作成し、Power BI を使用して管理者の引き継ぎパスを示します。</span><span class="sxs-lookup"><span data-stu-id="a167f-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="a167f-112">Power bi にサインアップするには、 [power bi サイト](https://powerbi.com)に移動して、[**無料**  >  **試用版**の開始] ([power bi Pro と共有] ボックス) を選択します。</span><span class="sxs-lookup"><span data-stu-id="a167f-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="a167f-113">組織のドメイン名 (など) を使用するユーザーアカウントでサインアップ `powerbiadmin@contoso.com` します。</span><span class="sxs-lookup"><span data-stu-id="a167f-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="a167f-114">アカウントが既に使用されている場合は、現在のパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="a167f-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="a167f-115">**確認コード**の電子メールを確認し、電子メールアドレスを検証するコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a167f-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="a167f-116">手順 2: 新しいアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="a167f-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="a167f-117">確認コードを入力すると、新しいアカウントを作成できるページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a167f-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="a167f-118">ユーザー名とパスワードのフィールドに、使用するアカウントを入力し、[**開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a167f-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="a167f-119">手順 3: ドメインの所有権を確認し、管理者になる</span><span class="sxs-lookup"><span data-stu-id="a167f-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="a167f-120">[**管理者になる**] ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="a167f-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="a167f-121">ウィザードが開始されない場合は、[**管理者**] タイルを探して選択します。</span><span class="sxs-lookup"><span data-stu-id="a167f-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="a167f-122">[**はい、管理者にする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a167f-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="a167f-123">TXT レコードをドメインレジストラーに追加することによって、引き継ぎたいドメインを所有していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a167f-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="a167f-124">ウィザードによって、追加する TXT レコードが提供されます。また、レジストラーの web サイトへのリンクと、ステップごとの手順へのリンクも提供します。</span><span class="sxs-lookup"><span data-stu-id="a167f-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="a167f-125">レジストラーサイトに TXT レコードを追加したら、ウィザードに戻り、[Ok] を選択して、**レコードを追加**しました。</span><span class="sxs-lookup"><span data-stu-id="a167f-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a167f-126">シャドウテナントを引き継ぐことは、既存の情報やサービスに影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="a167f-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="a167f-127">ただし、ドメイン内のユーザーがライセンスを必要とするサービスにサインアップしている場合は、管理者の役割を引き継ぐ際にライセンスを購入するように求められます。</span><span class="sxs-lookup"><span data-stu-id="a167f-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="a167f-128">管理者セットアッププロセスが完了すると、ライセンスを追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a167f-128">You can add or remove licenses once the admin setup process is finished.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="a167f-129">関連記事</span><span class="sxs-lookup"><span data-stu-id="a167f-129">Related articles</span></span>

<span data-ttu-id="a167f-130">YouTube: [POWER BI および Microsoft 365 に関して IT 管理者を引き継ぐための3つの手順](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="a167f-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="a167f-131">Azure AD での管理の引き継ぎ</span><span class="sxs-lookup"><span data-stu-id="a167f-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="a167f-132">ドメインに関するヘルプを取得する</span><span class="sxs-lookup"><span data-stu-id="a167f-132">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)

[<span data-ttu-id="a167f-133">組織でのセルフサービスサインアップの使用</span><span class="sxs-lookup"><span data-stu-id="a167f-133">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="a167f-134">Power BI サービス管理者の役割について</span><span class="sxs-lookup"><span data-stu-id="a167f-134">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

