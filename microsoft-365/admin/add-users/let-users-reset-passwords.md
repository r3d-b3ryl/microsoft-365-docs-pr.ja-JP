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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: セルフサービス のパスワードリセット ツールを使用して、ユーザーが自分のパスワードをリセットできるポリシーを設定する方法について学習します。
ms.openlocfilehash: ac6d7f16cb35cec757340a94c262c3541bea927a
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394317"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="73bea-103">ユーザーが自分でパスワードをリセットできるようにする</span><span class="sxs-lookup"><span data-stu-id="73bea-103">Let users reset their own passwords</span></span>

<span data-ttu-id="73bea-104">管理者Microsoft 365、ユーザーがセルフサービス のパスワードリセット ツールを使用[](https://go.microsoft.com/fwlink/p/?LinkId=522677)して、パスワードをリセットする必要がなさそう。</span><span class="sxs-lookup"><span data-stu-id="73bea-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="73bea-105">仕事が少ない!</span><span class="sxs-lookup"><span data-stu-id="73bea-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="73bea-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="73bea-106">Before you begin</span></span>
  
- <span data-ttu-id="73bea-107">クラウド ユーザーのセルフサービス パスワード リセットは、ビジネス、教育、または非営利の有料プランMicrosoft 365無料で取得できます。</span><span class="sxs-lookup"><span data-stu-id="73bea-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="73bea-108">この機能は、試用版ではMicrosoft 365しません。</span><span class="sxs-lookup"><span data-stu-id="73bea-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="73bea-p103">この操作には Azure を使用します。これらの手順を行うときに、自動的に **無料** で Azure にあるこの機能を取得できます。その他の Azure 機能を使用しない場合は、セルフサービスによるパスワード リセットをオンにするために費用はかかりません。</span><span class="sxs-lookup"><span data-stu-id="73bea-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="73bea-112">**オンプレミスの Active Directory を使用** している場合、上記の 2 つの点は適用されません。</span><span class="sxs-lookup"><span data-stu-id="73bea-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="73bea-113">むしろ、これを設定できますが、この設定には有料サブスクリプションが **必要** Azure AD Premium。</span><span class="sxs-lookup"><span data-stu-id="73bea-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="73bea-114">この記事は、職場、学校、または非営利団体のパスワードの有効期限ポリシーを設定する管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="73bea-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="73bea-115">これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="73bea-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="73bea-116">管理者アカウントとは</span><span class="sxs-lookup"><span data-stu-id="73bea-116">What's an admin account?</span></span>](../../business-video/admin-center-overview.md)

<span data-ttu-id="73bea-117">これらの手順を実行するには [、グローバル管理者またはパスワード](about-admin-roles.md) 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="73bea-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="73bea-118">ウォッチ: ユーザーが自分のパスワードをリセットする</span><span class="sxs-lookup"><span data-stu-id="73bea-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="73bea-119">このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](../../business-video/index.yml)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="73bea-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="73bea-120">手順: ユーザーが自分のパスワードをリセットする</span><span class="sxs-lookup"><span data-stu-id="73bea-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="73bea-121">次の手順を行うと、社内のすべてのユーザーに対してセルフサービスによるパスワードのリセットがオンになります。</span><span class="sxs-lookup"><span data-stu-id="73bea-121">These steps turn on self-service password reset for everyone in your business.</span></span>

1. <span data-ttu-id="73bea-122">管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">で、[</a>組織の設定]**ページ設定**  >  **移動** します。</span><span class="sxs-lookup"><span data-stu-id="73bea-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

2. <span data-ttu-id="73bea-123">[組織の設定] ページ **の上部で** 、[セキュリティ] タブ **&選択** します。</span><span class="sxs-lookup"><span data-stu-id="73bea-123">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="73bea-124">[セルフサービス **パスワードのリセット] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73bea-124">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="73bea-125">[ **セルフサービス パスワードのリセット] で**、[Azure portal に移動] を選択してセルフサービス **パスワードのリセットを有効にします**。</span><span class="sxs-lookup"><span data-stu-id="73bea-125">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="73bea-126">左側のナビゲーション ウィンドウで、[ **ユーザー**] を選択し、[ユーザー] ウィンドウ **で [ユーザー] |[すべてのユーザー]** ページで、[パスワードの **リセット] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73bea-126">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="73bea-127">[プロパティ **] ページで** 、[ **すべて** ] を選択して、ビジネスのすべてのユーザーに対して有効にし、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="73bea-127">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="73bea-128">ユーザーがサインインすると、今後のパスワードのリセットに役立つ追加情報を入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="73bea-128">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="73bea-129">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="73bea-129">Related content</span></span>

<span data-ttu-id="73bea-130">[組織のパスワード有効期限ポリシーを設定する](../manage/set-password-expiration-policy.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="73bea-130">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>\
<span data-ttu-id="73bea-131">[個別のユーザーのパスワードを無期限に設定する](set-password-to-never-expire.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="73bea-131">[Set an individual user's password to never expire](set-password-to-never-expire.md) (article)</span></span>\
<span data-ttu-id="73bea-132">[Microsoft 365 ビジネス トレーニング ビデオ](../../business-video/index.yml)(リンク ページ)</span><span class="sxs-lookup"><span data-stu-id="73bea-132">[Microsoft 365 Business training videos](../../business-video/index.yml) (link page)</span></span>
