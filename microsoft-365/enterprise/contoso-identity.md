---
title: Contoso 社の ID
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社で、IDaaS (Identity as a Service) を活用して、従業員向けのクラウド ベース認証や、パートナーと顧客向けのフェデレーション認証を提供している方法を説明します。
ms.openlocfilehash: dc893fb1e632cf15a612ebf13e911173933d9af3
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673213"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="9a18e-103">Contoso 社の ID</span><span class="sxs-lookup"><span data-stu-id="9a18e-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="9a18e-104">Microsoftは、Azure Active Directory（Azure AD）を使用して、自社のクラウド製品にIDaaS (Identity as a Service)を提供します。</span><span class="sxs-lookup"><span data-stu-id="9a18e-104">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="9a18e-105">Microsoft 365 EnterpriseEnterprise導入のため、ContosoのIDaaSソリューションは、自社運用のIDプロバイダーを利用しながら、既存の信頼できるサードパーティのIDプロバイダーと連携した認証方法を一体化させる必要がありました。</span><span class="sxs-lookup"><span data-stu-id="9a18e-105">To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="9a18e-106">ContosoのActive Directoryドメイン　サービス フォレスト</span><span class="sxs-lookup"><span data-stu-id="9a18e-106">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="9a18e-107">Contosoは、contoso.comに1つのActive Directoryドメインサービス（AD DS）フォレストを使用し、7つのサブドメイン（世界中の各地域に1つ）を使用します。</span><span class="sxs-lookup"><span data-stu-id="9a18e-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="9a18e-108">本社、地域ハブ オフィス、サテライト オフィスには、ローカルの認証と承認のためのドメイン コントローラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9a18e-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="9a18e-109">これは、地域ハブを含む世界のさまざまな地域の地域ドメインを持つ Contoso フォレストです。</span><span class="sxs-lookup"><span data-stu-id="9a18e-109">Here is the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Contoso 社の世界中のフォレストとドメイン](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="9a18e-111">Contosoは、contoso.comフォレストのアカウントとグループをMicrosoft 365の作業とサービスの認証・承認に使用したいと考えていました。</span><span class="sxs-lookup"><span data-stu-id="9a18e-111">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="9a18e-112">Contoso 社のフェデレーション認証インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="9a18e-112">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="9a18e-113">Contoso 社では次のことが可能です。</span><span class="sxs-lookup"><span data-stu-id="9a18e-113">Contoso allows:</span></span>

- <span data-ttu-id="9a18e-114">顧客は Microsoft、Facebook、または Google のメール アカウントを使用してパブリック Web サイトにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="9a18e-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="9a18e-115">ベンダーおよびパートナーは、LinkedIn、Salesforce、または Google のメール アカウントを使用してパートナー エクストラネットにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="9a18e-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="9a18e-p103">これは、公開 Web サイト、パートナーのエクストラネット、および Active Directory フェデレーション サービス (AD FS) サーバーのセットを含む Contoso 社の DMZ です。DMZ は、顧客、パートナー、およびインターネット サービスを含むインターネットに接続されています。</span><span class="sxs-lookup"><span data-stu-id="9a18e-p103">Here is the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![Contoso 社の顧客とパートナー向けのフェデレーション認証のサポート](./media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="9a18e-119">DMZ の AD FS サーバーは、ID のプロバイダーが提供しパブリック Web サイトにアクセスするための顧客資格情報、およびパートナー エクストラネットにアクセスするためのパートナー資格情報の認証を容易にします。</span><span class="sxs-lookup"><span data-stu-id="9a18e-119">AD FS servers in the DMZ facilitate the authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="9a18e-p104">Contoso 社は、このインフラストラクチャを維持し、顧客とパートナーの認証専用で使用することに決定しました。Contoso 社の ID 設計者は、このインフラストラクチャから Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) および [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) ソリューションへの変換を調査中です。</span><span class="sxs-lookup"><span data-stu-id="9a18e-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="9a18e-122">クラウドベース認証のためのパスワードハッシュ同期によるハイブリッドID</span><span class="sxs-lookup"><span data-stu-id="9a18e-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="9a18e-123">Contosoは、自社運用のAD DSフォレストをMicrosoft 365クラウドリソースへの認証に活用したいと考えていました。</span><span class="sxs-lookup"><span data-stu-id="9a18e-123">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="9a18e-124">ここから、パスワードハッシュ同期（PHS）が誕生しました。</span><span class="sxs-lookup"><span data-stu-id="9a18e-124">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="9a18e-125">PHSは、自社運用のAD DSフォレストをMicrosoft 365 Enterpriseの登録のあるAzure ADテナントと同期し、ユーザーアカウントとグループアカウント、およびハッシュ化されたバージョンのユーザーアカウントパスワードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9a18e-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="9a18e-126">継続的なディレクトリ同期を実行するために、ContosoはAzure AD 連携ツールをパリのデータセンター内のサーバーに展開しました。</span><span class="sxs-lookup"><span data-stu-id="9a18e-126">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> 

<span data-ttu-id="9a18e-127">これは、変更のために Contoso AD DS フォレストをポーリングし、それらの変更を Azure AD テナントと同期する Azure AD Connect を実行しているサーバーです。</span><span class="sxs-lookup"><span data-stu-id="9a18e-127">Here is the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Contoso 社の PHS ディレクトリ同期インフラストラクチャ](./media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="9a18e-129">ID およびデバイス アクセスの条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="9a18e-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="9a18e-130">Contosoは、3 つの保護レベルに対して Azure AD と Intune の[条件付きアクセス ポリシー](identity-access-policies.md)セットを作成しました。</span><span class="sxs-lookup"><span data-stu-id="9a18e-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="9a18e-131">**ベースライン**保護はすべてのユーザーアカウントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9a18e-131">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="9a18e-132">**選定**保護が上級幹部および幹部職員に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9a18e-132">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="9a18e-133">**高規制**保護は、高度に規制されたデータにアクセスできる財務、法務、および研究部門の特定のユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9a18e-133">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="9a18e-134">これが、Contoso 社が結果として得られる ID およびデバイスの条件付きアクセス ポリシーのセットです。</span><span class="sxs-lookup"><span data-stu-id="9a18e-134">Here is Contoso's resulting set of identity and device Conditional Access policies.</span></span>

![Contoso 社の ID およびデバイスの条件付きアクセス ポリシー](./media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="9a18e-136">次の手順</span><span class="sxs-lookup"><span data-stu-id="9a18e-136">Next step</span></span>

<span data-ttu-id="9a18e-137">Contoso 社が Configuration Manager インフラストラクチャを利用して、現在の Windows 10 Enterprise を組織全体に展開し、維持する方法について[説明](contoso-win10.md)します。</span><span class="sxs-lookup"><span data-stu-id="9a18e-137">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a18e-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a18e-138">See also</span></span>

[<span data-ttu-id="9a18e-139">Microsoft 365 Enterprise の ID</span><span class="sxs-lookup"><span data-stu-id="9a18e-139">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="9a18e-140">展開ガイド</span><span class="sxs-lookup"><span data-stu-id="9a18e-140">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9a18e-141">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="9a18e-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
