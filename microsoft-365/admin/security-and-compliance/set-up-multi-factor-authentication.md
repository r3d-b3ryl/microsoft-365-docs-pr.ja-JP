---
title: ユーザーの多要素認証を設定する
f1.keywords:
- NOCSH
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 組織向けに多要素認証を設定する方法について説明します。
monikerRange: o365-worldwide
ms.openlocfilehash: 7ee6f3a7fc01fa998e3b984683ddad1402fe5587
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393621"
---
# <a name="set-up-multifactor-authentication"></a><span data-ttu-id="d86a2-103">多要素認証を設定する</span><span class="sxs-lookup"><span data-stu-id="d86a2-103">Set up multifactor authentication</span></span>

<span data-ttu-id="d86a2-104">[多要素認証 (MFA) および Microsoft 365 のサポート](multi-factor-authentication-microsoft-365.md)を理解して、多要素認証を組織に設定し、展開します。</span><span class="sxs-lookup"><span data-stu-id="d86a2-104">Based on your understanding of [multifactor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it's time to set it up and roll it out to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d86a2-105">2019 年 10 月 21 日以降にサブスクリプションまたは試用版を購入した場合、サインインすると MFA を要求するメッセージが表示され、[セキュリティの既定](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)の設定は、サブスクリプションに対して自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="d86a2-105">If you purchased your subscription or trial after October 21, 2019, and you're prompted for MFA when you sign in, [security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d86a2-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="d86a2-106">Before you begin</span></span>

- <span data-ttu-id="d86a2-107">MFA を管理するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d86a2-107">You must be a Global admin to manage MFA.</span></span> <span data-ttu-id="d86a2-108">詳細については、「[管理者の役割について](../add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d86a2-108">For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="d86a2-109">従来のユーザーごとの MFA をオンにしている場合は、[従来のユーザーごとの MFA をオフにします](#turn-off-legacy-per-user-mfa)。</span><span class="sxs-lookup"><span data-stu-id="d86a2-109">If you have legacy per-user MFA turned on, [Turn off legacy per-user MFA](#turn-off-legacy-per-user-mfa).</span></span>
- <span data-ttu-id="d86a2-110">Windows デバイスで Office 2013 クライアントを使用している場合は、[Office 2013 クライアントの最新のライセンス認証をオンにします](./enable-modern-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="d86a2-110">If you have Office 2013 clients on Windows devices, [turn on Modern Authentication for Office 2013 clients](./enable-modern-authentication.md).</span></span>
- <span data-ttu-id="d86a2-111">高度: Active Directory フェデレーション サービス (AD FS) を使用しているサードパーティのディレクトリ サービスがある場合は、Azure MFA Server をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="d86a2-111">Advanced: If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="d86a2-112">詳細については、「[Azure AD Multifactor Authentication およびサード パーティ製 VPN ソリューションでの高度なシナリオ](/azure/active-directory/authentication/howto-mfaserver-nps-vpn)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d86a2-112">See [advanced scenarios with Azure AD Multifactor Authentication and third-party VPN solutions](/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="turn-security-defaults-on-or-off"></a><span data-ttu-id="d86a2-113">セキュリティの既定値をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="d86a2-113">Turn Security defaults on or off</span></span>

<span data-ttu-id="d86a2-114">ほとんどの組織では、セキュリティの既定値により、適切なレベルのサインイン セキュリティが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d86a2-114">For most organizations, Security defaults offer a good level of additional sign-in security.</span></span> <span data-ttu-id="d86a2-115">詳細については、[「セキュリティの既定値とは?」](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d86a2-115">For more information, see [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="d86a2-116">サブスクリプションが新しい場合は、セキュリティの既定値が自動的にオンになります。</span><span class="sxs-lookup"><span data-stu-id="d86a2-116">If your subscription is new, Security defaults might already be turned on for you automatically.</span></span>

<span data-ttu-id="d86a2-117">Azure ポータル内の Azure Active Directory (Azure AD) の **プロパティ** ウィンドウで、セキュリティの既定値を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="d86a2-117">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1. <span data-ttu-id="d86a2-118">グローバル管理者の資格情報を使用して、[MIcrosoft 365 管理センター](https://admin.microsoft.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d86a2-118">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2. <span data-ttu-id="d86a2-119">左側のナビゲーションで、**[すべて表示]** を選択し、**[管理センター]** の **[Azure Active Directory]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d86a2-119">In the left nav choose **Show All** and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="d86a2-120">**Azure Active Directory 管理センター** で、**[Azure Active Directory]** \> **[プロパティ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d86a2-120">In the **Azure Active Directory admin center** choose **Azure Active Directory** \> **Properties**.</span></span>
4. <span data-ttu-id="d86a2-121">ページの下部で、**[セキュリティの既定値の管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d86a2-121">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="d86a2-122">セキュリティの規定値を有効にするには **[はい]** を選び、セキュリティの規定値を無効にするには **[いいえ]** を選んで、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d86a2-122">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="d86a2-123">[条件付きアクセスのベースライン ポリシー](/azure/active-directory/conditional-access/concept-baseline-protection) を使用している場合は、セキュリティの既定値の使用に移行する前に、オフにするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d86a2-123">If you have been using [baseline Conditional Access policies](/azure/active-directory/conditional-access/concept-baseline-protection), you will be prompted to turn them off before you move to using security defaults.</span></span>

1. <span data-ttu-id="d86a2-124">[条件付きアクセス ポリシー ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) へ移動します。</span><span class="sxs-lookup"><span data-stu-id="d86a2-124">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="d86a2-125">各ベースライン ポリシーで [**オン**] を選択し、 [**ポリシーを有効にする**] を [**オフ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="d86a2-125">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="d86a2-126">[[Azure Active Directory] のプロパティ ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d86a2-126">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="d86a2-127">ページの下部で、[**セキュリティの既定値の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d86a2-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="d86a2-128">セキュリティの規定値を有効にするには [**はい**] を選び、セキュリティの規定値を無効にするには [**いいえ**] を選んで [**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d86a2-128">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="use-conditional-access-policies"></a><span data-ttu-id="d86a2-129">条件付きアクセス ポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="d86a2-129">Use Conditional Access policies</span></span>

<span data-ttu-id="d86a2-130">より細かいサインイン セキュリティを必要としている組織の場合、条件付きアクセス ポリシーを使用すると、より詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="d86a2-130">If your organization has more granular sign-in security needs, Conditional Access policies can offer you more control.</span></span> <span data-ttu-id="d86a2-131">条件付きアクセスを使用すると、ユーザーがアプリケーションまたはサービスへのアクセスを許可される前に、サインイン イベントに反応し、追加のアクションを要求するポリシーを作成し定義できます。</span><span class="sxs-lookup"><span data-stu-id="d86a2-131">Conditional Access lets you create and define policies that react to sign in events and request additional actions before a user is granted access to an application or service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d86a2-132">条件付きアクセス ポリシーを有効にする前に、ユーザーごとの MFA とセキュリティの既定値をオフにします。</span><span class="sxs-lookup"><span data-stu-id="d86a2-132">Turn off both per-user MFA and Security defaults before you enable Conditional Access policies.</span></span>

<span data-ttu-id="d86a2-133">条件付きアクセスを利用できるのは、Azure AD Premium P1 を購入したお客様、またはこの機能を含むライセンス (Microsoft 365 Business Premium、Microsoft 365 E3 など) を購入したお客様です。</span><span class="sxs-lookup"><span data-stu-id="d86a2-133">Conditional Access is available for customers who have purchased Azure AD Premium P1, or licenses that include this, such as Microsoft 365 Business Premium, and Microsoft 365 E3.</span></span> <span data-ttu-id="d86a2-134">詳細については、[「条件付きアクセス ポリシーを作成する」](/azure/active-directory/authentication/tutorial-enable-azure-mfa) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d86a2-134">For more information, see [create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span></span>

<span data-ttu-id="d86a2-135">リスクベースの条件付きアクセスは、Azure AD Premium P2 ライセンスを通して、またはこの機能を含むライセンス (Microsoft 365 E5 など) を通じて利用できます。</span><span class="sxs-lookup"><span data-stu-id="d86a2-135">Risk-based conditional access is available through Azure AD Premium P2 license, or licenses that include this, such as Microsoft 365 E5.</span></span> <span data-ttu-id="d86a2-136">詳細については、[「リスクベースの条件付きアクセス」](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d86a2-136">For more information, see [risk-based Conditional Access](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span></span>

<span data-ttu-id="d86a2-137">Azure AD P1 および P2 の詳細については、「[Azure Active Directory の料金](https://azure.microsoft.com/pricing/details/active-directory/)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d86a2-137">For more information about the Azure AD P1 and P2, see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="turn-on-modern-authentication-for-your-organization"></a><span data-ttu-id="d86a2-138">組織の先進認証をオンにする</span><span class="sxs-lookup"><span data-stu-id="d86a2-138">Turn on Modern authentication for your organization</span></span>

<span data-ttu-id="d86a2-139">ほとんどのサブスクリプションでは、先進認証が自動的にオンになりますが、2017 年 8 月より前にサブスクリプションを購入した場合、多要素認証などの機能を Outlook などの Windows クライアントで機能させるには、先進認証をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d86a2-139">For most subscriptions modern authentication is automatically turned on, but if you purchased your subscription before August 2017, it is likely that you will need to turn on Modern Authentication in order to get features like Multifactor Authentication to work in Windows clients like Outlook.</span></span>


1. <span data-ttu-id="d86a2-140">Microsoft 365 管理センターで、左側のナビゲーションの **[設定]** \> **[組織の設定]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d86a2-140">In the Microsoft 365 admin center, in the left nav choose **Settings** \> **Org settings**.</span></span>
2. <span data-ttu-id="d86a2-141">**[サービス]** タブで、**[先進認証]** を選択し、**[先進認証]** ウィンドウで、**[先進認証を有効にする]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d86a2-141">Under the **Services** tab, choose **Modern authentication**, and in the **Modern authentication** pane, make sure **Enable Modern authentication** is selected.</span></span> <span data-ttu-id="d86a2-142">**[変更の保存]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="d86a2-142">Choose **Save changes**.</span></span>

### <a name="turn-off-legacy-per-user-mfa"></a><span data-ttu-id="d86a2-143">従来のユーザーごとの MFA をオフにする</span><span class="sxs-lookup"><span data-stu-id="d86a2-143">Turn off legacy per-user MFA</span></span>

<span data-ttu-id="d86a2-144">以前にユーザーごとの MFA をオンにしている場合は、セキュリティの既定値が有効になる前にオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d86a2-144">If you have previously turned on per-user MFA, you must turn it off before enabling Security defaults.</span></span>

1. <span data-ttu-id="d86a2-145">Microsoft 365 管理センターで、左側のナビゲーションの **[ユーザー]** \> **[アクティブ ユーザー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d86a2-145">In the Microsoft 365 admin center, in the left nav choose **Users** \> **Active users**.</span></span>
1. <span data-ttu-id="d86a2-146">**[アクティブ ユーザー]** ページで、**[多要素認証]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d86a2-146">On the **Active users** page, choose **Multi-factor authentication**.</span></span>
1. <span data-ttu-id="d86a2-147">多要素認証ページで、各ユーザーを選択し、その多要素認証ステータスを **[無効]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="d86a2-147">On the multi-factor authentication page, select each user and set their Multi-Factor auth status to **Disabled**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d86a2-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="d86a2-148">Next steps</span></span>

- [<span data-ttu-id="d86a2-149">追加の検証手法を登録する方法</span><span class="sxs-lookup"><span data-stu-id="d86a2-149">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="d86a2-150">機能: 多要素認証</span><span class="sxs-lookup"><span data-stu-id="d86a2-150">What is: Multifactor Authentication</span></span>](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [<span data-ttu-id="d86a2-151">登録後のサインインの方法</span><span class="sxs-lookup"><span data-stu-id="d86a2-151">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="d86a2-152">追加の検証手法を変更する方法</span><span class="sxs-lookup"><span data-stu-id="d86a2-152">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)

## <a name="related-content"></a><span data-ttu-id="d86a2-153">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="d86a2-153">Related content</span></span>

<span data-ttu-id="d86a2-154">[多要素認証をオンにする](../../business-video/turn-on-mfa.md) (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="d86a2-154">[Turn on multifactor authentication](../../business-video/turn-on-mfa.md) (video)</span></span>\
<span data-ttu-id="d86a2-155">[スマートフォンの多要素認証をオンにする](../../business-video/set-up-mfa.md) (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="d86a2-155">[Turn on multifactor authentication for your phone](../../business-video/set-up-mfa.md) (video)</span></span>