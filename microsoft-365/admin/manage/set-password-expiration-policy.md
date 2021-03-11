---
title: 組織のパスワード有効期限ポリシーを設定します。
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: Microsoft 365 管理センターで組織のパスワード有効期限ポリシーを設定する方法について説明します。
ms.openlocfilehash: 4a7b544b6eded6f0cd6441ad7f6b02de790e5e44
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "50603986"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="1efcd-103">組織のパスワード有効期限ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="1efcd-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1efcd-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="1efcd-104">The admin center is changing.</span></span> <span data-ttu-id="1efcd-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-worldwide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1efcd-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-worldwide).</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="1efcd-106">開始する前に</span><span class="sxs-lookup"><span data-stu-id="1efcd-106">Before you begin</span></span>

<span data-ttu-id="1efcd-107">この記事は、職場、学校、または非営利団体のパスワードの有効期限ポリシーを設定する管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="1efcd-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="1efcd-108">これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1efcd-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="1efcd-109">[管理者アカウントとは](../admin-overview/admin-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1efcd-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span>

<span data-ttu-id="1efcd-110">これらの手順を実行するには、[グローバル管理者](../add-users/about-admin-roles.md)である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1efcd-110">You must be a [global admin](../add-users/about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="1efcd-111">ユーザーの場合は、自分のパスワードを期限なしに設定する権限はありません。</span><span class="sxs-lookup"><span data-stu-id="1efcd-111">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="1efcd-112">職場または学校のテクニカル サポートに、この記事の手順を実行するように依頼してください。</span><span class="sxs-lookup"><span data-stu-id="1efcd-112">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="1efcd-113">管理者は、ユーザー パスワードを一定の日数が経過したら期限切れにするか、パスワードの有効期限が切れないように設定することができます。</span><span class="sxs-lookup"><span data-stu-id="1efcd-113">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span>

## <a name="set-password-expiration-policy"></a><span data-ttu-id="1efcd-114">パスワードの有効期限ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="1efcd-114">Set password expiration policy</span></span>

> [!Tip]
> <span data-ttu-id="1efcd-115">既定では、パスワードの有効期限は 90 日に設定されています。</span><span class="sxs-lookup"><span data-stu-id="1efcd-115">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="1efcd-116">最近の研究では、強制的なパスワードの変更はメリットよりデメリットの方が大きいことが強く示唆されています。</span><span class="sxs-lookup"><span data-stu-id="1efcd-116">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="1efcd-117">ハッカーが簡単に推測できる方法で、より弱いパスワードの選択、パスワードの再利用、または古いパスワードの更新をユーザーに促します。</span><span class="sxs-lookup"><span data-stu-id="1efcd-117">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="1efcd-118">パスワードを無期限に設定する場合は、[多要素認証](../security-and-compliance/set-up-multi-factor-authentication.md)を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1efcd-118">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="1efcd-119">特定の時間が経過するとユーザーのパスワードが期限切れになるように設定する場合は、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1efcd-119">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>

1. <span data-ttu-id="1efcd-120">管理センターで、[**設定**] \> [**組織の設定**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="1efcd-120">In the admin center, go to the **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="1efcd-121">[<a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">セキュリティとプライバシー</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1efcd-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="1efcd-122">グローバル管理者でない場合は、[セキュリティとプライバシー] オプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="1efcd-122">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="1efcd-123">[**パスワードの有効期限ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1efcd-123">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="1efcd-124">ユーザーがパスワードを変更する必要がないようにするには、[**数日後にユーザーのパスワードが期限切れになるように設定する**] の横にあるチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1efcd-124">If you don't want users to have to change passwords, uncheck the box next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="1efcd-125">パスワードの有効期限が切れる頻度を入力します。</span><span class="sxs-lookup"><span data-stu-id="1efcd-125">Type how often passwords should expire.</span></span> <span data-ttu-id="1efcd-126">14 〜 730 の日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="1efcd-126">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="1efcd-127">2 つ目のボックスに、パスワードが期限切れになる前にユーザーに通知する日数を入力して、[ **保存** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1efcd-127">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="1efcd-128">日数を 1 から 30 から選びます。</span><span class="sxs-lookup"><span data-stu-id="1efcd-128">Choose a number of days from 1 to 30.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="1efcd-129">パスワードの有効期限機能に関する重要事項</span><span class="sxs-lookup"><span data-stu-id="1efcd-129">Important things you need to know about the password expiration feature</span></span>
  
- <span data-ttu-id="1efcd-p108">Outlook アプリのみを使用するユーザーには、キャッシュで有効期限が切れるまで Microsoft 365 パスワードのリセットは強制されません。これは、実際に期限が切れた日から数日経過することがあります。管理者レベルでは、これに対する回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="1efcd-p108">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>

## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="1efcd-133">最後に使用したパスワードの再使用を禁止する</span><span class="sxs-lookup"><span data-stu-id="1efcd-133">Prevent last password from being used again</span></span>

<span data-ttu-id="1efcd-134">ユーザーが古いパスワードを再使用できないようにするには、オンプレミスの Active Directory (AD) でパスワードの履歴の記録を適用します。</span><span class="sxs-lookup"><span data-stu-id="1efcd-134">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="1efcd-135">詳細については、[「カスタムパスワードポリシーを作成する 」](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1efcd-135">See [Create a custom password policy](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="1efcd-136">Azure AD では、ユーザーがパスワードを変更する場合、前回のパスワードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="1efcd-136">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="1efcd-137">パスワード ポリシーは、Azure AD で直接作成および管理されるすべてのユーザーアカウントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1efcd-137">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="1efcd-138">このパスワード ポリシーは変更できません。</span><span class="sxs-lookup"><span data-stu-id="1efcd-138">This password policy can't be modified.</span></span> <span data-ttu-id="1efcd-139">詳細については、「[Azure AD のパスワード ポリシー](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1efcd-139">See [Azure AD password policies](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="1efcd-140">オンプレミスの Active Directory から Azure AD (Microsoft 365) へユーザー パスワード ハッシュを同期する</span><span class="sxs-lookup"><span data-stu-id="1efcd-140">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="1efcd-141">この記事は、クラウド専用ユーザー (Azure AD) の有効期限ポリシーを設定するユーザーを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="1efcd-141">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="1efcd-142">パスワード ハッシュ同期、パススルー認証、ADFSなどのオンプレミス フェデレーションを使用するハイブリッド ID ユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="1efcd-142">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="1efcd-143">ユーザー パスワード ハッシュをオンプレミスの AD から Azure AD に同期する方法については、「[Implement password hash synchronization with Azure AD Connect sync (Azure AD Connect 同期でパスワード ハッシュ同期を実装する)](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1efcd-143">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a><span data-ttu-id="1efcd-144">Azure Active Directory のパスワード ポリシーとアカウントの制限</span><span class="sxs-lookup"><span data-stu-id="1efcd-144">Password policies and account restrictions in Azure Active Directory</span></span>

<span data-ttu-id="1efcd-145">Azure Active Directory には、その他のパスワード ポリシーと制限を設定できます。</span><span class="sxs-lookup"><span data-stu-id="1efcd-145">You can set more password policies and restrictions in Azure active directory.</span></span> <span data-ttu-id="1efcd-146">詳細については、「[Azure Active Directory のパスワード ポリシーとアカウントの制限](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="1efcd-146">Check out [Password policies and account restrictions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy) for more info.</span></span>

## <a name="update-password-policy"></a><span data-ttu-id="1efcd-147">パスワードポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="1efcd-147">Update password Policy</span></span>

<span data-ttu-id="1efcd-148">Set-MsolPasswordPolicy コマンドレットは、指定されたドメインまたはテナントのパスワードポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="1efcd-148">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant.</span></span> <span data-ttu-id="1efcd-149">2つの設定が必要です。まず、パスワードを変更するまでの有効期間を指定します。2番目に、パスワードの有効期限が近づいているという最初の通知をユーザーが受け取るときにトリガーされる、パスワードの有効期限までの日数を示します。</span><span class="sxs-lookup"><span data-stu-id="1efcd-149">Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="1efcd-150">特定のドメインまたはテナントのパスワードポリシーを更新する方法については、[「Set-MsolPasswordPolicy」](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1efcd-150">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span></span>

## <a name="related-content"></a><span data-ttu-id="1efcd-151">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="1efcd-151">Related content</span></span>

[<span data-ttu-id="1efcd-152">ユーザーが自分でパスワードをリセットできるようにする</span><span class="sxs-lookup"><span data-stu-id="1efcd-152">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="1efcd-153">パスワードをリセットする</span><span class="sxs-lookup"><span data-stu-id="1efcd-153">Reset passwords</span></span>](../add-users/reset-passwords.md)
