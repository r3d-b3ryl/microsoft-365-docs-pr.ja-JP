---
title: Office 365 ユーザー用の多要素認証を設定する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: セキュリティの既定値を使用して Office 365 ユーザー用の多要素認証を設定する方法について説明します。
monikerRange: o365-worldwide
ms.openlocfilehash: 4dc52c25c3a9351be1a9f4d094d664bc4ed527f9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361048"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="a08e1-103">多要素認証をセットアップする</span><span class="sxs-lookup"><span data-stu-id="a08e1-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="a08e1-104">新しい法人向け Office 365 または Microsoft 365 Business のすべてのサブスクリプションは、自動的にセキュリティの既定値が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a08e1-104">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="a08e1-105">つまり、すべてのユーザーが多要素認証 (MFA) を設定し、モバイル デバイスに Authenticator アプリをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a08e1-105">This means that every user will have to set up multi-factor authentication (MFA) and install the Authenticator app on their mobile device.</span></span> <span data-ttu-id="a08e1-106">詳細については、「[Office 365 で 2 段階認証をセットアップする](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a08e1-106">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="a08e1-107">サインインするたびに追加の認証を実行するには、次にあげる 9 個の管理者ロールが必要になります。</span><span class="sxs-lookup"><span data-stu-id="a08e1-107">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>
- <span data-ttu-id="a08e1-108">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="a08e1-108">Global administrator</span></span>
- <span data-ttu-id="a08e1-109">SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="a08e1-109">SharePoint administrator</span></span>
- <span data-ttu-id="a08e1-110">Exchange 管理者</span><span class="sxs-lookup"><span data-stu-id="a08e1-110">Exchange administrator</span></span>
- <span data-ttu-id="a08e1-111">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="a08e1-111">Conditional Access administrator</span></span>
- <span data-ttu-id="a08e1-112">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="a08e1-112">Security administrator</span></span>
- <span data-ttu-id="a08e1-113">ヘルプデスク管理者/パスワード管理者</span><span class="sxs-lookup"><span data-stu-id="a08e1-113">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="a08e1-114">課金管理者</span><span class="sxs-lookup"><span data-stu-id="a08e1-114">Billing administrator</span></span>
- <span data-ttu-id="a08e1-115">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="a08e1-115">User administrator</span></span>
- <span data-ttu-id="a08e1-116">認証管理者</span><span class="sxs-lookup"><span data-stu-id="a08e1-116">Authentication administrator</span></span>

<span data-ttu-id="a08e1-117">他のすべてのユーザーは、必要に応じて追加認証を求められます。</span><span class="sxs-lookup"><span data-stu-id="a08e1-117">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="a08e1-118">詳細については、「[セキュリティの既定値とは](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a08e1-118">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

> [!NOTE]
> <span data-ttu-id="a08e1-p103">多要素認証を設定または変更するには、Office 365 のグローバル管理者である必要があります。 </span><span class="sxs-lookup"><span data-stu-id="a08e1-p103">You must be an Office 365 global admin to set up or modify multi-factor authentication. </span></span><br><br>
> <span data-ttu-id="a08e1-120">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a08e1-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="a08e1-121">以前にベースライン ポリシーを使用して MFA をセットアップしている場合は、[それらをオフにして、セキュリティの既定値をオンにする必要があります](#move-from-baseline-policies-to-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="a08e1-121">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="a08e1-122">ただし、Microsoft 365 Business を所有している場合、またはサブスクリプションに [Azure Active Directory Premium 1、または Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/) が含まれている場合は、[条件付きアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) ポリシーを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a08e1-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium 1, or Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="a08e1-123">条件付きアクセス ポリシーを使用するには、[先進認証が有効になっていること](#enable-multi-factor-authentication-for-your-organization)を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a08e1-123">To use conditional access policies, you need to make sure [modern authentication is enabled](#enable-multi-factor-authentication-for-your-organization).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="a08e1-124">セキュリティの既定値の管理</span><span class="sxs-lookup"><span data-stu-id="a08e1-124">Manage security defaults</span></span>

1. <span data-ttu-id="a08e1-125">グローバル管理者の資格情報を使用して、[管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="a08e1-125">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="a08e1-126">[Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a08e1-126">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>

3. <span data-ttu-id="a08e1-127">ページの下部で、[**セキュリティの既定値の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a08e1-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="a08e1-128">セキュリティの規定値を有効にするには [**はい**] を選択し、セキュリティの規定値を無効にするには [**いいえ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a08e1-128">Choose **Yes** to enable security defaults and **No** to disable security defaults.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="a08e1-129">ベースライン ポリシーからセキュリティの既定値に移行する</span><span class="sxs-lookup"><span data-stu-id="a08e1-129">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="a08e1-130">[管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)で、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a08e1-130">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="a08e1-131">[**サインインとセキュリティ**] の横の [**サインインのセキュリティを強化する**] で [**表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a08e1-131">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="a08e1-132">[**サインインのセキュリティを強化する**] で、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a08e1-132">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="a08e1-133">[**Azure portal 条件付きアクセス - ポリシー**] ページで、[**オン**]になっているベースライン ポリシーをそれぞれ選び、[**オフ**]に設定します。</span><span class="sxs-lookup"><span data-stu-id="a08e1-133">On the **Azure portal Conditional Access - Policies** page,  choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="a08e1-134">[[Azure Active Directory のプロパティ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)] ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a08e1-134">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="a08e1-135">ページの下部で、[**セキュリティの既定値の管理**]を選択し、[**セキュリティの既定値の有効化**] ウィンドウで、[**Enable Security defaults (セキュリティの規定値を有効にする)**] トグルを [**はい**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="a08e1-135">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="a08e1-136">組織の先進認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="a08e1-136">Enable Modern authentication for your organization</span></span>

<span data-ttu-id="a08e1-137">Office 2016 のクライアント アプリケーションはすべて、Active Directory Authentication Library (ADAL) を使用して MFA をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a08e1-137">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="a08e1-138">つまり、Office 2016 クライアントでは、アプリ パスワードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a08e1-138">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="a08e1-139">ただし、Office 365 サブスクリプションが ADAL または先進認証に対して有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a08e1-139">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="a08e1-140">先進認証を有効にするには、[管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)で **[設定]** \> **[設定]** の順に選択し、次に **[サービス]** タブのリストから **[先進認証]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a08e1-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="a08e1-141">[**先進認証**] パネルの [**先進認証を有効にする**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a08e1-141">Check the **Enable modern authentication** box in the **Modern authentication** panel.</span></span> 

    ![チェックボックスをオンにした状態の [先進認証] パネル](../../media/enablemodernauth.png)
    
## <a name="enable-multi-factor-authentication-for-your-organization"></a><span data-ttu-id="a08e1-143">組織の多要素認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="a08e1-143">Enable multi-factor authentication for your organization</span></span>
    
1. <span data-ttu-id="a08e1-144">[管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)で、[**ユーザー** ] および [**アクティブなユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a08e1-144">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Users** and **Active Users**.</span></span>

2. <span data-ttu-id="a08e1-145">[**アクティブなユーザー** ] セクションで、[**多要素認証**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a08e1-145">In the **Active Users** section, Click on  **multi-factor authentication**.</span></span>

3. <span data-ttu-id="a08e1-146">[**多要素認証**] ページで、この設定を1人のユーザーに対して有効にする場合は [**ユーザー** ] を選択し、複数のユーザーを有効にする場合は [**一括更新**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a08e1-146">On the **Multi-factor authentication** page, select **user** if you are enabling this for one user or select **Bulk Update** to enable multiple users.</span></span>

4. <span data-ttu-id="a08e1-147">**クイック操作**の下にある [**有効化**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a08e1-147">CLick on **Enable** under **Quick Steps**.</span></span>

5. <span data-ttu-id="a08e1-148">ポップアップウィンドウで、[**多要素認証を有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a08e1-148">In the Pop-up window, Click on **Enable Multi-Factor Authentication**.</span></span>

<span data-ttu-id="a08e1-149">組織に多要素認証を設定した後、ユーザーはデバイスに 2 段階認証を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a08e1-149">After you set up multi-factor authentication for your organization, your users will be required to set up two-step verification on their devices.</span></span> <span data-ttu-id="a08e1-150">詳細については、「[Office 365 で 2 段階認証をセットアップする](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a08e1-150">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>
    
> [!TIP]
> <span data-ttu-id="a08e1-151">ユーザーに Authenticator アプリをセットアップする方法を説明するには、「[Office 365 で Microsoft Authenticator を使用する](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a08e1-151">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a08e1-152">2017 年 8 月に、Skype for Business Online と Exchange Online を含むすべての新しい Office 365 テナントには、既定で先進認証が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a08e1-152">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="a08e1-153">Skype for Business Online の先進認証状態を確認するには、グローバル管理者の資格情報を使用して Skype for Business Online PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="a08e1-153">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="a08e1-154">Get-CsOAuthConfiguration を実行して、-ClientADALAuthOverride の出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="a08e1-154">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="a08e1-155">-ClientADALAuthOverride が「許可」の場合は、先進認証が有効になります。</span><span class="sxs-lookup"><span data-stu-id="a08e1-155">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="a08e1-156">Exchange Online の MA 状態を確認するには、「[Exchange Online で先進認証を有効にする](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a08e1-156">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="a08e1-157">関連記事</span><span class="sxs-lookup"><span data-stu-id="a08e1-157">Related articles</span></span>

[<span data-ttu-id="a08e1-158">Office 365とMicrosoft 365 Businessプランを安全にする10の方法</span><span class="sxs-lookup"><span data-stu-id="a08e1-158">Top 10 ways to secure Office 365 and Microsoft 365 Business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="a08e1-159">Windows デバイスの Office 2013 の先進認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="a08e1-159">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
