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
ms.openlocfilehash: 7e48f72f2fd8cfc5042bd15f994cc98bfa5fca8c
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "43503973"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="b29fe-103">多要素認証をセットアップする</span><span class="sxs-lookup"><span data-stu-id="b29fe-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b29fe-104">2019年10月21日以降にサブスクリプションまたは試用版を購入した場合に、多要素認証 (MFA) を予期せずに要求されると、サブスクリプションに対して[セキュリティの既定値](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="b29fe-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="b29fe-105">新しい法人向け Office 365 または Microsoft 365 Business のすべてのサブスクリプションは、自動的にセキュリティの既定値が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="b29fe-105">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="b29fe-106">これは、すべてのユーザーが MFA を設定し、モバイルデバイスに Microsoft Authenticator アプリをインストールする必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b29fe-106">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="b29fe-107">詳細については、「[Office 365 で 2 段階認証をセットアップする](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29fe-107">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="b29fe-108">サインインするたびに追加の認証を実行するには、次にあげる 9 個の管理者ロールが必要になります。</span><span class="sxs-lookup"><span data-stu-id="b29fe-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="b29fe-109">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="b29fe-109">Global administrator</span></span>
- <span data-ttu-id="b29fe-110">SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="b29fe-110">SharePoint administrator</span></span>
- <span data-ttu-id="b29fe-111">Exchange 管理者</span><span class="sxs-lookup"><span data-stu-id="b29fe-111">Exchange administrator</span></span>
- <span data-ttu-id="b29fe-112">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="b29fe-112">Conditional Access administrator</span></span>
- <span data-ttu-id="b29fe-113">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="b29fe-113">Security administrator</span></span>
- <span data-ttu-id="b29fe-114">ヘルプデスク管理者/パスワード管理者</span><span class="sxs-lookup"><span data-stu-id="b29fe-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="b29fe-115">課金管理者</span><span class="sxs-lookup"><span data-stu-id="b29fe-115">Billing administrator</span></span>
- <span data-ttu-id="b29fe-116">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="b29fe-116">User administrator</span></span>
- <span data-ttu-id="b29fe-117">認証管理者</span><span class="sxs-lookup"><span data-stu-id="b29fe-117">Authentication administrator</span></span>

<span data-ttu-id="b29fe-118">他のすべてのユーザーは、必要に応じて追加認証を求められます。</span><span class="sxs-lookup"><span data-stu-id="b29fe-118">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="b29fe-119">詳細については、「[セキュリティの既定とは](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29fe-119">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

> [!NOTE]
> <span data-ttu-id="b29fe-120">MFA を設定または変更するには、Office 365 のグローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b29fe-120">You must be an Office 365 global admin to set up or modify MFA.</span></span> <br><br>
> <span data-ttu-id="b29fe-121">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b29fe-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="b29fe-122">以前にベースライン ポリシーを使用して MFA をセットアップしている場合は、[それらをオフにして、セキュリティの既定値をオンにする必要があります](#move-from-baseline-policies-to-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="b29fe-122">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="b29fe-123">ただし、Microsoft 365 Business またはサブスクリプションに[Azure Active Directory Premium P1 または Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)が搭載されている場合は、[条件付きアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)ポリシーを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b29fe-123">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="b29fe-124">条件付きアクセスポリシーを使用するには、[先進認証](#enable-modern-authentication-for-your-organization)が有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b29fe-124">To use conditional access policies, you need to make sure [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="b29fe-125">ユーザーに Authenticator アプリをセットアップする方法を説明するには、「[Office 365 で Microsoft Authenticator を使用する](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b29fe-125">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="b29fe-126">セキュリティの既定値の管理</span><span class="sxs-lookup"><span data-stu-id="b29fe-126">Manage security defaults</span></span>

1. <span data-ttu-id="b29fe-127">グローバル管理者の資格情報を使用して、[管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b29fe-127">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="b29fe-128">[Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b29fe-128">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="b29fe-129">ページの下部で、[**セキュリティの既定値の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b29fe-129">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="b29fe-130">セキュリティの既定値を有効にする場合は [**はい]** 、セキュリティの既定値を無効にする場合は [**いいえ**] を選択し、[**保存**] を選択</span><span class="sxs-lookup"><span data-stu-id="b29fe-130">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="b29fe-131">ベースライン ポリシーからセキュリティの既定値に移行する</span><span class="sxs-lookup"><span data-stu-id="b29fe-131">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="b29fe-132">[管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)で、[**すべて表示**] を選択し、[**管理センター**] の下にある [ **Azure Active Directory** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b29fe-132">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Show all**, and then **Azure Active Directory** under **Admin centers**.</span></span>

2. <span data-ttu-id="b29fe-133">**Azure active directory 管理センター**で、[ **azure active directory** > **セキュリティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b29fe-133">In the  **Azure Active Directory admin center** choose **Azure Active Directory** > **Security**.</span></span>

3. <span data-ttu-id="b29fe-134">[**セキュリティ] |**[作業の開始] ページで、[**条件付きアクセス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b29fe-134">On the **Security | Getting started** page, choose **Conditional Access**.</span></span> 

4. <span data-ttu-id="b29fe-135">[**条件付きアクセスポリシー** ] ページで、にある各基準ポリシーを選択し、 **[\*\*\*\*オフ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="b29fe-135">On the **Conditional Access - Policies** page, choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="b29fe-136">[[Azure Active Directory のプロパティ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)] ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b29fe-136">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="b29fe-137">ページの下部にある [セキュリティの**既定の管理**] をクリックし、[**セキュリティ**の既定値を有効にする] ウィンドウで、[**セキュリティの既定値を有効**にする] を [**はい**] に設定して、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b29fe-137">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="b29fe-138">組織の先進認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="b29fe-138">Enable modern authentication for your organization</span></span>

<span data-ttu-id="b29fe-139">Office 2016 のクライアント アプリケーションはすべて、Active Directory Authentication Library (ADAL) を使用して MFA をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b29fe-139">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="b29fe-140">つまり、Office 2016 クライアントでは、アプリ パスワードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b29fe-140">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="b29fe-141">ただし、Office 365 サブスクリプションが ADAL または先進認証に対して有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b29fe-141">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="b29fe-142">先進認証を有効にするには、[管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)で **[設定]** \> **[設定]** の順に選択し、次に **[サービス]** タブのリストから **[先進認証]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b29fe-142">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="b29fe-143">**モダン認証**パネルの [**モダン認証を有効にする (推奨)** ] チェックボックスをオンにし、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b29fe-143">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![チェックボックスをオンにした状態の [先進認証] パネル](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="b29fe-145">2017 年 8 月に、Skype for Business Online と Exchange Online を含むすべての新しい Office 365 テナントには、既定で先進認証が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="b29fe-145">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="b29fe-146">Skype for Business Online の先進認証状態を確認するには、グローバル管理者の資格情報を使用して Skype for Business Online PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="b29fe-146">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="b29fe-147">Get-CsOAuthConfiguration を実行して、-ClientADALAuthOverride の出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="b29fe-147">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="b29fe-148">-ClientADALAuthOverride が「許可」の場合は、先進認証が有効になります。</span><span class="sxs-lookup"><span data-stu-id="b29fe-148">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>

<span data-ttu-id="b29fe-149">Exchange Online の MA 状態を確認するには、「[Exchange Online で先進認証を有効にする](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29fe-149">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="b29fe-150">関連記事</span><span class="sxs-lookup"><span data-stu-id="b29fe-150">Related articles</span></span>

[<span data-ttu-id="b29fe-151">Office 365とMicrosoft 365 Businessプランを安全にする10の方法</span><span class="sxs-lookup"><span data-stu-id="b29fe-151">Top 10 ways to secure Office 365 and Microsoft 365 Business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="b29fe-152">Windows デバイスの Office 2013 の先進認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="b29fe-152">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
