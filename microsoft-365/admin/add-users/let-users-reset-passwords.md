---
title: ユーザーが自分でパスワードをリセットできるようにする
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: セルフサービスのパスワードリセットツールを使用してパスワードをリセットする方法について説明します。
ms.openlocfilehash: 1684afd1baf32acc6c4245938b2ac7ee024d7374
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47361809"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="54444-103">ユーザーが自分でパスワードをリセットできるようにする</span><span class="sxs-lookup"><span data-stu-id="54444-103">Let users reset their own passwords</span></span>

<span data-ttu-id="54444-104">Microsoft 365 管理者は、 [セルフサービスのパスワードリセットツール](https://go.microsoft.com/fwlink/p/?LinkId=522677) を使用して、ユーザーのパスワードをリセットする必要がないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="54444-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="54444-105">作業が少なくてすみます。</span><span class="sxs-lookup"><span data-stu-id="54444-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="54444-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="54444-106">Before you begin</span></span>
  
- <span data-ttu-id="54444-107">Microsoft 365 business、エデュケーション、または非営利 **団体の有料プランを使用し** て、クラウドユーザーのセルフサービスのパスワードリセットを利用できます。</span><span class="sxs-lookup"><span data-stu-id="54444-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="54444-108">Microsoft 365 の試用版では動作しません。</span><span class="sxs-lookup"><span data-stu-id="54444-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="54444-p103">この操作には Azure を使用します。これらの手順を行うときに、自動的に **無料** で Azure にあるこの機能を取得できます。その他の Azure 機能を使用しない場合は、セルフサービスによるパスワード リセットをオンにするために費用はかかりません。</span><span class="sxs-lookup"><span data-stu-id="54444-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="54444-112">**オンプレミスの Active Directory を使用している場合**は、上の2つのポイントは適用されません。</span><span class="sxs-lookup"><span data-stu-id="54444-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="54444-113">代わりに、これを設定できますが、 **AZURE AD Premium への有料サブスクリプションが必要**です。</span><span class="sxs-lookup"><span data-stu-id="54444-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="54444-114">この記事は、職場、学校、または非営利団体のパスワードの有効期限ポリシーを設定する管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="54444-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="54444-115">これらの手順を完了するには、Microsoft 365 管理者アカウントでサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54444-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="54444-116">管理者アカウントとは</span><span class="sxs-lookup"><span data-stu-id="54444-116">What's an admin account?</span></span>](../admin-overview/admin-overview.md)

<span data-ttu-id="54444-117">これらの手順を実行するには、 [グローバル管理者またはパスワード管理者](about-admin-roles.md) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="54444-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="54444-118">視聴: ユーザーが自分のパスワードをリセットすることを許可する</span><span class="sxs-lookup"><span data-stu-id="54444-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="54444-119">このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="54444-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="54444-120">手順: ユーザーが自分のパスワードをリセットすることを許可する</span><span class="sxs-lookup"><span data-stu-id="54444-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="54444-121">次の手順を行うと、社内のすべてのユーザーに対してセルフサービスによるパスワードのリセットがオンになります。</span><span class="sxs-lookup"><span data-stu-id="54444-121">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="54444-122"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>で、[設定] [ **Settings** > **組織の設定**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="54444-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="54444-123"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>で、[**設定** \> **セキュリティ &amp; プライバシー** ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="54444-123">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="54444-124"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**設定**の設定] [ \> **Settings** \> **セキュリティ &amp; プライバシー** ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="54444-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="54444-125">[ **組織の設定** ] ページの上部で、[ **セキュリティ & プライバシー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="54444-125">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="54444-126">[ **セルフサービスのパスワードのリセット**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="54444-126">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="54444-127">[ **セルフサービスのパスワードのリセット**] で、[ **Azure portal に移動] を選択して、セルフサービスのパスワードのリセットを有効**にします。</span><span class="sxs-lookup"><span data-stu-id="54444-127">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="54444-128">左側のナビゲーションウィンドウで [ **ユーザー**] を選択し、[ **ユーザー |[すべてのユーザー** ] ページで、[ **パスワードのリセット**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="54444-128">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="54444-129">[ **プロパティ** ] ページで、[ **すべて** ] を選択して、会社のすべてのユーザーに対して有効にし、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="54444-129">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="54444-130">ユーザーがサインインすると、今後、パスワードを再設定するのに役立つ追加の連絡先情報を入力するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="54444-130">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="54444-131">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="54444-131">Related content</span></span>

[<span data-ttu-id="54444-132">組織のパスワード有効期限ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="54444-132">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)

[<span data-ttu-id="54444-133">有効期限が切れないように個別のユーザーのパスワードを設定する</span><span class="sxs-lookup"><span data-stu-id="54444-133">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="54444-134">Microsoft 365 Business のトレーニング ビデオ</span><span class="sxs-lookup"><span data-stu-id="54444-134">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
