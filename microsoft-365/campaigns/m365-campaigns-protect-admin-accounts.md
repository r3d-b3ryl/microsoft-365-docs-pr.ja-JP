---
title: 管理者アカウントを保護する
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 管理者アカウントをセットアップして保護する方法について説明します。
ms.openlocfilehash: 76c90b48e0f0859ed856b6e3dc772aedfc2ccdaf
ms.sourcegitcommit: 7713e777731025c165e9e936198609503ade5665
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "38753744"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="01a36-103">管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="01a36-103">Protect your administrator accounts</span></span>

<span data-ttu-id="01a36-104">管理者アカウントには、昇格された特権が付与されるので、ハッカーおよびサイバー犯罪者にとって重要な目標となります。</span><span class="sxs-lookup"><span data-stu-id="01a36-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="01a36-105">この記事の内容</span><span class="sxs-lookup"><span data-stu-id="01a36-105">This article describes:</span></span>

- <span data-ttu-id="01a36-106">緊急対応のための追加の管理者アカウントをセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="01a36-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="01a36-107">これらのアカウントを保護する方法。</span><span class="sxs-lookup"><span data-stu-id="01a36-107">How to protect these accounts.</span></span>
 
<span data-ttu-id="01a36-108">Microsoft 365 Business にサインアップして、情報を入力すると、自動的にグローバル管理者になります。グローバル管理者は、Microsoft 管理センターのユーザーアカウントとその他のすべての設定を最終的に制御しますが、さまざまなレベルのアクセス権を持つ管理者アカウントの種類が多数あります。</span><span class="sxs-lookup"><span data-stu-id="01a36-108">When you sign up for Microsoft 365 Business and enter your information, you automatically become the global admin. A global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="01a36-109">それぞれの種類の管理者の役割の異なるアクセスレベルについては、「[管理者ロールについ](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01a36-109">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>


## <a name="create-additional-admin-accounts"></a><span data-ttu-id="01a36-110">追加の管理者アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="01a36-110">Create additional admin accounts</span></span>

<span data-ttu-id="01a36-111">管理用にのみ管理者アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="01a36-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="01a36-112">管理者は、Office アプリを定期的に使用するための個別のユーザーアカウントを持ち、他の管理者機能の管理に必要な場合にのみ管理アカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01a36-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="01a36-113">また、管理者アカウントから Microsoft 365 Business license を削除して、料金を支払う必要がないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="01a36-113">It's also a good idea to remove the Microsoft 365 Business license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="01a36-114">他の信頼された従業員に対する管理者アクセス権を与えるには、少なくとも1つのグローバル管理者アカウントを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01a36-114">You'll want to set up at least one additional global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="01a36-115">また、ユーザー管理用に別の管理者アカウントを作成することもできます (この役割は、**ユーザー管理の管理者**と呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="01a36-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="01a36-116">詳細については、「[管理者の役割につい](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01a36-116">For more information, see [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="01a36-117">追加の管理者アカウントを作成するには:</span><span class="sxs-lookup"><span data-stu-id="01a36-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="01a36-118"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">管理センター</a>に移動し、左側のナビゲーションで [**ユーザー** \>の**アクティブなユーザー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01a36-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![左側のナビゲーションで、[ユーザー]、[アクティブユーザー] の順に選択します。](media/Activeusers.png)

2. <span data-ttu-id="01a36-120">[**アクティブなユーザー** ] ページで、ページの上部にある [**ユーザーの追加**] を選択し、[**新しいユーザー** ] パネルで名前とその他の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="01a36-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="01a36-121">[**役割**] セクションを展開し、[**グローバル管理者**] を選択して、このユーザーにグローバル管理者アクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="01a36-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="01a36-122">[カスタマイズされた**管理者**] を選択して、表示される役割のいずれかを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="01a36-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="01a36-123">[**代替メールアドレス**] テキストボックスに別の電子メールを入力します。</span><span class="sxs-lookup"><span data-stu-id="01a36-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="01a36-124">ロックアウトされている場合は、このアドレスを使用してパスワード情報を回復できます。グローバル管理者の場合、billing ステートメントはこのアドレスにも送信されます。</span><span class="sxs-lookup"><span data-stu-id="01a36-124">You can use this address to recover your password information if you get locked out. For global admins, a billing statement will also be sent to this address.</span></span>

    ![管理者の役割を選択する](media/adminroles.png)
    
4. <span data-ttu-id="01a36-126">[**製品ライセンス**] セクションで、 **Microsoft 365 Business**のセレクターを**オフ**にし、[**製品ライセンスなしでユーザーを作成**する] を **[オン**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="01a36-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![製品ライセンスを選択する](media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="01a36-128">緊急管理者アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="01a36-128">Create an emergency admin account</span></span>

<span data-ttu-id="01a36-129">また、多要素認証 (MFA) で設定されていないバックアップアカウントを作成して、誤ってロックしないようにする必要があります (たとえば、2番目の確認フォームとして使用している電話を失った場合)。</span><span class="sxs-lookup"><span data-stu-id="01a36-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="01a36-130">このアカウントのパスワードが、語句または16文字以上の長さであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="01a36-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="01a36-131">これは、"ブレイクガラスアカウント" と呼ばれることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="01a36-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="01a36-132">自分のユーザーアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="01a36-132">Create a user account for yourself</span></span>

<span data-ttu-id="01a36-133">ユーザーアカウントを使用して、メールのチェックを含む、組織とのグループ作業に参加します。</span><span class="sxs-lookup"><span data-stu-id="01a36-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="01a36-134">これは、管理者の資格情報が*alice の @Contoso<span></span>Chavez*に似ている可能性があることを意味し、通常のユーザーアカウントは*<span></span>alice @Contoso*に似ている場合があります。</span><span class="sxs-lookup"><span data-stu-id="01a36-134">This means your admin credentials might be similar to  *Alice.Chavez<span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="01a36-135">新しいユーザーアカウントを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="01a36-135">To create a new user account:</span></span>
1. <span data-ttu-id="01a36-136"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">管理センター</a>に移動し、左側のナビゲーションで [**ユーザー** \>の**アクティブなユーザー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01a36-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="01a36-137">[**アクティブなユーザー** ] ページで、ページの上部にある [**ユーザーの追加**] を選択し、[**新しいユーザー** ] パネルで名前とその他の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="01a36-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="01a36-138">[**役割**] セクションを展開し、[**ユーザー (管理者権限なし)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01a36-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
1. <span data-ttu-id="01a36-139">[**製品ライセンス**] セクションで、 **Microsoft 365 Business**のセレクターを **[オン**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="01a36-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span> 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a><span data-ttu-id="01a36-140">多要素認証のためにこれらの各アカウントを登録する</span><span class="sxs-lookup"><span data-stu-id="01a36-140">Register each of these accounts for multi-factor authentication</span></span>


## <a name="additional-recommendations"></a><span data-ttu-id="01a36-141">その他の推奨事項</span><span class="sxs-lookup"><span data-stu-id="01a36-141">Additional recommendations</span></span>

- <span data-ttu-id="01a36-142">管理者アカウントが多要素認証にも設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="01a36-142">Be sure that admin accounts are also set up for multi-factor authentication.</span></span> <span data-ttu-id="01a36-143">これを行う方法については、「[条件付きアクセスポリシーを構成](m365-campaigns-conditional-access.md)する」で説明します。</span><span class="sxs-lookup"><span data-stu-id="01a36-143">We'll show you how to do this in [Configure conditional access policies](m365-campaigns-conditional-access.md).</span></span>
- <span data-ttu-id="01a36-144">管理者アカウントを使用する前に、個人の電子メールアカウントを含む、関連のないブラウザーセッションとアプリをすべて閉じてください。</span><span class="sxs-lookup"><span data-stu-id="01a36-144">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="01a36-145">プライベートまたは incognito ブラウザウィンドウでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="01a36-145">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="01a36-146">管理タスクを完了した後、ブラウザーセッションからサインアウトしてください。</span><span class="sxs-lookup"><span data-stu-id="01a36-146">After completing admin tasks, be sure to sign out of the browser session.</span></span>