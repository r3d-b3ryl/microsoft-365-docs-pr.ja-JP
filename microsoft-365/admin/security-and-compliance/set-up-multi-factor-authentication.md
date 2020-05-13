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
ms.openlocfilehash: 4c0df9198db8154c1aa748a68eff29dd9bf3bca1
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213012"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="a47f6-103">多要素認証をセットアップする</span><span class="sxs-lookup"><span data-stu-id="a47f6-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a47f6-104">2019年10月21日以降にサブスクリプションまたは試用版を購入した場合に、多要素認証 (MFA) を予期せずに要求されると、サブスクリプションに対して[セキュリティの既定値](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="a47f6-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="a47f6-105">すべての新しい Microsoft 365 サブスクリプションの[セキュリティの既定値](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="a47f6-105">Every new Microsoft 365 subscription will automatically have [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) turned on.</span></span> <span data-ttu-id="a47f6-106">これは、すべてのユーザーが多要素認証 (MFA) を設定し、モバイルデバイスに Microsoft Authenticator アプリをインストールする必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a47f6-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="a47f6-107">詳細については、「 [Microsoft 365 アカウントの MFA を設定する](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a47f6-107">For more information, see [Set up MFA for a Microsoft 365 account](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>

<span data-ttu-id="a47f6-108">サインインするたびに追加の認証を実行するには、次にあげる 9 個の管理者ロールが必要になります。</span><span class="sxs-lookup"><span data-stu-id="a47f6-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="a47f6-109">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="a47f6-109">Global administrator</span></span>
- <span data-ttu-id="a47f6-110">SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="a47f6-110">SharePoint administrator</span></span>
- <span data-ttu-id="a47f6-111">Exchange 管理者</span><span class="sxs-lookup"><span data-stu-id="a47f6-111">Exchange administrator</span></span>
- <span data-ttu-id="a47f6-112">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="a47f6-112">Conditional Access administrator</span></span>
- <span data-ttu-id="a47f6-113">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="a47f6-113">Security administrator</span></span>
- <span data-ttu-id="a47f6-114">ヘルプデスク管理者/パスワード管理者</span><span class="sxs-lookup"><span data-stu-id="a47f6-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="a47f6-115">課金管理者</span><span class="sxs-lookup"><span data-stu-id="a47f6-115">Billing administrator</span></span>
- <span data-ttu-id="a47f6-116">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="a47f6-116">User administrator</span></span>
- <span data-ttu-id="a47f6-117">認証管理者</span><span class="sxs-lookup"><span data-stu-id="a47f6-117">Authentication administrator</span></span>

<span data-ttu-id="a47f6-118">他のすべてのユーザーは、必要に応じて追加認証を求められます。</span><span class="sxs-lookup"><span data-stu-id="a47f6-118">All other users will be asked to perform additional authentication when needed.</span></span>

> [!NOTE]
> <span data-ttu-id="a47f6-119">MFA を設定または変更するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a47f6-119">You must be a global admin to set up or modify MFA</span></span> <br><br>
> <span data-ttu-id="a47f6-120">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a47f6-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="a47f6-121">以前にベースラインポリシーを使用して MFA をセットアップしている場合は、[セキュリティの既定値を有効にするために、これらの機能をオフにする必要があり](#move-from-baseline-policies-to-security-defaults)ます。</span><span class="sxs-lookup"><span data-stu-id="a47f6-121">If you have previously set up MFA with baseline policies, [you must turn them off to turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="a47f6-122">ただし、Microsoft 365 Business またはサブスクリプションに[Azure Active Directory Premium P1 または Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)が搭載されている場合は、[条件付きアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)ポリシーを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a47f6-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="a47f6-123">条件付きアクセスポリシーを使用するには、セキュリティの既定値を無効にし、[先進認証](#enable-modern-authentication-for-your-organization)が有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a47f6-123">To use Conditional Access policies, you need to make sure security defaults are disabled and [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="a47f6-124">Microsoft Authenticator アプリをセットアップする方法をユーザーに説明するには、「 [office 365 で Microsoft authenticator を使用](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a47f6-124">To explain to your users how to set up the Microsoft Authenticator app, see [Use Microsoft Authenticator with Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="a47f6-125">セキュリティの既定値の管理</span><span class="sxs-lookup"><span data-stu-id="a47f6-125">Manage security defaults</span></span>

1. <span data-ttu-id="a47f6-126">グローバル管理者の資格情報を使用して、[管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="a47f6-126">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with global admin credentials.</span></span>
2. <span data-ttu-id="a47f6-127">[ [Azure Active Directory-プロパティ] ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)に移動します。</span><span class="sxs-lookup"><span data-stu-id="a47f6-127">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="a47f6-128">ページの下部で、[**セキュリティの既定値の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a47f6-128">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="a47f6-129">[**はい]** を選択して**セキュリティの既定**値を有効にし、セキュリティの既定値を無効にして [**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a47f6-129">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="a47f6-130">ベースライン ポリシーからセキュリティの既定値に移行する</span><span class="sxs-lookup"><span data-stu-id="a47f6-130">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="a47f6-131">[[条件付きアクセスポリシー] ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)に移動します。</span><span class="sxs-lookup"><span data-stu-id="a47f6-131">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="a47f6-132">有効になっているそれぞれ**の**ベースラインポリシーを選択し、[**ポリシーの有効化**] を [**オフ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="a47f6-132">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="a47f6-133">[ [Azure Active Directory-プロパティ] ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)に移動します。</span><span class="sxs-lookup"><span data-stu-id="a47f6-133">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="a47f6-134">ページの下部にある [セキュリティの**既定の管理**] をクリックし、[**セキュリティ**の既定値を有効にする] ウィンドウで、[**セキュリティの既定値を有効**にする] を [**はい**] に設定して、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a47f6-134">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="a47f6-135">組織の先進認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="a47f6-135">Enable modern authentication for your organization</span></span>

<span data-ttu-id="a47f6-136">Office 2016 のクライアント アプリケーションはすべて、Active Directory Authentication Library (ADAL) を使用して MFA をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a47f6-136">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="a47f6-137">つまり、Office 2016 クライアントでは、アプリ パスワードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a47f6-137">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="a47f6-138">詳細については、[この記事](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a47f6-138">See [this article](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) for more information.</span></span>

<span data-ttu-id="a47f6-139">ただし、Microsoft 365 サブスクリプションが ADAL に対して有効になっていること、または先進認証が有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a47f6-139">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="a47f6-140">先進認証を有効にするには、[管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)で **[設定]** \> **[設定]** の順に選択し、次に **[サービス]** タブのリストから **[先進認証]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a47f6-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="a47f6-141">**モダン認証**パネルの [**モダン認証を有効にする (推奨)** ] チェックボックスをオンにし、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a47f6-141">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![チェックボックスをオンにした状態の [先進認証] パネル](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="a47f6-143">2017年8月現在、Skype for Business online と Exchange online を含むすべての新しい Microsoft 365 サブスクリプションでは、先進認証が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a47f6-143">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="a47f6-144">Skype for Business Online の先進認証状態を確認するには、グローバル管理者の資格情報を使用して Skype for Business Online PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="a47f6-144">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="a47f6-145">Get-CsOAuthConfiguration を実行して、-ClientADALAuthOverride の出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="a47f6-145">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="a47f6-146">-ClientADALAuthOverride が「許可」の場合は、先進認証が有効になります。</span><span class="sxs-lookup"><span data-stu-id="a47f6-146">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="a47f6-147">Exchange Online の MA 状態を確認するには、「[Exchange Online で先進認証を有効にする](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a47f6-147">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="a47f6-148">関連記事</span><span class="sxs-lookup"><span data-stu-id="a47f6-148">Related articles</span></span>

[<span data-ttu-id="a47f6-149">Microsoft 365 for business プランをセキュリティで保護するための10位の方法</span><span class="sxs-lookup"><span data-stu-id="a47f6-149">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="a47f6-150">Windows デバイスの Office 2013 の先進認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="a47f6-150">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
