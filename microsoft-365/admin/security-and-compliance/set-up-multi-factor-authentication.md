---
title: ユーザーに多要素認証をセットアップする
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
description: セキュリティの既定値を使用してユーザーに多要素認証を設定する方法について説明します。
monikerRange: o365-worldwide
ms.openlocfilehash: 4a829aa597596564b9c2f468e72f3a766b198372
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627682"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="33c4f-103">多要素認証をセットアップする</span><span class="sxs-lookup"><span data-stu-id="33c4f-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="33c4f-104">2019年10月21日以降にサブスクリプションまたは試用版を購入した場合に、MFA を予期せずに要求されると、サブスクリプションに対して[セキュリティの既定値](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="33c4f-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="33c4f-105">すべての新しい Microsoft 365 サブスクリプションのセキュリティの既定値が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="33c4f-105">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="33c4f-106">つまり、すべてのユーザーが多要素認証 (MFA) を設定し、モバイル デバイスに Authenticator アプリをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="33c4f-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Authenticator app on their mobile device.</span></span> <span data-ttu-id="33c4f-107">詳細については、「 [Microsoft 365 の2段階認証をセットアップする](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33c4f-107">For more information, see [Set up 2-step verification for Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="33c4f-108">サインインするたびに追加の認証を実行するには、次にあげる 9 個の管理者ロールが必要になります。</span><span class="sxs-lookup"><span data-stu-id="33c4f-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="33c4f-109">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="33c4f-109">Global administrator</span></span>
- <span data-ttu-id="33c4f-110">SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="33c4f-110">SharePoint administrator</span></span>
- <span data-ttu-id="33c4f-111">Exchange 管理者</span><span class="sxs-lookup"><span data-stu-id="33c4f-111">Exchange administrator</span></span>
- <span data-ttu-id="33c4f-112">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="33c4f-112">Conditional Access administrator</span></span>
- <span data-ttu-id="33c4f-113">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="33c4f-113">Security administrator</span></span>
- <span data-ttu-id="33c4f-114">ヘルプデスク管理者/パスワード管理者</span><span class="sxs-lookup"><span data-stu-id="33c4f-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="33c4f-115">課金管理者</span><span class="sxs-lookup"><span data-stu-id="33c4f-115">Billing administrator</span></span>
- <span data-ttu-id="33c4f-116">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="33c4f-116">User administrator</span></span>
- <span data-ttu-id="33c4f-117">認証管理者</span><span class="sxs-lookup"><span data-stu-id="33c4f-117">Authentication administrator</span></span>

<span data-ttu-id="33c4f-118">他のすべてのユーザーは、必要に応じて追加認証を求められます。</span><span class="sxs-lookup"><span data-stu-id="33c4f-118">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="33c4f-119">詳細については、「[セキュリティの既定値とは](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33c4f-119">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

> [!NOTE]
> <span data-ttu-id="33c4f-120">多要素認証を設定または変更するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="33c4f-120">You must be a global admin to set up or modify multi-factor authentication.</span></span> <br><br>
> <span data-ttu-id="33c4f-121">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="33c4f-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="33c4f-122">以前にベースライン ポリシーを使用して MFA をセットアップしている場合は、[それらをオフにして、セキュリティの既定値をオンにする必要があります](#move-from-baseline-policies-to-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="33c4f-122">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="33c4f-123">ただし、Microsoft 365 Business を所有している場合、またはサブスクリプションに [Azure Active Directory Premium 1、または Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/) が含まれている場合は、[条件付きアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) ポリシーを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="33c4f-123">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium 1, or Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="33c4f-124">条件付きアクセスポリシーを使用するには、[先進認証](#enable-modern-authentication-for-your-organization)が有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33c4f-124">To use conditional access policies, you need to make sure [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="33c4f-125">ユーザーに Authenticator アプリをセットアップする方法を説明するには、「[Office 365 で Microsoft Authenticator を使用する](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="33c4f-125">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="33c4f-126">セキュリティの既定値の管理</span><span class="sxs-lookup"><span data-stu-id="33c4f-126">Manage security defaults</span></span>

1. <span data-ttu-id="33c4f-127">グローバル管理者の資格情報を使用して、[管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="33c4f-127">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="33c4f-128">[Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="33c4f-128">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="33c4f-129">ページの下部で、[**セキュリティの既定値の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33c4f-129">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="33c4f-130">セキュリティの規定値を有効にするには [**はい**] を選択し、セキュリティの規定値を無効にするには [**いいえ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33c4f-130">Choose **Yes** to enable security defaults and **No** to disable security defaults.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="33c4f-131">ベースライン ポリシーからセキュリティの既定値に移行する</span><span class="sxs-lookup"><span data-stu-id="33c4f-131">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="33c4f-132">[管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)で、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33c4f-132">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="33c4f-133">[**サインインとセキュリティ**] の横の [**サインインのセキュリティを強化する**] で [**表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33c4f-133">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="33c4f-134">[**サインインのセキュリティを強化する**] で、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33c4f-134">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="33c4f-135">[**条件付きアクセスポリシー** ] ページで、にある各基準ポリシーを選択し、 **[\*\*\*\*オフ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="33c4f-135">On the **Conditional Access - Policies** page, choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="33c4f-136">[[Azure Active Directory のプロパティ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)] ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="33c4f-136">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="33c4f-137">ページの下部にある [セキュリティの**既定の管理**] をクリックし、[**セキュリティ**の既定値を有効にする] ウィンドウで、[**セキュリティの既定値を有効**にする] を [**はい**] に設定して、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33c4f-137">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="33c4f-138">組織の先進認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="33c4f-138">Enable modern authentication for your organization</span></span>

<span data-ttu-id="33c4f-139">Office 2016 のクライアント アプリケーションはすべて、Active Directory Authentication Library (ADAL) を使用して MFA をサポートします。</span><span class="sxs-lookup"><span data-stu-id="33c4f-139">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="33c4f-140">つまり、Office 2016 クライアントでは、アプリ パスワードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="33c4f-140">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="33c4f-141">ただし、Microsoft 365 サブスクリプションが ADAL に対して有効になっていること、または先進認証が有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33c4f-141">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="33c4f-142">先進認証を有効にするには、[管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)で **[設定]** \> **[設定]** の順に選択し、次に **[サービス]** タブのリストから **[先進認証]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33c4f-142">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="33c4f-143">**モダン認証**パネルの [**モダン認証を有効にする (推奨)** ] チェックボックスをオンにし、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33c4f-143">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![チェックボックスをオンにした状態の [先進認証] パネル](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="33c4f-145">2017年8月現在、Skype for Business online と Exchange online を含むすべての新しい Microsoft 365 サブスクリプションでは、先進認証が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="33c4f-145">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="33c4f-146">Skype for Business Online の先進認証状態を確認するには、グローバル管理者の資格情報を使用して Skype for Business Online PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="33c4f-146">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="33c4f-147">Get-CsOAuthConfiguration を実行して、-ClientADALAuthOverride の出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="33c4f-147">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="33c4f-148">-ClientADALAuthOverride が「許可」の場合は、先進認証が有効になります。</span><span class="sxs-lookup"><span data-stu-id="33c4f-148">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="33c4f-149">Exchange Online の MA 状態を確認するには、「[Exchange Online で先進認証を有効にする](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33c4f-149">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="33c4f-150">関連記事</span><span class="sxs-lookup"><span data-stu-id="33c4f-150">Related articles</span></span>

[<span data-ttu-id="33c4f-151">Microsoft 365 for business プランをセキュリティで保護するための10位の方法</span><span class="sxs-lookup"><span data-stu-id="33c4f-151">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="33c4f-152">Windows デバイスの Office 2013 の先進認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="33c4f-152">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
