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
description: ハイブリッドモダン認証 (HMA) Exchange Serverを使用して、より安全なユーザー認証と承認を提供する、オンプレミスのユーザー認証を構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 21ffec620ac3e262679fc0e2385f6f0f1b31933b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362260"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="b53ad-103">Exchange Server をオンプレミスで構成して、ハイブリッド先進認証を使用するには</span><span class="sxs-lookup"><span data-stu-id="b53ad-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="b53ad-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="b53ad-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b53ad-105">ハイブリッドモダン認証 (HMA) は、より安全なユーザー認証と承認を提供する ID 管理の方法であり、Exchange サーバーのオンプレミスハイブリッド展開で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b53ad-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="b53ad-106">FYI</span><span class="sxs-lookup"><span data-stu-id="b53ad-106">FYI</span></span>

<span data-ttu-id="b53ad-107">開始する前に、次の呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="b53ad-107">Before we begin, I call:</span></span>

- <span data-ttu-id="b53ad-108">ハイブリッドモダン認証 \> HMA</span><span class="sxs-lookup"><span data-stu-id="b53ad-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="b53ad-109">Exchangeオンプレミス \> EXCH</span><span class="sxs-lookup"><span data-stu-id="b53ad-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="b53ad-110">\>Exchange OnlineEXO</span><span class="sxs-lookup"><span data-stu-id="b53ad-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="b53ad-111">また、この記事のグラフィックに、灰色で表示される要素が *HMA* 固有の構成に含まれていないという'灰色表示' または "淡色" のオブジェクトがある場合。</span><span class="sxs-lookup"><span data-stu-id="b53ad-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="b53ad-112">ハイブリッドモダン認証の有効化</span><span class="sxs-lookup"><span data-stu-id="b53ad-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="b53ad-113">HMA をオンにすると、次の意味があります。</span><span class="sxs-lookup"><span data-stu-id="b53ad-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="b53ad-114">開始する前にプレレポートを満たしてください。</span><span class="sxs-lookup"><span data-stu-id="b53ad-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="b53ad-115">多くの **前提条件は**、Skype for Business と Exchange の両方で一般的です。ハイブリッドモダン認証の概要と、オンプレミスの Skype for Business サーバーと Exchange [サーバー](hybrid-modern-auth-overview.md)で使用するための前提条件です。</span><span class="sxs-lookup"><span data-stu-id="b53ad-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="b53ad-116">この記事の手順を開始する前に、これを行います。</span><span class="sxs-lookup"><span data-stu-id="b53ad-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="b53ad-117">Azure サーバーにサービス プリンシパル名 **(SPN)** としてオンプレミス Web サービス URL を追加AD。</span><span class="sxs-lookup"><span data-stu-id="b53ad-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span> <span data-ttu-id="b53ad-118">EXCH が複数のテナントとハイブリッドである場合、これらのオンプレミス Web サービス URL は、EXCH とのハイブリッドにあるすべてのテナントの Azure AD で SPN として追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b53ad-118">In case EXCH is in hybrid with **multiple tenants**, these on-premises web service URLs must be added as SPNs in the Azure AD of all the tenants which are in hybrid with EXCH.</span></span>

1. <span data-ttu-id="b53ad-119">すべての仮想ディレクトリが HMA に対して有効になっているか確認する</span><span class="sxs-lookup"><span data-stu-id="b53ad-119">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="b53ad-120">EvoSTS Auth Server オブジェクトの確認</span><span class="sxs-lookup"><span data-stu-id="b53ad-120">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="b53ad-121">EXCH で HMA を有効にする。</span><span class="sxs-lookup"><span data-stu-id="b53ad-121">Enabling HMA in EXCH.</span></span>

> [!NOTE]
> <span data-ttu-id="b53ad-122">お使いのバージョンのOfficeサポートMA?</span><span class="sxs-lookup"><span data-stu-id="b53ad-122">Does your version of Office support MA?</span></span> <span data-ttu-id="b53ad-123">[「2013 年および 2016 年 2016](modern-auth-for-office-2013-and-2016.md)年のクライアント アプリOffice最新の認証のしくみOfficeを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b53ad-123">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>


## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="b53ad-124">すべての前提条件を満たしていることを確認する</span><span class="sxs-lookup"><span data-stu-id="b53ad-124">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="b53ad-125">多くの前提条件は、Skype for Business と Exchange Skype for Business の両方で一般的なので、ハイブリッドモダン認証の概要と、オンプレミスのサーバーと Exchange サーバーで使用するための前提条件を[確認してください](hybrid-modern-auth-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b53ad-125">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="b53ad-126">この記事  *の手順*  を開始する前に、これを行います。</span><span class="sxs-lookup"><span data-stu-id="b53ad-126">Do this  *before*  you begin any of the steps in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="b53ad-127">Outlook Web AppおよびExchangeコントロール パネルはハイブリッドモダン認証では機能しません。</span><span class="sxs-lookup"><span data-stu-id="b53ad-127">Outlook Web App and Exchange Control Panel does not work with hybrid Modern Authentication.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="b53ad-128">Azure サーバーにオンプレミス Web サービス URL を SPN として追加AD</span><span class="sxs-lookup"><span data-stu-id="b53ad-128">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="b53ad-129">オンプレミスの Web サービス URL を Azure または SPN として割り当てるAD実行します。</span><span class="sxs-lookup"><span data-stu-id="b53ad-129">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="b53ad-130">SPN は、認証と承認の間にクライアント コンピューターとデバイスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="b53ad-130">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="b53ad-131">オンプレミスから Azure Active Directory (Azure AD) への接続に使用できるすべての URL は、Azure AD に登録する必要があります (これには、内部名前空間と外部名前空間の両方が含まれます)。</span><span class="sxs-lookup"><span data-stu-id="b53ad-131">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="b53ad-132">最初に、AAD に追加する必要があるすべての URL を収集します。</span><span class="sxs-lookup"><span data-stu-id="b53ad-132">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="b53ad-133">オンプレミスで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b53ad-133">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
```

<span data-ttu-id="b53ad-134">クライアントが接続できる URL が、AAD の HTTPS サービス プリンシパル名として一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b53ad-134">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span> <span data-ttu-id="b53ad-135">EXCH が複数のテナントとハイブリッドの場合、これらの HTTPS SPN は EXCH とのハイブリッドのすべてのテナントの AAD に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b53ad-135">In case EXCH is in hybrid with **multiple tenants**, these HTTPS SPNs should be added in the AAD of all the tenants in hybrid with EXCH.</span></span>

1. <span data-ttu-id="b53ad-136">まず、次の手順で AAD [に接続します](connect-to-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="b53ad-136">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="b53ad-137">以下のコマンドを _使用するには、このページConnect-MsolService_ オプションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b53ad-137">You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="b53ad-138">ユーザーに関連Exchange URL の場合は、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b53ad-138">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="b53ad-139">このコマンドの出力には https://  *autodiscover.yourdomain.com*  と https:// mail.yourdomain.com  *URL* を含める必要がありますが、主に 000000002-00000-0ff1-ce000-0000-00000000000/で始まる SPN で構成されます。このコマンドの出力をメモします (および後で比較する場合はスクリーンショットを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b53ad-139">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="b53ad-140">不足している https:// の URL が存在する場合は、これらの特定のレコードをこの一覧に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b53ad-140">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="b53ad-141">この一覧に内部および外部の MAPI/HTTP、EWS、ActiveSync、OAB、および自動検出レコードが表示されていない場合は、以下のコマンドを使用して追加する必要があります (URL の例は ' と ' ' ですが、サンプル URL を独自の URL に置き換えます)。 `mail.corp.contoso.com` `owa.contoso.com` </span><span class="sxs-lookup"><span data-stu-id="b53ad-141">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="b53ad-142">手順 2 から Get-MsolServicePrincipalコマンドを実行し、出力を確認して、新しいレコードが追加されたのを確認します。</span><span class="sxs-lookup"><span data-stu-id="b53ad-142">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="b53ad-143">前のリスト/スクリーンショットと SPN の新しいリストを比較します。</span><span class="sxs-lookup"><span data-stu-id="b53ad-143">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="b53ad-144">レコードの新しいリストのスクリーンショットを撮る場合があります。</span><span class="sxs-lookup"><span data-stu-id="b53ad-144">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="b53ad-145">成功した場合は、一覧に 2 つの新しい URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b53ad-145">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="b53ad-146">この例では、SPN の一覧に特定の URL と  `https://mail.corp.contoso.com`  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="b53ad-146">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="b53ad-147">仮想ディレクトリが適切に構成されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="b53ad-147">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="b53ad-148">次に、次のコマンドを実行Exchange使用する可能性があるすべての仮想ディレクトリ Outlookで OAuth が正しく有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="b53ad-148">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="b53ad-149">出力を確認して、 **これらの各 VDir** で OAuth が有効になっていることを確認します。次のように表示されます (また、重要な確認は 'OAuth' です)。</span><span class="sxs-lookup"><span data-stu-id="b53ad-149">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="b53ad-150">OAuth がサーバーと 4 つの仮想ディレクトリから見つからない場合は、処理を進む前に関連するコマンドを使用して追加する必要があります[(Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory) [、Set-WebServicesVirtualDirectory、Set-OABVirtualDirectory、Set-AutodiscoverVirtualDirectory)。](/powershell/module/exchange/set-webservicesvirtualdirectory) [](/powershell/module/exchange/set-oabvirtualdirectory) [](/powershell/module/exchange/set-autodiscovervirtualdirectory)</span><span class="sxs-lookup"><span data-stu-id="b53ad-150">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="b53ad-151">EvoSTS Auth Server オブジェクトが存在するを確認する</span><span class="sxs-lookup"><span data-stu-id="b53ad-151">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="b53ad-152">この最後のコマンドのオンプレミス Exchange管理シェルに戻します。</span><span class="sxs-lookup"><span data-stu-id="b53ad-152">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="b53ad-153">これで、オンプレミスに evoSTS 認証プロバイダーのエントリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b53ad-153">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -like "EvoSts"}
```

<span data-ttu-id="b53ad-154">出力に Name EvoSts の AuthServer が表示され、'Enabled' 状態は True である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b53ad-154">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="b53ad-155">これが表示されていない場合は、最新バージョンのハイブリッド構成ウィザードをダウンロードして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b53ad-155">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="b53ad-156">EXCH が複数のテナントとハイブリッドになっている場合、出力には、EXCH とハイブリッドの各テナントの Name EvoSts - {GUID} の 1 つの AuthServer が表示され、これらすべての AuthServer オブジェクトに対して 'Enabled' 状態が True である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b53ad-156">In case EXCH is in hybrid with **multiple tenants**, your output should show one AuthServer of the Name EvoSts - {GUID} for each tenant in hybrid with EXCH and the 'Enabled' state should be True for all of these AuthServer objects.</span></span>

 <span data-ttu-id="b53ad-157">**重要** 環境で 2010 Exchangeを実行している場合、EvoSTS 認証プロバイダーは作成されません。</span><span class="sxs-lookup"><span data-stu-id="b53ad-157">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="b53ad-158">HMA を有効にする</span><span class="sxs-lookup"><span data-stu-id="b53ad-158">Enable HMA</span></span>

<span data-ttu-id="b53ad-159">オンプレミスの管理シェルでExchangeコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b53ad-159">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

<span data-ttu-id="b53ad-160">EXCH バージョンが Exchange 2016 (CU18 以上) または Exchange 2019 (CU7 以上) で、ハイブリッドが 2020 年 9 月以降にダウンロードされた HCW で構成されている場合は、オンプレミスの Exchange 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b53ad-160">If the EXCH version is Exchange 2016 (CU18 or higher) or Exchange 2019 (CU7 or higher) and hybrid was configured with HCW downloaded after September 2020, run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -DomainName "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> <span data-ttu-id="b53ad-161">EXCH が複数のテナントとハイブリッドである場合、EXCH には複数の AuthServer オブジェクトが存在し、各テナントに対応するドメインがあります。</span><span class="sxs-lookup"><span data-stu-id="b53ad-161">In case EXCH is in hybrid with **multiple tenants**, there are multiple AuthServer objects present in EXCH with domains corresponding to each tenant.</span></span>  <span data-ttu-id="b53ad-162">**IsDefaultAuthorizationEndpoint** フラグは、これらの AuthServer オブジェクトの 1 つについて true に設定する必要があります **(IsDefaultAuthorizationEndpoint** コマンドレットを使用)。</span><span class="sxs-lookup"><span data-stu-id="b53ad-162">The **IsDefaultAuthorizationEndpoint** flag should be set to true (using the **IsDefaultAuthorizationEndpoint** cmdlet) for any one of these AuthServer objects.</span></span> <span data-ttu-id="b53ad-163">すべての Authserver オブジェクトに対してこのフラグを true に設定することはできません。これらの AuthServer オブジェクトの **IsDefaultAuthorizationEndpoint** フラグの 1 つが true に設定されている場合でも、HMA は有効になります。</span><span class="sxs-lookup"><span data-stu-id="b53ad-163">This flag can't be set to true for all the Authserver objects and HMA would be enabled even if one of these AuthServer object's **IsDefaultAuthorizationEndpoint** flag is set to true.</span></span>

## <a name="verify"></a><span data-ttu-id="b53ad-164">確認する</span><span class="sxs-lookup"><span data-stu-id="b53ad-164">Verify</span></span>

<span data-ttu-id="b53ad-165">HMA を有効にした後、クライアントの次のログインでは新しい認証フローが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b53ad-165">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="b53ad-166">HMA をオンにしてもクライアントの再認証はトリガーされず、Exchange が新しい設定を取得するには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b53ad-166">Note that just turning on HMA won't trigger a reauthentication for any client, and it might take a while for Exchange to pick up the new settings.</span></span>

<span data-ttu-id="b53ad-167">また、ctrl キーを押しながら Outlook クライアントのアイコン (Windows 通知トレイ) を右クリックし、[接続状態] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b53ad-167">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="b53ad-168">OAuth で使用されるベアラー トークンを表す 'Bearer'の 'Authn' 型に対してクライアントの SMTP アドレス \* を探します。</span><span class="sxs-lookup"><span data-stu-id="b53ad-168">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

> [!NOTE]
> <span data-ttu-id="b53ad-169">HMA を使用してSkype for Business構成する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="b53ad-169">Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="b53ad-170">2 つの記事が必要です。1 つは、サポートされているトポロジを一覧表示する記事と、構成を実行する方法[を示す記事です](configure-skype-for-business-for-hybrid-modern-authentication.md)。 [](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)</span><span class="sxs-lookup"><span data-stu-id="b53ad-170">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="b53ad-171">iOS および Android 用の Outlook でのハイブリッド先進認証の使用</span><span class="sxs-lookup"><span data-stu-id="b53ad-171">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="b53ad-172">オンプレミスのお客様が TCP 443 Exchangeサーバーを使用している場合は、次の IP アドレス範囲のトラフィック処理をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="b53ad-172">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP address ranges:</span></span>

```text
52.125.128.0/20
52.127.96.0/23
```

<span data-ttu-id="b53ad-173">iOS と Android 用 Outlook アプリは、Microsoft サービス を使用して、Microsoft 365 または Office 365 をモバイル デバイスで体験し、日常の生活と仕事を見つけ、計画し、優先順位を付ける最善の方法として設計されています。</span><span class="sxs-lookup"><span data-stu-id="b53ad-173">The Outlook app for iOS and Android is designed as the best way to experience Microsoft 365 or Office 365 on your mobile device by using Microsoft services to help find, plan, and prioritize your daily life and work.</span></span> <span data-ttu-id="b53ad-174">詳細については、「ハイブリッドモダン認証と iOS および Android のOutlookを使用する[」を参照してください](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)。</span><span class="sxs-lookup"><span data-stu-id="b53ad-174">For more information, please refer to [Using hybrid Modern Authentication with Outlook for iOS and Android](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b53ad-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="b53ad-175">Related topics</span></span>

[<span data-ttu-id="b53ad-176">専用/ITAR から vNext への移行Office 365認証の最新の構成要件</span><span class="sxs-lookup"><span data-stu-id="b53ad-176">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
