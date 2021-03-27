---
title: 管理者アカウントを保護する
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
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
ms.openlocfilehash: 0d687407fad1cec5da49dbc33ffeb84366f1c309
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398243"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="a3ee0-103">管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="a3ee0-103">Protect your administrator accounts</span></span>

<span data-ttu-id="a3ee0-104">管理者アカウントには昇格された特権が付与されていますので、ハッカーやサイバー犯罪者にとって貴重なターゲットです。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="a3ee0-105">この記事の内容</span><span class="sxs-lookup"><span data-stu-id="a3ee0-105">This article describes:</span></span>

- <span data-ttu-id="a3ee0-106">緊急事態に備え、追加の管理者アカウントを設定する方法。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="a3ee0-107">これらのアカウントを保護する方法。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-107">How to protect these accounts.</span></span>

<span data-ttu-id="a3ee0-108">Microsoft 365 にサインアップして情報を入力すると、自動的にグローバル管理者になります。グローバル管理者は、Microsoft 管理センターのユーザー アカウントと他のすべての設定を最終的に制御できますが、アクセスの程度が異なるさまざまな種類の管理アカウントがあります。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-108">When you sign up for Microsoft 365 and enter your information, you automatically become the Global admin. A Global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="a3ee0-109">管理 [役割の種類ごとに異](/office365/admin/add-users/about-admin-roles) なるアクセス レベルの詳細については、管理者の役割に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-109">See [about admin roles](/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>

## <a name="create-additional-admin-accounts"></a><span data-ttu-id="a3ee0-110">追加の管理者アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="a3ee0-110">Create additional admin accounts</span></span>

<span data-ttu-id="a3ee0-111">管理アカウントは管理にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="a3ee0-112">管理者は、Office アプリを定期的に使用するための個別のユーザー アカウントを持ち、アカウントやデバイスの管理や他の管理機能の作業に必要な場合にのみ管理アカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="a3ee0-113">また、管理者アカウントから Microsoft 365 ライセンスを削除して、支払いを行う必要がなさる必要がなさるのも良い考えです。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-113">It's also a good idea to remove the Microsoft 365 license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="a3ee0-114">別の信頼できる従業員に管理者アクセス権を与えるために、少なくとも 1 つの追加のグローバル管理者アカウントをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-114">You'll want to set up at least one additional Global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="a3ee0-115">ユーザー管理用に個別の管理者アカウントを作成することもできます (この役割はユーザー管理 **管理者と呼ばれています**)。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="a3ee0-116">詳細については、「管理者の役割 [」を参照してください](/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-116">For more information, see [about admin roles](/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="a3ee0-117">追加の管理者アカウントを作成するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="a3ee0-118">管理センターに移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">し、</a> 左側のナビゲーションで **[ユーザー** \> **のアクティブな** ユーザー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![左側のナビゲーションで [ユーザー] と [アクティブ ユーザー] の順に選択します。](../media/Activeusers.png)

 2. <span data-ttu-id="a3ee0-120">[アクティブ **なユーザー]** ページで、ページの上部にある [ユーザーの追加]を選択し、[新しいユーザー] パネルで名前と他の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
 3. <span data-ttu-id="a3ee0-121">[役割] **セクションを展開** し、[グローバル管理者] **を** 選択して、このユーザーにグローバル管理者アクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="a3ee0-122">[カスタマイズされた管理者] **を選択し** 、表示される役割を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="a3ee0-123">[代替メール アドレス] テキスト ボックス **に別のメールを** 入力します。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="a3ee0-124">ロックアウトされた場合は、このアドレスを使用してパスワード情報を回復できます。グローバル管理者の場合、請求明細書もこのアドレスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-124">You can use this address to recover your password information if you get locked out. For Global admins, a billing statement will also be sent to this address.</span></span>

    ![管理者の役割を選択する](../media/adminroles.png)

 4. <span data-ttu-id="a3ee0-126">[製品 **ライセンス] セクション** で **、Microsoft 365 Business** のセレクターを [オフ] に、製品ライセンスなしでユーザーを作成するを [オン **]** に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![製品ライセンスの選択](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="a3ee0-128">緊急管理者アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="a3ee0-128">Create an emergency admin account</span></span>

<span data-ttu-id="a3ee0-129">また、多要素認証 (MFA) でセットアップされていないバックアップ アカウントを作成して、誤って自分自身をロックアウトしないようにする必要があります (たとえば、第 2 の検証形式として使用している携帯電話を紛失した場合など)。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="a3ee0-130">このアカウントのパスワードが語句または 16 文字以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="a3ee0-131">これは、多くの場合、"break-glass アカウント" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="a3ee0-132">自分でユーザー アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="a3ee0-132">Create a user account for yourself</span></span>

<span data-ttu-id="a3ee0-133">ユーザー アカウントを使用して、メールの確認など、組織との共同作業に参加します。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="a3ee0-134">つまり、管理者資格情報は  *Alice.Chavez <span></span> @Contoso.org* に似ている可能性があります。通常のユーザー アカウントは *Alice <span></span> @Contoso.com に似ている可能性があります*。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-134">This means your admin credentials might be similar to  *Alice.Chavez <span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="a3ee0-135">新しいユーザー アカウントを作成するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-135">To create a new user account:</span></span>

1. <span data-ttu-id="a3ee0-136">管理センターに移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">し、</a> 左側のナビゲーションで **[ユーザー** \> **のアクティブな** ユーザー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="a3ee0-137">[アクティブ **なユーザー]** ページで、ページの上部にある [ユーザーの追加]を選択し、[新しいユーザー] パネルで名前と他の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="a3ee0-138">[役割] **セクションを展開** し、[ユーザー] **(管理アクセスなし) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
4. <span data-ttu-id="a3ee0-139">[製品 **ライセンス] セクション** で **、Microsoft 365 Business** のセレクターを [オン] に移動 **します**。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span>

## <a name="turn-on-security-defaults"></a><span data-ttu-id="a3ee0-140">セキュリティの既定値を有効にする</span><span class="sxs-lookup"><span data-stu-id="a3ee0-140">Turn on security defaults</span></span>

<span data-ttu-id="a3ee0-141">セキュリティの既定値は、Microsoft が組織の代わりに管理する構成済みのセキュリティ設定を提供することで、組織を ID 関連の攻撃から保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-141">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="a3ee0-142">これらの設定には、すべての管理者およびユーザー アカウントに対して多要素認証 (MFA) を有効にする機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-142">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="a3ee0-143">セキュリティの既定値の詳細と有効にする方法については、「セキュリティの既定値を有効にする [」を参照してください](m365-campaigns-conditional-access.md)。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-143">For more information about security defaults and to learn how to enable them on, see [Turn on security defaults](m365-campaigns-conditional-access.md).</span></span>

## <a name="additional-recommendations"></a><span data-ttu-id="a3ee0-144">その他の推奨事項</span><span class="sxs-lookup"><span data-stu-id="a3ee0-144">Additional recommendations</span></span>

- <span data-ttu-id="a3ee0-145">管理者アカウントを使用する前に、関連のないブラウザー セッションとアプリ (個人用メール アカウントを含む) を閉じます。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-145">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="a3ee0-146">プライベート ウィンドウまたはシークレット ブラウザー ウィンドウでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-146">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="a3ee0-147">管理タスクを完了した後は、必ずブラウザー セッションからサインアウトしてください。</span><span class="sxs-lookup"><span data-stu-id="a3ee0-147">After completing admin tasks, be sure to sign out of the browser session.</span></span>
