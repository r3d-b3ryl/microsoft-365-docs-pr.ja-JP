---
title: Contoso 社の ID
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社で、IDaaS (Identity as a Service) を活用して、従業員向けのクラウド ベース認証や、パートナーと顧客向けのフェデレーション認証を提供している方法を説明します。
ms.openlocfilehash: dea0f53ef1c3fdc2ea32256303c6120c614c904d
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754643"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="434d1-103">Contoso 社の ID</span><span class="sxs-lookup"><span data-stu-id="434d1-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="434d1-104">Microsoft は、Azure Active Directory (Azure AD) を通じて、クラウド製品全体で Id (IDaaS) をサービスとして提供します。</span><span class="sxs-lookup"><span data-stu-id="434d1-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="434d1-105">企業向けの Microsoft 365 を採用するために、Contoso IDaaS ソリューションは社内 id プロバイダーを使用し、信頼できる既存のサードパーティ id プロバイダーとのフェデレーション認証を含める必要がありました。</span><span class="sxs-lookup"><span data-stu-id="434d1-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="434d1-106">Contoso Active Directory ドメインサービスフォレスト</span><span class="sxs-lookup"><span data-stu-id="434d1-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="434d1-107">Contoso 社では \. 、世界の地域ごとに1つずつ、7つのサブドメインを持つ contoso com に対して1つの Active Directory ドメインサービス (AD DS) フォレストを使用しています。</span><span class="sxs-lookup"><span data-stu-id="434d1-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="434d1-108">本社、地域ハブ オフィス、サテライト オフィスには、ローカルの認証と承認のためのドメイン コントローラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="434d1-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="434d1-109">地域ハブを含む世界のさまざまな部分については、地域ドメインを含む Contoso フォレストを参照してください。</span><span class="sxs-lookup"><span data-stu-id="434d1-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Contoso 社の世界中のフォレストとドメイン](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="434d1-111">Contoso 社は、 \. Microsoft 365 のワークロードおよびサービスの認証と承認のために、contoso com フォレスト内のアカウントとグループを使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="434d1-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="434d1-112">Contoso 社のフェデレーション認証インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="434d1-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="434d1-113">Contoso 社では次のことが可能です。</span><span class="sxs-lookup"><span data-stu-id="434d1-113">Contoso allows:</span></span>

- <span data-ttu-id="434d1-114">お客様は、Microsoft、Facebook、または Google のメールアカウントを使用して、会社のパブリック web サイトにサインインします。</span><span class="sxs-lookup"><span data-stu-id="434d1-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="434d1-115">ベンダーおよびパートナーは、自分の LinkedIn、Salesforce、または Google のメールアカウントを使用して、会社のパートナーエクストラネットにサインインします。</span><span class="sxs-lookup"><span data-stu-id="434d1-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="434d1-p103">ここでは、パブリック web サイト、パートナーエクストラネット、および Active Directory フェデレーションサービス (AD FS) サーバーのセットを含む Contoso DMZ を示します。DMZ は、顧客、パートナー、インターネットサービスを含むインターネットに接続されています。</span><span class="sxs-lookup"><span data-stu-id="434d1-p103">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![顧客とパートナーのフェデレーション認証の Contoso サポート](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="434d1-119">DMZ の AD FS サーバーは、パブリック web サイトにアクセスし、パートナーエクストラネットにアクセスするためのパートナー資格情報を提供するために、id プロバイダーによる顧客資格情報の認証を容易にします。</span><span class="sxs-lookup"><span data-stu-id="434d1-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="434d1-p104">Contoso 社は、このインフラストラクチャを維持し、顧客とパートナーの認証に専念することを決定しました。Contoso 社の id 設計者は、このインフラストラクチャから Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) および [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) ソリューションへの変換について調査しています。</span><span class="sxs-lookup"><span data-stu-id="434d1-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication. Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="434d1-122">クラウドベース認証のためのパスワードハッシュ同期によるハイブリッドID</span><span class="sxs-lookup"><span data-stu-id="434d1-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="434d1-123">Contoso 社は、オンプレミスの AD DS フォレストを使用して、Microsoft 365 cloud resources への認証を希望しています。</span><span class="sxs-lookup"><span data-stu-id="434d1-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="434d1-124">パスワードハッシュ同期 (PHS) の使用を決定しました。</span><span class="sxs-lookup"><span data-stu-id="434d1-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="434d1-125">PHS は、オンプレミスの AD DS フォレストを、Microsoft 365 for enterprise サブスクリプションの Azure AD テナントと同期し、ユーザーアカウントとグループアカウント、およびハッシュされたバージョンのユーザーアカウントパスワードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="434d1-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="434d1-126">ディレクトリ同期を実行するために、Contoso 社では、パリデータセンター内のサーバーに Azure AD Connect ツールを展開しました。</span><span class="sxs-lookup"><span data-stu-id="434d1-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="434d1-127">Azure ad Connect を実行しているサーバーは、変更については Contoso AD DS フォレストをポーリングしてから、それらの変更を Azure AD テナントと同期します。</span><span class="sxs-lookup"><span data-stu-id="434d1-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Contoso PHS ディレクトリ同期インフラストラクチャ](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="434d1-129">ID およびデバイス アクセスの条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="434d1-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="434d1-130">Contosoは、3 つの保護レベルに対して Azure AD と Intune の[条件付きアクセス ポリシー](identity-access-policies.md)セットを作成しました。</span><span class="sxs-lookup"><span data-stu-id="434d1-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="434d1-131">*ベースライン* の保護は、すべてのユーザーアカウントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="434d1-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="434d1-132">*重要* な保護は、シニアリーダーシップおよび経営スタッフに適用されます。</span><span class="sxs-lookup"><span data-stu-id="434d1-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="434d1-133">*高度* な規制による保護は、厳しく規制されたデータにアクセスできる財務、法律、研究部門の特定のユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="434d1-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="434d1-134">Contoso identity とデバイスの条件付きアクセスポリシーの結果セットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="434d1-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Contoso 社の ID およびデバイスの条件付きアクセス ポリシー](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="434d1-136">次の手順</span><span class="sxs-lookup"><span data-stu-id="434d1-136">Next step</span></span>

<span data-ttu-id="434d1-137">Contoso 社が Microsoft エンドポイント構成マネージャーインフラストラクチャを使用して、組織全体に [現在の Windows 10 Enterprise を展開し、維持](contoso-win10.md) する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="434d1-137">Learn how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to [deploy and keep current Windows 10 Enterprise](contoso-win10.md) across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="434d1-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="434d1-138">See also</span></span>

[<span data-ttu-id="434d1-139">Microsoft 365 の ID ロードマップ</span><span class="sxs-lookup"><span data-stu-id="434d1-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="434d1-140">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="434d1-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="434d1-141">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="434d1-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
