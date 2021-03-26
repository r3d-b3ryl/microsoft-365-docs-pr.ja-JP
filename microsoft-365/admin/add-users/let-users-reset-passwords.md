---
title: ユーザーが自分でパスワードをリセットできるようにする
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: セルフサービス のパスワード リセット ツールを使用してパスワードをリセットする方法について学習します。
ms.openlocfilehash: f43c409e98aa98e942bd7c7cbb15302422df241d
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222125"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="0751c-103">ユーザーが自分でパスワードをリセットできるようにする</span><span class="sxs-lookup"><span data-stu-id="0751c-103">Let users reset their own passwords</span></span>

<span data-ttu-id="0751c-104">Microsoft 365 管理者は、セルフサービス のパスワード[](https://go.microsoft.com/fwlink/p/?LinkId=522677)リセット ツールを使用して、パスワードをリセットする必要がなさそう。</span><span class="sxs-lookup"><span data-stu-id="0751c-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="0751c-105">仕事が少ない!</span><span class="sxs-lookup"><span data-stu-id="0751c-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="0751c-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="0751c-106">Before you begin</span></span>
  
- <span data-ttu-id="0751c-107">Microsoft 365 のビジネス、教育、または非営利の有料プランで、クラウド ユーザーのセルフサービス パスワードリセットを無料で受け取る。</span><span class="sxs-lookup"><span data-stu-id="0751c-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="0751c-108">Microsoft 365 試用版では動作しません。</span><span class="sxs-lookup"><span data-stu-id="0751c-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="0751c-p103">この操作には Azure を使用します。これらの手順を行うときに、自動的に **無料** で Azure にあるこの機能を取得できます。その他の Azure 機能を使用しない場合は、セルフサービスによるパスワード リセットをオンにするために費用はかかりません。</span><span class="sxs-lookup"><span data-stu-id="0751c-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="0751c-112">**オンプレミスの Active Directory を使用** している場合、上記の 2 つの点は適用されません。</span><span class="sxs-lookup"><span data-stu-id="0751c-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="0751c-113">むしろ、これを設定できますが、 **有料のサブスクリプションが必要** です Azure AD Premium .</span><span class="sxs-lookup"><span data-stu-id="0751c-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="0751c-114">この記事は、職場、学校、または非営利団体のパスワードの有効期限ポリシーを設定する管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="0751c-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="0751c-115">これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0751c-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="0751c-116">管理者アカウントとは</span><span class="sxs-lookup"><span data-stu-id="0751c-116">What's an admin account?</span></span>](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview)

<span data-ttu-id="0751c-117">これらの手順を実行するには [、グローバル管理者またはパスワード](about-admin-roles.md) 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0751c-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="0751c-118">ウォッチ: ユーザーが自分のパスワードをリセットする</span><span class="sxs-lookup"><span data-stu-id="0751c-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="0751c-119">このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0751c-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="0751c-120">手順: ユーザーが自分のパスワードをリセットする</span><span class="sxs-lookup"><span data-stu-id="0751c-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="0751c-121">次の手順を行うと、社内のすべてのユーザーに対してセルフサービスによるパスワードのリセットがオンになります。</span><span class="sxs-lookup"><span data-stu-id="0751c-121">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="0751c-122">管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">で、[</a>設定組織の設定 **]** > **ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="0751c-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0751c-123">管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">で、[</a>設定セキュリティのプライバシー **]** \> **ページ &amp; に移動** します。</span><span class="sxs-lookup"><span data-stu-id="0751c-123">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0751c-124">管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">で、[</a>設定] [セキュリティのプライバシー **]** \>  \> **ページ &amp; に移動** します。</span><span class="sxs-lookup"><span data-stu-id="0751c-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="0751c-125">[組織の設定] ページ **の上部で** 、[セキュリティ] タブ **&選択** します。</span><span class="sxs-lookup"><span data-stu-id="0751c-125">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="0751c-126">[セルフサービス **パスワードのリセット] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0751c-126">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="0751c-127">[ **セルフサービス パスワードのリセット] で**、[Azure portal に移動] を選択してセルフサービス **パスワードのリセットを有効にします**。</span><span class="sxs-lookup"><span data-stu-id="0751c-127">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="0751c-128">左側のナビゲーション ウィンドウで、[ **ユーザー**] を選択し、[ユーザー] ウィンドウ **で [ユーザー] |[すべてのユーザー]** ページで、[パスワードの **リセット] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0751c-128">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="0751c-129">[プロパティ **] ページで** 、[ **すべて** ] を選択して、ビジネスのすべてのユーザーに対して有効にし、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0751c-129">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="0751c-130">ユーザーがサインインすると、今後のパスワードのリセットに役立つ追加情報を入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="0751c-130">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="0751c-131">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="0751c-131">Related content</span></span>

[<span data-ttu-id="0751c-132">組織のパスワード有効期限ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="0751c-132">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)

[<span data-ttu-id="0751c-133">有効期限が切れないように個別のユーザーのパスワードを設定する</span><span class="sxs-lookup"><span data-stu-id="0751c-133">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="0751c-134">Microsoft 365 Business のトレーニング ビデオ</span><span class="sxs-lookup"><span data-stu-id="0751c-134">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
