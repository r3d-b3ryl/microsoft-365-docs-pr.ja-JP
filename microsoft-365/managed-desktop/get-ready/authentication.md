---
title: Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する
description: Azure クライアントが認証を提供するためにオンプレミスAD通信を行AD重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f6b1e257fd767fa112fddb41d773065b8002a2a3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909192"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a><span data-ttu-id="75895-104">Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する</span><span class="sxs-lookup"><span data-stu-id="75895-104">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>

<span data-ttu-id="75895-105">Microsoft Managed Desktop では、デバイスは Azure Active Directory (Azure Active Directory) に自動的に参加AD。</span><span class="sxs-lookup"><span data-stu-id="75895-105">In Microsoft Managed Desktop, devices are automatically joined to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="75895-106">このため、オンプレミスの Active Directory を使用している場合は、Azure AD に参加しているデバイスがオンプレミスの Active Directory と通信できるよう、いくつかのことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75895-106">For this reason, if you are using an on-premises Active Directory, you'll have to check some things to ensure that devices joined to Azure AD can communicate with your on-premises Active Directory.</span></span> 

> [!NOTE]  
> <span data-ttu-id="75895-107">*ハイブリッド* Azure AD参加は、Microsoft Managed Desktop ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="75895-107">*Hybrid* Azure AD join is not supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="75895-108">Azure Active Directory を使用すると、ユーザーはシングル Sign-On (SSO) を利用できます。つまり、通常、リソースを使用する度に資格情報を提供する必要がなされません。</span><span class="sxs-lookup"><span data-stu-id="75895-108">Azure Active Directory lets your users take advantage of Single Sign-On (SSO), which means they typically won't have to provide credentials every time they use resources.</span></span>

<span data-ttu-id="75895-109">Azure Active Directory への参加の詳細については、「How [to: Plan your Azure AD実装」を参照してください](/azure/active-directory/devices/azureadjoin-plan)。</span><span class="sxs-lookup"><span data-stu-id="75895-109">For information about joining Azure Active Directory, refer to [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).</span></span> <span data-ttu-id="75895-110">Azure AD に参加しているデバイスでのシングル Sign-On (SSO) のバックグラウンド情報については [、「Azure](/azure/active-directory/devices/azuread-join-sso#how-it-works)AD 参加デバイスでのオンプレミス リソースへの SSO の動作」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75895-110">For background information about Single Sign-On (SSO) on devices joined to Azure AD, see [How SSO to on-premises resources works on Azure AD joined devices](/azure/active-directory/devices/azuread-join-sso#how-it-works).</span></span>


<span data-ttu-id="75895-111">この記事では、ローカルの Active Directory 接続に依存するアプリや他のリソースが Microsoft Managed Desktop でスムーズに動作するために確認する必要がある内容について説明します。</span><span class="sxs-lookup"><span data-stu-id="75895-111">This article explains the things you need to check in order to ensure that apps and other resources that depend on local Active Directory connectivity will work smoothly with Microsoft Managed Desktop.</span></span>


## <a name="single-sign-on-for-on-premises-resources"></a><span data-ttu-id="75895-112">オンプレミス Sign-Onの単一のリソース</span><span class="sxs-lookup"><span data-stu-id="75895-112">Single Sign-On for on-premises resources</span></span>

<span data-ttu-id="75895-113">UPN Sign-Onを使用したシングル デバイス (SSO) は、Microsoft 管理デスクトップ デバイスで既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="75895-113">Single Sign-On (SSO) by using UPN and password is enabled by default on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="75895-114">ただし、ユーザーは Windows Hello for Business を使用できます。追加のセットアップ手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="75895-114">But your users can also use Windows Hello for Business, which requires some extra setup steps.</span></span> 

### <a name="single-sign-on-by-using-upn-and-password"></a><span data-ttu-id="75895-115">UPN Sign-Onパスワードを使用した単一のデバイス</span><span class="sxs-lookup"><span data-stu-id="75895-115">Single Sign-On by using UPN and password</span></span>

<span data-ttu-id="75895-116">ほとんどの組織では、ユーザーは MICROSOFT 管理デスクトップ デバイスで SSO を使用して UPN とパスワードによる認証を行えます。</span><span class="sxs-lookup"><span data-stu-id="75895-116">In most organizations, your users will be able to use SSO to authenticate by UPN and password on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="75895-117">ただし、この関数が動作する場合は、次の機能を確認してください。</span><span class="sxs-lookup"><span data-stu-id="75895-117">However, to make sure this function will work, you should double-check the following things:</span></span>

- <span data-ttu-id="75895-118">Azure AD Connect がセットアップされ、その後で実行されているオンプレミスの Active Directory サーバー Windows Server 2008 R2確認します。</span><span class="sxs-lookup"><span data-stu-id="75895-118">Confirm that Azure AD Connect is set up and uses an on-premises Active Directory server running Windows Server 2008 R2 or later.</span></span>
- <span data-ttu-id="75895-119">Azure AD Connect がサポートされているバージョンを実行し、これらの 3 つの属性を Azure サーバーと同期するようにAD。</span><span class="sxs-lookup"><span data-stu-id="75895-119">Confirm that Azure AD Connect is running a supported version and is set to sync these three attributes with Azure AD:</span></span> 
    - <span data-ttu-id="75895-120">DNS ドメイン Active Directory の名前 (ユーザーが存在する場所)</span><span class="sxs-lookup"><span data-stu-id="75895-120">DNS domain name of the on-premises Active Directory (where the users are located)</span></span>
    - <span data-ttu-id="75895-121">オンプレミスの Active Directory の NetBIOS (ユーザーが存在する場所)</span><span class="sxs-lookup"><span data-stu-id="75895-121">NetBIOS of your on-premises Active Directory (where the users are located)</span></span>
    - <span data-ttu-id="75895-122">ユーザーの SAM アカウント名</span><span class="sxs-lookup"><span data-stu-id="75895-122">SAM account name of the user</span></span>


### <a name="single-sign-on-by-using-windows-hello-for-business"></a><span data-ttu-id="75895-123">Windows Hello Sign-Onを使用した単一のアプリケーション</span><span class="sxs-lookup"><span data-stu-id="75895-123">Single Sign-On by using Windows Hello for Business</span></span>

<span data-ttu-id="75895-124">Microsoft Managed Desktop デバイスは、Windows Hello for Business を採用することで、ユーザーに高速でパスワードレスなエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="75895-124">Microsoft Managed Desktop devices also offer your users a fast, passwordless experience by employing Windows Hello for Business.</span></span> <span data-ttu-id="75895-125">ユーザーがそれぞれの UPN とパスワードを指定せずに Windows Hello for Business が動作するようにするには、「Azure AD に参加しているデバイスをオンプレミス用に構成する Single-Sign On using [Windows Hello for Business」](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) を参照して要件を確認し、そこに示す手順に従います。</span><span class="sxs-lookup"><span data-stu-id="75895-125">To ensure Windows Hello for Business will work without your users having to provide respective UPN and password, visit [Configure Azure AD joined devices for On-premises Single-Sign On using Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) to check the requirements, and then follow the steps provided there.</span></span>


## <a name="apps-and-resources-that-use-authentication"></a><span data-ttu-id="75895-126">認証を使用するアプリとリソース</span><span class="sxs-lookup"><span data-stu-id="75895-126">Apps and resources that use authentication</span></span>

<span data-ttu-id="75895-127">Azure Active Directory [で動作するように](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) アプリを設定する方法の詳細については、「Azure コンテンツ セットのアプリケーションとリソースに関する考慮事項を理解する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75895-127">Refer to [Understand considerations for applications and resources](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in the Azure content set for full guidance on setting up apps to work with Azure Active Directory.</span></span> <span data-ttu-id="75895-128">まとめると、以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="75895-128">In summary:</span></span>


- <span data-ttu-id="75895-129">Azure ADアプリ ギャラリーに追加されたアプリなど、クラウドベースのアプリを使用する場合、Microsoft Managed Desktop を操作するためにそれ以上の準備は必要ない場合が多い。</span><span class="sxs-lookup"><span data-stu-id="75895-129">If you use **cloud-based apps**, such as those added to the Azure AD app gallery, most don't require any further preparation to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="75895-130">ただし、Web アカウント マネージャー (WAM) を使用しない Win32 アプリでは、ユーザーに認証を求めるメッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="75895-130">However, any Win32 apps that don't use Web Account Manager (WAM) might still prompt users for authentication.</span></span>

- <span data-ttu-id="75895-131">オンプレミスでホストされている **アプリの場合は**、ブラウザーの信頼できるサイトの一覧にアプリを必ず追加してください。</span><span class="sxs-lookup"><span data-stu-id="75895-131">For apps that are **hosted on-premises**, be sure to add those apps to the trusted sites list in your browsers.</span></span> <span data-ttu-id="75895-132">この手順では、ユーザーに資格情報の入力を求めることなく、Windows 認証をシームレスに動作できます。</span><span class="sxs-lookup"><span data-stu-id="75895-132">This step will enable Windows authentication to work seamlessly, without users being prompted for credentials.</span></span> <span data-ttu-id="75895-133">アプリを追加するには、「構成可能な設定 [」リファレンスの](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) 「信頼できる [サイト」を参照してください](../working-with-managed-desktop/config-setting-ref.md)。</span><span class="sxs-lookup"><span data-stu-id="75895-133">To add apps, refer to [Trusted sites](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) in the [Configurable settings reference](../working-with-managed-desktop/config-setting-ref.md).</span></span>

- <span data-ttu-id="75895-134">Active Directory フェデレーション サービスを使用している場合は、「FS でのシングル サインオンの確認と管理」の手順を使用して SSO が有効AD [します](/previous-versions/azure/azure-services/jj151809(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="75895-134">If you are using Active Directory Federated Services, check that SSO is enabled by using the steps in [Verify and manage single sign-on with AD FS](/previous-versions/azure/azure-services/jj151809(v=azure.100)).</span></span> 

- <span data-ttu-id="75895-135">オンプレミス **で古い** プロトコルを使用するアプリの場合、デバイスが認証のためにオンプレミスのドメイン コントローラーにアクセスできる限り、追加のセットアップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="75895-135">For apps that are **on-premises and use older protocols**, no extra setup is required, as long as the devices have access to an on-premises domain controller to authenticate.</span></span> <span data-ttu-id="75895-136">ただし、これらのアプリケーションにセキュリティで保護されたアクセスを提供するには、Azure ADアプリケーション プロキシを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75895-136">To provide secure access for these applications, however, you should deploy Azure AD Application Proxy.</span></span> <span data-ttu-id="75895-137">詳細については、「Azure Active Directory のアプリケーション プロキシを介したオンプレミス アプリケーションへのリモート アクセス」 [を参照してください](/azure/active-directory/manage-apps/application-proxy)。</span><span class="sxs-lookup"><span data-stu-id="75895-137">For more information, see [Remote access to on-premises applications through Azure Active Directory's Application Proxy](/azure/active-directory/manage-apps/application-proxy).</span></span>

- <span data-ttu-id="75895-138">オンプレミスで **実行され、** コンピューター認証に依存するアプリはサポートされていないので、新しいバージョンへの置き換えも検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75895-138">Apps that run **on-premises and rely on machine authentication** aren't supported, so you should consider replacing them with newer versions.</span></span>

### <a name="network-shares-that-use-authentication"></a><span data-ttu-id="75895-139">認証を使用するネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="75895-139">Network shares that use authentication</span></span>

<span data-ttu-id="75895-140">UNC パスを使用してデバイスがオンプレミスのドメイン コントローラーにアクセスできる限り、ユーザーがネットワーク共有にアクセスするには、追加のセットアップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="75895-140">No extra setup is required for users to access network shares, as long as the devices have access to an on-premises domain controller by using a UNC path.</span></span>

### <a name="printers"></a><span data-ttu-id="75895-141">プリンター</span><span class="sxs-lookup"><span data-stu-id="75895-141">Printers</span></span>

<span data-ttu-id="75895-142">ハイブリッド クラウド印刷を構成しない限り、Microsoft Managed Desktop デバイスは、オンプレミスの Active Directory に発行されたプリンター [に接続できません](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。</span><span class="sxs-lookup"><span data-stu-id="75895-142">Microsoft Managed Desktop devices cannot connect to printers that are published to your on-premises Active Directory unless you have configured [Hybrid Cloud Print](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>

<span data-ttu-id="75895-143">クラウド専用環境ではプリンターを自動的に検出することはできませんが、ユーザーは、デバイスがオンプレミスのドメイン コントローラーにアクセスできる限り、プリンター パスまたはプリンター キュー パスを使用してオンプレミスプリンターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="75895-143">While printers can't be automatically discovered in a cloud only environment, your users can use on-premises printers by using the printer path or printer queue path, as long as the devices have access to an on-premises domain controller.</span></span>

<!--add fuller material on printers when available-->