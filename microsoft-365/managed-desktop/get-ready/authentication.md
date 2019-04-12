---
title: Microsoft マネージドデスクトップへのオンプレミスリソースアクセスの準備
description: Azure ad が認証を提供するためにオンプレミスの ad と通信できることを確認するための重要な手順
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0f9cbe6712b8d16f435cfdf5fd84875656fa9c2e
ms.sourcegitcommit: ef589025820ddf6edb5f454826b1c12c9bcb8e49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2019
ms.locfileid: "31824467"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a><span data-ttu-id="86f60-104">Microsoft マネージドデスクトップへのオンプレミスリソースアクセスの準備</span><span class="sxs-lookup"><span data-stu-id="86f60-104">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>

<span data-ttu-id="86f60-105">Microsoft マネージドデスクトップでは、デバイスは自動的に Azure Active Directory に参加します。</span><span class="sxs-lookup"><span data-stu-id="86f60-105">In Microsoft Managed Desktop, devices are automatically joined to Azure Active Directory.</span></span> <span data-ttu-id="86f60-106">これは、オンプレミスの active directory を使用している場合に、Azure AD に参加しているデバイスがオンプレミスの active directory と通信できることを確認するために、いくつかのことを確認する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="86f60-106">This means that if you are using an on-premises Active Directory, you'll have to check some things to ensure that devices joined to Azure AD can communicate with your on-premises Active Directory.</span></span> 

> [!NOTE]  
> <span data-ttu-id="86f60-107">*ハイブリッド*Azure AD join は、Microsoft マネージドデスクトップではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="86f60-107">*Hybrid* Azure AD join is not supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="86f60-108">Azure Active Directory を使用すると、ユーザーはシングルサインオン (SSO) を利用できます。これは、通常、ユーザーが何かを実行するたびに資格情報を提供する必要がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="86f60-108">Azure Active Directory lets your users take advantage of Single Sign-On (SSO), which means they typically won't have to provide credentials every time they want to do something.</span></span> <span data-ttu-id="86f60-109">azure active directory の初めての方は、「 [How to: Plan for azure ad join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)」を参照してください。ただし、azure active directory のドキュメントを参照しているため、*ハイブリッド*azure ad join は Microsoft によってサポートされていないことに注意してください。管理されたデスクトップ。</span><span class="sxs-lookup"><span data-stu-id="86f60-109">If you're completely new to Azure Active Directory, refer to [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)--however, as you reference Azure Active Directory documentation, keep in mind that *hybrid* Azure AD join is not supported by Microsoft Managed Desktop.</span></span>


<span data-ttu-id="86f60-110">このトピックでは、ローカルの Active Directory 接続に依存するアプリとその他のリソースが、Microsoft マネージドデスクトップで円滑に動作するようにするために確認する必要がある事柄について説明します。</span><span class="sxs-lookup"><span data-stu-id="86f60-110">This topic explains the things you need to check in order to ensure that apps and other resources that depend on local Active Directory connectivity will work smoothly with Microsoft Managed Desktop.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="86f60-111">ユーザーが Azure Active Directory にデバイスを登録し、Intune に登録できるようにするには、このトピックの残りの部分に進む前に、「[デバイスの設定を構成](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings)する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="86f60-111">For users to be able to register devices in Azure Active Directory and enroll in Intune (required for Microsoft Managed Desktop), follow the steps in [Configure your device settings](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) before proceeding with the rest of this topic.</span></span>


## <a name="single-sign-on-for-on-premises-resources"></a><span data-ttu-id="86f60-112">オンプレミスのリソースのシングルサインオン</span><span class="sxs-lookup"><span data-stu-id="86f60-112">Single Sign-On for on-premises resources</span></span>

<span data-ttu-id="86f60-113">UPN またはパスワード (既定の方法) を使用してデバイスのシングルサインオン (SSO) を既定で有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="86f60-113">Single Sign-On (SSO) for your devices by using UPN or passwords (the default method) should already work by default.</span></span> <span data-ttu-id="86f60-114">ただし、Windows Hello for business を使用することもできます。これには、いくつかのセットアップ手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="86f60-114">But you can also use Windows Hello for Business, which requires some extra setup steps.</span></span> <span data-ttu-id="86f60-115">sso に関する背景情報については、「Azure AD に参加している[デバイスで sso とオンプレミスのリソースがどのように機能するか](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86f60-115">For background information about SSO, see [How SSO to on-premises resources works on Azure AD joined devices](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).</span></span>


### <a name="single-sign-on-by-using-upn-and-passwords"></a><span data-ttu-id="86f60-116">UPN とパスワードを使用したシングルサインオン</span><span class="sxs-lookup"><span data-stu-id="86f60-116">Single Sign-On by using UPN and passwords</span></span>

<span data-ttu-id="86f60-117">ユーザーが UPN とパスワードによる認証を行うために特別なセットアップは必要ありません。これは、既定で Azure から取得されます。</span><span class="sxs-lookup"><span data-stu-id="86f60-117">No special setup is required for your users to authenticate by UPN and password--you get this by default from Azure.</span></span> <span data-ttu-id="86f60-118">ただし、これが正常に動作することを確認するには、次の点を再度確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86f60-118">However, to make sure this will work, you should double-check the following:</span></span>

- <span data-ttu-id="86f60-119">Azure active directory (AAD) Connect が、Windows server 2008 R2 以降を実行しているオンプレミスの Active directory サーバーでセットアップされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="86f60-119">Confirm that Azure Active Directory (AAD) Connect is set up with an on-premises Active Directory server running Windows Server 2008 R2 or later.</span></span>
- <span data-ttu-id="86f60-120">AAD Connect は、サポートされているバージョンを実行しており、次の3つのキー属性を Azure AD と同期するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="86f60-120">AAD Connect is running a supported version and is set to sync these three key attributes with Azure AD:</span></span> 
    - <span data-ttu-id="86f60-121">ユーザーが社内の Active Directory に存在する DNS ドメイン名</span><span class="sxs-lookup"><span data-stu-id="86f60-121">DNS domain name where the user is present in your on-premises Active Directory</span></span>
    - <span data-ttu-id="86f60-122">ユーザーがオンプレミスの Active Directory に存在する NetBIOS ドメイン名</span><span class="sxs-lookup"><span data-stu-id="86f60-122">NetBIOS domain name where the user is present in your on-premises Active Directory</span></span>
    - <span data-ttu-id="86f60-123">ユーザーの SAM アカウント名</span><span class="sxs-lookup"><span data-stu-id="86f60-123">SAM account name of the user</span></span>


### <a name="sso-by-using-windows-hello-for-business"></a><span data-ttu-id="86f60-124">Windows Hello for business を使用した SSO</span><span class="sxs-lookup"><span data-stu-id="86f60-124">SSO by using Windows Hello for Business</span></span>

<span data-ttu-id="86f60-125">または、Windows Hello for business を使用することで、ユーザーにすばやくパスワードを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="86f60-125">Alternately, you can offer your users a fast, passwordless experience by employing Windows Hello for Business.</span></span> <span data-ttu-id="86f60-126">これを設定するには、「 [Windows Hello for business を使用してオンプレミスのシングルサインオンで Azure AD に参加](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)しているデバイスを構成する」を参照し、要件を確認してから、そこに示されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="86f60-126">To set this up, visit [Configure Azure AD joined devices for On-premises Single-Sign On using Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) to check the requirements, and then follow the steps provided there.</span></span>


## <a name="apps-and-resources-that-use-authentication"></a><span data-ttu-id="86f60-127">認証を使用するアプリとリソース</span><span class="sxs-lookup"><span data-stu-id="86f60-127">Apps and resources that use authentication</span></span>

<span data-ttu-id="86f60-128">azure Active Directory と連携するようにアプリをセットアップするための詳細なガイダンスについては、「azure コンテンツセットの[アプリケーションとリソースに関する考慮事項](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86f60-128">Refer to [Understand considerations for applications and resources](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in the Azure content set for full guidance on setting up apps to work with Azure Active Directory.</span></span> <span data-ttu-id="86f60-129">概要:</span><span class="sxs-lookup"><span data-stu-id="86f60-129">In summary:</span></span>


- <span data-ttu-id="86f60-130">Azure AD app gallery に追加されたものなど、**クラウドベースのアプリ**を使用している場合、多くの場合、Microsoft マネージドデスクトップを操作するための準備は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="86f60-130">If you use **cloud-based apps**, such as those added to the Azure AD app gallery, most don't require any further preparation to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="86f60-131">ただし、Web アカウントマネージャー (WAM) を使用していない Win32 アプリでは、認証のためにユーザーに確認を求めることができます。</span><span class="sxs-lookup"><span data-stu-id="86f60-131">However, any Win32 apps that don't use Web Account Manager (WAM) {verify this acronym} might still prompt users for authentication.</span></span>

- <span data-ttu-id="86f60-132">**オンプレミスでホスト**されているアプリの場合は、それらのアプリをブラウザーの信頼済みサイトの一覧に追加してください。</span><span class="sxs-lookup"><span data-stu-id="86f60-132">For apps that are **hosted on-premises**, be sure to add those apps to the trusted sites list in your browsers.</span></span> <span data-ttu-id="86f60-133">これにより、ユーザーが資格情報の入力を求められることなく、Windows 認証がシームレスに動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="86f60-133">This will enable Windows authentication to work seamlessly, without users being prompted for credentials.</span></span>

- <span data-ttu-id="86f60-134">Active Directory フェデレーションサービスを使用している場合は、「 [AD FS を使用してシングルサインオンを確認および管理](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="86f60-134">If you are using Active Directory Federated Services, follow the steps in [Verify and manage single sign-on with AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)).</span></span> 

- <span data-ttu-id="86f60-135">**オンプレミス**のアプリで古いプロトコルを使用する場合、デバイスがオンプレミスのドメインコントローラーにアクセスできる限り、特別なセットアップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="86f60-135">For apps that are **on-premises and use older protocols**, no extra setup is required, as long as the devices have access to an on-premises domain controller.</span></span> <span data-ttu-id="86f60-136">ただし、これらのアプリケーションにセキュリティで保護されたアクセスを提供するには、Azure AD アプリケーションプロキシを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86f60-136">To provide secure access for these applications, however, you should deploy Azure AD Application Proxy.</span></span> <span data-ttu-id="86f60-137">詳細については、「 [Azure Active Directory のアプリケーションプロキシを使用したオンプレミスアプリケーションへのリモートアクセス](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86f60-137">For more information, see [Remote access to on-premises applications through Azure Active Directory's Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

- <span data-ttu-id="86f60-138">オンプレミスで実行され、**コンピューター認証に依存**するアプリはサポートされていないため、これらを新しいバージョンに置き換えることを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86f60-138">Apps that run **on-premises and rely on machine authentication** aren't supported, so you should consider replacing these with newer versions.</span></span>

## <a name="network-shares-that-use-authentication"></a><span data-ttu-id="86f60-139">認証を使用するネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="86f60-139">Network shares that use authentication</span></span>

<span data-ttu-id="86f60-140">デバイスが UNC パスを使用してオンプレミスのドメインコントローラーにアクセスできる限り、ユーザーがネットワーク共有にアクセスするための特別なセットアップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="86f60-140">No extra setup is required for users to access network shares, as long as the devices have access to an on-premises domain controller by using a UNC path.</span></span>

## <a name="printers"></a><span data-ttu-id="86f60-141">プリンター</span><span class="sxs-lookup"><span data-stu-id="86f60-141">Printers</span></span>

<span data-ttu-id="86f60-142">プリンターをクラウドのみの環境で自動的に検出することはできませんが、ユーザーはプリンターの UNC パスを使用して直接追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="86f60-142">While printers can't be automatically discovered in a cloud only environment, your users can also use the printers’ UNC path to directly add them.</span></span>

<!--add fuller material on printers when available-->