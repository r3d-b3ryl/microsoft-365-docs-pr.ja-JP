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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 'Microsoft 365 管理センターで組織のパスワード有効期限ポリシーを設定する方法について説明します。 '
ms.openlocfilehash: 88953317bea2b96c04c291dd028a4e9131b9a83e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361662"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="cc4de-103">組織のパスワード有効期限ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="cc4de-103">Set the password expiration policy for your organization</span></span>

<span data-ttu-id="cc4de-104">この記事は、職場、学校、または非営利団体のパスワードの有効期限ポリシーを設定する管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="cc4de-104">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span>  

<span data-ttu-id="cc4de-105">ユーザーの場合は、自分のパスワードを期限なしに設定する権限はありません。</span><span class="sxs-lookup"><span data-stu-id="cc4de-105">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="cc4de-106">職場または学校のテクニカル サポートに、この記事の手順を実行するように依頼してください。</span><span class="sxs-lookup"><span data-stu-id="cc4de-106">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="cc4de-107">管理者は、ユーザー パスワードを一定の日数が経過したら期限切れにするか、パスワードの有効期限が切れないように設定することができます。</span><span class="sxs-lookup"><span data-stu-id="cc4de-107">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> 

> [!Tip]
> <span data-ttu-id="cc4de-108">既定では、パスワードの有効期限は 90 日に設定されています。</span><span class="sxs-lookup"><span data-stu-id="cc4de-108">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="cc4de-109">最近の研究では、強制的なパスワードの変更はメリットよりデメリットの方が大きいことが強く示唆されています。</span><span class="sxs-lookup"><span data-stu-id="cc4de-109">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="cc4de-110">ハッカーが簡単に推測できる方法で、より弱いパスワードの選択、パスワードの再利用、または古いパスワードの更新をユーザーに促します。</span><span class="sxs-lookup"><span data-stu-id="cc4de-110">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="cc4de-111">パスワードを無期限に設定する場合は、[多要素認証](../security-and-compliance/set-up-multi-factor-authentication.md)を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cc4de-111">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="cc4de-112">特定の時間が経過するとユーザーのパスワードが期限切れになるように設定する場合は、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cc4de-112">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="cc4de-113">[Office 365 のグローバル管理者](../add-users/about-admin-roles.md)のみ次の手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="cc4de-113">Only [Office 365 global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="cc4de-114">管理センターで、[**設定**] \> [**設定**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cc4de-114">In the admin center, go to the **Settings** \> **Settings**.</span></span>

2. <span data-ttu-id="cc4de-115">[<a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">セキュリティとプライバシー</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cc4de-115">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="cc4de-116">Office 365 のグローバル管理者でない場合は、[セキュリティとプライバシー] オプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="cc4de-116">If you aren't an Office 365 global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="cc4de-117">[**パスワードの有効期限ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc4de-117">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="cc4de-118">ユーザーがパスワードを変更する必要がないようにするには、[**数日後にユーザーのパスワードが期限切れになるように設定する**] の横のチェックボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc4de-118">If you don't want users to have to change passwords, select the checkbox next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="cc4de-119">パスワードの有効期限が切れる頻度を入力します。</span><span class="sxs-lookup"><span data-stu-id="cc4de-119">Type how often passwords should expire.</span></span> <span data-ttu-id="cc4de-120">14 〜 730 の日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc4de-120">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="cc4de-121">2 つ目のボックスに、パスワードが期限切れになる前にユーザーに通知する日数を入力して、[ **保存** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc4de-121">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="cc4de-122">日数を 1 から 30 から選びます。</span><span class="sxs-lookup"><span data-stu-id="cc4de-122">Choose a number of days from 1 to 30.</span></span>
    
7. <span data-ttu-id="cc4de-123">ユーザーのパスワードの有効期限が切れた場合は、画面の右下隅に通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc4de-123">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="cc4de-124">パスワードの有効期限機能に関する重要事項</span><span class="sxs-lookup"><span data-stu-id="cc4de-124">Important things you need to know about the password expiration feature</span></span>

<span data-ttu-id="cc4de-125">2018 年 1 月現在、この機能については以下の点にご留意ください。</span><span class="sxs-lookup"><span data-stu-id="cc4de-125">Here are some things to know about how this feature currently works as of January 2018:</span></span>
  
- <span data-ttu-id="cc4de-p106">Outlook アプリのみを使用するユーザーには、キャッシュで有効期限が切れるまで Office 365 パスワードのリセットは強制されません。これは、実際に期限が切れた日から数日経過することがあります。管理者レベルでは、これに対する回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="cc4de-p106">People who only use the Outlook app won't be forced to reset their Office 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>
    
- <span data-ttu-id="cc4de-p107">ユーザーには、X 日後にパスワードの有効期限が切れる旨のメール通知が送られません。この機能は必要ですか? **[ここで投票してください。](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span><span class="sxs-lookup"><span data-stu-id="cc4de-p107">Users do not get an email notification that their password is going to expire in X number of days. Do you want this feature? **[Vote here!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span></span>
    
## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="cc4de-132">最後に使用したパスワードの再使用を禁止する</span><span class="sxs-lookup"><span data-stu-id="cc4de-132">Prevent last password from being used again</span></span>

<span data-ttu-id="cc4de-133">ユーザーが古いパスワードを再使用することを禁止する場合、Azure AD でこの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cc4de-133">If you want to prevent your users from recycling old passwords, you can do so in Azure AD.</span></span> <span data-ttu-id="cc4de-134">「[組織のパスワード有効期限ポリシーを設定する](https://docs.microsoft.com/office365/admin/manage/set-password-expiration-policy?view=o365-worldwide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc4de-134">See [Set the password expiration policy for your organization](https://docs.microsoft.com/office365/admin/manage/set-password-expiration-policy?view=o365-worldwide).</span></span>

<span data-ttu-id="cc4de-135">また、従業員がモバイル デバイスを使用して Office 365 にアクセスしている場合、それをワイプしてパスワードが保存されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cc4de-135">In addition, if an employee used a mobile device to access Office 365, you can wipe it to ensure the password is no longer stored and recycled from there.</span></span> <span data-ttu-id="cc4de-136">詳細については、「[元従業員のモバイル デバイスをワイプし、ブロックする](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc4de-136">To learn more, see [Wipe and block a former employee's mobile device](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span></span>


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-office-365"></a><span data-ttu-id="cc4de-137">オンプレミスの Active Directory から Azure AD (Office 365) へユーザー パスワード ハッシュを同期する</span><span class="sxs-lookup"><span data-stu-id="cc4de-137">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Office 365)</span></span>

<span data-ttu-id="cc4de-138">この記事は、クラウド専用ユーザー (Azure AD) の有効期限ポリシーを設定するユーザーを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="cc4de-138">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="cc4de-139">パスワード ハッシュ同期、パススルー認証、または ADFS などのオンプレミスのフェデレーションを使用するハイブリッド ID ユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="cc4de-139">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="cc4de-140">ユーザー パスワード ハッシュをオンプレミスの AD から Azure AD に同期する方法については、「[Implement password hash synchronization with Azure AD Connect sync (Azure AD Connect 同期でパスワード ハッシュ同期を実装する)](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc4de-140">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
