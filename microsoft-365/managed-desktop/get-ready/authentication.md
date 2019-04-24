---
title: Microsoft マネージドデスクトップへのオンプレミスリソースアクセスの準備
description: Azure ad が認証を提供するためにオンプレミスの ad と通信できることを確認するための重要な手順
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: c4ebe0c7ad3d1e197cf90cc975366df61d3b0cb5
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276918"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a><span data-ttu-id="00471-104">Microsoft マネージドデスクトップへのオンプレミスリソースアクセスの準備</span><span class="sxs-lookup"><span data-stu-id="00471-104">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>

<span data-ttu-id="00471-105">Microsoft マネージドデスクトップでは、デバイスは自動的に azure Active Directory (azure AD) に参加します。</span><span class="sxs-lookup"><span data-stu-id="00471-105">In Microsoft Managed Desktop, devices are automatically joined to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="00471-106">これは、オンプレミスの active directory を使用している場合に、Azure AD に参加しているデバイスがオンプレミスの active directory と通信できることを確認するために、いくつかのことを確認する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="00471-106">This means that if you are using an on-premises Active Directory, you'll have to check some things to ensure that devices joined to Azure AD can communicate with your on-premises Active Directory.</span></span> 

> [!NOTE]  
> <span data-ttu-id="00471-107">*ハイブリッド*Azure AD join は、Microsoft マネージドデスクトップではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="00471-107">*Hybrid* Azure AD join is not supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="00471-108">Azure Active Directory では、ユーザーはシングルサインオン (SSO) を利用できます。これは、通常、リソースを使用するたびに資格情報を提供する必要がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="00471-108">Azure Active Directory lets your users take advantage of Single Sign-On (SSO), which means they typically won't have to provide credentials every time they use resources.</span></span>

<span data-ttu-id="00471-109">azure Active Directory への参加の詳細については、「 [How to: Plan for azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00471-109">For information about joining Azure Active Directory, refer to [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).</span></span> <span data-ttu-id="00471-110">azure ad に参加しているデバイスのシングルサインオン (sso) に関する背景情報については、「azure ad に参加している[デバイスでの sso とオンプレミスのリソースのしくみ](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00471-110">For background information about Single Sign-On (SSO) on devices joined to Azure AD, see [How SSO to on-premises resources works on Azure AD joined devices](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).</span></span>


<span data-ttu-id="00471-111">このトピックでは、ローカルの Active Directory 接続に依存するアプリとその他のリソースが、Microsoft マネージドデスクトップで円滑に動作するようにするために確認する必要がある事柄について説明します。</span><span class="sxs-lookup"><span data-stu-id="00471-111">This topic explains the things you need to check in order to ensure that apps and other resources that depend on local Active Directory connectivity will work smoothly with Microsoft Managed Desktop.</span></span>


## <a name="single-sign-on-for-on-premises-resources"></a><span data-ttu-id="00471-112">オンプレミスのリソースのシングルサインオン</span><span class="sxs-lookup"><span data-stu-id="00471-112">Single Sign-On for on-premises resources</span></span>

<span data-ttu-id="00471-113">UPN とパスワードを使用したシングルサインオン (SSO) は、Microsoft マネージドデスクトップデバイスでは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="00471-113">Single Sign-On (SSO) by using UPN and password is enabled by default on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="00471-114">ただし、ユーザーは Windows Hello for business を使用することもできます。これには、いくつかのセットアップ手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="00471-114">But your users can also use Windows Hello for Business, which requires some extra setup steps.</span></span> 

### <a name="single-sign-on-by-using-upn-and-password"></a><span data-ttu-id="00471-115">UPN とパスワードを使用したシングルサインオン</span><span class="sxs-lookup"><span data-stu-id="00471-115">Single Sign-On by using UPN and password</span></span>

<span data-ttu-id="00471-116">ほとんどの組織では、ユーザーは SSO を使用して、Microsoft マネージドデスクトップデバイス上の UPN とパスワードによる認証を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="00471-116">In most organizations, your users will be able to use SSO to authenticate by UPN and password on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="00471-117">ただし、これが正常に動作することを確認するには、次の点を再度確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00471-117">However, to make sure this will work, you should double-check the following:</span></span>

- <span data-ttu-id="00471-118">Azure AD Connect がセットアップされており、Windows server 2008 R2 以降を実行しているオンプレミスの Active Directory サーバーを使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="00471-118">Confirm that Azure AD Connect is set up and uses an on-premises Active Directory server running Windows Server 2008 R2 or later.</span></span>
- <span data-ttu-id="00471-119">azure ad Connect でサポートされているバージョンが実行されており、次の3つの属性を azure ad と同期するように設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="00471-119">Confirm that Azure AD Connect is running a supported version and is set to sync these three attributes with Azure AD:</span></span> 
    - <span data-ttu-id="00471-120">オンプレミスの Active Directory の DNS ドメイン名 (エンドユーザーが配置されている場所)</span><span class="sxs-lookup"><span data-stu-id="00471-120">DNS domain name of the on-premises Active Directory (where the end-users are located)</span></span>
    - <span data-ttu-id="00471-121">オンプレミスの Active Directory の NetBIOS (エンドユーザーが配置されている場所)</span><span class="sxs-lookup"><span data-stu-id="00471-121">NetBIOS of your on-premises Active Directory (where the end-users are located)</span></span>
    - <span data-ttu-id="00471-122">ユーザーの SAM アカウント名</span><span class="sxs-lookup"><span data-stu-id="00471-122">SAM account name of the user</span></span>


### <a name="single-sign-on-by-using-windows-hello-for-business"></a><span data-ttu-id="00471-123">Windows Hello for business を使用したシングルサインオン</span><span class="sxs-lookup"><span data-stu-id="00471-123">Single Sign-On by using Windows Hello for Business</span></span>

<span data-ttu-id="00471-124">Microsoft マネージドデスクトップデバイスでは、Windows Hello for business を使用することで、ユーザーにすばやくパスワードを提供することがなくなります。</span><span class="sxs-lookup"><span data-stu-id="00471-124">Microsoft Managed Desktop devices also offer your users a fast, passwordless experience by employing Windows Hello for Business.</span></span> <span data-ttu-id="00471-125">ユーザーがそれぞれの UPN とパスワードを提供しなくても、windows hello for business が動作することを確認するには、「 [windows hello for business を使用して、オンプレミスのシングルサインオン用に Azure AD に参加しているデバイスを構成](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)する」を参照して、要件を確認してから、記載されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="00471-125">To ensure Windows Hello for Business will work without your users having to provide respective UPN and password, visit [Configure Azure AD joined devices for On-premises Single-Sign On using Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) to check the requirements, and then follow the steps provided there.</span></span>


## <a name="apps-and-resources-that-use-authentication"></a><span data-ttu-id="00471-126">認証を使用するアプリとリソース</span><span class="sxs-lookup"><span data-stu-id="00471-126">Apps and resources that use authentication</span></span>

<span data-ttu-id="00471-127">azure Active Directory と連携するようにアプリをセットアップするための詳細なガイダンスについては、「azure コンテンツセットの[アプリケーションとリソースに関する考慮事項](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00471-127">Refer to [Understand considerations for applications and resources](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in the Azure content set for full guidance on setting up apps to work with Azure Active Directory.</span></span> <span data-ttu-id="00471-128">概要:</span><span class="sxs-lookup"><span data-stu-id="00471-128">In summary:</span></span>


- <span data-ttu-id="00471-129">Azure AD app gallery に追加されたものなど、**クラウドベースのアプリ**を使用している場合、多くの場合、Microsoft マネージドデスクトップを操作するための準備は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="00471-129">If you use **cloud-based apps**, such as those added to the Azure AD app gallery, most don't require any further preparation to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="00471-130">ただし、Web アカウントマネージャー (WAM) を使用していない Win32 アプリでも、ユーザーに対して認証を求めるメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="00471-130">However, any Win32 apps that don't use Web Account Manager (WAM) might still prompt users for authentication.</span></span>

- <span data-ttu-id="00471-131">**オンプレミスでホスト**されているアプリの場合は、それらのアプリをブラウザーの信頼済みサイトの一覧に追加してください。</span><span class="sxs-lookup"><span data-stu-id="00471-131">For apps that are **hosted on-premises**, be sure to add those apps to the trusted sites list in your browsers.</span></span> <span data-ttu-id="00471-132">これにより、ユーザーが資格情報の入力を求められることなく、Windows 認証がシームレスに動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="00471-132">This will enable Windows authentication to work seamlessly, without users being prompted for credentials.</span></span> <span data-ttu-id="00471-133">これを行うには、[構成可能な設定のリファレンス](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref)で、[[信頼済みサイト](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites)] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00471-133">To do this, refer to [Trusted sites](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) in the [Configurable settings reference](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref).</span></span>

- <span data-ttu-id="00471-134">Active Directory フェデレーションサービスを使用している場合は、「AD FS を使用して[シングルサインオンを確認および管理](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))する」の手順を使用して、SSO が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="00471-134">If you are using Active Directory Federated Services, check that SSO is enabled by using the steps in [Verify and manage single sign-on with AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)).</span></span> 

- <span data-ttu-id="00471-135">**オンプレミス**のアプリで古いプロトコルを使用する場合、デバイスが認証のためにオンプレミスのドメインコントローラーにアクセスできる限り、特別なセットアップは不要です。</span><span class="sxs-lookup"><span data-stu-id="00471-135">For apps that are **on-premises and use older protocols**, no extra setup is required, as long as the devices have access to an on-premises domain controller to authenticate.</span></span> <span data-ttu-id="00471-136">ただし、これらのアプリケーションにセキュリティで保護されたアクセスを提供するには、Azure AD アプリケーションプロキシを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00471-136">To provide secure access for these applications, however, you should deploy Azure AD Application Proxy.</span></span> <span data-ttu-id="00471-137">詳細については、「 [Azure Active Directory のアプリケーションプロキシを使用したオンプレミスアプリケーションへのリモートアクセス](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00471-137">For more information, see [Remote access to on-premises applications through Azure Active Directory's Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

- <span data-ttu-id="00471-138">オンプレミスで実行され、**コンピューター認証に依存**するアプリはサポートされていないため、これらを新しいバージョンに置き換えることを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00471-138">Apps that run **on-premises and rely on machine authentication** aren't supported, so you should consider replacing these with newer versions.</span></span>

### <a name="network-shares-that-use-authentication"></a><span data-ttu-id="00471-139">認証を使用するネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="00471-139">Network shares that use authentication</span></span>

<span data-ttu-id="00471-140">デバイスが UNC パスを使用してオンプレミスのドメインコントローラーにアクセスできる限り、ユーザーがネットワーク共有にアクセスするための特別なセットアップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="00471-140">No extra setup is required for users to access network shares, as long as the devices have access to an on-premises domain controller by using a UNC path.</span></span>

### <a name="printers"></a><span data-ttu-id="00471-141">プリンター</span><span class="sxs-lookup"><span data-stu-id="00471-141">Printers</span></span>

<span data-ttu-id="00471-142">Microsoft マネージドデスクトップデバイスは、[ハイブリッドクラウド印刷](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)を構成していない限り、オンプレミスの Active Directory に公開されているプリンターに接続することはできません。</span><span class="sxs-lookup"><span data-stu-id="00471-142">Microsoft Managed Desktop devices cannot connect to printers that are published to your on-premises Active Directory unless you have configured [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>

<span data-ttu-id="00471-143">プリンターをクラウドのみの環境で自動的に検出することはできませんが、デバイスがオンプレミスのドメインコントローラーにアクセスできる限り、ユーザーはプリンターのパスまたはプリンターキューのパスを使用してオンプレミスのプリンターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="00471-143">While printers can't be automatically discovered in a cloud only environment, your users can use on-premises printers by using the printer path or printer queue path, as long as the devices have access to an on-premises domain controller.</span></span>

<!--add fuller material on printers when available-->
