---
title: Exchange Server をオンプレミスで構成して、ハイブリッド先進認証を使用するには
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: ハイブリッドモダン認証 (HMA) Exchange Serverを使用して、より安全なユーザー認証と承認を提供するオンプレミスの組織を構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3841f429399500cfc24ebadc89c74d478d2290d9
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780286"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="51442-103">Exchange Server をオンプレミスで構成して、ハイブリッド先進認証を使用するには</span><span class="sxs-lookup"><span data-stu-id="51442-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="51442-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="51442-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="51442-105">ハイブリッドモダン認証 (HMA) は、より安全なユーザー認証と承認を提供する ID 管理の方法であり、Exchange サーバーのオンプレミスハイブリッド展開で使用できます。</span><span class="sxs-lookup"><span data-stu-id="51442-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="51442-106">FYI</span><span class="sxs-lookup"><span data-stu-id="51442-106">FYI</span></span>

<span data-ttu-id="51442-107">始める前に、次の呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="51442-107">Before we begin, I call:</span></span>

- <span data-ttu-id="51442-108">ハイブリッドモダン認証 \> HMA</span><span class="sxs-lookup"><span data-stu-id="51442-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="51442-109">Exchange オンプレミス \> EXCH</span><span class="sxs-lookup"><span data-stu-id="51442-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="51442-110">Exchange Online \> EXO</span><span class="sxs-lookup"><span data-stu-id="51442-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="51442-111">また、この記事のグラフィックに"灰色表示" または "淡色表示" のオブジェクトがある場合、これは、灰色で表示される要素が *HMA* 固有の構成に含まれていないという意味です。</span><span class="sxs-lookup"><span data-stu-id="51442-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="51442-112">ハイブリッドのモダン認証の有効化</span><span class="sxs-lookup"><span data-stu-id="51442-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="51442-113">HMA をオンにした場合は、次の意味があります。</span><span class="sxs-lookup"><span data-stu-id="51442-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="51442-114">開始する前に、事前に確認してください。</span><span class="sxs-lookup"><span data-stu-id="51442-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="51442-115">多くの **前提条件** は Skype for Business と Exchange の両方で一般的です。ハイブリッドモダン認証の概要と、オンプレミスの [Skype for Business](hybrid-modern-auth-overview.md)サーバーおよび Exchange サーバーで使用するための前提条件。</span><span class="sxs-lookup"><span data-stu-id="51442-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="51442-116">この記事の手順を開始する前に、この操作を行います。</span><span class="sxs-lookup"><span data-stu-id="51442-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="51442-117">Azure AD でのオンプレミス Web サービス URL のサービス プリンシパル名 **(SPN)** としての追加。</span><span class="sxs-lookup"><span data-stu-id="51442-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="51442-118">HMA に対してすべての仮想ディレクトリが有効になっているか確認する</span><span class="sxs-lookup"><span data-stu-id="51442-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="51442-119">EvoSTS 認証サーバー オブジェクトの確認</span><span class="sxs-lookup"><span data-stu-id="51442-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="51442-120">EXCH で HMA を有効にする。</span><span class="sxs-lookup"><span data-stu-id="51442-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="51442-121">**注** ご使用のバージョンのOfficeサポートMA?</span><span class="sxs-lookup"><span data-stu-id="51442-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="51442-122">[2016 クライアント アプリの最新Office 2013およびOfficeのしくみを参照してください](modern-auth-for-office-2013-and-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="51442-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>

## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="51442-123">すべての前提条件を満たしていることを確認する</span><span class="sxs-lookup"><span data-stu-id="51442-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="51442-124">多くの前提条件は Skype for Business と Exchange の両方で一般的です。このため、ハイブリッドモダン認証の概要と、オンプレミスの Skype for Business および Exchange サーバーで使用するための前提条件を [確認してください](hybrid-modern-auth-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="51442-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="51442-125">この記事  *の手順*  を開始する前に、この操作を行います。</span><span class="sxs-lookup"><span data-stu-id="51442-125">Do this  *before*  you begin any of the steps in this article.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="51442-126">オンプレミスの Web サービス URL を Azure AD に SPN として追加する</span><span class="sxs-lookup"><span data-stu-id="51442-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="51442-127">オンプレミスの Web サービス URL を Azure SPN として割り当てるコマンドADします。</span><span class="sxs-lookup"><span data-stu-id="51442-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="51442-128">SPN は、認証および承認時にクライアント コンピューターおよびデバイスによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="51442-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="51442-129">オンプレミスから Azure Active Directory (Azure AD) への接続に使用される可能性があるすべての URL は、Azure AD に登録する必要があります (これには、内部名前空間と外部名前空間の両方が含まれます)。</span><span class="sxs-lookup"><span data-stu-id="51442-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="51442-130">まず、AAD に追加する必要があるすべての URL を収集します。</span><span class="sxs-lookup"><span data-stu-id="51442-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="51442-131">オンプレミスで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="51442-131">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="51442-132">クライアントが接続できる URL が、AAD の HTTPS サービス プリンシパル名として表示されます。</span><span class="sxs-lookup"><span data-stu-id="51442-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>

1. <span data-ttu-id="51442-133">まず、次の手順で AAD [に接続します](connect-to-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="51442-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

   <span data-ttu-id="51442-134">**注** 以下のコマンドを使用するには、このページの _Connect-MsolService_ オプションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51442-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="51442-135">Exchange 関連の URL の場合は、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="51442-135">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="51442-136">このコマンドの出力には https://  *autodiscover.yourdomain.com*  と https://  *mail.yourdomain.com* URL を含める必要がありますが、そのほとんどは 000000002-0000-0ff1-ce00-00000000000000/ で始まる SPN で構成されます。</span><span class="sxs-lookup"><span data-stu-id="51442-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="51442-137">オンプレミスからhttps://が見つからない場合は、これらの特定のレコードをこのリストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51442-137">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="51442-138">この一覧に内部および外部の MAPI/HTTP、EWS、ActiveSync、OAB、および自動検出レコードが表示されていない場合は、次のコマンドを使用して追加する必要があります (URL の例は ' ' と ' ' ですが、サンプル URL は独自の URL に置き換えます)。 `mail.corp.contoso.com` `owa.contoso.com` </span><span class="sxs-lookup"><span data-stu-id="51442-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="51442-139">手順 2. で Get-MsolServicePrincipal コマンドを再度実行し、出力を確認して、新しいレコードが追加されたのを確認します。</span><span class="sxs-lookup"><span data-stu-id="51442-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="51442-140">前のリスト/スクリーンショットと SPN の新しいリストを比較します。</span><span class="sxs-lookup"><span data-stu-id="51442-140">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="51442-141">レコードの新しいリストのスクリーンショットを撮る場合があります。</span><span class="sxs-lookup"><span data-stu-id="51442-141">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="51442-142">成功した場合は、一覧に 2 つの新しい URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51442-142">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="51442-143">この例では、SPN の一覧に特定の URL と  `https://mail.corp.contoso.com`  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="51442-143">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="51442-144">仮想ディレクトリが正しく構成されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="51442-144">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="51442-145">次のコマンドを実行して、Outlook が使用する可能性があるすべての仮想ディレクトリの Exchange で OAuth が正しく有効にされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="51442-145">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="51442-146">出力を確認して、これらの各 VDir で **OAuth** が有効になっていることを確認します。次のように表示されます (確認する重要な部分は 'OAuth' です)。</span><span class="sxs-lookup"><span data-stu-id="51442-146">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="51442-147">OAuth がサーバーと 4 つの仮想ディレクトリに存在しなされていない場合は、次に進む前に、関連するコマンド (Set-MapiVirtualDirectory、Set-WebServicesVirtualDirectory、Set-OABVirtualDirectory、Set-AutodiscoverVirtualDirectory) を使用して追加する必要があります。[](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory) [](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory) [](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory) [](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)</span><span class="sxs-lookup"><span data-stu-id="51442-147">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="51442-148">EvoSTS 認証サーバー オブジェクトが存在するを確認する</span><span class="sxs-lookup"><span data-stu-id="51442-148">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="51442-149">この最後のコマンドについて、オンプレミスの Exchange 管理シェル に戻る。</span><span class="sxs-lookup"><span data-stu-id="51442-149">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="51442-150">これで、オンプレミスに evoSTS 認証プロバイダーのエントリが設定されているのを検証できます。</span><span class="sxs-lookup"><span data-stu-id="51442-150">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="51442-151">出力には Name EvoSts の AuthServer が表示され、'Enabled' 状態は True である必要があります。</span><span class="sxs-lookup"><span data-stu-id="51442-151">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="51442-152">表示されていない場合は、最新バージョンのハイブリッド構成ウィザードをダウンロードして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51442-152">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

 <span data-ttu-id="51442-153">**重要** 環境で Exchange 2010 を実行している場合、EvoSTS 認証プロバイダーは作成されません。</span><span class="sxs-lookup"><span data-stu-id="51442-153">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="51442-154">HMA を有効にする</span><span class="sxs-lookup"><span data-stu-id="51442-154">Enable HMA</span></span>

<span data-ttu-id="51442-155">オンプレミスの Exchange 管理シェル で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="51442-155">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="51442-156">確認する</span><span class="sxs-lookup"><span data-stu-id="51442-156">Verify</span></span>

<span data-ttu-id="51442-157">HMA を有効にした後、クライアントの次のログインでは新しい認証フローが使用されます。</span><span class="sxs-lookup"><span data-stu-id="51442-157">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="51442-158">HMA を有効にしただけで、クライアントの再認証はトリガーしない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="51442-158">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="51442-159">クライアントは、認証トークンまたは証明書の有効期間に基づいて再認証します。</span><span class="sxs-lookup"><span data-stu-id="51442-159">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="51442-160">また、Outlook クライアントのアイコン (Windows 通知トレイ内) を右クリックして [接続状態] をクリックすると同時に、Ctrl キーを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="51442-160">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="51442-161">OAuth で使用されるベアラー トークンを表す 'Bearer' の 'Authn' タイプに対してクライアントの SMTP アドレス \* を探します。</span><span class="sxs-lookup"><span data-stu-id="51442-161">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

 <span data-ttu-id="51442-162">**注** HMA を使用して Skype for Business を構成する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="51442-162">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="51442-163">2 つの記事が必要になります。1 つはサポートされているトポロジを示し、もう 1 つは構成の方法[を示しています](configure-skype-for-business-for-hybrid-modern-authentication.md)。 [](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)</span><span class="sxs-lookup"><span data-stu-id="51442-163">You'll need two articles: One that lists [supported topologies](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="51442-164">iOS および Android 用の Outlook でのハイブリッド先進認証の使用</span><span class="sxs-lookup"><span data-stu-id="51442-164">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="51442-165">TCP 443 で Exchange サーバーを使用しているオンプレミスのお客様は、次の IP 範囲のトラフィック処理をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="51442-165">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP ranges:</span></span>

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a><span data-ttu-id="51442-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="51442-166">Related topics</span></span>

[<span data-ttu-id="51442-167">Office 365 専用/ITAR から vNext への移行のための最新の認証構成要件</span><span class="sxs-lookup"><span data-stu-id="51442-167">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
