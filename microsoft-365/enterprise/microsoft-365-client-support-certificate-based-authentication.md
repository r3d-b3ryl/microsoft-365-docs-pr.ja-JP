---
title: 'Microsoft 365 クライアント アプリのサポート: 証明書ベース認証'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: この記事では、証明書ベースの認証に対する Microsoft 365 クライアント アプリのサポートの詳細について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5ebef7c10aa61ba28c8fb841468be244f6e8542
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905001"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a><span data-ttu-id="6cfd4-103">Microsoft 365 クライアント アプリのサポート: 証明書ベース認証</span><span class="sxs-lookup"><span data-stu-id="6cfd4-103">Microsoft 365 Client App Support: Certificate-based Authentication</span></span>

<span data-ttu-id="6cfd4-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="6cfd4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6cfd4-105">最新の認証は、認証と承認方法の組み合わせの傘下の用語です。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-105">Modern authentication is an umbrella term for a combination of authentication and authorization methods.</span></span> <span data-ttu-id="6cfd4-106">以下のようなメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-106">These methods include:</span></span>

- <span data-ttu-id="6cfd4-107">**認証方法**: 多要素認証。クライアント証明書ベースの認証。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-107">**Authentication methods**: Multi-factor Authentication; Client Certificate-based authentication.</span></span>
- <span data-ttu-id="6cfd4-108">**承認方法**: Microsoft による Open Authorization (OAuth) の実装。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-108">**Authorization methods**: Microsoft's implementation of Open Authorization (OAuth).</span></span>

<span data-ttu-id="6cfd4-109">Active Directory 認証ライブラリ (ADAL) や Microsoft 認証ライブラリ (MSAL) など、認証ライブラリを使用して、最新の認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-109">Modern authentication is enabled by using an authentication library, like Active Directory Authentication Library (ADAL) or Microsoft Authentication Library (MSAL).</span></span> <span data-ttu-id="6cfd4-110">最新の認証とは、クライアントが Microsoft 365 リソースへのアクセスを認証および承認するために使用する認証です。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-110">Modern authentication is what clients use to authenticate and authorize access to Microsoft 365 resources.</span></span> <span data-ttu-id="6cfd4-111">最新の認証では、OAuth を使用し、ユーザー資格情報へのアクセスを必要とせずに、クライアントが Microsoft 365 サービスにアクセスするための安全なメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-111">Modern authentication uses OAuth and provides a secure mechanism for clients to access Microsoft 365 services, without requiring access to user credentials.</span></span> <span data-ttu-id="6cfd4-112">サインイン時に、ユーザーは Azure Active Directory で直接認証を行い、その代りアクセス/更新トークンのペアを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-112">At sign-in, the user authenticates directly with Azure Active Directory and receives an access/refresh token pair in return.</span></span> <span data-ttu-id="6cfd4-113">アクセス トークンは、Microsoft 365 テナント内の適切なリソースへのクライアント アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-113">The access token grants the client access to the appropriate resources in the Microsoft 365 tenant.</span></span> <span data-ttu-id="6cfd4-114">更新トークンは、現在のアクセス トークンの有効期限が切れたときに、新しいアクセス トークンまたは更新トークンのペアを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-114">A refresh token is used to obtain a new access or refresh token pair when the current access token expires.</span></span>

<span data-ttu-id="6cfd4-115">最新の認証では、証明書ベースの認証など、さまざまな認証メカニズムがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-115">Modern authentication supports different authentication mechanisms, like certificate-based authentication.</span></span> <span data-ttu-id="6cfd4-116">Windows、Android、または iOS デバイス上のクライアントは、証明書ベース認証 (CBA) を使用して、デバイス上のクライアント証明書を使用して Azure Active Directory に対して認証できます。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-116">Clients on Windows, Android, or iOS devices can use certificate-based authentication (CBA) to authenticate to Azure Active Directory using a client certificate on the device.</span></span> <span data-ttu-id="6cfd4-117">一般的なユーザー名/パスワードの代わりに、証明書を使用して Azure Active Directory からアクセス/更新トークンのペアを取得します。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-117">Instead of a typical username/password, the certificate is used to obtain an access/refresh token pair from Azure Active Directory.</span></span>

<span data-ttu-id="6cfd4-118">証明書ベースの [認証の詳細については、次のページを参照してください](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-118">Learn more about [certificate-based authentication](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="6cfd4-119">サポートされているクライアント&プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="6cfd4-119">Supported clients & platforms</span></span>

<span data-ttu-id="6cfd4-120">次のクライアントとプラットフォームの最新バージョンでは、クライアント内の Azure Active Directory アカウントにサインインするときに証明書ベースの認証がサポートされます (たとえば、アプリにアカウントを追加する場合)。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-120">The latest versions of the following clients and platforms support certificate-based authentication when signing into Azure Active Directory accounts within the client (for example, when adding an account to the app).</span></span> <span data-ttu-id="6cfd4-121">Microsoft 365 でのプラットフォームサポートの詳細については [、「Microsoft 365](/microsoft-365/microsoft-365-and-office-resources)のシステム要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-121">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Certificate-based authentication services support table](../includes/microsoft-365-client-support-certificate-based-authentication-include.md)]

>[!NOTE]
><span data-ttu-id="6cfd4-122">iOS と Android のエッジは、アカウントの追加フロー中に証明書ベースの認証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-122">Edge for iOS and Android supports certificate-based authentication during account add flows.</span></span> <span data-ttu-id="6cfd4-123">iOS と Android のエッジは、通常はイントラネット サイトである Web サイトに対して認証を実行する場合、証明書ベースの認証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-123">Edge for iOS and Android does not support certificate-based authentication when performing authentication against web sites, which are typically intranet sites.</span></span> <br><br>  <span data-ttu-id="6cfd4-124">このシナリオでは、ユーザーは Web サイト (通常はイントラネット上) に移動し、Web サイトはユーザーに証明書による認証を要求します。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-124">In this scenario, a user navigates to a web site (usually on the intranet) where the web site requires the user to authenticate via a certificate.</span></span> <span data-ttu-id="6cfd4-125">これは、最新の認証を全く伴うのではなく、Microsoft 認証ライブラリを活用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-125">This does not involve modern authentication at all and does not leverage a Microsoft authentication library.</span></span> <span data-ttu-id="6cfd4-126">これは、iOS の制限による影響です。iOS は、サード パーティ製アプリが証明書が保存されているシステムキーチェーンにアクセスするのを防止します (Apple アプリと [Safari Webview](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) コントローラーだけがシステムキーチェーンにアクセスできます)。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-126">This is due to a limitation with iOS: iOS prevents third-party apps from accessing the system keychain where the certificates are stored (only Apple apps and the [Safari webview controller](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) can access the system keychain).</span></span> <br><br> <span data-ttu-id="6cfd4-127">Edge は [WebKit](https://developer.apple.com/documentation/webkit) フレームワークを使用して Web サイトをレンダリングします。Edge はシステムキーチェーンにアクセスできず、証明書の選択肢をユーザーに提示できません。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-127">As Edge relies on the [WebKit](https://developer.apple.com/documentation/webkit) framework for rendering web sites, Edge is unable to access the system keychain and present the user with a certificate choice.</span></span> <span data-ttu-id="6cfd4-128">これは、残念ながら、Apple のアーキテクチャによる設計です。</span><span class="sxs-lookup"><span data-stu-id="6cfd4-128">This, unfortunately, is by design due to Apple's architecture.</span></span>

## <a name="supported-powershell-modules"></a><span data-ttu-id="6cfd4-129">サポートされている PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="6cfd4-129">Supported PowerShell modules</span></span>

- [<span data-ttu-id="6cfd4-130">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="6cfd4-130">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="6cfd4-131">Exchange Online の PowerShell</span><span class="sxs-lookup"><span data-stu-id="6cfd4-131">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="6cfd4-132">SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="6cfd4-132">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

