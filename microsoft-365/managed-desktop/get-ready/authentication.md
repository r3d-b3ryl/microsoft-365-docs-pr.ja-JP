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
audience: Admin
ms.openlocfilehash: 6df23e0d7e3ea0ecd7ebacd96f00cb47b9e0aa84
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574597"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a><span data-ttu-id="237f9-104">Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する</span><span class="sxs-lookup"><span data-stu-id="237f9-104">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>

<span data-ttu-id="237f9-105">このMicrosoft マネージド デスクトップデバイスは自動的に (Azure Azure Active Directory) AD。</span><span class="sxs-lookup"><span data-stu-id="237f9-105">In Microsoft Managed Desktop, devices are automatically joined to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="237f9-106">このため、オンプレミスの Active Directory を使用している場合は、Azure AD に参加しているデバイスがオンプレミスの Active Directory と通信できるよう、いくつかのことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="237f9-106">For this reason, if you are using an on-premises Active Directory, you'll have to check some things to ensure that devices joined to Azure AD can communicate with your on-premises Active Directory.</span></span> 

> [!NOTE]  
> <span data-ttu-id="237f9-107">*ハイブリッド* Azure AD参加は、ユーザーがサポートMicrosoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="237f9-107">*Hybrid* Azure AD join is not supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="237f9-108">Azure Active Directoryを使用すると、ユーザーはシングル Sign-On (SSO) を利用できます。つまり、通常、ユーザーはリソースを使用する度に資格情報を提供する必要がなされます。</span><span class="sxs-lookup"><span data-stu-id="237f9-108">Azure Active Directory lets your users take advantage of Single Sign-On (SSO), which means they typically won't have to provide credentials every time they use resources.</span></span>

<span data-ttu-id="237f9-109">参加方法の詳細[Azure Active Directory、「How to: Plan your Azure AD実装」を参照してください](/azure/active-directory/devices/azureadjoin-plan)。</span><span class="sxs-lookup"><span data-stu-id="237f9-109">For information about joining Azure Active Directory, refer to [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).</span></span> <span data-ttu-id="237f9-110">Azure AD に参加しているデバイスでのシングル Sign-On (SSO) のバックグラウンド情報については [、「Azure](/azure/active-directory/devices/azuread-join-sso#how-it-works)AD 参加デバイスでのオンプレミス リソースへの SSO の動作」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="237f9-110">For background information about Single Sign-On (SSO) on devices joined to Azure AD, see [How SSO to on-premises resources works on Azure AD joined devices](/azure/active-directory/devices/azuread-join-sso#how-it-works).</span></span>


<span data-ttu-id="237f9-111">この記事では、ローカルの Active Directory 接続に依存するアプリや他のリソースが、ローカル Active Directory 接続でスムーズに動作するために確認する必要があるMicrosoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="237f9-111">This article explains the things you need to check in order to ensure that apps and other resources that depend on local Active Directory connectivity will work smoothly with Microsoft Managed Desktop.</span></span>


## <a name="single-sign-on-for-on-premises-resources"></a><span data-ttu-id="237f9-112">オンプレミス Sign-Onの単一のリソース</span><span class="sxs-lookup"><span data-stu-id="237f9-112">Single Sign-On for on-premises resources</span></span>

<span data-ttu-id="237f9-113">UPN Sign-Onを使用したシングル Sign-On (SSO) は、デバイスで既定でMicrosoft マネージド デスクトップされます。</span><span class="sxs-lookup"><span data-stu-id="237f9-113">Single Sign-On (SSO) by using UPN and password is enabled by default on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="237f9-114">ただし、ユーザーは Hello for Business Windowsを使用できます。追加のセットアップ手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="237f9-114">But your users can also use Windows Hello for Business, which requires some extra setup steps.</span></span> 

### <a name="single-sign-on-by-using-upn-and-password"></a><span data-ttu-id="237f9-115">UPN Sign-Onパスワードを使用した単一のデバイス</span><span class="sxs-lookup"><span data-stu-id="237f9-115">Single Sign-On by using UPN and password</span></span>

<span data-ttu-id="237f9-116">ほとんどの組織では、ユーザーは SSO を使用して、デバイス上の UPN とパスワードMicrosoft マネージド デスクトップできます。</span><span class="sxs-lookup"><span data-stu-id="237f9-116">In most organizations, your users will be able to use SSO to authenticate by UPN and password on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="237f9-117">ただし、この関数が動作する場合は、次の機能を確認してください。</span><span class="sxs-lookup"><span data-stu-id="237f9-117">However, to make sure this function will work, you should double-check the following things:</span></span>

- <span data-ttu-id="237f9-118">Azure AD Connectがセットアップされ、サーバー 2008 R2 以降で実行されているオンプレミスの Active Directory サーバー Windows使用します。</span><span class="sxs-lookup"><span data-stu-id="237f9-118">Confirm that Azure AD Connect is set up and uses an on-premises Active Directory server running Windows Server 2008 R2 or later.</span></span>
- <span data-ttu-id="237f9-119">Azure AD Connectがサポートされているバージョンを実行し、これらの 3 つの属性を Azure サーバーと同期するようにAD。</span><span class="sxs-lookup"><span data-stu-id="237f9-119">Confirm that Azure AD Connect is running a supported version and is set to sync these three attributes with Azure AD:</span></span> 
    - <span data-ttu-id="237f9-120">DNS ドメイン Active Directory の名前 (ユーザーが存在する場所)</span><span class="sxs-lookup"><span data-stu-id="237f9-120">DNS domain name of the on-premises Active Directory (where the users are located)</span></span>
    - <span data-ttu-id="237f9-121">オンプレミスの Active Directory の NetBIOS (ユーザーが存在する場所)</span><span class="sxs-lookup"><span data-stu-id="237f9-121">NetBIOS of your on-premises Active Directory (where the users are located)</span></span>
    - <span data-ttu-id="237f9-122">ユーザーの SAM アカウント名</span><span class="sxs-lookup"><span data-stu-id="237f9-122">SAM account name of the user</span></span>


### <a name="single-sign-on-by-using-windows-hello-for-business"></a><span data-ttu-id="237f9-123">Hello for Business Sign-Onを使用Windows単一のユーザー</span><span class="sxs-lookup"><span data-stu-id="237f9-123">Single Sign-On by using Windows Hello for Business</span></span>

<span data-ttu-id="237f9-124">Microsoft マネージド デスクトップデバイスは、Hello for Business を採用することで、ユーザーにパスワードを使用しない高速Windowsを提供します。</span><span class="sxs-lookup"><span data-stu-id="237f9-124">Microsoft Managed Desktop devices also offer your users a fast, passwordless experience by employing Windows Hello for Business.</span></span> <span data-ttu-id="237f9-125">Windows Hello for Business が、ユーザーがそれぞれの UPN とパスワードを指定せずに動作するようにするには、「Azure AD に参加しているデバイスをオンプレミス用に構成する Single-Sign On using [Windows Hello for Business」](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)を参照して要件を確認し、次に示す手順に従います。</span><span class="sxs-lookup"><span data-stu-id="237f9-125">To ensure Windows Hello for Business will work without your users having to provide respective UPN and password, visit [Configure Azure AD joined devices for On-premises Single-Sign On using Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) to check the requirements, and then follow the steps provided there.</span></span>


## <a name="apps-and-resources-that-use-authentication"></a><span data-ttu-id="237f9-126">認証を使用するアプリとリソース</span><span class="sxs-lookup"><span data-stu-id="237f9-126">Apps and resources that use authentication</span></span>

<span data-ttu-id="237f9-127">詳細については[、「Azure コンテンツ セット内](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources)のアプリケーションとリソースに関する考慮事項を理解する」を参照して、アプリケーションを使用して動作するようにアプリを設定Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="237f9-127">Refer to [Understand considerations for applications and resources](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in the Azure content set for full guidance on setting up apps to work with Azure Active Directory.</span></span> <span data-ttu-id="237f9-128">まとめると、以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="237f9-128">In summary:</span></span>


- <span data-ttu-id="237f9-129">Azure ADアプリ ギャラリーに追加されたアプリなど、クラウドベースのアプリを使用する場合、ほとんどの場合、Microsoft マネージド デスクトップ を操作するためにそれ以上の準備は必要Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="237f9-129">If you use **cloud-based apps**, such as those added to the Azure AD app gallery, most don't require any further preparation to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="237f9-130">ただし、Web アカウント マネージャー (WAM) を使用しない Win32 アプリでは、ユーザーに認証を求めるメッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="237f9-130">However, any Win32 apps that don't use Web Account Manager (WAM) might still prompt users for authentication.</span></span>

- <span data-ttu-id="237f9-131">オンプレミスでホストされている **アプリの場合は**、ブラウザーの信頼できるサイトの一覧にアプリを必ず追加してください。</span><span class="sxs-lookup"><span data-stu-id="237f9-131">For apps that are **hosted on-premises**, be sure to add those apps to the trusted sites list in your browsers.</span></span> <span data-ttu-id="237f9-132">この手順では、ユーザー Windows求めることなく、認証をシームレスに動作できます。</span><span class="sxs-lookup"><span data-stu-id="237f9-132">This step will enable Windows authentication to work seamlessly, without users being prompted for credentials.</span></span> <span data-ttu-id="237f9-133">アプリを追加するには、「構成可能な設定 [」リファレンスの](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) 「信頼できる [サイト」を参照してください](../working-with-managed-desktop/config-setting-ref.md)。</span><span class="sxs-lookup"><span data-stu-id="237f9-133">To add apps, refer to [Trusted sites](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) in the [Configurable settings reference](../working-with-managed-desktop/config-setting-ref.md).</span></span>

- <span data-ttu-id="237f9-134">Active Directory フェデレーション サービスを使用している場合は、「FS でのシングル サインオンの確認と管理」の手順を使用して SSO が有効AD [します](/previous-versions/azure/azure-services/jj151809(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="237f9-134">If you are using Active Directory Federated Services, check that SSO is enabled by using the steps in [Verify and manage single sign-on with AD FS](/previous-versions/azure/azure-services/jj151809(v=azure.100)).</span></span> 

- <span data-ttu-id="237f9-135">オンプレミス **で古い** プロトコルを使用するアプリの場合、デバイスが認証のためにオンプレミスのドメイン コントローラーにアクセスできる限り、追加のセットアップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="237f9-135">For apps that are **on-premises and use older protocols**, no extra setup is required, as long as the devices have access to an on-premises domain controller to authenticate.</span></span> <span data-ttu-id="237f9-136">ただし、これらのアプリケーションにセキュリティで保護されたアクセスを提供するには、Azure ADアプリケーション プロキシを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="237f9-136">To provide secure access for these applications, however, you should deploy Azure AD Application Proxy.</span></span> <span data-ttu-id="237f9-137">詳細については、「アプリケーション プロキシを介したオンプレミス アプリケーションへのリモート アクセス[Azure Active Directoryを参照してください](/azure/active-directory/manage-apps/application-proxy)。</span><span class="sxs-lookup"><span data-stu-id="237f9-137">For more information, see [Remote access to on-premises applications through Azure Active Directory's Application Proxy](/azure/active-directory/manage-apps/application-proxy).</span></span>

- <span data-ttu-id="237f9-138">オンプレミスで **実行され、** コンピューター認証に依存するアプリはサポートされていないので、新しいバージョンへの置き換えも検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="237f9-138">Apps that run **on-premises and rely on machine authentication** aren't supported, so you should consider replacing them with newer versions.</span></span>

### <a name="network-shares-that-use-authentication"></a><span data-ttu-id="237f9-139">認証を使用するネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="237f9-139">Network shares that use authentication</span></span>

<span data-ttu-id="237f9-140">UNC パスを使用してデバイスがオンプレミスのドメイン コントローラーにアクセスできる限り、ユーザーがネットワーク共有にアクセスするには、追加のセットアップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="237f9-140">No extra setup is required for users to access network shares, as long as the devices have access to an on-premises domain controller by using a UNC path.</span></span>

### <a name="printers"></a><span data-ttu-id="237f9-141">プリンター</span><span class="sxs-lookup"><span data-stu-id="237f9-141">Printers</span></span>

<span data-ttu-id="237f9-142">Microsoft マネージド デスクトップハイブリッド クラウド印刷を構成しない限り、オンプレミスの Active Directory に発行されたプリンターにデバイス[を接続できません](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。</span><span class="sxs-lookup"><span data-stu-id="237f9-142">Microsoft Managed Desktop devices cannot connect to printers that are published to your on-premises Active Directory unless you have configured [Hybrid Cloud Print](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>

<span data-ttu-id="237f9-143">クラウド専用環境ではプリンターを自動的に検出することはできませんが、ユーザーは、デバイスがオンプレミスのドメイン コントローラーにアクセスできる限り、プリンター パスまたはプリンター キュー パスを使用してオンプレミスプリンターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="237f9-143">While printers can't be automatically discovered in a cloud only environment, your users can use on-premises printers by using the printer path or printer queue path, as long as the devices have access to an on-premises domain controller.</span></span>

<!--add fuller material on printers when available-->
## <a name="steps-to-get-ready"></a><span data-ttu-id="237f9-144">準備の手順</span><span class="sxs-lookup"><span data-stu-id="237f9-144">Steps to get ready</span></span>

1. <span data-ttu-id="237f9-145">詳細については[、「前提条件」をMicrosoft マネージド デスクトップ。](prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="237f9-145">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="237f9-146">準備 [状況評価ツールを使用します](readiness-assessment-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="237f9-146">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="237f9-147">ゲスト アカウントの前提条件</span><span class="sxs-lookup"><span data-stu-id="237f9-147">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="237f9-148">Microsoft マネージド デスクトップのネットワーク構成</span><span class="sxs-lookup"><span data-stu-id="237f9-148">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="237f9-149">Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する</span><span class="sxs-lookup"><span data-stu-id="237f9-149">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. <span data-ttu-id="237f9-150">[オンプレミス のリソース アクセスを](authentication.md)Microsoft マネージド デスクトップする (この記事)</span><span class="sxs-lookup"><span data-stu-id="237f9-150">[Prepare on-premises resources access for Microsoft Managed Desktop](authentication.md) (This article)</span></span>
7. [<span data-ttu-id="237f9-151">Microsoft マネージド デスクトップのアプリ</span><span class="sxs-lookup"><span data-stu-id="237f9-151">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="237f9-152">Microsoft マネージド デスクトップ用に、マップされたドライブを準備する</span><span class="sxs-lookup"><span data-stu-id="237f9-152">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="237f9-153">Microsoft マネージド デスクトップ用に、印刷リソースを準備する</span><span class="sxs-lookup"><span data-stu-id="237f9-153">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
