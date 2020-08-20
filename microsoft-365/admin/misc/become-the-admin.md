---
title: 内部管理者のイークバーを実行する
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
description: Microsoft 365 の管理されていないテナントを経由するメールとドメインの所有権を確認する方法について説明します。
ms.openlocfilehash: 9c1d98616b10737553060bcbad62df9b3b4c0c9a
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814470"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="d5b0a-103">内部管理者のイークバーを実行する</span><span class="sxs-lookup"><span data-stu-id="d5b0a-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="d5b0a-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="d5b0a-105">管理者がセルフサービス ユーザー サインアップによって作成された非管理対象テナントを置き継いき、内部管理者のイールでこれを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="d5b0a-106">Azure AD を使用する任意のクラウド サービスにセルフサービス サインアップすると、管理されていないテナントまたは "シャドウ" の Azure AD ディレクトリにユーザーが追加され、管理されていないテナントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="d5b0a-107">非管理対象テナントは、グローバル管理者が存在しないディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="d5b0a-108">テナントが管理対象か非管理対象かを判断するには、「テナントの [種類の決定」を参照してください](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="d5b0a-109">手順 1: メール アドレスを確認する</span><span class="sxs-lookup"><span data-stu-id="d5b0a-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="d5b0a-110">テナントでセルフサービスが有効になっている場合、ユーザーは Power BI などの無料サービスを自分で購読できます。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="d5b0a-111">この手順では、セルフサービス ユーザーのサブスクリプションで管理対象の管理対象のないテナントが作成されていると想定しています。最初の手順では、管理されていないテナントでユーザー コンテキストを作成し、Power BI を使用して管理者の選択取り込みパスを示します。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="d5b0a-112">Power BI にサインアップするには、Power BI サイトに**Start Free**[移動して、[無料](https://powerbi.com)のスタート画面一覧で (Power BI Pro で共有する]  >  **Start free trial**ボックスで) [無料のスタート画面を使い始めにする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="d5b0a-113">組織のドメイン名を使用するユーザー アカウント (例: `powerbiadmin@contoso.com`</span><span class="sxs-lookup"><span data-stu-id="d5b0a-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="d5b0a-114">アカウントが既に使用されている場合は、現在のパスワードを使ってサインインします。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="d5b0a-115">メールで確認コードを **確認し、** メール アドレスを検証するコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="d5b0a-116">手順 2: 新しいアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="d5b0a-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="d5b0a-117">確認コードを入力すると、新しいアカウントを作成できるページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="d5b0a-118">ユーザー名フィールドとパスワード フィールドに使用するアカウントを入力し、[スタート] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="d5b0a-119">手順 3: ドメインの所有権を確認し、管理者になる</span><span class="sxs-lookup"><span data-stu-id="d5b0a-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="d5b0a-120">[ **管理者になる] ウィザード** が開きます。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="d5b0a-121">ウィザードが開始されない場合は、[管理者] タイル **を見つ** け、選択します。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="d5b0a-122">Select **Yes, I want to be the admin.**</span><span class="sxs-lookup"><span data-stu-id="d5b0a-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="d5b0a-123">TXT レコードをドメイン レジストラーに追加して、自分が管理するドメインを所有していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="d5b0a-124">ウィザードから追加する TXT レコードが表示されます。また、レジストラーの Web サイトへのリンクと手順のリンクも表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="d5b0a-125">テレナー サイトに TXT レコードを追加したら、ウィザードに戻り **、[OK] を選択すると、レコードが追加されました**。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d5b0a-126">シャドウ テナントを引き続き取りても、既存の情報やサービスには影響はありません。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="d5b0a-127">ただし、ドメイン内のユーザーがライセンスを必要とするサービスにサインアップしている場合は、管理者ロールを取得する一部として、それらのユーザーのライセンスを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="d5b0a-128">管理者セットアップ プロセスが完了したら、ライセンスを購入するか、削除できます。</span><span class="sxs-lookup"><span data-stu-id="d5b0a-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="d5b0a-129">関連記事</span><span class="sxs-lookup"><span data-stu-id="d5b0a-129">Related articles</span></span>

<span data-ttu-id="d5b0a-130">YouTube: [Power BI と Microsoft 365 で IT 管理者のイーオーバーを行う 3 つの手順](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="d5b0a-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="d5b0a-131">Azure 管理センターでの管理者のAD</span><span class="sxs-lookup"><span data-stu-id="d5b0a-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="d5b0a-132">組織でのセルフサービス サインアップの使用</span><span class="sxs-lookup"><span data-stu-id="d5b0a-132">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="d5b0a-133">Power BI サービス管理者の役割について</span><span class="sxs-lookup"><span data-stu-id="d5b0a-133">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

