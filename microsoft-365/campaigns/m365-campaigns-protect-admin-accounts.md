---
title: 管理者アカウントを保護する
f1.keywords:
- NOCSH
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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 管理者アカウントを設定して保護する方法について学習します。
ms.openlocfilehash: 73e4b69571b1e1d0a4d1585224fe256ff135c40a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044490"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="96935-103">管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="96935-103">Protect your administrator accounts</span></span>

<span data-ttu-id="96935-104">管理者アカウントには昇格された特権が付与されます。このため、管理者アカウントはハッカーやサイバー犯罪の重要なターゲットです。</span><span class="sxs-lookup"><span data-stu-id="96935-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="96935-105">この記事の内容</span><span class="sxs-lookup"><span data-stu-id="96935-105">This article describes:</span></span>

- <span data-ttu-id="96935-106">緊急事態に備え、追加の管理者アカウントを設定する方法。</span><span class="sxs-lookup"><span data-stu-id="96935-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="96935-107">これらのアカウントを保護する方法。</span><span class="sxs-lookup"><span data-stu-id="96935-107">How to protect these accounts.</span></span>

<span data-ttu-id="96935-108">Microsoft 365 にサインアップして情報を入力すると、自動的にグローバル管理者になります。グローバル管理者は、Microsoft 管理センターでユーザー アカウントと他のすべての設定を最終的に制御しますが、アクセスの程度が異なるさまざまな種類の管理者アカウントがあります。</span><span class="sxs-lookup"><span data-stu-id="96935-108">When you sign up for Microsoft 365 and enter your information, you automatically become the global admin. A global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="96935-109">管理者 [ロールの種類ごとに](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) 異なるアクセス レベルの詳細については、管理者ロールに関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96935-109">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>

## <a name="create-additional-admin-accounts"></a><span data-ttu-id="96935-110">追加の管理者アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="96935-110">Create additional admin accounts</span></span>

<span data-ttu-id="96935-111">管理アカウントは管理専用に使用します。</span><span class="sxs-lookup"><span data-stu-id="96935-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="96935-112">管理者は、Office アプリを定期的に使用するために別のユーザー アカウントを持ち、アカウントやデバイスの管理や他の管理機能の作業に必要な場合にのみ管理アカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96935-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="96935-113">また、管理者アカウントから Microsoft 365 ライセンスを削除して、料金を支払う必要がなさらないのも良い方法です。</span><span class="sxs-lookup"><span data-stu-id="96935-113">It's also a good idea to remove the Microsoft 365 license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="96935-114">別の信頼できる従業員に管理者アクセス権を付与するために、少なくとも 1 つの追加のグローバル管理者アカウントを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96935-114">You'll want to set up at least one additional global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="96935-115">ユーザー管理用に個別の管理者アカウントを作成することもできます (この役割はユーザー管理 **管理者と呼ばれています**)。</span><span class="sxs-lookup"><span data-stu-id="96935-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="96935-116">詳細については、「管理者ロール [」を参照してください](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="96935-116">For more information, see [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="96935-117">追加の管理者アカウントを作成するには:</span><span class="sxs-lookup"><span data-stu-id="96935-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="96935-118">管理センターに <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">移動し、</a> 左側のナビゲーションで **[アクティブ** な \> **ユーザー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="96935-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![Choose Users and then Active users in the left nav](../media/Activeusers.png)

 2. <span data-ttu-id="96935-120">[**アクティブなユーザー]** ページで、ページの上部にある [ユーザーの追加]を選択し、[新しいユーザー] パネルで名前と他の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="96935-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
 3. <span data-ttu-id="96935-121">[ロール **] セクションを展開** し、[グローバル管理者] を **選択して、** このユーザーにグローバル管理者アクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="96935-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="96935-122">カスタマイズされた管理者を **選択し** 、表示される役割を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="96935-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="96935-123">[代替メール アドレス] テキスト ボックス **に代替メールを** 入力します。</span><span class="sxs-lookup"><span data-stu-id="96935-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="96935-124">ロックアウトされた場合は、このアドレスを使用してパスワード情報を復元できます。グローバル管理者の場合は、請求明細書もこの住所に送信されます。</span><span class="sxs-lookup"><span data-stu-id="96935-124">You can use this address to recover your password information if you get locked out. For global admins, a billing statement will also be sent to this address.</span></span>

    ![管理者ロールを選択する](../media/adminroles.png)

 4. <span data-ttu-id="96935-126">[製品ライセンス **]** セクションで **、Microsoft 365 Business** のセレクターを [オフ] に、製品ライセンスのないユーザーの作成を [オン **]** に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="96935-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![製品ライセンスを選択する](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="96935-128">緊急管理者アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="96935-128">Create an emergency admin account</span></span>

<span data-ttu-id="96935-129">また、多要素認証 (MFA) でセットアップされていないバックアップ アカウントを作成して、誤って自分自身をロックアウトしないようにする必要があります (たとえば、2 番目の形式の検証として使用している電話を紛失した場合など)。</span><span class="sxs-lookup"><span data-stu-id="96935-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="96935-130">このアカウントのパスワードが語句または 16 文字以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="96935-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="96935-131">これは、多くの場合、"割れ子アカウント" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="96935-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="96935-132">自分用のユーザー アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="96935-132">Create a user account for yourself</span></span>

<span data-ttu-id="96935-133">ユーザー アカウントを使用して、メールの確認など、組織との共同作業に参加します。</span><span class="sxs-lookup"><span data-stu-id="96935-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="96935-134">つまり、管理者の資格情報は  *Alice.Chavez <span></span> @Contoso.org* に似ている可能性があります。また、通常のユーザー アカウントは *Alice <span></span> @Contoso.com* に似ています。</span><span class="sxs-lookup"><span data-stu-id="96935-134">This means your admin credentials might be similar to  *Alice.Chavez <span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="96935-135">新しいユーザー アカウントを作成するには:</span><span class="sxs-lookup"><span data-stu-id="96935-135">To create a new user account:</span></span>

1. <span data-ttu-id="96935-136">管理センターに <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">移動し、</a> 左側のナビゲーションで **[アクティブ** \> **なユーザー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="96935-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="96935-137">[**アクティブなユーザー]** ページで、ページの上部にある [ユーザーの追加]を選択し、[新しいユーザー] パネルで名前と他の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="96935-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="96935-138">[役割 **] セクションを** 展開し、[ユーザー \*\*](管理アクセス権なし) を選択します\*\*。</span><span class="sxs-lookup"><span data-stu-id="96935-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
4. <span data-ttu-id="96935-139">[製品ライセンス **] セクション** で **、Microsoft 365 Business** のセレクターを [オン] に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="96935-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span>

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a><span data-ttu-id="96935-140">多要素認証用にこれらの各アカウントを登録する</span><span class="sxs-lookup"><span data-stu-id="96935-140">Register each of these accounts for multi-factor authentication</span></span>

<span data-ttu-id="96935-141">これらのアカウントが多要素認証 [を使用している必要があります](m365-campaigns-multifactor-authenication.md)。</span><span class="sxs-lookup"><span data-stu-id="96935-141">Make sure these accounts are using [multifactor authentication](m365-campaigns-multifactor-authenication.md).</span></span>

## <a name="additional-recommendations"></a><span data-ttu-id="96935-142">その他の推奨事項</span><span class="sxs-lookup"><span data-stu-id="96935-142">Additional recommendations</span></span>

- <span data-ttu-id="96935-143">管理者アカウントも多要素認証用に設定してください。</span><span class="sxs-lookup"><span data-stu-id="96935-143">Be sure that admin accounts are also set up for multi-factor authentication.</span></span> <span data-ttu-id="96935-144">これを行う方法については、「条件付きアクセス ポリシーを構成 [する」を参照してください](m365-campaigns-conditional-access.md)。</span><span class="sxs-lookup"><span data-stu-id="96935-144">We'll show you how to do this in [Configure conditional access policies](m365-campaigns-conditional-access.md).</span></span>
- <span data-ttu-id="96935-145">管理者アカウントを使用する前に、個人用の電子メール アカウントを含む、関連のないブラウザー セッションとアプリを閉じてください。</span><span class="sxs-lookup"><span data-stu-id="96935-145">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="96935-146">プライベート ウィンドウまたはシークレット ブラウザー ウィンドウでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="96935-146">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="96935-147">管理タスクを完了した後、必ずブラウザー セッションからサインアウトしてください。</span><span class="sxs-lookup"><span data-stu-id="96935-147">After completing admin tasks, be sure to sign out of the browser session.</span></span>
