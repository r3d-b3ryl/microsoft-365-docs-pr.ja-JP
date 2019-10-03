---
title: Contoso 社の ID
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社で、IDaaS (Identity as a Service) を活用して、従業員向けのクラウド ベース認証や、パートナーと顧客向けのフェデレーション認証を提供している方法を説明します。
ms.openlocfilehash: 5c78e8cc9235eb2ca5de091c05d1883ed6cca1b4
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369608"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="f1b06-103">Contoso 社の ID</span><span class="sxs-lookup"><span data-stu-id="f1b06-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="f1b06-104">**概要:** Contoso 社で、IDaaS (Identity as a Service) を活用して、従業員向けのクラウド ベース認証や、パートナーと顧客向けのフェデレーション認証を提供している方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="f1b06-104">**Summary:** How Contoso takes advantage of Identity as a Service (IDaaS) and provides cloud-based authentication for its employees and federated authentication for its partners and customers.</span></span>

<span data-ttu-id="f1b06-105">Microsoftは、Azure Active Directory（Azure AD）を使用して、自社のクラウド製品にIDaaS (Identity as a Service)を提供します。</span><span class="sxs-lookup"><span data-stu-id="f1b06-105">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="f1b06-106">Microsoft 365 EnterpriseEnterprise導入のため、ContosoのIDaaSソリューションは、自社運用のIDプロバイダーを利用しながら、既存の信頼できるサードパーティのIDプロバイダーと連携した認証方法を一体化させる必要がありました。</span><span class="sxs-lookup"><span data-stu-id="f1b06-106">To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="f1b06-107">ContosoのActive Directoryドメイン　サービス フォレスト</span><span class="sxs-lookup"><span data-stu-id="f1b06-107">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="f1b06-108">Contosoは、contoso.comに1つのActive Directoryドメインサービス（AD DS）フォレストを使用し、7つのサブドメイン（世界中の各地域に1つ）を使用します。</span><span class="sxs-lookup"><span data-stu-id="f1b06-108">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="f1b06-109">本社、地域ハブ オフィス、サテライト オフィスには、ローカルの認証と承認のためのドメイン コントローラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1b06-109">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="f1b06-110">図 1 では、地域ハブを含む世界各地の地域ドメインを持つ Contoso 社のフォレストを示しています。</span><span class="sxs-lookup"><span data-stu-id="f1b06-110">Figure 1 shows the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Contoso 社の世界的なフォレストとドメイン](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="f1b06-112">**図 1: Contoso 社の世界的なフォレストとドメイン**</span><span class="sxs-lookup"><span data-stu-id="f1b06-112">**Figure 1: Contoso's forest and domains worldwide**</span></span>

<span data-ttu-id="f1b06-113">Contosoは、contoso.comフォレストのアカウントとグループをMicrosoft 365の作業とサービスの認証・承認に使用したいと考えていました。</span><span class="sxs-lookup"><span data-stu-id="f1b06-113">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="f1b06-114">Contoso 社のフェデレーション認証インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="f1b06-114">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="f1b06-115">Contoso 社では次のことが可能です。</span><span class="sxs-lookup"><span data-stu-id="f1b06-115">Contoso allows:</span></span>

- <span data-ttu-id="f1b06-116">顧客は Microsoft、Facebook、または Google のメール アカウントを使用してパブリック Web サイトにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="f1b06-116">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="f1b06-117">ベンダーおよびパートナーは、LinkedIn、Salesforce、または Google のメール アカウントを使用してパートナー エクストラネットにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="f1b06-117">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="f1b06-p103">図 2 は、公開 Web サイト、パートナーのエクストラネット、および Active Directory フェデレーション サービス (AD FS) サーバーのセットを含む Contoso 社の DMZ を示しています。DMZ は、顧客、パートナー、およびインターネット サービスを含むインターネットに接続されています。</span><span class="sxs-lookup"><span data-stu-id="f1b06-p103">Figure 2 shows the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![Contoso 社の顧客とパートナーのフェデレーション認証のサポート](./media/contoso-identity/contoso-identity-fig2.png)

<span data-ttu-id="f1b06-121">**図 2: Contoso 社の顧客とパートナーのフェデレーション認証のサポート**</span><span class="sxs-lookup"><span data-stu-id="f1b06-121">**Figure 2: Contoso's support for federated authentication for customers and partners**</span></span>
 
<span data-ttu-id="f1b06-122">DMZ の AD FS サーバーは、ID のプロバイダーが提供しパブリック Web サイトにアクセスするための顧客資格情報、およびパートナー エクストラネットにアクセスするためのパートナー資格情報の認証を容易にします。</span><span class="sxs-lookup"><span data-stu-id="f1b06-122">AD FS servers in the DMZ authenticate customer credentials for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="f1b06-123">Contoso 社は、このインフラストラクチャを維持し、顧客とパートナーの認証専用にすることを決定しました。</span><span class="sxs-lookup"><span data-stu-id="f1b06-123">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD B2B and B2C solutions.</span></span> <span data-ttu-id="f1b06-124">Contoso 社の ID アーキテクトは、このインフラストラクチャから Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) および [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) ソリューションへの変換を調査しています。</span><span class="sxs-lookup"><span data-stu-id="f1b06-124">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="f1b06-125">クラウドベース認証のためのパスワードハッシュ同期によるハイブリッドID</span><span class="sxs-lookup"><span data-stu-id="f1b06-125">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="f1b06-126">Contosoは、自社運用のAD DSフォレストをMicrosoft 365クラウドリソースへの認証に活用したいと考えていました。</span><span class="sxs-lookup"><span data-stu-id="f1b06-126">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="f1b06-127">ここから、パスワードハッシュ同期（PHS）が誕生しました。</span><span class="sxs-lookup"><span data-stu-id="f1b06-127">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="f1b06-128">PHSは、自社運用のAD DSフォレストをMicrosoft 365 Enterpriseの登録のあるAzure ADテナントと同期し、ユーザーアカウントとグループアカウント、およびハッシュ化されたバージョンのユーザーアカウントパスワードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="f1b06-128">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="f1b06-129">継続的なディレクトリ同期を実行するために、ContosoはAzure AD 連携ツールをパリのデータセンター内のサーバーに展開しました。</span><span class="sxs-lookup"><span data-stu-id="f1b06-129">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> <span data-ttu-id="f1b06-130">図3は、Azure AD Connectを実行しているサーバーがContoso AD DSフォレストに変更をポーリングし、それらの変更をAzure ADテナントと同期することを示しています。</span><span class="sxs-lookup"><span data-stu-id="f1b06-130">Figure 3 shows the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Contoso 社の PHS ディレクトリ同期インフラストラクチャ](./media/contoso-identity/contoso-identity-fig4.png)
 
<span data-ttu-id="f1b06-132">**図3：ContosoのPHSディレクトリ同期インフラストラクチャ**</span><span class="sxs-lookup"><span data-stu-id="f1b06-132">**Figure 3: Contoso's PHS directory synchronization infrastructure**</span></span>


## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="f1b06-133">IDおよび機器のアクセスに対する条件付きアクセスポリシー</span><span class="sxs-lookup"><span data-stu-id="f1b06-133">Conditional access policies for identity and device access</span></span>

<span data-ttu-id="f1b06-134">Contosoは、3つの保護レベルに対して、Azure ADとIntuneの[条件付きアクセスポリシー](identity-access-policies.md)を作成しました。</span><span class="sxs-lookup"><span data-stu-id="f1b06-134">Contoso created a set of Azure AD and Intune [conditional access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="f1b06-135">**ベースライン**保護はすべてのユーザーアカウントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f1b06-135">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="f1b06-136">**選定**保護が上級幹部および幹部職員に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f1b06-136">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="f1b06-137">**高規制**保護は、高度に規制されたデータにアクセスできる財務、法務、および研究部門の特定のユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f1b06-137">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="f1b06-138">図4は、この結果得られるIDと機器の条件付きアクセスポリシーのセットを示しています。</span><span class="sxs-lookup"><span data-stu-id="f1b06-138">Figure 4 shows their resulting set of identity and device conditional access policies.</span></span>

![Contoso 社の ID とデバイスの条件付きアクセスポリシー](./media/contoso-identity/contoso-identity-fig5.png)
 
<span data-ttu-id="f1b06-140">**図4：ContosoのIDと機器の条件付きアクセスポリシー**</span><span class="sxs-lookup"><span data-stu-id="f1b06-140">**Figure 4: Contoso’s identity and device conditional access policies**</span></span>

## <a name="next-step"></a><span data-ttu-id="f1b06-141">次の手順</span><span class="sxs-lookup"><span data-stu-id="f1b06-141">Next step</span></span>

<span data-ttu-id="f1b06-142">Contoso 社が System Center Configuration Manager インフラストラクチャを利用して、現在の Windows 10 Enterprise を組織全体に展開し、維持する方法について[説明](contoso-win10.md)します。</span><span class="sxs-lookup"><span data-stu-id="f1b06-142">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1b06-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1b06-143">See also</span></span>

[<span data-ttu-id="f1b06-144">Microsoft 365 Enterprise の ID</span><span class="sxs-lookup"><span data-stu-id="f1b06-144">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="f1b06-145">展開ガイド</span><span class="sxs-lookup"><span data-stu-id="f1b06-145">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f1b06-146">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="f1b06-146">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
