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
ms.openlocfilehash: accd60f6699e7ebf04963213128d1ca1ffc8f7fe
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911074"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="8921f-103">Contoso 社の ID</span><span class="sxs-lookup"><span data-stu-id="8921f-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="8921f-104">Microsoft は、Azure Active Directory (Azure Active Directory) を通じてクラウド サービス全体で Identity as a Service (IDaaS) をAD。</span><span class="sxs-lookup"><span data-stu-id="8921f-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="8921f-105">Microsoft 365 for enterprise を採用するには、Contoso IDaaS ソリューションでオンプレミス ID プロバイダーを使用し、既存の信頼できるサード パーティ ID プロバイダーとのフェデレーション認証を含める必要がありました。</span><span class="sxs-lookup"><span data-stu-id="8921f-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="8921f-106">Contoso Active Directory ドメイン サービス フォレスト</span><span class="sxs-lookup"><span data-stu-id="8921f-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="8921f-107">Contoso は、7 つのサブドメインを持つ contoso com の単一の Active Directory ドメイン サービス (DS) フォレスト (AD DS) を使用します。1 つは世界の各地域に \. 1 つです。</span><span class="sxs-lookup"><span data-stu-id="8921f-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="8921f-108">本社、地域ハブ オフィス、サテライト オフィスには、ローカルの認証と承認のためのドメイン コントローラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8921f-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="8921f-109">地域ハブを含む世界の各地域の地域ドメインを持つ Contoso フォレストを次に示します。</span><span class="sxs-lookup"><span data-stu-id="8921f-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Contoso 社の世界中のフォレストとドメイン](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="8921f-111">Contoso 社は、Microsoft 365 ワークロードとサービスの認証と承認に contoso com フォレスト内のアカウントとグループ \. を使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="8921f-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="8921f-112">Contoso フェデレーション認証インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="8921f-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="8921f-113">Contoso 社では次のことが可能です。</span><span class="sxs-lookup"><span data-stu-id="8921f-113">Contoso allows:</span></span>

- <span data-ttu-id="8921f-114">お客様は、Microsoft、Facebook、または Google メール アカウントを使用して、会社のパブリック Web サイトにサインインします。</span><span class="sxs-lookup"><span data-stu-id="8921f-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="8921f-115">ベンダーとパートナーは、LinkedIn、Salesforce、または Google メール アカウントを使用して、会社のパートナーエクストラネットにサインインします。</span><span class="sxs-lookup"><span data-stu-id="8921f-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="8921f-116">パブリック Web サイト、パートナー エクストラネット、および Active Directory フェデレーション サービス (FS) サーバーのセットを含む Contoso DMZ をADします。</span><span class="sxs-lookup"><span data-stu-id="8921f-116">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="8921f-117">DMZ は、顧客、パートナー、およびインターネット サービスを含むインターネットに接続されています。</span><span class="sxs-lookup"><span data-stu-id="8921f-117">The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![顧客とパートナーのフェデレーション認証に対する Contoso のサポート](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="8921f-119">AD FS サーバーを使用すると、パブリック Web サイトにアクセスするための ID プロバイダーによる顧客資格情報の認証と、パートナーエクストラネットへのアクセスのためのパートナー資格情報の認証が容易になります。</span><span class="sxs-lookup"><span data-stu-id="8921f-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="8921f-120">Contoso 社は、このインフラストラクチャを維持し、顧客とパートナー認証に使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="8921f-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication.</span></span> <span data-ttu-id="8921f-121">Contoso 社の ID アーキテクトは、このインフラストラクチャから Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) および [B2C](/azure/active-directory-b2c/solution-articles) ソリューションへの変換を調査しています。</span><span class="sxs-lookup"><span data-stu-id="8921f-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) and [B2C](/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="8921f-122">クラウドベース認証のためのパスワードハッシュ同期によるハイブリッドID</span><span class="sxs-lookup"><span data-stu-id="8921f-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="8921f-123">Contoso 社は、Microsoft 365 クラウド リソースADにオンプレミスの DS フォレストを使用したいと考えた。</span><span class="sxs-lookup"><span data-stu-id="8921f-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="8921f-124">パスワード ハッシュ同期 (PHS) の使用を決定しました。</span><span class="sxs-lookup"><span data-stu-id="8921f-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="8921f-125">PHS は、エンタープライズ サブスクリプションの Microsoft 365 の Azure AD テナントとオンプレミスの AD DS フォレストを同期し、ユーザー アカウントとグループ アカウント、およびハッシュ化されたバージョンのユーザー アカウント パスワードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="8921f-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="8921f-126">ディレクトリ同期を行うには、Contoso 社は Azure AD Connect ツールをパリ データセンター内のサーバーに展開しました。</span><span class="sxs-lookup"><span data-stu-id="8921f-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="8921f-127">Azure AD Connect を実行しているサーバーは、Contoso AD DS フォレストをポーリングして変更を Azure AD テナントと同期します。</span><span class="sxs-lookup"><span data-stu-id="8921f-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Contoso PHS ディレクトリ同期インフラストラクチャ](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="8921f-129">ID およびデバイス アクセスの条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="8921f-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="8921f-130">Contosoは、3 つの保護レベルに対して Azure AD と Intune の[条件付きアクセス ポリシー](../security/office-365-security/identity-access-policies.md)セットを作成しました。</span><span class="sxs-lookup"><span data-stu-id="8921f-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](../security/office-365-security/identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="8921f-131">*ベースライン* 保護は、すべてのユーザー アカウントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8921f-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="8921f-132">*機密性の* 高い保護は、上級リーダーシップとエグゼクティブ スタッフに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8921f-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="8921f-133">*規制の厳* しい保護は、規制の厳しいデータにアクセスできる財務部門、法務部門、研究部門の特定のユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8921f-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="8921f-134">Contoso ID ポリシーとデバイス条件付きアクセス ポリシーのセットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="8921f-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Contoso 社の ID およびデバイスの条件付きアクセス ポリシー](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="8921f-136">次の手順</span><span class="sxs-lookup"><span data-stu-id="8921f-136">Next step</span></span>

<span data-ttu-id="8921f-137">Contoso 社が Microsoft Endpoint Configuration Manager インフラストラクチャを使用して、組織全体に [現在の Windows 10 Enterprise](contoso-win10.md) を展開して維持する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8921f-137">Learn how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to [deploy and keep current Windows 10 Enterprise](contoso-win10.md) across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="8921f-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="8921f-138">See also</span></span>

[<span data-ttu-id="8921f-139">Microsoft 365 の ID ロードマップ</span><span class="sxs-lookup"><span data-stu-id="8921f-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="8921f-140">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="8921f-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="8921f-141">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="8921f-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)