---
title: Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する
description: 認証を提供するために Azure ADオンプレミスの組織と通信AD確認するための重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c1732dc17188427f9a181d1c47abe71bb8f39584
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841413"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a><span data-ttu-id="40973-104">Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する</span><span class="sxs-lookup"><span data-stu-id="40973-104">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>

<span data-ttu-id="40973-105">Microsoft マネージド デスクトップでは、デバイスは自動的に Azure Active Directory (Azure AD) に参加します。</span><span class="sxs-lookup"><span data-stu-id="40973-105">In Microsoft Managed Desktop, devices are automatically joined to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="40973-106">このため、オンプレミスの Active Directory を使用している場合は、Azure AD に参加しているデバイスがオンプレミスの Active Directory と通信できるよう、いくつかのことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40973-106">For this reason, if you are using an on-premises Active Directory, you'll have to check some things to ensure that devices joined to Azure AD can communicate with your on-premises Active Directory.</span></span> 

> [!NOTE]  
> <span data-ttu-id="40973-107">*ハイブリッド* Azure AD参加は、Microsoft マネージド デスクトップではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="40973-107">*Hybrid* Azure AD join is not supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="40973-108">Azure Active Directory を使用すると、ユーザーはシングル Sign-On (SSO) を利用できます。つまり、通常、ユーザーはリソースを使用する度に資格情報を提供する必要がなされません。</span><span class="sxs-lookup"><span data-stu-id="40973-108">Azure Active Directory lets your users take advantage of Single Sign-On (SSO), which means they typically won't have to provide credentials every time they use resources.</span></span>

<span data-ttu-id="40973-109">Azure Active Directory への参加の詳細については、「方法: Azure active Directory への参加の実装AD [参照してください](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)。</span><span class="sxs-lookup"><span data-stu-id="40973-109">For information about joining Azure Active Directory, refer to [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).</span></span> <span data-ttu-id="40973-110">Azure AD に参加しているデバイスでのシングル Sign-On (SSO) の背景情報については [、「Azure](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)AD に参加しているデバイスでのオンプレミス リソースへの SSO の動作」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40973-110">For background information about Single Sign-On (SSO) on devices joined to Azure AD, see [How SSO to on-premises resources works on Azure AD joined devices](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).</span></span>


<span data-ttu-id="40973-111">この記事では、ローカルの Active Directory 接続に依存するアプリや他のリソースが Microsoft マネージド デスクトップで円滑に動作するために確認する必要がある項目について説明します。</span><span class="sxs-lookup"><span data-stu-id="40973-111">This article explains the things you need to check in order to ensure that apps and other resources that depend on local Active Directory connectivity will work smoothly with Microsoft Managed Desktop.</span></span>


## <a name="single-sign-on-for-on-premises-resources"></a><span data-ttu-id="40973-112">オンプレミス Sign-On単一のリソース</span><span class="sxs-lookup"><span data-stu-id="40973-112">Single Sign-On for on-premises resources</span></span>

<span data-ttu-id="40973-113">MICROSOFT Sign-On デバイスでは、UPN とパスワードを使用したシングル クライアント (SSO) が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="40973-113">Single Sign-On (SSO) by using UPN and password is enabled by default on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="40973-114">ただし、ユーザーは Windows Hello for Business も使用できます。追加のセットアップ手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="40973-114">But your users can also use Windows Hello for Business, which requires some extra setup steps.</span></span> 

### <a name="single-sign-on-by-using-upn-and-password"></a><span data-ttu-id="40973-115">UPN Sign-Onパスワードを使用した単一の構成</span><span class="sxs-lookup"><span data-stu-id="40973-115">Single Sign-On by using UPN and password</span></span>

<span data-ttu-id="40973-116">ほとんどの組織では、ユーザーは MICROSOFT マネージド デスクトップ デバイスで SSO を使用して UPN とパスワードで認証できます。</span><span class="sxs-lookup"><span data-stu-id="40973-116">In most organizations, your users will be able to use SSO to authenticate by UPN and password on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="40973-117">ただし、この関数が動作するには、次のことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40973-117">However, to make sure this function will work, you should double-check the following things:</span></span>

- <span data-ttu-id="40973-118">Azure AD Connect がセットアップされ、その後で実行されているオンプレミスの Active Directory サーバー Windows Server 2008 R2確認します。</span><span class="sxs-lookup"><span data-stu-id="40973-118">Confirm that Azure AD Connect is set up and uses an on-premises Active Directory server running Windows Server 2008 R2 or later.</span></span>
- <span data-ttu-id="40973-119">Azure AD Connect がサポートされているバージョンを実行し、これら 3 つの属性を Azure AD と同期するように設定AD。</span><span class="sxs-lookup"><span data-stu-id="40973-119">Confirm that Azure AD Connect is running a supported version and is set to sync these three attributes with Azure AD:</span></span> 
    - <span data-ttu-id="40973-120">DNS ドメイン Active Directory の名前 (ユーザーが存在する場所)</span><span class="sxs-lookup"><span data-stu-id="40973-120">DNS domain name of the on-premises Active Directory (where the users are located)</span></span>
    - <span data-ttu-id="40973-121">オンプレミスの Active Directory の NetBIOS (ユーザーが存在する場所)</span><span class="sxs-lookup"><span data-stu-id="40973-121">NetBIOS of your on-premises Active Directory (where the users are located)</span></span>
    - <span data-ttu-id="40973-122">ユーザーの SAM アカウント名</span><span class="sxs-lookup"><span data-stu-id="40973-122">SAM account name of the user</span></span>


### <a name="single-sign-on-by-using-windows-hello-for-business"></a><span data-ttu-id="40973-123">Windows Hello for Business Sign-On使用した単一の機能</span><span class="sxs-lookup"><span data-stu-id="40973-123">Single Sign-On by using Windows Hello for Business</span></span>

<span data-ttu-id="40973-124">また、Microsoft マネージド デスクトップ デバイスでは、Windows Hello for Business を使用して、ユーザーに高速でパスワードレスなエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="40973-124">Microsoft Managed Desktop devices also offer your users a fast, passwordless experience by employing Windows Hello for Business.</span></span> <span data-ttu-id="40973-125">ユーザーがそれぞれの UPN とパスワードを入力せずに Windows Hello for Business が動作するようにするには、「Azure AD に参加しているデバイスをオンプレミスの Single-Sign 用に構成する」にアクセスして [、Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) を使用して要件を確認し、そこで提供されている手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="40973-125">To ensure Windows Hello for Business will work without your users having to provide respective UPN and password, visit [Configure Azure AD joined devices for On-premises Single-Sign On using Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) to check the requirements, and then follow the steps provided there.</span></span>


## <a name="apps-and-resources-that-use-authentication"></a><span data-ttu-id="40973-126">認証を使用するアプリとリソース</span><span class="sxs-lookup"><span data-stu-id="40973-126">Apps and resources that use authentication</span></span>

<span data-ttu-id="40973-127">Azure Active Directory [で動作する](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) アプリの設定に関する完全なガイダンスについては、Azure コンテンツ セットのアプリケーションとリソースに関する考慮事項を理解するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40973-127">Refer to [Understand considerations for applications and resources](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in the Azure content set for full guidance on setting up apps to work with Azure Active Directory.</span></span> <span data-ttu-id="40973-128">まとめると、以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="40973-128">In summary:</span></span>


- <span data-ttu-id="40973-129">Azure ADアプリ ギャラリーに追加されたアプリなど、クラウドベースのアプリを使用する場合、Microsoft マネージド デスクトップで動作するためにそれ以上の準備は必要ない場合があります。</span><span class="sxs-lookup"><span data-stu-id="40973-129">If you use **cloud-based apps**, such as those added to the Azure AD app gallery, most don't require any further preparation to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="40973-130">ただし、Web アカウント マネージャー (WAM) を使用しない Win32 アプリでは、ユーザーに認証を求めるメッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="40973-130">However, any Win32 apps that don't use Web Account Manager (WAM) might still prompt users for authentication.</span></span>

- <span data-ttu-id="40973-131">オンプレミスでホスト **されているアプリの** 場合は、ブラウザーの信頼済みサイト一覧にそれらのアプリを追加してください。</span><span class="sxs-lookup"><span data-stu-id="40973-131">For apps that are **hosted on-premises**, be sure to add those apps to the trusted sites list in your browsers.</span></span> <span data-ttu-id="40973-132">この手順を実行すると、ユーザーに資格情報の入力を求めることなく、Windows 認証をシームレスに動作できます。</span><span class="sxs-lookup"><span data-stu-id="40973-132">This step will enable Windows authentication to work seamlessly, without users being prompted for credentials.</span></span> <span data-ttu-id="40973-133">アプリを追加するには、構成可能な設定 [のリファレンスの](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) 「信頼済み [サイト」を参照してください](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref)。</span><span class="sxs-lookup"><span data-stu-id="40973-133">To add apps, refer to [Trusted sites](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) in the [Configurable settings reference](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref).</span></span>

- <span data-ttu-id="40973-134">Active Directory フェデレーション サービスを使用している場合は、「AD FS を使用してシングル サインオンを確認および管理する」の手順に従って [SSO が有効ADします](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="40973-134">If you are using Active Directory Federated Services, check that SSO is enabled by using the steps in [Verify and manage single sign-on with AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)).</span></span> 

- <span data-ttu-id="40973-135">オンプレミス **で古い** プロトコルを使用するアプリの場合、デバイスが認証のためにオンプレミスのドメイン コントローラーにアクセスできる限り、追加のセットアップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="40973-135">For apps that are **on-premises and use older protocols**, no extra setup is required, as long as the devices have access to an on-premises domain controller to authenticate.</span></span> <span data-ttu-id="40973-136">ただし、これらのアプリケーションに安全なアクセスを提供するには、Azure AD Application Proxy を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40973-136">To provide secure access for these applications, however, you should deploy Azure AD Application Proxy.</span></span> <span data-ttu-id="40973-137">詳細については、Azure Active Directory のアプリケーション プロキシを介したオンプレミス アプリケーションへのリモート アクセス [に関するページを参照してください](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)。</span><span class="sxs-lookup"><span data-stu-id="40973-137">For more information, see [Remote access to on-premises applications through Azure Active Directory's Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

- <span data-ttu-id="40973-138">オンプレミスで **実行され** 、コンピューター認証に依存するアプリはサポートされていないので、新しいバージョンに置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="40973-138">Apps that run **on-premises and rely on machine authentication** aren't supported, so you should consider replacing them with newer versions.</span></span>

### <a name="network-shares-that-use-authentication"></a><span data-ttu-id="40973-139">認証を使用するネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="40973-139">Network shares that use authentication</span></span>

<span data-ttu-id="40973-140">UNC パスを使用してデバイスがオンプレミスのドメイン コントローラーにアクセスできる限り、ユーザーがネットワーク共有にアクセスするために追加のセットアップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="40973-140">No extra setup is required for users to access network shares, as long as the devices have access to an on-premises domain controller by using a UNC path.</span></span>

### <a name="printers"></a><span data-ttu-id="40973-141">プリンター</span><span class="sxs-lookup"><span data-stu-id="40973-141">Printers</span></span>

<span data-ttu-id="40973-142">Microsoft マネージド デスクトップ デバイスは、ハイブリッド クラウド印刷を構成しない限り、オンプレミスの Active Directory に発行されたプリンター [に接続できません](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。</span><span class="sxs-lookup"><span data-stu-id="40973-142">Microsoft Managed Desktop devices cannot connect to printers that are published to your on-premises Active Directory unless you have configured [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>

<span data-ttu-id="40973-143">クラウド専用環境でプリンターを自動的に検出することはできませんが、ユーザーは、デバイスがオンプレミスのドメイン コントローラーにアクセスできる限り、プリンター パスまたはプリンター キュー パスを使用してオンプレミスのプリンターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="40973-143">While printers can't be automatically discovered in a cloud only environment, your users can use on-premises printers by using the printer path or printer queue path, as long as the devices have access to an on-premises domain controller.</span></span>

<!--add fuller material on printers when available-->
