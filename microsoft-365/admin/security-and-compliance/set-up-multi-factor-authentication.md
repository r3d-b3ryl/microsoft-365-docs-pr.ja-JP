---
title: ユーザーの多要素認証を設定する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 組織向けに多要素認証を設定する方法について説明します。
monikerRange: o365-worldwide
ms.openlocfilehash: 34133f4204c1ee305b0a249a0ff8e0e9edaf5599
ms.sourcegitcommit: e891c7c25f351f10f250af3f483f68594976ddc9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "45153679"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="f47ab-103">多要素認証をセットアップする</span><span class="sxs-lookup"><span data-stu-id="f47ab-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="f47ab-104">[多要素認証 (MFA) を理解し、Microsoft 365でサポートされていること](multi-factor-authentication-microsoft-365.md) を理解したら、それを設定し、組織にロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="f47ab-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f47ab-105">2019 年 10 月 21 日以降にサブスクリプションまたは試用版を購入した場合、サインインすると MFA を要求するメッセージが表示され、[セキュリティの既定](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) の設定は、サブスクリプションに対して自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="f47ab-105">If you purchased your subscription or trial after October 21, 2019, and you're prompted for MFA when you sign in, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="f47ab-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="f47ab-106">Before you begin</span></span>

- <span data-ttu-id="f47ab-107">MFA を管理するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f47ab-107">You must be a Global admin to manage MFA.</span></span> <span data-ttu-id="f47ab-108">詳細については、[「管理者ロールについて」](../add-users/about-admin-roles.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f47ab-108">For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="f47ab-109">個人のレガシー MFA をオンにしている場合は、[個人のレガシー MFA をオフにします](#turn-off-legacy-per-person-mfa)。</span><span class="sxs-lookup"><span data-stu-id="f47ab-109">If you have legacy per person MFA turned on, [Turn off legacy per person MFA](#turn-off-legacy-per-person-mfa).</span></span>
- <span data-ttu-id="f47ab-110">Windows デバイスで Office 2013 クライアントを使用している場合は、[Office 2013 クライアントの最新のライセンス認証をオンに します](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)。</span><span class="sxs-lookup"><span data-stu-id="f47ab-110">If you have Office 2013 clients on Windows devices, [turn on Modern Authentication for Office 2013 clients](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>
- <span data-ttu-id="f47ab-111">高度: Active Directory フェデレーション サービス (AD FS) を使用しているサードパーティ ディレクトリ サービスがある場合は、Azure MFA サーバーをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="f47ab-111">Advanced: If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="f47ab-112">詳細については、「[Azure Multi-Factor Authentication およびサードパーティ製の VPN ソリューションでの高度なシナリオ](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f47ab-112">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="turn-security-defaults-on-or-off"></a><span data-ttu-id="f47ab-113">セキュリティの既定値をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="f47ab-113">Turn Security defaults on or off</span></span>

<span data-ttu-id="f47ab-114">ほとんどの組織では、セキュリティの既定値により、適切なレベルのサインイン セキュリティが提供されます。</span><span class="sxs-lookup"><span data-stu-id="f47ab-114">For most organizations, Security defaults offer a good level of additional sign-in security.</span></span> <span data-ttu-id="f47ab-115">詳細については、[「セキュリティの既定値とは?」](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f47ab-115">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="f47ab-116">サブスクリプションが新しい場合は、セキュリティの既定値が自動的にオンになります。</span><span class="sxs-lookup"><span data-stu-id="f47ab-116">If your subscription is new, Security defaults might already be turned on for you automatically.</span></span>

<span data-ttu-id="f47ab-117">Azure ポータル内の Azure Active Directory (Azure AD) の **プロパティ** ウィンドウで、セキュリティの既定値を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="f47ab-117">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="f47ab-118">グローバル管理者の資格情報を使用して、[MIcrosoft 365 管理センター](https://admin.microsoft.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f47ab-118">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="f47ab-119">左側のナビゲーションで、**[すべて表示]** を選択し、**[管理センター]** の **[Azure Active Directory]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f47ab-119">In the left nav choose **Show All** and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="f47ab-120">**Azure Active Directory 管理センター** で、**[Azure Active Directory]** > **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f47ab-120">In the **Azure Active Directory admin center** choose **Azure Active Directory** > **Properties**.</span></span>
3.  <span data-ttu-id="f47ab-121">ページの下部で、**[セキュリティの既定値の管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f47ab-121">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="f47ab-122">セキュリティの規定値を有効にするには **[はい]** を選び、セキュリティの規定値を無効にするには **[いいえ]** を選んで、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f47ab-122">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="f47ab-123">[条件付きアクセスのベースライン ポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection) を使用している場合は、セキュリティの既定値の使用に移行する前に、オフにするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f47ab-123">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), you will be prompted to turn them off before you move to using security defaults.</span></span>

1.  <span data-ttu-id="f47ab-124">[条件付きアクセス ポリシー ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) へ移動します。</span><span class="sxs-lookup"><span data-stu-id="f47ab-124">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="f47ab-125">各ベースライン ポリシーで [**オン**] を選択し、 [**ポリシーを有効にする**] を [**オフ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="f47ab-125">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="f47ab-126">[[Azure Active Directory] のプロパティ ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f47ab-126">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="f47ab-127">ページの下部で、[**セキュリティの既定値の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f47ab-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="f47ab-128">セキュリティの規定値を有効にするには [**はい**] を選び、セキュリティの規定値を無効にするには [**いいえ**] を選んで [**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f47ab-128">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="use-conditional-access-policies"></a><span data-ttu-id="f47ab-129">条件付きアクセス ポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="f47ab-129">Use Conditional Access policies</span></span>

<span data-ttu-id="f47ab-130">より細かいサインイン セキュリティを必要としている組織の場合、条件付きアクセス ポリシーを使用すると、より詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="f47ab-130">If your organization has more granular sign-in security needs, Conditional Access policies can offer you more control.</span></span> <span data-ttu-id="f47ab-131">条件付きアクセスを使用すると、ユーザーがアプリケーションまたはサービスへのアクセスを許可される前に、サインイン イベントに反応し、追加のアクションを要求するポリシーを作成し定義できます。</span><span class="sxs-lookup"><span data-stu-id="f47ab-131">Conditional Access lets you create and define policies that react to sign in events and request additional actions before a user is granted access to an application or service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f47ab-132">条件付きアクセス ポリシーを有効にする前に、個人の MFA とセキュリティの既定値をオフにします。</span><span class="sxs-lookup"><span data-stu-id="f47ab-132">Turn off both per person MFA and Security defaults before you enable Conditional Access policies.</span></span> 

<span data-ttu-id="f47ab-133">条件付きアクセスを利用できるのは、Azure AD Premium P1 を購入したお客様、またはこの機能を含むライセンス (Microsoft 365 Business Premium、Microsoft 365 E3 など) を購入したお客様です。</span><span class="sxs-lookup"><span data-stu-id="f47ab-133">Conditional Access is available for customers who have purchased Azure AD Premium P1, or licenses that include this, such as Microsoft 365 Business Premium, and Microsoft 365 E3.</span></span> <span data-ttu-id="f47ab-134">詳細については、[「条件付きアクセス ポリシーを作成する」](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f47ab-134">For more information, see [create a Conditional Access policy](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span></span>

<span data-ttu-id="f47ab-135">リスクベースの条件付きアクセスは、Azure AD Premium P2 ライセンスを通して、またはこの機能を含むライセンス (Microsoft 365 E5 など) を通じて利用できます。</span><span class="sxs-lookup"><span data-stu-id="f47ab-135">Risk-based conditional access is available through Azure AD Premium P2 license, or licences that include this, such as Microsoft 365 E5.</span></span> <span data-ttu-id="f47ab-136">詳細については、[「リスクベースの条件付きアクセス」](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f47ab-136">For more information, see [risk-based Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span></span>

<span data-ttu-id="f47ab-137">Azure AD P1 および P2 の詳細については、「[Azure Active Directory の料金](https://azure.microsoft.com/pricing/details/active-directory/)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f47ab-137">For more information about the Azure AD P1 and P2, see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="turn-on-modern-authentication-for-your-organization"></a><span data-ttu-id="f47ab-138">組織の先進認証をオンにする</span><span class="sxs-lookup"><span data-stu-id="f47ab-138">Turn on Modern authentication for your organization</span></span>

<span data-ttu-id="f47ab-139">ほとんどのサブスクリプションでは、先進認証が自動的にオンになりますが、サブスクリプションをずっと前に購入した場合は、オンにならない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f47ab-139">For most subscriptions modern authentication is automatically turned on, but if you purchased your subscription a long time ago, it might not be.</span></span> <span data-ttu-id="f47ab-140">Office アプリで MFA が適切に機能する前に、この機能をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f47ab-140">This has to be turned on before MFA works appropriately with Office apps.</span></span>

1. <span data-ttu-id="f47ab-141">Microsoft 365 管理センターで、左側のナビゲーションの **[設定]** > **[組織の設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f47ab-141">In the Microsoft 365 admin center, in the left nav choose **Settings** > **Org settings**.</span></span>
1. <span data-ttu-id="f47ab-142">**[サービス]** タブで、**[先進認証]** を選択し、**[先進認証]** ウィンドウで、**[先進認証を有効にする]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f47ab-142">Under **Services** tab, choose **Modern authentication**, and in the **Modern authentication** pane, make sure **Enable Modern authentication** is selected.</span></span> <span data-ttu-id="f47ab-143">**[変更の保存]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="f47ab-143">Choose **Save changes**.</span></span>

### <a name="turn-off-legacy-per-person-mfa"></a><span data-ttu-id="f47ab-144">個人のレガシー MFA をオフにする</span><span class="sxs-lookup"><span data-stu-id="f47ab-144">Turn off legacy per person MFA</span></span>

<span data-ttu-id="f47ab-145">以前に個人の MFA をオンにしている場合は、セキュリティの既定値が有効になる前にオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f47ab-145">If you have previously turned on per person MFA, you must turn it off before enabling Security defaults.</span></span>

1. <span data-ttu-id="f47ab-146">Microsoft 365 管理センターで、左側のナビゲーションの **[ユーザー]** > **[アクティブ ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f47ab-146">In the Microsoft 365 admin center, in the left nav choose **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="f47ab-147">**[アクティブ ユーザー]** ページで、**[多要素認証]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f47ab-147">On the **Active users** page, choose **Multi-factor authentication**.</span></span>
1. <span data-ttu-id="f47ab-148">多要素認証ページで、各ユーザーを選択し、その多要素認証ステータスを **[無効]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="f47ab-148">On the multi-factor authentication page, select each user and set their Multi-Factor auth status to **Disabled**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f47ab-149">次の手順</span><span class="sxs-lookup"><span data-stu-id="f47ab-149">Next steps</span></span>

- [<span data-ttu-id="f47ab-150">追加の検証手法を登録する方法</span><span class="sxs-lookup"><span data-stu-id="f47ab-150">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="f47ab-151">登録後のサインインの方法</span><span class="sxs-lookup"><span data-stu-id="f47ab-151">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="f47ab-152">追加の検証手法を変更する方法</span><span class="sxs-lookup"><span data-stu-id="f47ab-152">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="f47ab-153">新しいスマートフォンのような状況に対処する方法</span><span class="sxs-lookup"><span data-stu-id="f47ab-153">How to deal with situations like a new smart phone</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)
- [<span data-ttu-id="f47ab-154">MFA のサインインのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f47ab-154">Troubleshoot MFA sign-ins</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)




