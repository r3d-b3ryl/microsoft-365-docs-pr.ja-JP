---
title: 手順 3. エンタープライズ テナント用の Microsoft 365 の ID
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Microsoft 365 テナントに適切な ID モデルを展開し、強力なユーザー サインインを適用します。
ms.openlocfilehash: 18d950bcca0c4f24e4777d0e29bd8e319d0de77f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920870"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="31d62-104">手順 3. </span><span class="sxs-lookup"><span data-stu-id="31d62-104">Step 3.</span></span> <span data-ttu-id="31d62-105">エンタープライズ テナント用の Microsoft 365 の ID</span><span class="sxs-lookup"><span data-stu-id="31d62-105">Identity for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="31d62-106">Microsoft 365 テナントには、サインインの ID と認証を管理するための Azure Active Directory (Azure AD) テナントが含まれています。組織の Microsoft 365 ユーザー アクセスとアクセス許可を管理するには、ID インフラストラクチャを正しく構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31d62-106">Your Microsoft 365 tenant includes an Azure Active Directory (Azure AD) tenant to manage identities and authentication for sign-ins. Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

## <a name="cloud-only-vs-hybrid"></a><span data-ttu-id="31d62-107">クラウド専用とハイブリッド</span><span class="sxs-lookup"><span data-stu-id="31d62-107">Cloud-only vs. hybrid</span></span>

<span data-ttu-id="31d62-108">ID モデルの 2 種類と、最適な適合と利点を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31d62-108">Here are the two types of identity models and their best fit and benefits.</span></span>


| <span data-ttu-id="31d62-109">モデル</span><span class="sxs-lookup"><span data-stu-id="31d62-109">Model</span></span> | <span data-ttu-id="31d62-110">説明</span><span class="sxs-lookup"><span data-stu-id="31d62-110">Description</span></span> | <span data-ttu-id="31d62-111">Microsoft 365 がユーザー資格情報を認証する方法</span><span class="sxs-lookup"><span data-stu-id="31d62-111">How Microsoft 365 authenticates user credentials</span></span> | <span data-ttu-id="31d62-112">最適シナリオ</span><span class="sxs-lookup"><span data-stu-id="31d62-112">Best for</span></span> | <span data-ttu-id="31d62-113">最大のメリット</span><span class="sxs-lookup"><span data-stu-id="31d62-113">Greatest benefit</span></span> |
|:-------|:-----|:-----|:-----|:-----|
| <span data-ttu-id="31d62-114">クラウド専用</span><span class="sxs-lookup"><span data-stu-id="31d62-114">Cloud-only</span></span> | <span data-ttu-id="31d62-115">ユーザー アカウントは、Microsoft 365 テナントの Azure ADテナントにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="31d62-115">User account only exists in the Azure AD tenant for your Microsoft 365 tenant.</span></span> | <span data-ttu-id="31d62-116">Microsoft 365 ADの Azure クライアント テナントは、クラウド ID アカウントを使用して認証を実行します。</span><span class="sxs-lookup"><span data-stu-id="31d62-116">The Azure AD tenant for your Microsoft 365 tenant performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="31d62-117">DS を使用するオンプレミスの組織または必要AD組織。</span><span class="sxs-lookup"><span data-stu-id="31d62-117">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="31d62-118">使いやすい。</span><span class="sxs-lookup"><span data-stu-id="31d62-118">Simple to use.</span></span> <span data-ttu-id="31d62-119">追加のディレクトリ ツールやサーバーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="31d62-119">No extra directory tools or servers required.</span></span> |
| <span data-ttu-id="31d62-120">ハイブリッド</span><span class="sxs-lookup"><span data-stu-id="31d62-120">Hybrid</span></span> |  <span data-ttu-id="31d62-121">ユーザー アカウントはオンプレミスの Active Directory ドメイン サービス (AD DS) に存在し、コピーは Microsoft 365 テナントの Azure AD テナントにも存在します。</span><span class="sxs-lookup"><span data-stu-id="31d62-121">User account exists in your on-premises Active Directory Domain Services (AD DS) and a copy is also in the Azure AD tenant for your Microsoft 365 tenant.</span></span> <span data-ttu-id="31d62-122">Azure AD接続は、オンプレミス サーバー上で実行され、DS ADを Azure ADテナントに同期します。</span><span class="sxs-lookup"><span data-stu-id="31d62-122">Azure AD Connect runs on an on-premises server to synchronize AD DS changes to your Azure AD tenant.</span></span> <span data-ttu-id="31d62-123">Azure ADのユーザー アカウントには、既にハッシュされた DS ユーザー アカウント のパスワードADが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="31d62-123">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> | <span data-ttu-id="31d62-124">Microsoft 365 ADの Azure クライアント テナントは、認証プロセスを処理するか、ユーザーを別の ID プロバイダーにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="31d62-124">The Azure AD tenant for your Microsoft 365 tenant either handles the authentication process or redirects the user to another identity provider.</span></span> | <span data-ttu-id="31d62-125">DS または別AD ID プロバイダーを使用している組織。</span><span class="sxs-lookup"><span data-stu-id="31d62-125">Organizations using AD DS or another identity provider.</span></span> | <span data-ttu-id="31d62-126">ユーザーは、オンプレミスまたはクラウドベースのリソースにアクセスするときに同じ資格情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="31d62-126">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||||

<span data-ttu-id="31d62-127">クラウド専用 ID の基本的なコンポーネントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="31d62-127">Here are the basic components of cloud-only identity.</span></span>
 
![クラウド専用 ID の基本的なコンポーネント](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="31d62-129">この図では、オンプレミスユーザーとリモート ユーザーは、Microsoft 365 テナントの Azure ADアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="31d62-129">In this illustration, on-premises and remote users sign in with accounts in the Azure AD tenant of their Microsoft 365 tenant.</span></span>

<span data-ttu-id="31d62-130">ハイブリッド ID の基本的なコンポーネントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="31d62-130">Here are the basic components of hybrid identity.</span></span>

![ハイブリッド ID の基本的なコンポーネント](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="31d62-132">AD この図では、オンプレミスユーザーとリモート ユーザーは、オンプレミスの DS からコピーされた Azure AD テナントのアカウントを使用して Microsoft 365 テナントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="31d62-132">In this illustration, on-premises and remote users sign in to their Microsoft 365 tenant with accounts in the Azure AD tenant that have been copied from their on-premises AD DS.</span></span>

## <a name="synchronizing-your-on-premises-ad-ds"></a><span data-ttu-id="31d62-133">オンプレミスの DS のADする</span><span class="sxs-lookup"><span data-stu-id="31d62-133">Synchronizing your on-premises AD DS</span></span>

<span data-ttu-id="31d62-134">ビジネス ニーズと技術的要件に応じて、ハイブリッド ID モデルとディレクトリ同期は、Microsoft 365 を採用している企業のお客様にとって最も一般的な選択肢です。</span><span class="sxs-lookup"><span data-stu-id="31d62-134">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="31d62-135">ディレクトリ同期を使用すると、AD DS の ID を管理し、ユーザー アカウント、グループ、連絡先に対する更新はすべて、Microsoft 365 テナントの Azure AD テナントに同期されます。</span><span class="sxs-lookup"><span data-stu-id="31d62-135">Directory synchronization allows you to manage identities in your AD DS and all updates to user accounts, groups, and contacts are synchronized to the Azure AD tenant of your Microsoft 365 tenant.</span></span>

>[!Note]
><span data-ttu-id="31d62-136">DS ADが初めて同期される場合、Microsoft 365 ライセンスが自動的に割り当てられるのではなく、電子メールなどの Microsoft 365 サービスにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="31d62-136">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="31d62-137">最初に使用場所を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="31d62-137">You must first assign them a usage location.</span></span> <span data-ttu-id="31d62-138">次に、グループ メンバーシップを使用して、個別または動的にこれらのユーザー アカウントにライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="31d62-138">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

<span data-ttu-id="31d62-139">ハイブリッド ID モデルを使用する場合の 2 種類の認証を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31d62-139">Here are the two types of authentication when using the hybrid identity model.</span></span>

| <span data-ttu-id="31d62-140">認証の種類</span><span class="sxs-lookup"><span data-stu-id="31d62-140">Authentication type</span></span> | <span data-ttu-id="31d62-141">説明</span><span class="sxs-lookup"><span data-stu-id="31d62-141">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="31d62-142">管理された認証</span><span class="sxs-lookup"><span data-stu-id="31d62-142">Managed authentication</span></span> | <span data-ttu-id="31d62-143">Azure ADは、ローカルに保存されたハッシュ バージョンのパスワードを使用して認証プロセスを処理するか、オンプレミスのソフトウェア エージェントに資格情報を送信して、オンプレミスの AD DS によって認証されます。</span><span class="sxs-lookup"><span data-stu-id="31d62-143">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span> <br> <br>  <span data-ttu-id="31d62-144">管理認証には、パスワード ハッシュ同期 (PHS) とパススルー認証 (PTA) の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="31d62-144">There are two types of managed authentication: Password hash synchronization (PHS) and Pass-through authentication (PTA).</span></span> <span data-ttu-id="31d62-145">PHS を使用すると、Azure AD認証自体が実行されます。</span><span class="sxs-lookup"><span data-stu-id="31d62-145">With PHS, Azure AD performs the authentication itself.</span></span> <span data-ttu-id="31d62-146">PTA を使用すると、Azure AD DS AD認証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="31d62-146">With PTA, Azure AD has AD DS perform the authentication.</span></span> |
| <span data-ttu-id="31d62-147">フェデレーション認証</span><span class="sxs-lookup"><span data-stu-id="31d62-147">Federated authentication</span></span> | <span data-ttu-id="31d62-148">Azure AD認証を要求するクライアント コンピューターを別の ID プロバイダーにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="31d62-148">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span> |
|  |  |

<span data-ttu-id="31d62-149">詳細 [については、「適切な認証方法の選択](/azure/active-directory/hybrid/choose-ad-authn) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31d62-149">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>

## <a name="enforcing-strong-sign-ins"></a><span data-ttu-id="31d62-150">強力なサインインのエンフォース</span><span class="sxs-lookup"><span data-stu-id="31d62-150">Enforcing strong sign-ins</span></span>

<span data-ttu-id="31d62-151">ユーザー サインインのセキュリティを強化するには、次の表の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="31d62-151">To increase the security of user sign-ins, use the features and capabilities in the following table.</span></span>

| <span data-ttu-id="31d62-152">機能</span><span class="sxs-lookup"><span data-stu-id="31d62-152">Capability</span></span> | <span data-ttu-id="31d62-153">説明</span><span class="sxs-lookup"><span data-stu-id="31d62-153">Description</span></span> | <span data-ttu-id="31d62-154">詳細情報</span><span class="sxs-lookup"><span data-stu-id="31d62-154">More information</span></span> | <span data-ttu-id="31d62-155">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="31d62-155">Licensing requirements</span></span> |
|:-------|:-----|:-----|:-----|:-----|
| <span data-ttu-id="31d62-156">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="31d62-156">Windows Hello for Business</span></span> | <span data-ttu-id="31d62-157">Windows デバイスに署名するときに、パスワードを強力な 2 要素認証に置き換える。</span><span class="sxs-lookup"><span data-stu-id="31d62-157">Replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="31d62-158">この 2 要素認証は、デバイスと生体認証または PIN に関連付けられる新しい種類のユーザー資格情報です。</span><span class="sxs-lookup"><span data-stu-id="31d62-158">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span> | [<span data-ttu-id="31d62-159">Windows Hello for Business の概要</span><span class="sxs-lookup"><span data-stu-id="31d62-159">Windows Hello for Business Overview</span></span>](/windows/security/identity-protection/hello-for-business/hello-overview) | <span data-ttu-id="31d62-160">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="31d62-160">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="31d62-161">Azure AD パスワード保護</span><span class="sxs-lookup"><span data-stu-id="31d62-161">Azure AD Password Protection</span></span> | <span data-ttu-id="31d62-162">既知の脆弱なパスワードとそのバリアントを検出してブロックし、組織に固有の追加の弱い用語をブロックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="31d62-162">Detects and blocks known weak passwords and their variants and can also block additional weak terms that are specific to your organization.</span></span> | [<span data-ttu-id="31d62-163">Azure ADパスワード保護を構成する</span><span class="sxs-lookup"><span data-stu-id="31d62-163">Configure Azure AD password protection</span></span>](/azure/active-directory/authentication/concept-password-ban-bad) | <span data-ttu-id="31d62-164">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="31d62-164">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="31d62-165">多要素認証 (MFA) を使用する</span><span class="sxs-lookup"><span data-stu-id="31d62-165">Use multi-factor authentication (MFA)</span></span> | <span data-ttu-id="31d62-166">MFA では、ユーザー サインインは、スマートフォン アプリでの検証やスマートフォンに送信されるテキスト メッセージなど、ユーザー アカウントのパスワードを超えた追加の検証の対象となる必要があります。</span><span class="sxs-lookup"><span data-stu-id="31d62-166">MFA requires that user sign-ins be subject to an additional verification beyond the user account password, such as verification with a smartphone app or a text message sent to a smartphone.</span></span> <span data-ttu-id="31d62-167">ユーザー [が MFA を](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) 設定する方法については、このビデオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31d62-167">See [this video](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) for instructions on how users set up MFA.</span></span> | [<span data-ttu-id="31d62-168">エンタープライズ向け Microsoft 365 の MFA</span><span class="sxs-lookup"><span data-stu-id="31d62-168">MFA for Microsoft 365 for enterprise</span></span>](../enterprise/microsoft-365-secure-sign-in.md#mfa) | <span data-ttu-id="31d62-169">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="31d62-169">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="31d62-170">ID とデバイスのアクセス構成</span><span class="sxs-lookup"><span data-stu-id="31d62-170">Identity and device access configurations</span></span> | <span data-ttu-id="31d62-171">推奨される前提条件機能とその設定と条件付きアクセス、Intune、Azure AD Identity Protection ポリシーを組み合わせて構成される設定とポリシー。</span><span class="sxs-lookup"><span data-stu-id="31d62-171">Settings and policies that consist of recommended prerequisite features and their settings combined with Conditional Access, Intune, and Azure AD Identity Protection policies that determine whether a given access request should be granted and under what conditions.</span></span>  | [<span data-ttu-id="31d62-172">ID とデバイスのアクセス構成</span><span class="sxs-lookup"><span data-stu-id="31d62-172">Identity and device access configurations</span></span>](../security/office-365-security/microsoft-365-policies-configurations.md) | <span data-ttu-id="31d62-173">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="31d62-173">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="31d62-174">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="31d62-174">Azure AD Identity Protection</span></span> | <span data-ttu-id="31d62-175">資格情報の侵害から保護します。攻撃者がユーザーのアカウント名とパスワードを決定して、組織のクラウド サービスとデータにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="31d62-175">Protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> | [<span data-ttu-id="31d62-176">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="31d62-176">Azure AD Identity Protection</span></span>](/azure/active-directory/active-directory-identityprotection) | <span data-ttu-id="31d62-177">Microsoft 365 E5 または Microsoft 365 E3 &脅威防止アドオン</span><span class="sxs-lookup"><span data-stu-id="31d62-177">Microsoft 365 E5 or Microsoft 365 E3 with the Identity & Threat Protection add-on</span></span> |
|  |  |  |



## <a name="results-of-step-3"></a><span data-ttu-id="31d62-178">手順 3 の結果</span><span class="sxs-lookup"><span data-stu-id="31d62-178">Results of Step 3</span></span>

<span data-ttu-id="31d62-179">Microsoft 365 テナントの ID については、次の点を決定しました。</span><span class="sxs-lookup"><span data-stu-id="31d62-179">For identity for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="31d62-180">使用する ID モデル。</span><span class="sxs-lookup"><span data-stu-id="31d62-180">Which identity model to use.</span></span>
- <span data-ttu-id="31d62-181">ユーザーとデバイスへの強力なアクセスを強制する方法。</span><span class="sxs-lookup"><span data-stu-id="31d62-181">How you will enforce strong user and device access.</span></span>

<span data-ttu-id="31d62-182">新しいハイブリッド ID 要素が強調表示されたテナントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31d62-182">Here is an example a tenant with the new hybrid identity elements highlighted.</span></span>

![テナントのハイブリッド ID の例](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

<span data-ttu-id="31d62-184">この図では、テナントには次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="31d62-184">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="31d62-185">DirSync ADおよび Azure AD Connect を使用して Azure ADテナントと同期されている DS フォレストをADします。</span><span class="sxs-lookup"><span data-stu-id="31d62-185">An AD DS forest that is being synchronized with the Azure AD tenant using a DirSync server and Azure AD Connect.</span></span>
- <span data-ttu-id="31d62-186">DS フォレストからAD DS ユーザー アカウントおよび他のオブジェクトADコピー。</span><span class="sxs-lookup"><span data-stu-id="31d62-186">A copy of the AD DS user accounts and other objects from the AD DS forest.</span></span>
- <span data-ttu-id="31d62-187">ユーザー アカウントに基づいてセキュリティで保護されたユーザー サインインとアクセスを強制するための一連の条件付きアクセス ポリシー。</span><span class="sxs-lookup"><span data-stu-id="31d62-187">A set of Conditional Access policies to enforce secure user sign-ins and access based on the user account.</span></span> 

## <a name="ongoing-maintenance-for-identity"></a><span data-ttu-id="31d62-188">ID の継続的なメンテナンス</span><span class="sxs-lookup"><span data-stu-id="31d62-188">Ongoing maintenance for identity</span></span>

<span data-ttu-id="31d62-189">継続的に、次の必要が生じ得る場合があります。</span><span class="sxs-lookup"><span data-stu-id="31d62-189">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="31d62-190">ユーザー アカウントとグループを追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="31d62-190">Add or modify user accounts and groups.</span></span> <span data-ttu-id="31d62-191">クラウド専用 ID の場合は、Microsoft 365 管理センターや PowerShell などの Azure AD ツールを使用して、クラウドベースのユーザーとグループを維持します。</span><span class="sxs-lookup"><span data-stu-id="31d62-191">For cloud-only identity, you maintain your cloud-based users and groups with Azure AD tools such as the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="31d62-192">ハイブリッド ID の場合は、DS ツールを使用してオンプレミスのユーザーとグループAD維持します。</span><span class="sxs-lookup"><span data-stu-id="31d62-192">For hybrid identity, you maintain your on-premises users and groups with AD DS tools.</span></span>
- <span data-ttu-id="31d62-193">サインイン セキュリティ要件を適用するために、ID とデバイス アクセス構成を追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="31d62-193">Add or modify your identity and device access configuration to enforce sign-in security requirements.</span></span>

## <a name="next-step"></a><span data-ttu-id="31d62-194">次の手順</span><span class="sxs-lookup"><span data-stu-id="31d62-194">Next step</span></span>

<span data-ttu-id="31d62-195">[![手順 4.オンプレミスのサーバーとデータOffice移行する](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)</span><span class="sxs-lookup"><span data-stu-id="31d62-195">[![Step 4. Migrate your on-premises Office servers and data](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)</span></span>

<span data-ttu-id="31d62-196">移行を [続行して](tenant-management-migration.md) 、オンプレミスのサーバーとそのOffice Microsoft 365 に移行します。</span><span class="sxs-lookup"><span data-stu-id="31d62-196">Continue with [migration](tenant-management-migration.md) to migrate your on-premises Office servers and their data to Microsoft 365.</span></span>